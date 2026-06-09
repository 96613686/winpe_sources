# CZipFolder::BuildMainEnumerator(HWND__ *)

- ea: `0x18000ed94`
- end: `0x18000eff2`
- name: `?BuildMainEnumerator@CZipFolder@@QEAAJPEAUHWND__@@@Z`
- size: `606`
- prototype: `__int64 __fastcall(CZipFolder *__hidden this, HWND)`
- caller_count: `6`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e970`
- `0x180011ab0`
- `0x180012550`
- `0x180012de0`
- `0x18001ea30`
- `0x18002cc30`

## callees

- `0x18000ac9c`
- `0x18000ed94`
- `0x180010c30`
- `0x180012160`
- `0x180012648`
- `0x18001e8a4`
- `0x18001fa2c`
- `0x18001fae8`
- `0x180020344`
- `0x1800214ac`
- `0x180025864`
- `0x1800318f8`
- `0x180032684`
- `0x180036f50`
- `0x18003732c`
- `0x180037958`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eec0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eec0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ee0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ee0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ee2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ee2f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ee96`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ee96`
- `KERNEL32!lstrcmpiW` at `0x18000ef06`
- `KERNEL32!lstrcmpiW` at `0x18000ef06`

## pseudocode

```c
__int64 __fastcall CZipFolder::BuildMainEnumerator(CZipFolder *this, HWND a2)
{
  int ZipFiletime; // ebx
  CEnumArchive **v5; // rdi
  __int64 v6; // rdx
  const WCHAR *v7; // r14
  CZipFolder *v8; // rcx
  int EnumeratorFromCache; // ebx
  __int64 v10; // rcx
  CZipFolder *v12; // rcx
  struct _DSA *v13; // rcx
  int v14; // ebx
  const WCHAR *ItemPtr; // rax
  const WCHAR *v16; // rsi
  CEnumArchive *v17; // rax
  CEnumArchive *v18; // rax
  RTL_SRWLOCK *v19; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 pitem[260]; // [rsp+30h] [rbp-D0h] BYREF
  CEnumArchive *v21; // [rsp+238h] [rbp+138h]
  FILETIME FileTime1; // [rsp+240h] [rbp+140h] BYREF

  FileTime1 = 0;
  ZipFiletime = CZipFolder::GetZipFiletime(this, &FileTime1);
  if ( ZipFiletime < 0 )
    return (unsigned int)ZipFiletime;
  v5 = (CEnumArchive **)((char *)this + 1120);
  v6 = *((_QWORD *)this + 140);
  if ( v6 )
  {
    if ( !CompareFileTime(&FileTime1, (const FILETIME *)(v6 + 36)) )
      return (unsigned int)ZipFiletime;
  }
  SafeRelease<CEnumArchive>((char *)this + 1120);
  AcquireSRWLockShared(&g_srwCacheLock);
  v7 = (const WCHAR *)((char *)this + 72);
  EnumeratorFromCache = CZipFolder::_GetEnumeratorFromCache(
                          v8,
                          (const unsigned __int16 *)this + 36,
                          FileTime1,
                          (struct CEnumArchive **)this + 140);
  ReleaseSRWLockShared(&g_srwCacheLock);
  if ( EnumeratorFromCache >= 0 )
    goto LABEL_4;
  AcquireSRWLockExclusive(&g_srwCacheLock);
  v19 = &g_srwCacheLock;
  ZipFiletime = CZipFolder::_GetEnumeratorFromCache(
                  v12,
                  (const unsigned __int16 *)this + 36,
                  FileTime1,
                  (struct CEnumArchive **)this + 140);
  if ( ZipFiletime < 0 )
  {
    v13 = g_hdsaEnumCache;
    v14 = *(_DWORD *)g_hdsaEnumCache - 1;
    if ( v14 >= 0 )
    {
      while ( 1 )
      {
        ItemPtr = (const WCHAR *)DSA_GetItemPtr(v13, v14);
        v16 = ItemPtr;
        if ( ItemPtr && !lstrcmpiW(v7, ItemPtr) )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 + 65) + 16LL))(*((_QWORD *)v16 + 65));
          DSA_DeleteItem(g_hdsaEnumCache, v14);
        }
        if ( --v14 < 0 )
          break;
        v13 = g_hdsaEnumCache;
      }
    }
    v17 = (CEnumArchive *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
    {
      v18 = CEnumArchive::CEnumArchive(v17);
      *v5 = v18;
      if ( v18 )
      {
        *(FILETIME *)((char *)v18 + 36) = FileTime1;
        memset_0(pitem, 0, 0x210u);
        ZipFiletime = StringCchCopyW(pitem, 0x104u, v7);
        if ( ZipFiletime < 0 )
          goto LABEL_10;
        v21 = *v5;
        if ( DSA_InsertItem(g_hdsaEnumCache, 0, pitem) != -1 )
        {
          (*(void (__fastcall **)(CEnumArchive *))(*(_QWORD *)*v5 + 8LL))(*v5);
          goto LABEL_10;
        }
      }
    }
    else
    {
      *v5 = 0;
    }
    ZipFiletime = -2147024882;
  }
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
  if ( ZipFiletime < 0 )
  {
LABEL_11:
    SafeRelease<CEnumArchive>(v5);
    return (unsigned int)ZipFiletime;
  }
