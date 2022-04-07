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

organizations ||--o{ contract_histories: ""
organizations ||--o{ roles: ""
organizations ||--o{ members: ""
organizations ||--o{ offices: ""
organizations ||--o{ products: ""
organizations ||--o{ approvers: ""
organizations ||--o{ materials: ""
organizations ||--o{ inventory_items: ""
organizations ||--o{ notification_groups: ""
organizations ||--o{ organization_configs: ""
organizations ||--o{ partners: ""
organizations ||--o{ delivery_companies: ""
organizations ||--o{ optional_keys: ""
organizations ||--o{ freee_connections: ""
organizations ||--o{ monthly_office_sales: ""
organizations ||--o{ monthly_partner_sales: ""
organizations ||--o{ manufacturing_products: ""
organizations ||--o{ ingredients: ""

contract_histories ||--o{ option_features: ""

notification_groups ||--o{ notification_group_members: ""
notification_groups ||--o{ product_catalogs: ""

roles ||--o{ members: ""
roles ||--o{ restricted_features: ""
roles ||--o{ role_offices: ""

offices ||--o{ matters: ""
offices ||--o{ negotiations: ""
offices ||--o{ monthly_office_sale: ""
offices ||--o{ monthly_partner_sale: ""
offices ||--o{ products: ""
offices ||--o{ materials: ""
offices ||--o{ product_catalogs: ""
offices ||--o{ intraoffice_transfers: ""
offices ||--o{ request_orders: ""
offices ||--o{ record_groups: ""
offices ||--o{ select_candidates: ""
offices ||--o{ inspection_templates: ""
offices ||--o{ inspection_select_candidates: ""
offices ||--o{ arrivals: ""
offices ||--o{ partner_arrivals: ""
offices ||--o{ office_arrivals: ""
offices ||--o{ shipments: ""
offices ||--o{ partner_shipments: ""
offices ||--o{ office_shipments: ""
offices ||--o{ office_shipments_as_to_office: ""
offices ||--o{ stock_locations: ""
offices ||--o{ stock_location_tags: ""
offices ||--o{ inventory_lots: ""
offices ||--o{ inventory_histories: ""
offices ||--o{ stocktakes: ""
offices ||--o{ manufacturing_lines: ""

members ||--o{ devices: ""
members ||--o{ offices: ""
members ||--o{ product_histories: ""
members ||--o{ record_template_confirmers: ""
members ||--o{ record_template_mem_charges: ""
members ||--o{ notifiers: ""
members ||--o{ inspection_template_confirmers: ""
members ||--o{ inspection_template_mem_charges: ""
members ||--o{ comments: ""
members ||--o{ record_histories: ""
members ||--o{ inspection_histories: ""
members ||--o{ inspection_history_confirmers: ""
members ||--o{ inspection_history_mem_charges: ""
members ||--o{ product_catalogs: ""
members ||--o{ approvers: ""
members ||--o{ matters: ""
members ||--o{ negotiations: ""
members ||--o{ freee_invoices: ""
members ||--o{ arrivals: ""
members ||--o{ shipments_as_member: ""
members ||--o{ shipments_as_worker: ""
members ||--o{ office_shipments_as_to_office_staff: ""
members ||--o{ stock_locations: ""
members ||--o{ notification_group_members: ""
members ||--o{ stocktakes_as_confirmer: ""
members ||--o{ record_values: ""
members ||--o{ intraoffice_transfers_as_worker: ""

products ||--o{ product_histories: ""
products ||--o{ allowed_item_offices: ""
products ||--o{ product_catalog_products: ""
products ||--o{ matter_detail_products: ""
products ||--o{ request_order_items: ""


materials ||--o{ optional_values: ""

optional_keys ||--o{ optional_values: ""
```

## 制限事項
- ""の外では英語以外は使用できない
- 属性にコメントを付けるとGithub上では表示に失敗する
- Github上では表示が崩れる
- 変更中をどう表現するか（gitで履歴管理されるのでそもそもする必要あるか）
- コンフリクトがどれほど発生するかは懸念点

## ドキュメント
[ドキュメント](https://mermaid-js.github.io/mermaid/#/)
