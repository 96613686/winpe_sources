# CViewStatePropertyBag::IsSameBag(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ulong)

- ea: `0x1800088e0`
- end: `0x180008f6c`
- name: `?IsSameBag@CViewStatePropertyBag@@QEAAHPEBU_ITEMIDLIST_ABSOLUTE@@PEBGK@Z`
- size: `1676`
- prototype: `__int64 __fastcall(CViewStatePropertyBag *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, PCWSTR psz1, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180008730`

## callees

- `0x1800088e0`
- `0x18000ad64`
- `0x180012550`
- `0x1800177c8`
- `0x180028f88`
- `0x180029300`
- `0x1800293e4`
- `0x180029758`
- `0x1800298b0`
- `0x180029fb0`
- `0x18002a108`
- `0x18002a134`
- `0x18002a3f8`
- `0x18002bba4`
- `0x18002c29c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ba0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ba0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bb7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008cc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008cc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e89`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008b6f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d22`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008dbd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008b6f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d22`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008dbd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18000893c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180008f33`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18000893c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x180008f33`
- `SHELL32!SHCreateItemFromIDList` at `0x18000899a`
- `SHELL32!SHCreateItemFromIDList` at `0x1800089d0`
- `SHELL32!SHCreateItemFromIDList` at `0x18000899a`
- `SHELL32!SHCreateItemFromIDList` at `0x1800089d0`
- `SHELL32!__imp_ILClone` at `0x180008c88`
- `SHELL32!__imp_ILClone` at `0x180008c88`
- `SHELL32!__imp_ILIsEqual` at `0x180008d5b`
- `SHELL32!__imp_ILIsEqual` at `0x180008d5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ddf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008eca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ddf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008eca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008a6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008a6b`

## string_xrefs

- `0x180008b99`: `kernelbase.dll`
- `0x180008a97`: `BagsComparisonTest`

## pseudocode

