# CThumbnailCache::_ShouldConsiderItem(IShellItem *)

- ea: `0x180014c4c`
- end: `0x180014cc7`
- name: `?_ShouldConsiderItem@CThumbnailCache@@AEAA_NPEAUIShellItem@@@Z`
- size: `123`
- prototype: `bool __fastcall(CThumbnailCache *__hidden this, struct IShellItem *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008a70`
- `0x180014ae0`

## callees

- `0x180014c4c`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180014caf`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180014caf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cbf`

## pseudocode

```c
bool __fastcall CThumbnailCache::_ShouldConsiderItem(CThumbnailCache *this, struct IShellItem *a2)
{
  bool v2; // bl
  struct IShellItemVtbl *lpVtbl; // rax
  LPCWSTR pszPath; // [rsp+20h] [rbp-18h] BYREF

  v2 = 1;
  if ( *((_DWORD *)this + 193) )
  {
    lpVtbl = a2->lpVtbl;
    pszPath = 0;
    if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPCWSTR *))lpVtbl->GetDisplayName)(
           a2,
           2147844096LL,
           &pszPath) >= 0 )
    {
      v2 = !PathIsNetworkPathW(pszPath);
      CoTaskMemFree((LPVOID)pszPath);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180014c4c  push    rbx
0x180014c4e  sub     rsp, 30h
0x180014c52  mov     rax, cs:__security_cookie
0x180014c59  xor     rax, rsp
0x180014c5c  mov     [rsp+38h+var_10], rax
0x180014c61  cmp     dword ptr [rcx+304h], 0
0x180014c68  mov     r9, rdx
0x180014c6b  mov     bl, 1
0x180014c6d  jnz     short loc_180014C84
0x180014c6f  mov     al, bl
0x180014c71  mov     rcx, [rsp+38h+var_10]
0x180014c76  xor     rcx, rsp; StackCookie
0x180014c79  call    __security_check_cookie
0x180014c7e  add     rsp, 30h
0x180014c82  pop     rbx
0x180014c83  retn
0x180014c84  mov     rax, [rdx]
0x180014c87  lea     r8, [rsp+38h+pszPath]
0x180014c8c  mov     edx, 80058000h
0x180014c91  mov     [rsp+38h+pszPath], 0
0x180014c9a  mov     rcx, r9
0x180014c9d  mov     rax, [rax+28h]
0x180014ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ca6  test    eax, eax
0x180014ca8  js      short loc_180014C6F
0x180014caa  mov     rcx, [rsp+38h+pszPath]; pszPath
0x180014caf  call    cs:__imp_PathIsNetworkPathW
0x180014cb5  mov     rcx, [rsp+38h+pszPath]; pv
0x180014cba  test    eax, eax
0x180014cbc  setz    bl
0x180014cbf  call    cs:__imp_CoTaskMemFree
0x180014cc5  jmp     short loc_180014C6F
```
