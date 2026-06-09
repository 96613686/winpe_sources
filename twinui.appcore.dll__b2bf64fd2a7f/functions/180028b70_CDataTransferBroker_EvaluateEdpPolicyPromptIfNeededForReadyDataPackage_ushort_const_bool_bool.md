# CDataTransferBroker::EvaluateEdpPolicyPromptIfNeededForReadyDataPackage(ushort const *,bool,bool *)

- ea: `0x180028b70`
- end: `0x180028f6a`
- name: `?EvaluateEdpPolicyPromptIfNeededForReadyDataPackage@CDataTransferBroker@@UEAAJPEBG_NPEA_N@Z`
- size: `1018`
- prototype: `__int64 __fastcall(CDataTransferBroker *__hidden this, const unsigned __int16 *, bool, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ccf0`

## callees

- `0x180003d24`
- `0x1800192a8`
- `0x18001cc38`
- `0x18001d95c`
- `0x180026498`
- `0x180028b70`
- `0x180028f70`
- `0x180066158`
- `0x1800662e0`
- `0x180067f48`
- `0x18006a1e0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028da7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028ec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028da7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028ec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028e46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028e46`
- `ntdll!RtlNtStatusToDosError` at `0x180028bab`
- `ntdll!RtlNtStatusToDosError` at `0x180028bab`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180028e4f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180028e4f`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsContextExemptOrEnlightenedAllowed` at `0x180028d78`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsContextExemptOrEnlightenedAllowed` at `0x180028d78`
- `ext-ms-win-edputil-policy-l1-1-0!EdpCheckAccessForContext` at `0x180028dea`
- `ext-ms-win-edputil-policy-l1-1-0!EdpCheckAccessForContext` at `0x180028dea`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccessForContext` at `0x180028e80`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccessForContext` at `0x180028e80`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForPackageFullName` at `0x180028d31`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForPackageFullName` at `0x180028d31`

## pseudocode

```c
__int64 __fastcall CDataTransferBroker::EvaluateEdpPolicyPromptIfNeededForReadyDataPackage(
        CDataTransferBroker *this,
        const unsigned __int16 *a2,
        char a3,
        bool *a4)
{
  NTSTATUS EdpEnforcementLevel2; // eax
  signed int v9; // eax
  bool v10; // sf
  int ReadyDataPackage; // eax
  unsigned int v12; // ebx
  struct Windows::ApplicationModel::DataTransfer::IDataPackage *v13; // rdi
  __int64 (__fastcall *v14)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64 *); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, const unsigned __int16 *, __int64 *); // rbx
  int v22; // eax
  int ContextForPackageFullName; // eax
  __int64 v24; // rdx
  __int64 v25; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v27; // rbx
  PCWSTR v28; // rax
  __int64 v29; // rdi
  PCWSTR v30; // rbx
  HWND ForegroundWindow; // rax
  int v32; // eax
  int v34; // [rsp+20h] [rbp-79h]
  HSTRING string; // [rsp+40h] [rbp-59h] BYREF
  int v36; // [rsp+48h] [rbp-51h] BYREF
  __int64 v37; // [rsp+50h] [rbp-49h] BYREF
  __int64 v38; // [rsp+58h] [rbp-41h] BYREF
  __int64 v39; // [rsp+60h] [rbp-39h] BYREF
  __int64 v40; // [rsp+68h] [rbp-31h] BYREF
  struct Windows::ApplicationModel::DataTransfer::IDataPackage *v41; // [rsp+70h] [rbp-29h] BYREF
  int v42[2]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v43; // [rsp+80h] [rbp-19h]
  __int128 v44; // [rsp+88h] [rbp-11h]
  __int128 v45; // [rsp+98h] [rbp-1h]
  __int64 v46; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  int v48; // [rsp+118h] [rbp+7Fh] BYREF

  *a4 = 1;
  v48 = 0;
  EdpEnforcementLevel2 = EdpGetEdpEnforcementLevel2(&v48);
  v9 = RtlNtStatusToDosError(EdpEnforcementLevel2);
  v10 = v9 < 0;
  if ( v9 > 0 )
    v10 = 1;
  if ( !v10 && v48 )
  {
    v41 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    ReadyDataPackage = CDataTransferBroker::GetReadyDataPackage(this, &v41);
    v12 = ReadyDataPackage;
    if ( ReadyDataPackage < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x596,
        (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
        (const char *)(unsigned int)ReadyDataPackage,
        v34);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      return v12;
    }
    v13 = v41;
    v37 = 0;
    v14 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64 *))(*(_QWORD *)v41 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    v15 = v14(v13, &v37);
    v12 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x599,
        (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
        (const char *)(unsigned int)v15,
        v34);
LABEL_32:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      goto LABEL_33;
    }
    v39 = 0;
    v16 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet>::As<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet3>(
            &v37,
            &v39);
    v12 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59C,
        (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
        (const char *)(unsigned int)v16,
        v34);
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      goto LABEL_32;
    }
    v17 = v39;
    string = 0;
    v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v19 = v18(v17, &string);
    v12 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59F,
        (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
        (const char *)(unsigned int)v19,
        v34);
