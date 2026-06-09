# Windows::Usage::UserPresent(void)

- ea: `0x180057380`
- end: `0x180057517`
- name: `?UserPresent@Usage@Windows@@UEBA_NXZ`
- size: `407`
- prototype: `bool __fastcall(Windows::Usage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x180019e48`
- `0x1800209fc`
- `0x180023a18`
- `0x180025cd0`
- `0x180056f30`
- `0x180057380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180057433`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180057433`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800573a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800573a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800573b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800573b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800573d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800573d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800573be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800573be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057488`
- `POWRPROF!PowerSettingRegisterNotification` at `0x180057418`
- `POWRPROF!PowerSettingRegisterNotification` at `0x180057418`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18005745e`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18005745e`

## string_xrefs

- `0x1800574c6`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x1800574db`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x1800574f3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x180057505`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::Usage::UserPresent(Windows::Usage *this)
{
  const char *v1; // r9
  DWORD v2; // eax
  DWORD v3; // eax
  unsigned int v4; // r8d
  const char *v5; // r9
  DWORD v6; // eax
  bool v7; // bl
  unsigned int v8; // r8d
  const char *v9; // r9
  HANDLE hObject; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+28h] [rbp-20h]
  _QWORD Recipient[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  HPOWERNOTIFY RegistrationHandle; // [rsp+78h] [rbp+30h] BYREF

  v12 = 0;
  hObject = CreateEventW(0, 1, 0, 0);
  if ( !hObject )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      v1);
  RegistrationHandle = 0;
  Recipient[0] = lambda_39fef23757c4ab2fdddfbc266ad8ec65_::_lambda_invoker_cdecl_;
  Recipient[1] = &hObject;
  v2 = PowerSettingRegisterNotification(&GUID_GLOBAL_USER_PRESENCE, 2u, Recipient, &RegistrationHandle);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      (const char *)v2,
      (unsigned int)hObject);
  v3 = WaitForSingleObject(hObject, 0x7530u);
  if ( v3 == 258 )
  {
    if ( !(_DWORD)v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
        (const char *)0x800705B4LL,
        (int)hObject);
  }
  else if ( v3 == -1 )
  {
    wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x97, v4, v5);
  }
  v6 = PowerSettingUnregisterNotification(RegistrationHandle);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      (const char *)(v6 != 0),
      (unsigned int)hObject);
  v7 = HIDWORD(v12) == 0;
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
  return v7;
}

```

## disassembly

```asm
0x180057380  push    rbp
0x180057382  push    rbx
0x180057383  push    rsi
0x180057384  push    rdi
0x180057385  mov     rbp, rsp
0x180057388  sub     rsp, 48h
0x18005738c  xor     eax, eax
0x18005738e  mov     [rbp+hObject], rax
0x180057392  mov     [rbp+var_20], rax
0x180057396  xor     r9d, r9d; lpName
0x180057399  xor     r8d, r8d; bInitialState
0x18005739c  lea     edx, [rax+1]; bManualReset
0x18005739f  xor     ecx, ecx; lpEventAttributes
0x1800573a1  call    cs:__imp_CreateEventW
0x1800573a7  mov     rbx, rax
0x1800573aa  mov     rsi, [rbp+hObject]
0x1800573ae  test    rsi, rsi
0x1800573b1  jz      short loc_1800573D8
0x1800573b3  call    cs:__imp_GetLastError
0x1800573b9  mov     edi, eax
0x1800573bb  mov     rcx, rsi; hObject
0x1800573be  call    cs:__imp_CloseHandle
0x1800573c4  mov     rcx, [rbp+20h]; this
0x1800573c8  test    eax, eax
0x1800573ca  jz      loc_1800574BB
0x1800573d0  mov     ecx, edi; dwErrCode
0x1800573d2  call    cs:__imp_SetLastError
0x1800573d8  mov     [rbp+hObject], rbx
0x1800573dc  mov     rcx, [rbp+20h]; this
0x1800573e0  test    rbx, rbx
0x1800573e3  jz      loc_1800574C6
0x1800573e9  mov     [rbp+RegistrationHandle], 0
0x1800573f1  lea     rax, _lambda_39fef23757c4ab2fdddfbc266ad8ec65____lambda_invoker_cdecl_
0x1800573f8  mov     [rbp+Recipient], rax
0x1800573fc  lea     rax, [rbp+hObject]
0x180057400  mov     [rbp+var_10], rax
0x180057404  lea     r9, [rbp+RegistrationHandle]; RegistrationHandle
0x180057408  lea     r8, [rbp+Recipient]; Recipient
0x18005740c  mov     edx, 2; Flags
0x180057411  lea     rcx, GUID_GLOBAL_USER_PRESENCE; SettingGuid
0x180057418  call    cs:__imp_PowerSettingRegisterNotification
0x18005741e  mov     rcx, [rbp+20h]; this
0x180057422  test    eax, eax
0x180057424  jnz     loc_1800574D8
0x18005742a  mov     edx, 7530h; dwMilliseconds
0x18005742f  mov     rcx, [rbp+hObject]; hHandle
0x180057433  call    cs:__imp_WaitForSingleObject
0x180057439  cmp     eax, 102h
0x18005743e  jz      short loc_180057447
0x180057440  cmp     eax, 0FFFFFFFFh
0x180057443  jz      short loc_1800574AC
0x180057445  jmp     short loc_18005745A
0x180057447  cmp     dword ptr [rbp+var_20], 0
0x18005744b  setz    al
0x18005744e  mov     rcx, [rbp+20h]; this
0x180057452  test    al, al
0x180057454  jnz     loc_1800574ED
0x18005745a  mov     rcx, [rbp+RegistrationHandle]; RegistrationHandle
0x18005745e  call    cs:__imp_PowerSettingUnregisterNotification
0x180057464  xor     r9d, r9d
0x180057467  test    eax, eax
0x180057469  setnz   r9b; char *
0x18005746d  mov     rcx, [rbp+20h]; this
0x180057471  test    eax, eax
0x180057473  jnz     loc_180057505
0x180057479  cmp     dword ptr [rbp+var_20+4], eax
0x18005747c  setz    bl
0x18005747f  mov     rcx, [rbp+hObject]; hObject
0x180057483  test    rcx, rcx
0x180057486  jz      short loc_180057492
0x180057488  call    cs:__imp_CloseHandle
0x18005748e  test    eax, eax
0x180057490  jz      short loc_18005749D
0x180057492  mov     al, bl
0x180057494  add     rsp, 48h
0x180057498  pop     rdi
0x180057499  pop     rsi
0x18005749a  pop     rbx
0x18005749b  pop     rbp
0x18005749c  retn
0x18005749d  mov     rcx, [rbp+20h]; this
0x1800574a1  mov     edx, 0A0Bh; void *
0x1800574a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800574ac  mov     rcx, [rbp+20h]; this
0x1800574b0  mov     edx, 97h; void *
0x1800574b5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800574bb  mov     edx, 0A0Bh; void *
0x1800574c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800574c6  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800574cd  mov     edx, 6Bh ; 'k'; void *
0x1800574d2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800574d8  mov     r9d, eax; char *
0x1800574db  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800574e2  mov     edx, 8Dh; void *
0x1800574e7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800574ed  mov     r9d, 800705B4h; char *
0x1800574f3  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800574fa  mov     edx, 94h; void *
0x1800574ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057505  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005750c  mov     edx, 9Ch; void *
0x180057511  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
