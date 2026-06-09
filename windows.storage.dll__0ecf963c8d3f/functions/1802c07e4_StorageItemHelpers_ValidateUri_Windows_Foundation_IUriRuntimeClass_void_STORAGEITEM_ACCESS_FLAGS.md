# StorageItemHelpers::ValidateUri(Windows::Foundation::IUriRuntimeClass *,void *,STORAGEITEM_ACCESS_FLAGS)

- ea: `0x1802c07e4`
- end: `0x1802c0ba6`
- name: `?ValidateUri@StorageItemHelpers@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAXW4STORAGEITEM_ACCESS_FLAGS@@@Z`
- size: `962`
- prototype: `int __high(struct Windows::Foundation::IUriRuntimeClass *, void *, enum STORAGEITEM_ACCESS_FLAGS)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1802c0550`
- `0x180359360`
- `0x1803ed710`
- `0x180418b4c`

## callees

- `0x180010110`
- `0x180010220`
- `0x180011660`
- `0x1800432f0`
- `0x180060a10`
- `0x180068eec`
- `0x18028049c`
- `0x1802c07e4`
- `0x1802c0bac`
- `0x1802edadc`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802c088c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802c0917`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802c088c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802c0917`
- `FirewallAPI!NetworkIsolationDiagnoseConnectFailureAndGetInfo` at `0x1802c0a2c`
- `FirewallAPI!NetworkIsolationDiagnoseConnectFailureAndGetInfo` at `0x1802c0a2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802c0870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802c0900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802c0870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802c0900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802c0a1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802c0a1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c0a69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c0b1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c0b71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c0a69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c0b1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c0b71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1802c08a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1802c08d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1802c0934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1802c08a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1802c08d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1802c0934`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802c09e9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802c09e9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802c0a58`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802c0a89`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802c0a58`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802c0a89`

## string_xrefs

