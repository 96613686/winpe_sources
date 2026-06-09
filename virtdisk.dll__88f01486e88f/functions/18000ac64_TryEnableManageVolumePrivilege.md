# TryEnableManageVolumePrivilege

- ea: `0x18000ac64`
- end: `0x18000ad97`
- name: `TryEnableManageVolumePrivilege`
- size: `307`
- prototype: `DWORD __fastcall(PHANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800025c0`
- `0x180003930`
- `0x180009b90`

## callees

- `0x180005730`
- `0x18000ac64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad62`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000ad52`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000ad52`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000acd7`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000acd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ac94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000aceb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ac94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000aceb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000acaf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ad06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000acaf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ad06`

## pseudocode

```c
DWORD __fastcall TryEnableManageVolumePrivilege(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  DWORD result; // eax
  HANDLE v4; // rax
  HANDLE v5; // rcx
  DWORD ReturnLength; // [rsp+30h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+48h] [rbp-18h] BYREF

  ReturnLength = 0;
  PreviousState = 0;
  NewState = 0;
  CurrentThread = GetCurrentThread();
  result = OpenThreadToken(CurrentThread, 0x28u, 1, TokenHandle);
  if ( !result )
  {
    result = GetLastError();
    if ( result == 1008 )
    {
      result = ImpersonateSelf(SecurityImpersonation);
      if ( result )
      {
        *((_BYTE *)TokenHandle + 8) = 1;
        v4 = GetCurrentThread();
        result = OpenThreadToken(v4, 0x28u, 1, TokenHandle);
      }
    }
  }
  v5 = *TokenHandle;
  if ( *TokenHandle )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    NewState.Privileges[0].Luid = (LUID)28LL;
    ReturnLength = 16;
    result = AdjustTokenPrivileges(v5, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
    if ( result )
    {
      result = GetLastError();
      if ( result != 1300 && PreviousState.PrivilegeCount == 1 )
        *((_BYTE *)TokenHandle + 9) = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ac64  mov     [rsp-8+arg_8], rbx
0x18000ac69  push    rbp
0x18000ac6a  mov     rbp, rsp
0x18000ac6d  sub     rsp, 60h
0x18000ac71  mov     rax, cs:__security_cookie
0x18000ac78  xor     rax, rsp
0x18000ac7b  mov     [rbp+var_8], rax
0x18000ac7f  xorps   xmm0, xmm0
0x18000ac82  mov     [rbp+var_30], 0
0x18000ac89  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm0
0x18000ac8d  mov     rbx, rcx
0x18000ac90  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18000ac94  call    cs:__imp_GetCurrentThread
0x18000ac9b  nop     dword ptr [rax+rax+00h]
0x18000aca0  mov     edx, 28h ; '('; DesiredAccess
0x18000aca5  mov     r9, rbx; TokenHandle
0x18000aca8  mov     rcx, rax; ThreadHandle
0x18000acab  lea     r8d, [rdx-27h]; OpenAsSelf
0x18000acaf  call    cs:__imp_OpenThreadToken
0x18000acb6  nop     dword ptr [rax+rax+00h]
0x18000acbb  test    eax, eax
0x18000acbd  jnz     short loc_18000AD12
0x18000acbf  call    cs:__imp_GetLastError
0x18000acc6  nop     dword ptr [rax+rax+00h]
0x18000accb  cmp     eax, 3F0h
0x18000acd0  jnz     short loc_18000AD12
0x18000acd2  mov     ecx, 2; ImpersonationLevel
0x18000acd7  call    cs:__imp_ImpersonateSelf
0x18000acde  nop     dword ptr [rax+rax+00h]
0x18000ace3  test    eax, eax
0x18000ace5  jz      short loc_18000AD12
0x18000ace7  mov     byte ptr [rbx+8], 1
0x18000aceb  call    cs:__imp_GetCurrentThread
0x18000acf2  nop     dword ptr [rax+rax+00h]
0x18000acf7  mov     edx, 28h ; '('; DesiredAccess
0x18000acfc  mov     r9, rbx; TokenHandle
0x18000acff  mov     rcx, rax; ThreadHandle
0x18000ad02  lea     r8d, [rdx-27h]; OpenAsSelf
0x18000ad06  call    cs:__imp_OpenThreadToken
0x18000ad0d  nop     dword ptr [rax+rax+00h]
0x18000ad12  mov     rcx, [rbx]; TokenHandle
0x18000ad15  test    rcx, rcx
0x18000ad18  jz      short loc_18000AD7F
0x18000ad1a  lea     rax, [rbp+var_30]
0x18000ad1e  mov     [rbp+NewState.PrivilegeCount], 1
0x18000ad25  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18000ad2a  lea     r8, [rbp+NewState]; NewState
0x18000ad2e  lea     rax, [rbp+var_18]
0x18000ad32  mov     [rbp+NewState.Privileges.Attributes], 2
0x18000ad39  mov     r9d, 10h; BufferLength
0x18000ad3f  mov     [rsp+60h+PreviousState], rax; PreviousState
0x18000ad44  xor     edx, edx; DisableAllPrivileges
0x18000ad46  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 1Ch
0x18000ad4e  mov     [rbp+var_30], r9d
0x18000ad52  call    cs:__imp_AdjustTokenPrivileges
0x18000ad59  nop     dword ptr [rax+rax+00h]
0x18000ad5e  test    eax, eax
0x18000ad60  jz      short loc_18000AD7F
0x18000ad62  call    cs:__imp_GetLastError
0x18000ad69  nop     dword ptr [rax+rax+00h]
0x18000ad6e  cmp     eax, 514h
0x18000ad73  jz      short loc_18000AD7F
0x18000ad75  cmp     [rbp+var_18.PrivilegeCount], 1
0x18000ad79  jnz     short loc_18000AD7F
0x18000ad7b  mov     byte ptr [rbx+9], 1
0x18000ad7f  mov     rcx, [rbp+var_8]
0x18000ad83  xor     rcx, rsp; StackCookie
0x18000ad86  call    __security_check_cookie
0x18000ad8b  mov     rbx, [rsp+60h+arg_8]
0x18000ad90  add     rsp, 60h
0x18000ad94  pop     rbp
0x18000ad95  retn
```
