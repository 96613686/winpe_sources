# StorageItemHelpers::ValidateUri(Windows::Foundation::IUriRuntimeClass *,void *,STORAGEITEM_ACCESS_FLAGS)

- ea: `0x18021dda8`
- end: `0x18021e180`
- name: `?ValidateUri@StorageItemHelpers@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAXW4STORAGEITEM_ACCESS_FLAGS@@@Z`
- size: `984`
- prototype: `int __high(struct Windows::Foundation::IUriRuntimeClass *, void *, enum STORAGEITEM_ACCESS_FLAGS)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18021f0d0`
- `0x18036a210`
- `0x1803fcbf0`
- `0x180428c0c`

## callees

- `0x180017e60`
- `0x180038f50`
- `0x18007bbf0`
- `0x18007c1c0`
- `0x18007c510`
- `0x180083c94`
- `0x18021dda8`
- `0x18021e588`
- `0x18021e638`
- `0x1802fe700`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021de56`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021decb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021de56`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021decb`
- `FirewallAPI!NetworkIsolationDiagnoseConnectFailureAndGetInfo` at `0x18021dfe1`
- `FirewallAPI!NetworkIsolationDiagnoseConnectFailureAndGetInfo` at `0x18021dfe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021de34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021deae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021de34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021deae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021dfcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021dfcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021e02a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021e0eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021e144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021e02a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021e0eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021e144`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18021df92`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18021df92`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18021e013`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18021e050`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18021e013`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18021e050`

## string_xrefs

- `0x18021df3a`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021df79`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021dfa6`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021e040`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021e0d0`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021e128`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18021ddda`: `ValidateUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StorageItemHelpers::ValidateUri(__int64 a1, void *a2, char a3)
{
  int v6; // eax
  unsigned int LastError; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  char v10; // bl
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  bool v13; // si
  __int64 v14; // rax
  int v15; // eax
  const char *v16; // r9
  const WCHAR *StringRawBuffer; // rax
  signed int Info; // eax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING v25[4]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v26; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v27; // [rsp+68h] [rbp-98h] BYREF
  NETISO_ERROR_TYPE netIsoError; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v29; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[192]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  WinRTStorageTelemetry::WatchCurrentThread(v30, "ValidateUri", 0);
  v26 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 136LL))(a1, &v26);
  LastError = v6;
  if ( v6 >= 0 )
  {
    v10 = 1;
    if ( WindowsCreateStringReference(L"http", 4u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v13 = 1;
    if ( !(unsigned __int8)Windows::Internal::operator==(&v26, &string) )
    {
      v12 = Windows::Internal::StringReference::StringReference(v25, (const unsigned __int16 (*)[6])v11);
      if ( !(unsigned __int8)Windows::Internal::operator==(&v26, v12) )
        v13 = 0;
    }
    if ( WindowsCreateStringReference(L"ms-appx", 7u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    if ( !(unsigned __int8)Windows::Internal::operator==(&v26, &string) )
    {
      v14 = Windows::Internal::StringReference::StringReference(v25, L"ms-appdata");
      if ( !(unsigned __int8)Windows::Internal::operator==(&v26, v14) )
        v10 = 0;
    }
    if ( (a3 & 4) != 0 && v13 )
    {
      if ( (((unsigned __int64)a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastError = -2147024581;
        v8 = 2147942715LL;
        v9 = 8241;
        goto LABEL_18;
      }
      v27 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 88LL))(a1, &v27);
      LastError = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2034,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
          (const char *)(unsigned int)v15,
          (int)string);
LABEL_32:
        Windows::Internal::String::~String((Windows::Internal::String *)&v27);
        goto LABEL_33;
      }
      if ( !ImpersonateLoggedOnUser(a2) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x2038,
                      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
                      v16);
        goto LABEL_32;
      }
      netIsoError = NETISO_ERROR_TYPE_NONE;
      StringRawBuffer = WindowsGetStringRawBuffer(v27, 0);
      Info = NetworkIsolationDiagnoseConnectFailureAndGetInfo(StringRawBuffer, &netIsoError);
      LastError = Info;
      if ( Info > 0 )
        LastError = (unsigned __int16)Info | 0x80070000;
      if ( (LastError & 0x80000000) != 0 )
      {
        v19 = 8255;
        goto LABEL_31;
      }
      if ( netIsoError )
      {
        LastError = -2147024891;
        v19 = 8254;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
          (const char *)LastError,
          (int)string);
        RevertToSelf();
        goto LABEL_32;
      }
      RevertToSelf();
      if ( v27 )
        WindowsDeleteString(v27);
    }
    else if ( (a3 & 2) == 0 || !v10 )
    {
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2049,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)0x80070057LL,
        (int)string);
