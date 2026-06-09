# CStorageFileBase::CreateAndProtectWin32FileHandleNoOplock(ulong,CREATE_FILE_HANDLE_OPTIONS,ushort const *,void * *)

- ea: `0x1800bd210`
- end: `0x1800bd5af`
- name: `?CreateAndProtectWin32FileHandleNoOplock@CStorageFileBase@@UEAAJKW4CREATE_FILE_HANDLE_OPTIONS@@PEBGPEAPEAX@Z`
- size: `927`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x18001a354`
- `0x18001adbc`
- `0x18001c458`
- `0x180038f50`
- `0x180044320`
- `0x18007bbf0`
- `0x18007c1c0`
- `0x18007ea3c`
- `0x180083c94`
- `0x1800bd210`
- `0x1800bd5b8`
- `0x1800c8920`
- `0x1801720d0`
- `0x18023ee10`
- `0x180359760`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd59e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd59e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180663e2f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180663e2f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bd3fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180663d2f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bd3fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180663d2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd4eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd4eb`
- `efswrt!EnterpriseDataProtect` at `0x180663d91`
- `efswrt!EnterpriseDataProtect` at `0x180663d91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bd3c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180663d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180663d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bd3c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180663d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180663d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd447`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd496`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd4fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd447`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd496`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd4fc`

## string_xrefs

