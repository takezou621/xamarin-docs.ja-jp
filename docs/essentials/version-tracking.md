---
title: 'Xamarin.Essentials: バージョン管理'
description: Xamarin.Essentials で VersionTracking クラスでは、アプリケーションのバージョンを確認することができ、ビルド番号と共に、最初にある場合は、このような追加の情報を見ることが起動するアプリケーションまたは現在のバージョンについては、前のビルドを取得情報、および詳細。
ms.assetid: 670C7E8A-E882-4AC0-97D2-A53D90ADD6A3
author: jamesmontemagno
ms.author: jamont
ms.date: 05/04/2018
ms.openlocfilehash: 2c092d6767045f0af956c5dab74801077dadb51f
ms.sourcegitcommit: ea1dc12a3c2d7322f234997daacbfdb6ad542507
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "34783003"
---
# <a name="xamarinessentials-version-tracking"></a>Xamarin.Essentials: バージョン管理

![プレリリース NuGet](~/media/shared/pre-release.png)

**VersionTracking**クラスでは、アプリケーションのバージョンを確認することができ、これまでに起動するアプリケーションまたは現在のバージョンの取得前のビルド番号と共に、最初にある場合は、このような追加情報を表示ビルド情報、および詳細。

## <a name="using-version-tracking"></a>バージョン管理を使用します。

クラスの Xamarin.Essentials への参照を追加します。

```csharp
using Xamarin.Essentials;
```

初めて使用するとき、 **VersionTracking**クラスの現在のバージョンの追跡を開始します。 呼び出す必要があります`Track`早い段階が読み込まれた現在のバージョン情報が追跡されるたびに、アプリケーションでのみ。

```csharp
VersionTracking.Track();
```

初期後`Track`が呼び出されたバージョン情報を読み取ることができます。

```csharp

// First time ever launched application
var firstLaunch = VersionTracking.IsFirstLaunchEver;

// First time launching current version
var firstLaunchCurrent = VersionTracking.IsFirstLaunchForCurrentVersion;

// First time launching current build
var firstLaunchBuild = VersionTracking.IsFirstLaunchForCurrentBuild;

// Current app version (2.0.0)
var currentVersion = VersionTracking.CurrentVersion;

// Current build (2)
var currentBuild = VersionTracking.CurrentBuild;

// Previous app version (1.0.0)
var previousVersion = VersionTracking.PreviousVersion;

// Previous app build (1)
var previousBuild = VersionTracking.PreviousBuild;

// First version of app installed (1.0.0)
var firstVersion = VersionTracking.FirstInstalledVersion;

// First build of app installed (1)
var firstBuild = VersionTracking.FirstInstalledBuild;

// List of versions installed (1.0.0, 2.0.0)
var versionHistory = VersionTracking.VersionHistory;

// List of builds installed (1, 2)
var buildHistory = VersionTracking.BuildHistory;
```

## <a name="platform-implementation-specifics"></a>プラットフォームの実装の詳細

使用してすべてのバージョン情報を格納、[設定](preferences.md)Xamarin.Essentials で API のファイル名で保存および **[、-アプリ-パッケージの ID] .xamarinessentials**です。

アプリケーションのアンインストールにより、 _LocalSettings_、および追跡情報を削除するすべてのバージョン。

## <a name="api"></a>API

- [バージョンの追跡のソース コード](https://github.com/xamarin/Essentials/tree/master/Xamarin.Essentials/VersionTracking)
- [バージョン管理の API ドキュメント](xref:Xamarin.Essentials.VersionTracking)