```c
int __fastcall CViewStatePropertyBag::IsSameBag(
        CViewStatePropertyBag *this,
        const struct _ITEMIDLIST_ABSOLUTE *a2,
        PCWSTR psz1,
        int a4)
{
  char IsEnabled; // al
  int v9; // ecx
  int v10; // r14d
  _QWORD *v12; // rax
  wil::details::in1diag3 *v13; // rcx
  _QWORD *v14; // rdi
  __int64 v15; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  LPITEMIDLIST v18; // rbx
  ITEMIDLIST *v19; // r8
  const ITEMIDLIST *v20; // rcx
  int v21; // eax
  ITEMIDLIST *v22; // r8
  const ITEMIDLIST *v23; // rcx
  tip2::test_state *v24; // r12
  BOOL v25; // r15d
  ITEMIDLIST *v26; // rcx
  int v27; // eax
  int v28; // eax
  ITEMIDLIST *v29; // rcx
  int v30[4]; // [rsp+30h] [rbp-49h] BYREF
  LPCITEMIDLIST *p_pidl1; // [rsp+40h] [rbp-39h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v32; // [rsp+48h] [rbp-31h] BYREF
  __int16 v33; // [rsp+50h] [rbp-29h]
  int v34; // [rsp+52h] [rbp-27h]
  __int16 v35; // [rsp+56h] [rbp-23h]
  __int128 v36; // [rsp+58h] [rbp-21h]
  __int64 v37; // [rsp+68h] [rbp-11h]
  int v38; // [rsp+70h] [rbp-9h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+78h] [rbp-1h] BYREF
  void *v40; // [rsp+80h] [rbp+7h] BYREF
  void *ppv; // [rsp+88h] [rbp+Fh] BYREF

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::GetImpl'::`2'::impl);
  v9 = *((_DWORD *)this + 14);
  if ( !IsEnabled )
    return a4 == v9
        && (!psz1 || !StrCmpW(psz1, *((PCWSTR *)this + 6)))
        && (!a2 || CViewStatePropertyBag::_IsSamePidl(this, a2));
  if ( a4 != v9 || psz1 && StrCmpW(psz1, *((PCWSTR *)this + 6)) )
    return 0;
  if ( !a2 )
    return 1;
  if ( (*((_BYTE *)this + 56) & 4) == 0 )
    return CViewStatePropertyBag::_IsSamePidl(this, a2);
  if ( CViewStatePropertyBag::_IsSamePidl(this, a2) )
    return 1;
  v10 = 0;
  v40 = 0;
  ppv = 0;
  if ( SHCreateItemFromIDList((LPCITEMIDLIST)a2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
  {
    v40 = 0;
    if ( SHCreateItemFromIDList(*((LPCITEMIDLIST *)this + 4), &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v40) >= 0 )
    {
      v38 = 0;
      if ( (*(int (__fastcall **)(void *, void *, __int64, int *))(*(_QWORD *)ppv + 56LL))(ppv, v40, 0x10000000, &v38) >= 0 )
      {
        LOBYTE(v10) = v38 == 0;
        if ( v40 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v40 + 16LL))(v40);
        if ( ppv )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        return v10;
      }
    }
  }
  v12 = CoTaskMemAlloc(0x128u);
  v14 = v12;
  if ( !v12 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  LODWORD(p_pidl1) = 59205490;
  v34 = 0;
  *v12 = &tip2::details::test_data_interface::`vftable';
  v35 = 0;
  v32 = (struct _ITEMIDLIST_ABSOLUTE *)"BagsComparisonTest";
  HIDWORD(p_pidl1) = 49408;
  v33 = 1;
  v36 = 0;
  v37 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v12 + 1, v12, &p_pidl1);
  *((_BYTE *)v14 + 272) = 0;
  v14[33] = v14 + 2;
  *(_QWORD *)((char *)v14 + 276) = 0;
  *v14 = &tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::`vftable';
  *((_DWORD *)v14 + 72) = 1;
  tip2::details::shared_data<0,0,0>::start(v14 + 1, v30);
  _InterlockedIncrement((volatile signed __int32 *)v14 + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)v14 + 5);
  ++*((_DWORD *)v14 + 60);
  *((_BYTE *)v14 + 272) = 1;
  tip2::details::shared_data<0,0,0>::end_update(v14 + 1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 72, 0xFFFFFFFF) == 1 )
  {
    *v14 = &tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::`vftable';
    if ( v14[31] && (*((_BYTE *)v14 + 28) & 1) == 0 )
      tip2::details::shared_data<0,0,0>::complete_helper(v14 + 1, 4);
    DeleteCriticalSection((LPCRITICAL_SECTION)v14 + 5);
    v15 = v14[31];
    if ( v15 )
    {
      ProcAddress = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
      if ( `TestClose'::`2'::s_pfnTestClose )
        goto LABEL_26;
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestClose");
      `TestClose'::`2'::s_pfnTestClose = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_26:
        ((void (__fastcall *)(__int64))ProcAddress)(v15);
    }
    tip2::test_state::~test_state((tip2::test_state *)(v14 + 2));
    CoTaskMemFree(v14);
  }
  pidl1 = 0;
  p_pidl1 = &pidl1;
  v32 = 0;
  v18 = 0;
  LOBYTE(v33) = 1;
  v30[0] = NormalizePidlForViewState((LPCITEMIDLIST)a2, &v32);
  if ( (_BYTE)v33 )
  {
    v19 = (ITEMIDLIST *)*p_pidl1;
    *p_pidl1 = (LPCITEMIDLIST)v32;
    if ( v19 )
      CoTaskMemFree(v19);
  }
  if ( *((_QWORD *)this + 5) )
  {
    v38 = 0;
LABEL_37:
    v23 = (const ITEMIDLIST *)*((_QWORD *)this + 5);
    if ( v23 )
      v18 = ILClone(v23);
    goto LABEL_39;
  }
  v20 = (const ITEMIDLIST *)*((_QWORD *)this + 4);
  p_pidl1 = (LPCITEMIDLIST *)((char *)this + 40);
  v32 = 0;
  LOBYTE(v33) = 1;
  v21 = NormalizePidlForViewState(v20, &v32);
  v38 = v21;
  if ( (_BYTE)v33 )
  {
    v22 = (ITEMIDLIST *)*p_pidl1;
    *p_pidl1 = (LPCITEMIDLIST)v32;
    if ( v22 )
    {
      CoTaskMemFree(v22);
      v21 = v38;
    }
  }
  if ( v21 >= 0 )
    goto LABEL_37;
