# UserTokenUtility::GetUserTokenForReport(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180052cc4`
- end: `0x180052efe`
- name: `?GetUserTokenForReport@UserTokenUtility@@SAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006df10`

## callees

- `0x1800058a4`
- `0x180005be8`
- `0x180006a24`
- `0x180007fd8`
- `0x180008004`
- `0x180028648`
- `0x180028760`
- `0x18002d930`
- `0x18003de9c`
- `0x180052cc4`
- `0x180053300`
- `0x180053d3c`
- `0x1800aa638`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e3a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180052dae`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180052dae`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180052dc2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180052dc2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180052d96`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180052d96`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180052d6f`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180052d6f`

## string_xrefs

- `0x180052e68`: `onecore\windows\feedback\core\wercommon\libex\usertokenutility.cpp`
- `0x180052e96`: `onecore\windows\feedback\core\wercommon\libex\usertokenutility.cpp`
- `0x180052e31`: `GetUserTokenForReport failed. Unable to impersonate logged on user.`
- `0x180052e5a`: `GetUserTokenForReport failed. Unable to obtain a valid user token.`
- `0x180052d42`: `Unable to obtain a valid user token.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserTokenUtility::GetUserTokenForReport(LPCWSTR lpFileName, __int64 a2)
{
  signed int ActiveUserSessions; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rdx
  const char *v9; // rax
  unsigned int *i; // rbx
  unsigned int v11; // edi
  __int64 v12; // rax
  HANDLE FirstFileW; // rdi
  signed int LastError; // eax
  signed int v15; // eax
  const char *v17; // [rsp+28h] [rbp-D8h]
  HANDLE hToken; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v20);
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
      v17);
    goto LABEL_22;
  }
  ActiveUserSessions = UserTokenUtility::QueryActiveUserSessions(v20);
  if ( ActiveUserSessions >= 0 )
  {
    for ( i = (unsigned int *)v20[0]; ; ++i )
    {
      if ( i == (unsigned int *)v20[1] )
      {
        ActiveUserSessions = 0;
        goto LABEL_22;
      }
      v11 = *i;
      v12 = tlx::replace<tlx::file_handle_traits>(&hToken);
      if ( !(unsigned int)QueryUserToken(v11, v12) || (unsigned __int64)hToken + 1 <= 1 )
        break;
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        LastError = GetLastError();
        ActiveUserSessions = LastError;
        if ( LastError > 0 )
          ActiveUserSessions = (unsigned __int16)LastError | 0x80070000;
        v8 = 933;
        v9 = "GetUserTokenForReport failed. Unable to impersonate logged on user.";
        goto LABEL_19;
      }
      FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
      v19 = FirstFileW;
      RevertToSelf();
      if ( FirstFileW != (HANDLE)-1LL )
      {
        tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(&v19);
        tlx::unique_any<tlx::file_handle_traits>::operator=(a2, &hToken);
        ActiveUserSessions = 0;
        goto LABEL_24;
      }
      tlx::unique_any<tlx::file_handle_traits>::reset(&hToken, 0);
      tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(&v19);
    }
    v15 = GetLastError();
    ActiveUserSessions = v15;
    if ( v15 > 0 )
      ActiveUserSessions = (unsigned __int16)v15 | 0x80070000;
    v8 = 925;
    v9 = "GetUserTokenForReport failed. Unable to obtain a valid user token.";
  }
  else
  {
    v8 = 909;
    v9 = "Unable to obtain a valid user token.";
  }
LABEL_19:
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\windows\\feedback\\core\\wercommon\\libex\\usertokenutility.cpp",
    (const char *)(unsigned int)ActiveUserSessions,
    (int)v9,
    v17);
  if ( ActiveUserSessions < 0 )
    goto LABEL_20;
LABEL_22:
  if ( hToken != (HANDLE)-1LL && (char *)hToken + 1 != HANDLE_FLAG_INHERIT )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v7);
LABEL_24:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hToken);
  utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(v20);
  return (unsigned int)ActiveUserSessions;
}

```

## disassembly

