# CQuickConnectExperienceManager::OnViewPropertiesChanging(CSingleViewShellExperience *)

- ea: `0x180411580`
- end: `0x180411afe`
- name: `?OnViewPropertiesChanging@CQuickConnectExperienceManager@@MEAAJPEAVCSingleViewShellExperience@@@Z`
- size: `1406`
- prototype: `int(CQuickConnectExperienceManager *__hidden this, struct CSingleViewShellExperience *)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x1800510f0`
- `0x18007b3e0`
- `0x1800d0708`
- `0x1800d1628`
- `0x1801b75c0`
- `0x1802cf010`
- `0x1803214b0`
- `0x18032174c`
- `0x180321abc`
- `0x180356360`
- `0x180403ab0`
- `0x18040fa90`
- `0x18040fc2c`
- `0x180410794`
- `0x1804107e8`
- `0x180411580`
- `0x1804121ac`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18041185d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18041196f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804119b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180411a8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18041185d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18041196f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1804119b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180411a8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1804119d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180411a24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180411a5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1804119d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180411a24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180411a5a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1804119ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180411a3e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180411a74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1804119ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180411a3e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180411a74`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180411762`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180411762`

## string_xrefs

- `0x18041164c`: `IsQuickConnectViewServiceReady`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CQuickConnectExperienceManager::OnViewPropertiesChanging(
        CQuickConnectExperienceManager *this,
        struct CSingleViewShellExperience *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, __int64, struct IInspectable **); // rbx
  bool v8; // r8
  bool v9; // r9
  HSTRING v10; // rbx
  HSTRING v11; // rax
  int Boolean; // eax
  __int64 v13; // rdx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v14; // rdx
  HWND v15; // rdi
  __int64 v16; // rdi
  void (__fastcall *v17)(__int64, __int64, struct IInspectable **); // rbx
  HSTRING *v18; // rsi
  bool v19; // r8
  bool v20; // r9
  HSTRING v21; // rbx
  HSTRING v22; // rax
  int v23; // eax
  __int64 v24; // rdi
  void (__fastcall *v25)(__int64, __int64, struct IInspectable **); // rbx
  HSTRING *v26; // rsi
  bool v27; // r8
  bool v28; // r9
  HSTRING v29; // rbx
  HSTRING v30; // rax
  int updated; // eax
  __int64 v32; // rdx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v34; // rax
  const WCHAR *v35; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v38[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  int v40; // [rsp+40h] [rbp-C0h]
  HSTRING *v41; // [rsp+48h] [rbp-B8h] BYREF
  struct IInspectable *v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v44; // [rsp+60h] [rbp-A0h] BYREF
  int v45; // [rsp+68h] [rbp-98h]
  HSTRING *v46; // [rsp+70h] [rbp-90h] BYREF
  int v47; // [rsp+78h] [rbp-88h]
  HSTRING *v48; // [rsp+80h] [rbp-80h] BYREF
  int v49; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-70h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-58h]
  _QWORD v52[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  wil::ActivityBase<QuickConnectLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<QuickConnectLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v52);
  v52[0] = &QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging::`vftable';
  QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging::StartActivity((QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging *)v52);
  v43 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
         (char *)a2 + 32,
         &v43);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v44 = 0;
    v45 = 0;
    v6 = v43;
    v7 = *(void (__fastcall **)(__int64, __int64, struct IInspectable **))(*(_QWORD *)v43 + 48LL);
    v41 = &v44;
    v42 = 0;
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"IsQuickConnectViewServiceReady",
      0x1Fu,
      0x1Eu);
    v7(v6, v51, &v42);
    v51 = 0;
    RoVariant::RoVariant((RoVariant *)&string, v42, v8, v9);
    v10 = string;
    string = 0;
    LODWORD(v6) = v40;
    v40 = 0;
    RoVariant::~RoVariant((RoVariant *)&string);
    v11 = v44;
    v44 = v10;
    string = v11;
    LODWORD(v11) = v45;
    v45 = v6;
    v40 = (int)v11;
    RoVariant::~RoVariant((RoVariant *)&string);
    if ( v44 )
    {
      v38[0] = 0;
      v41 = (HSTRING *)v44;
      LODWORD(v42) = v45;
      Boolean = RoVariant::Accessor::GetBoolean((RoVariant::Accessor *)&v41, v38);
      v5 = Boolean;
      if ( Boolean < 0 )
      {
        v13 = 692;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\quickconnectexperiencemanager.cpp",
          (const char *)(unsigned int)Boolean,
          bIgnoreCase);
LABEL_7:
        RoVariant::~RoVariant((RoVariant *)&v44);
        goto LABEL_30;
      }
      if ( v38[0] )
      {
        QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging::ExperienceManager_OnViewPropertiesChanging_IsQuickConnectViewServiceReady((QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging *)v52);
        v15 = ExperienceManagerUtils::WindowFromViewWrapper(*((ExperienceManagerUtils **)this + 6), v14);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 272);
        Boolean = CoreQueryWindowService(
                    v15,
                    &GUID_4aaaff25_9e49_4ab5_b2af_c798c01c536c,
                    &GUID_4aaaff25_9e49_4ab5_b2af_c798c01c536c,
                    (char *)this + 272);
        v5 = Boolean;
        if ( Boolean < 0 )
        {
          v13 = 705;
          goto LABEL_6;
        }
        Boolean = CQuickConnectExperienceManager::CheckAndPopulateContact((CQuickConnectExperienceManager *)((char *)this - 48));
        v5 = Boolean;
        if ( Boolean < 0 )
        {
          v13 = 708;
          goto LABEL_6;
        }
      }
    }
    v46 = 0;
    v47 = 0;
    v16 = v43;
    v17 = *(void (__fastcall **)(__int64, __int64, struct IInspectable **))(*(_QWORD *)v43 + 48LL);
    v41 = (HSTRING *)&v46;
    v42 = 0;
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Title", 6u, 5u);
    v17(v16, v51, &v42);
    v51 = 0;
    v18 = v41;
    RoVariant::RoVariant((RoVariant *)&string, v42, v19, v20);
    v21 = string;
    string = 0;
    LODWORD(v16) = v40;
    v40 = 0;
    RoVariant::~RoVariant((RoVariant *)&string);
    v22 = *v18;
    *v18 = v21;
    string = v22;
    LODWORD(v22) = *((_DWORD *)v18 + 2);
    *((_DWORD *)v18 + 2) = v16;
    v40 = (int)v22;
    RoVariant::~RoVariant((RoVariant *)&string);
    if ( v46 )
    {
      v41 = v46;
      LODWORD(v42) = v47;
      WindowsDeleteString(*((HSTRING *)this + 41));
      *((_QWORD *)this + 41) = 0;
      v23 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v41, (HSTRING *)this + 41);
      v5 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2CD,
          (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\quickconnectexperiencemanager.cpp",
          (const char *)(unsigned int)v23,
          bIgnoreCase);