LABEL_44:
      if ( v26 )
        WindowsDeleteString(v26);
      goto LABEL_46;
    }
    v29 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 104LL))(a1, &v29);
    LastError = v20;
    if ( v20 >= 0 )
    {
      v20 = StorageItemHelpers::ValidateCanonicalPath(v29, 3);
      LastError = v20;
      if ( v20 >= 0 )
      {
        Windows::Internal::String::~String((Windows::Internal::String *)&v29);
        Windows::Internal::String::~String((Windows::Internal::String *)&v26);
        StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v30);
        return 0;
      }
      v21 = 8271;
    }
    else
    {
      v21 = 8270;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v20,
      (int)string);
    if ( v29 )
      WindowsDeleteString(v29);
    goto LABEL_44;
  }
  v8 = (unsigned int)v6;
  v9 = 8230;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
    (const char *)v8,
    (int)string);
LABEL_33:
  Windows::Internal::String::~String((Windows::Internal::String *)&v26);
LABEL_46:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v30);
  return LastError;
}

```

## disassembly

```asm
0x18021dda8  mov     [rsp-8+arg_10], rbx
0x18021ddad  push    rbp
0x18021ddae  push    rsi
0x18021ddaf  push    rdi
0x18021ddb0  push    r14
0x18021ddb2  push    r15
0x18021ddb4  lea     rbp, [rsp-50h]
0x18021ddb9  sub     rsp, 150h
0x18021ddc0  mov     rax, cs:__security_cookie
0x18021ddc7  xor     rax, rsp
0x18021ddca  mov     [rbp+70h+var_30], rax
0x18021ddce  mov     r15d, r8d
0x18021ddd1  mov     r14, rdx
0x18021ddd4  mov     rdi, rcx
0x18021ddd7  xor     r8d, r8d
0x18021ddda  lea     rdx, aValidateuri; "ValidateUri"
0x18021dde1  lea     rcx, [rbp+70h+var_F0]
0x18021dde5  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x18021ddea  nop
0x18021ddeb  mov     [rsp+170h+var_110], 0
0x18021ddf4  mov     rax, [rdi]
0x18021ddf7  lea     rdx, [rsp+170h+var_110]
0x18021ddfc  mov     rcx, rdi
0x18021ddff  mov     rax, [rax+88h]
0x18021de06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021de0b  mov     ebx, eax
0x18021de0d  test    eax, eax
0x18021de0f  jns     short loc_18021DE1E
0x18021de11  mov     r9d, eax
0x18021de14  mov     edx, 2026h
0x18021de19  jmp     loc_18021DF3A
0x18021de1e  lea     r9, [rsp+170h+string]; string
0x18021de23  lea     r8, [rsp+170h+hstringHeader]; hstringHeader
0x18021de28  mov     edx, 4; length
0x18021de2d  lea     rcx, aHttp_0; "http"
0x18021de34  call    cs:__imp_WindowsCreateStringReference
0x18021de3b  nop     dword ptr [rax+rax+00h]
0x18021de40  mov     ebx, 1
0x18021de45  test    eax, eax
0x18021de47  jns     short loc_18021DE62
0x18021de49  xor     r9d, r9d; lpArguments
0x18021de4c  xor     r8d, r8d; nNumberOfArguments
0x18021de4f  mov     edx, ebx; dwExceptionFlags
0x18021de51  mov     ecx, 0C000000Dh; dwExceptionCode
0x18021de56  call    cs:__imp_RaiseException
0x18021de5d  nop     dword ptr [rax+rax+00h]
0x18021de62  lea     rdx, [rsp+170h+string]
0x18021de67  lea     rcx, [rsp+170h+var_110]
0x18021de6c  call    ??8Internal@Windows@@YA_NAEBVString@01@0@Z; Windows::Internal::operator==(Windows::Internal::String const &,Windows::Internal::String const &)
0x18021de71  test    al, al
0x18021de73  jnz     short loc_18021DE95
0x18021de75  lea     rcx, [rsp+170h+var_130]; string
0x18021de7a  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x18021de7f  mov     rdx, rax
0x18021de82  lea     rcx, [rsp+170h+var_110]
0x18021de87  call    ??8Internal@Windows@@YA_NAEBVString@01@0@Z; Windows::Internal::operator==(Windows::Internal::String const &,Windows::Internal::String const &)
0x18021de8c  test    al, al
0x18021de8e  jnz     short loc_18021DE95
0x18021de90  xor     sil, sil
0x18021de93  jmp     short loc_18021DE98
0x18021de95  mov     sil, bl
0x18021de98  lea     r9, [rsp+170h+string]; string
0x18021de9d  lea     r8, [rsp+170h+hstringHeader]; hstringHeader
0x18021dea2  mov     edx, 7; length
0x18021dea7  lea     rcx, aMsAppx; "ms-appx"
0x18021deae  call    cs:__imp_WindowsCreateStringReference
0x18021deb5  nop     dword ptr [rax+rax+00h]
0x18021deba  test    eax, eax
0x18021debc  jns     short loc_18021DED7
0x18021debe  xor     r9d, r9d; lpArguments
0x18021dec1  xor     r8d, r8d; nNumberOfArguments
0x18021dec4  mov     edx, ebx; dwExceptionFlags
0x18021dec6  mov     ecx, 0C000000Dh; dwExceptionCode
0x18021decb  call    cs:__imp_RaiseException
0x18021ded2  nop     dword ptr [rax+rax+00h]
0x18021ded7  lea     rdx, [rsp+170h+string]
0x18021dedc  lea     rcx, [rsp+170h+var_110]
0x18021dee1  call    ??8Internal@Windows@@YA_NAEBVString@01@0@Z; Windows::Internal::operator==(Windows::Internal::String const &,Windows::Internal::String const &)
0x18021dee6  test    al, al
0x18021dee8  jnz     short loc_18021DF0E
0x18021deea  lea     rdx, aMsAppdata; "ms-appdata"
0x18021def1  lea     rcx, [rsp+170h+var_130]; string
0x18021def6  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x18021defb  mov     rdx, rax
0x18021defe  lea     rcx, [rsp+170h+var_110]
0x18021df03  call    ??8Internal@Windows@@YA_NAEBVString@01@0@Z; Windows::Internal::operator==(Windows::Internal::String const &,Windows::Internal::String const &)
0x18021df08  test    al, al
0x18021df0a  jnz     short loc_18021DF0E
0x18021df0c  xor     bl, bl
0x18021df0e  test    r15b, 4
0x18021df12  jz      loc_18021E077
0x18021df18  test    sil, sil
0x18021df1b  jz      loc_18021E077
0x18021df21  lea     rax, [r14+1]
0x18021df25  test    rax, 0FFFFFFFFFFFFFFFEh
0x18021df2b  jnz     short loc_18021DF4F
0x18021df2d  mov     ebx, 8007013Bh
0x18021df32  mov     r9d, ebx; char *
0x18021df35  mov     edx, 2031h; void *
0x18021df3a  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021df41  mov     rcx, [rbp+78h]; this
0x18021df45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021df4a  jmp     loc_18021E068
0x18021df4f  mov     [rsp+170h+var_108], 0
0x18021df58  mov     rax, [rdi]
0x18021df5b  lea     rdx, [rsp+170h+var_108]
0x18021df60  mov     rcx, rdi
0x18021df63  mov     rax, [rax+58h]
0x18021df67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021df6c  mov     ebx, eax
0x18021df6e  test    eax, eax
0x18021df70  jns     short loc_18021DF8F
0x18021df72  mov     rcx, [rbp+78h]; this
0x18021df76  mov     r9d, eax; char *
0x18021df79  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021df80  mov     edx, 2034h; void *
0x18021df85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021df8a  jmp     loc_18021E05D
0x18021df8f  mov     rcx, r14; hToken
0x18021df92  call    cs:__imp_ImpersonateLoggedOnUser
0x18021df99  nop     dword ptr [rax+rax+00h]
0x18021df9e  test    eax, eax
0x18021dfa0  jnz     short loc_18021DFBE
0x18021dfa2  mov     rcx, [rbp+78h]; this
0x18021dfa6  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021dfad  mov     edx, 2038h; void *
0x18021dfb2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18021dfb7  mov     ebx, eax
0x18021dfb9  jmp     loc_18021E05D
0x18021dfbe  mov     [rsp+170h+netIsoError], 0
0x18021dfc6  xor     edx, edx; length
0x18021dfc8  mov     rcx, [rsp+170h+var_108]; string
0x18021dfcd  call    cs:__imp_WindowsGetStringRawBuffer
0x18021dfd4  nop     dword ptr [rax+rax+00h]
0x18021dfd9  lea     rdx, [rsp+170h+netIsoError]; netIsoError
0x18021dfde  mov     rcx, rax; wszServerName
0x18021dfe1  call    cs:__imp_NetworkIsolationDiagnoseConnectFailureAndGetInfo
0x18021dfe8  nop     dword ptr [rax+rax+00h]
0x18021dfed  mov     ebx, eax
0x18021dfef  test    eax, eax
0x18021dff1  jle     short loc_18021DFFC
0x18021dff3  movzx   ebx, ax
0x18021dff6  or      ebx, 80070000h
0x18021dffc  test    ebx, ebx
0x18021dffe  js      short loc_18021E038
0x18021e000  cmp     [rsp+170h+netIsoError], 0
0x18021e005  jz      short loc_18021E013
0x18021e007  mov     ebx, 80070005h
0x18021e00c  mov     edx, 203Eh
0x18021e011  jmp     short loc_18021E03D
0x18021e013  call    cs:__imp_RevertToSelf
0x18021e01a  nop     dword ptr [rax+rax+00h]
0x18021e01f  nop
0x18021e020  mov     rcx, [rsp+170h+var_108]; string
0x18021e025  test    rcx, rcx
0x18021e028  jz      short loc_18021E089
0x18021e02a  call    cs:__imp_WindowsDeleteString
0x18021e031  nop     dword ptr [rax+rax+00h]
0x18021e036  jmp     short loc_18021E089
0x18021e038  mov     edx, 203Fh; void *
0x18021e03d  mov     r9d, ebx; char *
0x18021e040  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021e047  mov     rcx, [rbp+78h]; this
0x18021e04b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021e050  call    cs:__imp_RevertToSelf
0x18021e057  nop     dword ptr [rax+rax+00h]
0x18021e05c  nop
0x18021e05d  lea     rcx, [rsp+170h+var_108]; this
0x18021e062  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021e067  nop
0x18021e068  lea     rcx, [rsp+170h+var_110]; this
0x18021e06d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021e072  jmp     loc_18021E151
0x18021e077  test    r15b, 2
0x18021e07b  jz      loc_18021E11C
0x18021e081  test    bl, bl
0x18021e083  jz      loc_18021E11C
0x18021e089  mov     [rsp+170h+var_F8], 0
0x18021e092  mov     rax, [rdi]
0x18021e095  lea     rdx, [rsp+170h+var_F8]
0x18021e09a  mov     rcx, rdi
0x18021e09d  mov     rax, [rax+68h]
0x18021e0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021e0a6  mov     ebx, eax
0x18021e0a8  test    eax, eax
0x18021e0aa  jns     short loc_18021E0B3
0x18021e0ac  mov     edx, 204Eh
0x18021e0b1  jmp     short loc_18021E0CD
0x18021e0b3  mov     edx, 3
0x18021e0b8  mov     rcx, [rsp+170h+var_F8]
0x18021e0bd  call    ?ValidateCanonicalPath@StorageItemHelpers@@YAJPEAUHSTRING__@@W4CANONICALIZE_FLAGS@@@Z; StorageItemHelpers::ValidateCanonicalPath(HSTRING__ *,CANONICALIZE_FLAGS)
0x18021e0c2  mov     ebx, eax
0x18021e0c4  test    eax, eax
0x18021e0c6  jns     short loc_18021E0F9
0x18021e0c8  mov     edx, 204Fh; void *
0x18021e0cd  mov     r9d, eax; char *
0x18021e0d0  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021e0d7  mov     rcx, [rbp+78h]; this
0x18021e0db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021e0e0  nop
0x18021e0e1  mov     rcx, [rsp+170h+var_F8]; string
0x18021e0e6  test    rcx, rcx
0x18021e0e9  jz      short loc_18021E13A
0x18021e0eb  call    cs:__imp_WindowsDeleteString
0x18021e0f2  nop     dword ptr [rax+rax+00h]
0x18021e0f7  jmp     short loc_18021E13A
0x18021e0f9  lea     rcx, [rsp+170h+var_F8]; this
0x18021e0fe  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021e103  nop
0x18021e104  lea     rcx, [rsp+170h+var_110]; this
0x18021e109  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18021e10e  nop
0x18021e10f  lea     rcx, [rbp+70h+var_F0]; this
0x18021e113  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18021e118  xor     eax, eax
0x18021e11a  jmp     short loc_18021E15C
0x18021e11c  mov     rcx, [rbp+78h]; this
0x18021e120  mov     ebx, 80070057h
0x18021e125  mov     r9d, ebx; char *
0x18021e128  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18021e12f  mov     edx, 2049h; void *
0x18021e134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021e139  nop
0x18021e13a  mov     rcx, [rsp+170h+var_110]; string
0x18021e13f  test    rcx, rcx
0x18021e142  jz      short loc_18021E151
0x18021e144  call    cs:__imp_WindowsDeleteString
0x18021e14b  nop     dword ptr [rax+rax+00h]
0x18021e150  nop
0x18021e151  lea     rcx, [rbp+70h+var_F0]; this
0x18021e155  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18021e15a  mov     eax, ebx
0x18021e15c  mov     rcx, [rbp+70h+var_30]
0x18021e160  xor     rcx, rsp; StackCookie
0x18021e163  call    __security_check_cookie
0x18021e168  mov     rbx, [rsp+170h+arg_10]
0x18021e170  add     rsp, 150h
0x18021e177  pop     r15
0x18021e179  pop     r14
0x18021e17b  pop     rdi
0x18021e17c  pop     rsi
0x18021e17d  pop     rbp
0x18021e17e  retn
```