```asm
0x180052cc4  mov     [rsp-8+arg_10], rbx
0x180052cc9  mov     [rsp-8+arg_18], rsi
0x180052cce  push    rbp
0x180052ccf  push    rdi
0x180052cd0  push    r14
0x180052cd2  lea     rbp, [rsp-1C0h]
0x180052cda  sub     rsp, 2C0h
0x180052ce1  mov     rax, cs:__security_cookie
0x180052ce8  xor     rax, rsp
0x180052ceb  mov     [rbp+1D0h+var_20], rax
0x180052cf2  mov     r14, rdx
0x180052cf5  mov     rsi, rcx
0x180052cf8  lea     rcx, [rsp+2D0h+var_290]
0x180052cfd  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x180052d02  nop
0x180052d03  mov     [rsp+2D0h+hToken], 0
0x180052d0c  xor     edx, edx; Val
0x180052d0e  mov     r8d, 250h; Size
0x180052d14  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x180052d19  call    memset_0
0x180052d1e  test    rsi, rsi
0x180052d21  jnz     short loc_180052D2D
0x180052d23  mov     ebx, 80070057h
0x180052d28  jmp     loc_180052E80
0x180052d2d  lea     rcx, [rsp+2D0h+var_290]
0x180052d32  call    ?QueryActiveUserSessions@UserTokenUtility@@SAJAEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z; UserTokenUtility::QueryActiveUserSessions(utl::vector<ulong,utl::allocator<ulong>> &)
0x180052d37  mov     ebx, eax
0x180052d39  test    eax, eax
0x180052d3b  jns     short loc_180052D4E
0x180052d3d  mov     edx, 38Dh
0x180052d42  lea     rax, aUnableToObtain; "Unable to obtain a valid user token."
0x180052d49  jmp     loc_180052E61
0x180052d4e  mov     rbx, [rsp+2D0h+var_290]
0x180052d53  cmp     rbx, [rsp+2D0h+var_288]
0x180052d58  jz      loc_180052EA9
0x180052d5e  mov     edi, [rbx]
0x180052d60  lea     rcx, [rsp+2D0h+hToken]
0x180052d65  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180052d6a  mov     rdx, rax
0x180052d6d  mov     ecx, edi
0x180052d6f  call    cs:__imp_QueryUserToken
0x180052d76  nop     dword ptr [rax+rax+00h]
0x180052d7b  test    eax, eax
0x180052d7d  jz      loc_180052E3A
0x180052d83  mov     rcx, [rsp+2D0h+hToken]; hToken
0x180052d88  lea     rax, [rcx+1]
0x180052d8c  cmp     rax, 1
0x180052d90  jbe     loc_180052E3A
0x180052d96  call    cs:__imp_ImpersonateLoggedOnUser
0x180052d9d  nop     dword ptr [rax+rax+00h]
0x180052da2  test    eax, eax
0x180052da4  jz      short loc_180052E11
0x180052da6  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180052dab  mov     rcx, rsi; lpFileName
0x180052dae  call    cs:__imp_FindFirstFileW
0x180052db5  nop     dword ptr [rax+rax+00h]
0x180052dba  mov     rdi, rax
0x180052dbd  mov     [rsp+2D0h+var_298], rax
0x180052dc2  call    cs:__imp_RevertToSelf
0x180052dc9  nop     dword ptr [rax+rax+00h]
0x180052dce  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180052dd2  jnz     short loc_180052DF3
0x180052dd4  xor     edx, edx
0x180052dd6  lea     rcx, [rsp+2D0h+hToken]
0x180052ddb  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180052de0  lea     rcx, [rsp+2D0h+var_298]
0x180052de5  call    ??1?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(void)
0x180052dea  add     rbx, 4
0x180052dee  jmp     loc_180052D53
0x180052df3  lea     rcx, [rsp+2D0h+var_298]
0x180052df8  call    ??1?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(void)
0x180052dfd  lea     rdx, [rsp+2D0h+hToken]
0x180052e02  mov     rcx, r14
0x180052e05  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x180052e0a  xor     ebx, ebx
0x180052e0c  jmp     loc_180052EBF
0x180052e11  call    cs:__imp_GetLastError
0x180052e18  nop     dword ptr [rax+rax+00h]
0x180052e1d  mov     ebx, eax
0x180052e1f  test    eax, eax
0x180052e21  jle     short loc_180052E2C
0x180052e23  movzx   ebx, ax
0x180052e26  or      ebx, 80070000h
0x180052e2c  mov     edx, 3A5h
0x180052e31  lea     rax, aGetusertokenfo_0; "GetUserTokenForReport failed. Unable to"...
0x180052e38  jmp     short loc_180052E61
0x180052e3a  call    cs:__imp_GetLastError
0x180052e41  nop     dword ptr [rax+rax+00h]
0x180052e46  mov     ebx, eax
0x180052e48  test    eax, eax
0x180052e4a  jle     short loc_180052E55
0x180052e4c  movzx   ebx, ax
0x180052e4f  or      ebx, 80070000h
0x180052e55  mov     edx, 39Dh; void *
0x180052e5a  lea     rax, aGetusertokenfo; "GetUserTokenForReport failed. Unable to"...
0x180052e61  mov     rcx, [rbp+1D8h]; this
0x180052e68  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werco"...
0x180052e6f  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x180052e74  mov     r9d, ebx; char *
0x180052e77  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052e7c  test    ebx, ebx
0x180052e7e  jns     short loc_180052EAB
0x180052e80  mov     rcx, [rbp+1D8h]; this
0x180052e87  lea     rax, aNoLoggedInUser; "No logged in users own this report, or "...
0x180052e8e  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x180052e93  mov     r9d, ebx; char *
0x180052e96  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werco"...
0x180052e9d  mov     edx, 3C9h; void *
0x180052ea2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052ea7  jmp     short loc_180052EAB
0x180052ea9  xor     ebx, ebx
0x180052eab  mov     rax, [rsp+2D0h+hToken]
0x180052eb0  inc     rax
0x180052eb3  cmp     rax, 1
0x180052eb7  jbe     short loc_180052EBF
0x180052eb9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180052ebe  nop
0x180052ebf  lea     rcx, [rsp+2D0h+hToken]
0x180052ec4  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180052ec9  nop
0x180052eca  lea     rcx, [rsp+2D0h+var_290]
0x180052ecf  call    ?_Uninit@?$vector@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@V?$allocator@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(void)
0x180052ed4  mov     eax, ebx
0x180052ed6  mov     rcx, [rbp+1D0h+var_20]
0x180052edd  xor     rcx, rsp; StackCookie
0x180052ee0  call    __security_check_cookie
0x180052ee5  lea     r11, [rsp+2D0h+var_10]
0x180052eed  mov     rbx, [r11+30h]
0x180052ef1  mov     rsi, [r11+38h]
0x180052ef5  mov     rsp, r11
0x180052ef8  pop     r14
0x180052efa  pop     rdi
0x180052efb  pop     rbp
0x180052efc  retn
```