- `0x1800bd2c9`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1800bd480`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1800bd585`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180663d5a`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x180663daf`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1800bd324`: `CreateAndProtectWin32FileHandleNoOplockAsync`
- `0x180663e12`: `This file was already protected to an enterprise ID, but the protection has been revoked.`
- `0x180663e68`: `This file is already protected to an EDP identity; it cannot have a new one applied.`
- `0x180663e50`: `This file cannot be protected. It may be compressed, read-only, cert-based EFS protected, etc.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CStorageFileBase::CreateAndProtectWin32FileHandleNoOplock(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        _QWORD *a5)
{
  struct Windows::System::IUser *RawUser; // rax
  int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  void *v17; // rbx
  unsigned int v18; // r14d
  DWORD v19; // r15d
  __int64 v20; // rsi
  const WCHAR *v21; // rax
  char *v22; // rax
  unsigned int LastError; // edi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdx
  const WCHAR *StringRawBuffer; // rax
  HANDLE FileW; // rax
  const char *v29; // r9
  PCWSTR v30; // rax
  int v31; // eax
  unsigned int v32; // r9d
  unsigned int v33; // r8d
  const WCHAR *v34; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h]
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v45[88]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v46[104]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  *a5 = 0;
  v38 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  RawUser = CStorageItem::GetRawUser((CStorageItem *)(a1 - 432));
  v40 = (a1 - 304) & -(__int64)(a1 != 432);
  *(_QWORD *)v39 = RawUser;
  v44 = 0;
  LODWORD(v37) = 2;
  v10 = Microsoft::WRL::Details::MakeAndInitialize<CapturedCallerContext,Windows::Internal::ICapturedCallerContext,enum Windows::Internal::MuaApiUserPolicy &,enum Windows::Internal::MuaApiUserPolicyFlags &,IUnknown * &,Windows::System::IUser * &>(
          (unsigned int)&v38,
          (unsigned int)&v37,
          (unsigned int)&v44,
          (unsigned int)&v40,
          (__int64)v39);
  v12 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3042,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v10,
      dwCreationDisposition);
    v13 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v12;
  }
  LOBYTE(v11) = 1;
  WinRTStorageTelemetry::WatchCurrentThread(v45, "CreateAndProtectWin32FileHandleNoOplockAsync", v11);
  Microsoft::WRL::ComPtr<IStream>::operator=(v46, v38);
  string = 0;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)(a1 - 416) + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v16 = v15(a1 - 416, &string);
  v12 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3048,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v16,
      dwCreationDisposition);
    WindowsDeleteString(string);
    string = 0;
    StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v45);
    v24 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return v12;
  }
  v17 = 0;
  *(_QWORD *)v39 = 0;
  if ( a4 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v37,
      a4,
      -1);
    v26 = v37;
    v37 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v39,
      v26);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v37);
    v17 = *(void **)v39;
    if ( !*(_QWORD *)v39 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x304E,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      goto LABEL_11;
    }
  }
  v18 = a2 != 0 ? 0xFFFFFFFE : 0;
  v19 = a2 != 0 ? -1073741824 : 0x80000000;
  v20 = -1;
  v37 = -1;
  if ( v17 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    FileW = CreateFileW(StringRawBuffer, 0, 7u, 0, 3u, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v37,
      FileW);
    v20 = v37;
    if ( v37 == -1 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3075,
                    (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
                    v29);
      goto LABEL_10;
    }
    v44 = 0;
    v30 = WindowsGetStringRawBuffer(string, 0);
    v31 = EnterpriseDataProtect(v30, v17, &v44);
    LastError = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3078,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)v31,
        dwCreationDispositiona);
      goto LABEL_10;
    }
    if ( v44 != 3 )
    {
      switch ( v44 )
      {
        case 2:
          v42 = 0;
          v32 = 89;
          v33 = 90;
          v34 = L"This file was already protected to an enterprise ID, but the protection has been revoked.";
          break;
        case 4:
        case 5:
          goto LABEL_38;
        case 6:
          v42 = 0;
          v32 = 94;
          v33 = 95;
          v34 = L"This file cannot be protected. It may be compressed, read-only, cert-based EFS protected, etc.";
          break;
        case 7:
LABEL_38:
          v42 = 0;
          v32 = 84;
          v33 = 85;
          v34 = L"This file is already protected to an EDP identity; it cannot have a new one applied.";
          break;
        default:
          v42 = 0;
          v32 = 43;
          v33 = 44;
          v34 = L"Could not protect the file: Reason unknown.";
          break;
      }
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v34, v33, v32);
      LastError = -2146893015;
      RoOriginateError(2148074281LL, v42);
      goto LABEL_10;
    }
  }
  v21 = WindowsGetStringRawBuffer(string, 0);
  v22 = (char *)CreateFileW(v21, v19, v18 + 7, 0, 3u, a3 & 0x40000000, 0);
  v40 = (__int64)v22;
  if ( ((unsigned __int64)(v22 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::GetLastErrorFailHr((wil::details *)(v22 + 1));
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
LABEL_10:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v37);
LABEL_11:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v39);
    WindowsDeleteString(string);
    string = 0;
    StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    return LastError;
  }
  *a5 = v22;
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v20);
  if ( v17 )
    CoTaskMemFree(v17);
  WindowsDeleteString(string);
  string = 0;
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v45);
  v25 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x1800bd210  mov     [rsp-8+arg_8], rbx
