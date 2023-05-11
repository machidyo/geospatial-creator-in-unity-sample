# geospatial-creator-in-unity-sample
eospatial Creator In Unityのサンプルリポジトリです。API Keyを設定することで実行できるようになります。

# 前提
- Windows11
- Android（iOSの設定を入れてありません）
- Unity 2021.3.11f1

# 利用手順
## 1. GCPの設定

1. [Google Photorealistic 3D TilesをCesium for Unityで使う方法](https://lilea.net/lab/how-to-setup-photorealistic-3d-tiles-for-cesium-for-unity/)の **APIキー取得編** を参考にして、以下a～cを実施します。
    1. プロジェクトの作成
    2. API Keyの取得
    3. Maps Tile APIの有効化
2. 1.cのMaps Tile APIの有効化と同じ要領で、ARCore APIを有効にします

## 2. Unityの設定
### 2.1 Unityプロジェクト
1. 本リポジトリからUnityプロジェクトを取得します
2. Projectを表示してAssets/Samples/ARCore Extentions/1.37.0/Geospatial Sample/ScenesのGeospatialシーンを開きます

### 2.2 Android API Keyの設定
1. Project Settingを開きます
2. XR Plug-in Managemnt → ARCore Extentions を選択します
3. 2.1で準備したKeyをAndroid API Keyに設定します
    
    ![2023-05-12_01h42_58](https://github.com/machidyo/geospatial-creator-in-unity-sample/assets/1772636/bfc7ce49-345d-4daf-b33e-c12197117f37)

### 2.3 Google Map Tiles API Keyの設定
1. HierarchyでAR GeoSpatial Creator Originを選択します
2. Insepctorを表示します
3. 2.1で準備したKeyをGoogle Map Tiles API Keyの設定を設定します
    
    ![2023-05-12_01h45_11](https://github.com/machidyo/geospatial-creator-in-unity-sample/assets/1772636/1004c4cb-16e8-4dde-8fa3-84fb51d9b66d)

4. うまくいくと以下のような形で、Sceneに渋谷の街並みが表示されるはずです
    
    ![2023-05-12_01h47_43](https://github.com/machidyo/geospatial-creator-in-unity-sample/assets/1772636/b42db473-f9ec-4e75-b08d-9e3e3e265cfc)

# 使い方
## 表示する場所の移動方法
1. HierarchyでAR GeoSpatial Creator Originを選択します
2. Insepctorを表示します
3. Latitude, Longitudeを変更することで場所が変わります
    
    ![2023-05-12_02h05_34](https://github.com/machidyo/geospatial-creator-in-unity-sample/assets/1772636/10f581d2-aba0-48f8-92f3-d937f6f803dc)

4. Heightを変更すると、その高さから見たときにちょうどいい感じに拡大縮小してくれます。例えば2000みたいな大きい値を入力すると、上空から見たときにちょうどいいサイズになるので、近すぎるとテクスチャが非常にぼやけたになり何かわからなくなります。一度ひいてみてみてください。

## オブジェクトの配置方法
1. HierarchyでAR GeoSpatial Creator Anchorを選択します
2. シーン上で矢印を操作して動かすか、InspectorのLatitude, Longitudeを変更することで、オブジェクトの位置が変わります
    
    ![2023-05-12_02h12_16](https://github.com/machidyo/geospatial-creator-in-unity-sample/assets/1772636/41c018d5-a99a-4542-a4ba-920921967f11)

## オブジェクトの変更方法
1. デフォルトではAR GeoSpatial Creator Anchorの下にCubesというオブジェクトがありますが、これを削除して、好きなものに変更してください

## Andoridでの実行方法
1. AndroidをWindowsと接続します
    1. 【注意】Androidが開発者モードでないといけないなど、諸設定があります。[こちら](https://vanikki.com/unity-android-test/)のビルド手順を参照ください
2. File → BuildSettings を開きます
3. Build And Run を押して完了を待ちます
4. 実際の場所に行ってアプリを実行します。うまくいけばオブジェクトを配置した方向を向けると、オブジェクトが表示されていると思います。
    1. 【注意】ARCoreサンプルプロジェクトをそのまま流用している関係から、表示以外の機能（Anchorの作成機能）なども実行されているため、画面をタップするとAnchorが配置されたりします。

# OSS
OSS                                                         | Licnece
------------------------------------------------------------|-------------------------------------------
[cesiumu-unity](https://github.com/CesiumGS/cesium-unity)   | Apache-2.0, Unknown licenses found
