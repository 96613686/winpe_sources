# Windows::Usage::UserPresent(void)

- ea: `0x180094870`
- end: `0x180094a3a`
- name: `?UserPresent@Usage@Windows@@UEBA_NXZ`
- size: `458`
- prototype: `bool __fastcall(Windows::Usage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180008ea8`
- `0x180010e80`
- `0x180010f24`
- `0x1800112d0`
- `0x180094870`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009493c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009493c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800948aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800948aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800948bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800948bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800948db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800948db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800948c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009498c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800948c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009498c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180094921`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180094921`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180094962`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180094962`

## string_xrefs

- `0x1800949cc`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x1800949e9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x1800949fe`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x180094a16`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x180094a28`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::Usage::UserPresent(Windows::Usage *this)
{
  const char *v1; // r9
  DWORD v2; // eax
  DWORD v3; // eax
  const char *v4; // r9
  DWORD v5; // eax
  bool v6; // bl
  unsigned int v7; // r8d
  const char *v8; // r9
  HPOWERNOTIFY RegistrationHandle; // [rsp+20h] [rbp-30h] BYREF
  _QWORD Recipient[2]; // [rsp+28h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-18h] BYREF
  __int64 v13; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v13 = 0;
  hObject = CreateEventW(0, 1, 0, 0);
  if ( !hObject )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      v1);
  RegistrationHandle = 0;
  Recipient[0] = Windows::Usage::UserPresent_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
  Recipient[1] = &hObject;
  v2 = PowerSettingRegisterNotification(&GUID_GLOBAL_USER_PRESENCE, 2u, Recipient, &RegistrationHandle);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xE3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      (const char *)v2,
      (unsigned int)RegistrationHandle);
  v3 = WaitForSingleObject(hObject, 0x7530u);
  if ( v3 == 258 )
  {
    if ( !(_DWORD)v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
        (const char *)0x800705B4LL,
        (int)RegistrationHandle);
  }
  else if ( v3 == -1 )
  {
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xED,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      v4);
  }
  v5 = PowerSettingUnregisterNotification(RegistrationHandle);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xF2,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
      (const char *)(v5 != 0),
      (unsigned int)RegistrationHandle);
  v6 = HIDWORD(v13) == 0;
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v7, v8);
  return v6;
}

```

## disassembly

