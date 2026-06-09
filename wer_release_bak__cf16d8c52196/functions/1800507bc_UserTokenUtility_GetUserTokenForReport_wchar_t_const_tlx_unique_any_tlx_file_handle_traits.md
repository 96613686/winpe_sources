# UserTokenUtility::GetUserTokenForReport(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x1800507bc`
- end: `0x1800509ba`
- name: `?GetUserTokenForReport@UserTokenUtility@@SAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006ad60`

## callees

- `0x180005e08`
- `0x180007e10`
- `0x180007e34`
- `0x18000bc2c`
- `0x18001a2cc`
- `0x180027884`
- `0x18002bed4`
- `0x18003bf14`
- `0x1800507bc`
- `0x180050db0`
- `0x1800517cc`
- `0x1800a57d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508fd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800508c0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800508c0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180050896`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180050896`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005089f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005089f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180050884`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180050884`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180050867`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180050867`

## string_xrefs

- `0x180050925`: `onecore\windows\feedback\core\wercommon\libex\usertokenutility.cpp`
- `0x180050953`: `onecore\windows\feedback\core\wercommon\libex\usertokenutility.cpp`
- `0x1800508f4`: `GetUserTokenForReport failed. Unable to impersonate logged on user.`
- `0x180050917`: `GetUserTokenForReport failed. Unable to obtain a valid user token.`
- `0x18005083a`: `Unable to obtain a valid user token.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserTokenUtility::GetUserTokenForReport(LPCWSTR lpFileName, void **a2)
{
  signed int ActiveUserSessions; // ebx
  __int64 v5; // rdx
  const char *v6; // rax
  unsigned int *i; // rbx
  unsigned int v8; // edi
  __int64 v9; // rax
  HANDLE FirstFileW; // rdi
  signed int LastError; // eax
  signed int v12; // eax
  const char *v14; // [rsp+28h] [rbp-D8h]
  HANDLE hToken; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[3]; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v16);
  hToken = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !lpFileName )
  {
    ActiveUserSessions = -2147024809;
LABEL_20:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x3C9,
      (unsigned int)"onecore\\windows\\feedback\\core\\wercommon\\libex\\usertokenutility.cpp",
      (const char *)(unsigned int)ActiveUserSessions,
      (int)"No logged in users own this report, or report does not exist",
      v14);
    goto LABEL_22;
  }
  ActiveUserSessions = UserTokenUtility::QueryActiveUserSessions(v16);
  if ( ActiveUserSessions >= 0 )
  {
    for ( i = (unsigned int *)v16[0]; ; ++i )
    {
      if ( i == (unsigned int *)v16[1] )
      {
        ActiveUserSessions = 0;
        goto LABEL_22;
      }
      v8 = *i;
      v9 = tlx::replace<tlx::file_handle_traits>(&hToken);
      if ( !(unsigned int)QueryUserToken(v8, v9) || (unsigned __int64)hToken + 1 <= 1 )
        break;
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        LastError = GetLastError();
        ActiveUserSessions = LastError;
        if ( LastError > 0 )
          ActiveUserSessions = (unsigned __int16)LastError | 0x80070000;
        v5 = 933;
        v6 = "GetUserTokenForReport failed. Unable to impersonate logged on user.";
        goto LABEL_19;
      }
      FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
      RevertToSelf();
      if ( FirstFileW != (HANDLE)-1LL )
      {
        FindClose(FirstFileW);
        tlx::unique_any<tlx::file_handle_traits>::operator=(a2, &hToken);
        ActiveUserSessions = 0;
        goto LABEL_24;
      }
      tlx::unique_any<tlx::file_handle_traits>::reset(&hToken, 0);
    }
    v12 = GetLastError();
    ActiveUserSessions = v12;
    if ( v12 > 0 )
      ActiveUserSessions = (unsigned __int16)v12 | 0x80070000;
    v5 = 925;
    v6 = "GetUserTokenForReport failed. Unable to obtain a valid user token.";
  }
  else
  {
    v5 = 909;
    v6 = "Unable to obtain a valid user token.";
  }
LABEL_19:
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\windows\\feedback\\core\\wercommon\\libex\\usertokenutility.cpp",
    (const char *)(unsigned int)ActiveUserSessions,
    (int)v6,
    v14);
  if ( ActiveUserSessions < 0 )
    goto LABEL_20;
LABEL_22:
  if ( hToken != (HANDLE)-1LL && (char *)hToken + 1 != HANDLE_FLAG_INHERIT )
    MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_24:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hToken);
  utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(v16);
  return (unsigned int)ActiveUserSessions;
}

