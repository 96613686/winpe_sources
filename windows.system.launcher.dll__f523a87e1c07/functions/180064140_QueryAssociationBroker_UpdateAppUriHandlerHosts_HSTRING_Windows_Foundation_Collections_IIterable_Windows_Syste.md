# QueryAssociationBroker::UpdateAppUriHandlerHosts(HSTRING__ *,Windows::Foundation::Collections::IIterable<Windows::System::AppUriHandlerHost *> *)

- ea: `0x180064140`
- end: `0x180064654`
- name: `?UpdateAppUriHandlerHosts@QueryAssociationBroker@@UEAAJPEAUHSTRING__@@PEAU?$IIterable@PEAVAppUriHandlerHost@System@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `1300`
- prototype: `__int64 __fastcall(__int64, HSTRING, __int64)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18001d10c`
- `0x180063cd8`
- `0x180063db8`
- `0x180063de4`
- `0x180063ec0`
- `0x180063f24`
- `0x180063fe4`
- `0x18006403c`
- `0x180064140`
- `0x18006465c`
- `0x180064da8`
- `0x180066cfc`
- `0x180067840`
- `0x18008a030`
- `0x1800a0ee8`
- `0x1800aae88`
- `0x1800b217c`
- `0x1800b2238`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180064543`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180064543`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180064501`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800645b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180064501`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800645b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006420e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800643cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006420e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800643cf`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180064556`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180064556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006435e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800643ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006435e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800643ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800642de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800642de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064611`

## string_xrefs

