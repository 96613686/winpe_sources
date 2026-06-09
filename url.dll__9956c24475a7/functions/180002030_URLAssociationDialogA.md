# URLAssociationDialogA

- ea: `0x180002030`
- end: `0x180002050`
- name: `URLAssociationDialogA`
- size: `32`
- prototype: `HRESULT __stdcall(HWND hwndParent, DWORD dwInFlags, PCWSTR pcszFile, PCWSTR pcszURL, PWSTR pszAppBuf, UINT ucAppBufLen)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180002039`
- `KERNEL32!SetLastError` at `0x180002039`

## pseudocode

```c
HRESULT __stdcall URLAssociationDialogA(
        HWND hwndParent,
        DWORD dwInFlags,
        PCWSTR pcszFile,
        PCWSTR pcszURL,
        PWSTR pszAppBuf,
        UINT ucAppBufLen)
{
  SetLastError(0x32u);
  return -2147467263;
}

```

## disassembly

```asm
0x180002030  sub     rsp, 28h; MIMEAssociationDialogA
0x180002034  mov     ecx, 32h ; '2'; dwErrCode
0x180002039  call    cs:__imp_SetLastError
0x180002040  nop     dword ptr [rax+rax+00h]
0x180002045  mov     eax, 80004001h
0x18000204a  add     rsp, 28h
0x18000204e  retn
```
