# PopupClientStatics::GetForWindowId(uint,Windows::Internal::Shell::Popups::IPopupClient * *)

- ea: `0x180004110`
- end: `0x18000470e`
- name: `?GetForWindowId@PopupClientStatics@@UEAAJIPEAPEAUIPopupClient@Popups@Shell@Internal@Windows@@@Z`
- size: `1534`
- prototype: `__int64 __fastcall(PopupClientStatics *__hidden this, unsigned int, struct Windows::Internal::Shell::Popups::IPopupClient **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003074`
- `0x180003d24`
- `0x1800040e0`
- `0x180004110`
- `0x180004714`
- `0x180004890`
- `0x180004930`
- `0x1800052f0`
- `0x180018294`
- `0x18001cc38`
- `0x180026614`
- `0x18002b1e0`
- `0x180037c44`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800043ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004496`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800043ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004496`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall PopupClientStatics::GetForWindowId(
        PopupClientStatics *this,
        int a2,
        struct Windows::Internal::Shell::Popups::IPopupClient **a3)
{
  int v5; // ebx
  _DWORD *v6; // rax
  __int64 v7; // r8
  unsigned int v8; // r9d
  unsigned int v9; // r15d
  unsigned int v10; // r12d
  int v11; // r14d
  unsigned int v12; // edx
  __int64 v13; // rcx
  int v14; // ebx
  _DWORD *v15; // rax
  __int64 v16; // r8
  unsigned int v17; // r9d
  unsigned int v18; // r14d
  unsigned int v19; // r15d
  int v20; // edi
  unsigned int v21; // edx
  LPVOID v22; // rdi
  int (__fastcall *v23)(LPVOID, __int64 *, GUID *, __int64 *); // rbx
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rcx
  LPVOID v27; // rcx
  __int64 v28; // rcx
  HRESULT v29; // eax
  __int64 v30; // rdx
  struct Windows::Internal::Shell::Popups::IPopupClientBroker *v31; // rcx
  LPVOID v33; // rcx
  struct Windows::Internal::Shell::Popups::IPopupClientBroker *v34; // rdi
  PopupClientImpl *v35; // rax
  int v36; // edi
  volatile signed __int64 *v37; // rbx
  signed __int64 v38; // rcx
  signed __int32 v39; // edx
  bool v40; // zf
  signed __int64 v41; // rax
  signed __int32 i; // r8d
  __int64 v43; // rdx
  struct Windows::Internal::Shell::Popups::IPopupClient *v44; // rax
  struct Windows::Internal::Shell::Popups::IPopupClientBroker *v45; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-69h]
  int ppva; // [rsp+20h] [rbp-69h]
  int ppvb; // [rsp+20h] [rbp-69h]
  int v49; // [rsp+30h] [rbp-59h]
  LPVOID v50; // [rsp+50h] [rbp-39h] BYREF
  struct Windows::Internal::Shell::Popups::IPopupClientBroker *v51; // [rsp+58h] [rbp-31h] BYREF
  __int64 v52; // [rsp+60h] [rbp-29h] BYREF
  LPVOID v53; // [rsp+68h] [rbp-21h] BYREF
  struct Windows::Internal::Shell::Popups::IPopupClient *v54; // [rsp+70h] [rbp-19h] BYREF
  char v55[4]; // [rsp+78h] [rbp-11h] BYREF
  _DWORD v56[6]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v57[72]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v5 = *(_DWORD *)Feature_CUIPopupHelper__descriptor;
  if ( (*(_DWORD *)Feature_CUIPopupHelper__descriptor & 4) == 0 )
    v5 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CUIPopupHelper>::GetCachedFeatureEnabledState(
                      this,
                      &v54);
  LODWORD(v50) = 0;
  WORD2(v50) = 3;
  *(_DWORD *)v55 = 3;
  v6 = (_DWORD *)wil_details_FeatureReporting_RecordUsageInCache(v56, &qword_1800B3618, 2);
  v9 = v6[1];
  v10 = v6[2];
  v11 = v6[4];
  if ( *v6 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      &wil::details::g_enabledStateManager,
      0x84350Cu,
      (struct wil_details_FeatureReportingCache *)&qword_1800B3618);
  if ( v9 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x84350C, v10, v9, v8, (const char *)ppv);
  if ( !v11 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( (v5 & 0x400) != 0 )
  {
    v12 = 2;
    if ( (v5 & 0x800) != 0 )
      v12 = -2147483646;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x84350C, v12, 0, v8, (const char *)ppv);
  }
  if ( !v11 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v7) = 3;
      g_wil_details_realtimeFeatureUsageHook(8664332, 2, v7);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(8664332, &v50, 0, 1, v55, 0, 0, 1);
  }
  *a3 = 0;
  v56[0] = 0;
  v56[1] = a2;
  v56[2] = 0;
  v51 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  v51 = 0;
  v14 = *(_DWORD *)Feature_CUIPopupHelper__descriptor;
  if ( (*(_DWORD *)Feature_CUIPopupHelper__descriptor & 4) == 0 )
    v14 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CUIPopupHelper>::GetCachedFeatureEnabledState(
                       v13,
                       v55);
  LODWORD(v50) = 0;
  WORD2(v50) = 3;
  *(_DWORD *)v55 = 3;
  v15 = (_DWORD *)wil_details_FeatureReporting_RecordUsageInCache(v57, &qword_1800B3618, 2);
  v18 = v15[1];
  v19 = v15[2];
  v20 = v15[4];
  if ( *v15 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      &wil::details::g_enabledStateManager,
      0x84350Cu,
      (struct wil_details_FeatureReportingCache *)&qword_1800B3618);
  if ( v18 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x84350C, v19, v18, v17, (const char *)ppv);
  if ( !v20 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( (v14 & 0x400) != 0 )
  {
    v21 = 2;
    if ( (v14 & 0x800) != 0 )
      v21 = -2147483646;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x84350C, v21, 0, v17, (const char *)ppv);
  }
  if ( !v20 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v16) = 3;
      g_wil_details_realtimeFeatureUsageHook(8664332, 2, v16);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      LOBYTE(v49) = 0;
      g_wil_details_pfnFeatureLoggingHook(8664332, &v50, 0, 1, v55, 0, v49, 1);
    }
  }
  v53 = 0;
  v52 = 0;
  if ( CoCreateInstance(&CLSID_ShellServiceHostBrokerProvider, 0, 4u, &GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf, &v53) >= 0 )
  {
    v22 = v53;
    v23 = *(int (__fastcall **)(LPVOID, __int64 *, GUID *, __int64 *))(*(_QWORD *)v53 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    if ( v23(v22, qword_1800931F0, &GUID_5627cb1e_76a9_4621_a276_b68fb43d4d25, &v52) >= 0 )
    {
      v24 = (*(__int64 (__fastcall **)(__int64, struct Windows::Internal::Shell::Popups::IPopupClientBroker **))(*(_QWORD *)v52 + 48LL))(
              v52,
              &v51);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\shell\\onecore\\popupclient\\lib\\popupclientstatics.cpp",
          (const char *)(unsigned int)v24,
          ppva);
        v26 = v52;
        if ( v52 )
        {
          v52 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        v27 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
        }
        goto LABEL_49;
      }
    }
  }
  v28 = v52;
  if ( !v52 )
  {
    v50 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    v29 = CoCreateInstance(
            &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
            0,
            4u,
            &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
            &v50);
    v25 = v29;
    if ( v29 < 0 )
    {
      v30 = 112;
LABEL_48:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\shell\\onecore\\popupclient\\lib\\popupclientstatics.cpp",
        (const char *)(unsigned int)v29,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecoreuap\\shell\\onecore\\popupclient\\lib\\popupclientstatics.cpp",
        (const char *)v25,
        ppvb);
      v31 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::Shell::Popups::IPopupClientBroker *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      return v25;
    }
    v29 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, struct Windows::Internal::Shell::Popups::IPopupClientBroker **))(*(_QWORD *)v50 + 24LL))(
            v50,
            qword_1800931F0,
            &GUID_4637e79c_de03_4aef_8a87_e796659e5e8d,
            &v51);
    v25 = v29;
    if ( v29 < 0 )
    {
      v30 = 113;
      goto LABEL_48;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    v28 = v52;
  }
  if ( v28 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v33 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v54 = 0;
  v34 = v51;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  v54 = 0;
  v35 = (PopupClientImpl *)operator new(0x98u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v35 )
  {
    v36 = -2147024882;
LABEL_73:
    v43 = 64;
LABEL_74:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v43,
      (unsigned int)"onecoreuap\\shell\\onecore\\popupclient\\lib\\popupclientstatics.cpp",
      (const char *)(unsigned int)v36,
      ppva);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    return (unsigned int)v36;
  }
  v37 = (volatile signed __int64 *)PopupClientImpl::PopupClientImpl(v35);
  v53 = (LPVOID)v37;
  v52 = 0;
  v36 = PopupClientImpl::RuntimeClassInitialize(
          (PopupClientImpl *)v37,
          v34,
          (const struct Windows::Internal::Shell::Popups::ClientIdentifier *)v56);
  if ( v36 < 0 )
  {
    if ( v37 )
    {
      v38 = *((_QWORD *)v37 + 7);
      while ( v38 >= 0 )
      {
        if ( (_DWORD)v38 == 0x7FFFFFFF )
          goto LABEL_73;
        v39 = v38 - 1;
        v41 = _InterlockedCompareExchange64(v37 + 7, v38 - 1, v38);
        v40 = v38 == v41;
        v38 = v41;
        if ( v40 )
          goto LABEL_70;
      }
      for ( i = *(_DWORD *)(2 * v38 + 0x10); i != 0x7FFFFFFF; i = *(_DWORD *)(2 * v38 + 0x10) )
      {
        if ( i == _InterlockedCompareExchange((volatile signed __int32 *)(2 * v38 + 16), i - 1, i) )
          break;
      }
      v39 = i - 1;
LABEL_70:
      if ( !v39 )
      {
        (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*v37 + 96))(v37, 1);
        if ( Microsoft::WRL::Details::ModuleBase::module_ )
          (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                               + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
    }
    goto LABEL_73;
  }
  v54 = (struct Windows::Internal::Shell::Popups::IPopupClient *)v37;
  (*(void (__fastcall **)(volatile signed __int64 *))(*v37 + 8))(v37);
  Microsoft::WRL::ComPtr<PopupClientImpl>::InternalRelease(&v53);
  v44 = v54;
  if ( !v54 )
  {
    v36 = -2147024882;
    v43 = 65;
    goto LABEL_74;
  }
  v54 = 0;
  *a3 = v44;
  v45 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::Shell::Popups::IPopupClientBroker *))(*(_QWORD *)v45 + 16LL))(v45);
  }
  return 0;
}

