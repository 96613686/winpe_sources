# CWallpaperCore::_AddUserPath(ushort const *,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x18003f4dc`
- end: `0x18003f7fc`
- name: `?_AddUserPath@CWallpaperCore@@AEAAJPEBGPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `800`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this, const unsigned __int16 *, LPCITEMIDLIST pidl)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003d500`
- `0x18003f0d8`

## callees

- `0x18003ef34`
- `0x18003f4dc`
- `0x18004e540`
- `0x18004f6cc`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `SHELL32!SHGetNameFromIDList` at `0x18003f5ee`
- `SHELL32!SHGetNameFromIDList` at `0x18003f5ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f62f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f6cb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f62f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f6cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f78f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f7ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f78f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f7ba`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_AddUserPath(CWallpaperCore *this, const unsigned __int16 *a2, LPCITEMIDLIST pidl)
{
  int v4; // r12d
  int v6; // edi
  int i; // esi
  struct _DPA *v8; // rcx
  int v9; // eax
  PVOID Ptr; // r13
  int j; // r14d
  struct _DPA *v12; // rcx
  int v13; // eax
  const ITEMIDLIST *v14; // rax
  int k; // r14d
  struct _DPA *v16; // rcx
  int v17; // eax
  LPCITEMIDLIST *v18; // rax
  int m; // r14d
  struct _DPA *v20; // rcx
  int v21; // eax
  LPCITEMIDLIST *v22; // rax
  int (*v23)(struct IXFeedFolder *, void *); // rdx
  int v24; // edi
  int (*v25)(struct IXFeed *, void *); // r8
  void *v26; // rsi
  LPVOID v28; // [rsp+30h] [rbp-20h] BYREF
  PWSTR ppszName; // [rsp+38h] [rbp-18h] BYREF
  PWSTR v30; // [rsp+40h] [rbp-10h] BYREF
  LPVOID v31; // [rsp+48h] [rbp-8h]
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+58h] BYREF

  v4 = (int)a2;
  v6 = 0;
  if ( a2 )
  {
    for ( i = 0; ; ++i )
    {
      v8 = (struct _DPA *)*((_QWORD *)this + 12);
      v9 = v8 ? *(_DWORD *)v8 : 0;
      if ( i >= v9 )
        break;
      Ptr = DPA_GetPtr(v8, i);
      for ( j = 0; ; ++j )
      {
        v12 = (struct _DPA *)*((_QWORD *)Ptr + 133);
        v13 = v12 ? *(_DWORD *)v12 : 0;
        if ( j >= v13 )
          break;
        v14 = (const ITEMIDLIST *)DPA_GetPtr(v12, j);
        if ( (unsigned int)ILIsEqualByAliasOrPath(pidl, v14) )
          return (unsigned int)v6;
      }
    }
    for ( k = 0; ; ++k )
    {
      v16 = (struct _DPA *)*((_QWORD *)this + 10);
      v17 = v16 ? *(_DWORD *)v16 : 0;
      if ( k >= v17 )
        break;
      v18 = (LPCITEMIDLIST *)DPA_GetPtr(v16, k);
      if ( (unsigned int)ILIsEqualByAliasOrPath(pidl, *v18) )
        return (unsigned int)v6;
    }
    for ( m = 0; ; ++m )
    {
      v20 = (struct _DPA *)*((_QWORD *)this + 11);
      v21 = v20 ? *(_DWORD *)v20 : 0;
      if ( m >= v21 )
        break;
      v22 = (LPCITEMIDLIST *)DPA_GetPtr(v20, m);
      if ( (unsigned int)ILIsEqualByAliasOrPath(pidl, *v22) )
        return (unsigned int)v6;
    }
    ppszName = 0;
    if ( SHGetNameFromIDList(pidl, SIGDN_DESKTOPABSOLUTEPARSING, &ppszName) < 0 )
    {
      return (unsigned int)CWallpaperCore::_AddPath((int)this, (int)this + 80, 0, v4, pidl);
    }
    else
    {
      v30 = ppszName;
      v31 = 0;
      ppv = 0;
      if ( CoCreateInstance(&CLSID_XFeedsManager, 0, 1u, &GUID_5357e238_fb12_4aca_a930_cab7832b84bf, &ppv) < 0 )
        goto LABEL_43;
      pv = 0;
      v24 = (*(__int64 (__fastcall **)(LPVOID, GUID *, LPVOID *))(*(_QWORD *)ppv + 24LL))(
              ppv,
              &GUID_4c963678_3a51_4b88_8531_98b90b6508f2,
              &pv);
      if ( v24 >= 0 )
      {
        EnumerateRSSFeedsInFolder((struct IXFeedFolder *)pv, v23, v25, &v30);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v24 >= 0 && (v26 = v31) != 0 )
      {
        v28 = 0;
        if ( CoCreateInstance(&CLSID_XFeedsManager, 0, 3u, &GUID_5357e238_fb12_4aca_a930_cab7832b84bf, &v28) < 0 )
          goto LABEL_41;
        ppv = 0;
        v6 = (*(__int64 (__fastcall **)(LPVOID, void *, GUID *, LPVOID *))(*(_QWORD *)v28 + 56LL))(
               v28,
               v26,
               &GUID_a44179a4_e0f6_403b_af8d_d080f425a451,
               &ppv);
        if ( v6 >= 0 )
        {
          pv = 0;
          v6 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)ppv + 32LL))(ppv, &pv);
          if ( v6 >= 0 )
          {
            v6 = CWallpaperCore::_AddPath((int)this, (int)this + 80, 0, (int)pv, pidl);
            CoTaskMemFree(pv);
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
        if ( v6 < 0 )
LABEL_41:
          v6 = CWallpaperCore::_AddPath((int)this, (int)this + 80, 0, v4, pidl);
        CoTaskMemFree(v26);
      }
      else
      {
LABEL_43:
        v6 = CWallpaperCore::_AddPath((int)this, (int)this + 80, 0, v4, pidl);
      }
      CoTaskMemFree(ppszName);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003f4dc  mov     [rsp-38h+arg_0], rbx
0x18003f4e1  push    rbp
0x18003f4e2  push    rsi
0x18003f4e3  push    rdi
0x18003f4e4  push    r12
0x18003f4e6  push    r13
0x18003f4e8  push    r14
0x18003f4ea  push    r15
0x18003f4ec  mov     rbp, rsp
0x18003f4ef  sub     rsp, 50h
0x18003f4f3  xor     r13d, r13d
0x18003f4f6  mov     r15, r8
0x18003f4f9  mov     r12, rdx
0x18003f4fc  mov     rbx, rcx
0x18003f4ff  mov     edi, r13d
0x18003f502  test    rdx, rdx
0x18003f505  jz      loc_18003F7E1
0x18003f50b  mov     esi, r13d
0x18003f50e  mov     rcx, [rbx+60h]; hdpa
0x18003f512  test    rcx, rcx
0x18003f515  jz      short loc_18003F51B
0x18003f517  mov     eax, [rcx]
0x18003f519  jmp     short loc_18003F51E
0x18003f51b  mov     eax, r13d
0x18003f51e  cmp     esi, eax
0x18003f520  jge     short loc_18003F56E
0x18003f522  movsxd  rdx, esi; i
0x18003f525  call    DPA_GetPtr
0x18003f52a  mov     r13, rax
0x18003f52d  xor     r14d, r14d
0x18003f530  mov     rcx, [r13+428h]; hdpa
0x18003f537  test    rcx, rcx
0x18003f53a  jz      short loc_18003F540
0x18003f53c  mov     eax, [rcx]
0x18003f53e  jmp     short loc_18003F542
0x18003f540  xor     eax, eax
0x18003f542  cmp     r14d, eax
0x18003f545  jge     short loc_18003F567
0x18003f547  movsxd  rdx, r14d; i
0x18003f54a  call    DPA_GetPtr
0x18003f54f  mov     rdx, rax; LPCITEMIDLIST
0x18003f552  mov     rcx, r15; pidl
0x18003f555  call    ILIsEqualByAliasOrPath
0x18003f55a  test    eax, eax
0x18003f55c  jnz     loc_18003F7E1
0x18003f562  inc     r14d
0x18003f565  jmp     short loc_18003F530
0x18003f567  inc     esi
0x18003f569  xor     r13d, r13d
0x18003f56c  jmp     short loc_18003F50E
0x18003f56e  mov     r14d, r13d
0x18003f571  mov     rcx, [rbx+50h]; hdpa
0x18003f575  test    rcx, rcx
0x18003f578  jz      short loc_18003F57E
0x18003f57a  mov     eax, [rcx]
0x18003f57c  jmp     short loc_18003F581
0x18003f57e  mov     eax, r13d
0x18003f581  cmp     r14d, eax
0x18003f584  jge     short loc_18003F5A6
0x18003f586  movsxd  rdx, r14d; i
0x18003f589  call    DPA_GetPtr
0x18003f58e  mov     rcx, r15; pidl
0x18003f591  mov     rdx, [rax]; LPCITEMIDLIST
0x18003f594  call    ILIsEqualByAliasOrPath
0x18003f599  test    eax, eax
0x18003f59b  jnz     loc_18003F7E1
0x18003f5a1  inc     r14d
0x18003f5a4  jmp     short loc_18003F571
0x18003f5a6  mov     r14d, r13d
0x18003f5a9  mov     rcx, [rbx+58h]; hdpa
0x18003f5ad  test    rcx, rcx
0x18003f5b0  jz      short loc_18003F5B6
0x18003f5b2  mov     eax, [rcx]
0x18003f5b4  jmp     short loc_18003F5B9
0x18003f5b6  mov     eax, r13d
0x18003f5b9  cmp     r14d, eax
0x18003f5bc  jge     short loc_18003F5DE
0x18003f5be  movsxd  rdx, r14d; i
0x18003f5c1  call    DPA_GetPtr
0x18003f5c6  mov     rcx, r15; pidl
0x18003f5c9  mov     rdx, [rax]; LPCITEMIDLIST
0x18003f5cc  call    ILIsEqualByAliasOrPath
0x18003f5d1  test    eax, eax
0x18003f5d3  jnz     loc_18003F7E1
0x18003f5d9  inc     r14d
0x18003f5dc  jmp     short loc_18003F5A9
0x18003f5de  lea     r8, [rbp+ppszName]; ppszName
0x18003f5e2  mov     [rbp+ppszName], r13
0x18003f5e6  mov     edx, 80028000h; sigdnName
0x18003f5eb  mov     rcx, r15; pidl
0x18003f5ee  call    cs:__imp_SHGetNameFromIDList
0x18003f5f5  nop     dword ptr [rax+rax+00h]
0x18003f5fa  test    eax, eax
0x18003f5fc  js      loc_18003F7C8
0x18003f602  mov     rax, [rbp+ppszName]
0x18003f606  lea     r9, _GUID_5357e238_fb12_4aca_a930_cab7832b84bf; riid
0x18003f60d  xor     edx, edx; pUnkOuter
0x18003f60f  mov     [rbp+var_10], rax
0x18003f613  lea     rax, [rbp+arg_18]
0x18003f617  mov     [rbp+var_8], r13
0x18003f61b  lea     rcx, CLSID_XFeedsManager; rclsid
0x18003f622  mov     [rbp+arg_18], r13
0x18003f626  mov     [rsp+50h+ppv], rax; ppv
0x18003f62b  lea     r8d, [rdx+1]; dwClsContext
0x18003f62f  call    cs:__imp_CoCreateInstance
0x18003f636  nop     dword ptr [rax+rax+00h]
0x18003f63b  test    eax, eax
0x18003f63d  js      loc_18003F79D
0x18003f643  mov     rcx, [rbp+arg_18]
0x18003f647  lea     r8, [rbp+pv]
0x18003f64b  mov     [rbp+pv], r13
0x18003f64f  lea     rdx, _GUID_4c963678_3a51_4b88_8531_98b90b6508f2
0x18003f656  mov     rax, [rcx]
0x18003f659  mov     rax, [rax+18h]
0x18003f65d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f662  mov     edi, eax
0x18003f664  test    eax, eax
0x18003f666  js      short loc_18003F685
0x18003f668  mov     rcx, [rbp+pv]; struct IXFeedFolder *
0x18003f66c  lea     r9, [rbp+var_10]; void *
0x18003f670  call    ?EnumerateRSSFeedsInFolder@@YAHPEAUIXFeedFolder@@P6AH0PEAX@ZP6AHPEAUIXFeed@@1@Z1@Z; EnumerateRSSFeedsInFolder(IXFeedFolder *,int (*)(IXFeedFolder *,void *),int (*)(IXFeed *,void *),void *)
0x18003f675  mov     rcx, [rbp+pv]
0x18003f679  mov     rax, [rcx]
0x18003f67c  mov     rax, [rax+10h]
0x18003f680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f685  mov     rcx, [rbp+arg_18]
0x18003f689  mov     rax, [rcx]
0x18003f68c  mov     rax, [rax+10h]
0x18003f690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f695  test    edi, edi
0x18003f697  js      loc_18003F79D
0x18003f69d  mov     rsi, [rbp+var_8]
0x18003f6a1  test    rsi, rsi
0x18003f6a4  jz      loc_18003F79D
0x18003f6aa  xor     edx, edx; pUnkOuter
0x18003f6ac  mov     [rbp+var_20], r13
0x18003f6b0  lea     rax, [rbp+var_20]
0x18003f6b4  lea     r9, _GUID_5357e238_fb12_4aca_a930_cab7832b84bf; riid
0x18003f6bb  mov     [rsp+50h+ppv], rax; ppv
0x18003f6c0  lea     rcx, CLSID_XFeedsManager; rclsid
0x18003f6c7  lea     r8d, [rdx+3]; dwClsContext
0x18003f6cb  call    cs:__imp_CoCreateInstance
0x18003f6d2  nop     dword ptr [rax+rax+00h]
0x18003f6d7  test    eax, eax
0x18003f6d9  js      loc_18003F773
0x18003f6df  mov     rcx, [rbp+var_20]
0x18003f6e3  lea     r9, [rbp+arg_18]
0x18003f6e7  mov     [rbp+arg_18], r13
0x18003f6eb  lea     r8, _GUID_a44179a4_e0f6_403b_af8d_d080f425a451
0x18003f6f2  mov     rdx, rsi
0x18003f6f5  mov     rax, [rcx]
0x18003f6f8  mov     rax, [rax+38h]
0x18003f6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f701  mov     edi, eax
0x18003f703  test    eax, eax
0x18003f705  js      short loc_18003F75F
0x18003f707  mov     rcx, [rbp+arg_18]
0x18003f70b  lea     rdx, [rbp+pv]
0x18003f70f  mov     [rbp+pv], r13
0x18003f713  mov     rax, [rcx]
0x18003f716  mov     rax, [rax+20h]
0x18003f71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f71f  mov     edi, eax
0x18003f721  test    eax, eax
0x18003f723  js      short loc_18003F74F
0x18003f725  mov     r9, [rbp+pv]; int
0x18003f729  lea     rdx, [rbx+50h]; int
0x18003f72d  xor     r8d, r8d; int
0x18003f730  mov     [rsp+50h+ppv], r15; pidl
0x18003f735  mov     rcx, rbx; int
0x18003f738  call    ?_AddPath@CWallpaperCore@@AEAAJPEAV?$CDPANewMem@UWALLPAPER_PATH@CWallpaperCore@@@@W4PATHTYPE@1@PEBGPEBU_ITEMIDLIST_ABSOLUTE@@H@Z; CWallpaperCore::_AddPath(CDPANewMem<CWallpaperCore::WALLPAPER_PATH> *,CWallpaperCore::PATHTYPE,ushort const *,_ITEMIDLIST_ABSOLUTE const *,int)
0x18003f73d  mov     rcx, [rbp+pv]; pv
0x18003f741  mov     edi, eax
0x18003f743  call    cs:__imp_CoTaskMemFree
0x18003f74a  nop     dword ptr [rax+rax+00h]
0x18003f74f  mov     rcx, [rbp+arg_18]
0x18003f753  mov     rax, [rcx]
0x18003f756  mov     rax, [rax+10h]
0x18003f75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f75f  mov     rcx, [rbp+var_20]
0x18003f763  mov     rax, [rcx]
0x18003f766  mov     rax, [rax+10h]
0x18003f76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f76f  test    edi, edi
0x18003f771  jns     short loc_18003F78C
0x18003f773  lea     rdx, [rbx+50h]; int
0x18003f777  mov     [rsp+50h+ppv], r15; pidl
0x18003f77c  mov     r9, r12; int
0x18003f77f  xor     r8d, r8d; int
0x18003f782  mov     rcx, rbx; int
0x18003f785  call    ?_AddPath@CWallpaperCore@@AEAAJPEAV?$CDPANewMem@UWALLPAPER_PATH@CWallpaperCore@@@@W4PATHTYPE@1@PEBGPEBU_ITEMIDLIST_ABSOLUTE@@H@Z; CWallpaperCore::_AddPath(CDPANewMem<CWallpaperCore::WALLPAPER_PATH> *,CWallpaperCore::PATHTYPE,ushort const *,_ITEMIDLIST_ABSOLUTE const *,int)
0x18003f78a  mov     edi, eax
0x18003f78c  mov     rcx, rsi; pv
0x18003f78f  call    cs:__imp_CoTaskMemFree
0x18003f796  nop     dword ptr [rax+rax+00h]
0x18003f79b  jmp     short loc_18003F7B6
0x18003f79d  lea     rdx, [rbx+50h]; int
0x18003f7a1  mov     [rsp+50h+ppv], r15; pidl
0x18003f7a6  mov     r9, r12; int
0x18003f7a9  xor     r8d, r8d; int
0x18003f7ac  mov     rcx, rbx; int
0x18003f7af  call    ?_AddPath@CWallpaperCore@@AEAAJPEAV?$CDPANewMem@UWALLPAPER_PATH@CWallpaperCore@@@@W4PATHTYPE@1@PEBGPEBU_ITEMIDLIST_ABSOLUTE@@H@Z; CWallpaperCore::_AddPath(CDPANewMem<CWallpaperCore::WALLPAPER_PATH> *,CWallpaperCore::PATHTYPE,ushort const *,_ITEMIDLIST_ABSOLUTE const *,int)
0x18003f7b4  mov     edi, eax
0x18003f7b6  mov     rcx, [rbp+ppszName]; pv
0x18003f7ba  call    cs:__imp_CoTaskMemFree
0x18003f7c1  nop     dword ptr [rax+rax+00h]
0x18003f7c6  jmp     short loc_18003F7E1
0x18003f7c8  lea     rdx, [rbx+50h]; int
0x18003f7cc  mov     [rsp+50h+ppv], r15; pidl
0x18003f7d1  mov     r9, r12; int
0x18003f7d4  xor     r8d, r8d; int
0x18003f7d7  mov     rcx, rbx; int
0x18003f7da  call    ?_AddPath@CWallpaperCore@@AEAAJPEAV?$CDPANewMem@UWALLPAPER_PATH@CWallpaperCore@@@@W4PATHTYPE@1@PEBGPEBU_ITEMIDLIST_ABSOLUTE@@H@Z; CWallpaperCore::_AddPath(CDPANewMem<CWallpaperCore::WALLPAPER_PATH> *,CWallpaperCore::PATHTYPE,ushort const *,_ITEMIDLIST_ABSOLUTE const *,int)
0x18003f7df  mov     edi, eax
0x18003f7e1  mov     rbx, [rsp+50h+arg_0]
0x18003f7e9  mov     eax, edi
0x18003f7eb  add     rsp, 50h
0x18003f7ef  pop     r15
0x18003f7f1  pop     r14
0x18003f7f3  pop     r13
0x18003f7f5  pop     r12
0x18003f7f7  pop     rdi
0x18003f7f8  pop     rsi
0x18003f7f9  pop     rbp
0x18003f7fa  retn
```
