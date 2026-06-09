# SetCancelOneOffUpdateUI(HWND__ *,_PropArrayInfo *,ushort *,ushort *,int)

- ea: `0x18005a288`
- end: `0x18005a3c0`
- name: `?SetCancelOneOffUpdateUI@@YAXPEAUHWND__@@PEAU_PropArrayInfo@@PEAG2H@Z`
- size: `312`
- prototype: `void __usercall(HWND hWnd@<rcx>, struct _PropArrayInfo *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180059ac4`
- `0x180059f4c`
- `0x18005abf0`

## callees

- `0x180033ae0`
- `0x18005a288`
- `0x180091ef0`

## import_xrefs

- `USER32!LoadStringW` at `0x18005a36d`
- `USER32!LoadStringW` at `0x18005a36d`
- `USER32!SendMessageW` at `0x18005a39c`
- `USER32!SendMessageW` at `0x18005a39c`
- `USER32!EnableWindow` at `0x18005a335`
- `USER32!EnableWindow` at `0x18005a335`
- `USER32!GetDlgItem` at `0x18005a32a`
- `USER32!GetDlgItem` at `0x18005a340`
- `USER32!GetDlgItem` at `0x18005a32a`
- `USER32!GetDlgItem` at `0x18005a340`
- `USER32!GetParent` at `0x18005a387`
- `USER32!GetParent` at `0x18005a387`
- `USER32!SetDlgItemTextW` at `0x18005a2fb`
- `USER32!SetDlgItemTextW` at `0x18005a313`
- `USER32!SetDlgItemTextW` at `0x18005a37e`
- `USER32!SetDlgItemTextW` at `0x18005a2fb`
- `USER32!SetDlgItemTextW` at `0x18005a313`
- `USER32!SetDlgItemTextW` at `0x18005a37e`
- `USER32!ShowWindow` at `0x18005a34b`
- `USER32!ShowWindow` at `0x18005a34b`

## pseudocode

```c

```
