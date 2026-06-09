# DeleteLVCertItem(HWND__ *,int,_PropArrayInfo *)

- ea: `0x18004c2d0`
- end: `0x18004c3f5`
- name: `?DeleteLVCertItem@@YAHPEAUHWND__@@HPEAU_PropArrayInfo@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(HWND hWnd, int, struct _PropArrayInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180056560`

## callees

- `0x18000553c`
- `0x18004c2d0`
- `0x180091eaa`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004c3cb`
- `KERNEL32!LocalFree` at `0x18004c3cb`
- `USER32!SendMessageW` at `0x18004c316`
- `USER32!SendMessageW` at `0x18004c3e1`
- `USER32!SendMessageW` at `0x18004c316`
- `USER32!SendMessageW` at `0x18004c3e1`
- `CRYPT32!CertFreeCertificateContext` at `0x18004c372`
- `CRYPT32!CertFreeCertificateContext` at `0x18004c372`

## pseudocode

```c

```
