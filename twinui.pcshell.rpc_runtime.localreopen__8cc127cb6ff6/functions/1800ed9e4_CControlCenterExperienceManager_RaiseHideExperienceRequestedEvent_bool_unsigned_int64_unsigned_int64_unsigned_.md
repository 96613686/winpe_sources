# CControlCenterExperienceManager::RaiseHideExperienceRequestedEvent(bool,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x1800ed9e4`
- end: `0x1800edead`
- name: `?RaiseHideExperienceRequestedEvent@CControlCenterExperienceManager@@AEAAJ_N_K11@Z`
- size: `1225`
- prototype: `int(CControlCenterExperienceManager *__hidden this, bool, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802a5344`

## callees

- `0x1800134f8`
- `0x18001f6e0`
- `0x1800237c8`
- `0x18002d770`
- `0x180047278`
- `0x180050424`
- `0x18005d940`
- `0x1800ecfc0`
- `0x1800ed8e0`
- `0x1800ed9e4`
- `0x1800ee174`
- `0x1800ef804`
- `0x1800ef904`
- `0x1800ef9dc`
- `0x1800efa3c`
- `0x1800efbe8`
- `0x1802ad5e4`
- `0x1802da728`
- `0x180356360`
- `0x1803f0840`
- `0x1803f12b4`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800eda97`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800edb46`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800edbe6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800edc63`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800edcdd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ede17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ede2d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ede43`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ede59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800eda97`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800edb46`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800edbe6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800edc63`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800edcdd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ede17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ede2d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ede43`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ede59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800eda80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800edb30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800edbd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800edc4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800edcc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800eda80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800edb30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800edbd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800edc4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800edcc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CControlCenterExperienceManager::RaiseHideExperienceRequestedEvent(
        CControlCenterExperienceManager *this,
        bool a2)
{
  HRESULT v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned int v9; // eax
  UINT32 v10; // edx
  HRESULT v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // edi
  __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  unsigned int v17; // eax
  UINT32 v18; // edx
  HRESULT v19; // eax
  unsigned __int64 v20; // rdi
  unsigned int v21; // eax
  UINT32 v22; // edx
  HRESULT v23; // eax
  unsigned int v24; // eax
  UINT32 v25; // edx
  HRESULT v26; // eax
  int v27; // eax
  struct Windows::Foundation::Collections::IPropertySet *v28; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v29; // rbx
  __int64 v30; // rax
  struct Windows::Foundation::Collections::IPropertySet *v31; // r9
  int v32; // eax
  int v34; // [rsp+20h] [rbp-E0h]
  struct Windows::Foundation::Collections::IPropertySet *v35; // [rsp+30h] [rbp-D0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v36; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  void **v39; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v40[272]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v41[8]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v42[48]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v39,
    "EM_RaiseHideExperienceRequestedEventActivity");
  v39 = &ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::`vftable';
  ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::StartActivity(
    (ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity *)&v39,
    a2,
    0,
    0,
    0);
  if ( !*((_QWORD *)this + 18) )
    goto LABEL_54;
  v36 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
         string,
         &v36);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B2,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\controlcenterexperiencemanager.cpp",
      (const char *)(unsigned int)v5,
      v34);
LABEL_47:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::~EM_RaiseHideExperienceRequestedEventActivity((ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity *)&v39);
    return v6;
  }
  v35 = v36;
  Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v35);
  string = 0;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( aSuppressanimat[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_54:
    ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::NoOp_ApplicationNotRunning((ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity *)&v39);
    goto LABEL_55;
  }
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v8);
  v10 = v9 - 1;
  if ( (unsigned int)v8 < v9 )
    v10 = v8;
  v11 = WindowsCreateStringReference(L"SuppressAnimations", v10, &hstringHeader, &string);
  if ( v11 < 0 )
    RaiseException(v11, 1u, 0, 0);
  LOBYTE(v13) = a2;
  v14 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(&v35, string, v12, v13);
  if ( v14 < 0 )
  {
    v15 = 949;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\controlcenterexperiencemanager.cpp",
      (const char *)(unsigned int)v14,
      v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v6 = v14;
    goto LABEL_47;
  }
  string = 0;
  v16 = -1;
  do
    ++v16;
  while ( aEdgegestureoff[v16] );
  if ( v16 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v17 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v18 = v17 - 1;
  if ( (unsigned int)v16 < v17 )
    v18 = v16;
  v19 = WindowsCreateStringReference(L"EdgeGestureOffset", v18, &hstringHeader, &string);
  if ( v19 < 0 )
    RaiseException(v19, 1u, 0, 0);
  v14 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned __int64>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v35,
          string);
  if ( v14 < 0 )
  {
    v15 = 950;
    goto LABEL_15;
  }
  string = 0;
  v20 = -1;
  do
    ++v20;
  while ( aInputanimation_1[v20] );
  if ( v20 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v21 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v20);
  v22 = v21 - 1;
  if ( (unsigned int)v20 < v21 )
    v22 = v20;
  v23 = WindowsCreateStringReference(L"InputAnimationProviderId", v22, &hstringHeader, &string);
  if ( v23 < 0 )
    RaiseException(v23, 1u, 0, 0);
  v14 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned __int64>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v35,
          string);
  if ( v14 < 0 )
  {
    v15 = 951;
    goto LABEL_15;
  }
  string = 0;
  do
    ++v7;
  while ( aInputanimation_3[v7] );
  if ( v7 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v24 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v7);
  v25 = v24 - 1;
  if ( (unsigned int)v7 < v24 )
    v25 = v7;
  v26 = WindowsCreateStringReference(L"InputAnimationSourceId", v25, &hstringHeader, &string);
  if ( v26 < 0 )
    RaiseException(v26, 1u, 0, 0);
  v27 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned __int64>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v35,
          string);
  v6 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B8,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\controlcenterexperiencemanager.cpp",
      (const char *)(unsigned int)v27,
      v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v28 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v39 = &ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::`vftable';
    wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v39);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v42);
    wil::details::shared_object<wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ControlCenterLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v41);
    wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ControlCenterLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ControlCenterLogging,_TlgReflectorTag_Param0IsProviderType>(v40);
    return v6;
  }
  v29 = v36;
  v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_180750300);
  v32 = CSingleViewShellExperience::Reactivate(
          (CControlCenterExperienceManager *)((char *)this + 120),
          *(HSTRING *)(v30 + 24),
          v29,
          v31);
  v6 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\controlcenterexperiencemanager.cpp",
      (const char *)(unsigned int)v32,
      v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    goto LABEL_47;
  }
  ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::EventRaised((ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity *)&v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
LABEL_55:
  wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v39, 0);
  ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::~EM_RaiseHideExperienceRequestedEventActivity((ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity *)&v39);
  return 0;
}