LABEL_16:
        RoVariant::~RoVariant((RoVariant *)&v46);
        goto LABEL_7;
      }
    }
    v48 = 0;
    v49 = 0;
    v24 = v43;
    v25 = *(void (__fastcall **)(__int64, __int64, struct IInspectable **))(*(_QWORD *)v43 + 48LL);
    v41 = (HSTRING *)&v48;
    v42 = 0;
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"EventType", 0xAu, 9u);
    v25(v24, v51, &v42);
    v51 = 0;
    v26 = v41;
    RoVariant::RoVariant((RoVariant *)&string, v42, v27, v28);
    v29 = string;
    string = 0;
    LODWORD(v24) = v40;
    v40 = 0;
    RoVariant::~RoVariant((RoVariant *)&string);
    v30 = *v26;
    *v26 = v29;
    string = v30;
    LODWORD(v30) = *((_DWORD *)v26 + 2);
    *((_DWORD *)v26 + 2) = v24;
    v40 = (int)v30;
    RoVariant::~RoVariant((RoVariant *)&string);
    if ( v48 )
    {
      string = 0;
      v41 = v48;
      LODWORD(v42) = v49;
      WindowsDeleteString(0);
      string = 0;
      updated = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v41, &string);
      v5 = updated;
      if ( updated < 0 )
      {
        v32 = 728;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\quickconnectexperiencemanager.cpp",
          (const char *)(unsigned int)updated,
          bIgnoreCase);
        WindowsDeleteString(string);
        string = 0;
        RoVariant::~RoVariant((RoVariant *)&v48);
        goto LABEL_16;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"WindowResize", -1, 0) == 2 )
      {
        QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging::ExperienceManager_OnViewPropertiesChanging_WindowResize((QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging *)v52);
        updated = CQuickConnectExperienceManager::UpdateWindowPosition(
                    (CQuickConnectExperienceManager *)((char *)this - 48),
                    a2);
        v5 = updated;
        if ( updated < 0 )
        {
          v32 = 733;
          goto LABEL_20;
        }
      }
      else
      {
        v34 = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(v34, -1, L"DisableReturnFocus", -1, 0) == 2 )
        {
          *((_BYTE *)this + 368) = 1;
        }
        else
        {
          v35 = WindowsGetStringRawBuffer(string, 0);
          if ( CompareStringOrdinal(v35, -1, L"EnableReturnFocus", -1, 0) == 2 )
            *((_BYTE *)this + 368) = 0;
        }
      }
      WindowsDeleteString(string);
    }
    wil::ActivityBase<QuickConnectLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v52);
    RoVariant::~RoVariant((RoVariant *)&v48);
    RoVariant::~RoVariant((RoVariant *)&v46);
    RoVariant::~RoVariant((RoVariant *)&v44);
    v5 = 0;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2AA,
    (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\quickconnectexperiencemanager.cpp",
    (const char *)(unsigned int)v4,
    bIgnoreCase);
