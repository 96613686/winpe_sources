# PopupClientStatics::GetBroker(Windows::Internal::Shell::Popups::IPopupClientBroker * *)

- ea: `0x1800039c0`
- end: `0x180003d1c`
- name: `?GetBroker@PopupClientStatics@@AEAAJPEAPEAUIPopupClientBroker@Popups@Shell@Internal@Windows@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(PopupClientStatics *__hidden this, struct Windows::Internal::Shell::Popups::IPopupClientBroker **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005ceb0`

## callees

- `0x180003074`
- `0x1800039c0`
- `0x180003d24`
- `0x1800040e0`
- `0x180004714`
- `0x180018294`
- `0x18001cc38`
- `0x180026614`
- `0x180037c44`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003a76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003c92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003a76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003c92`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PopupClientStatics::GetBroker(
        PopupClientStatics *this,
        struct Windows::Internal::Shell::Popups::IPopupClientBroker **a2)
{
  int v3; // ebx
  _DWORD *v4; // rax
  __int64 v5; // r8
  unsigned int v6; // r9d
  unsigned int v7; // r14d
  unsigned int v8; // r15d
  int v9; // edi
  __int64 v10; // rcx
  LPVOID v11; // rcx
  LPVOID v13; // rdi
  int (__fastcall *v14)(LPVOID, __int64 *, GUID *, __int64 *); // rbx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  LPVOID v18; // rcx
  unsigned int v19; // edx
  HRESULT v20; // ebx
  __int64 v21; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  int ppvb; // [rsp+20h] [rbp-50h]
  _BYTE v25[32]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  LPVOID v27; // [rsp+B0h] [rbp+40h] BYREF
  int v28; // [rsp+B8h] [rbp+48h] BYREF
  __int16 v29; // [rsp+BCh] [rbp+4Ch]
  __int64 v30; // [rsp+C0h] [rbp+50h] BYREF
  LPVOID v31; // [rsp+C8h] [rbp+58h] BYREF

  v27 = this;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_CUIPopupHelper__descriptor;
  if ( (*(_DWORD *)Feature_CUIPopupHelper__descriptor & 4) == 0 )
    v3 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CUIPopupHelper>::GetCachedFeatureEnabledState(
                      this,
                      &v27);
  v28 = 0;
  v29 = 3;
  LODWORD(v27) = 3;
  v4 = (_DWORD *)wil_details_FeatureReporting_RecordUsageInCache(v25, &qword_1800B3618, 2);
  v7 = v4[1];
  v8 = v4[2];
  v9 = v4[4];
  if ( *v4 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      &wil::details::g_enabledStateManager,
      0x84350Cu,
      (struct wil_details_FeatureReportingCache *)&qword_1800B3618);
  if ( v7 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x84350C, v8, v7, v6, (const char *)ppv);
  if ( !v9 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( (v3 & 0x400) != 0 )
  {
    v19 = 2;
    if ( (v3 & 0x800) != 0 )
      v19 = -2147483646;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x84350C, v19, 0, v6, (const char *)ppv);
  }
  if ( !v9 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v5) = 3;
      g_wil_details_realtimeFeatureUsageHook(8664332, 2, v5);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(8664332, &v28, 0, 1, &v27, 0, 0, 1);
  }
  v31 = 0;
  v30 = 0;
  if ( CoCreateInstance(&CLSID_ShellServiceHostBrokerProvider, 0, 4u, &GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf, &v31) >= 0 )
  {
    v13 = v31;
    v14 = *(int (__fastcall **)(LPVOID, __int64 *, GUID *, __int64 *))(*(_QWORD *)v31 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    if ( v14(v13, qword_1800931F0, &GUID_5627cb1e_76a9_4621_a276_b68fb43d4d25, &v30) >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, struct Windows::Internal::Shell::Popups::IPopupClientBroker **))(*(_QWORD *)v30 + 48LL))(
              v30,
              a2);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\shell\\onecore\\popupclient\\lib\\popupclientstatics.cpp",
          (const char *)(unsigned int)v15,
          ppva);
        v17 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        v18 = v31;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
        }
        return v16;
      }
    }
  }
  v10 = v30;
  if ( !v30 )
  {
    v27 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v20 = CoCreateInstance(
            &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
            0,
            4u,
            &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
            &v27);
    if ( v20 >= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, struct Windows::Internal::Shell::Popups::IPopupClientBroker **))(*(_QWORD *)v27 + 24LL))(
              v27,
              qword_1800931F0,
              &GUID_4637e79c_de03_4aef_8a87_e796659e5e8d,
              a2);
      if ( v20 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
        v10 = v30;
        goto LABEL_13;
      }
      v21 = 113;
    }
    else
    {
      v21 = 112;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\shell\\onecore\\popupclient\\lib\\popupclientstatics.cpp",
      (const char *)(unsigned int)v20,
      ppvb);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    return (unsigned int)v20;
  }
LABEL_13:
  if ( v10 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return 0;
}

```

## disassembly

