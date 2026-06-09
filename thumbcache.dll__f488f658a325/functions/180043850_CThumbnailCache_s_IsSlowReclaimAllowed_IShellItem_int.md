# CThumbnailCache::s_IsSlowReclaimAllowed(IShellItem *,int *)

- ea: `0x180043850`
- end: `0x1800438fe`
- name: `?s_IsSlowReclaimAllowed@CThumbnailCache@@CAJPEAUIShellItem@@PEAH@Z`
- size: `174`
- prototype: `__int64 __fastcall(struct IShellItem *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800429b4`

## callees

- `0x180035830`
- `0x180043850`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800438c2`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800438c2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1800438b3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1800438b3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004389c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004389c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438de`

## pseudocode

```c
__int64 __fastcall CThumbnailCache::s_IsSlowReclaimAllowed(struct IShellItem *a1, int *a2)
{
  struct IShellItemVtbl *lpVtbl; // rax
  int v4; // ebx
  LPCWSTR pszPath; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  lpVtbl = a1->lpVtbl;
  pszPath = 0;
  v4 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPCWSTR *))lpVtbl->GetDisplayName)(
         a1,
         2147647488LL,
         &pszPath);
  if ( v4 >= 0 )
  {
    if ( PathIsUNCW(pszPath) )
    {
      *a2 = 1;
    }
    else if ( PathStripToRootW((LPWSTR)pszPath) )
    {
      *a2 = GetDriveTypeW(pszPath) != 3;
    }
    else
    {
      v4 = -2147024809;
    }
    CoTaskMemFree((LPVOID)pszPath);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180043850  mov     [rsp+arg_10], rbx
0x180043855  push    rdi
0x180043856  sub     rsp, 30h
0x18004385a  mov     rax, cs:__security_cookie
0x180043861  xor     rax, rsp
0x180043864  mov     [rsp+38h+var_10], rax
0x180043869  mov     dword ptr [rdx], 0
0x18004386f  lea     r8, [rsp+38h+pszPath]
0x180043874  mov     rax, [rcx]
0x180043877  mov     rdi, rdx
0x18004387a  mov     edx, 80028000h
0x18004387f  mov     [rsp+38h+pszPath], 0
0x180043888  mov     rax, [rax+28h]
0x18004388c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043891  mov     ebx, eax
0x180043893  test    eax, eax
0x180043895  js      short loc_1800438E4
0x180043897  mov     rcx, [rsp+38h+pszPath]; pszPath
0x18004389c  call    cs:__imp_PathIsUNCW
0x1800438a2  test    eax, eax
0x1800438a4  jz      short loc_1800438AE
0x1800438a6  mov     dword ptr [rdi], 1
0x1800438ac  jmp     short loc_1800438D9
0x1800438ae  mov     rcx, [rsp+38h+pszPath]; pszPath
0x1800438b3  call    cs:__imp_PathStripToRootW
0x1800438b9  test    eax, eax
0x1800438bb  jz      short loc_1800438D4
0x1800438bd  mov     rcx, [rsp+38h+pszPath]; lpRootPathName
0x1800438c2  call    cs:__imp_GetDriveTypeW
0x1800438c8  xor     ecx, ecx
0x1800438ca  cmp     eax, 3
0x1800438cd  setnz   cl
0x1800438d0  mov     [rdi], ecx
0x1800438d2  jmp     short loc_1800438D9
0x1800438d4  mov     ebx, 80070057h
0x1800438d9  mov     rcx, [rsp+38h+pszPath]; pv
0x1800438de  call    cs:__imp_CoTaskMemFree
0x1800438e4  mov     eax, ebx
0x1800438e6  mov     rcx, [rsp+38h+var_10]
0x1800438eb  xor     rcx, rsp; StackCookie
0x1800438ee  call    __security_check_cookie
0x1800438f3  mov     rbx, [rsp+38h+arg_10]
0x1800438f8  add     rsp, 30h
0x1800438fc  pop     rdi
0x1800438fd  retn
```
