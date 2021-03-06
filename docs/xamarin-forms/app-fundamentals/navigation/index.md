---
title: Xamarin.Forms ナビゲーション
description: このガイドでは、Xamarin.Forms アプリでのナビゲーションを実行する方法について説明します。 Xamarin.Forms では、さまざまな使用されているページの種類に応じて、別のページ ナビゲーションのエクスペリエンスを提供します。
ms.prod: xamarin
ms.assetid: BC5D0C6C-D5A9-4B12-A492-ED1F570CEC87
ms.technology: xamarin-forms
author: davidbritch
ms.author: dabritch
ms.date: 12/01/2017
ms.openlocfilehash: 90aedee42af7ed1788110e832fb3b435d870ee77
ms.sourcegitcommit: 66682dd8e93c0e4f5dee69f32b5fc5a96443e307
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "35241957"
---
# <a name="xamarinforms-navigation"></a>Xamarin.Forms ナビゲーション

_Xamarin.Forms では、さまざまな使用されているページの種類に応じて、別のページ ナビゲーションのエクスペリエンスを提供します。_

![](images/page-types.png "Xamarin.Forms ページの種類")

## <a name="hierarchical-navigationhierarchicalmd"></a>[階層ナビゲーション](hierarchical.md)

[`NavigationPage`](https://developer.xamarin.com/api/type/Xamarin.Forms.NavigationPage/) クラスは、ユーザーが前後を希望どおりにページを移動することができる階層ナビゲーション エクスペリエンスを提供します。 このクラスは、[`Page`](https://developer.xamarin.com/api/type/Xamarin.Forms.Page/) オブジェクトの後入れ先出し (LIFO) スタックとしてナビゲーションを提供します。

## <a name="tabbedpagetabbed-pagemd"></a>[TabbedPage](tabbed-page.md)

Xamarin.Forms [ `TabbedPage` ](https://developer.xamarin.com/api/type/Xamarin.Forms.TabbedPage/)タブより大きな詳細領域の一覧、詳細領域へのコンテンツの読み込みの各タブで構成されます。

## <a name="carouselpagecarousel-pagemd"></a>[CarouselPage](carousel-page.md)

Xamarin.Forms [ `CarouselPage` ](https://developer.xamarin.com/api/type/Xamarin.Forms.CarouselPage/)ギャラリーなどのコンテンツのページ間を移動するユーザーが横方向にスワイプできますページです。

## <a name="masterdetailpagemaster-detail-pagemd"></a>[MasterDetailPage](master-detail-page.md)

Xamarin.Forms [ `MasterDetailPage` ](https://developer.xamarin.com/api/type/Xamarin.Forms.MasterDetailPage/)項目を表示するマスター ページ、およびマスター ページの項目に関する詳細情報を表示する詳細ページ 2 つのページの関連情報を管理するページです。

## <a name="modal-pagesmodalmd"></a>[モーダル ページ](modal.md)

Xamarin.Forms では、モーダルのページのサポートも提供します。 モーダル ページは、そのタスクが完了するかキャンセルされるまで、他の操作ができない自己完結型のタスクを完了させるようユーザーに促します。

## <a name="displaying-pop-upspop-upsmd"></a>[ポップアップを表示します。](pop-ups.md)

Xamarin.Forms は、次の 2 つの pop 増のようなユーザー インターフェイス要素: アラートとアクション シートです。 これらのインターフェイス要素は、単純な質問をユーザーに確認してを使用してタスクを使用してユーザーに使用できます。