LABEL_39:
  if ( v30[0] < 0 || v38 < 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v14 + 72);
    EnterCriticalSection((LPCRITICAL_SECTION)v14 + 5);
    v27 = v30[0];
    ++*((_DWORD *)v14 + 60);
    *((_DWORD *)v14 + 69) = v27;
    tip2::details::shared_data<0,0,0>::end_update(v14 + 1);
    tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::Release(v14);
    *(_QWORD *)v30 = v14;
    _InterlockedIncrement((volatile signed __int32 *)v14 + 72);
    EnterCriticalSection((LPCRITICAL_SECTION)v14 + 5);
    v28 = v38;
    ++*((_DWORD *)v14 + 60);
    *((_DWORD *)v14 + 70) = v28;
    tip2::test_data_control<tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>>::~test_data_control<tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>>(v30);
LABEL_66:
    _InterlockedIncrement((volatile signed __int32 *)v14 + 72);
    EnterCriticalSection((LPCRITICAL_SECTION)v14 + 5);
    ++*((_DWORD *)v14 + 60);
    tip2::details::shared_data<0,0,0>::complete(v14 + 1);
    tip2::details::shared_data<0,0,0>::end_update(v14 + 1);
    tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::Release(v14);
    if ( v18 )
      CoTaskMemFree(v18);
    v29 = (ITEMIDLIST *)pidl1;
    pidl1 = 0;
    if ( v29 )
      CoTaskMemFree(v29);
    tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::Release(v14);
    if ( v40 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v40 + 16LL))(v40);
    if ( ppv )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    return CViewStatePropertyBag::_IsSamePidl(this, a2);
  }
  if ( !pidl1 || !v18 )
    goto LABEL_66;
  _InterlockedIncrement((volatile signed __int32 *)v14 + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)v14 + 5);
  ++*((_DWORD *)v14 + 60);
  tip2::details::shared_data<0,0,0>::complete(v14 + 1);
  tip2::details::shared_data<0,0,0>::end_update(v14 + 1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 72, 0xFFFFFFFF) == 1 )
  {
    *v14 = &tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::`vftable';
    if ( v14[31] && (*((_BYTE *)v14 + 28) & 1) == 0 )
      tip2::details::shared_data<0,0,0>::complete_helper(v14 + 1, 4);
    DeleteCriticalSection((LPCRITICAL_SECTION)v14 + 5);
    if ( v14[31] )
      TestClose();
    v24 = (tip2::test_state *)(v14 + 2);
    tip2::test_state::~test_state((tip2::test_state *)(v14 + 2));
    CoTaskMemFree(v14);
  }
  else
  {
    v24 = (tip2::test_state *)(v14 + 2);
  }
  v25 = ILIsEqual(pidl1, v18);
  CoTaskMemFree(v18);
  v26 = (ITEMIDLIST *)pidl1;
  pidl1 = 0;
  if ( v26 )
    CoTaskMemFree(v26);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 72, 0xFFFFFFFF) == 1 )
  {
    *v14 = &tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::`vftable';
    if ( v14[31] && (*((_BYTE *)v14 + 28) & 1) == 0 )
      tip2::details::shared_data<0,0,0>::complete_helper(v14 + 1, 4);
    DeleteCriticalSection((LPCRITICAL_SECTION)v14 + 5);
    if ( v14[31] )
      TestClose();
    tip2::test_state::~test_state(v24);
    CoTaskMemFree(v14);
  }
  if ( v40 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v40 + 16LL))(v40);
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return v25;
}

