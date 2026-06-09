# Windows::Internal::System::AppServiceLauncher::LaunchAppServiceAsync(Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::IAsyncOperation<bool> * *)

- ea: `0x18001e850`
- end: `0x18001eafc`
- name: `?LaunchAppServiceAsync@AppServiceLauncher@System@Internal@Windows@@UEAAJPEAUIUriRuntimeClass@Foundation@4@PEAUIPropertySet@Collections@64@PEAPEAU?$IAsyncOperation@_N@64@@Z`
- size: `684`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d790`
- `0x18001e350`
- `0x180043b30`
- `0x18009b640`

## callees

- `0x180010c04`
- `0x18001d69c`
- `0x18001dd40`
- `0x18001e0e0`
- `0x18001e1a0`
- `0x18001e850`
- `0x18001eb04`
- `0x18001eb40`
- `0x18001f0dc`
- `0x180020468`
- `0x1800204c0`
- `0x1800210f8`
- `0x18004a54c`
- `0x18004aca4`
- `0x18004acdc`
- `0x18006f9c8`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e8c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e9e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ea5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eabc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e8c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e9e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ea5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eabc`

## string_xrefs

- `0x18001e8f8`: `onecoreuap\shell\windows.system.launcher\launcherappservicelib\lib\windows.internal.system.appservicelauncher.cpp`
- `0x18001e9b7`: `onecoreuap\shell\windows.system.launcher\launcherappservicelib\lib\windows.internal.system.appservicelauncher.cpp`
- `0x18001e87b`: `LaunchAppServiceAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::System::AppServiceLauncher::LaunchAppServiceAsync(
        __int64 a1,
        __int64 a2,
        const char *a3,
        _QWORD *a4)
{
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 PackageFamilyNameAndServiceName; // rbx
  int v11; // ecx
  _QWORD *v12; // r8
  _QWORD *v13; // rdx
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-228h]
  __int64 v18; // [rsp+20h] [rbp-228h]
  int v19; // [rsp+20h] [rbp-228h]
  __int64 v20; // [rsp+28h] [rbp-220h]
  HSTRING string; // [rsp+30h] [rbp-218h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-210h]
  _QWORD v23[4]; // [rsp+40h] [rbp-208h] BYREF
  _QWORD v24[4]; // [rsp+60h] [rbp-1E8h] BYREF
  _BYTE v25[32]; // [rsp+80h] [rbp-1C8h] BYREF
  _BYTE v26[32]; // [rsp+A0h] [rbp-1A8h] BYREF
  void **v27; // [rsp+C0h] [rbp-188h] BYREF
  _BYTE v28[272]; // [rsp+C8h] [rbp-180h] BYREF
  _BYTE v29[8]; // [rsp+1D8h] [rbp-70h] BYREF
  _BYTE v30[48]; // [rsp+1E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v27,
    "LaunchAppServiceAsync");
  v27 = &LauncherClientProvider::LaunchAppServiceAsync::`vftable';
  LauncherClientProvider::LaunchAppServiceAsync::StartActivity((LauncherClientProvider::LaunchAppServiceAsync *)&v27);
  *a4 = 0;
  string = 0;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 136LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(a2, &string);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\launcherappservicelib\\lib\\windows.internal.system.apps"
                    "ervicelauncher.cpp",
      (const char *)(unsigned int)v8,
      v17);
LABEL_11:
    WindowsDeleteString(string);
    string = 0;
    v27 = &LauncherClientProvider::LaunchAppServiceAsync::`vftable';
    wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v27);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v30);
    wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v29);
    wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(v28);
    return v9;
  }
  std::wstring::wstring(v23);
  std::wstring::wstring(v24);
  try
  {
    PackageFamilyNameAndServiceName = _GetPackageFamilyNameAndServiceName();
    std::wstring::operator=(v24, PackageFamilyNameAndServiceName + 32);
    std::wstring::operator=(v23, PackageFamilyNameAndServiceName);
    std::wstring::_Tidy_deallocate(v26);
    std::wstring::_Tidy_deallocate(v25);
    v12 = v23;
    if ( v23[3] > 7u )
      LODWORD(v12) = v23[0];
    v13 = v24;
    if ( v24[3] > 7u )
      LODWORD(v13) = v24[0];
    v20 = (__int64)a4;
    v18 = a2;
    v14 = a3;
  }
  catch ( ... )
  {
    v22 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0xCD,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\launcherappservicelib\\lib\\windows.internal.syste"
                          "m.appservicelauncher.cpp",
            v14);
    std::tuple<std::wstring,std::wstring>::~tuple<std::wstring,std::wstring>(v23);
    WindowsDeleteString(string);
    string = 0;
    LauncherClientProvider::LaunchAppServiceAsync::~LaunchAppServiceAsync((LauncherClientProvider::LaunchAppServiceAsync *)&v27);
    return v22;
  }
  v15 = Windows::Internal::System::AppServiceLauncher::OpenAppServiceAndSendMessageAsync(
          v11,
          (_DWORD)v13,
          (_DWORD)v12,
          (_DWORD)v14,
          v18,
          v20);
  v9 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\launcherappservicelib\\lib\\windows.internal.system.apps"
                    "ervicelauncher.cpp",
      (const char *)(unsigned int)v15,
      v19);
    std::wstring::_Tidy_deallocate(v24);
    std::wstring::_Tidy_deallocate(v23);
    goto LABEL_11;
  }
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v27);
  std::wstring::_Tidy_deallocate(v24);
  std::wstring::_Tidy_deallocate(v23);
  WindowsDeleteString(string);
  string = 0;
  v27 = &LauncherClientProvider::LaunchAppServiceAsync::`vftable';
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v27);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v30);
  wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v29);
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(v28);
  return 0;
}

