# ExperienceManagerUtils::RaiseReactivatedEvent(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,ulong,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180050558`
- end: `0x180050913`
- name: `?RaiseReactivatedEvent@ExperienceManagerUtils@@YAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@KPEAUHSTRING__@@11PEAUIPropertySet@Collections@Foundation@6@2@Z`
- size: `955`
- prototype: `__int64 __usercall@<rax>(ExperienceManagerUtils *__hidden this@<rcx>, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *@<rdx>, unsigned int@<r8d>, HSTRING@<r9>, HSTRING, HSTRING, struct Windows::Foundation::Collections::IPropertySet *, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004828c`
- `0x180049368`
- `0x180050424`

## callees

- `0x1800134f8`
- `0x18001f6e0`
- `0x1800237c8`
- `0x18004daa0`
- `0x180050558`
- `0x18005091c`
- `0x180050ff8`
- `0x1800510f0`
- `0x180051190`
- `0x18017ec94`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180050634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800506fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180050634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800506fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800506e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005077d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800507b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800506e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005077d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800507b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800505a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800505b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800505c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800505a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800505b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800505c1`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180050666`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180050666`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ExperienceManagerUtils::RaiseReactivatedEvent(
        ExperienceManagerUtils *this,
        struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING string,
        HSTRING a6)
{
  const unsigned __int16 *StringRawBuffer; // rsi
  const unsigned __int16 *v10; // rdi
  const unsigned __int16 *v11; // rbx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v12; // rdx
  HWND v13; // rsi
  HRESULT v14; // eax
  int v15; // ebx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING, int *); // rbx
  int v19; // eax
  __int64 v20; // rcx
  HSTRING v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v31; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING newString; // [rsp+30h] [rbp-D0h] BYREF
  HRESULT v33; // [rsp+38h] [rbp-C8h]
  unsigned int v34; // [rsp+40h] [rbp-C0h]
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  HWND v36; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v37; // [rsp+58h] [rbp-A8h] BYREF
  HRESULT v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v41[43]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v42[42]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  v34 = (unsigned int)a2;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v10 = WindowsGetStringRawBuffer(a4, 0);
  v11 = WindowsGetStringRawBuffer(a3, 0);
  wil::ActivityBase<SingleViewExperienceLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SingleViewExperienceLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v42);
  v42[0] = &SingleViewExperienceTelemetry::Reactivate::`vftable';
  SingleViewExperienceTelemetry::Reactivate::StartActivity(
    (SingleViewExperienceTelemetry::Reactivate *)v42,
    v11,
    v10,
    StringRawBuffer);
  if ( !this || (v13 = ExperienceManagerUtils::WindowFromViewWrapper(this, v12)) == 0 )
  {
    v15 = -2147023496;
    goto LABEL_16;
  }
  WindowsDeleteString(0);
  newString = 0;
  v14 = WindowsDuplicateString(string, &newString);
  v15 = v14;
  v33 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\experiencemanagerutils.cpp",
      (const char *)(unsigned int)v14,
      v30[0]);