LABEL_30:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_31;
    }
    v20 = *((_QWORD *)this + 10);
    v38 = 0;
    v21 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v20 + 104LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v38,
      0);
    v22 = v21(v20, a2, &v38);
    v12 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A2,
        (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
        (const char *)(unsigned int)v22,
        v34);
LABEL_29:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
      goto LABEL_30;
    }
    v40 = 0;
    ContextForPackageFullName = EdpGetContextForPackageFullName(v38, &v40);
    v12 = ContextForPackageFullName;
    if ( ContextForPackageFullName < 0 )
    {
      v24 = 1445;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
        (const char *)(unsigned int)ContextForPackageFullName,
        v34);
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&v40);
      goto LABEL_29;
    }
    v25 = v40;
    v36 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    ContextForPackageFullName = EdpIsContextExemptOrEnlightenedAllowed(StringRawBuffer, v25, &v36);
    v12 = ContextForPackageFullName;
    if ( ContextForPackageFullName < 0 )
    {
      v24 = 1448;
      goto LABEL_17;
    }
    if ( v36 == 1 )
    {
LABEL_21:
      wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&v40);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      v12 = 0;
      goto LABEL_33;
    }
    if ( !a3 )
    {
      v27 = v40;
      v28 = WindowsGetStringRawBuffer(string, 0);
      ContextForPackageFullName = EdpCheckAccessForContext(v28, v27, &v36);
      v12 = ContextForPackageFullName;
      if ( ContextForPackageFullName < 0 )
      {
        v24 = 1457;
        goto LABEL_17;
      }
      *a4 = v36 != 2;
      goto LABEL_21;
    }
    *(_QWORD *)v42 = v41;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v42);
    v29 = v40;
    v43 = v38;
    v45 = 0;
    v46 = 0;
    v44 = 0;
    HIDWORD(v45) = 1;
    v30 = WindowsGetStringRawBuffer(string, 0);
    ForegroundWindow = GetForegroundWindow();
    v32 = EdpRequestAccessForContext(
            ForegroundWindow,
            v30,
            v29,
            lambda_6189d7b3750556187fa2ffcfbc9a3fad_::_lambda_invoker_cdecl_);
    v12 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F2,
        (unsigned int)"onecoreuap\\shell\\twinui\\sharinganddevices\\platform\\sharingmanager.cpp",
        (const char *)(unsigned int)v32,
        (int)v42);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
      goto LABEL_28;
    }
    LOBYTE(v48) = 0;
    *a4 = v36 == 1;
    ModernShareTelemetry::ModernShareFlow::EdpPolicyEval<enum EDP_POLICY_RESULT &,bool,bool &>(
      (char *)this + 488,
      &v36,
      &v48,
      a4);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
    wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&v40);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  }
  return 0;
}

