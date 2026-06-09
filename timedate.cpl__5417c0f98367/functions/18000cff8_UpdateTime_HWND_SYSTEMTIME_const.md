# UpdateTime(HWND__ *,_SYSTEMTIME * const)

- ea: `0x18000cff8`
- end: `0x18000d0a5`
- name: `?UpdateTime@@YAXPEAUHWND__@@QEAU_SYSTEMTIME@@@Z`
- size: `173`
- prototype: `void __fastcall(HWND hDlg, LPARAM lParam)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000a670`
- `0x18000cf98`

## callees

- `0x18000cff8`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18000d03c`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18000d03c`
- `USER32!SetWindowTextW` at `0x18000d05c`
- `USER32!SetWindowTextW` at `0x18000d05c`
- `USER32!GetDlgItem` at `0x18000d04e`
- `USER32!GetDlgItem` at `0x18000d06a`
- `USER32!GetDlgItem` at `0x18000d04e`
- `USER32!GetDlgItem` at `0x18000d06a`
- `USER32!SendMessageW` at `0x18000d07e`
- `USER32!SendMessageW` at `0x18000d07e`

## pseudocode

```c

```
