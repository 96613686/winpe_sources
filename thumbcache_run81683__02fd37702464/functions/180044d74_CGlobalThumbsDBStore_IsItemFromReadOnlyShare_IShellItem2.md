# CGlobalThumbsDBStore::_IsItemFromReadOnlyShare(IShellItem2 *)

- ea: `0x180044d74`
- end: `0x180044e27`
- name: `?_IsItemFromReadOnlyShare@CGlobalThumbsDBStore@@AEAAHPEAUIShellItem2@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(CGlobalThumbsDBStore *__hidden this, struct IShellItem2 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180044a74`

## callees

- `0x180035830`
- `0x180044d74`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180044df7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180044df7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180044dce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180044dce`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180044dc0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180044dc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044e02`
- `SHELL32!__imp_PathComparePaths` at `0x180044de2`
- `SHELL32!__imp_PathComparePaths` at `0x180044de2`

## pseudocode

```c
__int64 __fastcall CGlobalThumbsDBStore::_IsItemFromReadOnlyShare(RTL_SRWLOCK *this, struct IShellItem2 *a2)
{
  struct IShellItem2Vtbl *lpVtbl; // rax
  unsigned int v4; // ebx
  LPWSTR pszPath; // [rsp+20h] [rbp-18h] BYREF

  lpVtbl = a2->lpVtbl;
  v4 = 0;
  pszPath = 0;
  if ( ((int (__fastcall *)(struct IShellItem2 *, __int64, LPWSTR *))lpVtbl->GetDisplayName)(a2, 2147844096LL, &pszPath) >= 0 )
  {
    if ( PathRemoveFileSpecW(pszPath) )
    {
      AcquireSRWLockShared(this + 1);
      if ( this[3].Ptr && (PathComparePaths(pszPath) & 4) != 0 )
        LOBYTE(v4) = HIDWORD(this[4].Ptr) == 2;
      ReleaseSRWLockShared(this + 1);
    }
    CoTaskMemFree(pszPath);
  }
  return v4;
}

```

## disassembly

```asm
0x180044d74  mov     r11, rsp
0x180044d77  mov     [r11+18h], rbx
0x180044d7b  mov     [r11+20h], rsi
0x180044d7f  push    rdi
0x180044d80  sub     rsp, 30h
0x180044d84  mov     rax, cs:__security_cookie
0x180044d8b  xor     rax, rsp
0x180044d8e  mov     [rsp+38h+var_10], rax
0x180044d93  mov     rax, [rdx]
0x180044d96  lea     r8, [r11-18h]
0x180044d9a  mov     r9, rdx
0x180044d9d  mov     rdi, rcx
0x180044da0  xor     ebx, ebx
0x180044da2  mov     edx, 80058000h
0x180044da7  mov     rcx, r9
0x180044daa  mov     [r11-18h], rbx
0x180044dae  mov     rax, [rax+28h]
0x180044db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044db7  test    eax, eax
0x180044db9  js      short loc_180044E08
0x180044dbb  mov     rcx, [rsp+38h+pszPath]; pszPath
0x180044dc0  call    cs:__imp_PathRemoveFileSpecW
0x180044dc6  test    eax, eax
0x180044dc8  jz      short loc_180044DFD
0x180044dca  lea     rcx, [rdi+8]; SRWLock
0x180044dce  call    cs:__imp_AcquireSRWLockShared
0x180044dd4  mov     rdx, [rdi+18h]
0x180044dd8  test    rdx, rdx
0x180044ddb  jz      short loc_180044DF3
0x180044ddd  mov     rcx, [rsp+38h+pszPath]
0x180044de2  call    cs:__imp_PathComparePaths
0x180044de8  test    al, 4
0x180044dea  jz      short loc_180044DF3
0x180044dec  cmp     dword ptr [rdi+24h], 2
0x180044df0  setz    bl
0x180044df3  lea     rcx, [rdi+8]; SRWLock
0x180044df7  call    cs:__imp_ReleaseSRWLockShared
0x180044dfd  mov     rcx, [rsp+38h+pszPath]; pv
0x180044e02  call    cs:__imp_CoTaskMemFree
0x180044e08  mov     eax, ebx
0x180044e0a  mov     rcx, [rsp+38h+var_10]
0x180044e0f  xor     rcx, rsp; StackCookie
0x180044e12  call    __security_check_cookie
0x180044e17  mov     rbx, [rsp+38h+arg_10]
0x180044e1c  mov     rsi, [rsp+38h+arg_18]
0x180044e21  add     rsp, 30h
0x180044e25  pop     rdi
0x180044e26  retn
```
