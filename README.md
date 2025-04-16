# simple_boxbot_v1 開発ログまとめ（ChatGPT Canvasより）

このプロジェクトは、ROS 2 Humble + Gazebo環境で、単純な直方体モデルを表示し、将来的には動作制御も行えるように開発されたものです。

---

## ✅ 最終的に成功したステップ
- **URDF名**：`simple_boxbot.urdf`
- **構成要素**：直方体1つ（`base_link`）のみを表示
- **表示方法**：`robot_state_publisher` + `joint_state_publisher_gui` によるRViz表示およびGazebo表示の両方
- **確認済**：RViz表示は`robot_description`が正しく配信されており、`fixed_frame`を`base_link`に設定

---

## 🔁 開発中に遭遇した主なエラーと対処

| 内容 | 対応策 |
|------|--------|
| `robot_state_publisher` の `robot_description` が空 or Node not found | `--ros-args -p robot_description:=...` を明示的に渡して起動 |
| RVizでモデルが表示されない | Fixed Frame を `map` → `base_link` に変更（ただし変更後も未表示だった）|
| Gazeboで `/spawn_entity` サービスが未起動 | `gazebo --verbose` で起動し、`gazebo_ros_factory` Pluginを確認 |
| Gazeboの表示が遅い or 重い | 単一の直方体に絞ることで軽量化 |

---

## 💡 今後の提案

### ✅ A案（採用済）
- **軽量なシンプル構成で再スタート**
  - エラーの多い`example_4`や過去の残骸を一度クリーンアップ
  - 表示成功したモデルをベースにステップアップ方式で開発を進行
  - GitHubへのバックアップも実施済（`simple_boxbot_v1`）

### ❌ B案（見送り）
- 複雑な既存exampleを元に再構築（エラーが頻発したため中断）

---

## 🔗 参考Canvasログ一覧
- https://chatgpt.com/canvas/shared/67f7d3d226548191b1ff8118d786c445
- https://chatgpt.com/canvas/shared/67fdff415e2c81918b71d0fdcae3edbf
- https://chatgpt.com/canvas/shared/67fe023f979c8191879c7528eeebd175
- https://chatgpt.com/canvas/shared/67fdffa19bac819182c9d9e3d793850f

---

## 🗂️ GitHubリポジトリ
- https://github.com/q121p/simple_boxbot_v1

READMEや開発者向けドキュメントにこの要約をそのまま記載してもOKです。

何か追加したい点があれば教えてください！