```

## disassembly

```asm
0x18001e850  push    rbx
0x18001e852  push    rsi
0x18001e853  push    r12
0x18001e855  push    r14
0x18001e857  push    r15
0x18001e859  sub     rsp, 220h
0x18001e860  mov     rax, cs:__security_cookie
0x18001e867  xor     rax, rsp
0x18001e86a  mov     [rsp+248h+var_38], rax
0x18001e872  mov     r14, r9
0x18001e875  mov     r15, r8
0x18001e878  mov     rsi, rdx
0x18001e87b  lea     rdx, aLaunchappservi; "LaunchAppServiceAsync"
0x18001e882  lea     rcx, [rsp+248h+var_188]
0x18001e88a  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001e88f  lea     r12, ??_7LaunchAppServiceAsync@LauncherClientProvider@@6B@; const LauncherClientProvider::LaunchAppServiceAsync::`vftable'
0x18001e896  mov     [rsp+248h+var_188], r12
0x18001e89e  lea     rcx, [rsp+248h+var_188]; this
0x18001e8a6  call    ?StartActivity@LaunchAppServiceAsync@LauncherClientProvider@@QEAAXXZ; LauncherClientProvider::LaunchAppServiceAsync::StartActivity(void)
0x18001e8ab  nop
0x18001e8ac  mov     qword ptr [r14], 0
0x18001e8b3  mov     [rsp+248h+string], 0
0x18001e8bc  mov     rax, [rsi]
0x18001e8bf  mov     rbx, [rax+88h]
0x18001e8c6  xor     ecx, ecx; string
0x18001e8c8  call    cs:__imp_WindowsDeleteString
0x18001e8ce  mov     [rsp+248h+string], 0
0x18001e8d7  lea     rdx, [rsp+248h+string]
0x18001e8dc  mov     rcx, rsi
0x18001e8df  mov     rax, rbx
0x18001e8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8e7  mov     ebx, eax
0x18001e8e9  test    eax, eax
0x18001e8eb  jns     short loc_18001E90E
0x18001e8ed  mov     rcx, [rsp+248h]; this
0x18001e8f5  mov     r9d, eax; char *
0x18001e8f8  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.system.launc"...
0x18001e8ff  mov     edx, 0C6h; void *
0x18001e904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e909  jmp     loc_18001E9DE
0x18001e90e  lea     rcx, [rsp+248h+var_208]
0x18001e913  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e918  lea     rcx, [rsp+248h+var_1E8]
0x18001e91d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e922  nop
0x18001e923  lea     rdx, [rsp+248h+string]
0x18001e928  lea     rcx, [rsp+248h+var_1C8]
0x18001e930  call    ?_GetPackageFamilyNameAndServiceName@@YA?AV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@AEAVHString@Wrappers@WRL@Microsoft@@@Z; _GetPackageFamilyNameAndServiceName(Microsoft::WRL::Wrappers::HString &)
0x18001e935  mov     rbx, rax
0x18001e938  lea     rdx, [rax+20h]
0x18001e93c  lea     rcx, [rsp+248h+var_1E8]
0x18001e941  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001e946  mov     rdx, rbx
0x18001e949  lea     rcx, [rsp+248h+var_208]
0x18001e94e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001e953  lea     rcx, [rsp+248h+var_1A8]
0x18001e95b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e960  lea     rcx, [rsp+248h+var_1C8]
0x18001e968  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e96d  nop
0x18001e96e  lea     r8, [rsp+248h+var_208]
0x18001e973  cmp     [rsp+248h+var_1F0], 7
0x18001e979  cmova   r8, [rsp+248h+var_208]
0x18001e97f  lea     rdx, [rsp+248h+var_1E8]
0x18001e984  cmp     [rsp+248h+var_1D0], 7
0x18001e98a  cmova   rdx, [rsp+248h+var_1E8]
0x18001e990  mov     [rsp+248h+var_220], r14
0x18001e995  mov     qword ptr [rsp+248h+var_228], rsi; int
0x18001e99a  mov     r9, r15
0x18001e99d  call    ?OpenAppServiceAndSendMessageAsync@AppServiceLauncher@System@Internal@Windows@@AEAAJPEBG0PEAUIPropertySet@Collections@Foundation@4@PEAUIUriRuntimeClass@74@PEAPEAU?$IAsyncOperation@_N@74@@Z; Windows::Internal::System::AppServiceLauncher::OpenAppServiceAndSendMessageAsync(ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::IAsyncOperation<bool> * *)
0x18001e9a2  mov     ebx, eax
0x18001e9a4  test    eax, eax
0x18001e9a6  jns     loc_18001EA35
0x18001e9ac  mov     rcx, [rsp+248h]; this
0x18001e9b4  mov     r9d, eax; char *
0x18001e9b7  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.system.launc"...
0x18001e9be  mov     edx, 0D3h; void *
0x18001e9c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9c8  nop
0x18001e9c9  lea     rcx, [rsp+248h+var_1E8]
0x18001e9ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e9d3  lea     rcx, [rsp+248h+var_208]
0x18001e9d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e9dd  nop
0x18001e9de  mov     rcx, [rsp+248h+string]; string
0x18001e9e3  call    cs:__imp_WindowsDeleteString
0x18001e9e9  mov     [rsp+248h+string], 0
0x18001e9f2  mov     [rsp+248h+var_188], r12
0x18001e9fa  lea     rcx, [rsp+248h+var_188]
0x18001ea02  call    ?Destroy@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ea07  lea     rcx, [rsp+248h+var_68]; this
0x18001ea0f  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001ea14  lea     rcx, [rsp+248h+var_70]
0x18001ea1c  call    ?reset@?$shared_object@V?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001ea21  lea     rcx, [rsp+248h+var_180]
0x18001ea29  call    ??1?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001ea2e  mov     eax, ebx
0x18001ea30  jmp     loc_18001EADC
0x18001ea35  lea     rcx, [rsp+248h+var_188]
0x18001ea3d  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001ea42  nop
0x18001ea43  lea     rcx, [rsp+248h+var_1E8]
0x18001ea48  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ea4d  lea     rcx, [rsp+248h+var_208]
0x18001ea52  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ea57  nop
0x18001ea58  mov     rcx, [rsp+248h+string]; string
0x18001ea5d  call    cs:__imp_WindowsDeleteString
0x18001ea63  mov     [rsp+248h+string], 0
0x18001ea6c  mov     [rsp+248h+var_188], r12
0x18001ea74  lea     rcx, [rsp+248h+var_188]
0x18001ea7c  call    ?Destroy@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ea81  lea     rcx, [rsp+248h+var_68]; this
0x18001ea89  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001ea8e  lea     rcx, [rsp+248h+var_70]
0x18001ea96  call    ?reset@?$shared_object@V?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001ea9b  lea     rcx, [rsp+248h+var_180]
0x18001eaa3  call    ??1?$ActivityData@VLauncherClientProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LauncherClientProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001eaa8  xor     eax, eax
0x18001eaaa  jmp     short loc_18001EADC
0x18001eaac  lea     rcx, [rsp+248h+var_208]
0x18001eab1  call    ??1?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::tuple<std::wstring,std::wstring>::~tuple<std::wstring,std::wstring>(void)
0x18001eab6  nop
0x18001eab7  mov     rcx, [rsp+248h+string]; string
0x18001eabc  call    cs:__imp_WindowsDeleteString
0x18001eac2  mov     [rsp+248h+string], 0
0x18001eacb  lea     rcx, [rsp+248h+var_188]; this
0x18001ead3  call    ??1LaunchAppServiceAsync@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::LaunchAppServiceAsync::~LaunchAppServiceAsync(void)
0x18001ead8  mov     eax, [rsp+248h+var_210]
0x18001eadc  mov     rcx, [rsp+248h+var_38]
0x18001eae4  xor     rcx, rsp; StackCookie
0x18001eae7  call    __security_check_cookie
0x18001eaec  add     rsp, 220h
0x18001eaf3  pop     r15
0x18001eaf5  pop     r14
0x18001eaf7  pop     r12
0x18001eaf9  pop     rsi
0x18001eafa  pop     rbx
0x18001eafb  retn
```