- `0x1800641d5`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180064223`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006430c`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006433a`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800643e4`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180064411`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180064473`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800644ae`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180064516`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180064568`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800645c9`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006417c`: `UpdateAppUriHandlerHosts`
- `0x180064202`: `AppUriHandlers`
- `0x180064367`: `VerifyHostedAppUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall QueryAssociationBroker::UpdateAppUriHandlerHosts(__int64 a1, HSTRING a2, __int64 a3)
{
  const unsigned __int16 *StringRawBuffer; // rbx
  int SystemApplicationDataKey; // eax
  unsigned int v7; // eax
  __int64 (__fastcall ****v9)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  int v12; // eax
  const unsigned __int16 *v13; // rdi
  const unsigned __int16 *v14; // rbx
  const WCHAR *v15; // rax
  unsigned int v16; // eax
  BOOL v17; // r15d
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  unsigned int v22; // eax
  const char *v23; // r9
  unsigned int v24; // eax
  int phkResult; // [rsp+20h] [rbp-358h]
  unsigned int phkResulta; // [rsp+20h] [rbp-358h]
  unsigned int phkResultb; // [rsp+20h] [rbp-358h]
  unsigned int phkResultc; // [rsp+20h] [rbp-358h]
  char v29[8]; // [rsp+30h] [rbp-348h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-340h] BYREF
  HKEY v31; // [rsp+40h] [rbp-338h] BYREF
  HSTRING string; // [rsp+48h] [rbp-330h] BYREF
  __int64 v33; // [rsp+50h] [rbp-328h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-320h] BYREF
  HKEY v35; // [rsp+60h] [rbp-318h] BYREF
  BYTE v36[8]; // [rsp+68h] [rbp-310h] BYREF
  char v37[8]; // [rsp+70h] [rbp-308h] BYREF
  int v38; // [rsp+78h] [rbp-300h]
  __int64 v39; // [rsp+88h] [rbp-2F0h] BYREF
  int v40; // [rsp+90h] [rbp-2E8h]
  __int64 v41; // [rsp+98h] [rbp-2E0h]
  _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-2D8h] BYREF
  _QWORD v43[42]; // [rsp+B0h] [rbp-2C8h] BYREF
  _QWORD v44[42]; // [rsp+200h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v43);
  v43[0] = &LauncherServiceProvider::UpdateAppUriHandlerHosts::`vftable';
  LauncherServiceProvider::UpdateAppUriHandlerHosts::StartActivity(
    (LauncherServiceProvider::UpdateAppUriHandlerHosts *)v43,
    StringRawBuffer);
  hKey = 0;
  SystemApplicationDataKey = GetSystemApplicationDataKey(a2, &hKey);
  if ( SystemApplicationDataKey < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x584,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)SystemApplicationDataKey,
      phkResult);
  v35 = 0;
  v7 = RegOpenKeyExW(hKey, L"AppUriHandlers", 0, 0xF003Fu, &v35);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x588,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)v7,
      phkResulta);
  wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
    v37,
    a3);
  v39 = 0;
  v40 = -1;
  v41 = 0;
  while ( v38 != -1 )
  {
    v9 = (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::operator*(v37);
    string = 0;
    v10 = *v9;
    v11 = (**v9)[6];
    WindowsDeleteString(0);
    string = 0;
    v12 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))v11)(v10, &string);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58E,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v12,
        phkResulta);
    if ( !string )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x80070057LL,
        phkResulta);
    v13 = WindowsGetStringRawBuffer(string, 0);
    v14 = WindowsGetStringRawBuffer(a2, 0);
    wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v44);
    v44[0] = &LauncherServiceProvider::VerifyHostedAppUri::`vftable';
    LauncherServiceProvider::VerifyHostedAppUri::StartActivity(
      (LauncherServiceProvider::VerifyHostedAppUri *)v44,
      v14,
      v13);
    v31 = 0;
    v15 = WindowsGetStringRawBuffer(string, 0);
    v16 = RegOpenKeyExW(v35, v15, 0, 0xF003Fu, &v31);
    if ( v16 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x595,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)v16,
        phkResultb);
    if ( !IsAppUriHandlerValidationDelegated(v31) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x598,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)0x80070005LL,
        phkResultb);
    v17 = IsAppUriHandlerEnabledByCustomCapability(v31);
    v33 = 0;
    v18 = *v9;
    v19 = ***v9;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v20 = v19(v18, &GUID_3a0bee95_29e4_51bf_8095_a3c068e3c72a, &v33);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v20,
        phkResultb);
    v29[0] = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v33 + 48LL))(v33, v29);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A2,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v21,
        phkResultb);
    if ( v17 != (v29[0] != 0) )
    {
      *(_DWORD *)Data = v29[0] != 0;
      v22 = RegSetValueExW(v31, L"IsEnabledByCapability", 0, 4u, Data, 4u);
      if ( v22 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x5A8,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)v22,
          phkResultc);
    }
    SystemTime = 0;
    *(_QWORD *)Data = 0;
    GetSystemTime(&SystemTime);
    if ( !SystemTimeToFileTime(&SystemTime, (LPFILETIME)Data) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        v23);
    *(_QWORD *)v36 = *(unsigned int *)Data + ((unsigned __int64)*(unsigned int *)&Data[4] << 32);
    v24 = RegSetValueExW(v31, L"LastSuccessfulValidationTime", 0, 0xBu, v36, 8u);
    if ( v24 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x5AC,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)v24,
        phkResulta);
    wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
    LauncherServiceProvider::VerifyHostedAppUri::~VerifyHostedAppUri((LauncherServiceProvider::VerifyHostedAppUri *)v44);
    WindowsDeleteString(string);
    wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::operator++(v37);
  }
  wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v39);
  wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v37);
  wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v43);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  LauncherServiceProvider::UpdateAppUriHandlerHosts::~UpdateAppUriHandlerHosts((LauncherServiceProvider::UpdateAppUriHandlerHosts *)v43);
  return 0;
}