```asm
0x1800039c0  mov     [rsp-38h+arg_0], rcx
0x1800039c5  push    rbp
0x1800039c6  push    rbx
0x1800039c7  push    rsi
0x1800039c8  push    rdi
0x1800039c9  push    r12
0x1800039cb  push    r14
0x1800039cd  push    r15
0x1800039cf  mov     rbp, rsp
0x1800039d2  sub     rsp, 70h
0x1800039d6  mov     rsi, rdx
0x1800039d9  xor     r12d, r12d
0x1800039dc  mov     [rdx], r12
0x1800039df  mov     rbx, cs:Feature_CUIPopupHelper__descriptor
0x1800039e6  mov     ebx, [rbx]
0x1800039e8  test    bl, 4
0x1800039eb  jz      loc_180003B9F
0x1800039f1  mov     [rbp+arg_8], r12d
0x1800039f5  mov     [rbp+arg_C], 3
0x1800039fb  mov     dword ptr [rbp+arg_0], 3
0x180003a02  mov     r8d, 2
0x180003a08  lea     rdx, qword_1800B3618
0x180003a0f  lea     rcx, [rbp+var_20]
0x180003a13  call    wil_details_FeatureReporting_RecordUsageInCache
0x180003a18  mov     r14d, [rax+4]
0x180003a1c  mov     r15d, [rax+8]
0x180003a20  mov     edi, [rax+10h]
0x180003a23  cmp     [rax], r12d
0x180003a26  jnz     loc_180003BAF
0x180003a2c  test    r14d, r14d
0x180003a2f  jnz     loc_180003BCC
0x180003a35  test    edi, edi
0x180003a37  jz      loc_180003BE1
0x180003a3d  bt      ebx, 0Ah
0x180003a41  jb      loc_180003B82
0x180003a47  test    edi, edi
0x180003a49  jz      loc_180003C00
0x180003a4f  mov     [rbp+arg_18], r12
0x180003a53  mov     [rbp+arg_10], r12
0x180003a57  lea     rax, [rbp+arg_18]
0x180003a5b  mov     [rsp+70h+ppv], rax; int
0x180003a60  lea     r9, _GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf; riid
0x180003a67  xor     edx, edx; pUnkOuter
0x180003a69  mov     r8d, 4; dwClsContext
0x180003a6f  lea     rcx, CLSID_ShellServiceHostBrokerProvider; rclsid
0x180003a76  call    cs:__imp_CoCreateInstance
0x180003a7c  test    eax, eax
0x180003a7e  jns     short loc_180003ACE
0x180003a80  mov     rcx, [rbp+arg_10]
0x180003a84  test    rcx, rcx
0x180003a87  jz      loc_180003C66
0x180003a8d  test    rcx, rcx
0x180003a90  jz      short loc_180003AA3
0x180003a92  mov     [rbp+arg_10], r12
0x180003a96  mov     rax, [rcx]
0x180003a99  mov     rax, [rax+10h]
0x180003a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa2  nop
0x180003aa3  mov     rcx, [rbp+arg_18]
0x180003aa7  test    rcx, rcx
0x180003aaa  jz      short loc_180003ABD
0x180003aac  mov     [rbp+arg_18], r12
0x180003ab0  mov     rax, [rcx]
0x180003ab3  mov     rax, [rax+10h]
0x180003ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003abc  nop
0x180003abd  xor     eax, eax
0x180003abf  add     rsp, 70h
0x180003ac3  pop     r15
0x180003ac5  pop     r14
0x180003ac7  pop     r12
0x180003ac9  pop     rdi
0x180003aca  pop     rsi
0x180003acb  pop     rbx
0x180003acc  pop     rbp
0x180003acd  retn
0x180003ace  mov     rdi, [rbp+arg_18]
0x180003ad2  mov     rax, [rdi]
0x180003ad5  mov     rbx, [rax+18h]
0x180003ad9  lea     rcx, [rbp+arg_10]
0x180003add  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180003ae2  lea     r9, [rbp+arg_10]
0x180003ae6  lea     r8, _GUID_5627cb1e_76a9_4621_a276_b68fb43d4d25
0x180003aed  lea     rdx, qword_1800931F0
0x180003af4  mov     rcx, rdi
0x180003af7  mov     rax, rbx
0x180003afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aff  test    eax, eax
0x180003b01  js      loc_180003A80
0x180003b07  mov     rcx, [rbp+arg_10]
0x180003b0b  mov     rax, [rcx]
0x180003b0e  mov     rdx, rsi
0x180003b11  mov     rax, [rax+30h]
0x180003b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b1a  mov     ebx, eax
0x180003b1c  test    eax, eax
0x180003b1e  jns     loc_180003A80
0x180003b24  mov     rcx, [rbp+38h]; this
0x180003b28  mov     r9d, eax; char *
0x180003b2b  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\onecore\\popupclient"...
0x180003b32  mov     edx, 63h ; 'c'; void *
0x180003b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b3c  nop
0x180003b3d  mov     rcx, [rbp+arg_10]
0x180003b41  test    rcx, rcx
0x180003b44  jz      short loc_180003B57
0x180003b46  mov     [rbp+arg_10], r12
0x180003b4a  mov     rax, [rcx]
0x180003b4d  mov     rax, [rax+10h]
0x180003b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b56  nop
0x180003b57  mov     rcx, [rbp+arg_18]
0x180003b5b  test    rcx, rcx
0x180003b5e  jz      short loc_180003B71
0x180003b60  mov     [rbp+arg_18], r12
0x180003b64  mov     rax, [rcx]
0x180003b67  mov     rax, [rax+10h]
0x180003b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b70  nop
0x180003b71  mov     eax, ebx
0x180003b73  add     rsp, 70h
0x180003b77  pop     r15
0x180003b79  pop     r14
0x180003b7b  pop     r12
0x180003b7d  pop     rdi
0x180003b7e  pop     rsi
0x180003b7f  pop     rbx
0x180003b80  pop     rbp
0x180003b81  retn
0x180003b82  mov     edx, 2; unsigned int
0x180003b87  bt      ebx, 0Bh
0x180003b8b  jb      short loc_180003BF9
0x180003b8d  xor     r8d, r8d; unsigned int
0x180003b90  mov     ecx, 84350Ch; this
0x180003b95  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180003b9a  jmp     loc_180003A47
0x180003b9f  lea     rdx, [rbp+arg_0]
0x180003ba3  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CUIPopupHelper@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CUIPopupHelper>::GetCachedFeatureEnabledState(void)
0x180003ba8  mov     ebx, [rax]
0x180003baa  jmp     loc_1800039F1
0x180003baf  lea     r8, qword_1800B3618; struct wil_details_FeatureReportingCache *
0x180003bb6  mov     edx, 84350Ch; unsigned int
0x180003bbb  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180003bc2  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180003bc7  jmp     loc_180003A2C
0x180003bcc  mov     r8d, r14d; unsigned int
0x180003bcf  mov     edx, r15d; unsigned int
0x180003bd2  mov     ecx, 84350Ch; this
0x180003bd7  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180003bdc  jmp     loc_180003A35
0x180003be1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x180003be8  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180003bef  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x180003bf4  jmp     loc_180003A3D
0x180003bf9  mov     edx, 80000002h
0x180003bfe  jmp     short loc_180003B8D
0x180003c00  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180003c07  test    rax, rax
0x180003c0a  jz      short loc_180003C1E
0x180003c0c  mov     r8b, 3
0x180003c0f  mov     edx, 2
0x180003c14  mov     ecx, 84350Ch
0x180003c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c1e  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180003c25  test    rax, rax
0x180003c28  jz      loc_180003A4F
0x180003c2e  mov     [rsp+70h+var_38], 1
0x180003c37  mov     [rsp+70h+var_40], r12b
0x180003c3c  mov     [rsp+70h+var_48], r12
0x180003c41  lea     rdx, [rbp+arg_0]
0x180003c45  mov     [rsp+70h+ppv], rdx
0x180003c4a  mov     r9d, 1
0x180003c50  xor     r8d, r8d
0x180003c53  lea     rdx, [rbp+arg_8]
0x180003c57  mov     ecx, 84350Ch
0x180003c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c61  jmp     loc_180003A4F
0x180003c66  mov     [rbp+arg_0], r12
0x180003c6a  lea     rcx, [rbp+arg_0]
0x180003c6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003c73  lea     rax, [rbp+arg_0]
0x180003c77  mov     [rsp+70h+ppv], rax; int
0x180003c7c  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180003c83  xor     edx, edx; pUnkOuter
0x180003c85  mov     r8d, 4; dwClsContext
0x180003c8b  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180003c92  call    cs:__imp_CoCreateInstance
0x180003c98  mov     ebx, eax
0x180003c9a  test    eax, eax
0x180003c9c  jns     short loc_180003CE2
0x180003c9e  mov     edx, 70h ; 'p'
0x180003ca3  jmp     short loc_180003CAA
0x180003ca5  mov     edx, 71h ; 'q'; void *
0x180003caa  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\onecore\\popupclient"...
0x180003cb1  mov     r9d, ebx; char *
0x180003cb4  mov     rcx, [rbp+38h]; this
0x180003cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cbd  nop
0x180003cbe  lea     rcx, [rbp+arg_0]
0x180003cc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003cc7  nop
0x180003cc8  lea     rcx, [rbp+arg_10]
0x180003ccc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180003cd1  nop
0x180003cd2  lea     rcx, [rbp+arg_18]
0x180003cd6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180003cdb  mov     eax, ebx
0x180003cdd  jmp     loc_180003ABF
0x180003ce2  mov     rcx, [rbp+arg_0]
0x180003ce6  mov     rax, [rcx]
0x180003ce9  mov     r9, rsi
0x180003cec  lea     r8, _GUID_4637e79c_de03_4aef_8a87_e796659e5e8d
0x180003cf3  lea     rdx, qword_1800931F0
0x180003cfa  mov     rax, [rax+18h]
0x180003cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d03  mov     ebx, eax
0x180003d05  test    eax, eax
0x180003d07  js      short loc_180003CA5
0x180003d09  lea     rcx, [rbp+arg_0]
0x180003d0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003d12  mov     rcx, [rbp+arg_10]
0x180003d16  jmp     loc_180003A8D
```
