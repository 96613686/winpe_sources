# RsopFileAccessCheck

- ea: `0x180011e90`
- end: `0x180011edd`
- name: `RsopFileAccessCheck`
- size: `77`
- prototype: `HRESULT __stdcall(LPWSTR pszFileName, PRSOPTOKEN pRsopToken, DWORD dwDesiredAccessMask, LPDWORD pdwGrantedAccessMask, LPBOOL pbAccessStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18000e9c0`
- `0x180011e90`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!RsopFileAccessCheckWorker` at `0x180011ec7`
- `ext-ms-win-profile-userenv-l1-1-0!RsopFileAccessCheckWorker` at `0x180011ec7`

## pseudocode

```c
HRESULT __stdcall RsopFileAccessCheck(
        LPWSTR pszFileName,
        PRSOPTOKEN pRsopToken,
        DWORD dwDesiredAccessMask,
        LPDWORD pdwGrantedAccessMask,
        LPBOOL pbAccessStatus)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return RsopFileAccessCheckWorker(pszFileName, pRsopToken, dwDesiredAccessMask, pdwGrantedAccessMask, pbAccessStatus);
  else
    return -2147467263;
}

```

## disassembly

```asm
0x180011e90  push    rbx
0x180011e92  push    rbp
0x180011e93  push    rsi
0x180011e94  push    rdi
0x180011e95  sub     rsp, 38h
0x180011e99  mov     rbx, r9
0x180011e9c  mov     edi, r8d
0x180011e9f  mov     rsi, rdx
0x180011ea2  mov     rbp, rcx
0x180011ea5  call    IsDeleteLinkFileWorkerPresent
0x180011eaa  test    al, al
0x180011eac  jz      short loc_180011ECF
0x180011eae  mov     rax, [rsp+58h+pbAccessStatus]
0x180011eb6  mov     r9, rbx
0x180011eb9  mov     r8d, edi
0x180011ebc  mov     [rsp+58h+var_38], rax
0x180011ec1  mov     rdx, rsi
0x180011ec4  mov     rcx, rbp
0x180011ec7  call    cs:__imp_RsopFileAccessCheckWorker
0x180011ecd  jmp     short loc_180011ED4
0x180011ecf  mov     eax, 80004001h
0x180011ed4  add     rsp, 38h
0x180011ed8  pop     rdi
0x180011ed9  pop     rsi
0x180011eda  pop     rbp
0x180011edb  pop     rbx
0x180011edc  retn
```