```asm
0x180094870  mov     [rsp-8+arg_0], rbx
0x180094875  mov     [rsp-8+arg_8], rsi
0x18009487a  mov     [rsp-8+arg_10], rdi
0x18009487f  push    rbp
0x180094880  mov     rbp, rsp
0x180094883  sub     rsp, 50h
0x180094887  mov     rax, cs:__security_cookie
0x18009488e  xor     rax, rsp
0x180094891  mov     [rbp+var_8], rax
0x180094895  xor     eax, eax
0x180094897  mov     [rbp+hObject], rax
0x18009489b  mov     [rbp+var_10], rax
0x18009489f  xor     r9d, r9d; lpName
0x1800948a2  xor     r8d, r8d; bInitialState
0x1800948a5  lea     edx, [rax+1]; bManualReset
0x1800948a8  xor     ecx, ecx; lpEventAttributes
0x1800948aa  call    cs:__imp_CreateEventW
0x1800948b0  mov     rbx, rax
0x1800948b3  mov     rsi, [rbp+hObject]
0x1800948b7  test    rsi, rsi
0x1800948ba  jz      short loc_1800948E1
0x1800948bc  call    cs:__imp_GetLastError
0x1800948c2  mov     edi, eax
0x1800948c4  mov     rcx, rsi; hObject
0x1800948c7  call    cs:__imp_CloseHandle
0x1800948cd  mov     rcx, [rbp+8]; this
0x1800948d1  test    eax, eax
0x1800948d3  jz      loc_1800949DE
0x1800948d9  mov     ecx, edi; dwErrCode
0x1800948db  call    cs:__imp_SetLastError
0x1800948e1  mov     [rbp+hObject], rbx
0x1800948e5  mov     rcx, [rbp+8]; this
0x1800948e9  test    rbx, rbx
0x1800948ec  jz      loc_1800949E9
0x1800948f2  mov     [rbp+RegistrationHandle], 0
0x1800948fa  lea     rax, _Windows__Usage__UserPresent____2____lambda_1____lambda_invoker_cdecl_
0x180094901  mov     [rbp+Recipient], rax
0x180094905  lea     rax, [rbp+hObject]
0x180094909  mov     [rbp+var_20], rax
0x18009490d  lea     r9, [rbp+RegistrationHandle]; RegistrationHandle
0x180094911  lea     r8, [rbp+Recipient]; Recipient
0x180094915  mov     edx, 2; Flags
0x18009491a  lea     rcx, GUID_GLOBAL_USER_PRESENCE; SettingGuid
0x180094921  call    cs:__imp_PowerSettingRegisterNotification
0x180094927  mov     rcx, [rbp+8]; this
0x18009492b  test    eax, eax
0x18009492d  jnz     loc_1800949FB
0x180094933  mov     edx, 7530h; dwMilliseconds
0x180094938  mov     rcx, [rbp+hObject]; hHandle
0x18009493c  call    cs:__imp_WaitForSingleObject
0x180094942  cmp     eax, 102h
0x180094947  jz      short loc_180094950
0x180094949  cmp     eax, 0FFFFFFFFh
0x18009494c  jz      short loc_1800949C8
0x18009494e  jmp     short loc_18009495E
0x180094950  mov     rcx, [rbp+8]; this
0x180094954  cmp     dword ptr [rbp+var_10], 0
0x180094958  jz      loc_180094A10
0x18009495e  mov     rcx, [rbp+RegistrationHandle]; RegistrationHandle
0x180094962  call    cs:__imp_PowerSettingUnregisterNotification
0x180094968  xor     r9d, r9d
0x18009496b  test    eax, eax
0x18009496d  setnz   r9b; char *
0x180094971  mov     rcx, [rbp+8]; this
0x180094975  test    eax, eax
0x180094977  jnz     loc_180094A28
0x18009497d  cmp     dword ptr [rbp+var_10+4], eax
0x180094980  setz    bl
0x180094983  mov     rcx, [rbp+hObject]; hObject
0x180094987  test    rcx, rcx
0x18009498a  jz      short loc_180094996
0x18009498c  call    cs:__imp_CloseHandle
0x180094992  test    eax, eax
0x180094994  jz      short loc_1800949B9
0x180094996  mov     al, bl
0x180094998  mov     rcx, [rbp+var_8]
0x18009499c  xor     rcx, rsp; StackCookie
0x18009499f  call    __security_check_cookie
0x1800949a4  mov     rbx, [rsp+50h+arg_0]
0x1800949a9  mov     rsi, [rsp+50h+arg_8]
0x1800949ae  mov     rdi, [rsp+50h+arg_10]
0x1800949b3  add     rsp, 50h
0x1800949b7  pop     rbp
0x1800949b8  retn
0x1800949b9  mov     rcx, [rbp+8]; this
0x1800949bd  mov     edx, 9D1h; void *
0x1800949c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800949c8  mov     rcx, [rbp+8]; this
0x1800949cc  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800949d3  mov     edx, 0EDh; void *
0x1800949d8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800949de  mov     edx, 9D1h; void *
0x1800949e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800949e9  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800949f0  mov     edx, 0C1h; void *
0x1800949f5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800949fb  mov     r9d, eax; char *
0x1800949fe  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180094a05  mov     edx, 0E3h; void *
0x180094a0a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180094a10  mov     r9d, 800705B4h; char *
0x180094a16  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180094a1d  mov     edx, 0EAh; void *
0x180094a22  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094a28  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180094a2f  mov     edx, 0F2h; void *
0x180094a34  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
