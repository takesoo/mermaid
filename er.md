```mermaid
erDiagram

organizations {
  id PrimaryKey
  name String
}

members {
  id PrimaryKey
  organization_id ForeignKey
  name String
  email String
}

roles {
  id PrimaryKey
  organization_id ForeignKey
  name String
  note String
  grant_kind Enum
}

offices {
  id PrimaryKey
  organization_id ForeignKey
  name String
  member_id ForeignKey
}

role_offices {
  id PrimaryKey
  role_id ForeignKey
  office_id ForeignKey
}

organizations ||--o{ members: ""
organizations ||--o{ roles: ""
organizations ||--o{ offices: ""
roles ||--o{ members: ""
roles ||--o{ role_offices: ""
offices ||--o{ role_offices: ""
members ||--o{ offices: "事業所責任者"

```

## 制限事項
- 日本語が使えない
- ()が使えない
- ２列構成を崩してはいけない
- 変更中をどう表現するか（gitで履歴管理されるのでそもそもする必要あるか）