```

## disassembly

```asm
0x1800507bc  mov     [rsp-8+arg_10], rbx
0x1800507c1  mov     [rsp-8+arg_18], rsi
0x1800507c6  push    rbp
0x1800507c7  push    rdi
0x1800507c8  push    r14
0x1800507ca  lea     rbp, [rsp-1B0h]
0x1800507d2  sub     rsp, 2B0h
0x1800507d9  mov     rax, cs:__security_cookie
0x1800507e0  xor     rax, rsp
0x1800507e3  mov     [rbp+1C0h+var_20], rax
0x1800507ea  mov     r14, rdx
0x1800507ed  mov     rsi, rcx
0x1800507f0  lea     rcx, [rsp+2C0h+var_288]
0x1800507f5  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x1800507fa  nop
0x1800507fb  mov     [rsp+2C0h+hToken], 0
0x180050804  xor     edx, edx; Val
0x180050806  mov     r8d, 250h; Size
0x18005080c  lea     rcx, [rsp+2C0h+FindFileData]; void *
0x180050811  call    memset_0
0x180050816  test    rsi, rsi
0x180050819  jnz     short loc_180050825
0x18005081b  mov     ebx, 80070057h
0x180050820  jmp     loc_18005093D
0x180050825  lea     rcx, [rsp+2C0h+var_288]
0x18005082a  call    ?QueryActiveUserSessions@UserTokenUtility@@SAJAEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z; UserTokenUtility::QueryActiveUserSessions(utl::vector<ulong,utl::allocator<ulong>> &)
0x18005082f  mov     ebx, eax
0x180050831  test    eax, eax
0x180050833  jns     short loc_180050846
0x180050835  mov     edx, 38Dh
0x18005083a  lea     rax, aUnableToObtain; "Unable to obtain a valid user token."
0x180050841  jmp     loc_18005091E
0x180050846  mov     rbx, [rsp+2C0h+var_288]
0x18005084b  cmp     rbx, [rsp+2C0h+var_280]
0x180050850  jz      loc_180050966
0x180050856  mov     edi, [rbx]
0x180050858  lea     rcx, [rsp+2C0h+hToken]
0x18005085d  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180050862  mov     rdx, rax
0x180050865  mov     ecx, edi
0x180050867  call    cs:__imp_QueryUserToken
0x18005086d  test    eax, eax
0x18005086f  jz      loc_1800508FD
0x180050875  mov     rcx, [rsp+2C0h+hToken]; hToken
0x18005087a  lea     rax, [rcx+1]
0x18005087e  cmp     rax, 1
0x180050882  jbe     short loc_1800508FD
0x180050884  call    cs:__imp_ImpersonateLoggedOnUser
0x18005088a  test    eax, eax
0x18005088c  jz      short loc_1800508DA
0x18005088e  lea     rdx, [rsp+2C0h+FindFileData]; lpFindFileData
0x180050893  mov     rcx, rsi; lpFileName
0x180050896  call    cs:__imp_FindFirstFileW
0x18005089c  mov     rdi, rax
0x18005089f  call    cs:__imp_RevertToSelf
0x1800508a5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800508a9  jnz     short loc_1800508BD
0x1800508ab  xor     edx, edx
0x1800508ad  lea     rcx, [rsp+2C0h+hToken]
0x1800508b2  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800508b7  add     rbx, 4
0x1800508bb  jmp     short loc_18005084B
0x1800508bd  mov     rcx, rdi; hFindFile
0x1800508c0  call    cs:__imp_FindClose
0x1800508c6  lea     rdx, [rsp+2C0h+hToken]
0x1800508cb  mov     rcx, r14
0x1800508ce  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x1800508d3  xor     ebx, ebx
0x1800508d5  jmp     loc_18005097C
0x1800508da  call    cs:__imp_GetLastError
0x1800508e0  mov     ebx, eax
0x1800508e2  test    eax, eax
0x1800508e4  jle     short loc_1800508EF
0x1800508e6  movzx   ebx, ax
0x1800508e9  or      ebx, 80070000h
0x1800508ef  mov     edx, 3A5h
0x1800508f4  lea     rax, aGetusertokenfo_0; "GetUserTokenForReport failed. Unable to"...
0x1800508fb  jmp     short loc_18005091E
0x1800508fd  call    cs:__imp_GetLastError
0x180050903  mov     ebx, eax
0x180050905  test    eax, eax
0x180050907  jle     short loc_180050912
0x180050909  movzx   ebx, ax
0x18005090c  or      ebx, 80070000h
0x180050912  mov     edx, 39Dh; void *
0x180050917  lea     rax, aGetusertokenfo; "GetUserTokenForReport failed. Unable to"...
0x18005091e  mov     rcx, [rbp+1C8h]; this
0x180050925  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werco"...
0x18005092c  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x180050931  mov     r9d, ebx; char *
0x180050934  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050939  test    ebx, ebx
0x18005093b  jns     short loc_180050968
0x18005093d  mov     rcx, [rbp+1C8h]; this
0x180050944  lea     rax, aNoLoggedInUser; "No logged in users own this report, or "...
0x18005094b  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x180050950  mov     r9d, ebx; char *
0x180050953  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werco"...
0x18005095a  mov     edx, 3C9h; void *
0x18005095f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050964  jmp     short loc_180050968
0x180050966  xor     ebx, ebx
0x180050968  mov     rax, [rsp+2C0h+hToken]
0x18005096d  inc     rax
0x180050970  cmp     rax, 1
0x180050974  jbe     short loc_18005097C
0x180050976  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005097b  nop
0x18005097c  lea     rcx, [rsp+2C0h+hToken]
0x180050981  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180050986  nop
0x180050987  lea     rcx, [rsp+2C0h+var_288]
0x18005098c  call    ?_Uninit@?$vector@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@V?$allocator@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(void)
0x180050991  mov     eax, ebx
0x180050993  mov     rcx, [rbp+1C0h+var_20]
0x18005099a  xor     rcx, rsp; StackCookie
0x18005099d  call    __security_check_cookie
0x1800509a2  lea     r11, [rsp+2C0h+var_10]
0x1800509aa  mov     rbx, [r11+30h]
0x1800509ae  mov     rsi, [r11+38h]
0x1800509b2  mov     rsp, r11
0x1800509b5  pop     r14
0x1800509b7  pop     rdi
0x1800509b8  pop     rbp
0x1800509b9  retn
```
