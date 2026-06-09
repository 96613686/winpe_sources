# UpdateTelemetryCountAndTimeStamp(HWND__ *,ushort const *,ushort const *)

- ea: `0x18005d4d0`
- end: `0x18005d530`
- name: `?UpdateTelemetryCountAndTimeStamp@@YA_NPEAUHWND__@@PEBG1@Z`
- size: `96`
- prototype: `bool __fastcall(HWND hWnd, LPCWSTR lpString, LPCWSTR)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180039674`
- `0x180039b70`

## callees

- `0x18005d4d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005d502`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005d502`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18005d4e8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18005d4e8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18005d4f8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18005d511`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18005d4f8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18005d511`

## pseudocode

```c

```
