# システム外部環境

---

## ビジネスコンテキスト

このダイアグラムではシステム化対象の最上位のビジネス単位を明らかにします。

```plantuml
@startuml
' 配置図を利用します。

' 要素
node 所属組織 {
    actor 関係者1
}
actor 関係者2
frame 業務 {
    frame 業務詳細
}

' 関連
関係者1 - 業務
業務詳細 - 関係者2

@enduml
```

---

### ビジネスユースケース

ビジネスユースケースは、ビジネスコンテキスト上の各業務を、それぞれさらにブレイクダウンした形で記述します。

```plantuml
@startuml
' 配置図を利用します。

' 要素
node 所属組織 {
    actor 関係者
}
frame 業務 {
    frame 業務詳細
}

' 関連
関係者 - 業務

@enduml
```

---

### バリエーション

ビジネスの現場で使われているルールがビジネスルールです。
ビジネスルールの元になる「バリエーション」と、その組み合わでである「条件」を記述します。

```plantuml
@startuml
' honkit の uml plugin は map に対応していないので、map ではなく、object で表現しています。
' map CapitalCity {
'  UK => London
'  USA => Washington
'  Germany => Berlin
' }

skinparam object {
    BackgroundColor<<条件>> LightCyan
}

object バリエーション1 {
  バリエーション1-1
  --
  バリエーション1-2
}
object バリエーション2 {
  バリエーション2-1
  --
  バリエーション2-2
}

object 条件<<条件>> {
  条件1
  --
  条件2
  --
  条件3
  --
  条件4
}

バリエーション1 -- 条件
バリエーション2 -- 条件

@enduml
```