0x1800bd215  push    rbp
0x1800bd216  push    rsi
0x1800bd217  push    rdi
0x1800bd218  push    r12
0x1800bd21a  push    r13
0x1800bd21c  push    r14
0x1800bd21e  push    r15
0x1800bd220  lea     rbp, [rsp-60h]
0x1800bd225  sub     rsp, 160h
0x1800bd22c  mov     rax, cs:__security_cookie
0x1800bd233  xor     rax, rsp
0x1800bd236  mov     [rbp+90h+var_40], rax
0x1800bd23a  mov     r14, r9
0x1800bd23d  mov     r12d, r8d
0x1800bd240  mov     esi, edx
0x1800bd242  mov     rdi, rcx
0x1800bd245  mov     r13, [rbp+90h+arg_20]
0x1800bd24c  xor     r15d, r15d
0x1800bd24f  mov     [r13+0], r15
0x1800bd253  mov     [rsp+190h+var_148], r15
0x1800bd258  lea     rcx, [rsp+190h+var_148]
0x1800bd25d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bd262  lea     rbx, [rdi-1B0h]
0x1800bd269  mov     rcx, rbx; this
0x1800bd26c  call    ?GetRawUser@CStorageItem@@IEAAPEAUIUser@System@Windows@@XZ; CStorageItem::GetRawUser(void)
0x1800bd271  lea     rdx, [rdi-130h]
0x1800bd278  neg     rbx
0x1800bd27b  sbb     rcx, rcx
0x1800bd27e  and     rcx, rdx
0x1800bd281  mov     [rsp+190h+var_138], rcx
0x1800bd286  mov     qword ptr [rsp+190h+var_140], rax
0x1800bd28b  mov     [rbp+90h+var_108], r15d
0x1800bd28f  mov     dword ptr [rsp+190h+var_150], 2
0x1800bd297  lea     rax, [rsp+190h+var_140]
0x1800bd29c  mov     qword ptr [rsp+190h+dwCreationDisposition], rax; int
0x1800bd2a1  lea     r9, [rsp+190h+var_138]
0x1800bd2a6  lea     r8, [rbp+90h+var_108]
0x1800bd2aa  lea     rdx, [rsp+190h+var_150]
0x1800bd2af  lea     rcx, [rsp+190h+var_148]
0x1800bd2b4  call    ??$MakeAndInitialize@VCapturedCallerContext@@UICapturedCallerContext@Internal@Windows@@AEAW4MuaApiUserPolicy@34@AEAW4MuaApiUserPolicyFlags@34@AEAPEAUIUnknown@@AEAPEAUIUser@System@4@@Details@WRL@Microsoft@@YAJPEAPEAUICapturedCallerContext@Internal@Windows@@AEAW4MuaApiUserPolicy@45@AEAW4MuaApiUserPolicyFlags@45@AEAPEAUIUnknown@@AEAPEAUIUser@System@5@@Z; Microsoft::WRL::Details::MakeAndInitialize<CapturedCallerContext,Windows::Internal::ICapturedCallerContext,Windows::Internal::MuaApiUserPolicy &,Windows::Internal::MuaApiUserPolicyFlags &,IUnknown * &,Windows::System::IUser * &>(Windows::Internal::ICapturedCallerContext * *,Windows::Internal::MuaApiUserPolicy &,Windows::Internal::MuaApiUserPolicyFlags &,IUnknown * &,Windows::System::IUser * &)
0x1800bd2b9  mov     ebx, eax
0x1800bd2bb  test    eax, eax
0x1800bd2bd  jns     short loc_1800BD321
0x1800bd2bf  mov     rcx, [rbp+98h]; this
0x1800bd2c6  mov     r9d, eax; char *
0x1800bd2c9  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1800bd2d0  mov     edx, 3042h; void *
0x1800bd2d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd2da  nop
0x1800bd2db  mov     rcx, [rsp+190h+var_148]
0x1800bd2e0  test    rcx, rcx
0x1800bd2e3  jz      short loc_1800BD2F7
0x1800bd2e5  mov     [rsp+190h+var_148], r15
0x1800bd2ea  mov     rax, [rcx]
0x1800bd2ed  mov     rax, [rax+10h]
0x1800bd2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd2f6  nop
0x1800bd2f7  mov     eax, ebx
0x1800bd2f9  mov     rcx, [rbp+90h+var_40]
0x1800bd2fd  xor     rcx, rsp; StackCookie
0x1800bd300  call    __security_check_cookie
0x1800bd305  mov     rbx, [rsp+190h+arg_8]
0x1800bd30d  add     rsp, 160h
0x1800bd314  pop     r15
0x1800bd316  pop     r14
0x1800bd318  pop     r13
0x1800bd31a  pop     r12
0x1800bd31c  pop     rdi
0x1800bd31d  pop     rsi
0x1800bd31e  pop     rbp
0x1800bd31f  retn
0x1800bd321  mov     r8b, 1
0x1800bd324  lea     rdx, aCreateandprote_0; "CreateAndProtectWin32FileHandleNoOplock"...
0x1800bd32b  lea     rcx, [rbp+90h+var_100]
0x1800bd32f  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x1800bd334  nop
0x1800bd335  mov     rdx, [rsp+190h+var_148]
0x1800bd33a  lea     rcx, [rbp+90h+var_A8]
0x1800bd33e  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1800bd343  mov     [rbp+90h+string], r15
0x1800bd347  mov     rax, [rdi-1A0h]
0x1800bd34e  mov     rbx, [rax+60h]
0x1800bd352  xor     ecx, ecx; string
0x1800bd354  call    cs:__imp_WindowsDeleteString
0x1800bd35b  nop     dword ptr [rax+rax+00h]
0x1800bd360  mov     [rbp+90h+string], r15
0x1800bd364  lea     rdx, [rbp+90h+string]
0x1800bd368  lea     rcx, [rdi-1A0h]
0x1800bd36f  mov     rax, rbx
0x1800bd372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd377  mov     ebx, eax
0x1800bd379  xor     edi, edi
0x1800bd37b  test    eax, eax
0x1800bd37d  js      loc_1800BD476
0x1800bd383  mov     ebx, edi
0x1800bd385  mov     qword ptr [rsp+190h+var_140], rbx
0x1800bd38a  test    r14, r14
0x1800bd38d  jnz     loc_1800BD539
0x1800bd393  mov     eax, esi
0x1800bd395  neg     eax
0x1800bd397  sbb     r14d, r14d
0x1800bd39a  and     r14d, 0FFFFFFFEh
0x1800bd39e  neg     esi
0x1800bd3a0  sbb     r15d, r15d
0x1800bd3a3  and     r15d, 40000000h
0x1800bd3aa  add     r15d, 80000000h
0x1800bd3b1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800bd3b5  mov     [rsp+190h+var_150], rsi
0x1800bd3ba  test    rbx, rbx
0x1800bd3bd  jnz     loc_180663D00
0x1800bd3c3  xor     edx, edx; length
0x1800bd3c5  mov     rcx, [rbp+90h+string]; string
0x1800bd3c9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bd3d0  nop     dword ptr [rax+rax+00h]
0x1800bd3d5  and     r12d, 40000000h
0x1800bd3dc  mov     [rsp+190h+hTemplateFile], rdi; hTemplateFile
0x1800bd3e1  mov     [rsp+190h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800bd3e6  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x1800bd3ee  xor     r9d, r9d; lpSecurityAttributes
0x1800bd3f1  lea     r8d, [r14+7]; dwShareMode
0x1800bd3f5  mov     edx, r15d; dwDesiredAccess
0x1800bd3f8  mov     rcx, rax; lpFileName
0x1800bd3fb  call    cs:__imp_CreateFileW
0x1800bd402  nop     dword ptr [rax+rax+00h]
0x1800bd407  mov     [rsp+190h+var_138], rax
0x1800bd40c  lea     rcx, [rax+1]; this
0x1800bd410  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800bd417  jnz     loc_1800BD4D1
0x1800bd41d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800bd422  mov     edi, eax
0x1800bd424  lea     rcx, [rsp+190h+var_138]
0x1800bd429  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800bd42e  lea     rcx, [rsp+190h+var_150]
0x1800bd433  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800bd438  lea     rcx, [rsp+190h+var_140]; void *
0x1800bd43d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800bd442  nop
0x1800bd443  mov     rcx, [rbp+90h+string]; string
0x1800bd447  call    cs:__imp_WindowsDeleteString
0x1800bd44e  nop     dword ptr [rax+rax+00h]
0x1800bd453  mov     [rbp+90h+string], 0
0x1800bd45b  lea     rcx, [rbp+90h+var_100]; this
0x1800bd45f  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1800bd464  nop
0x1800bd465  lea     rcx, [rsp+190h+var_148]
0x1800bd46a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bd46f  mov     eax, edi
0x1800bd471  jmp     loc_1800BD2F9
0x1800bd476  mov     rcx, [rbp+98h]; this
0x1800bd47d  mov     r9d, ebx; char *
0x1800bd480  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1800bd487  mov     edx, 3048h; void *
0x1800bd48c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd491  nop
0x1800bd492  mov     rcx, [rbp+90h+string]; string
0x1800bd496  call    cs:__imp_WindowsDeleteString
0x1800bd49d  nop     dword ptr [rax+rax+00h]
0x1800bd4a2  mov     [rbp+90h+string], rdi
0x1800bd4a6  lea     rcx, [rbp+90h+var_100]; this
0x1800bd4aa  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1800bd4af  nop
0x1800bd4b0  mov     rcx, [rsp+190h+var_148]
0x1800bd4b5  test    rcx, rcx
0x1800bd4b8  jz      short loc_1800BD4CC
0x1800bd4ba  mov     [rsp+190h+var_148], rdi
0x1800bd4bf  mov     rax, [rcx]
0x1800bd4c2  mov     rax, [rax+10h]
0x1800bd4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd4cb  nop
0x1800bd4cc  jmp     loc_1800BD2F7
0x1800bd4d1  mov     [r13+0], rax
0x1800bd4d5  lea     rax, [rsi-1]
0x1800bd4d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800bd4dd  jbe     loc_1800BD59B
0x1800bd4e3  test    rbx, rbx
0x1800bd4e6  jz      short loc_1800BD4F8
0x1800bd4e8  mov     rcx, rbx; pv
0x1800bd4eb  call    cs:__imp_CoTaskMemFree
0x1800bd4f2  nop     dword ptr [rax+rax+00h]
0x1800bd4f7  nop
0x1800bd4f8  mov     rcx, [rbp+90h+string]; string
0x1800bd4fc  call    cs:__imp_WindowsDeleteString
0x1800bd503  nop     dword ptr [rax+rax+00h]
0x1800bd508  mov     [rbp+90h+string], rdi
0x1800bd50c  lea     rcx, [rbp+90h+var_100]; this
0x1800bd510  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1800bd515  nop
0x1800bd516  mov     rcx, [rsp+190h+var_148]
0x1800bd51b  test    rcx, rcx
0x1800bd51e  jz      short loc_1800BD532
0x1800bd520  mov     [rsp+190h+var_148], rdi
0x1800bd525  mov     rax, [rcx]
0x1800bd528  mov     rax, [rax+10h]
0x1800bd52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd531  nop
0x1800bd532  xor     eax, eax
0x1800bd534  jmp     loc_1800BD2F9
0x1800bd539  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bd53d  mov     rdx, r14
0x1800bd540  lea     rcx, [rsp+190h+var_150]
0x1800bd545  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800bd54a  mov     rdx, [rsp+190h+var_150]
0x1800bd54f  mov     [rsp+190h+var_150], rdi
0x1800bd554  lea     rcx, [rsp+190h+var_140]
0x1800bd559  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800bd55e  lea     rcx, [rsp+190h+var_150]; void *
0x1800bd563  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800bd568  mov     rbx, qword ptr [rsp+190h+var_140]
0x1800bd56d  test    rbx, rbx
0x1800bd570  jnz     loc_1800BD393
0x1800bd576  mov     rcx, [rbp+98h]; this
0x1800bd57d  mov     edi, 8007000Eh
0x1800bd582  mov     r9d, edi; char *
0x1800bd585  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1800bd58c  mov     edx, 304Eh; void *
0x1800bd591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd596  jmp     loc_1800BD438
0x1800bd59b  mov     rcx, rsi; hObject
0x1800bd59e  call    cs:__imp_CloseHandle
0x1800bd5a5  nop     dword ptr [rax+rax+00h]
0x1800bd5aa  jmp     loc_1800BD4E3
0x180663d00  xor     edx, edx; length
0x180663d02  mov     rcx, [rbp+90h+string]; string
0x180663d06  call    cs:__imp_WindowsGetStringRawBuffer
0x180663d0d  nop     dword ptr [rax+rax+00h]
0x180663d12  mov     [rsp+190h+hTemplateFile], rdi; hTemplateFile
0x180663d17  mov     [rsp+190h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180663d1b  mov     [rsp+190h+dwCreationDisposition], 3; int
0x180663d23  xor     r9d, r9d; lpSecurityAttributes
0x180663d26  xor     edx, edx; dwDesiredAccess
0x180663d28  lea     r8d, [r9+7]; dwShareMode
0x180663d2c  mov     rcx, rax; lpFileName
0x180663d2f  call    cs:__imp_CreateFileW
0x180663d36  nop     dword ptr [rax+rax+00h]
0x180663d3b  mov     rdx, rax
0x180663d3e  lea     rcx, [rsp+190h+var_150]
0x180663d43  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180663d48  mov     rsi, [rsp+190h+var_150]
0x180663d4d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180663d51  jnz     short loc_180663D72
0x180663d53  mov     rcx, [rbp+98h]; this
0x180663d5a  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x180663d61  mov     edx, 3075h; void *
0x180663d66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180663d6b  mov     edi, eax
0x180663d6d  jmp     loc_1800BD42E
0x180663d72  mov     [rbp+90h+var_108], edi
0x180663d75  xor     edx, edx; length
0x180663d77  mov     rcx, [rbp+90h+string]; string
0x180663d7b  call    cs:__imp_WindowsGetStringRawBuffer
0x180663d82  nop     dword ptr [rax+rax+00h]
0x180663d87  lea     r8, [rbp+90h+var_108]
0x180663d8b  mov     rdx, rbx
0x180663d8e  mov     rcx, rax
0x180663d91  call    cs:__imp_EnterpriseDataProtect
0x180663d98  nop     dword ptr [rax+rax+00h]
0x180663d9d  mov     edi, eax
0x180663d9f  xor     edx, edx
0x180663da1  test    eax, eax
0x180663da3  jns     short loc_180663DC6
0x180663da5  mov     rcx, [rbp+98h]; this
0x180663dac  mov     r9d, eax; char *
0x180663daf  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x180663db6  mov     edx, 3078h; void *
0x180663dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180663dc0  nop
0x180663dc1  jmp     loc_1800BD42E
0x180663dc6  mov     ecx, [rbp+90h+var_108]
0x180663dc9  cmp     ecx, 3
0x180663dcc  jz      loc_180663E71
0x180663dd2  sub     ecx, 2
0x180663dd5  jz      short loc_180663E03
0x180663dd7  sub     ecx, 2
0x180663dda  jz      short loc_180663E59
0x180663ddc  sub     ecx, 1
0x180663ddf  jz      short loc_180663E59
0x180663de1  sub     ecx, 1
0x180663de4  jz      short loc_180663E41
0x180663de6  cmp     ecx, 1
0x180663de9  jz      short loc_180663E59
0x180663deb  mov     [rsp+190h+var_118], rdx
0x180663df0  mov     r9d, 2Bh ; '+'
0x180663df6  lea     r8d, [r9+1]
0x180663dfa  lea     rdx, aCouldNotProtec; "Could not protect the file: Reason unkn"...
0x180663e01  jmp     short loc_180663E19
0x180663e03  mov     [rsp+190h+var_118], rdx
0x180663e08  mov     r9d, 59h ; 'Y'; unsigned int
0x180663e0e  lea     r8d, [r9+1]; unsigned int
0x180663e12  lea     rdx, aThisFileWasAlr; "This file was already protected to an e"...
0x180663e19  lea     rcx, [rsp+190h+hstringHeader]; hstringHeader
0x180663e1e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180663e23  mov     rdx, [rsp+190h+var_118]
0x180663e28  mov     edi, 80090329h
0x180663e2d  mov     ecx, edi
0x180663e2f  call    cs:__imp_RoOriginateError
0x180663e36  nop     dword ptr [rax+rax+00h]
0x180663e3b  nop
0x180663e3c  jmp     loc_1800BD42E
0x180663e41  mov     [rsp+190h+var_118], rdx
  ... truncated ...
```
