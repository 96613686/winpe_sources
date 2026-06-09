# IsFullUriValidForRegisteredApp(HSTRING__ *,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,bool *)

- ea: `0x18007da9c`
- end: `0x18007de83`
- name: `?IsFullUriValidForRegisteredApp@@YAJPEAUHSTRING__@@PEAUIUriRuntimeClass@Foundation@Windows@@0PEA_N@Z`
- size: `999`
- prototype: `__int64 __fastcall(HSTRING, struct Windows::Foundation::IUriRuntimeClass *, HSTRING, bool *)`
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c520`
- `0x180029184`
- `0x18007d580`
- `0x18007da10`

## callees

- `0x180010c04`
- `0x18001d10c`
- `0x18001eb04`
- `0x180028b70`
- `0x1800329a0`
- `0x1800491d0`
- `0x18004a844`
- `0x18004acdc`
- `0x180066cfc`
- `0x18007a2f8`
- `0x18007da9c`
- `0x18008a030`
- `0x1800d6c74`
- `0x1800d7284`
- `0x1800d7d5c`
- `0x1800d7e3c`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dc30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dc68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dd72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dc30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dc68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dd72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007db31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007db3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007dc4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007dcd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007db31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007db3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007dc4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007dcd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dae9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dbfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007de31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007de58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dae9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dbfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007de31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007de58`

## string_xrefs

- `0x18007db14`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007db95`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007dbe6`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007dc9e`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007ddd4`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18007dc24`: `AppUriHandlers`
- `0x18007db48`: `AppUriHandlerValidation`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IsFullUriValidForRegisteredApp(
        HSTRING a1,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        HSTRING a3,
        bool *a4)
{
  __int64 (__fastcall *v8)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v12; // rbx
  int SystemApplicationDataKey; // eax
  int v14; // eax
  const WCHAR *v15; // rax
  int v16; // eax
  __int64 v17; // r8
  LPCWSTR *v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rax
  const WCHAR *v21; // rdx
  __int64 v22; // r8
  int v23; // eax
  LPCWSTR *v24; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HSTRING v29; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v31; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v33; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v34; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h]
  unsigned __int64 v37; // [rsp+78h] [rbp-88h]
  _BYTE v38[32]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v39[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  *a4 = 0;
  string = 0;
  v8 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 88LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(a2, &string);
  v10 = v9;
  if ( v9 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v12 = WindowsGetStringRawBuffer(a1, 0);
    wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v39);
    v39[0] = &LauncherClientProvider::AppUriHandlerValidation::`vftable';
    LauncherClientProvider::AppUriHandlerValidation::StartActivity(
      (LauncherClientProvider::AppUriHandlerValidation *)v39,
      v12,
      StringRawBuffer);
    hKey = 0;
    SystemApplicationDataKey = GetSystemApplicationDataKey(a1, &hKey);
    v10 = SystemApplicationDataKey;
    if ( SystemApplicationDataKey < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)SystemApplicationDataKey,
        phkResult);
LABEL_5:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      LauncherClientProvider::AppUriHandlerValidation::~AppUriHandlerValidation((LauncherClientProvider::AppUriHandlerValidation *)v39);
      goto LABEL_30;
    }
    v29 = 0;
    v14 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v29, &off_180123260);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v14,
        phkResult);