```

## disassembly

```asm
0x1800088e0  push    rbp
0x1800088e2  push    rbx
0x1800088e3  push    rdi
0x1800088e4  push    r12
0x1800088e6  push    r14
0x1800088e8  push    r15
0x1800088ea  lea     rbp, [rsp-2Fh]
0x1800088ef  sub     rsp, 0A8h
0x1800088f6  mov     rax, cs:__security_cookie
0x1800088fd  xor     rax, rsp
0x180008900  mov     [rbp+57h+var_40], rax
0x180008904  mov     edi, r9d
0x180008907  mov     rbx, r8
0x18000890a  mov     r12, rdx
0x18000890d  mov     r15, rcx
0x180008910  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784> `wil::Feature<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::GetImpl(void)'::`2'::impl
0x180008917  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::__private_IsEnabled(void)
0x18000891c  mov     ecx, [r15+38h]
0x180008920  test    al, al
0x180008922  jz      loc_180008F23
0x180008928  cmp     edi, ecx
0x18000892a  jnz     loc_180008F1C
0x180008930  test    rbx, rbx
0x180008933  jz      short loc_18000894A
0x180008935  mov     rdx, [r15+30h]; psz2
0x180008939  mov     rcx, rbx; psz1
0x18000893c  call    cs:__imp_StrCmpW
0x180008942  test    eax, eax
0x180008944  jnz     loc_180008F1C
0x18000894a  mov     [rsp+0D0h+arg_18], rsi
0x180008952  mov     [rsp+0D0h+var_30], r13
0x18000895a  test    r12, r12
0x18000895d  jz      loc_180008F12
0x180008963  test    byte ptr [r15+38h], 4
0x180008968  jz      loc_180008F02
0x18000896e  mov     rdx, r12; struct _ITEMIDLIST_ABSOLUTE *
0x180008971  mov     rcx, r15; this
0x180008974  call    ?_IsSamePidl@CViewStatePropertyBag@@AEAAHPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CViewStatePropertyBag::_IsSamePidl(_ITEMIDLIST_ABSOLUTE const *)
0x180008979  test    eax, eax
0x18000897b  jnz     loc_180008F12
0x180008981  xor     r14d, r14d
0x180008984  lea     r8, [rbp+57h+ppv]; ppv
0x180008988  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000898f  mov     [rbp+57h+var_50], r14
0x180008993  mov     rcx, r12; pidl
0x180008996  mov     [rbp+57h+ppv], r14
0x18000899a  call    cs:__imp_SHCreateItemFromIDList
0x1800089a0  test    eax, eax
0x1800089a2  js      loc_180008A66
0x1800089a8  mov     rcx, [rbp+57h+var_50]
0x1800089ac  mov     [rbp+57h+var_50], r14
0x1800089b0  test    rcx, rcx
0x1800089b3  jz      short loc_1800089C1
0x1800089b5  mov     rax, [rcx]
0x1800089b8  mov     rax, [rax+10h]
0x1800089bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089c1  mov     rcx, [r15+20h]; pidl
0x1800089c5  lea     r8, [rbp+57h+var_50]; ppv
0x1800089c9  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800089d0  call    cs:__imp_SHCreateItemFromIDList
0x1800089d6  test    eax, eax
0x1800089d8  js      loc_180008A66
0x1800089de  mov     rcx, [rbp+57h+ppv]
0x1800089e2  lea     r9, [rbp+57h+var_60]
0x1800089e6  mov     rdx, [rbp+57h+var_50]
0x1800089ea  mov     r8d, 10000000h
0x1800089f0  mov     [rbp+57h+var_60], r14d
0x1800089f4  mov     rax, [rcx]
0x1800089f7  mov     rax, [rax+38h]
0x1800089fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a00  test    eax, eax
0x180008a02  js      short loc_180008A66
0x180008a04  cmp     [rbp+57h+var_60], r14d
0x180008a08  mov     rcx, [rbp+57h+var_50]
0x180008a0c  setz    r14b
0x180008a10  test    rcx, rcx
0x180008a13  jz      short loc_180008A21
0x180008a15  mov     rax, [rcx]
0x180008a18  mov     rax, [rax+10h]
0x180008a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a21  mov     rcx, [rbp+57h+ppv]
0x180008a25  test    rcx, rcx
0x180008a28  jz      short loc_180008A36
0x180008a2a  mov     rdx, [rcx]
0x180008a2d  mov     rax, [rdx+10h]
0x180008a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a36  mov     eax, r14d
0x180008a39  mov     rsi, [rsp+0D0h+arg_18]
0x180008a41  mov     r13, [rsp+0D0h+var_30]
0x180008a49  mov     rcx, [rbp+57h+var_40]
0x180008a4d  xor     rcx, rsp; StackCookie
0x180008a50  call    __security_check_cookie
0x180008a55  add     rsp, 0A8h
0x180008a5c  pop     r15
0x180008a5e  pop     r14
0x180008a60  pop     r12
0x180008a62  pop     rdi
0x180008a63  pop     rbx
0x180008a64  pop     rbp
0x180008a65  retn
0x180008a66  mov     ecx, 128h; cb
0x180008a6b  call    cs:__imp_CoTaskMemAlloc
0x180008a71  mov     rdi, rax
0x180008a74  test    rax, rax
0x180008a77  jz      loc_180008F66
0x180008a7d  xor     ecx, ecx
0x180008a7f  mov     dword ptr [rbp+57h+var_90], 3876772h
0x180008a86  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180008a8d  mov     [rbp+57h+var_7E], ecx
0x180008a90  mov     [rdi], rax
0x180008a93  lea     r8, [rbp+57h+var_90]
0x180008a97  lea     rax, aBagscomparison; "BagsComparisonTest"
0x180008a9e  mov     [rbp+57h+var_7A], cx
0x180008aa2  xorps   xmm0, xmm0
0x180008aa5  mov     [rbp+57h+var_88], rax
0x180008aa9  mov     rdx, rdi
0x180008aac  mov     dword ptr [rbp+57h+var_90+4], 0C100h
0x180008ab3  lea     rcx, [rdi+8]
0x180008ab7  mov     [rbp+57h+var_80], 1
0x180008abd  movdqu  [rbp+57h+var_78], xmm0
0x180008ac2  mov     [rbp+57h+var_68], r14
0x180008ac6  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180008acb  lea     rax, [rdi+10h]
0x180008acf  mov     [rdi+110h], r14b
0x180008ad6  lea     rbx, ??_7?$merged_data@U_tip_BagsComparisonTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::`vftable'
0x180008add  mov     [rdi+108h], rax
0x180008ae4  lea     rdx, [rbp+57h+var_A0]
0x180008ae8  mov     [rdi+114h], r14
0x180008aef  lea     rcx, [rdi+8]
0x180008af3  mov     [rdi], rbx
0x180008af6  mov     dword ptr [rdi+120h], 1
0x180008b00  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180008b05  lock inc dword ptr [rdi+120h]
0x180008b0c  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180008b13  call    cs:__imp_EnterCriticalSection
0x180008b19  inc     dword ptr [rdi+0F0h]
0x180008b1f  lea     rcx, [rdi+8]
0x180008b23  mov     byte ptr [rdi+110h], 1
0x180008b2a  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180008b2f  mov     r13d, 0FFFFFFFFh
0x180008b35  mov     eax, r13d
0x180008b38  lock xadd [rdi+120h], eax
0x180008b40  cmp     eax, 1
0x180008b43  jnz     loc_180008BE3
0x180008b49  mov     [rdi], rbx
0x180008b4c  cmp     [rdi+0F8h], r14
0x180008b53  jz      short loc_180008B68
0x180008b55  test    [rdi+1Ch], al
0x180008b58  jnz     short loc_180008B68
0x180008b5a  mov     edx, 4
0x180008b5f  lea     rcx, [rdi+8]
0x180008b63  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180008b68  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180008b6f  call    cs:__imp_DeleteCriticalSection
0x180008b75  mov     rbx, [rdi+0F8h]
0x180008b7c  test    rbx, rbx
0x180008b7f  jz      short loc_180008BD1
0x180008b81  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180008b88  test    rax, rax
0x180008b8b  jnz     short loc_180008BC9
0x180008b8d  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180008b94  test    rax, rax
0x180008b97  jnz     short loc_180008BAD
0x180008b99  lea     rcx, ModuleName; "kernelbase.dll"
0x180008ba0  call    cs:__imp_GetModuleHandleW
0x180008ba6  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180008bad  lea     rdx, ProcName; "TestClose"
0x180008bb4  mov     rcx, rax; hModule
0x180008bb7  call    cs:__imp_GetProcAddress
0x180008bbd  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180008bc4  test    rax, rax
0x180008bc7  jz      short loc_180008BD1
0x180008bc9  mov     rcx, rbx
0x180008bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd1  lea     rcx, [rdi+10h]; this
0x180008bd5  call    ??1test_state@tip2@@QEAA@XZ; tip2::test_state::~test_state(void)
0x180008bda  mov     rcx, rdi; pv
0x180008bdd  call    cs:__imp_CoTaskMemFree
0x180008be3  lea     rax, [rbp+57h+pidl1]
0x180008be7  mov     [rbp+57h+pidl1], r14
0x180008beb  lea     rdx, [rbp+57h+var_88]; struct _ITEMIDLIST_ABSOLUTE **
0x180008bef  mov     [rbp+57h+var_90], rax
0x180008bf3  mov     rcx, r12; pidl
0x180008bf6  mov     [rbp+57h+var_88], r14
0x180008bfa  mov     rbx, r14
0x180008bfd  mov     byte ptr [rbp+57h+var_80], 1
0x180008c01  call    ?NormalizePidlForViewState@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; NormalizePidlForViewState(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x180008c06  mov     [rbp+57h+var_A0], eax
0x180008c09  cmp     byte ptr [rbp+57h+var_80], r14b
0x180008c0d  jz      short loc_180008C2B
0x180008c0f  mov     rdx, [rbp+57h+var_90]
0x180008c13  mov     rcx, [rbp+57h+var_88]
0x180008c17  mov     r8, [rdx]
0x180008c1a  mov     [rdx], rcx
0x180008c1d  test    r8, r8
0x180008c20  jz      short loc_180008C2B
0x180008c22  mov     rcx, r8; pv
0x180008c25  call    cs:__imp_CoTaskMemFree
0x180008c2b  cmp     [r15+28h], rbx
0x180008c2f  lea     rax, [r15+28h]
0x180008c33  jz      short loc_180008C3B
0x180008c35  mov     [rbp+57h+var_60], r14d
0x180008c39  jmp     short loc_180008C7F
0x180008c3b  mov     rcx, [r15+20h]; pidl
0x180008c3f  lea     rdx, [rbp+57h+var_88]; struct _ITEMIDLIST_ABSOLUTE **
0x180008c43  mov     [rbp+57h+var_90], rax
0x180008c47  mov     [rbp+57h+var_88], r14
0x180008c4b  mov     byte ptr [rbp+57h+var_80], 1
0x180008c4f  call    ?NormalizePidlForViewState@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; NormalizePidlForViewState(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x180008c54  mov     [rbp+57h+var_60], eax
0x180008c57  cmp     byte ptr [rbp+57h+var_80], bl
0x180008c5a  jz      short loc_180008C7B
0x180008c5c  mov     rdx, [rbp+57h+var_90]
0x180008c60  mov     rcx, [rbp+57h+var_88]
0x180008c64  mov     r8, [rdx]
0x180008c67  mov     [rdx], rcx
0x180008c6a  test    r8, r8
0x180008c6d  jz      short loc_180008C7B
0x180008c6f  mov     rcx, r8; pv
0x180008c72  call    cs:__imp_CoTaskMemFree
0x180008c78  mov     eax, [rbp+57h+var_60]
0x180008c7b  test    eax, eax
0x180008c7d  js      short loc_180008C91
0x180008c7f  mov     rcx, [r15+28h]; pidl
0x180008c83  test    rcx, rcx
0x180008c86  jz      short loc_180008C91
0x180008c88  call    cs:__imp_ILClone
0x180008c8e  mov     rbx, rax
0x180008c91  cmp     [rbp+57h+var_A0], r14d
0x180008c95  jl      loc_180008E17
0x180008c9b  cmp     [rbp+57h+var_60], r14d
0x180008c9f  jl      loc_180008E17
0x180008ca5  cmp     [rbp+57h+pidl1], r14
0x180008ca9  jz      loc_180008E7B
0x180008caf  test    rbx, rbx
0x180008cb2  jz      loc_180008E7B
0x180008cb8  lock inc dword ptr [rdi+120h]
0x180008cbf  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180008cc6  call    cs:__imp_EnterCriticalSection
0x180008ccc  inc     dword ptr [rdi+0F0h]
0x180008cd2  lea     rcx, [rdi+8]
0x180008cd6  call    ?complete@?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAAXXZ; tip2::details::shared_data<0,0,0>::complete(void)
0x180008cdb  lea     rcx, [rdi+8]
0x180008cdf  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180008ce4  mov     eax, r13d
0x180008ce7  lock xadd [rdi+120h], eax
0x180008cef  cmp     eax, 1
0x180008cf2  jnz     short loc_180008D50
0x180008cf4  lea     rax, ??_7?$merged_data@U_tip_BagsComparisonTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::`vftable'
0x180008cfb  mov     [rdi], rax
0x180008cfe  cmp     [rdi+0F8h], r14
0x180008d05  jz      short loc_180008D1B
0x180008d07  test    byte ptr [rdi+1Ch], 1
0x180008d0b  jnz     short loc_180008D1B
0x180008d0d  mov     edx, 4
0x180008d12  lea     rcx, [rdi+8]
0x180008d16  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180008d1b  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180008d22  call    cs:__imp_DeleteCriticalSection
0x180008d28  mov     rcx, [rdi+0F8h]
0x180008d2f  test    rcx, rcx
0x180008d32  jz      short loc_180008D39
0x180008d34  call    TestClose
0x180008d39  lea     r12, [rdi+10h]
0x180008d3d  mov     rcx, r12; this
0x180008d40  call    ??1test_state@tip2@@QEAA@XZ; tip2::test_state::~test_state(void)
0x180008d45  mov     rcx, rdi; pv
0x180008d48  call    cs:__imp_CoTaskMemFree
0x180008d4e  jmp     short loc_180008D54
0x180008d50  lea     r12, [rdi+10h]
0x180008d54  mov     rcx, [rbp+57h+pidl1]; pidl1
0x180008d58  mov     rdx, rbx; pidl2
0x180008d5b  call    cs:__imp_ILIsEqual
0x180008d61  mov     rcx, rbx; pv
0x180008d64  mov     r15d, eax
0x180008d67  call    cs:__imp_CoTaskMemFree
0x180008d6d  mov     rcx, [rbp+57h+pidl1]; pv
0x180008d71  mov     [rbp+57h+pidl1], r14
0x180008d75  test    rcx, rcx
0x180008d78  jz      short loc_180008D80
0x180008d7a  call    cs:__imp_CoTaskMemFree
0x180008d80  lock xadd [rdi+120h], r13d
0x180008d89  cmp     r13d, 1
0x180008d8d  jnz     short loc_180008DE5
0x180008d8f  lea     rax, ??_7?$merged_data@U_tip_BagsComparisonTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::`vftable'
0x180008d96  mov     [rdi], rax
0x180008d99  cmp     [rdi+0F8h], r14
0x180008da0  jz      short loc_180008DB6
0x180008da2  test    [rdi+1Ch], r13b
0x180008da6  jnz     short loc_180008DB6
0x180008da8  mov     edx, 4
0x180008dad  lea     rcx, [rdi+8]
0x180008db1  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180008db6  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180008dbd  call    cs:__imp_DeleteCriticalSection
0x180008dc3  mov     rcx, [rdi+0F8h]
0x180008dca  test    rcx, rcx
0x180008dcd  jz      short loc_180008DD4
0x180008dcf  call    TestClose
0x180008dd4  mov     rcx, r12; this
  ... truncated ...
```
