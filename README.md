# voicevox_additional_libraries

CUDA や DirectML、WebGPU など、VOICEVOX を動かすのに必要になることがあるライブラリ置き場

## 依存ライブラリの更新方法

onnxruntime のバージョンに合わせて CUDA・DirectML・cuDNN のバージョンを更新します。
現状は`download_and_deploy.yml`ファイルを直接書き換えることで更新しています。

依存する CUDA と cuDNN のバージョンは[ここ](https://onnxruntime.ai/docs/execution-providers/CUDA-ExecutionProvider.html#requirements)で確認できます。CUDA のパッチバージョンを知りたい場合は onnxruntime のコード内検索で「cuda メジャーバージョン.マイナーバージョン」辺りで検索するとヒントが見つかります。

DirectML のバージョンはリリースノートか、「Microsoft.AI.DirectML」とコード内検索すれば見つかります。

WebGPU 版で利用する DirectXShaderCompiler は、[DirectXShaderCompiler のリリース](https://github.com/microsoft/DirectXShaderCompiler/releases)から更新します。

## デプロイ方法

Release を作成するか、`download_and_deploy.yml`を workflow_dispatch で実行します。
