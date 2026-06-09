# CSlideshowSettingsAdapter::GetAllMatchingWallpapers(IWallpaperCollection * *)

- ea: `0x180004e50`
- end: `0x1800051b2`
- name: `?GetAllMatchingWallpapers@CSlideshowSettingsAdapter@@UEAAJPEAPEAUIWallpaperCollection@@@Z`
- size: `866`
- prototype: `__int64 __fastcall(CSlideshowSettingsAdapter *__hidden this, struct IWallpaperCollection **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004d70`
- `0x180004da0`
- `0x180004e50`
- `0x1800051b8`
- `0x1800051fc`
- `0x1800199d0`
- `0x1800336e0`
- `0x180035ccc`
- `0x180060b7c`
- `0x180060b9c`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180004f81`
- `SHELL32!SHCreateItemFromIDList` at `0x180004f81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004efe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004efe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004ff2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004ff2`

## pseudocode

```c
__int64 __fastcall CSlideshowSettingsAdapter::GetAllMatchingWallpapers(
        CSlideshowSettingsAdapter *this,
        struct IWallpaperCollection **a2)
{
  volatile signed __int32 *v3; // rax
  CFileSource *v4; // r14
  volatile signed __int32 *v5; // rdi
  __int64 v6; // rax
  struct CWallpaperCollection *v7; // rax
  struct CWallpaperCollection *v8; // rbx
  HRESULT v9; // esi
  HANDLE ProcessHeap; // rax
  void *v11; // rax
  const ITEMIDLIST *v13; // rcx
  volatile signed __int32 *v14; // rax
  volatile signed __int32 *v15; // rbx
  struct IWallpaperCollection *v16; // rax
  int v17; // esi
  volatile signed __int32 *v18; // r15
  void *v19; // rax
  HDPA v20; // rax
  __int64 v21; // rax
  CNamespaceWalkFilter *v22; // rbx
  void *ppv; // [rsp+60h] [rbp+30h] BYREF
  __int64 v24; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 6);
  if ( v3 )
    _InterlockedAdd(v3, 1u);
  v4 = (CFileSource *)*((_QWORD *)this + 6);
  if ( !v4 )
    return (unsigned int)-2147467259;
  v5 = (volatile signed __int32 *)*((_QWORD *)v4 + 3);
  if ( v5 )
  {
    if ( !*(_QWORD *)v5 )
    {
      *((_QWORD *)v4 + 3) = 0;
      goto LABEL_42;
    }
    if ( **(_DWORD **)v5 )
      goto LABEL_8;
  }
  *((_QWORD *)v4 + 3) = 0;
  if ( v5 )