- `0x1802c0991`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1802c09d0`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1802c09f7`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1802c0a79`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1802c0b03`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1802c0b55`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1802c0816`: `ValidateUri`

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
  HSTRING *v12; // rax
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
  INT32 result; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string1; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v28; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v29; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[192]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  WinRTStorageTelemetry::WatchCurrentThread(v30, "ValidateUri", 0);
  string1 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 136LL))(a1, &string1);
  LastError = v6;
  if ( v6 >= 0 )
  {
    v10 = 1;
    if ( WindowsCreateStringReference(L"http", 4u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    result = 0;
    WindowsCompareStringOrdinal(string1, string, &result);
    v13 = 1;
    if ( result )
    {
      v12 = (HSTRING *)Windows::Internal::StringReference::StringReference(v25, (const unsigned __int16 (*)[6])v11);
      result = 0;
      WindowsCompareStringOrdinal(string1, *v12, &result);
      if ( result )
        v13 = 0;
    }
    if ( WindowsCreateStringReference(L"ms-appx", 7u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    result = 0;
    WindowsCompareStringOrdinal(string1, string, &result);
    if ( result )
    {
      v14 = Windows::Internal::StringReference::StringReference(v25, L"ms-appdata");
      if ( !(unsigned __int8)Windows::Internal::operator==(&string1, v14) )
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
      v28 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 88LL))(a1, &v28);
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
        Windows::Internal::String::~String((Windows::Internal::String *)&v28);
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
      result = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(v28, 0);
      Info = NetworkIsolationDiagnoseConnectFailureAndGetInfo(StringRawBuffer, (NETISO_ERROR_TYPE *)&result);
      LastError = Info;
      if ( Info > 0 )
        LastError = (unsigned __int16)Info | 0x80070000;
      if ( (LastError & 0x80000000) != 0 )
      {
        v19 = 8255;
        goto LABEL_31;
      }
      if ( result )
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
      if ( v28 )
        WindowsDeleteString(v28);
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
      if ( string1 )
        WindowsDeleteString(string1);
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
        Windows::Internal::String::~String((Windows::Internal::String *)&string1);
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
  Windows::Internal::String::~String((Windows::Internal::String *)&string1);
LABEL_46:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v30);
  return LastError;
}

```

## disassembly

```asm
0x1802c07e4  mov     [rsp-8+arg_10], rbx
0x1802c07e9  push    rbp
0x1802c07ea  push    rsi
0x1802c07eb  push    rdi
0x1802c07ec  push    r14
0x1802c07ee  push    r15
0x1802c07f0  lea     rbp, [rsp-50h]
0x1802c07f5  sub     rsp, 150h
0x1802c07fc  mov     rax, cs:__security_cookie
0x1802c0803  xor     rax, rsp
0x1802c0806  mov     [rbp+70h+var_30], rax
0x1802c080a  mov     r15d, r8d
0x1802c080d  mov     r14, rdx
0x1802c0810  mov     rdi, rcx
0x1802c0813  xor     r8d, r8d
0x1802c0816  lea     rdx, aValidateuri; "ValidateUri"
0x1802c081d  lea     rcx, [rbp+70h+var_F0]
0x1802c0821  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x1802c0826  nop
0x1802c0827  mov     [rsp+170h+string1], 0
0x1802c0830  mov     rax, [rdi]
0x1802c0833  lea     rdx, [rsp+170h+string1]
0x1802c0838  mov     rcx, rdi
0x1802c083b  mov     rax, [rax+88h]
0x1802c0842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c0847  mov     ebx, eax
0x1802c0849  test    eax, eax
0x1802c084b  jns     short loc_1802C085A
0x1802c084d  mov     r9d, eax
0x1802c0850  mov     edx, 2026h
0x1802c0855  jmp     loc_1802C0991
0x1802c085a  lea     r9, [rsp+170h+string]; string
0x1802c085f  lea     r8, [rsp+170h+hstringHeader]; hstringHeader
0x1802c0864  mov     edx, 4; length
0x1802c0869  lea     rcx, aHttp_0; "http"
0x1802c0870  call    cs:__imp_WindowsCreateStringReference
0x1802c0876  mov     ebx, 1
0x1802c087b  test    eax, eax
0x1802c087d  jns     short loc_1802C0892
0x1802c087f  xor     r9d, r9d; lpArguments
0x1802c0882  xor     r8d, r8d; nNumberOfArguments
0x1802c0885  mov     edx, ebx; dwExceptionFlags
0x1802c0887  mov     ecx, 0C000000Dh; dwExceptionCode
0x1802c088c  call    cs:__imp_RaiseException
0x1802c0892  mov     [rsp+170h+result], 0
0x1802c089a  lea     r8, [rsp+170h+result]; result
0x1802c089f  mov     rdx, [rsp+170h+string]; string2
0x1802c08a4  mov     rcx, [rsp+170h+string1]; string1
0x1802c08a9  call    cs:__imp_WindowsCompareStringOrdinal
0x1802c08af  cmp     [rsp+170h+result], 0
0x1802c08b4  jz      short loc_1802C08E7
0x1802c08b6  lea     rcx, [rsp+170h+var_130]; string
0x1802c08bb  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x1802c08c0  mov     [rsp+170h+result], 0
0x1802c08c8  lea     r8, [rsp+170h+result]; result
0x1802c08cd  mov     rdx, [rax]; string2
0x1802c08d0  mov     rcx, [rsp+170h+string1]; string1
0x1802c08d5  call    cs:__imp_WindowsCompareStringOrdinal
0x1802c08db  cmp     [rsp+170h+result], 0
0x1802c08e0  jz      short loc_1802C08E7
0x1802c08e2  xor     sil, sil
0x1802c08e5  jmp     short loc_1802C08EA
0x1802c08e7  mov     sil, bl
0x1802c08ea  lea     r9, [rsp+170h+string]; string
0x1802c08ef  lea     r8, [rsp+170h+hstringHeader]; hstringHeader
0x1802c08f4  mov     edx, 7; length
0x1802c08f9  lea     rcx, aMsAppx; "ms-appx"
0x1802c0900  call    cs:__imp_WindowsCreateStringReference
0x1802c0906  test    eax, eax
0x1802c0908  jns     short loc_1802C091D
0x1802c090a  xor     r9d, r9d; lpArguments
0x1802c090d  xor     r8d, r8d; nNumberOfArguments
0x1802c0910  mov     edx, ebx; dwExceptionFlags
0x1802c0912  mov     ecx, 0C000000Dh; dwExceptionCode
0x1802c0917  call    cs:__imp_RaiseException
0x1802c091d  mov     [rsp+170h+result], 0
0x1802c0925  lea     r8, [rsp+170h+result]; result
0x1802c092a  mov     rdx, [rsp+170h+string]; string2
0x1802c092f  mov     rcx, [rsp+170h+string1]; string1
0x1802c0934  call    cs:__imp_WindowsCompareStringOrdinal
0x1802c093a  cmp     [rsp+170h+result], 0
0x1802c093f  jz      short loc_1802C0965
0x1802c0941  lea     rdx, aMsAppdata; "ms-appdata"
0x1802c0948  lea     rcx, [rsp+170h+var_130]; string
0x1802c094d  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x1802c0952  mov     rdx, rax
0x1802c0955  lea     rcx, [rsp+170h+string1]
0x1802c095a  call    ??8Internal@Windows@@YA_NAEBVString@01@0@Z; Windows::Internal::operator==(Windows::Internal::String const &,Windows::Internal::String const &)
0x1802c095f  test    al, al
0x1802c0961  jnz     short loc_1802C0965
0x1802c0963  xor     bl, bl
0x1802c0965  test    r15b, 4
0x1802c0969  jz      loc_1802C0AAA
0x1802c096f  test    sil, sil
0x1802c0972  jz      loc_1802C0AAA
0x1802c0978  lea     rax, [r14+1]
0x1802c097c  test    rax, 0FFFFFFFFFFFFFFFEh
0x1802c0982  jnz     short loc_1802C09A6
0x1802c0984  mov     ebx, 8007013Bh
0x1802c0989  mov     r9d, ebx; char *
0x1802c098c  mov     edx, 2031h; void *
0x1802c0991  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1802c0998  mov     rcx, [rbp+78h]; this
0x1802c099c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c09a1  jmp     loc_1802C0A9B
0x1802c09a6  mov     [rsp+170h+var_100], 0
0x1802c09af  mov     rax, [rdi]
0x1802c09b2  lea     rdx, [rsp+170h+var_100]
0x1802c09b7  mov     rcx, rdi
0x1802c09ba  mov     rax, [rax+58h]
0x1802c09be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c09c3  mov     ebx, eax
0x1802c09c5  test    eax, eax
0x1802c09c7  jns     short loc_1802C09E6
0x1802c09c9  mov     rcx, [rbp+78h]; this
0x1802c09cd  mov     r9d, eax; char *
0x1802c09d0  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1802c09d7  mov     edx, 2034h; void *
0x1802c09dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c09e1  jmp     loc_1802C0A90
0x1802c09e6  mov     rcx, r14; hToken
0x1802c09e9  call    cs:__imp_ImpersonateLoggedOnUser
0x1802c09ef  test    eax, eax
0x1802c09f1  jnz     short loc_1802C0A0F
0x1802c09f3  mov     rcx, [rbp+78h]; this
0x1802c09f7  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1802c09fe  mov     edx, 2038h; void *
0x1802c0a03  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802c0a08  mov     ebx, eax
0x1802c0a0a  jmp     loc_1802C0A90
0x1802c0a0f  mov     [rsp+170h+result], 0
0x1802c0a17  xor     edx, edx; length
0x1802c0a19  mov     rcx, [rsp+170h+var_100]; string
0x1802c0a1e  call    cs:__imp_WindowsGetStringRawBuffer
0x1802c0a24  lea     rdx, [rsp+170h+result]; netIsoError
0x1802c0a29  mov     rcx, rax; wszServerName
0x1802c0a2c  call    cs:__imp_NetworkIsolationDiagnoseConnectFailureAndGetInfo
0x1802c0a32  mov     ebx, eax
0x1802c0a34  test    eax, eax
0x1802c0a36  jle     short loc_1802C0A41
0x1802c0a38  movzx   ebx, ax
0x1802c0a3b  or      ebx, 80070000h
0x1802c0a41  test    ebx, ebx
0x1802c0a43  js      short loc_1802C0A71
0x1802c0a45  cmp     [rsp+170h+result], 0
0x1802c0a4a  jz      short loc_1802C0A58
0x1802c0a4c  mov     ebx, 80070005h
0x1802c0a51  mov     edx, 203Eh
0x1802c0a56  jmp     short loc_1802C0A76
0x1802c0a58  call    cs:__imp_RevertToSelf
0x1802c0a5e  nop
0x1802c0a5f  mov     rcx, [rsp+170h+var_100]; string
0x1802c0a64  test    rcx, rcx
0x1802c0a67  jz      short loc_1802C0ABC
0x1802c0a69  call    cs:__imp_WindowsDeleteString
0x1802c0a6f  jmp     short loc_1802C0ABC
0x1802c0a71  mov     edx, 203Fh; void *
0x1802c0a76  mov     r9d, ebx; char *
0x1802c0a79  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1802c0a80  mov     rcx, [rbp+78h]; this
0x1802c0a84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c0a89  call    cs:__imp_RevertToSelf
0x1802c0a8f  nop
0x1802c0a90  lea     rcx, [rsp+170h+var_100]; this
0x1802c0a95  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802c0a9a  nop
0x1802c0a9b  lea     rcx, [rsp+170h+string1]; this
0x1802c0aa0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802c0aa5  jmp     loc_1802C0B78
0x1802c0aaa  test    r15b, 2
0x1802c0aae  jz      loc_1802C0B49
0x1802c0ab4  test    bl, bl
0x1802c0ab6  jz      loc_1802C0B49
0x1802c0abc  mov     [rsp+170h+var_F8], 0
0x1802c0ac5  mov     rax, [rdi]
0x1802c0ac8  lea     rdx, [rsp+170h+var_F8]
0x1802c0acd  mov     rcx, rdi
0x1802c0ad0  mov     rax, [rax+68h]
0x1802c0ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c0ad9  mov     ebx, eax
0x1802c0adb  test    eax, eax
0x1802c0add  jns     short loc_1802C0AE6
0x1802c0adf  mov     edx, 204Eh
0x1802c0ae4  jmp     short loc_1802C0B00
0x1802c0ae6  mov     edx, 3
0x1802c0aeb  mov     rcx, [rsp+170h+var_F8]
0x1802c0af0  call    ?ValidateCanonicalPath@StorageItemHelpers@@YAJPEAUHSTRING__@@W4CANONICALIZE_FLAGS@@@Z; StorageItemHelpers::ValidateCanonicalPath(HSTRING__ *,CANONICALIZE_FLAGS)
0x1802c0af5  mov     ebx, eax
0x1802c0af7  test    eax, eax
0x1802c0af9  jns     short loc_1802C0B26
0x1802c0afb  mov     edx, 204Fh; void *
0x1802c0b00  mov     r9d, eax; char *
0x1802c0b03  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1802c0b0a  mov     rcx, [rbp+78h]; this
0x1802c0b0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c0b13  nop
0x1802c0b14  mov     rcx, [rsp+170h+var_F8]; string
0x1802c0b19  test    rcx, rcx
0x1802c0b1c  jz      short loc_1802C0B67
0x1802c0b1e  call    cs:__imp_WindowsDeleteString
0x1802c0b24  jmp     short loc_1802C0B67
0x1802c0b26  lea     rcx, [rsp+170h+var_F8]; this
0x1802c0b2b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802c0b30  nop
0x1802c0b31  lea     rcx, [rsp+170h+string1]; this
0x1802c0b36  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802c0b3b  nop
0x1802c0b3c  lea     rcx, [rbp+70h+var_F0]; this
0x1802c0b40  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1802c0b45  xor     eax, eax
0x1802c0b47  jmp     short loc_1802C0B83
0x1802c0b49  mov     rcx, [rbp+78h]; this
0x1802c0b4d  mov     ebx, 80070057h
0x1802c0b52  mov     r9d, ebx; char *
0x1802c0b55  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1802c0b5c  mov     edx, 2049h; void *
0x1802c0b61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c0b66  nop
0x1802c0b67  mov     rcx, [rsp+170h+string1]; string
0x1802c0b6c  test    rcx, rcx
0x1802c0b6f  jz      short loc_1802C0B78
0x1802c0b71  call    cs:__imp_WindowsDeleteString
0x1802c0b77  nop
0x1802c0b78  lea     rcx, [rbp+70h+var_F0]; this
0x1802c0b7c  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1802c0b81  mov     eax, ebx
0x1802c0b83  mov     rcx, [rbp+70h+var_30]
0x1802c0b87  xor     rcx, rsp; StackCookie
0x1802c0b8a  call    __security_check_cookie
0x1802c0b8f  mov     rbx, [rsp+170h+arg_10]
0x1802c0b97  add     rsp, 150h
0x1802c0b9e  pop     r15
0x1802c0ba0  pop     r14
0x1802c0ba2  pop     rdi
0x1802c0ba3  pop     rsi
0x1802c0ba4  pop     rbp
0x1802c0ba5  retn
```
