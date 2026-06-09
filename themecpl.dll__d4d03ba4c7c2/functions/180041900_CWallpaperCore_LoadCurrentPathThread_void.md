# CWallpaperCore::_LoadCurrentPathThread(void *)

- ea: `0x180041900`
- end: `0x180041afe`
- name: `?_LoadCurrentPathThread@CWallpaperCore@@CAKPEAX@Z`
- size: `510`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callees

- `0x180002280`
- `0x180002650`
- `0x18003dbc8`
- `0x180041900`
- `0x18004e78c`
- `0x180057010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x1800419d2`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800419d2`
- `SHELL32!SHGetIDListFromObject` at `0x180041a04`
- `SHELL32!SHGetIDListFromObject` at `0x180041a04`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800419ae`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800419ae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180041a4e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180041a4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a97`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004194b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004194b`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_LoadCurrentPathThread(WCHAR **a1)
{
  WCHAR *v1; // rax
  WCHAR *v3; // r8
  WCHAR *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  WCHAR *v7; // rcx
  volatile signed __int32 *v8; // rcx
  IUnknown *punk; // [rsp+20h] [rbp-E0h] BYREF
  void *ppv; // [rsp+28h] [rbp-D8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF

  v1 = *a1;
  ppidl = 0;
  pv = 0;
  if ( *v1 && CoInitializeEx(0, 6u) >= 0 )
  {
    v3 = *a1;
    v4 = pszPath;
    v5 = 2147483646;
    v6 = 260;
    do
    {
      if ( !v5 )
        break;
      if ( !*v3 )
        break;
      *v4++ = *v3++;
      --v5;
      --v6;
    }
    while ( v6 );
    v7 = v4 - 1;
    if ( v6 )
      v7 = v4;
    *v7 = 0;
    if ( v6 )
    {
      PathRemoveFileSpecW(pszPath);
      ppv = 0;
      if ( SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
      {
        punk = 0;
        if ( (int)GetFilteredShellItem((struct IShellItem *)ppv, (struct IShellItem **)&punk) >= 0 )
        {
          if ( SHGetIDListFromObject(punk, &ppidl) >= 0 )
            ((void (__fastcall *)(IUnknown *, _QWORD, LPVOID *))punk->lpVtbl[1].Release)(punk, 0, &pv);
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    CoUninitialize();
  }
  CTaskQueueItem::PostResult(a1[1], 1, ppidl, pv);
  CoTaskMemFree(ppidl);
  CoTaskMemFree(pv);
  CoTaskMemFree(*a1);
  v8 = (volatile signed __int32 *)a1[1];
  if ( v8 && _InterlockedExchangeAdd(v8 + 26, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v8 + 16LL))(v8, 1);
  operator delete(a1, (const struct std::nothrow_t *)0x10);
  return 0;
}

```

## disassembly

```asm
0x180041900  mov     [rsp-8+arg_8], rbx
0x180041905  mov     [rsp-8+arg_10], rdi
0x18004190a  push    rbp
0x18004190b  lea     rbp, [rsp-160h]
0x180041913  sub     rsp, 260h
0x18004191a  mov     rax, cs:__security_cookie
0x180041921  xor     rax, rsp
0x180041924  mov     [rbp+160h+var_10], rax
0x18004192b  mov     rax, [rcx]
0x18004192e  xor     edi, edi
0x180041930  mov     [rsp+260h+ppidl], rdi
0x180041935  mov     rbx, rcx
0x180041938  mov     [rsp+260h+pv], rdi
0x18004193d  cmp     [rax], di
0x180041940  jz      loc_180041A5A
0x180041946  lea     edx, [rdi+6]; dwCoInit
0x180041949  xor     ecx, ecx; pvReserved
0x18004194b  call    cs:__imp_CoInitializeEx
0x180041952  nop     dword ptr [rax+rax+00h]
0x180041957  test    eax, eax
0x180041959  js      loc_180041A5A
0x18004195f  mov     r8, [rbx]
0x180041962  lea     rax, [rsp+260h+pszPath]
0x180041967  mov     ecx, 7FFFFFFEh
0x18004196c  mov     edx, 104h
0x180041971  test    rcx, rcx
0x180041974  jz      short loc_180041995
0x180041976  movzx   r9d, word ptr [r8]
0x18004197a  test    r9w, r9w
0x18004197e  jz      short loc_180041995
0x180041980  mov     [rax], r9w
0x180041984  add     r8, 2
0x180041988  add     rax, 2
0x18004198c  dec     rcx
0x18004198f  sub     rdx, 1
0x180041993  jnz     short loc_180041971
0x180041995  test    rdx, rdx
0x180041998  lea     rcx, [rax-2]
0x18004199c  cmovnz  rcx, rax
0x1800419a0  mov     [rcx], di
0x1800419a3  jz      loc_180041A4E
0x1800419a9  lea     rcx, [rsp+260h+pszPath]; pszPath
0x1800419ae  call    cs:__imp_PathRemoveFileSpecW
0x1800419b5  nop     dword ptr [rax+rax+00h]
0x1800419ba  lea     r9, [rsp+260h+ppv]; ppv
0x1800419bf  mov     [rsp+260h+ppv], rdi
0x1800419c4  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800419cb  xor     edx, edx; pbc
0x1800419cd  lea     rcx, [rsp+260h+pszPath]; pszPath
0x1800419d2  call    cs:__imp_SHCreateItemFromParsingName
0x1800419d9  nop     dword ptr [rax+rax+00h]
0x1800419de  test    eax, eax
0x1800419e0  js      short loc_180041A4E
0x1800419e2  mov     rcx, [rsp+260h+ppv]; struct IShellItem *
0x1800419e7  lea     rdx, [rsp+260h+punk]; struct IShellItem **
0x1800419ec  mov     [rsp+260h+punk], rdi
0x1800419f1  call    ?GetFilteredShellItem@@YAJPEAUIShellItem@@PEAPEAU1@@Z; GetFilteredShellItem(IShellItem *,IShellItem * *)
0x1800419f6  test    eax, eax
0x1800419f8  js      short loc_180041A3D
0x1800419fa  mov     rcx, [rsp+260h+punk]; punk
0x1800419ff  lea     rdx, [rsp+260h+ppidl]; ppidl
0x180041a04  call    cs:__imp_SHGetIDListFromObject
0x180041a0b  nop     dword ptr [rax+rax+00h]
0x180041a10  test    eax, eax
0x180041a12  js      short loc_180041A2C
0x180041a14  mov     rcx, [rsp+260h+punk]
0x180041a19  lea     r8, [rsp+260h+pv]
0x180041a1e  xor     edx, edx
0x180041a20  mov     rax, [rcx]
0x180041a23  mov     rax, [rax+28h]
0x180041a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a2c  mov     rcx, [rsp+260h+punk]
0x180041a31  mov     rax, [rcx]
0x180041a34  mov     rax, [rax+10h]
0x180041a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a3d  mov     rcx, [rsp+260h+ppv]
0x180041a42  mov     rax, [rcx]
0x180041a45  mov     rax, [rax+10h]
0x180041a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a4e  call    cs:__imp_CoUninitialize
0x180041a55  nop     dword ptr [rax+rax+00h]
0x180041a5a  mov     r9, [rsp+260h+pv]
0x180041a5f  mov     edx, 1
0x180041a64  mov     r8, [rsp+260h+ppidl]
0x180041a69  mov     rcx, [rbx+8]
0x180041a6d  call    ?PostResult@CTaskQueueItem@@SAJPEAVCDefTaskLock@@W4PATH_TASK_ID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEBG@Z; CTaskQueueItem::PostResult(CDefTaskLock *,PATH_TASK_ID,_ITEMIDLIST_ABSOLUTE const *,ushort const *)
0x180041a72  mov     rcx, [rsp+260h+ppidl]; pv
0x180041a77  call    cs:__imp_CoTaskMemFree
0x180041a7e  nop     dword ptr [rax+rax+00h]
0x180041a83  mov     rcx, [rsp+260h+pv]; pv
0x180041a88  call    cs:__imp_CoTaskMemFree
0x180041a8f  nop     dword ptr [rax+rax+00h]
0x180041a94  mov     rcx, [rbx]; pv
0x180041a97  call    cs:__imp_CoTaskMemFree
0x180041a9e  nop     dword ptr [rax+rax+00h]
0x180041aa3  mov     rcx, [rbx+8]
0x180041aa7  test    rcx, rcx
0x180041aaa  jz      short loc_180041ACA
0x180041aac  or      eax, 0FFFFFFFFh
0x180041aaf  lock xadd [rcx+68h], eax
0x180041ab4  cmp     eax, 1
0x180041ab7  jnz     short loc_180041ACA
0x180041ab9  mov     rax, [rcx]
0x180041abc  mov     edx, 1
0x180041ac1  mov     rax, [rax+10h]
0x180041ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041aca  mov     edx, 10h; struct std::nothrow_t *
0x180041acf  mov     rcx, rbx; void *
0x180041ad2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180041ad7  xor     eax, eax
0x180041ad9  mov     rcx, [rbp+160h+var_10]
0x180041ae0  xor     rcx, rsp; StackCookie
0x180041ae3  call    __security_check_cookie
0x180041ae8  lea     r11, [rsp+260h+var_s0]
0x180041af0  mov     rbx, [r11+18h]
0x180041af4  mov     rdi, [r11+20h]
0x180041af8  mov     rsp, r11
0x180041afb  pop     rbp
0x180041afc  retn
```