```

## disassembly

```asm
0x180004110  mov     [rsp-8+arg_0], rbx
0x180004115  push    rbp
0x180004116  push    rsi
0x180004117  push    rdi
0x180004118  push    r12
0x18000411a  push    r13
0x18000411c  push    r14
0x18000411e  push    r15
0x180004120  lea     rbp, [rsp-27h]
0x180004125  sub     rsp, 0B0h
0x18000412c  mov     rsi, r8
0x18000412f  mov     edi, edx
0x180004131  mov     rbx, cs:Feature_CUIPopupHelper__descriptor
0x180004138  mov     ebx, [rbx]
0x18000413a  test    bl, 4
0x18000413d  jnz     short loc_18000414A
0x18000413f  lea     rdx, [rbp+57h+var_70]
0x180004143  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CUIPopupHelper@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CUIPopupHelper>::GetCachedFeatureEnabledState(void)
0x180004148  mov     ebx, [rax]
0x18000414a  xor     r13d, r13d
0x18000414d  mov     dword ptr [rbp+57h+var_90], r13d
0x180004151  mov     word ptr [rbp+57h+var_90+4], 3
0x180004157  mov     dword ptr [rbp+57h+var_68], 3
0x18000415e  mov     r8d, 2
0x180004164  lea     rdx, qword_1800B3618
0x18000416b  lea     rcx, [rbp+57h+var_60]
0x18000416f  call    wil_details_FeatureReporting_RecordUsageInCache
0x180004174  mov     r15d, [rax+4]
0x180004178  mov     r12d, [rax+8]
0x18000417c  mov     r14d, [rax+10h]
0x180004180  cmp     [rax], r13d
0x180004183  jz      short loc_18000419D
0x180004185  lea     r8, qword_1800B3618; struct wil_details_FeatureReportingCache *
0x18000418c  mov     edx, 84350Ch; unsigned int
0x180004191  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180004198  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000419d  test    r15d, r15d
0x1800041a0  jz      short loc_1800041B2
0x1800041a2  mov     r8d, r15d; unsigned int
0x1800041a5  mov     edx, r12d; unsigned int
0x1800041a8  mov     ecx, 84350Ch; this
0x1800041ad  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800041b2  test    r14d, r14d
0x1800041b5  jnz     short loc_1800041CA
0x1800041b7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1800041be  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800041c5  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x1800041ca  bt      ebx, 0Ah
0x1800041ce  jnb     short loc_1800041ED
0x1800041d0  mov     edx, 2
0x1800041d5  bt      ebx, 0Bh
0x1800041d9  jnb     short loc_1800041E0
0x1800041db  mov     edx, 80000002h; unsigned int
0x1800041e0  xor     r8d, r8d; unsigned int
0x1800041e3  mov     ecx, 84350Ch; this
0x1800041e8  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800041ed  test    r14d, r14d
0x1800041f0  jnz     short loc_18000424F
0x1800041f2  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800041f9  test    rax, rax
0x1800041fc  jz      short loc_180004210
0x1800041fe  mov     r8b, 3
0x180004201  mov     edx, 2
0x180004206  mov     ecx, 84350Ch
0x18000420b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004210  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180004217  test    rax, rax
0x18000421a  jz      short loc_18000424F
0x18000421c  mov     [rsp+0E0h+var_A8], 1
0x180004225  mov     [rsp+0E0h+var_B0], r13b
0x18000422a  mov     [rsp+0E0h+var_B8], r13
0x18000422f  lea     rcx, [rbp+57h+var_68]
0x180004233  mov     [rsp+0E0h+ppv], rcx; char *
0x180004238  mov     r9d, 1
0x18000423e  xor     r8d, r8d
0x180004241  lea     rdx, [rbp+57h+var_90]
0x180004245  mov     ecx, 84350Ch
0x18000424a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000424f  mov     [rsi], r13
0x180004252  mov     [rbp+57h+var_60], r13d
0x180004256  mov     [rbp+57h+var_5C], edi
0x180004259  xor     eax, eax
0x18000425b  mov     [rbp+57h+var_58], eax
0x18000425e  mov     [rbp+57h+var_88], r13
0x180004262  lea     rcx, [rbp+57h+var_88]
0x180004266  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000426b  mov     [rbp+57h+var_88], r13
0x18000426f  mov     rax, cs:Feature_CUIPopupHelper__descriptor
0x180004276  mov     ebx, [rax]
0x180004278  test    bl, 4
0x18000427b  jnz     short loc_180004288
0x18000427d  lea     rdx, [rbp+57h+var_68]
0x180004281  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CUIPopupHelper@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CUIPopupHelper>::GetCachedFeatureEnabledState(void)
0x180004286  mov     ebx, [rax]
0x180004288  mov     dword ptr [rbp+57h+var_90], r13d
0x18000428c  mov     word ptr [rbp+57h+var_90+4], 3
0x180004292  mov     dword ptr [rbp+57h+var_68], 3
0x180004299  mov     r8d, 2
0x18000429f  lea     rdx, qword_1800B3618
0x1800042a6  lea     rcx, [rbp+57h+var_48]
0x1800042aa  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800042af  mov     r14d, [rax+4]
0x1800042b3  mov     r15d, [rax+8]
0x1800042b7  mov     edi, [rax+10h]
0x1800042ba  cmp     dword ptr [rax], 0
0x1800042bd  jz      short loc_1800042D7
0x1800042bf  lea     r8, qword_1800B3618; struct wil_details_FeatureReportingCache *
0x1800042c6  mov     edx, 84350Ch; unsigned int
0x1800042cb  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800042d2  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800042d7  test    r14d, r14d
0x1800042da  jz      short loc_1800042EC
0x1800042dc  mov     r8d, r14d; unsigned int
0x1800042df  mov     edx, r15d; unsigned int
0x1800042e2  mov     ecx, 84350Ch; this
0x1800042e7  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800042ec  test    edi, edi
0x1800042ee  jnz     short loc_180004303
0x1800042f0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x1800042f7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800042fe  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180004303  bt      ebx, 0Ah
0x180004307  jnb     short loc_180004326
0x180004309  mov     edx, 2
0x18000430e  bt      ebx, 0Bh
0x180004312  jnb     short loc_180004319
0x180004314  mov     edx, 80000002h; unsigned int
0x180004319  xor     r8d, r8d; unsigned int
0x18000431c  mov     ecx, 84350Ch; this
0x180004321  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180004326  test    edi, edi
0x180004328  jnz     short loc_180004387
0x18000432a  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180004331  test    rax, rax
0x180004334  jz      short loc_180004348
0x180004336  mov     r8b, 3
0x180004339  mov     edx, 2
0x18000433e  mov     ecx, 84350Ch
0x180004343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004348  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000434f  test    rax, rax
0x180004352  jz      short loc_180004387
0x180004354  mov     [rsp+0E0h+var_A8], 1
0x18000435d  mov     [rsp+0E0h+var_B0], 0
0x180004362  mov     [rsp+0E0h+var_B8], r13
0x180004367  lea     rdx, [rbp+57h+var_68]
0x18000436b  mov     [rsp+0E0h+ppv], rdx
0x180004370  mov     r9d, 1
0x180004376  xor     r8d, r8d
0x180004379  lea     rdx, [rbp+57h+var_90]
0x18000437d  mov     ecx, 84350Ch
0x180004382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004387  mov     [rbp+57h+var_78], r13
0x18000438b  mov     [rbp+57h+var_80], r13
0x18000438f  lea     rax, [rbp+57h+var_78]
0x180004393  mov     [rsp+0E0h+ppv], rax; int
0x180004398  lea     r9, _GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf; riid
0x18000439f  xor     edx, edx; pUnkOuter
0x1800043a1  mov     r8d, 4; dwClsContext
0x1800043a7  lea     rcx, CLSID_ShellServiceHostBrokerProvider; rclsid
0x1800043ae  call    cs:__imp_CoCreateInstance
0x1800043b4  test    eax, eax
0x1800043b6  js      loc_18000445D
0x1800043bc  mov     rdi, [rbp+57h+var_78]
0x1800043c0  mov     rax, [rdi]
0x1800043c3  mov     rbx, [rax+18h]
0x1800043c7  lea     rcx, [rbp+57h+var_80]
0x1800043cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800043d0  lea     r9, [rbp+57h+var_80]
0x1800043d4  lea     r8, _GUID_5627cb1e_76a9_4621_a276_b68fb43d4d25
0x1800043db  lea     rdx, qword_1800931F0
0x1800043e2  mov     rcx, rdi
0x1800043e5  mov     rax, rbx
0x1800043e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ed  test    eax, eax
0x1800043ef  js      short loc_18000445D
0x1800043f1  mov     rcx, [rbp+57h+var_80]
0x1800043f5  mov     rax, [rcx]
0x1800043f8  lea     rdx, [rbp+57h+var_88]
0x1800043fc  mov     rax, [rax+30h]
0x180004400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004405  mov     ebx, eax
0x180004407  test    eax, eax
0x180004409  jns     short loc_18000445D
0x18000440b  mov     rcx, [rbp+5Fh]; this
0x18000440f  mov     r9d, eax; char *
0x180004412  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\onecore\\popupclient"...
0x180004419  mov     edx, 63h ; 'c'; void *
0x18000441e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004423  nop
0x180004424  mov     rcx, [rbp+57h+var_80]
0x180004428  test    rcx, rcx
0x18000442b  jz      short loc_18000443E
0x18000442d  mov     [rbp+57h+var_80], r13
0x180004431  mov     rax, [rcx]
0x180004434  mov     rax, [rax+10h]
0x180004438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443d  nop
0x18000443e  mov     rcx, [rbp+57h+var_78]
0x180004442  test    rcx, rcx
0x180004445  jz      short loc_180004458
0x180004447  mov     [rbp+57h+var_78], r13
0x18000444b  mov     rax, [rcx]
0x18000444e  mov     rax, [rax+10h]
0x180004452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004457  nop
0x180004458  jmp     loc_180004507
0x18000445d  mov     rcx, [rbp+57h+var_80]
0x180004461  test    rcx, rcx
0x180004464  jnz     loc_18000454E
0x18000446a  mov     [rbp+57h+var_90], r13
0x18000446e  lea     rcx, [rbp+57h+var_90]
0x180004472  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004477  lea     rax, [rbp+57h+var_90]
0x18000447b  mov     [rsp+0E0h+ppv], rax; int
0x180004480  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180004487  xor     edx, edx; pUnkOuter
0x180004489  mov     r8d, 4; dwClsContext
0x18000448f  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180004496  call    cs:__imp_CoCreateInstance
0x18000449c  mov     ebx, eax
0x18000449e  test    eax, eax
0x1800044a0  jns     short loc_1800044A9
0x1800044a2  mov     edx, 70h ; 'p'
0x1800044a7  jmp     short loc_1800044D6
0x1800044a9  mov     rcx, [rbp+57h+var_90]
0x1800044ad  mov     rax, [rcx]
0x1800044b0  lea     r9, [rbp+57h+var_88]
0x1800044b4  lea     r8, _GUID_4637e79c_de03_4aef_8a87_e796659e5e8d
0x1800044bb  lea     rdx, qword_1800931F0
0x1800044c2  mov     rax, [rax+18h]
0x1800044c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044cb  mov     ebx, eax
0x1800044cd  test    eax, eax
0x1800044cf  jns     short loc_180004541
0x1800044d1  mov     edx, 71h ; 'q'; void *
0x1800044d6  mov     r9d, eax; char *
0x1800044d9  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\onecore\\popupclient"...
0x1800044e0  mov     rcx, [rbp+5Fh]; this
0x1800044e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800044e9  nop
0x1800044ea  lea     rcx, [rbp+57h+var_90]
0x1800044ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800044f3  nop
0x1800044f4  lea     rcx, [rbp+57h+var_80]
0x1800044f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800044fd  nop
0x1800044fe  lea     rcx, [rbp+57h+var_78]
0x180004502  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180004507  mov     rcx, [rbp+5Fh]; this
0x18000450b  mov     r9d, ebx; char *
0x18000450e  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\onecore\\popupclient"...
0x180004515  mov     edx, 3Bh ; ';'; void *
0x18000451a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000451f  nop
0x180004520  mov     rcx, [rbp+57h+var_88]
0x180004524  test    rcx, rcx
0x180004527  jz      short loc_18000453A
0x180004529  mov     [rbp+57h+var_88], r13
0x18000452d  mov     rdx, [rcx]
0x180004530  mov     rax, [rdx+10h]
0x180004534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004539  nop
0x18000453a  mov     eax, ebx
0x18000453c  jmp     loc_1800046F3
0x180004541  lea     rcx, [rbp+57h+var_90]
0x180004545  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000454a  mov     rcx, [rbp+57h+var_80]
0x18000454e  test    rcx, rcx
0x180004551  jz      short loc_180004564
0x180004553  mov     [rbp+57h+var_80], r13
0x180004557  mov     rax, [rcx]
0x18000455a  mov     rax, [rax+10h]
0x18000455e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004563  nop
0x180004564  mov     rcx, [rbp+57h+var_78]
0x180004568  test    rcx, rcx
0x18000456b  jz      short loc_18000457E
0x18000456d  mov     [rbp+57h+var_78], r13
0x180004571  mov     rax, [rcx]
0x180004574  mov     rax, [rax+10h]
0x180004578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000457d  nop
0x18000457e  mov     [rbp+57h+var_70], r13
0x180004582  mov     rdi, [rbp+57h+var_88]
0x180004586  lea     rcx, [rbp+57h+var_70]
0x18000458a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000458f  mov     [rbp+57h+var_70], r13
0x180004593  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000459a  mov     ecx, 98h; unsigned __int64
0x18000459f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800045a4  test    rax, rax
0x1800045a7  jnz     short loc_1800045B3
0x1800045a9  mov     edi, 8007000Eh
0x1800045ae  jmp     loc_18000466D
0x1800045b3  mov     rcx, rax; this
0x1800045b6  call    ??0PopupClientImpl@@QEAA@XZ; PopupClientImpl::PopupClientImpl(void)
0x1800045bb  mov     rbx, rax
0x1800045be  mov     [rbp+57h+var_78], rax
0x1800045c2  mov     [rbp+57h+var_80], r13
  ... truncated ...
```