```

## disassembly

```asm
0x1800ed9e4  mov     [rsp-8+arg_10], rbx
0x1800ed9e9  push    rbp
0x1800ed9ea  push    rsi
0x1800ed9eb  push    rdi
0x1800ed9ec  push    r12
0x1800ed9ee  push    r13
0x1800ed9f0  push    r14
0x1800ed9f2  push    r15
0x1800ed9f4  lea     rbp, [rsp-0C0h]
0x1800ed9fc  sub     rsp, 1C0h
0x1800eda03  mov     rax, cs:__security_cookie
0x1800eda0a  xor     rax, rsp
0x1800eda0d  mov     [rbp+0F0h+var_40], rax
0x1800eda14  mov     r14b, dl
0x1800eda17  mov     r15, rcx
0x1800eda1a  lea     rdx, aEmRaisehideexp; "EM_RaiseHideExperienceRequestedEventAct"...
0x1800eda21  lea     rcx, [rsp+1F0h+var_190]
0x1800eda26  call    ??0?$ActivityBase@VControlCenterLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800eda2b  lea     rax, ??_7EM_RaiseHideExperienceRequestedEventActivity@ControlCenterTelemetry@ControlCenterUITelemetry@@6B@; const ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::`vftable'
0x1800eda32  mov     [rsp+1F0h+var_190], rax
0x1800eda37  xor     r12d, r12d
0x1800eda3a  mov     qword ptr [rsp+1F0h+var_1D0], r12; int
0x1800eda3f  xor     r9d, r9d; unsigned __int64
0x1800eda42  xor     r8d, r8d; unsigned __int64
0x1800eda45  mov     dl, r14b; bool
0x1800eda48  lea     rcx, [rsp+1F0h+var_190]; this
0x1800eda4d  call    ?StartActivity@EM_RaiseHideExperienceRequestedEventActivity@ControlCenterTelemetry@ControlCenterUITelemetry@@QEAAX_N_K11@Z; ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::StartActivity(bool,unsigned __int64,unsigned __int64,unsigned __int64)
0x1800eda52  nop
0x1800eda53  cmp     [r15+90h], r12
0x1800eda5a  jz      loc_1800EDE60
0x1800eda60  mov     [rsp+1F0h+var_1B8], r12
0x1800eda65  mov     [rsp+1F0h+string], r12
0x1800eda6a  lea     r9, [rsp+1F0h+string]; string
0x1800eda6f  lea     r8, [rsp+1F0h+hstringHeader]; hstringHeader
0x1800eda74  lea     edx, [r12+27h]; length
0x1800eda79  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x1800eda80  call    cs:__imp_WindowsCreateStringReference
0x1800eda86  test    eax, eax
0x1800eda88  jns     short loc_1800EDA9E
0x1800eda8a  xor     r9d, r9d; lpArguments
0x1800eda8d  xor     r8d, r8d; nNumberOfArguments
0x1800eda90  lea     edx, [r12+1]; dwExceptionFlags
0x1800eda95  mov     ecx, eax; dwExceptionCode
0x1800eda97  call    cs:__imp_RaiseException
0x1800eda9d  int     3; Trap to Debugger
0x1800eda9e  lea     rdx, [rsp+1F0h+var_1B8]
0x1800edaa3  mov     rcx, [rsp+1F0h+string]
0x1800edaa8  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x1800edaad  mov     ebx, eax
0x1800edaaf  test    eax, eax
0x1800edab1  jns     short loc_1800EDAD3
0x1800edab3  mov     rcx, [rbp+0F8h]; this
0x1800edaba  mov     r9d, eax; char *
0x1800edabd  lea     r8, aPcshellTwinuiE_23; "pcshell\\twinui\\experiencemanagers\\li"...
0x1800edac4  mov     edx, 3B2h; void *
0x1800edac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800edace  jmp     loc_1800EDDCA
0x1800edad3  mov     rax, [rsp+1F0h+var_1B8]
0x1800edad8  mov     [rsp+1F0h+var_1C0], rax
0x1800edadd  lea     rcx, [rsp+1F0h+var_1C0]
0x1800edae2  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x1800edae7  nop
0x1800edae8  mov     [rsp+1F0h+string], r12
0x1800edaed  mov     rsi, cs:off_1807094B0; "SuppressAnimations"
0x1800edaf4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800edaf8  mov     rdi, rbx
0x1800edafb  inc     rdi
0x1800edafe  cmp     [rsi+rdi*2], r12w
0x1800edb03  jnz     short loc_1800EDAFB
0x1800edb05  mov     r13d, 0FFFFFFFFh
0x1800edb0b  cmp     rdi, r13
0x1800edb0e  ja      loc_1800EDE4A
0x1800edb14  mov     ecx, edi; unsigned int
0x1800edb16  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800edb1b  lea     edx, [rax-1]
0x1800edb1e  cmp     edi, eax
0x1800edb20  cmovb   edx, edi; length
0x1800edb23  lea     r9, [rsp+1F0h+string]; string
0x1800edb28  lea     r8, [rsp+1F0h+hstringHeader]; hstringHeader
0x1800edb2d  mov     rcx, rsi; sourceString
0x1800edb30  call    cs:__imp_WindowsCreateStringReference
0x1800edb36  test    eax, eax
0x1800edb38  jns     short loc_1800EDB4D
0x1800edb3a  xor     r9d, r9d; lpArguments
0x1800edb3d  xor     r8d, r8d; nNumberOfArguments
0x1800edb40  lea     edx, [r9+1]; dwExceptionFlags
0x1800edb44  mov     ecx, eax; dwExceptionCode
0x1800edb46  call    cs:__imp_RaiseException
0x1800edb4c  nop
0x1800edb4d  mov     r9b, r14b
0x1800edb50  mov     rdx, [rsp+1F0h+string]
0x1800edb55  lea     rcx, [rsp+1F0h+var_1C0]
0x1800edb5a  call    ??$SetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJEPEAPEAUIInspectable@@@ZE@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uchar,IInspectable * *),uchar)
0x1800edb5f  mov     edi, eax
0x1800edb61  test    eax, eax
0x1800edb63  jns     short loc_1800EDB92
0x1800edb65  mov     edx, 3B5h; void *
0x1800edb6a  mov     rcx, [rbp+0F8h]; this
0x1800edb71  mov     r9d, edi; char *
0x1800edb74  lea     r8, aPcshellTwinuiE_23; "pcshell\\twinui\\experiencemanagers\\li"...
0x1800edb7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800edb80  nop
0x1800edb81  lea     rcx, [rsp+1F0h+var_1C0]
0x1800edb86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800edb8b  mov     ebx, edi
0x1800edb8d  jmp     loc_1800EDDCA
0x1800edb92  mov     [rsp+1F0h+string], r12
0x1800edb97  mov     rsi, cs:off_1807094B8; "EdgeGestureOffset"
0x1800edb9e  mov     rdi, rbx
0x1800edba1  inc     rdi
0x1800edba4  cmp     [rsi+rdi*2], r12w
0x1800edba9  jnz     short loc_1800EDBA1
0x1800edbab  cmp     rdi, r13
0x1800edbae  ja      loc_1800EDE34
0x1800edbb4  mov     ecx, edi; unsigned int
0x1800edbb6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800edbbb  lea     edx, [rax-1]
0x1800edbbe  cmp     edi, eax
0x1800edbc0  cmovb   edx, edi; length
0x1800edbc3  lea     r9, [rsp+1F0h+string]; string
0x1800edbc8  lea     r8, [rsp+1F0h+hstringHeader]; hstringHeader
0x1800edbcd  mov     rcx, rsi; sourceString
0x1800edbd0  call    cs:__imp_WindowsCreateStringReference
0x1800edbd6  test    eax, eax
0x1800edbd8  jns     short loc_1800EDBED
0x1800edbda  xor     r9d, r9d; lpArguments
0x1800edbdd  xor     r8d, r8d; nNumberOfArguments
0x1800edbe0  lea     edx, [r9+1]; dwExceptionFlags
0x1800edbe4  mov     ecx, eax; dwExceptionCode
0x1800edbe6  call    cs:__imp_RaiseException
0x1800edbec  nop
0x1800edbed  xor     r9d, r9d
0x1800edbf0  mov     rdx, [rsp+1F0h+string]; HSTRING
0x1800edbf5  lea     rcx, [rsp+1F0h+var_1C0]; this
0x1800edbfa  call    ??$SetValue@_K@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJ_KPEAPEAUIInspectable@@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned __int64>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(unsigned __int64,IInspectable * *),unsigned __int64)
0x1800edbff  mov     edi, eax
0x1800edc01  test    eax, eax
0x1800edc03  jns     short loc_1800EDC0F
0x1800edc05  mov     edx, 3B6h
0x1800edc0a  jmp     loc_1800EDB6A
0x1800edc0f  mov     [rsp+1F0h+string], r12
0x1800edc14  mov     rsi, cs:off_1807094C0; "InputAnimationProviderId"
0x1800edc1b  mov     rdi, rbx
0x1800edc1e  inc     rdi
0x1800edc21  cmp     [rsi+rdi*2], r12w
0x1800edc26  jnz     short loc_1800EDC1E
0x1800edc28  cmp     rdi, r13
0x1800edc2b  ja      loc_1800EDE1E
0x1800edc31  mov     ecx, edi; unsigned int
0x1800edc33  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800edc38  lea     edx, [rax-1]
0x1800edc3b  cmp     edi, eax
0x1800edc3d  cmovb   edx, edi; length
0x1800edc40  lea     r9, [rsp+1F0h+string]; string
0x1800edc45  lea     r8, [rsp+1F0h+hstringHeader]; hstringHeader
0x1800edc4a  mov     rcx, rsi; sourceString
0x1800edc4d  call    cs:__imp_WindowsCreateStringReference
0x1800edc53  test    eax, eax
0x1800edc55  jns     short loc_1800EDC6A
0x1800edc57  xor     r9d, r9d; lpArguments
0x1800edc5a  xor     r8d, r8d; nNumberOfArguments
0x1800edc5d  lea     edx, [r9+1]; dwExceptionFlags
0x1800edc61  mov     ecx, eax; dwExceptionCode
0x1800edc63  call    cs:__imp_RaiseException
0x1800edc69  nop
0x1800edc6a  xor     r9d, r9d
0x1800edc6d  mov     rdx, [rsp+1F0h+string]; HSTRING
0x1800edc72  lea     rcx, [rsp+1F0h+var_1C0]; this
0x1800edc77  call    ??$SetValue@_K@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJ_KPEAPEAUIInspectable@@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned __int64>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(unsigned __int64,IInspectable * *),unsigned __int64)
0x1800edc7c  mov     edi, eax
0x1800edc7e  test    eax, eax
0x1800edc80  jns     short loc_1800EDC8C
0x1800edc82  mov     edx, 3B7h
0x1800edc87  jmp     loc_1800EDB6A
0x1800edc8c  mov     [rsp+1F0h+string], r12
0x1800edc91  mov     rdi, cs:off_1807094A8; "InputAnimationSourceId"
0x1800edc98  inc     rbx
0x1800edc9b  cmp     [rdi+rbx*2], r12w
0x1800edca0  jnz     short loc_1800EDC98
0x1800edca2  cmp     rbx, r13
0x1800edca5  ja      loc_1800EDE08
0x1800edcab  mov     ecx, ebx; unsigned int
0x1800edcad  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800edcb2  lea     edx, [rax-1]
0x1800edcb5  cmp     ebx, eax
0x1800edcb7  cmovb   edx, ebx; length
0x1800edcba  lea     r9, [rsp+1F0h+string]; string
0x1800edcbf  lea     r8, [rsp+1F0h+hstringHeader]; hstringHeader
0x1800edcc4  mov     rcx, rdi; sourceString
0x1800edcc7  call    cs:__imp_WindowsCreateStringReference
0x1800edccd  test    eax, eax
0x1800edccf  jns     short loc_1800EDCE4
0x1800edcd1  xor     r9d, r9d; lpArguments
0x1800edcd4  xor     r8d, r8d; nNumberOfArguments
0x1800edcd7  lea     edx, [r9+1]; dwExceptionFlags
0x1800edcdb  mov     ecx, eax; dwExceptionCode
0x1800edcdd  call    cs:__imp_RaiseException
0x1800edce3  nop
0x1800edce4  xor     r9d, r9d
0x1800edce7  mov     rdx, [rsp+1F0h+string]; HSTRING
0x1800edcec  lea     rcx, [rsp+1F0h+var_1C0]; this
0x1800edcf1  call    ??$SetValue@_K@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJ_KPEAPEAUIInspectable@@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned __int64>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(unsigned __int64,IInspectable * *),unsigned __int64)
0x1800edcf6  mov     ebx, eax
0x1800edcf8  test    eax, eax
0x1800edcfa  jns     short loc_1800EDD76
0x1800edcfc  mov     rcx, [rbp+0F8h]; this
0x1800edd03  mov     r9d, eax; char *
0x1800edd06  lea     r8, aPcshellTwinuiE_23; "pcshell\\twinui\\experiencemanagers\\li"...
0x1800edd0d  mov     edx, 3B8h; void *
0x1800edd12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800edd17  nop
0x1800edd18  lea     rcx, [rsp+1F0h+var_1C0]
0x1800edd1d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800edd22  nop
0x1800edd23  mov     rcx, [rsp+1F0h+var_1B8]
0x1800edd28  test    rcx, rcx
0x1800edd2b  jz      short loc_1800EDD3F
0x1800edd2d  mov     [rsp+1F0h+var_1B8], r12
0x1800edd32  mov     rax, [rcx]
0x1800edd35  mov     rax, [rax+10h]
0x1800edd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edd3e  nop
0x1800edd3f  lea     rax, ??_7EM_RaiseHideExperienceRequestedEventActivity@ControlCenterTelemetry@ControlCenterUITelemetry@@6B@; const ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::`vftable'
0x1800edd46  mov     [rsp+1F0h+var_190], rax
0x1800edd4b  lea     rcx, [rsp+1F0h+var_190]
0x1800edd50  call    ?Destroy@?$ActivityBase@VControlCenterLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800edd55  lea     rcx, [rbp+0F0h+var_70]; this
0x1800edd5c  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800edd61  lea     rcx, [rbp+0F0h+var_78]
0x1800edd65  call    ?reset@?$shared_object@V?$ActivityData@VControlCenterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VControlCenterLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ControlCenterLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800edd6a  lea     rcx, [rsp+1F0h+var_188]
0x1800edd6f  call    ??1?$ActivityData@VControlCenterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VControlCenterLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ControlCenterLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ControlCenterLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800edd74  jmp     short loc_1800EDDDF
0x1800edd76  mov     rbx, [rsp+1F0h+var_1B8]
0x1800edd7b  lea     rdx, off_180750300; "HideExperienceRequested"
0x1800edd82  lea     rcx, [rsp+1F0h+hstringHeader]
0x1800edd87  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800edd8c  nop
0x1800edd8d  mov     r8, rbx; struct Windows::Foundation::Collections::IPropertySet *
0x1800edd90  mov     rdx, [rax+18h]; HSTRING
0x1800edd94  lea     rcx, [r15+78h]; this
0x1800edd98  call    ?Reactivate@CSingleViewShellExperience@@QEAAJPEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@Windows@@1@Z; CSingleViewShellExperience::Reactivate(HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *)
0x1800edd9d  mov     ebx, eax
0x1800edd9f  test    eax, eax
0x1800edda1  jns     short loc_1800EDDE6
0x1800edda3  mov     rcx, [rbp+0F8h]; this
0x1800eddaa  mov     r9d, eax; char *
0x1800eddad  lea     r8, aPcshellTwinuiE_23; "pcshell\\twinui\\experiencemanagers\\li"...
0x1800eddb4  mov     edx, 3B9h; void *
0x1800eddb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eddbe  nop
0x1800eddbf  lea     rcx, [rsp+1F0h+var_1C0]
0x1800eddc4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800eddc9  nop
0x1800eddca  lea     rcx, [rsp+1F0h+var_1B8]
0x1800eddcf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800eddd4  nop
0x1800eddd5  lea     rcx, [rsp+1F0h+var_190]; this
0x1800eddda  call    ??1EM_RaiseHideExperienceRequestedEventActivity@ControlCenterTelemetry@ControlCenterUITelemetry@@QEAA@XZ; ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::~EM_RaiseHideExperienceRequestedEventActivity(void)
0x1800edddf  mov     eax, ebx
0x1800edde1  jmp     loc_1800EDE83
0x1800edde6  lea     rcx, [rsp+1F0h+var_190]; this
0x1800eddeb  call    ?EventRaised@EM_RaiseHideExperienceRequestedEventActivity@ControlCenterTelemetry@ControlCenterUITelemetry@@QEAAXXZ; ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::EventRaised(void)
0x1800eddf0  nop
0x1800eddf1  lea     rcx, [rsp+1F0h+var_1C0]
0x1800eddf6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800eddfb  nop
0x1800eddfc  lea     rcx, [rsp+1F0h+var_1B8]
0x1800ede01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ede06  jmp     short loc_1800EDE6A
0x1800ede08  xor     r9d, r9d; lpArguments
0x1800ede0b  xor     r8d, r8d; nNumberOfArguments
0x1800ede0e  lea     edx, [r9+1]; dwExceptionFlags
0x1800ede12  mov     ecx, 80070216h; dwExceptionCode
0x1800ede17  call    cs:__imp_RaiseException
0x1800ede1d  int     3; Trap to Debugger
0x1800ede1e  xor     r9d, r9d; lpArguments
0x1800ede21  xor     r8d, r8d; nNumberOfArguments
0x1800ede24  lea     edx, [r9+1]; dwExceptionFlags
0x1800ede28  mov     ecx, 80070216h; dwExceptionCode
0x1800ede2d  call    cs:__imp_RaiseException
0x1800ede33  int     3; Trap to Debugger
0x1800ede34  xor     r9d, r9d; lpArguments
0x1800ede37  xor     r8d, r8d; nNumberOfArguments
0x1800ede3a  lea     edx, [r9+1]; dwExceptionFlags
0x1800ede3e  mov     ecx, 80070216h; dwExceptionCode
0x1800ede43  call    cs:__imp_RaiseException
0x1800ede49  int     3; Trap to Debugger
0x1800ede4a  xor     r9d, r9d; lpArguments
0x1800ede4d  xor     r8d, r8d; nNumberOfArguments
0x1800ede50  lea     edx, [r9+1]; dwExceptionFlags
0x1800ede54  mov     ecx, 80070216h; dwExceptionCode
0x1800ede59  call    cs:__imp_RaiseException
0x1800ede5f  nop
0x1800ede60  lea     rcx, [rsp+1F0h+var_190]; this
0x1800ede65  call    ?NoOp_ApplicationNotRunning@EM_RaiseHideExperienceRequestedEventActivity@ControlCenterTelemetry@ControlCenterUITelemetry@@QEAAXXZ; ControlCenterUITelemetry::ControlCenterTelemetry::EM_RaiseHideExperienceRequestedEventActivity::NoOp_ApplicationNotRunning(void)
0x1800ede6a  xor     edx, edx
0x1800ede6c  lea     rcx, [rsp+1F0h+var_190]
0x1800ede71  call    ?Stop@?$ActivityBase@VControlCenterLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ControlCenterLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800ede76  nop
  ... truncated ...
```
