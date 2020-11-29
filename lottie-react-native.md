## 結論

useRefを使いましょう

## やりたかったこと

React Nativeでいいねボタンを押した時に、以下のようなオシャレなアニメーションをつけたくなりました。

gif入れる

## Lottieを使うことにする

自作は辛いので調べているとこちらの記事の内容がドンピシャだったので、Lottieを使うことに決めました。

【React Native】【Expo】 Lottieでおしゃれなアニメーションを簡単に実現 - React Native Tech Blog https://tech.maricuru.com/entry/2018/04/11/120523

## lottie-react-nativeの実装例を探す

React Nativeでlottieを使うにはlottie-react-nativeが便利です。

以下のリポジトリや記事を参照しながら実装例を探していきました。

* [lottie-react-native/lottie-react-native](https://github.com/lottie-react-native/lottie-react-native)

* [Expo Lottie Docs](https://docs.expo.io/versions/latest/sdk/lottie)

* [【React Native】【Expo】 Lottieでおしゃれなアニメーションを簡単に実現 ](https://tech.maricuru.com/entry/2018/04/11/120523)

* [Lottieを使ってReactNativeアプリにアニメーションを追加する](https://qiita.com/tamago3keran/items/c286ec811510227e7b51)

* [React NativeにLottieアニメーションを実装したときに苦労した3つのこと](https://qiita.com/tamago3keran/items/3225eee8c7bf99413d2a)

## あれ？どれもClass Componentばかりだぞ...？

ここまで調べてきたところ、
Class Componentのインスタンスにanimationの参照をもたせている実装例ばかりです。

## 意地でもFunctional Componentで書きたい

既存のコンポーネントをガッツリFunctional Componentで書いてしまっていたので、
ここからClass Componentに書き換えるのは面倒です。何とか実現できる方法を探しました。

## Stackoverflowで良い質問を見つける

[useRef hooks doesn't work with lottie-react-native(https://stackoverflow.com/questions/58283848/useref-hooks-doesnt-work-with-lottie-react-native)

どうやらReact Hooksの機能の一つであるuseRefを使えばDOMの参照を取得できるので、
クラスを書かずに済みそうです。

Reactの公式ドキュメントでも紹介されていますね。
https://ja.reactjs.org/docs/hooks-reference.html#useref

## useRefで実装した例

Expoの公式ドキュメントの内容をuseRefに書き換えたものをSnackにアップロードしました。

[lottie-react-native-useref-example(https://snack.expo.io/@masarufuruya/lottie-react-native-useref-example)

実装のイメージはこちらを参考にしてください。

## まとめ

ということでFunctional Componentで書いてしまっていたコンポーネントに、
Lottieを使ってアニメーションをつけたくなったらuseRefを使いましょう。

React Hooks便利。
