---
title: 'Xamarin.Essentials: ジャイロスコープ'
description: Xamarin.Essentials でジャイロスコープ クラスを使用して、デバイスの 3 つのプライマリ軸の周りの回転を測定するデバイスのジャイロスコープ センサーを監視できます。
ms.assetid: DA4F968A-D988-41F5-8745-1BEE693660A1
author: jamesmontemagno
ms.author: jamont
ms.date: 05/04/2018
ms.openlocfilehash: 2f2961c6cb78293891e186e7e0f749a7aa2fb8fc
ms.sourcegitcommit: ea1dc12a3c2d7322f234997daacbfdb6ad542507
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "34783016"
---
# <a name="xamarinessentials-gyroscope"></a>Xamarin.Essentials: ジャイロスコープ

![プレリリース NuGet](~/media/shared/pre-release.png)

**ジャイロスコープ**クラスを使用して、デバイスの 3 つのプライマリ軸の周りの回転は、デバイスのジャイロスコープ センサーを監視できます。

## <a name="using-gyroscope"></a>ジャイロスコープを使用します。

クラスの Xamarin.Essentials への参照を追加します。

```csharp
using Xamarin.Essentials;
```

ジャイロスコープ機能が呼び出すことによって、`Start`と`Stop`ジャイロスコープへの変更をリッスンするメソッド。 加えた変更はを通じて送信、`ReadingChanged`イベント。 サンプルの使用方法を次に示します。

```csharp

public class GyroscopeTest
{
    // Set speed delay for monitoring changes.
    SensorSpeed speed = SensorSpeed.Ui;

    public GyroscopeTest()
    {
        // Register for reading changes.
        Gyroscope.ReadingChanged += Gyroscope_ReadingChanged;
    }

    void Gyroscope_ReadingChanged(GyroscopeChangedEventArgs e)
    {
        var data = e.Reading;
        // Process Angular Velocity X, Y, and Z
        Console.WriteLine($"Reading: X: {data.AngularVelocity.X}, Y: {data.AngularVelocity.Y}, Z: {data.AngularVelocity.Z}");
    }

    public void ToggleGyroscope()
    {
        try
        {
            if (Gyroscope.IsMonitoring)
              Gyroscope.Stop();
            else
              Gyroscope.Start(speed);
        }
        catch (FeatureNotSupportedException fnsEx)
        {
            // Feature not supported on device
        }
        catch (Exception ex)
        {
            // Other error has occurred.
        }
    }
}
```

## <a name="sensor-speedxrefxamarinessentialssensorspeed"></a>[センサー速度](xref:Xamarin.Essentials.SensorSpeed)

- **最も高速な**– (UI スレッドで返されるとは限りません) できる限り高速のセンサー データを取得します。
- **ゲーム**– ゲーム (UI スレッドで返されるとは限りません) に適したを評価します。
- **標準**– 既定のレートが画面の向きの変更に適してします。
- **Ui** – 一般的なユーザー インターフェイスの適切なを評価します。

## <a name="api"></a>API

- [ジャイロスコープ ソース コード](https://github.com/xamarin/Essentials/tree/master/Xamarin.Essentials/Gyroscope)
- [ジャイロスコープ API ドキュメント](xref:Xamarin.Essentials.Gyroscope)
