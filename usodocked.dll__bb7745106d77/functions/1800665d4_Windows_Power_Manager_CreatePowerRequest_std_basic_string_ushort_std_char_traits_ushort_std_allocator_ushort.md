# Windows::Power::Manager::CreatePowerRequest(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800665d4`
- end: `0x18006669e`
- name: `?CreatePowerRequest@Manager@Power@Windows@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180066d80`

## callees

- `0x180023a18`
- `0x1800665d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006664a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006664a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006665d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006665d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066655`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066655`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x18006661c`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x18006661c`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x180066632`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x180066632`

## string_xrefs

- `0x180066675`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\power.cpp`
- `0x18006668c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\power.cpp`

## pseudocode

```c
void __fastcall Windows::Power::Manager::CreatePowerRequest(__int64 a1, HMODULE a2)
{
  bool v3; // cc
  HANDLE v4; // rax
  const char *v5; // r9
  HANDLE v6; // rdi
  const char *v7; // r9
  char *v8; // rbp
  DWORD LastError; // ebx
  _REASON_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( ((*(_QWORD *)(a1 + 8) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v3 = *((_QWORD *)a2 + 3) <= 7u;
    *(_OWORD *)(&Context.Reason.SimpleReasonString + 1) = 0;
    Context.Version = 0;
    Context.Flags = 1;
    if ( !v3 )
      a2 = *(HMODULE *)a2;
    Context.Reason.Detailed.LocalizedReasonModule = a2;
    v4 = PowerCreateRequest(&Context);
    v6 = v4;
    if ( !v4 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\power.cpp",
        v5);
    if ( !PowerSetRequest(v4, PowerRequestExecutionRequired) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\power.cpp",
        v7);
    v8 = *(char **)(a1 + 8);
    if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v8);
      SetLastError(LastError);
    }
    *(_QWORD *)(a1 + 8) = v6;
  }
}

```

## disassembly

```asm
0x1800665d4  push    rbx
0x1800665d6  push    rbp
0x1800665d7  push    rsi
0x1800665d8  push    rdi
0x1800665d9  sub     rsp, 48h
0x1800665dd  mov     rax, [rcx+8]
0x1800665e1  mov     rsi, rcx
0x1800665e4  inc     rax
0x1800665e7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800665ed  jnz     short loc_180066667
0x1800665ef  cmp     qword ptr [rdx+18h], 7
0x1800665f4  xorps   xmm0, xmm0
0x1800665f7  movdqu  xmmword ptr [rsp+68h+Context.Reason+8], xmm0
0x1800665fd  mov     [rsp+68h+Context.Version], 0
0x180066605  mov     [rsp+68h+Context.Flags], 1
0x18006660d  jbe     short loc_180066612
0x18006660f  mov     rdx, [rdx]
0x180066612  lea     rcx, [rsp+68h+Context]; Context
0x180066617  mov     qword ptr [rsp+68h+Context.Reason], rdx
0x18006661c  call    cs:__imp_PowerCreateRequest
0x180066622  mov     rdi, rax
0x180066625  test    rax, rax
0x180066628  jz      short loc_180066687
0x18006662a  mov     edx, 3; RequestType
0x18006662f  mov     rcx, rax; PowerRequest
0x180066632  call    cs:__imp_PowerSetRequest
0x180066638  test    eax, eax
0x18006663a  jz      short loc_180066670
0x18006663c  mov     rbp, [rsi+8]
0x180066640  lea     rax, [rbp-1]
0x180066644  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180066648  ja      short loc_180066663
0x18006664a  call    cs:__imp_GetLastError
0x180066650  mov     rcx, rbp; hObject
0x180066653  mov     ebx, eax
0x180066655  call    cs:__imp_CloseHandle
0x18006665b  mov     ecx, ebx; dwErrCode
0x18006665d  call    cs:__imp_SetLastError
0x180066663  mov     [rsi+8], rdi
0x180066667  add     rsp, 48h
0x18006666b  pop     rdi
0x18006666c  pop     rsi
0x18006666d  pop     rbp
0x18006666e  pop     rbx
0x18006666f  retn
0x180066670  mov     rcx, [rsp+68h]; this
0x180066675  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18006667c  mov     edx, 27h ; '''; void *
0x180066681  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180066687  mov     rcx, [rsp+68h]; this
0x18006668c  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180066693  mov     edx, 26h ; '&'; void *
0x180066698  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