LABEL_8:
      WindowsDeleteString(v29);
      v29 = 0;
      goto LABEL_5;
    }
    v31 = 0;
    if ( !RegOpenKeyExW(hKey, L"AppUriHandlers", 0, 0x20019u, &v31) )
    {
      v33 = 0;
      v15 = WindowsGetStringRawBuffer(string, 0);
      if ( RegOpenKeyExW(v31, v15, 0, 0x20019u, &v33) )
      {
        WindowsGetStringRawBuffer(string, 0);
        std::wstring::wstring(lpSubKey);
        v18 = lpSubKey;
        if ( v37 > 7 )
          v18 = (LPCWSTR *)lpSubKey[0];
        v19 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v18, v36, v17, 46);
        while ( v19 != -1 && !*a4 )
        {
          v20 = std::wstring::substr(lpSubKey, v38, v19 + 1);
          std::wstring::operator=(lpSubKey, v20);
          std::wstring::_Tidy_deallocate(v38);
          v34 = 0;
          v21 = (const WCHAR *)lpSubKey;
          if ( v37 > 7 )
            v21 = lpSubKey[0];
          if ( !RegOpenKeyExW(v31, v21, 0, 0x20019u, &v34) )
          {
            v23 = CheckValidationStatusAndPathMatching(v34, a2, 1, a4, a3);
            v10 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA9,
                (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
                (const char *)(unsigned int)v23,
                phkResultb);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
              std::wstring::_Tidy_deallocate(lpSubKey);
              goto LABEL_13;
            }
          }
          v24 = lpSubKey;
          if ( v37 > 7 )
            v24 = (LPCWSTR *)lpSubKey[0];
          v19 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v24, v36, v22, 46);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
        }
        std::wstring::_Tidy_deallocate(lpSubKey);
      }
      else
      {
        v16 = CheckValidationStatusAndPathMatching(v33, a2, 0, a4, a3);
        v10 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9C,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
            (const char *)(unsigned int)v16,
            phkResulta);
LABEL_13:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
          goto LABEL_8;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
    }
    LauncherClientProvider::AppUriHandlerValidation::Stop((LauncherClientProvider::AppUriHandlerValidation *)v39, *a4);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
    WindowsDeleteString(v29);
    v29 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    LauncherClientProvider::AppUriHandlerValidation::~AppUriHandlerValidation((LauncherClientProvider::AppUriHandlerValidation *)v39);
    v10 = 0;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x87,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
    (const char *)(unsigned int)v9,
    phkResult);
LABEL_30:
  WindowsDeleteString(string);
  return v10;
}

