# DeleteSelectedItems(HWND__ *,IAddrBook *,_FILETIME *)

- ea: `0x180063a3c`
- end: `0x180063d5c`
- name: `?DeleteSelectedItems@@YAXPEAUHWND__@@PEAUIAddrBook@@PEAU_FILETIME@@@Z`
- size: `800`
- prototype: `void __fastcall(HWND hWnd, struct IAddrBook *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180047e90`
- `0x180060850`

## callees

- `0x180002818`
- `0x180033a7c`
- `0x180033ae0`
- `0x180063a3c`
- `0x1800648b0`
- `0x1800685fc`
- `0x1800695fc`
- `0x180069e24`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180063ba6`
- `KERNEL32!LocalAlloc` at `0x180063ba6`
- `USER32!SendMessageW` at `0x180063a9c`
- `USER32!SendMessageW` at `0x180063b68`
- `USER32!SendMessageW` at `0x180063bcb`
- `USER32!SendMessageW` at `0x180063c0b`
- `USER32!SendMessageW` at `0x180063c45`
- `USER32!SendMessageW` at `0x180063c5c`
- `USER32!SendMessageW` at `0x180063c76`
- `USER32!SendMessageW` at `0x180063cb0`
- `USER32!SendMessageW` at `0x180063cc5`
- `USER32!SendMessageW` at `0x180063ce6`
- `USER32!SendMessageW` at `0x180063a9c`
- `USER32!SendMessageW` at `0x180063b68`
- `USER32!SendMessageW` at `0x180063bcb`
- `USER32!SendMessageW` at `0x180063c0b`
- `USER32!SendMessageW` at `0x180063c45`
- `USER32!SendMessageW` at `0x180063c5c`
- `USER32!SendMessageW` at `0x180063c76`
- `USER32!SendMessageW` at `0x180063cb0`
- `USER32!SendMessageW` at `0x180063cc5`
- `USER32!SendMessageW` at `0x180063ce6`
- `USER32!LoadCursorW` at `0x180063b49`
- `USER32!LoadCursorW` at `0x180063b49`
- `USER32!GetParent` at `0x180063a60`
- `USER32!GetParent` at `0x180063aac`
- `USER32!GetParent` at `0x180063a60`
- `USER32!GetParent` at `0x180063aac`
- `USER32!SetCursor` at `0x180063b52`
- `USER32!SetCursor` at `0x180063c9a`
- `USER32!SetCursor` at `0x180063b52`
- `USER32!SetCursor` at `0x180063c9a`
- `USER32!GetWindowLongW` at `0x180063b77`
- `USER32!GetWindowLongW` at `0x180063b77`
- `USER32!SetWindowLongW` at `0x180063b90`
- `USER32!SetWindowLongW` at `0x180063c91`
- `USER32!SetWindowLongW` at `0x180063b90`
- `USER32!SetWindowLongW` at `0x180063c91`

## pseudocode

```c

```
