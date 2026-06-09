# ComboAddItem(HWND__ *,ushort *,__int64,ushort *,int *,int *)

- ea: `0x18005cf6c`
- end: `0x18005d1d4`
- name: `?ComboAddItem@@YAHPEAUHWND__@@PEAG_J1PEAH3@Z`
- size: `616`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, unsigned __int16 *@<rdx>, __int64@<r8>, unsigned __int16 *@<r9>, int *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005e0cc`
- `0x18005eea4`

## callees

- `0x1800270d4`
- `0x1800277e4`
- `0x18005cf6c`
- `0x18006a1f8`
- `0x180091eaa`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18005d11e`
- `KERNEL32!lstrcmpiW` at `0x18005d11e`
- `KERNEL32!LocalAlloc` at `0x18005d0e1`
- `KERNEL32!LocalAlloc` at `0x18005d0e1`
- `KERNEL32!LocalFree` at `0x18005d0cb`
- `KERNEL32!LocalFree` at `0x18005d171`
- `KERNEL32!LocalFree` at `0x18005d0cb`
- `KERNEL32!LocalFree` at `0x18005d171`
- `USER32!SendMessageW` at `0x18005cfa4`
- `USER32!SendMessageW` at `0x18005cffe`
- `USER32!SendMessageW` at `0x18005d067`
- `USER32!SendMessageW` at `0x18005d0b2`
- `USER32!SendMessageW` at `0x18005d0fd`
- `USER32!SendMessageW` at `0x18005d14b`
- `USER32!SendMessageW` at `0x18005d163`
- `USER32!SendMessageW` at `0x18005cfa4`
- `USER32!SendMessageW` at `0x18005cffe`
- `USER32!SendMessageW` at `0x18005d067`
- `USER32!SendMessageW` at `0x18005d0b2`
- `USER32!SendMessageW` at `0x18005d0fd`
- `USER32!SendMessageW` at `0x18005d14b`
- `USER32!SendMessageW` at `0x18005d163`

## pseudocode

```c

```
