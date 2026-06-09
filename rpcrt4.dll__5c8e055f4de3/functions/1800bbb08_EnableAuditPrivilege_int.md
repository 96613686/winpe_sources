# EnableAuditPrivilege(int)

- ea: `0x1800bbb08`
- end: `0x1800bbbd4`
- name: `?EnableAuditPrivilege@@YAHH@Z`
- size: `204`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800bbbdc`
- `0x1800bbd38`

## callees

- `0x1800bbb08`
- `0x1800ca140`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x1800bbb9d`
- `ntdll!NtAdjustPrivilegesToken` at `0x1800bbb9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbba9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbb58`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbb58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbb42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbb42`

## pseudocode

```c
_BOOL8 __fastcall EnableAuditPrivilege(int a1)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v3; // ebx
  ULONG ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  NewState = 0;
  PreviousState = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
    return 0;
  NewState.Privileges[0].Luid = (LUID)21LL;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = a1 != 0 ? 2 : 0;
  v3 = NtAdjustPrivilegesToken(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
  CloseHandle(TokenHandle);
  return v3 >= 0;
}

```

## disassembly

```asm
0x1800bbb08  mov     [rsp-8+arg_0], rbx
0x1800bbb0d  push    rbp
0x1800bbb0e  mov     rbp, rsp
0x1800bbb11  sub     rsp, 70h
0x1800bbb15  mov     rax, cs:__security_cookie
0x1800bbb1c  xor     rax, rsp
0x1800bbb1f  mov     [rbp+var_10], rax
0x1800bbb23  xorps   xmm0, xmm0
0x1800bbb26  mov     [rbp+TokenHandle], 0
0x1800bbb2e  xorps   xmm1, xmm1
0x1800bbb31  mov     [rbp+var_40], 0
0x1800bbb38  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800bbb3c  mov     ebx, ecx
0x1800bbb3e  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x1800bbb42  call    cs:__imp_GetCurrentThread
0x1800bbb48  mov     edx, 28h ; '('; DesiredAccess
0x1800bbb4d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bbb51  mov     rcx, rax; ThreadHandle
0x1800bbb54  lea     r8d, [rdx-27h]; OpenAsSelf
0x1800bbb58  call    cs:__imp_OpenThreadToken
0x1800bbb5e  test    eax, eax
0x1800bbb60  jz      short loc_1800BBBB8
0x1800bbb62  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800bbb66  lea     r8, [rbp+NewState]; NewState
0x1800bbb6a  neg     ebx
0x1800bbb6c  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 15h
0x1800bbb74  mov     r9d, 10h; BufferLength
0x1800bbb7a  mov     [rbp+NewState.PrivilegeCount], 1
0x1800bbb81  sbb     eax, eax
0x1800bbb83  xor     edx, edx; DisableAllPrivileges
0x1800bbb85  and     eax, 2
0x1800bbb88  mov     [rbp+NewState.Privileges.Attributes], eax
0x1800bbb8b  lea     rax, [rbp+var_40]
0x1800bbb8f  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800bbb94  lea     rax, [rbp+var_20]
0x1800bbb98  mov     [rsp+70h+PreviousState], rax; PreviousState
0x1800bbb9d  call    cs:__imp_NtAdjustPrivilegesToken
0x1800bbba3  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bbba7  mov     ebx, eax
0x1800bbba9  call    cs:__imp_CloseHandle
0x1800bbbaf  xor     eax, eax
0x1800bbbb1  test    ebx, ebx
0x1800bbbb3  setns   al
0x1800bbbb6  jmp     short loc_1800BBBBA
0x1800bbbb8  xor     eax, eax
0x1800bbbba  mov     rcx, [rbp+var_10]
0x1800bbbbe  xor     rcx, rsp; StackCookie
0x1800bbbc1  call    __security_check_cookie
0x1800bbbc6  mov     rbx, [rsp+70h+arg_0]
0x1800bbbce  add     rsp, 70h
0x1800bbbd2  pop     rbp
0x1800bbbd3  retn
```
