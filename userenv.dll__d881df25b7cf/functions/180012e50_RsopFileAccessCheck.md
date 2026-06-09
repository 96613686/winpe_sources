# RsopFileAccessCheck

- ea: `0x180012e50`
- end: `0x180012ea4`
- name: `RsopFileAccessCheck`
- size: `84`
- prototype: `HRESULT __stdcall(LPWSTR pszFileName, PRSOPTOKEN pRsopToken, DWORD dwDesiredAccessMask, LPDWORD pdwGrantedAccessMask, LPBOOL pbAccessStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18000f670`
- `0x180012e50`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!RsopFileAccessCheckWorker` at `0x180012e87`
- `ext-ms-win-profile-userenv-l1-1-0!RsopFileAccessCheckWorker` at `0x180012e87`

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
0x180012e50  push    rbx
0x180012e52  push    rbp
0x180012e53  push    rsi
0x180012e54  push    rdi
0x180012e55  sub     rsp, 38h
0x180012e59  mov     rbx, r9
0x180012e5c  mov     edi, r8d
0x180012e5f  mov     rsi, rdx
0x180012e62  mov     rbp, rcx
0x180012e65  call    IsDeleteLinkFileWorkerPresent
0x180012e6a  test    al, al
0x180012e6c  jz      short loc_180012E95
0x180012e6e  mov     rax, [rsp+58h+pbAccessStatus]
0x180012e76  mov     r9, rbx
0x180012e79  mov     r8d, edi
0x180012e7c  mov     [rsp+58h+var_38], rax
0x180012e81  mov     rdx, rsi
0x180012e84  mov     rcx, rbp
0x180012e87  call    cs:__imp_RsopFileAccessCheckWorker
0x180012e8e  nop     dword ptr [rax+rax+00h]
0x180012e93  jmp     short loc_180012E9A
0x180012e95  mov     eax, 80004001h
0x180012e9a  add     rsp, 38h
0x180012e9e  pop     rdi
0x180012e9f  pop     rsi
0x180012ea0  pop     rbp
0x180012ea1  pop     rbx
0x180012ea2  retn
```
