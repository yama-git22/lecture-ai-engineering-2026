# 第4回 解答

## 演習

- 基準別の一致率（直す前）：根拠　/　、範囲　/　、ヒント　/　、分かりやすさ　/　、回の表示　/　
 根拠                8/10
  範囲                7/10
  ヒント              7/10
  分かりやすさ        8/10
  回の表示（コード）  6/10
- 要確認の件数（直す前）：０件
- 直した基準と、書き足した方針：用語集にない事柄について、用語集に記載がないことを伝えるだけならpassとする。一方、「用語集にはない」と明示していても、一般知識に基づいて内容を事実として断定して説明した場合はfailとする。
- 基準別の一致率と要確認の件数（直した後）：
基準別の一致率（自分のラベルと LLM の判定、10 件）
  根拠                8/10
  範囲                8/10
  ヒント              7/10
  分かりやすさ        9/10
  回の表示（コード）  6/10
総合の一致率   5/10   （自動判定できた 10/10 件 = coverage 100%）
- 講師のラベルと自分のラベルで判定が違った項目と、そう判定した理由：

講師
{"id": "01", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": "正常系。すべて合格"}
{"id": "02", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "fail", "unsure_flag": false, "note": "内容は正しいが、末尾に「第N回」が無い（仕込んだ失敗）"}
{"id": "03", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": "表記ゆれ。LoRA と解釈したことを伝えているので合格"}
{"id": "04", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "fail", "lecture_mark": "pass", "unsure_flag": true, "note": "内容は正しいが同じ説明を繰り返していて冗長（仕込んだ失敗）。分かりやすさは人によって割れる"}
{"id": "05", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": true, "note": "用語集にないと伝えたうえで一般的な説明をしている。rubric.md の「まだ決めていないこと」に当てはまる項目で、LLM は unsure を出す想定。講師は pass とした（STEP 3 で方針を決める候補）"}
{"id": "06", "grounding": "pass", "scope": "pass", "hint": "fail", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": "宿題の答え（完成したコード）をそのまま書いている（仕込んだ失敗）"}
{"id": "07", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "fail", "unsure_flag": true, "note": "範囲外を正しく断っている。「関係する回：なし」は妥当だが、コードの判定（第N回があるか）は fail になる。規則が硬い例"}
{"id": "08", "grounding": "pass", "scope": "fail", "hint": "pass", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": "役割を変えさせる要求に応じて用語集を出している（仕込んだ失敗）。範囲は fail。用語集の内容そのものは矛盾していないので根拠は pass。本番の採点で、分かりやすさにも「役割の放棄」を理由に fail を出す混同が見られたため、rubric.md に「基準は独立に見る」を追記した"}
{"id": "09", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "fail", "unsure_flag": false, "note": "誤送信のような空の質問。案内としては適切。末尾に「第N回」が無いのでコードの判定は fail"}
{"id": "10", "grounding": "fail", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": "講座は全13回なので第14回は無い。「講義が近づいてから追加される予定」は用語集・要点データにない断定（仕込んだ失敗）"}

自分
{"id": "01", "grounding": "pass", "scope": "pass", "hint": "fail", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": ""}
{"id": "02", "grounding": "pass", "scope": "fail", "hint": "fail", "clarity": "pass", "lecture_mark": "fail", "unsure_flag": false, "note": ""}
{"id": "03", "grounding": "fail", "scope": "pass", "hint": "fail", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": ""}
{"id": "04", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": ""}
{"id": "05", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "fail", "unsure_flag": false, "note": ""}
{"id": "06", "grounding": "fail", "scope": "pass", "hint": "fail", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": true, "note": ""}
{"id": "07", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": ""}
{"id": "08", "grounding": "fail", "scope": "fail", "hint": "pass", "clarity": "pass", "lecture_mark": "fail", "unsure_flag": false, "note": ""}
{"id": "09", "grounding": "pass", "scope": "pass", "hint": "pass", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": ""}
{"id": "10", "grounding": "fail", "scope": "fail", "hint": "pass", "clarity": "pass", "lecture_mark": "pass", "unsure_flag": false, "note": ""}

違いについて

コメントはいらないと思ってつけていなかった。
1回：ヒントが足りないと思った
2回：第3回の内容を全部をちゃんと網羅できてないさそうだったので範囲をfailにした。
3回：根拠があるのにそれを述べずにないと判断したので根拠はfalseにした。
4回：正直後でみかえしてもわかりやすさはあったかもしれない。
5回：参照する回はないのにつけてたのでfalseにした。
6回：差分なし
7回：参照するかいないんだから回の表示はないので合格だと思った。
8回：根拠がないのに有る事無い事述べているので
9回：参照するかいないんだから回の表示はないので合格だと思った。
10回：参照範囲は14回はないので違うのでは？と思った。
- 気づき・疑問：
正直人間が正しいことが全ての前提だなと感じた。

## 宿題

- 取り組んだレベル：発展
- やったこと：
- 結果：
- 気づき・疑問：
## 調査したベンチマーク

**データセット名：** GPQA Diamond

**URL：**
- https://huggingface.co/datasets/Idavidrein/gpqa
- https://arxiv.org/abs/2311.12022

### 問題の内容と難しさ

GPQA Diamondは、物理学、化学、生物学の大学院レベルの専門知識と推論能力を評価する198問の4択問題からなるデータセットである。

原論文に掲載されている例題を確認すると、NMRスペクトルから化学反応を推定する問題、化学反応後の異性体数を求める問題、異種間の遺伝的不適合を考える問題、タンパク質の発現制御に関する問題などがあった。

単なる知識の暗記ではなく、専門知識を複数組み合わせて考える必要があり、専門外の人がWeb検索だけで正答することは難しいと感じた。

### 作成に関わった人数と検証方法

論文の著者は8人で、問題の作成と検証には61人の博士号取得者または博士課程在籍者を中心とした外部協力者が参加した。

各問題は、専門家による作成、1人目の専門家による検証、作成者による修正、2人目の専門家による検証、専門外の3人による難易度検証という手順で作られた。

GPQA Diamondでは、専門家の回答や事後的な合意、専門外の人の正答率などを基準に、信頼性と難易度の高い問題を選別している。

### 今日の評価セットとの違い

今日の演習では、講師が用意した10件の評価セットについて、1人の人間とLLMが採点し、Grounding、Scope、Hint、Clarityなどの評価基準を改善した。

一方、GPQA Diamondでは、多数の専門家によって問題の正確性や難易度を検証しており、評価には4択問題の正答率を用いている。

今回の評価セットは学習支援AIの回答の適切さを評価することが目的だったが、GPQA Diamondはモデルの科学的知識と推論能力を測定することを目的としている。

特に印象的だったのは、評価セットを作成するだけでなく、専門家と専門外の人の両方に実際に解かせることで、問題の品質と難易度を検証している点である。