LABEL_42:
    CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release((void *)v5);
  v6 = *((_QWORD *)v4 + 2);
  if ( !v6 )
  {
    v13 = (const ITEMIDLIST *)*((_QWORD *)v4 + 1);
    v24 = 0;
    ppv = 0;
    v9 = SHCreateItemFromIDList(v13, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( v9 < 0 )
      goto LABEL_15;
    v9 = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           0,
           &BHID_SFObject,
           &GUID_000214e6_0000_0000_c000_000000000046,
           &v24);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v9 < 0 )
      goto LABEL_15;
    v5 = 0;
    ppv = 0;
    v9 = CoCreateInstance(&CLSID_NamespaceWalker, 0, 1u, &GUID_57ced8a7_3f4a_432c_9350_30f24483f74f, &ppv);
    if ( v9 >= 0 )
    {
      v14 = (volatile signed __int32 *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v15 = v14;
      if ( !v14 )
        goto LABEL_22;
      *(_QWORD *)v14 = 0;
      *((_DWORD *)v14 + 2) = 1;
      v20 = g_pfn_DPA_Create(64);
      *(_QWORD *)v15 = v20;
      if ( v20 )
      {
        v17 = 0;
        v18 = v15;
        _InterlockedIncrement(v15 + 2);
      }
      else
      {
        v18 = 0;
        v17 = -2147024882;
      }
      CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release((void *)v15);
      if ( v17 >= 0 )
      {
        v19 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v19
          && (v21 = CNamespaceWalkFilter::CNamespaceWalkFilter(v19, v18), (v22 = (CNamespaceWalkFilter *)v21) != 0) )
        {
          v9 = (*(__int64 (__fastcall **)(void *, __int64, __int64, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 v24,
                 263341,
                 0,
                 v21);
          if ( v9 >= 0 )
          {
            v5 = v18;
            _InterlockedIncrement(v18 + 2);
            *((_QWORD *)v4 + 3) = v18;
            _InterlockedIncrement(v18 + 2);
          }
          CNamespaceWalkFilter::Release(v22);
        }
        else
        {
          v9 = -2147024882;
        }
        CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release((void *)v18);
      }
      else
      {
LABEL_22:
        v9 = -2147024882;
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v9 < 0 )
      goto LABEL_15;
    goto LABEL_9;
  }
  *((_QWORD *)v4 + 3) = v6;
  _InterlockedAdd((volatile signed __int32 *)(v6 + 8), 1u);
  v5 = (volatile signed __int32 *)*((_QWORD *)v4 + 3);
LABEL_8:
  _InterlockedAdd(v5 + 2, 1u);
LABEL_9:
  v7 = (struct CWallpaperCollection *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    *(_DWORD *)v7 = 1;
    *((_QWORD *)v7 + 2) = 0;
    *((_DWORD *)v7 + 6) = 0;
    *((_QWORD *)v7 + 1) = v5;
    _InterlockedAdd(v5 + 2, 1u);
    v9 = 0;
  }
  else
  {
    v9 = -2147024882;
  }
  CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release((void *)v5);
  if ( v9 >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v11 = HeapAlloc(ProcessHeap, 8u, 0x18u);
    ppv = v11;
    if ( v11
      && (v16 = CWallpaperCollectionAdapter::CWallpaperCollectionAdapter((CWallpaperCollectionAdapter *)v11, v8)) != 0 )
    {
      *a2 = v16;
    }
    else
    {
      v9 = -2147024882;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 && v8 )
    {
      CWallpaperCollection::~CWallpaperCollection(v8);
      operator delete(v8);
    }
  }
LABEL_15:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4, 0xFFFFFFFF) == 1 )
  {
    CFileSource::~CFileSource(v4);
    operator delete(v4);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004e50  mov     [rsp-28h+arg_10], rbx
0x180004e55  mov     [rsp-28h+arg_18], rsi
0x180004e5a  push    rbp
0x180004e5b  push    rdi
0x180004e5c  push    r12
0x180004e5e  push    r14
0x180004e60  push    r15
0x180004e62  mov     rbp, rsp
0x180004e65  sub     rsp, 30h
0x180004e69  mov     qword ptr [rdx], 0
0x180004e70  mov     r12, rdx
0x180004e73  mov     rax, [rcx+30h]
0x180004e77  mov     r15d, 1
0x180004e7d  test    rax, rax
0x180004e80  jz      short loc_180004E86
0x180004e82  lock add [rax], r15d
0x180004e86  mov     r14, [rcx+30h]
0x180004e8a  test    r14, r14
0x180004e8d  jz      loc_180005051
0x180004e93  mov     rdi, [r14+18h]
0x180004e97  test    rdi, rdi
0x180004e9a  jnz     loc_18000514B
0x180004ea0  mov     qword ptr [r14+18h], 0
0x180004ea8  test    rdi, rdi
0x180004eab  jnz     loc_180005157
0x180004eb1  mov     rax, [r14+10h]
0x180004eb5  test    rax, rax
0x180004eb8  jz      loc_180004F62
0x180004ebe  mov     [r14+18h], rax
0x180004ec2  lock add [rax+8], r15d
0x180004ec7  mov     rdi, [r14+18h]
0x180004ecb  lock add [rdi+8], r15d
0x180004ed0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004ed7  mov     ecx, 20h ; ' '; unsigned __int64
0x180004edc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004ee1  mov     rbx, rax
0x180004ee4  test    rax, rax
0x180004ee7  jnz     loc_180005172
0x180004eed  mov     esi, 8007000Eh
0x180004ef2  mov     rcx, rdi; lpMem
0x180004ef5  call    ?Release@?$CRefCountedDPA@V?$CDPAItemIdList@U_ITEMIDLIST_ABSOLUTE@@@@@@QEAAKXZ; CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release(void)
0x180004efa  test    esi, esi
0x180004efc  js      short loc_180004F38
0x180004efe  call    cs:__imp_GetProcessHeap
0x180004f04  mov     edx, 8; dwFlags
0x180004f09  mov     rcx, rax; hHeap
0x180004f0c  lea     r8d, [rdx+10h]; dwBytes
0x180004f10  call    cs:__imp_HeapAlloc
0x180004f16  mov     [rbp+ppv], rax
0x180004f1a  test    rax, rax
0x180004f1d  jnz     loc_18000505B
0x180004f23  mov     esi, 8007000Eh
0x180004f28  or      eax, 0FFFFFFFFh
0x180004f2b  lock xadd [rbx], eax
0x180004f2f  cmp     eax, 1
0x180004f32  jz      loc_180005194
0x180004f38  or      eax, 0FFFFFFFFh
0x180004f3b  lock xadd [r14], eax
0x180004f40  cmp     eax, 1
0x180004f43  jz      loc_180005078
0x180004f49  mov     rbx, [rsp+30h+arg_10]
0x180004f4e  mov     eax, esi
0x180004f50  mov     rsi, [rsp+30h+arg_18]
0x180004f55  add     rsp, 30h
0x180004f59  pop     r15
0x180004f5b  pop     r14
0x180004f5d  pop     r12
0x180004f5f  pop     rdi
0x180004f60  pop     rbp
0x180004f61  retn
0x180004f62  mov     rcx, [r14+8]; pidl
0x180004f66  lea     r8, [rbp+ppv]; ppv
0x180004f6a  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180004f71  mov     [rbp+arg_8], 0
0x180004f79  mov     [rbp+ppv], 0
0x180004f81  call    cs:__imp_SHCreateItemFromIDList
0x180004f87  mov     esi, eax
0x180004f89  test    eax, eax
0x180004f8b  js      short loc_180004F38
0x180004f8d  mov     rcx, [rbp+ppv]
0x180004f91  lea     rdx, [rbp+arg_8]
0x180004f95  mov     [rsp+30h+var_10], rdx
0x180004f9a  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180004fa1  lea     r8, BHID_SFObject
0x180004fa8  xor     edx, edx
0x180004faa  mov     rax, [rcx]
0x180004fad  mov     rax, [rax+18h]
0x180004fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb6  mov     rcx, [rbp+ppv]
0x180004fba  mov     esi, eax
0x180004fbc  mov     rax, [rcx]
0x180004fbf  mov     rax, [rax+10h]
0x180004fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc8  test    esi, esi
0x180004fca  js      loc_180004F38
0x180004fd0  lea     rax, [rbp+ppv]
0x180004fd4  xor     edi, edi
0x180004fd6  lea     r9, _GUID_57ced8a7_3f4a_432c_9350_30f24483f74f; riid
0x180004fdd  mov     [rbp+ppv], rdi
0x180004fe1  mov     r8d, r15d; dwClsContext
0x180004fe4  mov     [rsp+30h+var_10], rax; ppv
0x180004fe9  xor     edx, edx; pUnkOuter
0x180004feb  lea     rcx, CLSID_NamespaceWalker; rclsid
0x180004ff2  call    cs:__imp_CoCreateInstance
0x180004ff8  mov     esi, eax
0x180004ffa  test    eax, eax
0x180004ffc  js      short loc_180005034
0x180004ffe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005005  lea     ecx, [rdi+10h]; unsigned __int64
0x180005008  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000500d  mov     rbx, rax
0x180005010  test    rax, rax
0x180005013  jnz     loc_1800050CE
0x180005019  mov     esi, 8007000Eh
0x18000501e  mov     rcx, [rbp+ppv]
0x180005022  mov     rax, [rcx]
0x180005025  mov     rax, [rax+10h]
0x180005029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502e  mov     r15d, 1
0x180005034  mov     rcx, [rbp+arg_8]
0x180005038  mov     rax, [rcx]
0x18000503b  mov     rax, [rax+10h]
0x18000503f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005044  test    esi, esi
0x180005046  js      loc_180004F38
0x18000504c  jmp     loc_180004ED0
0x180005051  mov     esi, 80004005h
0x180005056  jmp     loc_180004F49
0x18000505b  mov     rdx, rbx; struct CWallpaperCollection *
0x18000505e  mov     rcx, rax; this
0x180005061  call    ??0CWallpaperCollectionAdapter@@QEAA@PEAVCWallpaperCollection@@@Z; CWallpaperCollectionAdapter::CWallpaperCollectionAdapter(CWallpaperCollection *)
0x180005066  test    rax, rax
0x180005069  jz      loc_180004F23
0x18000506f  mov     [r12], rax
0x180005073  jmp     loc_180004F28
0x180005078  mov     rcx, r14; this
0x18000507b  call    ??1CFileSource@@AEAA@XZ; CFileSource::~CFileSource(void)
0x180005080  mov     rcx, r14; lpMem
0x180005083  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005088  jmp     loc_180004F49
0x18000508d  xor     esi, esi
0x18000508f  mov     r15, rbx
0x180005092  lock inc dword ptr [rbx+8]
0x180005096  mov     rcx, rbx; lpMem
0x180005099  call    ?Release@?$CRefCountedDPA@V?$CDPAItemIdList@U_ITEMIDLIST_ABSOLUTE@@@@@@QEAAKXZ; CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release(void)
0x18000509e  test    esi, esi
0x1800050a0  js      loc_180005019
0x1800050a6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800050ad  mov     ecx, 18h; unsigned __int64
0x1800050b2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800050b7  test    rax, rax
0x1800050ba  jnz     short loc_1800050F2
0x1800050bc  mov     esi, 8007000Eh
0x1800050c1  mov     rcx, r15; lpMem
0x1800050c4  call    ?Release@?$CRefCountedDPA@V?$CDPAItemIdList@U_ITEMIDLIST_ABSOLUTE@@@@@@QEAAKXZ; CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release(void)
0x1800050c9  jmp     loc_18000501E
0x1800050ce  mov     [rax], rdi
0x1800050d1  mov     ecx, 40h ; '@'; cItemGrow
0x1800050d6  mov     [rax+8], r15d
0x1800050da  call    cs:g_pfn_DPA_Create
0x1800050e0  mov     [rbx], rax
0x1800050e3  test    rax, rax
0x1800050e6  jnz     short loc_18000508D
0x1800050e8  xor     r15d, r15d
0x1800050eb  mov     esi, 8007000Eh
0x1800050f0  jmp     short loc_180005096
0x1800050f2  mov     rdx, r15
0x1800050f5  mov     rcx, rax
0x1800050f8  call    ??0CNamespaceWalkFilter@@QEAA@PEAV?$CRefCountedDPA@V?$CDPAItemIdList@U_ITEMIDLIST_ABSOLUTE@@@@@@@Z; CNamespaceWalkFilter::CNamespaceWalkFilter(CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>> *)
0x1800050fd  mov     rbx, rax
0x180005100  test    rax, rax
0x180005103  jz      short loc_1800050BC
0x180005105  mov     rcx, [rbp+ppv]
0x180005109  xor     r9d, r9d
0x18000510c  mov     rdx, [rbp+arg_8]
0x180005110  mov     [rsp+30h+var_10], rbx
0x180005115  mov     r8, [rcx]
0x180005118  mov     rax, [r8+18h]
0x18000511c  mov     r8d, 404ADh
0x180005122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005127  mov     esi, eax
0x180005129  test    eax, eax
0x18000512b  js      short loc_18000513E
0x18000512d  mov     rdi, r15
0x180005130  lock inc dword ptr [r15+8]
0x180005135  mov     [r14+18h], r15
0x180005139  lock inc dword ptr [r15+8]
0x18000513e  mov     rcx, rbx; this
0x180005141  call    ?Release@CNamespaceWalkFilter@@UEAAKXZ; CNamespaceWalkFilter::Release(void)
0x180005146  jmp     loc_1800050C1
0x18000514b  mov     rax, [rdi]
0x18000514e  test    rax, rax
0x180005151  jnz     short loc_180005164
0x180005153  mov     [r14+18h], rax
0x180005157  mov     rcx, rdi; lpMem
0x18000515a  call    ?Release@?$CRefCountedDPA@V?$CDPAItemIdList@U_ITEMIDLIST_ABSOLUTE@@@@@@QEAAKXZ; CRefCountedDPA<CDPAItemIdList<_ITEMIDLIST_ABSOLUTE>>::Release(void)
0x18000515f  jmp     loc_180004EB1
0x180005164  cmp     dword ptr [rax], 0
0x180005167  jz      loc_180004EA0
0x18000516d  jmp     loc_180004ECB
0x180005172  mov     [rax], r15d
0x180005175  mov     qword ptr [rax+10h], 0
0x18000517d  mov     dword ptr [rax+18h], 0
0x180005184  mov     [rax+8], rdi
0x180005188  lock add [rdi+8], r15d
0x18000518d  xor     esi, esi
0x18000518f  jmp     loc_180004EF2
0x180005194  test    rbx, rbx
0x180005197  jz      loc_180004F38
0x18000519d  mov     rcx, rbx; this
0x1800051a0  call    ??1CWallpaperCollection@@AEAA@XZ; CWallpaperCollection::~CWallpaperCollection(void)
0x1800051a5  mov     rcx, rbx; lpMem
0x1800051a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800051ad  jmp     loc_180004F38
```
