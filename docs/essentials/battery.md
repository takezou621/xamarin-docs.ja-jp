---
title: 'Xamarin.Essentials: バッテリ'
description: このドキュメントでは、変更を監視し、デバイスのバッテリに関する情報を確認できる Xamarin.Essentials でバッテリ クラスについて説明します。
ms.assetid: 47EB26D8-8C62-477B-A13C-6977F74E6E43
author: jamesmontemagno
ms.author: jamont
ms.date: 05/04/2018
ms.openlocfilehash: 35764b4c2270359a7c010e1186f882e236e17fd5
ms.sourcegitcommit: ea1dc12a3c2d7322f234997daacbfdb6ad542507
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "34782087"
---
# <a name="xamarinessentials-battery"></a>Xamarin.Essentials: バッテリ

![プレリリース NuGet](~/media/shared/pre-release.png)

**バッテリ**クラスを使用して、デバイスのバッテリに関する情報を監視し、変更を確認できます。

## <a name="getting-started"></a>作業の開始

アクセスする、**バッテリ**次のプラットフォーム固有のセットアップの機能が必要です。

# <a name="androidtabandroid"></a>[Android](#tab/android)

`Battery`権限が必要と Android プロジェクトで構成する必要があります。 これは、次の方法で追加できます。

開く、 **AssemblyInfo.cs**下にあるファイル、**プロパティ**フォルダーを追加。

```csharp
[assembly: UsesPermission(Android.Manifest.Permission.Battery)]
```

または、Android のマニフェストを更新します。

開く、 **AndroidManifest.xml**下にあるファイル、**プロパティ**フォルダー内の次の追加と、**マニフェスト**ノード。

```xml
<uses-permission android:name="android.permission.BATTERY" />
```

または、Anroid プロジェクトを右クリックし、プロジェクトのプロパティを開きます。 **Android マニフェスト**検索、**権限が必要:** 領域とチェック、**バッテリ**権限です。 これは自動的に更新、 **AndroidManifest.xml**ファイル。

# <a name="iostabios"></a>[iOS](#tab/ios)

追加の設定が必要です。

# <a name="uwptabuwp"></a>[UWP](#tab/uwp)

追加の設定が必要です。

-----

## <a name="using-battery"></a>バッテリを使用します。

クラスの Xamarin.Essentials への参照を追加します。

```csharp
using Xamarin.Essentials;
```

現在のバッテリに関する情報を確認します。

```csharp
var level = Battery.ChargeLevel; // returns 0.0 to 1.0 or -1.0 if unable to determine.

var state = Battery.State;

switch (state)
{
    case BatteryState.Charging:
        // Currently charging
        break;
    case BatteryState.Full:
        // Battery is full
        break;
    case BatteryState.Discharging:
    case BatteryState.NotCharging:
        // Currently discharging battery or not being charged
        break;
    case BatteryState.NotPresent:
        // Battery doesn't exist in device (desktop computer)
    case BatteryState.Unknown:
        // Unable to detect battery state
        break;
}

var source = Battery.PowerSource;

switch (source)
{
    case BatteryPowerSource.Battery:
        // Being powered by the battery
        break;
    case BatteryPowerSource.Ac:
        // Being powered by A/C unit
        break;
    case BatteryPowerSource.Usb:
        // Being powered by USB cable
        break;
    case BatteryPowerSource.Wireless:
        // Powered via wireless charging
        break;
    case BatteryPowerSource.Unknown:
        // Unable to detect power source
        break;
}
```

バッテリのプロパティのいずれかが変更されるたびにイベントがトリガーされました。

```csharp
public class BatteryTest
{
    public BatteryTest()
    {
        // Register for battery changes, be sure to unsubscribe when needed
        Battery.BatteryChanged += Battery_BatteryChanged;
    }

    void Battery_BatteryChanged(BatteryChangedEventArgs   e)
    {
        var level = e.ChargeLevel;
        var state = e.State;
        var source = e.PowerSource;
        Console.WriteLine($"Reading: Level: {level}, State: {state}, Source: {source}");
    }
}
```

## <a name="platform-differences"></a>プラットフォームの違い

| プラットフォーム | 相違点 |
| --- | --- |
| iOS | デバイスを使用して、Api をテストする必要があります。 |
| iOS | のみは Ac またはバッテリを返します PowerSource。 |
| UWP | のみは Ac またはバッテリを返します PowerSource。 |

## <a name="api"></a>API

- [バッテリのソース コード](https://github.com/xamarin/Essentials/tree/master/Xamarin.Essentials/Battery)
- [バッテリの API ドキュメント](xref:Xamarin.Essentials.Battery)
