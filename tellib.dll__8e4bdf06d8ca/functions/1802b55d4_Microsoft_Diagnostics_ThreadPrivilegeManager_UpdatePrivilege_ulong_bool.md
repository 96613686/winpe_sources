# Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege(ulong,bool)

- ea: `0x1802b55d4`
- end: `0x1802b570e`
- name: `?UpdatePrivilege@ThreadPrivilegeManager@Diagnostics@Microsoft@@QEAAJK_N@Z`
- size: `314`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, unsigned int, bool)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801b5154`
- `0x1801b9fc0`
- `0x1801fa2e4`
- `0x18020994c`
- `0x1802907cc`
- `0x180299974`
- `0x180306a50`

## callees

- `0x18007fae8`
- `0x180089d90`
- `0x18008bd1c`
- `0x18012de40`
- `0x1802b55d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b56c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b56c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b5641`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b5641`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802b565a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802b565a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1802b560a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1802b560a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1802b56bb`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1802b56bb`

## string_xrefs

- `0x1802b561f`: `onecore\base\telemetry\utc\common\threadprivilegemanager.cpp`
- `0x1802b566f`: `onecore\base\telemetry\utc\common\threadprivilegemanager.cpp`
- `0x1802b56df`: `onecore\base\telemetry\utc\common\threadprivilegemanager.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege(void **TokenHandle)
{
  void *v2; // rcx
  const char *v3; // r9
  __int64 result; // rax
  const char *v5; // r9
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  DWORD LastError; // eax
  unsigned int PreviousState; // [rsp+20h] [rbp-38h]
  _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = *TokenHandle;
  if ( (((unsigned __int64)v2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( !*((_BYTE *)TokenHandle + 8) )
    {
      if ( !ImpersonateSelf(SecurityImpersonation) )
      {
        result = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x2C,
                   (unsigned int)"onecore\\base\\telemetry\\utc\\common\\threadprivilegemanager.cpp",
                   v3);
        goto LABEL_14;
      }
      *((_BYTE *)TokenHandle + 8) = 1;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x20u, 0, TokenHandle) )
    {
      result = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x34,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\common\\threadprivilegemanager.cpp",
                 v7);
      goto LABEL_14;
    }
    v2 = *TokenHandle;
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = (LUID)20LL;
  NewState.Privileges[0].Attributes = 2;
  AdjustTokenPrivileges(v2, 0, &NewState, 0x10u, 0, 0);
  LastError = GetLastError();
  if ( LastError )
    result = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x4D,
               (unsigned int)"onecore\\base\\telemetry\\utc\\common\\threadprivilegemanager.cpp",
               (const char *)LastError,
               PreviousState);
  else
    result = 0;
LABEL_14:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x51,
                               (unsigned int)"onecore\\base\\telemetry\\utc\\common\\threadprivilegemanager.cpp",
                               v5);
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1802b55d4  push    rbx
0x1802b55d6  sub     rsp, 50h
0x1802b55da  mov     rax, cs:__security_cookie
0x1802b55e1  xor     rax, rsp
0x1802b55e4  mov     [rsp+58h+var_10], rax
0x1802b55e9  mov     rbx, rcx
0x1802b55ec  mov     rcx, [rcx]
0x1802b55ef  lea     rax, [rcx+1]
0x1802b55f3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1802b55f9  jnz     loc_1802B5683
0x1802b55ff  cmp     byte ptr [rbx+8], 0
0x1802b5603  jnz     short loc_1802B5637
0x1802b5605  mov     ecx, 2; ImpersonationLevel
0x1802b560a  call    cs:__imp_ImpersonateSelf
0x1802b5611  nop     dword ptr [rax+rax+00h]
0x1802b5616  test    eax, eax
0x1802b5618  jnz     short loc_1802B5633
0x1802b561a  mov     rcx, [rsp+58h]; this
0x1802b561f  lea     r8, aOnecoreBaseTel_30; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b5626  lea     edx, [rax+2Ch]; void *
0x1802b5629  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802b562e  jmp     loc_1802B56FA
0x1802b5633  mov     byte ptr [rbx+8], 1
0x1802b5637  xor     edx, edx
0x1802b5639  mov     rcx, rbx
0x1802b563c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802b5641  call    cs:__imp_GetCurrentThread
0x1802b5648  nop     dword ptr [rax+rax+00h]
0x1802b564d  mov     r9, rbx; TokenHandle
0x1802b5650  xor     r8d, r8d; OpenAsSelf
0x1802b5653  lea     edx, [r8+20h]; DesiredAccess
0x1802b5657  mov     rcx, rax; ThreadHandle
0x1802b565a  call    cs:__imp_OpenThreadToken
0x1802b5661  nop     dword ptr [rax+rax+00h]
0x1802b5666  test    eax, eax
0x1802b5668  jnz     short loc_1802B5680
0x1802b566a  mov     rcx, [rsp+58h]; this
0x1802b566f  lea     r8, aOnecoreBaseTel_30; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b5676  lea     edx, [rax+34h]; void *
0x1802b5679  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802b567e  jmp     short loc_1802B56FA
0x1802b5680  mov     rcx, [rbx]; TokenHandle
0x1802b5683  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1802b568b  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 14h
0x1802b5694  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x1802b569c  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1802b56a5  mov     [rsp+58h+PreviousState], 0; unsigned int
0x1802b56ae  mov     r9d, 10h; BufferLength
0x1802b56b4  lea     r8, [rsp+58h+NewState]; NewState
0x1802b56b9  xor     edx, edx; DisableAllPrivileges
0x1802b56bb  call    cs:__imp_AdjustTokenPrivileges
0x1802b56c2  nop     dword ptr [rax+rax+00h]
0x1802b56c7  call    cs:__imp_GetLastError
0x1802b56ce  nop     dword ptr [rax+rax+00h]
0x1802b56d3  test    eax, eax
0x1802b56d5  jz      short loc_1802B56F2
0x1802b56d7  mov     rcx, [rsp+58h]; this
0x1802b56dc  mov     r9d, eax; char *
0x1802b56df  lea     r8, aOnecoreBaseTel_30; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b56e6  mov     edx, 4Dh ; 'M'; void *
0x1802b56eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802b56f0  jmp     short loc_1802B56FA
0x1802b56f2  xor     eax, eax
0x1802b56f4  jmp     short loc_1802B56FA
0x1802b56f6  mov     eax, [rsp+58h+var_28]
0x1802b56fa  mov     rcx, [rsp+58h+var_10]
0x1802b56ff  xor     rcx, rsp; StackCookie
0x1802b5702  call    __security_check_cookie
0x1802b5707  add     rsp, 50h
0x1802b570b  pop     rbx
0x1802b570c  retn
```
