---
title: 'Xamarin.Essentials: ファイル システムのヘルパー'
description: Xamarin.Essentials の FileSystem のクラスには、アプリ パッケージ内でファイルを開き、アプリケーションのキャッシュおよびデータ ディレクトリを検索するヘルパーの系列が含まれています。
ms.assetid: B3EC2DE0-EFC0-410C-AF71-7410AE84CF84
author: jamesmontemagno
ms.author: jamont
ms.date: 05/04/2018
ms.openlocfilehash: 13293ec05261cbdc1e70fd278002d1af18654851
ms.sourcegitcommit: ea1dc12a3c2d7322f234997daacbfdb6ad542507
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "34782586"
---
# <a name="xamarinessentials-file-system-helpers"></a>Xamarin.Essentials: ファイル システムのヘルパー

![プレリリース NuGet](~/media/shared/pre-release.png)

**FileSystem**クラスには、アプリケーションのキャッシュおよびデータ ディレクトリを検索して、アプリ パッケージ内でファイルを開くヘルパーのシリーズが含まれています。

## <a name="using-file-system-helpers"></a>ファイル システム ヘルパーの使用

クラスの Xamarin.Essentials への参照を追加します。

```csharp
using Xamarin.Essentials;
```

格納するアプリケーションのディレクトリを取得する**データ キャッシュ**です。 すべてのデータに一時的なデータよりも長く保持する必要がありますが、正しく動作するために必要なデータをすることはできません、キャッシュ データを使用できます。

```csharp
var cacheDir = FileSystem.CacheDirectory;
```

ユーザー データ ファイルではないすべてのファイルの最上位のアプリケーションのディレクトリを取得します。 これらのファイルはフレームワークを同期しているオペレーティング システムと共にバックアップされます。 プラットフォームの実装における次を参照してください。

```csharp
var mainDir = FileSystem.AppDataDirectory;
```

アプリケーション パッケージにバンドルされているファイルを開きます。

```csharp
 using (var stream = await FileSystem.OpenAppPackageFileAsync(templateFileName))
 {
    using (var reader = new StreamReader(stream))
    {
        var fileContents = await reader.ReadToEndAsync();
    }
 }
```

## <a name="platform-implementation-specifics"></a>プラットフォームの実装の詳細

# <a name="androidtabandroid"></a>[Android](#tab/android)

- **CacheDirectory** – を返します、 [CacheDir](https://developer.android.com/reference/android/content/Context.html#getCacheDir)現在のコンテキスト。
- **AppDataDirectory** – を返します、 [FilesDir](https://developer.android.com/reference/android/content/Context.html#getFilesDir)は、現在のコンテキストのバックアップを使用して[自動バックアップ](https://developer.android.com/guide/topics/data/autobackup.html)API 23 以降を起動します。

任意のファイルを追加、**資産**フォルダーに、Android プロジェクトおよびとしてビルド アクションをマーク**AndroidAsset**と共に使用する`OpenAppPackageFileAsync`です。

# <a name="iostabios"></a>[iOS](#tab/ios)

- **CacheDirectory** – を返します、[ライブラリ/キャッシュ](https://developer.apple.com/library/content/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html)ディレクトリ。
- **AppDataDirectory** – を返します、[ライブラリ](https://developer.apple.com/library/content/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html)iTunes と iCloud でバックアップされているディレクトリ。

任意のファイルを追加、**リソース**フォルダー、iOS にプロジェクトし、としてビルド アクションをマーク**BundledResource**と共に使用する`OpenAppPackageFileAsync`です。

# <a name="uwptabuwp"></a>[UWP](#tab/uwp)

- **CacheDirectory** – を返します、 [LocalCacheFolder](https://docs.microsoft.com/en-us/uwp/api/windows.storage.applicationdata.localcachefolder#Windows_Storage_ApplicationData_LocalCacheFolder)ディレクトリ.
- **AppDataDirectory** – を返します、 [LocalFolder](https://docs.microsoft.com/en-us/uwp/api/windows.storage.applicationdata.localfolder#Windows_Storage_ApplicationData_LocalFolder)をクラウドにバックアップされるディレクトリ。

UWP プロジェクトのルートにすべてのファイルを追加し、ビルド アクションとしてのマーク**コンテンツ**と共に使用する`OpenAppPackageFileAsync`です。

--------------

## <a name="api"></a>API

- [ファイル システム ヘルパーのソース コード](https://github.com/xamarin/Essentials/tree/master/Xamarin.Essentials/FileSystem)
- [ファイル システム API ドキュメント](xref:Xamarin.Essentials.FileSystem)
