---
title: SkiaSharp 行とパス
description: この記事では、Xamarin.Forms のアプリケーションで線やグラフィックス パスを描画する SkiaSharp を使用する方法について説明し、サンプル コードを示します。
ms.prod: xamarin
ms.assetid: 316A15FE-383D-4D06-8641-BAC7EE7474CA
ms.technology: xamarin-forms
author: charlespetzold
ms.author: chape
ms.date: 03/10/2017
ms.openlocfilehash: a922f7ec91624e20a9afedb8063328bdb7a4d42d
ms.sourcegitcommit: 66682dd8e93c0e4f5dee69f32b5fc5a96443e307
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "35243754"
---
# <a name="skiasharp-lines-and-paths"></a>SkiaSharp 行とパス

_SkiaSharp を使用して行およびグラフィックス パスを描画するには_

[前のセクション](~/xamarin-forms/user-interface/graphics/skiasharp/basics/index.md)を示す、SkiaSharp`SKCanvas`クラスには、四角形、楕円、および角の丸い四角形を描画するいくつかのメソッドが含まれています。 このセクションと以降のセクションの作成とレンダリングに接続されているさまざまなクラスをカバー*グラフィックス パス*です。

グラフィックス パスは、行と SkiaSharp 内の曲線を描画する最も一般的なアプローチです。 ここを使用して、`SKPath`小さな直線のコレクションを使用して、直線を描画するオブジェクト (と呼ばれる、*ポリライン*) 数学的に定義できる曲線の描画にします。 後のセクションには、曲線でサポートされているのさまざまな種類がについて説明します`SKPath`です。

という見出しの下に表示されるこのセクションのすべてのサンプル プログラム**線およびパス**のホーム ページで、 [ **SkiaSharpFormsDemos** ](https://developer.xamarin.com/samples/xamarin-forms/SkiaSharpForms/Demos/)プログラム、し、 [**パス**](https://github.com/xamarin/xamarin-forms-samples/tree/master/SkiaSharpForms/Demos/Demos/SkiaSharpFormsDemos/Paths)ソリューションのフォルダーです。

## <a name="lines-and-stroke-capslinesmd"></a>[線とストローク キャップ](lines.md)

SkiaSharp を使用して、異なるストローク キャップを持つ行を描画する方法を説明します。

## <a name="path-basicspathsmd"></a>[パスの基礎](paths.md)

直線と曲線を組み合わせる場合の SkiaSharp SKPath オブジェクトについて説明します。

## <a name="the-path-fill-typesfill-typesmd"></a>[パスの塗りつぶしの種類](fill-types.md)

SkiaSharp パスの塗りつぶし型で実行できるさまざまな影響を検出します。

## <a name="polylines-and-parametric-equationspolylinesmd"></a>[多角形やパラメーターの式](polylines.md)

SkiaSharp を使用して、パラメーター式で指定できますいずれかの行を表示します。

## <a name="dots-and-dashesdotsmd"></a>[ドットとダッシュ](dots.md)

SkiaSharp で点線および破線を描画の複雑さをマスターします。

## <a name="finger-paintingfinger-paintmd"></a>[指による描画](finger-paint.md)

指を使用して、キャンバスに描画します。


## <a name="related-links"></a>関連リンク

- [SkiaSharp Api](https://developer.xamarin.com/api/root/SkiaSharp/)
- [SkiaSharpFormsDemos (サンプル)](https://developer.xamarin.com/samples/xamarin-forms/SkiaSharpForms/Demos/)