```

## disassembly

```asm
0x180064140  mov     [rsp+arg_0], rbx
0x180064145  mov     [rsp+arg_10], rsi
0x18006414a  push    rdi
0x18006414b  push    r14
0x18006414d  push    r15
0x18006414f  sub     rsp, 360h
0x180064156  mov     rax, cs:__security_cookie
0x18006415d  xor     rax, rsp
0x180064160  mov     [rsp+378h+var_28], rax
0x180064168  mov     rdi, r8
0x18006416b  mov     r14, rdx
0x18006416e  xor     edx, edx; length
0x180064170  mov     rcx, r14; string
0x180064173  call    cs:__imp_WindowsGetStringRawBuffer
0x180064179  mov     rbx, rax
0x18006417c  lea     rdx, aUpdateappuriha; "UpdateAppUriHandlerHosts"
0x180064183  lea     rcx, [rsp+378h+var_2C8]; struct wil::details::IFailureCallback *
0x18006418b  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180064190  lea     rax, ??_7UpdateAppUriHandlerHosts@LauncherServiceProvider@@6B@; const LauncherServiceProvider::UpdateAppUriHandlerHosts::`vftable'
0x180064197  mov     [rsp+378h+var_2C8], rax
0x18006419f  mov     rdx, rbx; unsigned __int16 *
0x1800641a2  lea     rcx, [rsp+378h+var_2C8]; this
0x1800641aa  call    ?StartActivity@UpdateAppUriHandlerHosts@LauncherServiceProvider@@QEAAXPEBG@Z; LauncherServiceProvider::UpdateAppUriHandlerHosts::StartActivity(ushort const *)
0x1800641af  nop
0x1800641b0  mov     [rsp+378h+hKey], 0
0x1800641b9  lea     rdx, [rsp+378h+hKey]; HKEY *
0x1800641be  mov     rcx, r14; HSTRING
0x1800641c1  call    ?GetSystemApplicationDataKey@@YAJPEAUHSTRING__@@PEAPEAUHKEY__@@@Z; GetSystemApplicationDataKey(HSTRING__ *,HKEY__ * *)
0x1800641c6  mov     rcx, [rsp+378h]; this
0x1800641ce  test    eax, eax
0x1800641d0  jns     short loc_1800641E6
0x1800641d2  mov     r9d, eax; char *
0x1800641d5  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800641dc  mov     edx, 584h; void *
0x1800641e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800641e6  mov     [rsp+378h+var_318], 0
0x1800641ef  lea     rax, [rsp+378h+var_318]
0x1800641f4  mov     [rsp+378h+phkResult], rax; int
0x1800641f9  mov     r9d, 0F003Fh; samDesired
0x1800641ff  xor     r8d, r8d; ulOptions
0x180064202  lea     rdx, aAppurihandlers; "AppUriHandlers"
0x180064209  mov     rcx, [rsp+378h+hKey]; hKey
0x18006420e  call    cs:__imp_RegOpenKeyExW
0x180064214  mov     rcx, [rsp+378h]; this
0x18006421c  test    eax, eax
0x18006421e  jz      short loc_180064234
0x180064220  mov     r9d, eax; char *
0x180064223  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18006422a  mov     edx, 588h; void *
0x18006422f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180064234  mov     rdx, rdi
0x180064237  lea     rcx, [rsp+378h+var_308]
0x18006423c  call    ??0iterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAVAppUriHandlerHost@System@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::System::AppUriHandlerHost *> *)
0x180064241  nop
0x180064242  mov     [rsp+378h+var_2F0], 0
0x18006424e  mov     [rsp+378h+var_2E8], 0FFFFFFFFh
0x180064259  mov     [rsp+378h+var_2E0], 0
0x180064265  cmp     [rsp+378h+var_300], 0FFFFFFFFh
0x18006426a  jnz     short loc_1800642BC
0x18006426c  lea     rcx, [rsp+378h+var_2F0]
0x180064274  call    ??1iterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180064279  nop
0x18006427a  lea     rcx, [rsp+378h+var_308]
0x18006427f  call    ??1iterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180064284  lea     rcx, [rsp+378h+var_2C8]
0x18006428c  call    ?Stop@?$ActivityBase@VLauncherServiceProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180064291  nop
0x180064292  lea     rcx, [rsp+378h+var_318]
0x180064297  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006429c  nop
0x18006429d  lea     rcx, [rsp+378h+hKey]
0x1800642a2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800642a7  nop
0x1800642a8  lea     rcx, [rsp+378h+var_2C8]; this
0x1800642b0  call    ??1UpdateAppUriHandlerHosts@LauncherServiceProvider@@QEAA@XZ; LauncherServiceProvider::UpdateAppUriHandlerHosts::~UpdateAppUriHandlerHosts(void)
0x1800642b5  xor     eax, eax
0x1800642b7  jmp     loc_18006462A
0x1800642bc  lea     rcx, [rsp+378h+var_308]
0x1800642c1  call    ??Diterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIAppUriHandlerHost@System@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x1800642c6  mov     rsi, rax
0x1800642c9  mov     [rsp+378h+string], 0
0x1800642d2  mov     rdi, [rax]
0x1800642d5  mov     rdx, [rdi]
0x1800642d8  mov     rbx, [rdx+30h]
0x1800642dc  xor     ecx, ecx; string
0x1800642de  call    cs:__imp_WindowsDeleteString
0x1800642e4  mov     [rsp+378h+string], 0
0x1800642ed  lea     rdx, [rsp+378h+string]
0x1800642f2  mov     rcx, rdi
0x1800642f5  mov     rax, rbx
0x1800642f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642fd  mov     rcx, [rsp+378h]; this
0x180064305  test    eax, eax
0x180064307  jns     short loc_18006431D
0x180064309  mov     r9d, eax; char *
0x18006430c  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180064313  mov     edx, 58Eh; void *
0x180064318  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006431d  mov     rcx, [rsp+378h+string]; string
0x180064322  test    rcx, rcx
0x180064325  setnz   al
0x180064328  mov     r10, [rsp+378h]
0x180064330  test    al, al
0x180064332  jnz     short loc_18006434E
0x180064334  mov     r9d, 80070057h; char *
0x18006433a  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180064341  mov     edx, 58Fh; void *
0x180064346  mov     rcx, r10; this
0x180064349  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006434e  xor     edx, edx; length
0x180064350  call    cs:__imp_WindowsGetStringRawBuffer
0x180064356  mov     rdi, rax
0x180064359  xor     edx, edx; length
0x18006435b  mov     rcx, r14; string
0x18006435e  call    cs:__imp_WindowsGetStringRawBuffer
0x180064364  mov     rbx, rax
0x180064367  lea     rdx, aVerifyhostedap; "VerifyHostedAppUri"
0x18006436e  lea     rcx, [rsp+378h+var_178]; struct wil::details::IFailureCallback *
0x180064376  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18006437b  lea     rax, ??_7VerifyHostedAppUri@LauncherServiceProvider@@6B@; const LauncherServiceProvider::VerifyHostedAppUri::`vftable'
0x180064382  mov     [rsp+378h+var_178], rax
0x18006438a  mov     r8, rdi; unsigned __int16 *
0x18006438d  mov     rdx, rbx; unsigned __int16 *
0x180064390  lea     rcx, [rsp+378h+var_178]; this
0x180064398  call    ?StartActivity@VerifyHostedAppUri@LauncherServiceProvider@@QEAAXPEBG0@Z; LauncherServiceProvider::VerifyHostedAppUri::StartActivity(ushort const *,ushort const *)
0x18006439d  nop
0x18006439e  mov     [rsp+378h+var_338], 0
0x1800643a7  xor     edx, edx; length
0x1800643a9  mov     rcx, [rsp+378h+string]; string
0x1800643ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800643b4  lea     rcx, [rsp+378h+var_338]
0x1800643b9  mov     [rsp+378h+phkResult], rcx; int
0x1800643be  mov     r9d, 0F003Fh; samDesired
0x1800643c4  xor     r8d, r8d; ulOptions
0x1800643c7  mov     rdx, rax; lpSubKey
0x1800643ca  mov     rcx, [rsp+378h+var_318]; hKey
0x1800643cf  call    cs:__imp_RegOpenKeyExW
0x1800643d5  mov     rcx, [rsp+378h]; this
0x1800643dd  test    eax, eax
0x1800643df  jz      short loc_1800643F5
0x1800643e1  mov     r9d, eax; char *
0x1800643e4  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800643eb  mov     edx, 595h; void *
0x1800643f0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800643f5  mov     rcx, [rsp+378h+var_338]; HKEY
0x1800643fa  call    ?IsAppUriHandlerValidationDelegated@@YA_NPEAUHKEY__@@@Z; IsAppUriHandlerValidationDelegated(HKEY__ *)
0x1800643ff  mov     rcx, [rsp+378h]; this
0x180064407  test    al, al
0x180064409  jnz     short loc_180064422
0x18006440b  mov     r9d, 80070005h; char *
0x180064411  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180064418  mov     edx, 598h; void *
0x18006441d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064422  mov     rcx, [rsp+378h+var_338]; HKEY
0x180064427  call    ?IsAppUriHandlerEnabledByCustomCapability@@YA_NPEAUHKEY__@@@Z; IsAppUriHandlerEnabledByCustomCapability(HKEY__ *)
0x18006442c  movzx   r15d, al
0x180064430  mov     [rsp+378h+var_328], 0
0x180064439  mov     rdi, [rsi]
0x18006443c  mov     rdx, [rdi]
0x18006443f  mov     rbx, [rdx]
0x180064442  lea     rcx, [rsp+378h+var_328]
0x180064447  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006444c  lea     r8, [rsp+378h+var_328]
0x180064451  lea     rdx, _GUID_3a0bee95_29e4_51bf_8095_a3c068e3c72a
0x180064458  mov     rcx, rdi
0x18006445b  mov     rax, rbx
0x18006445e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064463  nop
0x180064464  mov     rcx, [rsp+378h]; this
0x18006446c  test    eax, eax
0x18006446e  jns     short loc_180064484
0x180064470  mov     r9d, eax; char *
0x180064473  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18006447a  mov     edx, 59Fh; void *
0x18006447f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064484  mov     [rsp+378h+var_348], 0
0x180064489  mov     rcx, [rsp+378h+var_328]
0x18006448e  mov     rax, [rcx]
0x180064491  lea     rdx, [rsp+378h+var_348]
0x180064496  mov     rax, [rax+30h]
0x18006449a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006449f  mov     rcx, [rsp+378h]; this
0x1800644a7  test    eax, eax
0x1800644a9  jns     short loc_1800644BF
0x1800644ab  mov     r9d, eax; char *
0x1800644ae  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800644b5  mov     edx, 5A2h; void *
0x1800644ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800644bf  xor     ecx, ecx
0x1800644c1  mov     dl, [rsp+378h+var_348]
0x1800644c5  test    dl, dl
0x1800644c7  setnz   cl
0x1800644ca  cmp     r15d, ecx
0x1800644cd  jz      short loc_180064527
0x1800644cf  xor     eax, eax
0x1800644d1  test    dl, dl
0x1800644d3  setnz   al
0x1800644d6  mov     dword ptr [rsp+378h+Data], eax
0x1800644da  mov     [rsp+378h+cbData], 4; cbData
0x1800644e2  lea     rax, [rsp+378h+Data]
0x1800644e7  mov     [rsp+378h+phkResult], rax; unsigned int
0x1800644ec  mov     r9d, 4; dwType
0x1800644f2  xor     r8d, r8d; Reserved
0x1800644f5  lea     rdx, aIsenabledbycap; "IsEnabledByCapability"
0x1800644fc  mov     rcx, [rsp+378h+var_338]; hKey
0x180064501  call    cs:__imp_RegSetValueExW
0x180064507  mov     rcx, [rsp+378h]; this
0x18006450f  test    eax, eax
0x180064511  jz      short loc_180064527
0x180064513  mov     r9d, eax; char *
0x180064516  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18006451d  mov     edx, 5A8h; void *
0x180064522  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180064527  xorps   xmm0, xmm0
0x18006452a  movups  xmmword ptr [rsp+378h+SystemTime.wYear], xmm0
0x180064532  mov     qword ptr [rsp+378h+Data], 0
0x18006453b  lea     rcx, [rsp+378h+SystemTime]; lpSystemTime
0x180064543  call    cs:__imp_GetSystemTime
0x180064549  lea     rdx, [rsp+378h+Data]; lpFileTime
0x18006454e  lea     rcx, [rsp+378h+SystemTime]; lpSystemTime
0x180064556  call    cs:__imp_SystemTimeToFileTime
0x18006455c  mov     rcx, [rsp+378h]; this
0x180064564  test    eax, eax
0x180064566  jnz     short loc_180064579
0x180064568  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x18006456f  mov     edx, 0A5h; void *
0x180064574  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180064579  mov     ecx, dword ptr [rsp+378h+Data+4]
0x18006457d  shl     rcx, 20h
0x180064581  mov     eax, dword ptr [rsp+378h+Data]
0x180064585  add     rcx, rax
0x180064588  mov     qword ptr [rsp+378h+var_310], rcx
0x18006458d  mov     [rsp+378h+cbData], 8; cbData
0x180064595  lea     rax, [rsp+378h+var_310]
0x18006459a  mov     [rsp+378h+phkResult], rax; unsigned int
0x18006459f  mov     r9d, 0Bh; dwType
0x1800645a5  xor     r8d, r8d; Reserved
0x1800645a8  lea     rdx, aLastsuccessful; "LastSuccessfulValidationTime"
0x1800645af  mov     rcx, [rsp+378h+var_338]; hKey
0x1800645b4  call    cs:__imp_RegSetValueExW
0x1800645ba  mov     rcx, [rsp+378h]; this
0x1800645c2  test    eax, eax
0x1800645c4  jz      short loc_1800645DA
0x1800645c6  mov     r9d, eax; char *
0x1800645c9  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800645d0  mov     edx, 5ACh; void *
0x1800645d5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800645da  lea     rcx, [rsp+378h+var_178]
0x1800645e2  call    ?Stop@?$ActivityBase@VLauncherServiceProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800645e7  nop
0x1800645e8  lea     rcx, [rsp+378h+var_328]
0x1800645ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800645f2  nop
0x1800645f3  lea     rcx, [rsp+378h+var_338]
0x1800645f8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800645fd  nop
0x1800645fe  lea     rcx, [rsp+378h+var_178]; this
0x180064606  call    ??1VerifyHostedAppUri@LauncherServiceProvider@@QEAA@XZ; LauncherServiceProvider::VerifyHostedAppUri::~VerifyHostedAppUri(void)
0x18006460b  nop
0x18006460c  mov     rcx, [rsp+378h+string]; string
0x180064611  call    cs:__imp_WindowsDeleteString
0x180064617  lea     rcx, [rsp+378h+var_308]
0x18006461c  call    ??Eiterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV012@XZ; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::operator++(void)
0x180064621  jmp     loc_180064265
0x180064626  mov     eax, dword ptr [rsp+378h+Data]
0x18006462a  mov     rcx, [rsp+378h+var_28]
0x180064632  xor     rcx, rsp; StackCookie
0x180064635  call    __security_check_cookie
0x18006463a  lea     r11, [rsp+378h+var_18]
0x180064642  mov     rbx, [r11+20h]
0x180064646  mov     rsi, [r11+30h]
0x18006464a  mov     rsp, r11
0x18006464d  pop     r15
0x18006464f  pop     r14
0x180064651  pop     rdi
0x180064652  retn
```
