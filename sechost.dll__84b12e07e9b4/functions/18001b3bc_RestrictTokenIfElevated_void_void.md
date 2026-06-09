# RestrictTokenIfElevated(void *,void * *)

- ea: `0x18001b3bc`
- end: `0x18001b55c`
- name: `?RestrictTokenIfElevated@@YAJPEAXPEAPEAX@Z`
- size: `416`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b2b4`

## callees

- `0x18001b3bc`
- `0x18001b564`
- `0x18001b5dc`
- `0x18004a1fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b51c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b51c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b417`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001b43f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001b43f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001b451`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001b451`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001b512`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001b512`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001b4ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001b4ab`

## string_xrefs

- `0x18001b531`: `Call: CreateRestrictedToken()`
- `0x18001b4ca`: `Call: GetTokenInformation() (TokenElevation)`
- `0x18001b470`: `Call: OpenProcessToken()`
- `0x18001b436`: `Call: OpenThreadToken()`

## pseudocode

```c
__int64 __fastcall RestrictTokenIfElevated(void *a1, void **a2)
{
  ULONG IsImpersonating; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  void *TokenHandle; // [rsp+50h] [rbp-10h] BYREF
  void *NewTokenHandle; // [rsp+58h] [rbp-8h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+10h] BYREF
  int TokenInformation_4; // [rsp+74h] [rbp+14h]
  DWORD ReturnLength; // [rsp+80h] [rbp+20h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+88h] [rbp+28h] BYREF

  TokenInformation_4 = HIDWORD(a1);
  TokenInformation = 0;
  ReturnLength = 0;
  NewTokenHandle = 0;
  TokenHandle = 0;
  IsImpersonating = NtCurrentTeb()->IsImpersonating;
  ExistingTokenHandle = 0;
  if ( IsImpersonating )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xAu, 0, &TokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = L"Call: OpenThreadToken()";
      goto LABEL_10;
    }
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      v7 = L"Call: OpenProcessToken()";
      goto LABEL_10;
    }
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &ExistingTokenHandle,
    TokenHandle);
  if ( GetTokenInformation(ExistingTokenHandle, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( TokenInformation )
    {
      if ( !CreateRestrictedToken(ExistingTokenHandle, 4u, 0, 0, 0, 0, 0, 0, &NewTokenHandle) )
      {
        v11 = GetLastError();
        v6 = v11;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        v7 = L"Call: CreateRestrictedToken()";
        goto LABEL_10;
      }
      *a2 = NewTokenHandle;
    }
    v6 = 0;
    goto LABEL_22;
  }
  v10 = GetLastError();
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  v7 = L"Call: GetTokenInformation() (TokenElevation)";
LABEL_10:
  IsolationApi::TelemetryHelper::LogIsolatedProcessTokenCreationFailure(v6, v7);
LABEL_22:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18001b3bc  mov     [rsp-8+arg_8], rbx
0x18001b3c1  mov     [rsp-8+TokenInformation], rcx
0x18001b3c6  push    rbp
0x18001b3c7  mov     rbp, rsp
0x18001b3ca  sub     rsp, 60h
0x18001b3ce  mov     dword ptr [rbp+TokenInformation], 0
0x18001b3d5  mov     rbx, rdx
0x18001b3d8  mov     [rbp+arg_10], 0
0x18001b3df  mov     [rbp+var_8], 0
0x18001b3e7  mov     [rbp+TokenHandle], 0
0x18001b3ef  mov     eax, gs:179Ch
0x18001b3f7  mov     [rbp+ExistingTokenHandle], 0
0x18001b3ff  test    eax, eax
0x18001b401  jz      short loc_18001B43F
0x18001b403  call    cs:__imp_GetCurrentThread
0x18001b409  xor     r8d, r8d; OpenAsSelf
0x18001b40c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001b410  mov     rcx, rax; ThreadHandle
0x18001b413  lea     edx, [r8+0Ah]; DesiredAccess
0x18001b417  call    cs:__imp_OpenThreadToken
0x18001b41d  test    eax, eax
0x18001b41f  jnz     short loc_18001B483
0x18001b421  call    cs:__imp_GetLastError
0x18001b427  mov     ebx, eax
0x18001b429  test    eax, eax
0x18001b42b  jle     short loc_18001B436
0x18001b42d  movzx   ebx, ax
0x18001b430  or      ebx, 80070000h
0x18001b436  lea     rdx, aCallOpenthread; "Call: OpenThreadToken()"
0x18001b43d  jmp     short loc_18001B477
0x18001b43f  call    cs:__imp_GetCurrentProcess
0x18001b445  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001b449  mov     edx, 0Ah; DesiredAccess
0x18001b44e  mov     rcx, rax; ProcessHandle
0x18001b451  call    cs:__imp_OpenProcessToken
0x18001b457  test    eax, eax
0x18001b459  jnz     short loc_18001B483
0x18001b45b  call    cs:__imp_GetLastError
0x18001b461  mov     ebx, eax
0x18001b463  test    eax, eax
0x18001b465  jle     short loc_18001B470
0x18001b467  movzx   ebx, ax
0x18001b46a  or      ebx, 80070000h
0x18001b470  lea     rdx, aCallOpenproces; "Call: OpenProcessToken()"
0x18001b477  mov     ecx, ebx; int
0x18001b479  call    ?LogIsolatedProcessTokenCreationFailure@TelemetryHelper@IsolationApi@@SAXJPEBG@Z; IsolationApi::TelemetryHelper::LogIsolatedProcessTokenCreationFailure(long,ushort const *)
0x18001b47e  jmp     loc_18001B546
0x18001b483  mov     rdx, [rbp+TokenHandle]
0x18001b487  lea     rcx, [rbp+ExistingTokenHandle]
0x18001b48b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001b490  mov     rcx, [rbp+ExistingTokenHandle]; TokenHandle
0x18001b494  lea     rax, [rbp+arg_10]
0x18001b498  mov     r9d, 4; TokenInformationLength
0x18001b49e  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18001b4a3  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001b4a7  lea     edx, [r9+10h]; TokenInformationClass
0x18001b4ab  call    cs:__imp_GetTokenInformation
0x18001b4b1  test    eax, eax
0x18001b4b3  jnz     short loc_18001B4D3
0x18001b4b5  call    cs:__imp_GetLastError
0x18001b4bb  mov     ebx, eax
0x18001b4bd  test    eax, eax
0x18001b4bf  jle     short loc_18001B4CA
0x18001b4c1  movzx   ebx, ax
0x18001b4c4  or      ebx, 80070000h
0x18001b4ca  lea     rdx, aCallGettokenin; "Call: GetTokenInformation() (TokenEleva"...
0x18001b4d1  jmp     short loc_18001B477
0x18001b4d3  cmp     dword ptr [rbp+TokenInformation], 0
0x18001b4d7  jz      short loc_18001B544
0x18001b4d9  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x18001b4dd  lea     rax, [rbp+var_8]
0x18001b4e1  mov     [rsp+60h+NewTokenHandle], rax; NewTokenHandle
0x18001b4e6  xor     r9d, r9d; SidsToDisable
0x18001b4e9  mov     [rsp+60h+SidsToRestrict], 0; SidsToRestrict
0x18001b4f2  xor     r8d, r8d; DisableSidCount
0x18001b4f5  mov     [rsp+60h+RestrictedSidCount], 0; RestrictedSidCount
0x18001b4fd  mov     [rsp+60h+PrivilegesToDelete], 0; PrivilegesToDelete
0x18001b506  lea     edx, [r9+4]; Flags
0x18001b50a  mov     dword ptr [rsp+60h+ReturnLength], 0; DeletePrivilegeCount
0x18001b512  call    cs:__imp_CreateRestrictedToken
0x18001b518  test    eax, eax
0x18001b51a  jnz     short loc_18001B53D
0x18001b51c  call    cs:__imp_GetLastError
0x18001b522  mov     ebx, eax
0x18001b524  test    eax, eax
0x18001b526  jle     short loc_18001B531
0x18001b528  movzx   ebx, ax
0x18001b52b  or      ebx, 80070000h
0x18001b531  lea     rdx, aCallCreaterest; "Call: CreateRestrictedToken()"
0x18001b538  jmp     loc_18001B477
0x18001b53d  mov     rax, [rbp+var_8]
0x18001b541  mov     [rbx], rax
0x18001b544  xor     ebx, ebx
0x18001b546  lea     rcx, [rbp+ExistingTokenHandle]
0x18001b54a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001b54f  mov     eax, ebx
0x18001b551  mov     rbx, [rsp+60h+arg_8]
0x18001b556  add     rsp, 60h
0x18001b55a  pop     rbp
0x18001b55b  retn
```
