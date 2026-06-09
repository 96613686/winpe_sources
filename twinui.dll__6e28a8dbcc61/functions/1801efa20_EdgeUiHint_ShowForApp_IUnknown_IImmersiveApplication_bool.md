# EdgeUiHint::ShowForApp(IUnknown *,IImmersiveApplication *,bool)

- ea: `0x1801efa20`
- end: `0x1801efde6`
- name: `?ShowForApp@EdgeUiHint@@UEAAJPEAUIUnknown@@PEAUIImmersiveApplication@@_N@Z`
- size: `966`
- prototype: `int(EdgeUiHint *__hidden this, struct IUnknown *, struct IImmersiveApplication *, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180015114`
- `0x18003c5e4`
- `0x18004f684`
- `0x180055dd0`
- `0x1800b6160`
- `0x1800ead54`
- `0x18013d330`
- `0x18014e434`
- `0x1801efa20`
- `0x1803a3010`

## import_xrefs

- `USER32!UpdateWindow` at `0x1801efd7c`
- `USER32!UpdateWindow` at `0x1801efd7c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1801efd9f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1801efd9f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1801efd73`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1801efd73`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetTimer` at `0x1801efdbc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetTimer` at `0x1801efdbc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x1801efd34`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x1801efd34`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801efa91`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801efab8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801efa91`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801efab8`
- `ext-ms-win-ntuser-private-l1-1-1!CreateWindowInBand` at `0x1801efd08`
- `ext-ms-win-ntuser-private-l1-1-1!CreateWindowInBand` at `0x1801efd08`
- `dwmapi!__imp_DwmpBeginTransitionRequest` at `0x1801efd4b`
- `dwmapi!__imp_DwmpBeginTransitionRequest` at `0x1801efd4b`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x1801efd63`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x1801efd63`
- `dwmapi!__imp_DwmpEndTransitionRequest` at `0x1801efd89`
- `dwmapi!__imp_DwmpEndTransitionRequest` at `0x1801efd89`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EdgeUiHint::ShowForApp(
        EdgeUiHint *this,
        struct IUnknown *a2,
        struct IImmersiveApplication *a3,
        char a4)
{
  IUnknown *v6; // rbx
  int v8; // edi
  __int64 v9; // rcx
  HRESULT Service; // eax
  unsigned int v11; // ebx
  int Site; // eax
  __int64 v13; // rdx
  HWND v15; // rcx
  int v16; // eax
  float v17; // xmm1_4
  float v18; // xmm0_4
  int v19; // edi
  int v20; // ebx
  int IsThreadRTL; // eax
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // eax
  __int64 WindowInBand; // rax
  const char *v28; // r9
  HWND *v29; // rbx
  int v30; // [rsp+20h] [rbp-49h]
  void *v31; // [rsp+70h] [rbp+7h] BYREF
  void *ppvOut[2]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = a2;
  v8 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations>::GetImpl'::`2'::impl,
    a2);
  v9 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( IUnknown_QueryService(v6, &stru_1804109E8, &GUID_af855df0_7bbf_47b3_ae2e_85ba3869660f, (void **)this + 7) >= 0 )
  {
    ppvOut[0] = 0;
    Service = IUnknown_QueryService(
                v6,
                &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
                &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
                ppvOut);
    v11 = Service;
    if ( Service < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
        (const char *)(unsigned int)Service,
        v30);
LABEL_11:
      wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(ppvOut);
      return v11;
    }
    v31 = 0;
    Site = CWRLObjectWithSite::GetSite(
             (EdgeUiHint *)((char *)this - 24),
             &GUID_49233ba3_27b2_46b6_9601_446910c8c663,
             &v31);
    v11 = Site;
    if ( Site < 0 )
    {
      v13 = 144;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
        (const char *)(unsigned int)Site,
        v30);
      wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(&v31);
      goto LABEL_11;
    }
    Site = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, void *))(**((_QWORD **)this + 7) + 32LL))(
             *((_QWORD *)this + 7),
             *((unsigned int *)this + 4),
             ppvOut[0],
             v31);
    v11 = Site;
    if ( Site < 0 )
    {
      v13 = 145;
      goto LABEL_10;
    }
    wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(&v31);
    wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(ppvOut);
    return (unsigned int)v8;
  }
  v15 = (HWND)*((_QWORD *)this + 3);
  if ( v15 )
  {
    v29 = (HWND *)((char *)this + 24);
    if ( IsWindowVisible(v15) )
    {
LABEL_41:
      if ( a4 )
        *((_QWORD *)this + 4) = SetTimer(*v29, 1u, 0x1388u, 0);
      return (unsigned int)v8;
    }
LABEL_36:
    v8 = DwmpBeginTransitionRequest(4);
    if ( v8 >= 0 )
    {
      v29 = (HWND *)((char *)this + 24);
      v8 = DwmpTransitionWindow(*((_QWORD *)this + 3), 1048601);
    }
    ShowWindow(*v29, 8);
    UpdateWindow(*v29);
    if ( v8 < 0 )
    {
      SendMessageW(*v29, 0x32Au, 4u, 4);
      v8 = 0;
    }
    else
    {
      DwmpEndTransitionRequest(4);
    }
    goto LABEL_41;
  }
  IUnknown_GetScaleFactor(v6, (enum DEVICE_SCALE_FACTOR *)this + 12);
  *(_OWORD *)ppvOut = 0;
  v16 = (*(__int64 (__fastcall **)(struct IImmersiveApplication *, void **))(*(_QWORD *)a3 + 200LL))(a3, ppvOut);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
      (const char *)(unsigned int)v16,
      v30);
    return v11;
  }
  v17 = (float)(16 * *((_DWORD *)this + 12)) / 100.0;
  if ( (unsigned int)(*((_DWORD *)this + 4) - 2) > 1 )
  {
    v18 = (float)(16 * *((_DWORD *)this + 12)) / 100.0;
    v17 = (float)(80 * *((_DWORD *)this + 12)) / 100.0;
  }
  else
  {
    v18 = (float)(80 * *((_DWORD *)this + 12)) / 100.0;
  }
  v19 = (int)v17;
  v20 = (int)v18;
  IsThreadRTL = Mirror_IsThreadRTL();
  v22 = *((_DWORD *)this + 4);
  if ( !v22 )
  {
    if ( IsThreadRTL )
    {
      v25 = LODWORD(ppvOut[1]) - v20 - LODWORD(ppvOut[0]);
      goto LABEL_32;
    }
    goto LABEL_30;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    if ( !IsThreadRTL )
    {
      v25 = LODWORD(ppvOut[1]) - v20;
LABEL_32:
      v26 = HIDWORD(ppvOut[0]) + (HIDWORD(ppvOut[1]) - v19 - HIDWORD(ppvOut[0])) / 2;
LABEL_33:
      WindowInBand = CreateWindowInBand(
                       134742144,
                       L"EdgeUiInputHintWndClass",
                       0,
                       0x80000000LL,
                       v25,
                       v26,
                       v20,
                       (int)v17,
                       0,
                       0,
                       &_ImageBase,
                       (char *)this - 24,
                       7);
      v29 = (HWND *)((char *)this + 24);
      *((_QWORD *)this + 3) = WindowInBand;
      if ( !WindowInBand )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0xE6,
                 (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
                 v28);
      goto LABEL_36;
    }
LABEL_30:
    v25 = (int)ppvOut[0];
    goto LABEL_32;
  }
  v24 = v23 - 1;
  if ( !v24 )
  {
    v25 = LODWORD(ppvOut[0]) + (LODWORD(ppvOut[1]) - v20 - LODWORD(ppvOut[0])) / 2;
    v26 = HIDWORD(ppvOut[0]);
    goto LABEL_33;
  }
  if ( v24 == 1 )
  {
    v25 = LODWORD(ppvOut[0]) + (LODWORD(ppvOut[1]) - v20 - LODWORD(ppvOut[0])) / 2;
    v26 = HIDWORD(ppvOut[1]) - v19;
    goto LABEL_33;
  }
  v8 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x110,
    (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
    (const char *)0x8000FFFFLL,
    v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801efa20  push    rbp
0x1801efa22  push    rbx
0x1801efa23  push    rsi
0x1801efa24  push    rdi
0x1801efa25  push    r12
0x1801efa27  push    r14
0x1801efa29  push    r15
0x1801efa2b  lea     rbp, [rsp-27h]
0x1801efa30  sub     rsp, 90h
0x1801efa37  mov     rax, cs:__security_cookie
0x1801efa3e  xor     rax, rsp
0x1801efa41  mov     [rbp+57h+var_38], rax
0x1801efa45  mov     r12b, r9b
0x1801efa48  mov     r15, r8
0x1801efa4b  mov     rbx, rdx
0x1801efa4e  mov     rsi, rcx
0x1801efa51  xor     edi, edi
0x1801efa53  mov     dl, 1
0x1801efa55  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputDrivenEdgeAnimations@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputDrivenEdgeAnimations@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations> `wil::Feature<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations>::GetImpl(void)'::`2'::impl
0x1801efa5c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_InputDrivenEdgeAnimations@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801efa61  lea     r14, [rsi+38h]
0x1801efa65  mov     rcx, [r14]
0x1801efa68  mov     [r14], rdi
0x1801efa6b  test    rcx, rcx
0x1801efa6e  jz      short loc_1801EFA7D
0x1801efa70  mov     rax, [rcx]
0x1801efa73  mov     rax, [rax+10h]
0x1801efa77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801efa7c  nop
0x1801efa7d  mov     r9, r14; ppvOut
0x1801efa80  lea     r8, _GUID_af855df0_7bbf_47b3_ae2e_85ba3869660f; riid
0x1801efa87  lea     rdx, stru_1804109E8; guidService
0x1801efa8e  mov     rcx, rbx; punk
0x1801efa91  call    cs:__imp_IUnknown_QueryService
0x1801efa97  test    eax, eax
0x1801efa99  js      loc_1801EFB72
0x1801efa9f  mov     [rbp+57h+ppvOut], 0
0x1801efaa7  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1801efaab  lea     rdx, _GUID_880b26f8_9197_43d0_8045_8702d0d72000; guidService
0x1801efab2  mov     r8, rdx; riid
0x1801efab5  mov     rcx, rbx; punk
0x1801efab8  call    cs:__imp_IUnknown_QueryService
0x1801efabe  mov     ebx, eax
0x1801efac0  test    eax, eax
0x1801efac2  jns     short loc_1801EFADE
0x1801efac4  mov     rcx, [rbp+5Fh]; this
0x1801efac8  mov     r9d, eax; char *
0x1801efacb  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801efad2  mov     edx, 8Eh; void *
0x1801efad7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801efadc  jmp     short loc_1801EFB4A
0x1801efade  mov     [rbp+57h+var_50], 0
0x1801efae6  lea     rcx, [rsi-18h]; this
0x1801efaea  lea     r8, [rbp+57h+var_50]; void **
0x1801efaee  lea     rdx, _GUID_49233ba3_27b2_46b6_9601_446910c8c663; struct _GUID *
0x1801efaf5  call    ?GetSite@CWRLObjectWithSite@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWRLObjectWithSite::GetSite(_GUID const &,void * *)
0x1801efafa  mov     ebx, eax
0x1801efafc  test    eax, eax
0x1801efafe  jns     short loc_1801EFB07
0x1801efb00  mov     edx, 90h
0x1801efb05  jmp     short loc_1801EFB2C
0x1801efb07  mov     rcx, [r14]
0x1801efb0a  mov     rax, [rcx]
0x1801efb0d  mov     r9, [rbp+57h+var_50]
0x1801efb11  mov     r8, [rbp+57h+ppvOut]
0x1801efb15  mov     edx, [rsi+10h]
0x1801efb18  mov     rax, [rax+20h]
0x1801efb1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801efb21  mov     ebx, eax
0x1801efb23  test    eax, eax
0x1801efb25  jns     short loc_1801EFB5A
0x1801efb27  mov     edx, 91h; void *
0x1801efb2c  mov     r9d, eax; char *
0x1801efb2f  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801efb36  mov     rcx, [rbp+5Fh]; this
0x1801efb3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801efb3f  nop
0x1801efb40  lea     rcx, [rbp+57h+var_50]
0x1801efb44  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1801efb49  nop
0x1801efb4a  lea     rcx, [rbp+57h+ppvOut]
0x1801efb4e  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1801efb53  mov     eax, ebx
0x1801efb55  jmp     loc_1801EFDC8
0x1801efb5a  lea     rcx, [rbp+57h+var_50]
0x1801efb5e  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1801efb63  nop
0x1801efb64  lea     rcx, [rbp+57h+ppvOut]
0x1801efb68  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1801efb6d  jmp     loc_1801EFDC6
0x1801efb72  lea     r14, [rsi-18h]
0x1801efb76  mov     rcx, [r14+30h]; hWnd
0x1801efb7a  test    rcx, rcx
0x1801efb7d  jnz     loc_1801EFD34
0x1801efb83  lea     rdx, [rsi+30h]; enum DEVICE_SCALE_FACTOR *
0x1801efb87  mov     rcx, rbx; punk
0x1801efb8a  call    ?IUnknown_GetScaleFactor@@YAJPEAUIUnknown@@PEAW4DEVICE_SCALE_FACTOR@@@Z; IUnknown_GetScaleFactor(IUnknown *,DEVICE_SCALE_FACTOR *)
0x1801efb8f  xorps   xmm0, xmm0
0x1801efb92  movdqu  xmmword ptr [rbp+57h+ppvOut], xmm0
0x1801efb97  mov     rax, [r15]
0x1801efb9a  lea     rdx, [rbp+57h+ppvOut]
0x1801efb9e  mov     rcx, r15
0x1801efba1  mov     rax, [rax+0C8h]
0x1801efba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801efbad  mov     ebx, eax
0x1801efbaf  test    eax, eax
0x1801efbb1  jns     short loc_1801EFBCD
0x1801efbb3  mov     rcx, [rbp+5Fh]; this
0x1801efbb7  mov     r9d, eax; char *
0x1801efbba  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801efbc1  mov     edx, 9Ch; void *
0x1801efbc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801efbcb  jmp     short loc_1801EFB53
0x1801efbcd  mov     eax, [rsi+10h]
0x1801efbd0  mov     r15d, 2
0x1801efbd6  sub     eax, r15d
0x1801efbd9  cmp     eax, 1
0x1801efbdc  setbe   dl
0x1801efbdf  mov     ecx, [rsi+30h]
0x1801efbe2  mov     eax, ecx
0x1801efbe4  shl     eax, 4
0x1801efbe7  movd    xmm1, eax
0x1801efbeb  cvtdq2ps xmm1, xmm1
0x1801efbee  divss   xmm1, cs:__real@42c80000
0x1801efbf6  lea     eax, [rcx+rcx*4]
0x1801efbf9  shl     eax, 4
0x1801efbfc  movd    xmm2, eax
0x1801efc00  cvtdq2ps xmm2, xmm2
0x1801efc03  divss   xmm2, cs:__real@42c80000
0x1801efc0b  test    dl, dl
0x1801efc0d  jz      short loc_1801EFC14
0x1801efc0f  movaps  xmm0, xmm2
0x1801efc12  jmp     short loc_1801EFC1A
0x1801efc14  movaps  xmm0, xmm1
0x1801efc17  movaps  xmm1, xmm2
0x1801efc1a  cvttss2si edi, xmm1
0x1801efc1e  cvttss2si ebx, xmm0
0x1801efc22  call    Mirror_IsThreadRTL
0x1801efc27  mov     ecx, [rsi+10h]
0x1801efc2a  test    ecx, ecx
0x1801efc2c  jz      short loc_1801EFC98
0x1801efc2e  sub     ecx, 1
0x1801efc31  jz      short loc_1801EFC8D
0x1801efc33  sub     ecx, 1
0x1801efc36  jz      short loc_1801EFC77
0x1801efc38  cmp     ecx, 1
0x1801efc3b  jz      short loc_1801EFC5F
0x1801efc3d  mov     rcx, [rbp+5Fh]; this
0x1801efc41  mov     edi, 8000FFFFh
0x1801efc46  mov     r9d, edi; char *
0x1801efc49  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801efc50  mov     edx, 110h; void *
0x1801efc55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801efc5a  jmp     loc_1801EFDC6
0x1801efc5f  mov     eax, dword ptr [rbp+57h+ppvOut+8]
0x1801efc62  sub     eax, ebx
0x1801efc64  sub     eax, dword ptr [rbp+57h+ppvOut]
0x1801efc67  cdq
0x1801efc68  idiv    r15d
0x1801efc6b  mov     ecx, eax
0x1801efc6d  add     ecx, dword ptr [rbp+57h+ppvOut]
0x1801efc70  mov     eax, dword ptr [rbp+57h+ppvOut+0Ch]
0x1801efc73  sub     eax, edi
0x1801efc75  jmp     short loc_1801EFCB8
0x1801efc77  mov     eax, dword ptr [rbp+57h+ppvOut+8]
0x1801efc7a  sub     eax, ebx
0x1801efc7c  sub     eax, dword ptr [rbp+57h+ppvOut]
0x1801efc7f  cdq
0x1801efc80  idiv    r15d
0x1801efc83  mov     ecx, eax
0x1801efc85  add     ecx, dword ptr [rbp+57h+ppvOut]
0x1801efc88  mov     eax, dword ptr [rbp+57h+ppvOut+4]
0x1801efc8b  jmp     short loc_1801EFCB8
0x1801efc8d  test    eax, eax
0x1801efc8f  jnz     short loc_1801EFC9C
0x1801efc91  mov     ecx, dword ptr [rbp+57h+ppvOut+8]
0x1801efc94  sub     ecx, ebx
0x1801efc96  jmp     short loc_1801EFCA9
0x1801efc98  test    eax, eax
0x1801efc9a  jnz     short loc_1801EFCA1
0x1801efc9c  mov     ecx, dword ptr [rbp+57h+ppvOut]
0x1801efc9f  jmp     short loc_1801EFCA9
0x1801efca1  mov     ecx, dword ptr [rbp+57h+ppvOut+8]
0x1801efca4  sub     ecx, ebx
0x1801efca6  sub     ecx, dword ptr [rbp+57h+ppvOut]
0x1801efca9  mov     eax, dword ptr [rbp+57h+ppvOut+0Ch]
0x1801efcac  sub     eax, edi
0x1801efcae  sub     eax, dword ptr [rbp+57h+ppvOut+4]
0x1801efcb1  cdq
0x1801efcb2  idiv    r15d
0x1801efcb5  add     eax, dword ptr [rbp+57h+ppvOut+4]
0x1801efcb8  mov     [rsp+0C0h+var_60], 7
0x1801efcc0  mov     [rsp+0C0h+var_68], r14
0x1801efcc5  lea     rdx, __ImageBase
0x1801efccc  mov     [rsp+0C0h+var_70], rdx
0x1801efcd1  mov     [rsp+0C0h+var_78], 0
0x1801efcda  mov     [rsp+0C0h+var_80], 0
0x1801efce3  mov     [rsp+0C0h+var_88], edi
0x1801efce7  mov     [rsp+0C0h+var_90], ebx
0x1801efceb  mov     [rsp+0C0h+var_98], eax
0x1801efcef  mov     [rsp+0C0h+var_A0], ecx
0x1801efcf3  mov     r9d, 80000000h
0x1801efcf9  xor     r8d, r8d
0x1801efcfc  lea     rdx, aEdgeuiinputhin; "EdgeUiInputHintWndClass"
0x1801efd03  mov     ecx, 8080080h
0x1801efd08  call    cs:__imp_CreateWindowInBand
0x1801efd0e  lea     rbx, [rsi+18h]
0x1801efd12  mov     [rbx], rax
0x1801efd15  test    rax, rax
0x1801efd18  jnz     short loc_1801EFD42
0x1801efd1a  mov     rcx, [rbp+5Fh]; this
0x1801efd1e  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801efd25  mov     edx, 0E6h; void *
0x1801efd2a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801efd2f  jmp     loc_1801EFDC8
0x1801efd34  call    cs:__imp_IsWindowVisible
0x1801efd3a  lea     rbx, [rsi+18h]
0x1801efd3e  test    eax, eax
0x1801efd40  jnz     short loc_1801EFDA7
0x1801efd42  mov     r14d, 4
0x1801efd48  mov     ecx, r14d
0x1801efd4b  call    cs:__imp_DwmpBeginTransitionRequest
0x1801efd51  mov     edi, eax
0x1801efd53  test    eax, eax
0x1801efd55  js      short loc_1801EFD6B
0x1801efd57  lea     rbx, [rsi+18h]
0x1801efd5b  mov     edx, 100019h
0x1801efd60  mov     rcx, [rbx]
0x1801efd63  call    cs:__imp_DwmpTransitionWindow
0x1801efd69  mov     edi, eax
0x1801efd6b  mov     edx, 8; nCmdShow
0x1801efd70  mov     rcx, [rbx]; hWnd
0x1801efd73  call    cs:__imp_ShowWindow
0x1801efd79  mov     rcx, [rbx]; hWnd
0x1801efd7c  call    cs:__imp_UpdateWindow
0x1801efd82  test    edi, edi
0x1801efd84  js      short loc_1801EFD91
0x1801efd86  mov     ecx, r14d
0x1801efd89  call    cs:__imp_DwmpEndTransitionRequest
0x1801efd8f  jmp     short loc_1801EFDA7
0x1801efd91  mov     r9, r14; lParam
0x1801efd94  mov     r8, r14; wParam
0x1801efd97  mov     edx, 32Ah; Msg
0x1801efd9c  mov     rcx, [rbx]; hWnd
0x1801efd9f  call    cs:__imp_SendMessageW
0x1801efda5  xor     edi, edi
0x1801efda7  test    r12b, r12b
0x1801efdaa  jz      short loc_1801EFDC6
0x1801efdac  xor     r9d, r9d; lpTimerFunc
0x1801efdaf  lea     edx, [r9+1]; nIDEvent
0x1801efdb3  mov     r8d, 1388h; uElapse
0x1801efdb9  mov     rcx, [rbx]; hWnd
0x1801efdbc  call    cs:__imp_SetTimer
0x1801efdc2  mov     [rsi+20h], rax
0x1801efdc6  mov     eax, edi
0x1801efdc8  mov     rcx, [rbp+57h+var_38]
0x1801efdcc  xor     rcx, rsp; StackCookie
0x1801efdcf  call    __security_check_cookie
0x1801efdd4  add     rsp, 90h
0x1801efddb  pop     r15
0x1801efddd  pop     r14
0x1801efddf  pop     r12
0x1801efde1  pop     rdi
0x1801efde2  pop     rsi
0x1801efde3  pop     rbx
0x1801efde4  pop     rbp
0x1801efde5  retn
```
