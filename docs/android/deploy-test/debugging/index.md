---
title: デバイスとエミュレーターで Xamarin.Android をデバッグする
description: Xamarin.Android アプリをテストおよびデバッグする方法
ms.prod: xamarin
ms.assetid: A355A471-8195-4391-93FE-0000BCB17923
ms.technology: xamarin-android
author: mgmclemore
ms.author: mamcle
ms.date: 04/25/2018
ms.openlocfilehash: a4ce36e28bd5b6dcf78d248b1f2ba951cad9b286
ms.sourcegitcommit: 0a72c7dea020b965378b6314f558bf5360dbd066
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="debugging"></a>デバッグ

このセクションでは、デバイスまたはエミュレーターで Xamarin.Android アプリをデバッグする方法について説明します。
## <a name="debugging-overview"></a>デバッグの概要

Android アプリケーションを開発するには、物理ハードウェア上で、またはエミュレーターを使用して、アプリケーションを実行する必要があります。 ハードウェアを使用するのが最適な方法ですが、常に実用的というわけではありません。 多くの場合、以下に示されるエミュレーターのいずれかを使用して、Android ハードウェアを簡単かつコスト効率良く、シミュレートまたはエミュレートすることができます。


### <a name="google-android-emulatorandroiddeploy-testdebuggingandroid-sdk-emulatorindexmd"></a>[Google Android Emulator](~/android/deploy-test/debugging/android-sdk-emulator/index.md)

これらの記事では、Android SDK で提供される既定のエミュレーターを使用する方法について説明します。 このエミュレーターは、Visual Studio for Windows と Visual Studio for Mac で使用できます。

### <a name="visual-studio-android-emulatorandroiddeploy-testdebuggingvisual-studio-android-emulatormd"></a>[Visual Studio Android Emulator](~/android/deploy-test/debugging/visual-studio-android-emulator.md)

この記事では、Visual Studio 2015 に組み込まれている Android エミュレーターを使用して、Xamarin.Android アプリをデバッグおよびテストする方法について説明します。 このエミュレーターは、Visual Studio 2015 を使用していて、カスタム デバイス プロファイルを必要としない場合に最適です。

### <a name="debugging-on-a-deviceandroiddeploy-testdebuggingdebug-on-devicemd"></a>[デバイスでのデバッグ](~/android/deploy-test/debugging/debug-on-device.md)

この記事では、物理 Android デバイスを構成して、Xamarin.Android アプリケーションを Visual Studio for Mac または Visual Studio のいずれかに直接展開する方法を説明します。

### <a name="android-debug-logandroiddeploy-testdebuggingandroid-debug-logmd"></a>[Android デバッグ ログ](~/android/deploy-test/debugging/android-debug-log.md)

開発者がアプリケーションのデバッグに使用する、よく使われるトリックに `Console.WriteLine` があります。 ただし、Android などのモバイル プラットフォームにコンソールはありません。 Android デバイスでは、アプリの書き込み中に使用する必要があることが多いログを提供します。 これは、取得するために入力するコマンドから、**logcat** と呼ばれることがあります。 この記事では、**logcat** を使用する方法について説明します。

> [!WARNING]
> 
  **Xamarin Android Player** は非推奨とされていることに注意してください。 詳細については、[このブログ投稿のお知らせ](https://blog.xamarin.com/live-from-dotnetconf-cycle-7-xamarin-studio-6-and-more/)を参照してください。