LABEL_18:
    WindowsDeleteString(newString);
    newString = 0;
    goto LABEL_16;
  }
  *(_QWORD *)v30 = 0;
  if ( a6 )
  {
    v31 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v16 = RoCreatePropertySetSerializer(&v31);
    v15 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\experiencemanagerutils.cpp",
        (const char *)(unsigned int)v16,
        v30[0]);
      v26 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v27 = *(_QWORD *)v30;
      if ( *(_QWORD *)v30 )
      {
        *(_QWORD *)v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      goto LABEL_18;
    }
    v17 = v31;
    v18 = *(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v31 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    v19 = v18(v17, a6, v30);
    v15 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\experiencemanagerutils.cpp",
        (const char *)(unsigned int)v19,
        v30[0]);
      v28 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = *(_QWORD *)v30;
      if ( *(_QWORD *)v30 )
      {
        *(_QWORD *)v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      goto LABEL_18;
    }
    v20 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v15 = v33;
  }
  v35 = 0;
  v36 = v13;
  v37 = 0;
  v38 = v15;
  if ( v15 >= 0 )
  {
    v21 = newString;
    WindowsDeleteString(0);
    v37 = 0;
    v38 = WindowsDuplicateString(v21, &v37);
  }
  v39 = *(_QWORD *)v30;
  Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v39);
  v40 = v35;
  Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v40);
  wil::ActivityBase<SingleViewExperienceLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SingleViewExperienceLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v41,
    v42);
  v41[0] = &SingleViewExperienceTelemetry::Reactivate::`vftable';
  v15 = Windows::Internal::ComTaskPool::QueueTask__lambda_b534361c50cb4958853f48f5e7b1e06a___(v23, v22, v34, &v36);
  SingleViewExperienceTelemetry::Reactivate::~Reactivate((SingleViewExperienceTelemetry::Reactivate *)v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  WindowsDeleteString(v37);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\experiencemanagerutils.cpp",
      (const char *)(unsigned int)v15,
      v30[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    goto LABEL_18;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v24 = *(_QWORD *)v30;
  if ( *(_QWORD *)v30 )
  {
    *(_QWORD *)v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  WindowsDeleteString(newString);
  newString = 0;
  v15 = 0;
LABEL_16:
  SingleViewExperienceTelemetry::Reactivate::~Reactivate((SingleViewExperienceTelemetry::Reactivate *)v42);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180050558  push    rbp
0x18005055a  push    rbx
0x18005055b  push    rsi
0x18005055c  push    rdi
0x18005055d  push    r12
0x18005055f  push    r13
0x180050561  push    r14
0x180050563  push    r15
0x180050565  lea     rbp, [rsp-238h]
0x18005056d  sub     rsp, 338h
0x180050574  mov     rax, cs:__security_cookie
0x18005057b  xor     rax, rsp
0x18005057e  mov     [rbp+270h+var_50], rax
0x180050585  mov     rbx, r9
0x180050588  mov     r14, r8
0x18005058b  mov     [rsp+370h+var_330], edx
0x18005058f  mov     r12, rcx
0x180050592  mov     r13, [rbp+270h+string]
0x180050599  mov     r15, [rbp+270h+arg_28]
0x1800505a0  xor     edx, edx; length
0x1800505a2  mov     rcx, r13; string
0x1800505a5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800505ab  mov     rsi, rax
0x1800505ae  xor     edx, edx; length
0x1800505b0  mov     rcx, rbx; string
0x1800505b3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800505b9  mov     rdi, rax
0x1800505bc  xor     edx, edx; length
0x1800505be  mov     rcx, r14; string
0x1800505c1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800505c7  mov     rbx, rax
0x1800505ca  lea     rcx, [rbp+270h+var_1A0]; struct wil::details::IFailureCallback *
0x1800505d1  call    ??0?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SingleViewExperienceLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800505d6  lea     rax, ??_7Reactivate@SingleViewExperienceTelemetry@@6B@; const SingleViewExperienceTelemetry::Reactivate::`vftable'
0x1800505dd  mov     [rbp+270h+var_1A0], rax
0x1800505e4  mov     r9, rsi; unsigned __int16 *
0x1800505e7  mov     r8, rdi; unsigned __int16 *
0x1800505ea  mov     rdx, rbx; unsigned __int16 *
0x1800505ed  lea     rcx, [rbp+270h+var_1A0]; this
0x1800505f4  call    ?StartActivity@Reactivate@SingleViewExperienceTelemetry@@QEAAXPEBG00@Z; SingleViewExperienceTelemetry::Reactivate::StartActivity(ushort const *,ushort const *,ushort const *)
0x1800505f9  nop
0x1800505fa  xor     r14d, r14d
0x1800505fd  test    r12, r12
0x180050600  jz      loc_180050908
0x180050606  mov     rcx, r12; this
0x180050609  call    ?WindowFromViewWrapper@ExperienceManagerUtils@@YAPEAUHWND__@@PEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; ExperienceManagerUtils::WindowFromViewWrapper(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x18005060e  mov     rsi, rax
0x180050611  test    rax, rax
0x180050614  jz      loc_180050908
0x18005061a  mov     [rsp+370h+newString], r14
0x18005061f  xor     ecx, ecx; string
0x180050621  call    cs:__imp_WindowsDeleteString
0x180050627  mov     [rsp+370h+newString], r14
0x18005062c  lea     rdx, [rsp+370h+newString]; newString
0x180050631  mov     rcx, r13; string
0x180050634  call    cs:__imp_WindowsDuplicateString
0x18005063a  mov     ebx, eax
0x18005063c  mov     [rsp+370h+var_338], eax
0x180050640  test    eax, eax
0x180050642  js      loc_1800507F6
0x180050648  mov     qword ptr [rsp+370h+var_350], r14; int
0x18005064d  test    r15, r15
0x180050650  jz      short loc_1800506C9
0x180050652  mov     [rsp+370h+var_348], r14
0x180050657  lea     rcx, [rsp+370h+var_348]
0x18005065c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050661  lea     rcx, [rsp+370h+var_348]
0x180050666  call    cs:__imp_RoCreatePropertySetSerializer
0x18005066c  mov     ebx, eax
0x18005066e  test    eax, eax
0x180050670  js      loc_180050824
0x180050676  mov     rdi, [rsp+370h+var_348]
0x18005067b  mov     rax, [rdi]
0x18005067e  mov     rbx, [rax+30h]
0x180050682  lea     rcx, [rsp+370h+var_350]
0x180050687  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005068c  lea     r8, [rsp+370h+var_350]
0x180050691  mov     rdx, r15
0x180050694  mov     rcx, rdi
0x180050697  mov     rax, rbx
0x18005069a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005069f  mov     ebx, eax
0x1800506a1  test    eax, eax
0x1800506a3  js      loc_18005087A
0x1800506a9  mov     rcx, [rsp+370h+var_348]
0x1800506ae  test    rcx, rcx
0x1800506b1  jz      short loc_1800506C5
0x1800506b3  mov     [rsp+370h+var_348], r14
0x1800506b8  mov     rax, [rcx]
0x1800506bb  mov     rax, [rax+10h]
0x1800506bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506c4  nop
0x1800506c5  mov     ebx, [rsp+370h+var_338]
0x1800506c9  mov     [rsp+370h+var_328], r14
0x1800506ce  mov     [rsp+370h+var_320], rsi
0x1800506d3  mov     [rsp+370h+var_318], r14
0x1800506d8  mov     [rsp+370h+var_310], ebx
0x1800506dc  test    ebx, ebx
0x1800506de  js      short loc_180050704
0x1800506e0  mov     rbx, [rsp+370h+newString]
0x1800506e5  xor     ecx, ecx; string
0x1800506e7  call    cs:__imp_WindowsDeleteString
0x1800506ed  mov     [rsp+370h+var_318], r14
0x1800506f2  lea     rdx, [rsp+370h+var_318]; newString
0x1800506f7  mov     rcx, rbx; string
0x1800506fa  call    cs:__imp_WindowsDuplicateString
0x180050700  mov     [rsp+370h+var_310], eax
0x180050704  mov     rax, qword ptr [rsp+370h+var_350]
0x180050709  mov     [rsp+370h+var_308], rax
0x18005070e  lea     rcx, [rsp+370h+var_308]
0x180050713  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x180050718  mov     rax, [rsp+370h+var_328]
0x18005071d  mov     [rsp+370h+var_300], rax
0x180050722  lea     rcx, [rsp+370h+var_300]
0x180050727  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x18005072c  lea     rdx, [rbp+270h+var_1A0]
0x180050733  lea     rcx, [rsp+370h+var_2F8]
0x180050738  call    ??0?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SingleViewExperienceLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<SingleViewExperienceLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType> const &)
0x18005073d  lea     rax, ??_7Reactivate@SingleViewExperienceTelemetry@@6B@; const SingleViewExperienceTelemetry::Reactivate::`vftable'
0x180050744  mov     [rsp+370h+var_2F8], rax
0x180050749  lea     r9, [rsp+370h+var_320]
0x18005074e  mov     r8d, [rsp+370h+var_330]
0x180050753  call    Windows__Internal__ComTaskPool__QueueTask__lambda_b534361c50cb4958853f48f5e7b1e06a___
0x180050758  mov     ebx, eax
0x18005075a  lea     rcx, [rsp+370h+var_2F8]; this
0x18005075f  call    ??1Reactivate@SingleViewExperienceTelemetry@@QEAA@XZ; SingleViewExperienceTelemetry::Reactivate::~Reactivate(void)
0x180050764  lea     rcx, [rsp+370h+var_300]
0x180050769  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005076e  lea     rcx, [rsp+370h+var_308]
0x180050773  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050778  mov     rcx, [rsp+370h+var_318]; string
0x18005077d  call    cs:__imp_WindowsDeleteString
0x180050783  test    ebx, ebx
0x180050785  js      loc_1800508D3
0x18005078b  lea     rcx, [rsp+370h+var_328]
0x180050790  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050795  nop
0x180050796  mov     rcx, qword ptr [rsp+370h+var_350]
0x18005079b  test    rcx, rcx
0x18005079e  jz      short loc_1800507B2
0x1800507a0  mov     qword ptr [rsp+370h+var_350], r14
0x1800507a5  mov     rax, [rcx]
0x1800507a8  mov     rax, [rax+10h]
0x1800507ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507b1  nop
0x1800507b2  mov     rcx, [rsp+370h+newString]; string
0x1800507b7  call    cs:__imp_WindowsDeleteString
0x1800507bd  mov     [rsp+370h+newString], r14
0x1800507c2  mov     ebx, r14d
0x1800507c5  lea     rcx, [rbp+270h+var_1A0]; this
0x1800507cc  call    ??1Reactivate@SingleViewExperienceTelemetry@@QEAA@XZ; SingleViewExperienceTelemetry::Reactivate::~Reactivate(void)
0x1800507d1  mov     eax, ebx
0x1800507d3  mov     rcx, [rbp+270h+var_50]
0x1800507da  xor     rcx, rsp; StackCookie
0x1800507dd  call    __security_check_cookie
0x1800507e2  add     rsp, 338h
0x1800507e9  pop     r15
0x1800507eb  pop     r14
0x1800507ed  pop     r13
0x1800507ef  pop     r12
0x1800507f1  pop     rdi
0x1800507f2  pop     rsi
0x1800507f3  pop     rbx
0x1800507f4  pop     rbp
0x1800507f5  retn
0x1800507f6  mov     rcx, [rbp+278h]; this
0x1800507fd  mov     r9d, eax; char *
0x180050800  lea     r8, aShellTwinuiExp_1; "shell\\twinui\\experiencemanagers\\core"...
0x180050807  mov     edx, 9Ch; void *
0x18005080c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050811  nop
0x180050812  mov     rcx, [rsp+370h+newString]; string
0x180050817  call    cs:__imp_WindowsDeleteString
0x18005081d  mov     [rsp+370h+newString], r14
0x180050822  jmp     short loc_1800507C5
0x180050824  mov     rcx, [rbp+278h]; this
0x18005082b  mov     r9d, eax; char *
0x18005082e  lea     r8, aShellTwinuiExp_1; "shell\\twinui\\experiencemanagers\\core"...
0x180050835  mov     edx, 0A3h; void *
0x18005083a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005083f  nop
0x180050840  mov     rcx, [rsp+370h+var_348]
0x180050845  test    rcx, rcx
0x180050848  jz      short loc_18005085C
0x18005084a  mov     [rsp+370h+var_348], r14
0x18005084f  mov     rax, [rcx]
0x180050852  mov     rax, [rax+10h]
0x180050856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005085b  nop
0x18005085c  mov     rcx, qword ptr [rsp+370h+var_350]
0x180050861  test    rcx, rcx
0x180050864  jz      short loc_180050878
0x180050866  mov     qword ptr [rsp+370h+var_350], r14
0x18005086b  mov     rax, [rcx]
0x18005086e  mov     rax, [rax+10h]
0x180050872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050877  nop
0x180050878  jmp     short loc_180050812
0x18005087a  mov     rcx, [rbp+278h]; this
0x180050881  mov     r9d, eax; char *
0x180050884  lea     r8, aShellTwinuiExp_1; "shell\\twinui\\experiencemanagers\\core"...
0x18005088b  mov     edx, 0A4h; void *
0x180050890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050895  nop
0x180050896  mov     rcx, [rsp+370h+var_348]
0x18005089b  test    rcx, rcx
0x18005089e  jz      short loc_1800508B2
0x1800508a0  mov     [rsp+370h+var_348], r14
0x1800508a5  mov     rax, [rcx]
0x1800508a8  mov     rax, [rax+10h]
0x1800508ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508b1  nop
0x1800508b2  mov     rcx, qword ptr [rsp+370h+var_350]
0x1800508b7  test    rcx, rcx
0x1800508ba  jz      short loc_1800508CE
0x1800508bc  mov     qword ptr [rsp+370h+var_350], r14
0x1800508c1  mov     rax, [rcx]
0x1800508c4  mov     rax, [rax+10h]
0x1800508c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508cd  nop
0x1800508ce  jmp     loc_180050812
0x1800508d3  mov     rcx, [rbp+278h]; this
0x1800508da  mov     r9d, ebx; char *
0x1800508dd  lea     r8, aShellTwinuiExp_1; "shell\\twinui\\experiencemanagers\\core"...
0x1800508e4  mov     edx, 0CDh; void *
0x1800508e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800508ee  lea     rcx, [rsp+370h+var_328]
0x1800508f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800508f8  nop
0x1800508f9  lea     rcx, [rsp+370h+var_350]
0x1800508fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050903  jmp     loc_180050812
0x180050908  mov     ebx, 80070578h
0x18005090d  jmp     loc_1800507C5
```
