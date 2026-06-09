# FillContainerCombo(HWND__ *,AddressBook *)

- ea: `0x180045d3c`
- end: `0x180045e9a`
- name: `?FillContainerCombo@@YAXPEAUHWND__@@PEAVAddressBook@@@Z`
- size: `350`
- prototype: `void __fastcall(HWND hWnd, struct AddressBook *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180045ea0`
- `0x180046c88`

## callees

- `0x180045d3c`
- `0x180064e84`
- `0x180093010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180045e4e`
- `KERNEL32!lstrcmpiW` at `0x180045e4e`
- `KERNEL32!EnterCriticalSection` at `0x180045d90`
- `KERNEL32!EnterCriticalSection` at `0x180045d90`
- `KERNEL32!LeaveCriticalSection` at `0x180045e69`
- `KERNEL32!LeaveCriticalSection` at `0x180045e69`
- `USER32!SendMessageW` at `0x180045d80`
- `USER32!SendMessageW` at `0x180045e04`
- `USER32!SendMessageW` at `0x180045e2f`
- `USER32!SendMessageW` at `0x180045e7d`
- `USER32!SendMessageW` at `0x180045d80`
- `USER32!SendMessageW` at `0x180045e04`
- `USER32!SendMessageW` at `0x180045e2f`
- `USER32!SendMessageW` at `0x180045e7d`

## pseudocode

```c

```