```

## disassembly

```asm
0x18007da9c  push    rbp
0x18007da9e  push    rbx
0x18007da9f  push    rsi
0x18007daa0  push    rdi
0x18007daa1  push    r12
0x18007daa3  push    r13
0x18007daa5  push    r14
0x18007daa7  push    r15
0x18007daa9  lea     rbp, [rsp-108h]
0x18007dab1  sub     rsp, 208h
0x18007dab8  mov     rax, cs:__security_cookie
0x18007dabf  xor     rax, rsp
0x18007dac2  mov     [rbp+140h+var_50], rax
0x18007dac9  mov     rsi, r9
0x18007dacc  mov     r15, r8
0x18007dacf  mov     r14, rdx
0x18007dad2  mov     r12, rcx
0x18007dad5  xor     r13d, r13d
0x18007dad8  mov     [r9], r13b
0x18007dadb  mov     [rsp+240h+string], r13
0x18007dae0  mov     rax, [rdx]
0x18007dae3  mov     rbx, [rax+58h]
0x18007dae7  xor     ecx, ecx; string
0x18007dae9  call    cs:__imp_WindowsDeleteString
0x18007daef  mov     [rsp+240h+string], r13
0x18007daf4  lea     rdx, [rsp+240h+string]
0x18007daf9  mov     rcx, r14
0x18007dafc  mov     rax, rbx
0x18007daff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db04  mov     ebx, eax
0x18007db06  test    eax, eax
0x18007db08  jns     short loc_18007DB2A
0x18007db0a  mov     rcx, [rbp+148h]; this
0x18007db11  mov     r9d, eax; char *
0x18007db14  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007db1b  mov     edx, 87h; void *
0x18007db20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007db25  jmp     loc_18007DE53
0x18007db2a  xor     edx, edx; length
0x18007db2c  mov     rcx, [rsp+240h+string]; string
0x18007db31  call    cs:__imp_WindowsGetStringRawBuffer
0x18007db37  mov     rdi, rax
0x18007db3a  xor     edx, edx; length
0x18007db3c  mov     rcx, r12; string
0x18007db3f  call    cs:__imp_WindowsGetStringRawBuffer
0x18007db45  mov     rbx, rax
0x18007db48  lea     rdx, aAppurihandlerv; "AppUriHandlerValidation"
0x18007db4f  lea     rcx, [rbp+140h+var_1A0]; struct wil::details::IFailureCallback *
0x18007db53  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007db58  lea     rax, ??_7AppUriHandlerValidation@LauncherClientProvider@@6B@; const LauncherClientProvider::AppUriHandlerValidation::`vftable'
0x18007db5f  mov     [rbp+140h+var_1A0], rax
0x18007db63  mov     r8, rdi; unsigned __int16 *
0x18007db66  mov     rdx, rbx; unsigned __int16 *
0x18007db69  lea     rcx, [rbp+140h+var_1A0]; this
0x18007db6d  call    ?StartActivity@AppUriHandlerValidation@LauncherClientProvider@@QEAAXPEBG0@Z; LauncherClientProvider::AppUriHandlerValidation::StartActivity(ushort const *,ushort const *)
0x18007db72  nop
0x18007db73  mov     [rsp+240h+hKey], r13
0x18007db78  lea     rdx, [rsp+240h+hKey]; HKEY *
0x18007db7d  mov     rcx, r12; HSTRING
0x18007db80  call    ?GetSystemApplicationDataKey@@YAJPEAUHSTRING__@@PEAPEAUHKEY__@@@Z; GetSystemApplicationDataKey(HSTRING__ *,HKEY__ * *)
0x18007db85  mov     ebx, eax
0x18007db87  test    eax, eax
0x18007db89  jns     short loc_18007DBC0
0x18007db8b  mov     rcx, [rbp+148h]; this
0x18007db92  mov     r9d, eax; char *
0x18007db95  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007db9c  mov     edx, 8Ch; void *
0x18007dba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dba6  nop
0x18007dba7  lea     rcx, [rsp+240h+hKey]
0x18007dbac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007dbb1  nop
0x18007dbb2  lea     rcx, [rbp+140h+var_1A0]; this
0x18007dbb6  call    ??1AppUriHandlerValidation@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::AppUriHandlerValidation::~AppUriHandlerValidation(void)
0x18007dbbb  jmp     loc_18007DE53
0x18007dbc0  mov     [rsp+240h+var_210], r13
0x18007dbc5  lea     rdx, off_180123260; "AppUriHandlers"
0x18007dbcc  lea     rcx, [rsp+240h+var_210]
0x18007dbd1  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007dbd6  mov     ebx, eax
0x18007dbd8  test    eax, eax
0x18007dbda  jns     short loc_18007DC0A
0x18007dbdc  mov     rcx, [rbp+148h]; this
0x18007dbe3  mov     r9d, eax; char *
0x18007dbe6  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007dbed  mov     edx, 8Fh; void *
0x18007dbf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dbf7  nop
0x18007dbf8  mov     rcx, [rsp+240h+var_210]; string
0x18007dbfd  call    cs:__imp_WindowsDeleteString
0x18007dc03  mov     [rsp+240h+var_210], r13
0x18007dc08  jmp     short loc_18007DBA7
0x18007dc0a  mov     [rsp+240h+var_200], r13
0x18007dc0f  lea     rax, [rsp+240h+var_200]
0x18007dc14  mov     qword ptr [rsp+240h+phkResult], rax; phkResult
0x18007dc19  mov     edi, 20019h
0x18007dc1e  mov     r9d, edi; samDesired
0x18007dc21  xor     r8d, r8d; ulOptions
0x18007dc24  lea     rdx, aAppurihandlers; "AppUriHandlers"
0x18007dc2b  mov     rcx, [rsp+240h+hKey]; hKey
0x18007dc30  call    cs:__imp_RegOpenKeyExW
0x18007dc36  test    eax, eax
0x18007dc38  jnz     loc_18007DE15
0x18007dc3e  mov     [rsp+240h+var_1F0], r13
0x18007dc43  xor     edx, edx; length
0x18007dc45  mov     rcx, [rsp+240h+string]; string
0x18007dc4a  call    cs:__imp_WindowsGetStringRawBuffer
0x18007dc50  lea     rcx, [rsp+240h+var_1F0]
0x18007dc55  mov     qword ptr [rsp+240h+phkResult], rcx; phkResult
0x18007dc5a  mov     r9d, edi; samDesired
0x18007dc5d  xor     r8d, r8d; ulOptions
0x18007dc60  mov     rdx, rax; lpSubKey
0x18007dc63  mov     rcx, [rsp+240h+var_200]; hKey
0x18007dc68  call    cs:__imp_RegOpenKeyExW
0x18007dc6e  test    eax, eax
0x18007dc70  jnz     short loc_18007DCCA
0x18007dc72  mov     qword ptr [rsp+240h+phkResult], r15; int
0x18007dc77  mov     r9, rsi; bool *
0x18007dc7a  xor     r8d, r8d; bool
0x18007dc7d  mov     rdx, r14; struct Windows::Foundation::IUriRuntimeClass *
0x18007dc80  mov     rcx, [rsp+240h+var_1F0]; HKEY
0x18007dc85  call    ?CheckValidationStatusAndPathMatching@@YAJPEAUHKEY__@@PEAUIUriRuntimeClass@Foundation@Windows@@_NPEA_NPEAUHSTRING__@@@Z; CheckValidationStatusAndPathMatching(HKEY__ *,Windows::Foundation::IUriRuntimeClass *,bool,bool *,HSTRING__ *)
0x18007dc8a  mov     ebx, eax
0x18007dc8c  test    eax, eax
0x18007dc8e  jns     loc_18007DE0B
0x18007dc94  mov     rcx, [rbp+148h]; this
0x18007dc9b  mov     r9d, eax; char *
0x18007dc9e  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007dca5  mov     edx, 9Ch; void *
0x18007dcaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dcaf  nop
0x18007dcb0  lea     rcx, [rsp+240h+var_1F0]
0x18007dcb5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007dcba  nop
0x18007dcbb  lea     rcx, [rsp+240h+var_200]
0x18007dcc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007dcc5  jmp     loc_18007DBF8
0x18007dcca  xor     edx, edx; length
0x18007dccc  mov     rcx, [rsp+240h+string]; string
0x18007dcd1  call    cs:__imp_WindowsGetStringRawBuffer
0x18007dcd7  mov     rdx, rax
0x18007dcda  lea     rcx, [rsp+240h+lpSubKey]
0x18007dcdf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007dce4  nop
0x18007dce5  lea     rcx, [rsp+240h+lpSubKey]
0x18007dcea  cmp     [rsp+240h+var_1C8], 7
0x18007dcf0  cmova   rcx, [rsp+240h+lpSubKey]
0x18007dcf6  mov     r12d, 2Eh ; '.'
0x18007dcfc  mov     r9d, r12d
0x18007dcff  mov     rdx, [rsp+240h+var_1D0]
0x18007dd04  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18007dd09  mov     rbx, rax
0x18007dd0c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007dd10  jz      loc_18007DE00
0x18007dd16  cmp     [rsi], r13b
0x18007dd19  jnz     loc_18007DE00
0x18007dd1f  lea     r8, [rbx+1]
0x18007dd23  lea     rdx, [rbp+140h+var_1C0]
0x18007dd27  lea     rcx, [rsp+240h+lpSubKey]
0x18007dd2c  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18007dd31  mov     rdx, rax
0x18007dd34  lea     rcx, [rsp+240h+lpSubKey]
0x18007dd39  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007dd3e  lea     rcx, [rbp+140h+var_1C0]
0x18007dd42  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007dd47  mov     [rsp+240h+var_1E8], r13
0x18007dd4c  lea     rdx, [rsp+240h+lpSubKey]
0x18007dd51  cmp     [rsp+240h+var_1C8], 7
0x18007dd57  cmova   rdx, [rsp+240h+lpSubKey]; lpSubKey
0x18007dd5d  lea     rax, [rsp+240h+var_1E8]
0x18007dd62  mov     qword ptr [rsp+240h+phkResult], rax; phkResult
0x18007dd67  mov     r9d, edi; samDesired
0x18007dd6a  xor     r8d, r8d; ulOptions
0x18007dd6d  mov     rcx, [rsp+240h+var_200]; hKey
0x18007dd72  call    cs:__imp_RegOpenKeyExW
0x18007dd78  test    eax, eax
0x18007dd7a  jnz     short loc_18007DD9A
0x18007dd7c  mov     qword ptr [rsp+240h+phkResult], r15; int
0x18007dd81  mov     r9, rsi; bool *
0x18007dd84  mov     r8b, 1; bool
0x18007dd87  mov     rdx, r14; struct Windows::Foundation::IUriRuntimeClass *
0x18007dd8a  mov     rcx, [rsp+240h+var_1E8]; HKEY
0x18007dd8f  call    ?CheckValidationStatusAndPathMatching@@YAJPEAUHKEY__@@PEAUIUriRuntimeClass@Foundation@Windows@@_NPEA_NPEAUHSTRING__@@@Z; CheckValidationStatusAndPathMatching(HKEY__ *,Windows::Foundation::IUriRuntimeClass *,bool,bool *,HSTRING__ *)
0x18007dd94  mov     ebx, eax
0x18007dd96  test    eax, eax
0x18007dd98  js      short loc_18007DDCA
0x18007dd9a  lea     rcx, [rsp+240h+lpSubKey]
0x18007dd9f  cmp     [rsp+240h+var_1C8], 7
0x18007dda5  cmova   rcx, [rsp+240h+lpSubKey]
0x18007ddab  mov     r9d, r12d
0x18007ddae  mov     rdx, [rsp+240h+var_1D0]
0x18007ddb3  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18007ddb8  mov     rbx, rax
0x18007ddbb  lea     rcx, [rsp+240h+var_1E8]
0x18007ddc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007ddc5  jmp     loc_18007DD0C
0x18007ddca  mov     rcx, [rbp+148h]; this
0x18007ddd1  mov     r9d, eax; char *
0x18007ddd4  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18007dddb  mov     edx, 0A9h; void *
0x18007dde0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dde5  nop
0x18007dde6  lea     rcx, [rsp+240h+var_1E8]
0x18007ddeb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007ddf0  nop
0x18007ddf1  lea     rcx, [rsp+240h+lpSubKey]
0x18007ddf6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ddfb  jmp     loc_18007DCB0
0x18007de00  lea     rcx, [rsp+240h+lpSubKey]
0x18007de05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007de0a  nop
0x18007de0b  lea     rcx, [rsp+240h+var_1F0]
0x18007de10  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007de15  mov     dl, [rsi]; bool
0x18007de17  lea     rcx, [rbp+140h+var_1A0]; this
0x18007de1b  call    ?Stop@AppUriHandlerValidation@LauncherClientProvider@@QEAAX_N@Z; LauncherClientProvider::AppUriHandlerValidation::Stop(bool)
0x18007de20  nop
0x18007de21  lea     rcx, [rsp+240h+var_200]
0x18007de26  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007de2b  nop
0x18007de2c  mov     rcx, [rsp+240h+var_210]; string
0x18007de31  call    cs:__imp_WindowsDeleteString
0x18007de37  mov     [rsp+240h+var_210], r13
0x18007de3c  lea     rcx, [rsp+240h+hKey]
0x18007de41  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007de46  nop
0x18007de47  lea     rcx, [rbp+140h+var_1A0]; this
0x18007de4b  call    ??1AppUriHandlerValidation@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::AppUriHandlerValidation::~AppUriHandlerValidation(void)
0x18007de50  mov     ebx, r13d
0x18007de53  mov     rcx, [rsp+240h+string]; string
0x18007de58  call    cs:__imp_WindowsDeleteString
0x18007de5e  mov     eax, ebx
0x18007de60  mov     rcx, [rbp+140h+var_50]
0x18007de67  xor     rcx, rsp; StackCookie
0x18007de6a  call    __security_check_cookie
0x18007de6f  add     rsp, 208h
0x18007de76  pop     r15
0x18007de78  pop     r14
0x18007de7a  pop     r13
0x18007de7c  pop     r12
0x18007de7e  pop     rdi
0x18007de7f  pop     rsi
0x18007de80  pop     rbx
0x18007de81  pop     rbp
0x18007de82  retn
```
