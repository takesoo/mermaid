```mermaid
erDiagram

organizations {
  integer id PK
  string name
}

%% コメントはこうして残せます
members {
  integer id PK
  integer organization_id FK
  string name
  string email
}

roles {
  integer id PK
  integer organization_id FK
  string name
  string note
  integer grant_kind
}

offices {
  integer id PK
  integer organization_id FK
  string name
  integer member_id FK
}

role_offices {
  integer id PK
  integer role_id FK
  integer office_id FK
}

organizations ||--o{ members: ""
organizations ||--o{ roles: ""
organizations ||--o{ offices: ""
roles ||--o{ members: ""
roles ||--o{ role_offices: ""
offices ||--o{ role_offices: ""
members ||--o{ offices: ""

```

## 制限事項
- ""の外では英語以外は使用できない
- 属性にコメントを付けるとGithub上では表示に失敗する
- Github上では表示が崩れる
- 変更中をどう表現するか（gitで履歴管理されるのでそもそもする必要あるか）
- コンフリクトがどれほど発生するかは懸念点

## ドキュメント
[ドキュメント](https://mermaid-js.github.io/mermaid/#/)