```

## disassembly

```asm
0x180028b70  push    rbp
0x180028b72  push    rbx
0x180028b73  push    rsi
0x180028b74  push    rdi
0x180028b75  push    r12
0x180028b77  push    r13
0x180028b79  push    r14
0x180028b7b  push    r15
0x180028b7d  lea     rbp, [rsp-1Fh]
0x180028b82  sub     rsp, 0B8h
0x180028b89  mov     r14, rcx
0x180028b8c  mov     byte ptr [r9], 1
0x180028b90  xor     r13d, r13d
0x180028b93  lea     rcx, [rbp+57h+arg_18]
0x180028b97  mov     [rbp+57h+arg_18], r13d
0x180028b9b  mov     rsi, r9
0x180028b9e  mov     r15b, r8b
0x180028ba1  mov     r12, rdx
0x180028ba4  call    EdpGetEdpEnforcementLevel2
0x180028ba9  mov     ecx, eax; Status
0x180028bab  call    cs:__imp_RtlNtStatusToDosError
0x180028bb1  test    eax, eax
0x180028bb3  jle     short loc_180028BBF
0x180028bb5  movzx   eax, ax
0x180028bb8  or      eax, 80070000h
0x180028bbd  test    eax, eax
0x180028bbf  js      loc_180028F54
0x180028bc5  cmp     [rbp+57h+arg_18], r13d
0x180028bc9  jz      loc_180028F54
0x180028bcf  lea     rcx, [rbp+57h+var_80]
0x180028bd3  mov     [rbp+57h+var_80], r13
0x180028bd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028bdc  lea     rdx, [rbp+57h+var_80]; struct Windows::ApplicationModel::DataTransfer::IDataPackage **
0x180028be0  mov     rcx, r14; this
0x180028be3  call    ?GetReadyDataPackage@CDataTransferBroker@@UEAAJPEAPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@@Z; CDataTransferBroker::GetReadyDataPackage(Windows::ApplicationModel::DataTransfer::IDataPackage * *)
0x180028be8  mov     ebx, eax
0x180028bea  test    eax, eax
0x180028bec  jns     short loc_180028C0B
0x180028bee  mov     rcx, [rbp+5Fh]; this
0x180028bf2  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180028bf9  mov     r9d, eax; char *
0x180028bfc  mov     edx, 596h; void *
0x180028c01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c06  jmp     loc_180028EDF
0x180028c0b  mov     rdi, [rbp+57h+var_80]
0x180028c0f  lea     rcx, [rbp+57h+var_A0]
0x180028c13  mov     [rbp+57h+var_A0], r13
0x180028c17  mov     rax, [rdi]
0x180028c1a  mov     rbx, [rax+38h]
0x180028c1e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028c23  lea     rdx, [rbp+57h+var_A0]
0x180028c27  mov     rcx, rdi
0x180028c2a  mov     rax, rbx
0x180028c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c32  mov     ebx, eax
0x180028c34  test    eax, eax
0x180028c36  jns     short loc_180028C55
0x180028c38  mov     rcx, [rbp+5Fh]; this
0x180028c3c  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180028c43  mov     r9d, eax; char *
0x180028c46  mov     edx, 599h; void *
0x180028c4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c50  jmp     loc_180028ED6
0x180028c55  lea     rdx, [rbp+57h+var_90]
0x180028c59  mov     [rbp+57h+var_90], r13
0x180028c5d  lea     rcx, [rbp+57h+var_A0]
0x180028c61  call    ??$As@UIDataPackagePropertySet3@DataTransfer@ApplicationModel@Windows@@@?$ComPtr@UIDataPackagePropertySet@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDataPackagePropertySet3@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet>::As<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackagePropertySet3>>)
0x180028c66  mov     ebx, eax
0x180028c68  test    eax, eax
0x180028c6a  jns     short loc_180028C89
0x180028c6c  mov     rcx, [rbp+5Fh]; this
0x180028c70  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180028c77  mov     r9d, eax; char *
0x180028c7a  mov     edx, 59Ch; void *
0x180028c7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c84  jmp     loc_180028ECD
0x180028c89  mov     rdi, [rbp+57h+var_90]
0x180028c8d  xor     ecx, ecx; string
0x180028c8f  mov     [rbp+57h+string], r13
0x180028c93  mov     rax, [rdi]
0x180028c96  mov     rbx, [rax+30h]
0x180028c9a  call    cs:__imp_WindowsDeleteString
0x180028ca0  lea     rdx, [rbp+57h+string]
0x180028ca4  mov     [rbp+57h+string], r13
0x180028ca8  mov     rcx, rdi
0x180028cab  mov     rax, rbx
0x180028cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cb3  mov     ebx, eax
0x180028cb5  test    eax, eax
0x180028cb7  jns     short loc_180028CD6
0x180028cb9  mov     rcx, [rbp+5Fh]; this
0x180028cbd  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180028cc4  mov     r9d, eax; char *
0x180028cc7  mov     edx, 59Fh; void *
0x180028ccc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028cd1  jmp     loc_180028EBF
0x180028cd6  mov     rdi, [r14+50h]
0x180028cda  lea     rcx, [rbp+57h+var_98]
0x180028cde  mov     [rbp+57h+var_98], r13
0x180028ce2  xor     edx, edx
0x180028ce4  mov     rax, [rdi]
0x180028ce7  mov     rbx, [rax+68h]
0x180028ceb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180028cf0  lea     r8, [rbp+57h+var_98]
0x180028cf4  mov     rdx, r12
0x180028cf7  mov     rcx, rdi
0x180028cfa  mov     rax, rbx
0x180028cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d02  mov     ebx, eax
0x180028d04  test    eax, eax
0x180028d06  jns     short loc_180028D25
0x180028d08  mov     rcx, [rbp+5Fh]; this
0x180028d0c  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180028d13  mov     r9d, eax; char *
0x180028d16  mov     edx, 5A2h; void *
0x180028d1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028d20  jmp     loc_180028EB6
0x180028d25  mov     rcx, [rbp+57h+var_98]
0x180028d29  lea     rdx, [rbp+57h+var_88]
0x180028d2d  mov     [rbp+57h+var_88], r13
0x180028d31  call    cs:__imp_EdpGetContextForPackageFullName
0x180028d37  mov     ebx, eax
0x180028d39  test    eax, eax
0x180028d3b  jns     short loc_180028D5A
0x180028d3d  mov     edx, 5A5h; void *
0x180028d42  mov     rcx, [rbp+5Fh]; this
0x180028d46  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180028d4d  mov     r9d, eax; char *
0x180028d50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028d55  jmp     loc_180028EAD
0x180028d5a  mov     rcx, [rbp+57h+string]; string
0x180028d5e  xor     edx, edx; length
0x180028d60  mov     rbx, [rbp+57h+var_88]
0x180028d64  mov     [rbp+57h+var_A8], r13d
0x180028d68  call    cs:__imp_WindowsGetStringRawBuffer
0x180028d6e  lea     r8, [rbp+57h+var_A8]
0x180028d72  mov     rdx, rbx
0x180028d75  mov     rcx, rax
0x180028d78  call    cs:__imp_EdpIsContextExemptOrEnlightenedAllowed
0x180028d7e  mov     ebx, eax
0x180028d80  test    eax, eax
0x180028d82  jns     short loc_180028D8B
0x180028d84  mov     edx, 5A8h
0x180028d89  jmp     short loc_180028D42
0x180028d8b  cmp     [rbp+57h+var_A8], 1
0x180028d8f  jnz     short loc_180028DCB
0x180028d91  lea     rcx, [rbp+57h+var_88]
0x180028d95  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x180028d9a  lea     rcx, [rbp+57h+var_98]
0x180028d9e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028da3  mov     rcx, [rbp+57h+string]; string
0x180028da7  call    cs:__imp_WindowsDeleteString
0x180028dad  lea     rcx, [rbp+57h+var_90]
0x180028db1  mov     [rbp+57h+string], r13
0x180028db5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028dba  lea     rcx, [rbp+57h+var_A0]
0x180028dbe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028dc3  mov     ebx, r13d
0x180028dc6  jmp     loc_180028EDF
0x180028dcb  test    r15b, r15b
0x180028dce  jnz     short loc_180028E0B
0x180028dd0  mov     rcx, [rbp+57h+string]; string
0x180028dd4  xor     edx, edx; length
0x180028dd6  mov     rbx, [rbp+57h+var_88]
0x180028dda  call    cs:__imp_WindowsGetStringRawBuffer
0x180028de0  lea     r8, [rbp+57h+var_A8]
0x180028de4  mov     rdx, rbx
0x180028de7  mov     rcx, rax
0x180028dea  call    cs:__imp_EdpCheckAccessForContext
0x180028df0  mov     ebx, eax
0x180028df2  test    eax, eax
0x180028df4  jns     short loc_180028E00
0x180028df6  mov     edx, 5B1h
0x180028dfb  jmp     loc_180028D42
0x180028e00  cmp     [rbp+57h+var_A8], 2
0x180028e04  setnz   al
0x180028e07  mov     [rsi], al
0x180028e09  jmp     short loc_180028D91
0x180028e0b  mov     rax, [rbp+57h+var_80]
0x180028e0f  lea     rcx, [rbp+57h+var_78]
0x180028e13  mov     qword ptr [rbp+57h+var_78], rax
0x180028e17  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180028e1c  mov     rax, [rbp+57h+var_98]
0x180028e20  xorps   xmm0, xmm0
0x180028e23  mov     rcx, [rbp+57h+string]; string
0x180028e27  xor     edx, edx; length
0x180028e29  mov     rdi, [rbp+57h+var_88]
0x180028e2d  mov     [rbp+57h+var_70], rax
0x180028e31  xor     eax, eax
0x180028e33  movups  [rbp+57h+var_58], xmm0
0x180028e37  mov     [rbp+57h+var_48], rax
0x180028e3b  movups  [rbp+57h+var_68], xmm0
0x180028e3f  mov     dword ptr [rbp+57h+var_58+0Ch], 1
0x180028e46  call    cs:__imp_WindowsGetStringRawBuffer
0x180028e4c  mov     rbx, rax
0x180028e4f  call    cs:__imp_GetForegroundWindow
0x180028e55  lea     rcx, [rbp+57h+var_A8]
0x180028e59  mov     r8, rdi
0x180028e5c  mov     [rsp+0F0h+var_C0], rcx
0x180028e61  lea     r9, _lambda_6189d7b3750556187fa2ffcfbc9a3fad____lambda_invoker_cdecl_
0x180028e68  lea     rcx, [rbp+57h+var_68]
0x180028e6c  mov     rdx, rbx
0x180028e6f  mov     [rsp+0F0h+var_C8], rcx
0x180028e74  lea     rcx, [rbp+57h+var_78]
0x180028e78  mov     qword ptr [rsp+0F0h+var_D0], rcx; int
0x180028e7d  mov     rcx, rax
0x180028e80  call    cs:__imp_EdpRequestAccessForContext
0x180028e86  mov     ebx, eax
0x180028e88  test    eax, eax
0x180028e8a  jns     short loc_180028EEC
0x180028e8c  mov     rcx, [rbp+5Fh]; this
0x180028e90  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\twinui\\sharingandde"...
0x180028e97  mov     r9d, eax; char *
0x180028e9a  mov     edx, 5F2h; void *
0x180028e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ea4  lea     rcx, [rbp+57h+var_78]
0x180028ea8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028ead  lea     rcx, [rbp+57h+var_88]
0x180028eb1  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x180028eb6  lea     rcx, [rbp+57h+var_98]
0x180028eba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028ebf  mov     rcx, [rbp+57h+string]; string
0x180028ec3  call    cs:__imp_WindowsDeleteString
0x180028ec9  mov     [rbp+57h+string], r13
0x180028ecd  lea     rcx, [rbp+57h+var_90]
0x180028ed1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028ed6  lea     rcx, [rbp+57h+var_A0]
0x180028eda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028edf  lea     rcx, [rbp+57h+var_80]
0x180028ee3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028ee8  mov     eax, ebx
0x180028eea  jmp     short loc_180028F56
0x180028eec  cmp     [rbp+57h+var_A8], 1
0x180028ef0  lea     rcx, [r14+1E8h]
0x180028ef7  mov     r9, rsi
0x180028efa  mov     byte ptr [rbp+57h+arg_18], r13b
0x180028efe  setz    al
0x180028f01  lea     r8, [rbp+57h+arg_18]
0x180028f05  lea     rdx, [rbp+57h+var_A8]
0x180028f09  mov     [rsi], al
0x180028f0b  call    ??$EdpPolicyEval@AEAW4EDP_POLICY_RESULT@@_NAEA_N@ModernShareFlow@ModernShareTelemetry@@QEAAXAEAW4EDP_POLICY_RESULT@@$$QEA_NAEA_N@Z; ModernShareTelemetry::ModernShareFlow::EdpPolicyEval<EDP_POLICY_RESULT &,bool,bool &>(EDP_POLICY_RESULT &,bool &&,bool &)
0x180028f10  lea     rcx, [rbp+57h+var_78]
0x180028f14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028f19  lea     rcx, [rbp+57h+var_88]
0x180028f1d  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x180028f22  lea     rcx, [rbp+57h+var_98]
0x180028f26  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028f2b  mov     rcx, [rbp+57h+string]; string
0x180028f2f  call    cs:__imp_WindowsDeleteString
0x180028f35  lea     rcx, [rbp+57h+var_90]
0x180028f39  mov     [rbp+57h+string], r13
0x180028f3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028f42  lea     rcx, [rbp+57h+var_A0]
0x180028f46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028f4b  lea     rcx, [rbp+57h+var_80]
0x180028f4f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028f54  xor     eax, eax
0x180028f56  add     rsp, 0B8h
0x180028f5d  pop     r15
0x180028f5f  pop     r14
0x180028f61  pop     r13
0x180028f63  pop     r12
0x180028f65  pop     rdi
0x180028f66  pop     rsi
0x180028f67  pop     rbx
0x180028f68  pop     rbp
0x180028f69  retn
```