LABEL_30:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging::~ExperienceManager_OnViewPropertiesChanging((QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging *)v52);
  return v5;
}

```

## disassembly

```asm
0x180411580  mov     [rsp-8+arg_10], rbx
0x180411585  mov     [rsp-8+arg_18], rsi
0x18041158a  push    rbp
0x18041158b  push    rdi
0x18041158c  push    r12
0x18041158e  push    r14
0x180411590  push    r15
0x180411592  lea     rbp, [rsp-110h]
0x18041159a  sub     rsp, 210h
0x1804115a1  mov     rax, cs:__security_cookie
0x1804115a8  xor     rax, rsp
0x1804115ab  mov     [rbp+130h+var_30], rax
0x1804115b2  mov     r15, rdx
0x1804115b5  mov     r14, rcx
0x1804115b8  lea     rdx, aExperiencemana; "ExperienceManager_OnViewPropertiesChang"...
0x1804115bf  lea     rcx, [rbp+130h+var_180]; struct wil::details::IFailureCallback *
0x1804115c3  call    ??0?$ActivityBase@VQuickConnectLoggingProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<QuickConnectLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<QuickConnectLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1804115c8  lea     rax, ??_7ExperienceManager_OnViewPropertiesChanging@QuickConnectTelemetry@@6B@; const QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging::`vftable'
0x1804115cf  mov     [rbp+130h+var_180], rax
0x1804115d3  lea     rcx, [rbp+130h+var_180]; this
0x1804115d7  call    ?StartActivity@ExperienceManager_OnViewPropertiesChanging@QuickConnectTelemetry@@QEAAXXZ; QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging::StartActivity(void)
0x1804115dc  nop
0x1804115dd  xor     r12d, r12d
0x1804115e0  mov     [rsp+230h+var_1D8], r12
0x1804115e5  lea     rcx, [r15+20h]
0x1804115e9  lea     rdx, [rsp+230h+var_1D8]
0x1804115ee  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1804115f3  mov     ebx, eax
0x1804115f5  test    eax, eax
0x1804115f7  jns     short loc_180411619
0x1804115f9  mov     rcx, [rbp+138h]; this
0x180411600  mov     r9d, eax; char *
0x180411603  lea     r8, aPcshellTwinuiE_18; "pcshell\\twinui\\experiencemanagers\\li"...
0x18041160a  mov     edx, 2AAh; void *
0x18041160f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180411614  jmp     loc_180411ABD
0x180411619  mov     [rsp+230h+var_1D0], r12
0x18041161e  mov     [rsp+230h+var_1C8], r12d
0x180411623  mov     rdi, [rsp+230h+var_1D8]
0x180411628  mov     rax, [rdi]
0x18041162b  mov     rbx, [rax+30h]
0x18041162f  lea     rax, [rsp+230h+var_1D0]
0x180411634  mov     [rsp+230h+var_1E8], rax
0x180411639  mov     [rsp+230h+var_1E0], r12
0x18041163e  mov     [rbp+130h+var_188], r12
0x180411642  mov     r9d, 1Eh; unsigned int
0x180411648  lea     r8d, [r9+1]; unsigned int
0x18041164c  lea     rdx, aIsquickconnect; "IsQuickConnectViewServiceReady"
0x180411653  lea     rcx, [rbp+130h+hstringHeader]; hstringHeader
0x180411657  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18041165c  nop
0x18041165d  lea     r8, [rsp+230h+var_1E0]
0x180411662  mov     rdx, [rbp+130h+var_188]
0x180411666  mov     rcx, rdi
0x180411669  mov     rax, rbx
0x18041166c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180411671  nop
0x180411672  mov     [rbp+130h+var_188], r12
0x180411676  mov     rsi, [rsp+230h+var_1E8]
0x18041167b  mov     rdx, [rsp+230h+var_1E0]; struct IInspectable *
0x180411680  lea     rcx, [rsp+230h+string]; this
0x180411685  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x18041168a  mov     rbx, [rsp+230h+string]
0x18041168f  mov     [rsp+230h+string], r12
0x180411694  mov     edi, [rsp+230h+var_1F0]
0x180411698  mov     [rsp+230h+var_1F0], r12d
0x18041169d  lea     rcx, [rsp+230h+string]; this
0x1804116a2  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1804116a7  mov     rax, [rsi]
0x1804116aa  mov     [rsi], rbx
0x1804116ad  mov     [rsp+230h+string], rax
0x1804116b2  mov     eax, [rsi+8]
0x1804116b5  mov     [rsi+8], edi
0x1804116b8  mov     [rsp+230h+var_1F0], eax
0x1804116bc  lea     rcx, [rsp+230h+string]; this
0x1804116c1  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1804116c6  nop
0x1804116c7  mov     rax, [rsp+230h+var_1D0]
0x1804116cc  test    rax, rax
0x1804116cf  jz      loc_18041178E
0x1804116d5  mov     [rsp+230h+var_200], r12b
0x1804116da  mov     [rsp+230h+var_1E8], rax
0x1804116df  mov     eax, [rsp+230h+var_1C8]
0x1804116e3  mov     dword ptr [rsp+230h+var_1E0], eax
0x1804116e7  lea     rdx, [rsp+230h+var_200]; unsigned __int8 *
0x1804116ec  lea     rcx, [rsp+230h+var_1E8]; this
0x1804116f1  call    ?GetBoolean@Accessor@RoVariant@@QEBAJPEAE@Z; RoVariant::Accessor::GetBoolean(uchar *)
0x1804116f6  mov     ebx, eax
0x1804116f8  test    eax, eax
0x1804116fa  jns     short loc_180411727
0x1804116fc  mov     edx, 2B4h; void *
0x180411701  mov     rcx, [rbp+138h]; this
0x180411708  mov     r9d, eax; char *
0x18041170b  lea     r8, aPcshellTwinuiE_18; "pcshell\\twinui\\experiencemanagers\\li"...
0x180411712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180411717  nop
0x180411718  lea     rcx, [rsp+230h+var_1D0]; this
0x18041171d  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180411722  jmp     loc_180411ABD
0x180411727  cmp     [rsp+230h+var_200], r12b
0x18041172c  jz      short loc_18041178E
0x18041172e  lea     rcx, [rbp+130h+var_180]; this
0x180411732  call    ?ExperienceManager_OnViewPropertiesChanging_IsQuickConnectViewServiceReady@ExperienceManager_OnViewPropertiesChanging@QuickConnectTelemetry@@QEAAXXZ; QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging::ExperienceManager_OnViewPropertiesChanging_IsQuickConnectViewServiceReady(void)
0x180411737  mov     rcx, [r14+30h]; this
0x18041173b  call    ?WindowFromViewWrapper@ExperienceManagerUtils@@YAPEAUHWND__@@PEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; ExperienceManagerUtils::WindowFromViewWrapper(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x180411740  mov     rdi, rax
0x180411743  lea     rbx, [r14+110h]
0x18041174a  mov     rcx, rbx
0x18041174d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180411752  mov     r9, rbx
0x180411755  lea     rdx, _GUID_4aaaff25_9e49_4ab5_b2af_c798c01c536c
0x18041175c  mov     r8, rdx
0x18041175f  mov     rcx, rdi
0x180411762  call    cs:__imp_CoreQueryWindowService
0x180411768  mov     ebx, eax
0x18041176a  test    eax, eax
0x18041176c  jns     short loc_180411775
0x18041176e  mov     edx, 2C1h
0x180411773  jmp     short loc_180411701
0x180411775  lea     rcx, [r14-30h]; this
0x180411779  call    ?CheckAndPopulateContact@CQuickConnectExperienceManager@@AEAAJXZ; CQuickConnectExperienceManager::CheckAndPopulateContact(void)
0x18041177e  mov     ebx, eax
0x180411780  test    eax, eax
0x180411782  jns     short loc_18041178E
0x180411784  mov     edx, 2C4h
0x180411789  jmp     loc_180411701
0x18041178e  mov     [rsp+230h+var_1C0], r12
0x180411793  mov     [rsp+230h+var_1B8], r12d
0x180411798  mov     rdi, [rsp+230h+var_1D8]
0x18041179d  mov     rax, [rdi]
0x1804117a0  mov     rbx, [rax+30h]
0x1804117a4  lea     rax, [rsp+230h+var_1C0]
0x1804117a9  mov     [rsp+230h+var_1E8], rax
0x1804117ae  mov     [rsp+230h+var_1E0], r12
0x1804117b3  mov     [rbp+130h+var_188], r12
0x1804117b7  mov     r9d, 5; unsigned int
0x1804117bd  lea     r8d, [r9+1]; unsigned int
0x1804117c1  lea     rdx, aTitle; "Title"
0x1804117c8  lea     rcx, [rbp+130h+hstringHeader]; hstringHeader
0x1804117cc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1804117d1  nop
0x1804117d2  lea     r8, [rsp+230h+var_1E0]
0x1804117d7  mov     rdx, [rbp+130h+var_188]
0x1804117db  mov     rcx, rdi
0x1804117de  mov     rax, rbx
0x1804117e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804117e6  nop
0x1804117e7  mov     [rbp+130h+var_188], r12
0x1804117eb  mov     rsi, [rsp+230h+var_1E8]
0x1804117f0  mov     rdx, [rsp+230h+var_1E0]; struct IInspectable *
0x1804117f5  lea     rcx, [rsp+230h+string]; this
0x1804117fa  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x1804117ff  mov     rbx, [rsp+230h+string]
0x180411804  mov     [rsp+230h+string], r12
0x180411809  mov     edi, [rsp+230h+var_1F0]
0x18041180d  mov     [rsp+230h+var_1F0], r12d
0x180411812  lea     rcx, [rsp+230h+string]; this
0x180411817  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18041181c  mov     rax, [rsi]
0x18041181f  mov     [rsi], rbx
0x180411822  mov     [rsp+230h+string], rax
0x180411827  mov     eax, [rsi+8]
0x18041182a  mov     [rsi+8], edi
0x18041182d  mov     [rsp+230h+var_1F0], eax
0x180411831  lea     rcx, [rsp+230h+string]; this
0x180411836  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18041183b  nop
0x18041183c  mov     rax, [rsp+230h+var_1C0]
0x180411841  test    rax, rax
0x180411844  jz      short loc_1804118A4
0x180411846  mov     [rsp+230h+var_1E8], rax
0x18041184b  mov     eax, [rsp+230h+var_1B8]
0x18041184f  mov     dword ptr [rsp+230h+var_1E0], eax
0x180411853  lea     rbx, [r14+148h]
0x18041185a  mov     rcx, [rbx]; string
0x18041185d  call    cs:__imp_WindowsDeleteString
0x180411863  mov     [rbx], r12
0x180411866  mov     rdx, rbx; HSTRING *
0x180411869  lea     rcx, [rsp+230h+var_1E8]; this
0x18041186e  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x180411873  mov     ebx, eax
0x180411875  test    eax, eax
0x180411877  jns     short loc_1804118A4
0x180411879  mov     rcx, [rbp+138h]; this
0x180411880  mov     r9d, eax; char *
0x180411883  lea     r8, aPcshellTwinuiE_18; "pcshell\\twinui\\experiencemanagers\\li"...
0x18041188a  mov     edx, 2CDh; void *
0x18041188f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180411894  nop
0x180411895  lea     rcx, [rsp+230h+var_1C0]; this
0x18041189a  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18041189f  jmp     loc_180411718
0x1804118a4  mov     [rbp+130h+var_1B0], r12
0x1804118a8  mov     [rbp+130h+var_1A8], r12d
0x1804118ac  mov     rdi, [rsp+230h+var_1D8]
0x1804118b1  mov     rax, [rdi]
0x1804118b4  mov     rbx, [rax+30h]
0x1804118b8  lea     rax, [rbp+130h+var_1B0]
0x1804118bc  mov     [rsp+230h+var_1E8], rax
0x1804118c1  mov     [rsp+230h+var_1E0], r12
0x1804118c6  mov     [rbp+130h+var_188], r12
0x1804118ca  mov     r9d, 9; unsigned int
0x1804118d0  lea     r8d, [r9+1]; unsigned int
0x1804118d4  lea     rdx, aEventtype; "EventType"
0x1804118db  lea     rcx, [rbp+130h+hstringHeader]; hstringHeader
0x1804118df  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1804118e4  nop
0x1804118e5  lea     r8, [rsp+230h+var_1E0]
0x1804118ea  mov     rdx, [rbp+130h+var_188]
0x1804118ee  mov     rcx, rdi
0x1804118f1  mov     rax, rbx
0x1804118f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804118f9  nop
0x1804118fa  mov     [rbp+130h+var_188], r12
0x1804118fe  mov     rsi, [rsp+230h+var_1E8]
0x180411903  mov     rdx, [rsp+230h+var_1E0]; struct IInspectable *
0x180411908  lea     rcx, [rsp+230h+string]; this
0x18041190d  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x180411912  mov     rbx, [rsp+230h+string]
0x180411917  mov     [rsp+230h+string], r12
0x18041191c  mov     edi, [rsp+230h+var_1F0]
0x180411920  mov     [rsp+230h+var_1F0], r12d
0x180411925  lea     rcx, [rsp+230h+string]; this
0x18041192a  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18041192f  mov     rax, [rsi]
0x180411932  mov     [rsi], rbx
0x180411935  mov     [rsp+230h+string], rax
0x18041193a  mov     eax, [rsi+8]
0x18041193d  mov     [rsi+8], edi
0x180411940  mov     [rsp+230h+var_1F0], eax
0x180411944  lea     rcx, [rsp+230h+string]; this
0x180411949  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18041194e  nop
0x18041194f  mov     rax, [rbp+130h+var_1B0]
0x180411953  test    rax, rax
0x180411956  jz      loc_180411A91
0x18041195c  mov     [rsp+230h+string], r12
0x180411961  mov     [rsp+230h+var_1E8], rax
0x180411966  mov     eax, [rbp+130h+var_1A8]
0x180411969  mov     dword ptr [rsp+230h+var_1E0], eax
0x18041196d  xor     ecx, ecx; string
0x18041196f  call    cs:__imp_WindowsDeleteString
0x180411975  mov     [rsp+230h+string], r12
0x18041197a  lea     rdx, [rsp+230h+string]; HSTRING *
0x18041197f  lea     rcx, [rsp+230h+var_1E8]; this
0x180411984  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x180411989  mov     ebx, eax
0x18041198b  test    eax, eax
0x18041198d  jns     short loc_1804119C9
0x18041198f  mov     edx, 2D8h; void *
0x180411994  lea     r8, aPcshellTwinuiE_18; "pcshell\\twinui\\experiencemanagers\\li"...
0x18041199b  mov     r9d, eax; char *
0x18041199e  mov     rcx, [rbp+138h]; this
0x1804119a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804119aa  nop
0x1804119ab  mov     rcx, [rsp+230h+string]; string
0x1804119b0  call    cs:__imp_WindowsDeleteString
0x1804119b6  mov     [rsp+230h+string], r12
0x1804119bb  lea     rcx, [rbp+130h+var_1B0]; this
0x1804119bf  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1804119c4  jmp     loc_180411895
0x1804119c9  xor     edx, edx; length
0x1804119cb  mov     rcx, [rsp+230h+string]; string
0x1804119d0  call    cs:__imp_WindowsGetStringRawBuffer
0x1804119d6  mov     [rsp+230h+bIgnoreCase], r12d; bIgnoreCase
0x1804119db  or      ebx, 0FFFFFFFFh
0x1804119de  mov     r9d, ebx; cchCount2
0x1804119e1  lea     r8, aWindowresize; "WindowResize"
0x1804119e8  mov     edx, ebx; cchCount1
0x1804119ea  mov     rcx, rax; lpString1
0x1804119ed  call    cs:__imp_CompareStringOrdinal
0x1804119f3  cmp     eax, 2
0x1804119f6  jnz     short loc_180411A1D
0x1804119f8  lea     rcx, [rbp+130h+var_180]; this
0x1804119fc  call    ?ExperienceManager_OnViewPropertiesChanging_WindowResize@ExperienceManager_OnViewPropertiesChanging@QuickConnectTelemetry@@QEAAXXZ; QuickConnectTelemetry::ExperienceManager_OnViewPropertiesChanging::ExperienceManager_OnViewPropertiesChanging_WindowResize(void)
0x180411a01  lea     rcx, [r14-30h]; this
0x180411a05  mov     rdx, r15; struct CSingleViewShellExperience *
0x180411a08  call    ?UpdateWindowPosition@CQuickConnectExperienceManager@@AEAAJPEAVCSingleViewShellExperience@@@Z; CQuickConnectExperienceManager::UpdateWindowPosition(CSingleViewShellExperience *)
0x180411a0d  mov     ebx, eax
0x180411a0f  test    eax, eax
0x180411a11  jns     short loc_180411A86
0x180411a13  mov     edx, 2DDh
0x180411a18  jmp     loc_180411994
0x180411a1d  xor     edx, edx; length
0x180411a1f  mov     rcx, [rsp+230h+string]; string
0x180411a24  call    cs:__imp_WindowsGetStringRawBuffer
0x180411a2a  mov     [rsp+230h+bIgnoreCase], r12d; bIgnoreCase
0x180411a2f  mov     r9d, ebx; cchCount2
0x180411a32  lea     r8, aDisablereturnf; "DisableReturnFocus"
0x180411a39  mov     edx, ebx; cchCount1
0x180411a3b  mov     rcx, rax; lpString1
0x180411a3e  call    cs:__imp_CompareStringOrdinal
0x180411a44  cmp     eax, 2
0x180411a47  jnz     short loc_180411A53
0x180411a49  mov     byte ptr [r14+170h], 1
0x180411a51  jmp     short loc_180411A86
0x180411a53  xor     edx, edx; length
0x180411a55  mov     rcx, [rsp+230h+string]; string
0x180411a5a  call    cs:__imp_WindowsGetStringRawBuffer
0x180411a60  mov     [rsp+230h+bIgnoreCase], r12d; bIgnoreCase
  ... truncated ...
```
