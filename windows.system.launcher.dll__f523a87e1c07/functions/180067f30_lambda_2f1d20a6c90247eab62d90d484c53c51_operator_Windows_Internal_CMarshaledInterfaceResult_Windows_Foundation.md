# _lambda_2f1d20a6c90247eab62d90d484c53c51_::operator()(Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVector<Windows::System::AppUriHandlerHost *>> &)

- ea: `0x180067f30`
- end: `0x180068269`
- name: `??R_lambda_2f1d20a6c90247eab62d90d484c53c51_@@QEAAJAEAV?$CMarshaledInterfaceResult@U?$IVector@PEAVAppUriHandlerHost@System@Windows@@@Collections@Foundation@Windows@@@Internal@Windows@@@Z`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c4410`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18001cc3c`
- `0x180020fe0`
- `0x180021114`
- `0x180024990`
- `0x18003c4f8`
- `0x18006323c`
- `0x180064714`
- `0x180064f44`
- `0x1800679c8`
- `0x180067f30`
- `0x180068270`
- `0x18008a030`
- `0x1800c2030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180068004`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180068004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006805f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800681e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800681fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006805f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800681e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800681fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180068030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180068077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180068030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180068077`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18006818b`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18006818b`

## string_xrefs

- `0x180067fb5`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x180068045`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x18006808c`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x1800680d4`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`
- `0x180068143`: `onecoreuap\shell\windows.system.launcher\lib\windows.system.appurihandlerregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall _lambda_2f1d20a6c90247eab62d90d484c53c51_::operator()(__int64 a1, RTL_SRWLOCK *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // rbx
  HRESULT v8; // eax
  __int64 v9; // rbx
  HRESULT v10; // eax
  const struct _GUID *v11; // rcx
  int QueryAssociationBrokerService; // eax
  void *v13; // rdi
  __int64 (__fastcall *v14)(void *, _QWORD, _QWORD, _QWORD); // rbx
  int v15; // eax
  __int64 v16; // rdi
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  const char *v19; // r9
  __int64 result; // rax
  int v21; // [rsp+20h] [rbp-1E8h]
  HSTRING newString; // [rsp+40h] [rbp-1C8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-1C0h] BYREF
  RTL_SRWLOCK *v24; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 v25; // [rsp+58h] [rbp-1B0h] BYREF
  void *v26; // [rsp+60h] [rbp-1A8h] BYREF
  __int64 v27; // [rsp+68h] [rbp-1A0h] BYREF
  __int64 v28; // [rsp+70h] [rbp-198h] BYREF
  char v29[8]; // [rsp+78h] [rbp-190h] BYREF
  _BYTE v30[16]; // [rsp+80h] [rbp-188h] BYREF
  _QWORD v31[42]; // [rsp+90h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v31,
    "GetAppAddedHosts");
  v31[0] = &LauncherClientProvider::GetAppAddedHosts::`vftable';
  LauncherClientProvider::GetAppAddedHosts::StartActivity((LauncherClientProvider::GetAppAddedHosts *)v31);
  v27 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::AppUriHandlerHost,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::AppUriHandlerHost *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::AppUriHandlerHost *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::AppUriHandlerHost *>,0>>(
         v4,
         &v27);
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
        (const char *)(unsigned int)v5,
        v21);
    GetStateRepoUserFromSystemUser(v30, *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL));
    wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerGroupStatics>(v29);
    string = 0;
    newString = 0;
    v6 = (RTL_SRWLOCK *)(*(_QWORD *)(a1 + 8) + 64LL);
    AcquireSRWLockShared(v6);
    v24 = v6;
    v7 = *(_QWORD *)(a1 + 8);
    WindowsDeleteString(0);
    string = 0;
    v8 = WindowsDuplicateString(*(HSTRING *)(v7 + 40), &string);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
        (const char *)(unsigned int)v8,
        v21);
    v9 = *(_QWORD *)(a1 + 8);
    WindowsDeleteString(newString);
    newString = 0;
    v10 = WindowsDuplicateString(*(HSTRING *)(v9 + 56), &newString);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
        (const char *)(unsigned int)v10,
        v21);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    v26 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    QueryAssociationBrokerService = GetQueryAssociationBrokerService(v11, &v26);
    if ( QueryAssociationBrokerService < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
        (const char *)(unsigned int)QueryAssociationBrokerService,
        v21);
    v25 = 0;
    v13 = v26;
    v14 = *(__int64 (__fastcall **)(void *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v26 + 128LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    v15 = v14(
            v13,
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL),
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL),
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL));
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
        (const char *)(unsigned int)v15,
        2);
    v16 = v25;
    v24 = a2 + 2;
    v17 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v24);
    v18 = v17;
    if ( v16 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v17);
      RoGetAgileReference(0, &GUID_4a226614_2197_526a_a9ff_03025d18e322, v16, v18);
    }
    else
    {
      v28 = 0;
      v24 = (RTL_SRWLOCK *)*v17;
      *v17 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    }
    wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    WindowsDeleteString(newString);
    newString = 0;
    WindowsDeleteString(string);
    string = 0;
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    LauncherClientProvider::GetAppAddedHosts::~GetAppAddedHosts((LauncherClientProvider::GetAppAddedHosts *)v31);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x73,
                           (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.appurihandlerregistration.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x180067f30  mov     [rsp+arg_10], rbx
0x180067f35  push    rsi
0x180067f36  push    rdi
0x180067f37  push    r14
0x180067f39  sub     rsp, 1F0h
0x180067f40  mov     rax, cs:__security_cookie
0x180067f47  xor     rax, rsp
0x180067f4a  mov     [rsp+208h+var_28], rax
0x180067f52  mov     r14, rdx
0x180067f55  mov     rsi, rcx
0x180067f58  lea     rdx, aGetappaddedhos; "GetAppAddedHosts"
0x180067f5f  lea     rcx, [rsp+208h+var_178]
0x180067f67  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180067f6c  lea     rax, ??_7GetAppAddedHosts@LauncherClientProvider@@6B@; const LauncherClientProvider::GetAppAddedHosts::`vftable'
0x180067f73  mov     [rsp+208h+var_178], rax
0x180067f7b  lea     rcx, [rsp+208h+var_178]; this
0x180067f83  call    ?StartActivity@GetAppAddedHosts@LauncherClientProvider@@QEAAXXZ; LauncherClientProvider::GetAppAddedHosts::StartActivity(void)
0x180067f88  nop
0x180067f89  mov     [rsp+208h+var_1A0], 0
0x180067f92  lea     rcx, [rsp+208h+var_1A0]
0x180067f97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067f9c  lea     rdx, [rsp+208h+var_1A0]
0x180067fa1  call    ??$CreateExternalObjectVector@VAppUriHandlerHost@System@Windows@@V?$AgileVector@PEAVAppUriHandlerHost@System@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerHost@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVAppUriHandlerHost@System@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppUriHandlerHost@System@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerHost@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVAppUriHandlerHost@System@Windows@@@5673@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::AppUriHandlerHost,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::AppUriHandlerHost *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::AppUriHandlerHost *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::AppUriHandlerHost *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::System::AppUriHandlerHost *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::AppUriHandlerHost *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::AppUriHandlerHost *>,0> * *)
0x180067fa6  mov     rcx, [rsp+208h]; this
0x180067fae  test    eax, eax
0x180067fb0  jns     short loc_180067FC6
0x180067fb2  mov     r9d, eax; char *
0x180067fb5  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180067fbc  mov     edx, 5Ah ; 'Z'; void *
0x180067fc1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067fc6  mov     rdx, [rsi+8]
0x180067fca  mov     rdx, [rdx+30h]
0x180067fce  lea     rcx, [rsp+208h+var_188]
0x180067fd6  call    ?GetStateRepoUserFromSystemUser@@YA?AV?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEAUIUser@System@Windows@@@Z; GetStateRepoUserFromSystemUser(Windows::System::IUser *)
0x180067fdb  nop
0x180067fdc  lea     rcx, [rsp+208h+var_190]
0x180067fe1  call    ??$GetActivationFactory@UIDynamicAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIDynamicAppUriHandlerGroupStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IDynamicAppUriHandlerGroupStatics>(ushort const *)
0x180067fe6  nop
0x180067fe7  mov     [rsp+208h+string], 0
0x180067ff0  mov     [rsp+208h+newString], 0
0x180067ff9  mov     rbx, [rsi+8]
0x180067ffd  add     rbx, 40h ; '@'
0x180068001  mov     rcx, rbx; SRWLock
0x180068004  call    cs:__imp_AcquireSRWLockShared
0x18006800a  mov     [rsp+208h+var_1B8], rbx
0x18006800f  mov     rbx, [rsi+8]
0x180068013  mov     rcx, [rsp+208h+string]; string
0x180068018  call    cs:__imp_WindowsDeleteString
0x18006801e  mov     [rsp+208h+string], 0
0x180068027  lea     rdx, [rsp+208h+string]; newString
0x18006802c  mov     rcx, [rbx+28h]; string
0x180068030  call    cs:__imp_WindowsDuplicateString
0x180068036  mov     rcx, [rsp+208h]; this
0x18006803e  test    eax, eax
0x180068040  jns     short loc_180068056
0x180068042  mov     r9d, eax; char *
0x180068045  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x18006804c  mov     edx, 64h ; 'd'; void *
0x180068051  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068056  mov     rbx, [rsi+8]
0x18006805a  mov     rcx, [rsp+208h+newString]; string
0x18006805f  call    cs:__imp_WindowsDeleteString
0x180068065  mov     [rsp+208h+newString], 0
0x18006806e  lea     rdx, [rsp+208h+newString]; newString
0x180068073  mov     rcx, [rbx+38h]; string
0x180068077  call    cs:__imp_WindowsDuplicateString
0x18006807d  mov     rcx, [rsp+208h]; this
0x180068085  test    eax, eax
0x180068087  jns     short loc_18006809E
0x180068089  mov     r9d, eax; char *
0x18006808c  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x180068093  mov     edx, 65h ; 'e'; void *
0x180068098  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006809e  lea     rcx, [rsp+208h+var_1B8]
0x1800680a3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800680a8  mov     [rsp+208h+var_1A8], 0
0x1800680b1  lea     rcx, [rsp+208h+var_1A8]
0x1800680b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800680bb  lea     rdx, [rsp+208h+var_1A8]; void **
0x1800680c0  call    ?GetQueryAssociationBrokerService@@YAJAEBU_GUID@@PEAPEAX@Z; GetQueryAssociationBrokerService(_GUID const &,void * *)
0x1800680c5  mov     rcx, [rsp+208h]; this
0x1800680cd  test    eax, eax
0x1800680cf  jns     short loc_1800680E5
0x1800680d1  mov     r9d, eax; char *
0x1800680d4  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x1800680db  mov     edx, 6Ah ; 'j'; void *
0x1800680e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800680e5  mov     [rsp+208h+var_1B0], 0
0x1800680ee  mov     rdi, [rsp+208h+var_1A8]
0x1800680f3  mov     rax, [rdi]
0x1800680f6  mov     rbx, [rax+80h]
0x1800680fd  lea     rcx, [rsp+208h+var_1B0]
0x180068102  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180068107  mov     rdx, [rsi+8]
0x18006810b  lea     rax, [rsp+208h+var_1B0]
0x180068110  mov     [rsp+208h+var_1E0], rax
0x180068115  mov     [rsp+208h+var_1E8], 2; int
0x18006811d  mov     r9, [rdx+30h]
0x180068121  mov     r8, [rdx+28h]
0x180068125  mov     rdx, [rdx+38h]
0x180068129  mov     rcx, rdi
0x18006812c  mov     rax, rbx
0x18006812f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068134  mov     rcx, [rsp+208h]; this
0x18006813c  test    eax, eax
0x18006813e  jns     short loc_180068154
0x180068140  mov     r9d, eax; char *
0x180068143  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.system.launc"...
0x18006814a  mov     edx, 6Fh ; 'o'; void *
0x18006814f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068154  mov     rdi, [rsp+208h+var_1B0]
0x180068159  lea     rax, [r14+10h]
0x18006815d  mov     [rsp+208h+var_1B8], rax
0x180068162  lea     rcx, [rsp+208h+var_1B8]
0x180068167  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18006816c  mov     rbx, rax
0x18006816f  test    rdi, rdi
0x180068172  jz      short loc_180068193
0x180068174  mov     rcx, rax
0x180068177  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006817c  mov     r9, rbx
0x18006817f  mov     r8, rdi
0x180068182  lea     rdx, _GUID_4a226614_2197_526a_a9ff_03025d18e322
0x180068189  xor     ecx, ecx
0x18006818b  call    cs:__imp_RoGetAgileReference
0x180068191  jmp     short loc_1800681BF
0x180068193  mov     [rsp+208h+var_198], 0
0x18006819c  mov     rax, [rax]
0x18006819f  mov     [rsp+208h+var_1B8], rax
0x1800681a4  mov     qword ptr [rbx], 0
0x1800681ab  lea     rcx, [rsp+208h+var_1B8]
0x1800681b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800681b5  lea     rcx, [rsp+208h+var_198]
0x1800681ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800681bf  lea     rcx, [rsp+208h+var_178]
0x1800681c7  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800681cc  nop
0x1800681cd  lea     rcx, [rsp+208h+var_1B0]
0x1800681d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800681d7  nop
0x1800681d8  lea     rcx, [rsp+208h+var_1A8]
0x1800681dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800681e2  nop
0x1800681e3  mov     rcx, [rsp+208h+newString]; string
0x1800681e8  call    cs:__imp_WindowsDeleteString
0x1800681ee  mov     [rsp+208h+newString], 0
0x1800681f7  mov     rcx, [rsp+208h+string]; string
0x1800681fc  call    cs:__imp_WindowsDeleteString
0x180068202  mov     [rsp+208h+string], 0
0x18006820b  lea     rcx, [rsp+208h+var_190]
0x180068210  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180068215  nop
0x180068216  lea     rcx, [rsp+208h+var_188]
0x18006821e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180068223  nop
0x180068224  lea     rcx, [rsp+208h+var_1A0]
0x180068229  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006822e  nop
0x18006822f  lea     rcx, [rsp+208h+var_178]; this
0x180068237  call    ??1GetAppAddedHosts@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::GetAppAddedHosts::~GetAppAddedHosts(void)
0x18006823c  nop
0x18006823d  xor     eax, eax
0x18006823f  jmp     short loc_180068245
0x180068241  mov     eax, dword ptr [rsp+208h+newString]
0x180068245  mov     rcx, [rsp+208h+var_28]
0x18006824d  xor     rcx, rsp; StackCookie
0x180068250  call    __security_check_cookie
0x180068255  mov     rbx, [rsp+208h+arg_10]
0x18006825d  add     rsp, 1F0h
0x180068264  pop     r14
0x180068266  pop     rdi
0x180068267  pop     rsi
0x180068268  retn
```
