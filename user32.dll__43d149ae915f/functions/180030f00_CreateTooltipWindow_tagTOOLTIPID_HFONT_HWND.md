# CreateTooltipWindow(tagTOOLTIPID,HFONT__ *,HWND__ *)

- ea: `0x180030f00`
- end: `0x1800310b6`
- name: `?CreateTooltipWindow@@YAXW4tagTOOLTIPID@@PEAUHFONT__@@PEAUHWND__@@@Z`
- size: `438`
- prototype: `void __high(enum tagTOOLTIPID, HFONT, HWND)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180030ea0`

## callees

- `0x180010e60`
- `0x180016310`
- `0x18002dc50`
- `0x18002dd20`
- `0x180030f00`
- `0x180031358`
- `0x18003142c`
- `0x180035be0`
- `0x180065d28`

## import_xrefs

- `win32u!NtUserShowWindow` at `0x180031090`
- `win32u!NtUserShowWindow` at `0x180031090`
- `win32u!NtUserDestroyWindow` at `0x180031098`
- `win32u!NtUserDestroyWindow` at `0x180031098`
- `ntdll!RtlAllocateHeap` at `0x180031020`
- `ntdll!RtlAllocateHeap` at `0x180031020`

## pseudocode

```c

```
