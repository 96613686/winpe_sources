# _lambda_1be4443667fd153a918e05e8c389068c_::operator()(Windows::Foundation::Collections::IIterable<Windows::System::AppUriHandlerHost *> *,Windows::Internal::CNoResult &)

- ea: `0x1800647b4`
- end: `0x180064ae7`
- name: `??R_lambda_1be4443667fd153a918e05e8c389068c_@@QEAAJPEAU?$IIterable@PEAVAppUriHandlerHost@System@Windows@@@Collections@Foundation@Windows@@AEAVCNoResult@Internal@4@@Z`
- size: `819`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c4390`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180020fe0`
- `0x180021114`
- `0x18003c4f8`
- `0x18006323c`
- `0x180063e3c`
- `0x180064714`
- `0x1800647b4`
- `0x180064af0`
- `0x180064e14`
- `0x180064f44`
- `0x18008a030`
- `0x1800c4780`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180064920`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180064920`
- `ntdll!RtlPublishWnfStateData` at `0x180064a32`
- `ntdll!RtlPublishWnfStateData` at `0x180064a32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006497b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064a6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064a7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006497b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064a6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064a7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006494c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180064993`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006494c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180064993`

## string_xrefs

- `0x18006483e`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x18006487b`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x1800648c9`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x180064961`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x1800649a8`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x180064a09`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall _lambda_1be4443667fd153a918e05e8c389068c_::operator()(__int64 a1, __int64 a2)
{
  int UniqueHostNamesFromUserList; // eax
  __int64 v5; // rcx
  int v6; // eax
  RTL_SRWLOCK *v7; // rbx
  __int64 (__fastcall *v8)(RTL_SRWLOCK *, GUID *, int *); // rdi
  int v9; // eax
  RTL_SRWLOCK *v10; // rbx
  __int64 v11; // rbx
  HRESULT v12; // eax
  __int64 v13; // rbx
  HRESULT v14; // eax
  int v15; // eax
  int v16; // eax
  const char *v17; // r9
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-1B8h]
  int v20; // [rsp+20h] [rbp-1B8h]
  HSTRING newString; // [rsp+40h] [rbp-198h] BYREF
  HSTRING string; // [rsp+48h] [rbp-190h] BYREF
  int v23[2]; // [rsp+50h] [rbp-188h] BYREF
  RTL_SRWLOCK *v24; // [rsp+58h] [rbp-180h] BYREF
  __int64 v25; // [rsp+60h] [rbp-178h] BYREF
  __int64 v26; // [rsp+68h] [rbp-170h] BYREF
  _QWORD v27[42]; // [rsp+70h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v27,
    "SetAppAddedHosts");
  v27[0] = &LauncherClientProvider::SetAppAddedHosts::`vftable';
  LauncherClientProvider::SetAppAddedHosts::StartActivity((LauncherClientProvider::SetAppAddedHosts *)v27);
  try
  {
    *(_QWORD *)v23 = 0;
    if ( a2 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v23);
      UniqueHostNamesFromUserList = GetUniqueHostNamesFromUserList(a2, v23);
      if ( UniqueHostNamesFromUserList < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
          (const char *)(unsigned int)UniqueHostNamesFromUserList,
          v19);
    }
    else
    {
      v24 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
      v6 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
             v5,
             &v24);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8C,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
          (const char *)(unsigned int)v6,
          v19);
      v7 = v24;
      v8 = *(__int64 (__fastcall **)(RTL_SRWLOCK *, GUID *, int *))v24->Ptr;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v23);
      v9 = v8(v7, &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e, v23);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
          (const char *)(unsigned int)v9,
          v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    }
    GetStateRepoUserFromSystemUser(&v26, *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL));
    wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerGroupStatics>(&v25);
    string = 0;
    newString = 0;
    v10 = (RTL_SRWLOCK *)(*(_QWORD *)(a1 + 8) + 64LL);
    AcquireSRWLockShared(v10);
    v24 = v10;
    v11 = *(_QWORD *)(a1 + 8);
    WindowsDeleteString(0);
    string = 0;
    v12 = WindowsDuplicateString(*(HSTRING *)(v11 + 40), &string);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
        (const char *)(unsigned int)v12,
        v19);
    v13 = *(_QWORD *)(a1 + 8);
    WindowsDeleteString(newString);
    newString = 0;
    v14 = WindowsDuplicateString(*(HSTRING *)(v13 + 56), &newString);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
        (const char *)(unsigned int)v14,
        v19);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    v20 = v23[0];
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING, HSTRING))(*(_QWORD *)v25 + 160LL))(
            v25,
            v26,
            newString,
            string);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
        (const char *)(unsigned int)v15,
        v20);
    v16 = RtlPublishWnfStateData(WNF_A2A_APPURIHANDLER_INSTALLED, 0, 0, 0) | 0x10000000;
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)(unsigned int)v16,
        0);
    wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v27);
    WindowsDeleteString(newString);
    newString = 0;
    WindowsDeleteString(string);
    string = 0;
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v25);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v23);
    LauncherClientProvider::SetAppAddedHosts::~SetAppAddedHosts((LauncherClientProvider::SetAppAddedHosts *)v27);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA1,
                           (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x1800647b4  mov     [rsp+arg_10], rbx
0x1800647b9  mov     [rsp+arg_18], rsi
0x1800647be  push    rdi
0x1800647bf  sub     rsp, 1D0h
0x1800647c6  mov     rax, cs:__security_cookie
0x1800647cd  xor     rax, rsp
0x1800647d0  mov     [rsp+1D8h+var_18], rax
0x1800647d8  mov     rbx, rdx
0x1800647db  mov     rsi, rcx
0x1800647de  lea     rdx, aSetappaddedhos; "SetAppAddedHosts"
0x1800647e5  lea     rcx, [rsp+1D8h+var_168]
0x1800647ea  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800647ef  lea     rax, ??_7SetAppAddedHosts@LauncherClientProvider@@6B@; const LauncherClientProvider::SetAppAddedHosts::`vftable'
0x1800647f6  mov     [rsp+1D8h+var_168], rax
0x1800647fb  lea     rcx, [rsp+1D8h+var_168]; this
0x180064800  call    ?StartActivity@SetAppAddedHosts@LauncherClientProvider@@QEAAXXZ; LauncherClientProvider::SetAppAddedHosts::StartActivity(void)
0x180064805  nop
0x180064806  mov     qword ptr [rsp+1D8h+var_188], 0
0x18006480f  test    rbx, rbx
0x180064812  jz      short loc_18006484F
0x180064814  lea     rcx, [rsp+1D8h+var_188]
0x180064819  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006481e  lea     rdx, [rsp+1D8h+var_188]
0x180064823  mov     rcx, rbx
0x180064826  call    ?GetUniqueHostNamesFromUserList@@YAJPEAU?$IIterable@PEAVAppUriHandlerHost@System@Windows@@@Collections@Foundation@Windows@@PEAPEAU?$IIterable@PEAUHSTRING__@@@234@@Z; GetUniqueHostNamesFromUserList(Windows::Foundation::Collections::IIterable<Windows::System::AppUriHandlerHost *> *,Windows::Foundation::Collections::IIterable<HSTRING__ *> * *)
0x18006482b  mov     rcx, [rsp+1D8h]; this
0x180064833  test    eax, eax
0x180064835  jns     loc_1800648E5
0x18006483b  mov     r9d, eax; char *
0x18006483e  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180064845  mov     edx, 87h; void *
0x18006484a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006484f  mov     [rsp+1D8h+var_180], 0
0x180064858  lea     rcx, [rsp+1D8h+var_180]
0x18006485d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064862  lea     rdx, [rsp+1D8h+var_180]
0x180064867  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x18006486c  mov     rcx, [rsp+1D8h]; this
0x180064874  test    eax, eax
0x180064876  jns     short loc_18006488D
0x180064878  mov     r9d, eax; char *
0x18006487b  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180064882  mov     edx, 8Ch; void *
0x180064887  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006488d  mov     rbx, [rsp+1D8h+var_180]
0x180064892  mov     rax, [rbx]
0x180064895  mov     rdi, [rax]
0x180064898  lea     rcx, [rsp+1D8h+var_188]
0x18006489d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800648a2  lea     r8, [rsp+1D8h+var_188]
0x1800648a7  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x1800648ae  mov     rcx, rbx
0x1800648b1  mov     rax, rdi
0x1800648b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648b9  nop
0x1800648ba  mov     rcx, [rsp+1D8h]; this
0x1800648c2  test    eax, eax
0x1800648c4  jns     short loc_1800648DB
0x1800648c6  mov     r9d, eax; char *
0x1800648c9  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x1800648d0  mov     edx, 8Dh; void *
0x1800648d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800648db  lea     rcx, [rsp+1D8h+var_180]
0x1800648e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800648e5  mov     rdx, [rsi+8]
0x1800648e9  mov     rdx, [rdx+30h]
0x1800648ed  lea     rcx, [rsp+1D8h+var_170]
0x1800648f2  call    ?GetStateRepoUserFromSystemUser@@YA?AV?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEAUIUser@System@Windows@@@Z; GetStateRepoUserFromSystemUser(Windows::System::IUser *)
0x1800648f7  nop
0x1800648f8  lea     rcx, [rsp+1D8h+var_178]
0x1800648fd  call    ??$GetActivationFactory@UIDynamicAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIDynamicAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerGroupStatics>(ushort const *)
0x180064902  nop
0x180064903  mov     [rsp+1D8h+string], 0
0x18006490c  mov     [rsp+1D8h+newString], 0
0x180064915  mov     rbx, [rsi+8]
0x180064919  add     rbx, 40h ; '@'
0x18006491d  mov     rcx, rbx; SRWLock
0x180064920  call    cs:__imp_AcquireSRWLockShared
0x180064926  mov     [rsp+1D8h+var_180], rbx
0x18006492b  mov     rbx, [rsi+8]
0x18006492f  mov     rcx, [rsp+1D8h+string]; string
0x180064934  call    cs:__imp_WindowsDeleteString
0x18006493a  mov     [rsp+1D8h+string], 0
0x180064943  lea     rdx, [rsp+1D8h+string]; newString
0x180064948  mov     rcx, [rbx+28h]; string
0x18006494c  call    cs:__imp_WindowsDuplicateString
0x180064952  mov     rcx, [rsp+1D8h]; this
0x18006495a  test    eax, eax
0x18006495c  jns     short loc_180064972
0x18006495e  mov     r9d, eax; char *
0x180064961  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180064968  mov     edx, 98h; void *
0x18006496d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064972  mov     rbx, [rsi+8]
0x180064976  mov     rcx, [rsp+1D8h+newString]; string
0x18006497b  call    cs:__imp_WindowsDeleteString
0x180064981  mov     [rsp+1D8h+newString], 0
0x18006498a  lea     rdx, [rsp+1D8h+newString]; newString
0x18006498f  mov     rcx, [rbx+38h]; string
0x180064993  call    cs:__imp_WindowsDuplicateString
0x180064999  mov     rcx, [rsp+1D8h]; this
0x1800649a1  test    eax, eax
0x1800649a3  jns     short loc_1800649BA
0x1800649a5  mov     r9d, eax; char *
0x1800649a8  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x1800649af  mov     edx, 99h; void *
0x1800649b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800649ba  lea     rcx, [rsp+1D8h+var_180]
0x1800649bf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800649c4  mov     rcx, [rsp+1D8h+var_178]
0x1800649c9  mov     r10, qword ptr [rsp+1D8h+var_188]
0x1800649ce  mov     rax, [rcx]
0x1800649d1  mov     [rsp+1D8h+var_1B0], 0
0x1800649da  mov     qword ptr [rsp+1D8h+var_1B8], r10; int
0x1800649df  mov     r9, [rsp+1D8h+string]
0x1800649e4  mov     r8, [rsp+1D8h+newString]
0x1800649e9  mov     rdx, [rsp+1D8h+var_170]
0x1800649ee  mov     rax, [rax+0A0h]
0x1800649f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800649fa  mov     rcx, [rsp+1D8h]; this
0x180064a02  test    eax, eax
0x180064a04  jns     short loc_180064A1A
0x180064a06  mov     r9d, eax; char *
0x180064a09  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180064a10  mov     edx, 9Ch; void *
0x180064a15  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064a1a  mov     qword ptr [rsp+1D8h+var_1B8], 0; int
0x180064a23  xor     r9d, r9d
0x180064a26  xor     r8d, r8d
0x180064a29  xor     edx, edx
0x180064a2b  mov     rcx, cs:WNF_A2A_APPURIHANDLER_INSTALLED
0x180064a32  call    cs:__imp_RtlPublishWnfStateData
0x180064a38  or      eax, 10000000h
0x180064a3d  mov     rcx, [rsp+1D8h]; this
0x180064a45  jge     short loc_180064A5B
0x180064a47  mov     r9d, eax; char *
0x180064a4a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180064a51  mov     edx, 35Ah; void *
0x180064a56  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064a5b  lea     rcx, [rsp+1D8h+var_168]
0x180064a60  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180064a65  nop
0x180064a66  mov     rcx, [rsp+1D8h+newString]; string
0x180064a6b  call    cs:__imp_WindowsDeleteString
0x180064a71  mov     [rsp+1D8h+newString], 0
0x180064a7a  mov     rcx, [rsp+1D8h+string]; string
0x180064a7f  call    cs:__imp_WindowsDeleteString
0x180064a85  mov     [rsp+1D8h+string], 0
0x180064a8e  lea     rcx, [rsp+1D8h+var_178]
0x180064a93  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180064a98  nop
0x180064a99  lea     rcx, [rsp+1D8h+var_170]
0x180064a9e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064aa3  nop
0x180064aa4  lea     rcx, [rsp+1D8h+var_188]
0x180064aa9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064aae  nop
0x180064aaf  lea     rcx, [rsp+1D8h+var_168]; this
0x180064ab4  call    ??1SetAppAddedHosts@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::SetAppAddedHosts::~SetAppAddedHosts(void)
0x180064ab9  nop
0x180064aba  xor     eax, eax
0x180064abc  jmp     short loc_180064AC2
0x180064abe  mov     eax, dword ptr [rsp+1D8h+newString]
0x180064ac2  mov     rcx, [rsp+1D8h+var_18]
0x180064aca  xor     rcx, rsp; StackCookie
0x180064acd  call    __security_check_cookie
0x180064ad2  lea     r11, [rsp+1D8h+var_8]
0x180064ada  mov     rbx, [r11+20h]
0x180064ade  mov     rsi, [r11+28h]
0x180064ae2  mov     rsp, r11
0x180064ae5  pop     rdi
0x180064ae6  retn
```
