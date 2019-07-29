//DBにデータを保存するメソッド
    public function storeData(Request $request) {
      // 新規インスタンス作成
      $syouhinn = new Syouhinn;

      // インスタンスに受け取った値を格納
      $syouhinn->syouhinn_name = $request->syouhinn_name;
      $syouhinn->tannka = $request->tannka;
      $syouhinn->kubunn_id = $request->kubunn_id;
      $syouhinn->torihikisaki_id = $request->torihikisaki_id;

      // データベースにデータを追加
      $syouhinn->save();
    }



    // データを編集する
    public function updateData(Request $request) {

      // 指定のデータを更新
      $syouhinn = Syouhinn::where('id', $request->id)->first();

      // インスタンスに受け取った値を格納
      $syouhinn->syouhinn_name = $request->syouhinn_name;
      $syouhinn->tannka = $request->tannka;
      // TODO:区分名、取引先名の取得
      $syouhinn->kubunn_id = $request->kubunn_id;
      $syouhinn->torihikisaki_id = $request->torihikisaki_id;

      // データベースのデータを更新
      $syouhinn->save();
    }
