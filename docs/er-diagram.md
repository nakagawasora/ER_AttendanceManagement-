# ER図

```mermaid
erDiagram
 direction TB
 USERS {
  string user_id PK ""  
  string attendance_sheet_id  ""  
  string slack_user_id  ""  
  string output_folder_id  ""  
  string personal_info_sheet_id  ""  
  string email  ""  
  string password_hash  ""  
  string name  ""  
  datetime deleted_at  ""  
 }

 WAGE_UPGRADES {
  string wage_upgrade_id PK ""  
  string user_id FK ""  
  string project_id FK ""  
  int amount  ""  
 }

 ROLE_ALLOWANCES {
  string role_allowance_id PK ""  
  string allowance_name  ""  
  string user_id FK ""  
  int amount  ""  
  datetime deleted_at  ""  
 }

 USER_PROJECT_ASSIGNMENT {
  string user_id FK ""  
  string project_id FK ""  
 }

 PROJECTS {
  string project_id PK ""  
  string project_name  ""  
  int base_wage  ""  
  boolean is_active  ""  
  string target_user_ids  ""  
 }

 ATTENDANCE_RECORDS {
  string record_id PK ""  
  string user_id FK ""  
  string project_name  ""  
  date work_date  ""  
  string work_content  ""  
  datetime start_time  ""  
  datetime end_time  ""  
  string memo  ""  
 }

 ADMIN_WHITELIST {
  string email PK ""  
  boolean active  ""  
  string memo  ""  
 }

 USERS||--o{WAGE_UPGRADES:"時給増分設定"
 USERS||--o{ROLE_ALLOWANCES:"役職手当設定"
 USERS||--|{USER_PROJECT_ASSIGNMENT:"PJ割当"
 USERS||--o{ATTENDANCE_RECORDS:"勤怠対象"
 PROJECTS||--o{WAGE_UPGRADES:"対象PJ"
 PROJECTS||--o{USER_PROJECT_ASSIGNMENT:"割当対象"
```

[Mermaid図](https://mermaid.ai/app/projects/32b41bf4-3b5d-4352-993a-bc26c382016e/diagrams/43a2c060-f974-4a59-9250-4b46f48831af/share/invite/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJkb2N1bWVudElEIjoiNDNhMmMwNjAtZjk3NC00YTU5LTkyNTAtNGI0NmY0ODgzMWFmIiwiYWNjZXNzIjoiRWRpdCIsInB1cnBvc2UiOiJzaGFyZS1pbnZpdGUiLCJpYXQiOjE3OTMyODU5OTQsImV4cCI6MTc5NTg3Nzk5NH0.p-gCzRROSBTJjjUS_mcg2kABIP1VQAIfIaI7LXZ4zv8?entryPoint=share-modal)
