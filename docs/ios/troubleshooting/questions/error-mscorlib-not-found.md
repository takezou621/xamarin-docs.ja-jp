---
title: '実行時エラー: アセンブリ mscorlib.dll が見つからなかったか、読み込めませんでした'
ms.topic: troubleshooting
ms.prod: xamarin
ms.assetid: 1027E16C-2C14-4BB5-AAAB-342F3E28E22E
ms.technology: xamarin-ios
author: bradumbaugh
ms.author: brumbaug
ms.openlocfilehash: 1470396e782fd2343de72e9bea042f45cd07e555
ms.sourcegitcommit: 945df041e2180cb20af08b83cc703ecd1aedc6b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2018
---
# <a name="runtime-error-the-assembly-mscorlibdll-was-not-found-or-could-not-be-loaded"></a>実行時エラー: アセンブリ mscorlib.dll が見つからなかったか、読み込めませんでした

```
<Warning>: The assembly mscorlib.dll was not found or could not be loaded.
<Warning>: It should have been installed in the `/Developer/MonoTouch/Source/monotouch/builds/install/target64/lib/mono/2.0/mscorlib.dll' directory.
<Warning>: Service exited with abnormal code: 1
```

この問題が発生したときに、*非表示*`.monotouch-32`と`.monotouch-64`フォルダーが見つかりません、`.xcarchive`の署名/IPA 作成、実行時エラーをトリガーします。

