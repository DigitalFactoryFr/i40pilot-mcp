# Tools

Snapshot of `tools/list` on 2026-10-24 (55 tools). The live list is authoritative. ✏️ = write tool, hidden on read-only connections.

## Show & follow (2)
- `i40pilot_show` — display a dashboard, 3D drawing, spreadsheet, Gantt… in the conversation (MCP Apps), read-only, with a button to open it in i40Pilot.
- `i40pilot_job_status` — status and result of an asynchronous job.

## Dashboards (16)
`bi_get_dashboard`, `bi_describe_dataset`, `bi_describe_widget_kinds`, `bi_export_powerbi`,
✏️ `bi_create_dashboard`, ✏️ `bi_add_widget`, ✏️ `bi_update_widget`, ✏️ `bi_delete_widget`,
✏️ `bi_set_widget_appearance`, ✏️ `bi_set_widget_capability`, ✏️ `bi_set_dashboard_tabs`,
✏️ `bi_create_theme`, ✏️ `bi_apply_theme_preset`, ✏️ `bi_collection_organize`,
✏️ `bi_run_dashboard_agent`, ✏️ `dashboards_make_public`

## Data sources & datasets (12)
`bi_list_connectors`, `bi_list_connector_templates`, `bi_list_sources`, `bi_list_datasets`,
`bi_introspect_schema`, `bi_test_connection`, `bi_list_computed_column_templates`,
✏️ `bi_create_data_source`, ✏️ `bi_create_data_source_from_template`, ✏️ `bi_bootstrap_datasets_from_source`,
✏️ `bi_create_dataset`, ✏️ `bi_add_computed_column`

## Spreadsheets (7)
`spreadsheet_list_workbooks`, `spreadsheet_discover_sheets`, `spreadsheet_read_context`,
✏️ `spreadsheet_create_workbook_from_file`, ✏️ `spreadsheet_append_rows`, ✏️ `spreadsheet_update_rows`,
✏️ `spreadsheet_delete_rows_by_criterion`

## Scheduling (5)
`schedule_cpm` (critical path), `schedule_dates`, ✏️ `gantt_append_task`, ✏️ `gantt_update_data`, ✏️ `gantt_delete_task`

## 3D CAD (4)
`drawboard_get_dsl_docs`, `drawboard_inspect_part`, `drawboard_view_render`, ✏️ `drawboard_run_program`

## Calendar (6)
`calendar_list_events`, ✏️ `calendar_create_event`, ✏️ `calendar_create_events`, ✏️ `calendar_update_event`,
✏️ `calendar_delete_event`, ✏️ `calendar_add_attendees`

## Forms & drive (3)
✏️ `forms_append_field`, ✏️ `forms_update_fields`, ✏️ `drive_create_upload_url`