LABEL_4:
  ZipFiletime = CEnumArchive::InitInstance(*v5, v7, a2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExplorerArchiveIntegrationPerf>::__private_IsEnabled(v10) )
    CEnumArchive::Lock(*v5);
  if ( ZipFiletime < 0 )
    goto LABEL_11;
  return (unsigned int)ZipFiletime;
}

```

## disassembly

```asm
0x18000ed94  mov     [rsp-8+arg_10], rbx
0x18000ed99  mov     [rsp-8+arg_18], rsi
0x18000ed9e  push    rbp
0x18000ed9f  push    rdi
0x18000eda0  push    r12
0x18000eda2  push    r14
0x18000eda4  push    r15
0x18000eda6  lea     rbp, [rsp-150h]
0x18000edae  sub     rsp, 250h
0x18000edb5  mov     rax, cs:__security_cookie
0x18000edbc  xor     rax, rsp
0x18000edbf  mov     [rbp+170h+var_28], rax
0x18000edc6  mov     r15, rdx
0x18000edc9  mov     qword ptr [rbp+170h+FileTime1.dwLowDateTime], 0
0x18000edd4  lea     rdx, [rbp+170h+FileTime1]; struct _FILETIME *
0x18000eddb  mov     rsi, rcx
0x18000edde  call    ?GetZipFiletime@CZipFolder@@QEAAJPEAU_FILETIME@@@Z; CZipFolder::GetZipFiletime(_FILETIME *)
0x18000ede3  mov     ebx, eax
0x18000ede5  test    eax, eax
0x18000ede7  js      short loc_18000EE5E
0x18000ede9  lea     rdi, [rsi+460h]
0x18000edf0  mov     rdx, [rdi]
0x18000edf3  test    rdx, rdx
0x18000edf6  jnz     loc_18000EE8B
0x18000edfc  mov     rcx, rdi
0x18000edff  call    ??$SafeRelease@VCEnumArchive@@@@YAXPEAPEAVCEnumArchive@@@Z; SafeRelease<CEnumArchive>(CEnumArchive * *)
0x18000ee04  lea     r12, ?g_srwCacheLock@@3Vsrwlock@wil@@A; wil::srwlock g_srwCacheLock
0x18000ee0b  mov     rcx, r12; SRWLock
0x18000ee0e  call    cs:__imp_AcquireSRWLockShared
0x18000ee14  mov     r8, qword ptr [rbp+170h+FileTime1.dwLowDateTime]; struct _FILETIME
0x18000ee1b  lea     r14, [rsi+48h]
0x18000ee1f  mov     rdx, r14; unsigned __int16 *
0x18000ee22  mov     r9, rdi; struct CEnumArchive **
0x18000ee25  call    ?_GetEnumeratorFromCache@CZipFolder@@AEAAJPEBGU_FILETIME@@PEAPEAVCEnumArchive@@@Z; CZipFolder::_GetEnumeratorFromCache(ushort const *,_FILETIME,CEnumArchive * *)
0x18000ee2a  mov     rcx, r12; SRWLock
0x18000ee2d  mov     ebx, eax
0x18000ee2f  call    cs:__imp_ReleaseSRWLockShared
0x18000ee35  test    ebx, ebx
0x18000ee37  js      loc_18000EEBD
0x18000ee3d  mov     rcx, [rdi]; this
0x18000ee40  mov     r8, r15; HWND
0x18000ee43  mov     rdx, r14; unsigned __int16 *
0x18000ee46  call    ?InitInstance@CEnumArchive@@QEAAJPEBGPEAUHWND__@@@Z; CEnumArchive::InitInstance(ushort const *,HWND__ *)
0x18000ee4b  mov     ebx, eax
0x18000ee4d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExplorerArchiveIntegrationPerf@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExplorerArchiveIntegrationPerf>::__private_IsEnabled(void)
0x18000ee52  test    al, al
0x18000ee54  jnz     loc_18000EFE5
0x18000ee5a  test    ebx, ebx
0x18000ee5c  js      short loc_18000EEB3
0x18000ee5e  mov     eax, ebx
0x18000ee60  mov     rcx, [rbp+170h+var_28]
0x18000ee67  xor     rcx, rsp; StackCookie
0x18000ee6a  call    __security_check_cookie
0x18000ee6f  lea     r11, [rsp+270h+var_20]
0x18000ee77  mov     rbx, [r11+40h]
0x18000ee7b  mov     rsi, [r11+48h]
0x18000ee7f  mov     rsp, r11
0x18000ee82  pop     r15
0x18000ee84  pop     r14
0x18000ee86  pop     r12
0x18000ee88  pop     rdi
0x18000ee89  pop     rbp
0x18000ee8a  retn
0x18000ee8b  add     rdx, 24h ; '$'; lpFileTime2
0x18000ee8f  lea     rcx, [rbp+170h+FileTime1]; lpFileTime1
0x18000ee96  call    cs:__imp_CompareFileTime
0x18000ee9c  test    eax, eax
0x18000ee9e  jz      short loc_18000EE5E
0x18000eea0  jmp     loc_18000EDFC
0x18000eea5  lea     rcx, [rsp+270h+var_250]
0x18000eeaa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000eeaf  test    ebx, ebx
0x18000eeb1  jns     short loc_18000EE3D
0x18000eeb3  mov     rcx, rdi
0x18000eeb6  call    ??$SafeRelease@VCEnumArchive@@@@YAXPEAPEAVCEnumArchive@@@Z; SafeRelease<CEnumArchive>(CEnumArchive * *)
0x18000eebb  jmp     short loc_18000EE5E
0x18000eebd  mov     rcx, r12; SRWLock
0x18000eec0  call    cs:__imp_AcquireSRWLockExclusive
0x18000eec6  mov     r8, qword ptr [rbp+170h+FileTime1.dwLowDateTime]; struct _FILETIME
0x18000eecd  mov     r9, rdi; struct CEnumArchive **
0x18000eed0  mov     rdx, r14; unsigned __int16 *
0x18000eed3  mov     [rsp+270h+var_250], r12
0x18000eed8  call    ?_GetEnumeratorFromCache@CZipFolder@@AEAAJPEBGU_FILETIME@@PEAPEAVCEnumArchive@@@Z; CZipFolder::_GetEnumeratorFromCache(ushort const *,_FILETIME,CEnumArchive * *)
0x18000eedd  mov     ebx, eax
0x18000eedf  test    eax, eax
0x18000eee1  jns     short loc_18000EEA5
0x18000eee3  mov     rcx, cs:?g_hdsaEnumCache@@3PEAU_DSA@@EA; hdsa
0x18000eeea  mov     ebx, [rcx]
0x18000eeec  sub     ebx, 1
0x18000eeef  js      short loc_18000EF3F
0x18000eef1  mov     edx, ebx; i
0x18000eef3  call    DSA_GetItemPtr
0x18000eef8  mov     rsi, rax
0x18000eefb  test    rax, rax
0x18000eefe  jz      short loc_18000EF31
0x18000ef00  mov     rdx, rax; lpString2
0x18000ef03  mov     rcx, r14; lpString1
0x18000ef06  call    cs:__imp_lstrcmpiW
0x18000ef0c  test    eax, eax
0x18000ef0e  jnz     short loc_18000EF31
0x18000ef10  mov     rcx, [rsi+208h]
0x18000ef17  mov     rax, [rcx]
0x18000ef1a  mov     rax, [rax+10h]
0x18000ef1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef23  mov     rcx, cs:?g_hdsaEnumCache@@3PEAU_DSA@@EA; hdsa
0x18000ef2a  mov     edx, ebx; i
0x18000ef2c  call    DSA_DeleteItem
0x18000ef31  sub     ebx, 1
0x18000ef34  js      short loc_18000EF3F
0x18000ef36  mov     rcx, cs:?g_hdsaEnumCache@@3PEAU_DSA@@EA; _DSA * g_hdsaEnumCache
0x18000ef3d  jmp     short loc_18000EEF1
0x18000ef3f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ef46  mov     ecx, 68h ; 'h'; unsigned __int64
0x18000ef4b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ef50  test    rax, rax
0x18000ef53  jz      short loc_18000EFD4
0x18000ef55  mov     rcx, rax; this
0x18000ef58  call    ??0CEnumArchive@@QEAA@XZ; CEnumArchive::CEnumArchive(void)
0x18000ef5d  mov     [rdi], rax
0x18000ef60  test    rax, rax
0x18000ef63  jz      short loc_18000EFDB
0x18000ef65  mov     rcx, qword ptr [rbp+170h+FileTime1.dwLowDateTime]
0x18000ef6c  xor     edx, edx; Val
0x18000ef6e  mov     [rax+24h], rcx
0x18000ef72  mov     r8d, 210h; Size
0x18000ef78  lea     rcx, [rsp+270h+pitem]; void *
0x18000ef7d  call    memset_0
0x18000ef82  mov     r8, r14; unsigned __int16 *
0x18000ef85  lea     rcx, [rsp+270h+pitem]; unsigned __int16 *
0x18000ef8a  mov     edx, 104h; unsigned __int64
0x18000ef8f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ef94  mov     ebx, eax
0x18000ef96  test    eax, eax
0x18000ef98  js      loc_18000EEA5
0x18000ef9e  mov     rax, [rdi]
0x18000efa1  lea     r8, [rsp+270h+pitem]; pitem
0x18000efa6  mov     rcx, cs:?g_hdsaEnumCache@@3PEAU_DSA@@EA; hdsa
0x18000efad  xor     edx, edx; i
0x18000efaf  mov     [rbp+170h+var_38], rax
0x18000efb6  call    DSA_InsertItem
0x18000efbb  cmp     eax, 0FFFFFFFFh
0x18000efbe  jz      short loc_18000EFDB
0x18000efc0  mov     rcx, [rdi]
0x18000efc3  mov     rax, [rcx]
0x18000efc6  mov     rax, [rax+8]
0x18000efca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efcf  jmp     loc_18000EEA5
0x18000efd4  mov     qword ptr [rdi], 0
0x18000efdb  mov     ebx, 8007000Eh
0x18000efe0  jmp     loc_18000EEA5
0x18000efe5  mov     rcx, [rdi]; this
0x18000efe8  call    ?Lock@CEnumArchive@@QEAAXXZ; CEnumArchive::Lock(void)
0x18000efed  jmp     loc_18000EE5A
```
