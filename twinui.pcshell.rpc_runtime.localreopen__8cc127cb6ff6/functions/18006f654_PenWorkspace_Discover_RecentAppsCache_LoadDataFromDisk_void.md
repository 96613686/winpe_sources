# PenWorkspace::Discover::RecentAppsCache::LoadDataFromDisk(void)

- ea: `0x18006f654`
- end: `0x18006f9ea`
- name: `?LoadDataFromDisk@RecentAppsCache@Discover@PenWorkspace@@AEAAJXZ`
- size: `918`
- prototype: `__int64 __fastcall(PenWorkspace::Discover::RecentAppsCache *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006f9f0`

## callees

- `0x1800237c8`
- `0x180033a20`
- `0x180051b40`
- `0x18005a710`
- `0x18005b670`
- `0x18006f654`
- `0x1800e1a60`
- `0x1800e1ce4`
- `0x1802bbaf8`
- `0x180356360`
- `0x180356edc`
- `0x18045dd3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f824`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f80e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f71c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f791`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f71c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f791`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f8a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f8a7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006f7b6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006f7b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006f848`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006f848`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f6ec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f6ec`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006f760`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006f760`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006f70f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006f70f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006f695`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006f695`

## string_xrefs

- `0x18006f6b1`: `pcshell\twinui\penworkspace\broker\lib\recentappscache.cpp`
- `0x18006f771`: `pcshell\twinui\penworkspace\broker\lib\recentappscache.cpp`
- `0x18006f7cf`: `pcshell\twinui\penworkspace\broker\lib\recentappscache.cpp`
- `0x18006f85e`: `pcshell\twinui\penworkspace\broker\lib\recentappscache.cpp`
- `0x18006f90d`: `pcshell\twinui\penworkspace\broker\lib\recentappscache.cpp`
- `0x18006f99e`: `pcshell\twinui\penworkspace\broker\lib\recentappscache.cpp`
- `0x18006f68e`: `%LOCALAPPDATA%\Microsoft\PenWorkspace\DiscoverCacheData.dat`
- `0x18006f807`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PenWorkspace::Discover::RecentAppsCache::LoadDataFromDisk(RTL_SRWLOCK *this)
{
  unsigned int LastError; // ebx
  char *FileW; // rax
  char *v4; // r14
  DWORD FileSize; // eax
  __int64 v6; // rdi
  SIZE_T v7; // rsi
  void *v8; // rax
  void *v9; // rbx
  size_t v10; // rax
  const char *v11; // r9
  WCHAR *v12; // rdi
  HRESULT v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  HSTRING v17; // rsi
  int ActivationFactory; // eax
  unsigned int v19; // esi
  __int64 v20; // rcx
  __int64 v22; // rsi
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64, struct Windows::Data::Json::IJsonObject **, char *); // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  char v44[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Data::Json::IJsonObject *v46; // [rsp+50h] [rbp-B0h] BYREF
  void *v47; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR *v48; // [rsp+60h] [rbp-A0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-98h] BYREF
  char *v50; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Dst[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  if ( !ExpandEnvironmentStringsW(L"%LOCALAPPDATA%\\Microsoft\\PenWorkspace\\DiscoverCacheData.dat", Dst, 0x104u) )
  {
    LastError = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x215,
      (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\recentappscache.cpp",
      (const char *)0x80004005LL,
      dwCreationDisposition);
    return LastError;
  }
  FileW = (char *)CreateFileW(Dst, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
  v4 = FileW;
  v50 = FileW;
  if ( FileW == (char *)-1LL )
  {
    LastError = -2147023728;
LABEL_28:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v50);
    return LastError;
  }
  FileSize = GetFileSize(FileW, 0);
  v6 = FileSize;
  v7 = FileSize + 1;
  v8 = CoTaskMemAlloc(v7);
  v9 = v8;
  v47 = v8;
  if ( !v8 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21F,
      (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\recentappscache.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
    goto LABEL_27;
  }
  v10 = CTCoAllocPolicy::_CoTaskMemSize(v8);
  memset_0(v9, 0, v10);
  NumberOfBytesRead = 0;
  if ( !ReadFile(v4, v9, v6, &NumberOfBytesRead, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x222,
                  (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\recentappscache.cpp",
                  v11);
LABEL_27:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v47);
    goto LABEL_28;
  }
  *((_BYTE *)v9 + v6) = 0;
  v12 = (WCHAR *)CoTaskMemAlloc(2 * v7);
  v48 = v12;
  if ( !MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v9, -1, v12, v7) )
  {
    LastError = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x227,
      (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\recentappscache.cpp",
      (const char *)0x80004005LL,
      dwCreationDispositionb);
LABEL_10:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v48);
    goto LABEL_27;
  }
  v45 = 0;
  string = 0;
  v13 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
    __debugbreak();
  }
  v17 = string;
  Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v45, v14, v15, v16);
  ActivationFactory = RoGetActivationFactory(v17, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v45);
  v19 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v46 = 0;
    v44[0] = 0;
    v22 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v48) + 24);
    string = 0;
    v23 = v45;
    v24 = *(__int64 (__fastcall **)(__int64, __int64, struct Windows::Data::Json::IJsonObject **, char *))(*(_QWORD *)v45 + 56LL);
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v46, v25, v26, v27);
    v28 = v24(v23, v22, &v46, v44);
    LastError = v28;
    if ( v28 >= 0 )
    {
      if ( !v44[0] )
      {
        PenWorkspaceBrokerTelemetry::FailedToParseJsonString();
        if ( !v44[0] )
        {
          Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v46, v37, v29, v30);
          Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v45, v38, v39, v40);
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v48);
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v47);
          LastError = -2147467259;
          goto LABEL_28;
        }
      }
      LastError = PenWorkspace::Discover::RecentAppsCache::LoadJsonDataFromDisk(this, v46, v29, v30);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22F,
        (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\recentappscache.cpp",
        (const char *)(unsigned int)v28,
        dwCreationDispositionb);
    }
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v46, v31, v32, v33);
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v45, v34, v35, v36);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x22A,
    (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\recentappscache.cpp",
    (const char *)(unsigned int)ActivationFactory,
    dwCreationDispositionb);
  v20 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  CoTaskMemFree(v12);
  CoTaskMemFree(v9);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  return v19;
}

```

