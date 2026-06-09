# CDateTimeCfgDialog::UpdateStatusStrings(_SYSTEMTIME * const)

- ea: `0x180008d80`
- end: `0x180008f6d`
- name: `?UpdateStatusStrings@CDateTimeCfgDialog@@QEAAXQEAU_SYSTEMTIME@@@Z`
- size: `493`
- prototype: `void(CDateTimeCfgDialog *__hidden this, struct _SYSTEMTIME *const)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180006818`
- `0x180007394`

## callees

- `0x180008d80`
- `0x180009890`
- `0x1800168c8`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008df4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008df4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008e25`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008eba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008e25`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008eba`
- `KERNEL32!ConvertSystemTimeToCalDateTime` at `0x180008e6e`
- `KERNEL32!ConvertSystemTimeToCalDateTime` at `0x180008e6e`
- `KERNEL32!GetCalendarDateFormat` at `0x180008e9c`
- `KERNEL32!GetCalendarDateFormat` at `0x180008e9c`
- `USER32!ShowWindow` at `0x180008f2c`
- `USER32!ShowWindow` at `0x180008f3f`
- `USER32!ShowWindow` at `0x180008f2c`
- `USER32!ShowWindow` at `0x180008f3f`
- `USER32!SetDlgItemTextW` at `0x180008f0d`
- `USER32!SetDlgItemTextW` at `0x180008f0d`
- `USER32!GetDlgItem` at `0x180008f21`
- `USER32!GetDlgItem` at `0x180008f21`

## pseudocode

```c

```