## disassembly

```asm
0x18006f654  push    rbp
0x18006f656  push    rbx
0x18006f657  push    rsi
0x18006f658  push    rdi
0x18006f659  push    r12
0x18006f65b  push    r13
0x18006f65d  push    r14
0x18006f65f  push    r15
0x18006f661  lea     rbp, [rsp-1C8h]
0x18006f669  sub     rsp, 2C8h
0x18006f670  mov     rax, cs:__security_cookie
0x18006f677  xor     rax, rsp
0x18006f67a  mov     [rbp+200h+var_50], rax
0x18006f681  mov     r12, rcx
0x18006f684  mov     r8d, 104h; nSize
0x18006f68a  lea     rdx, [rbp+200h+Dst]; lpDst
0x18006f68e  lea     rcx, aLocalappdataMi_0; "%LOCALAPPDATA%\\Microsoft\\PenWorkspace"...
0x18006f695  call    cs:__imp_ExpandEnvironmentStringsW
0x18006f69b  xor     r13d, r13d
0x18006f69e  test    eax, eax
0x18006f6a0  jnz     short loc_18006F6C7
0x18006f6a2  mov     rcx, [rbp+208h]; this
0x18006f6a9  mov     ebx, 80004005h
0x18006f6ae  mov     r9d, ebx; char *
0x18006f6b1  lea     r8, aPcshellTwinuiP_0; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18006f6b8  mov     edx, 215h; void *
0x18006f6bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f6c2  jmp     loc_18006F9C5
0x18006f6c7  mov     [rsp+300h+hTemplateFile], r13; hTemplateFile
0x18006f6cc  mov     [rsp+300h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18006f6d4  mov     [rsp+300h+dwCreationDisposition], 3; int
0x18006f6dc  xor     r9d, r9d; lpSecurityAttributes
0x18006f6df  mov     edx, 80000000h; dwDesiredAccess
0x18006f6e4  lea     r8d, [r9+1]; dwShareMode
0x18006f6e8  lea     rcx, [rbp+200h+Dst]; lpFileName
0x18006f6ec  call    cs:__imp_CreateFileW
0x18006f6f2  mov     r14, rax
0x18006f6f5  mov     [rsp+300h+var_290], rax
0x18006f6fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006f6fe  jnz     short loc_18006F70A
0x18006f700  mov     ebx, 80070490h
0x18006f705  jmp     loc_18006F9BB
0x18006f70a  xor     edx, edx; lpFileSizeHigh
0x18006f70c  mov     rcx, r14; hFile
0x18006f70f  call    cs:__imp_GetFileSize
0x18006f715  mov     edi, eax
0x18006f717  lea     esi, [rdi+1]
0x18006f71a  mov     ecx, esi; cb
0x18006f71c  call    cs:__imp_CoTaskMemAlloc
0x18006f722  mov     rbx, rax
0x18006f725  mov     [rsp+300h+var_2A8], rax
0x18006f72a  test    rax, rax
0x18006f72d  jz      loc_18006F98F
0x18006f733  mov     rcx, rax; void *
0x18006f736  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18006f73b  mov     r8, rax; Size
0x18006f73e  xor     edx, edx; Val
0x18006f740  mov     rcx, rbx; void *
0x18006f743  call    memset_0
0x18006f748  mov     [rsp+300h+NumberOfBytesRead], r13d
0x18006f74d  mov     qword ptr [rsp+300h+dwCreationDisposition], r13; lpOverlapped
0x18006f752  lea     r9, [rsp+300h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006f757  mov     r8d, edi; nNumberOfBytesToRead
0x18006f75a  mov     rdx, rbx; lpBuffer
0x18006f75d  mov     rcx, r14; hFile
0x18006f760  call    cs:__imp_ReadFile
0x18006f766  test    eax, eax
0x18006f768  jnz     short loc_18006F789
0x18006f76a  mov     rcx, [rbp+208h]; this
0x18006f771  lea     r8, aPcshellTwinuiP_0; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18006f778  mov     edx, 222h; void *
0x18006f77d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006f782  mov     ebx, eax
0x18006f784  jmp     loc_18006F9B0
0x18006f789  mov     [rdi+rbx], r13b
0x18006f78d  lea     rcx, [rsi+rsi]; cb
0x18006f791  call    cs:__imp_CoTaskMemAlloc
0x18006f797  mov     rdi, rax
0x18006f79a  mov     [rsp+300h+var_2A0], rax
0x18006f79f  mov     [rsp+300h+dwFlagsAndAttributes], esi; cchWideChar
0x18006f7a3  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; int
0x18006f7a8  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18006f7ac  mov     r8, rbx; lpMultiByteStr
0x18006f7af  xor     edx, edx; dwFlags
0x18006f7b1  mov     ecx, 0FDE9h; CodePage
0x18006f7b6  call    cs:__imp_MultiByteToWideChar
0x18006f7bc  test    eax, eax
0x18006f7be  jnz     short loc_18006F7F0
0x18006f7c0  mov     rcx, [rbp+208h]; this
0x18006f7c7  mov     ebx, 80004005h
0x18006f7cc  mov     r9d, ebx; char *
0x18006f7cf  lea     r8, aPcshellTwinuiP_0; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18006f7d6  mov     edx, 227h; void *
0x18006f7db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f7e0  nop
0x18006f7e1  lea     rcx, [rsp+300h+var_2A0]
0x18006f7e6  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18006f7eb  jmp     loc_18006F9B0
0x18006f7f0  mov     [rsp+300h+var_2B8], r13
0x18006f7f5  mov     [rbp+200h+string], r13
0x18006f7f9  lea     r9, [rbp+200h+string]; string
0x18006f7fd  lea     r8, [rsp+300h+hstringHeader]; hstringHeader
0x18006f802  mov     edx, 1Ch; length
0x18006f807  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18006f80e  call    cs:__imp_WindowsCreateStringReference
0x18006f814  test    eax, eax
0x18006f816  jns     short loc_18006F82B
0x18006f818  xor     r9d, r9d; lpArguments
0x18006f81b  xor     r8d, r8d; nNumberOfArguments
0x18006f81e  lea     edx, [r9+1]; dwExceptionFlags
0x18006f822  mov     ecx, eax; dwExceptionCode
0x18006f824  call    cs:__imp_RaiseException
0x18006f82a  int     3; Trap to Debugger
0x18006f82b  mov     rsi, [rbp+200h+string]
0x18006f82f  lea     rcx, [rsp+300h+var_2B8]
0x18006f834  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18006f839  lea     r8, [rsp+300h+var_2B8]
0x18006f83e  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18006f845  mov     rcx, rsi
0x18006f848  call    cs:__imp_RoGetActivationFactory
0x18006f84e  mov     esi, eax
0x18006f850  test    eax, eax
0x18006f852  jns     short loc_18006F8B4
0x18006f854  mov     rcx, [rbp+208h]; this
0x18006f85b  mov     r9d, eax; char *
0x18006f85e  lea     r8, aPcshellTwinuiP_0; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18006f865  mov     edx, 22Ah; void *
0x18006f86a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f86f  nop
0x18006f870  mov     rcx, [rsp+300h+var_2B8]
0x18006f875  test    rcx, rcx
0x18006f878  jz      short loc_18006F886
0x18006f87a  mov     [rsp+300h+var_2B8], r13
0x18006f87f  mov     rax, [rcx]
0x18006f882  call    qword ptr [rax+10h]
0x18006f885  nop
0x18006f886  mov     rcx, rdi; pv
0x18006f889  call    cs:__imp_CoTaskMemFree
0x18006f88f  nop
0x18006f890  mov     rcx, rbx; pv
0x18006f893  call    cs:__imp_CoTaskMemFree
0x18006f899  nop
0x18006f89a  lea     rax, [r14-1]
0x18006f89e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006f8a2  ja      short loc_18006F8AD
0x18006f8a4  mov     rcx, r14; hObject
0x18006f8a7  call    cs:__imp_CloseHandle
0x18006f8ad  mov     eax, esi
0x18006f8af  jmp     loc_18006F9C7
0x18006f8b4  mov     [rsp+300h+var_2B0], r13
0x18006f8b9  mov     [rsp+300h+var_2C0], r13b
0x18006f8be  lea     rdx, [rsp+300h+var_2A0]
0x18006f8c3  lea     rcx, [rsp+300h+hstringHeader]
0x18006f8c8  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18006f8cd  mov     rsi, [rax+18h]
0x18006f8d1  mov     [rbp+200h+string], r13
0x18006f8d5  mov     rdi, [rsp+300h+var_2B8]
0x18006f8da  mov     rax, [rdi]
0x18006f8dd  mov     rbx, [rax+38h]
0x18006f8e1  lea     rcx, [rsp+300h+var_2B0]
0x18006f8e6  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18006f8eb  lea     r9, [rsp+300h+var_2C0]
0x18006f8f0  lea     r8, [rsp+300h+var_2B0]
0x18006f8f5  mov     rdx, rsi
0x18006f8f8  mov     rcx, rdi
0x18006f8fb  call    rbx
0x18006f8fd  mov     ebx, eax
0x18006f8ff  test    eax, eax
0x18006f901  jns     short loc_18006F939
0x18006f903  mov     rcx, [rbp+208h]; this
0x18006f90a  mov     r9d, eax; char *
0x18006f90d  lea     r8, aPcshellTwinuiP_0; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18006f914  mov     edx, 22Fh; void *
0x18006f919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f91e  nop
0x18006f91f  lea     rcx, [rsp+300h+var_2B0]
0x18006f924  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18006f929  nop
0x18006f92a  lea     rcx, [rsp+300h+var_2B8]
0x18006f92f  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18006f934  jmp     loc_18006F7E1
0x18006f939  cmp     [rsp+300h+var_2C0], r13b
0x18006f93e  jnz     short loc_18006F97E
0x18006f940  call    ?FailedToParseJsonString@PenWorkspaceBrokerTelemetry@@SAXXZ; PenWorkspaceBrokerTelemetry::FailedToParseJsonString(void)
0x18006f945  cmp     [rsp+300h+var_2C0], r13b
0x18006f94a  jnz     short loc_18006F97E
0x18006f94c  lea     rcx, [rsp+300h+var_2B0]
0x18006f951  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18006f956  nop
0x18006f957  lea     rcx, [rsp+300h+var_2B8]
0x18006f95c  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18006f961  nop
0x18006f962  lea     rcx, [rsp+300h+var_2A0]
0x18006f967  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18006f96c  nop
0x18006f96d  lea     rcx, [rsp+300h+var_2A8]
0x18006f972  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18006f977  mov     ebx, 80004005h
0x18006f97c  jmp     short loc_18006F9BB
0x18006f97e  mov     rdx, [rsp+300h+var_2B0]; struct Windows::Data::Json::IJsonObject *
0x18006f983  mov     rcx, r12; this
0x18006f986  call    ?LoadJsonDataFromDisk@RecentAppsCache@Discover@PenWorkspace@@AEAAJPEAUIJsonObject@Json@Data@Windows@@@Z; PenWorkspace::Discover::RecentAppsCache::LoadJsonDataFromDisk(Windows::Data::Json::IJsonObject *)
0x18006f98b  mov     ebx, eax
0x18006f98d  jmp     short loc_18006F91F
0x18006f98f  mov     rcx, [rbp+208h]; this
0x18006f996  mov     ebx, 8007000Eh
0x18006f99b  mov     r9d, ebx; char *
0x18006f99e  lea     r8, aPcshellTwinuiP_0; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18006f9a5  mov     edx, 21Fh; void *
0x18006f9aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f9af  nop
0x18006f9b0  lea     rcx, [rsp+300h+var_2A8]
0x18006f9b5  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18006f9ba  nop
0x18006f9bb  lea     rcx, [rsp+300h+var_290]
0x18006f9c0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006f9c5  mov     eax, ebx
0x18006f9c7  mov     rcx, [rbp+200h+var_50]
0x18006f9ce  xor     rcx, rsp; StackCookie
0x18006f9d1  call    __security_check_cookie
0x18006f9d6  add     rsp, 2C8h
0x18006f9dd  pop     r15
0x18006f9df  pop     r14
0x18006f9e1  pop     r13
0x18006f9e3  pop     r12
0x18006f9e5  pop     rdi
0x18006f9e6  pop     rsi
0x18006f9e7  pop     rbx
0x18006f9e8  pop     rbp
0x18006f9e9  retn
```
