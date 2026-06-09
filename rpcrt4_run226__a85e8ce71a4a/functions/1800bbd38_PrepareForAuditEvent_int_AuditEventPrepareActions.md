# PrepareForAuditEvent(int,_AuditEventPrepareActions *)

- ea: `0x1800bbd38`
- end: `0x1800bbe5c`
- name: `?PrepareForAuditEvent@@YAHHPEAW4_AuditEventPrepareActions@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(int, enum _AuditEventPrepareActions *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bbe64`
- `0x1800bc0d0`

## callees

- `0x1800bbb08`
- `0x1800bbc0c`
- `0x1800bbd38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbdbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbdbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbdae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbdff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbe1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbdae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbdff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbe1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bbdc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bbdc8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbda0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbda0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbd8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbd8a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bbdda`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bbdda`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800bbe0f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800bbe3e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800bbe0f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800bbe3e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800bbdf3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800bbdf3`

## pseudocode

```c
__int64 __fastcall PrepareForAuditEvent(int a1, enum _AuditEventPrepareActions *a2)
{
  HANDLE CurrentThread; // rax
  int v5; // ebx
  int v6; // esi
  HANDLE CurrentProcess; // rax
  BOOL v8; // ebx
  BOOL v9; // ebx
  HANDLE ExistingTokenHandle; // [rsp+20h] [rbp-10h] BYREF
  int v11; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  TokenHandle = 0;
  ExistingTokenHandle = 0;
  v11 = 0;
  if ( !(unsigned int)IsAuditPrivilegeEnabled(a1, &v11) )
    return 0;
  if ( v11 )
  {
    *(_DWORD *)a2 = 0;
    return 1;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    CloseHandle(TokenHandle);
    v5 = 0;
    v6 = 1;
  }
  else
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x2Au, &ExistingTokenHandle) )
      return 0;
    v6 = 2;
    v8 = DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &TokenHandle);
    CloseHandle(ExistingTokenHandle);
    if ( !v8 )
      return 0;
    v9 = SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
    if ( !v9 )
      return 0;
    v5 = 1;
  }
  if ( (unsigned int)EnableAuditPrivilege(1) )
  {
    *(_DWORD *)a2 = v6;
    return 1;
  }
  if ( v5 )
    SetThreadToken(0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800bbd38  mov     [rsp-18h+arg_0], rbx
0x1800bbd3d  push    rbp
0x1800bbd3e  push    rsi
0x1800bbd3f  push    r14
0x1800bbd41  mov     rbp, rsp
0x1800bbd44  sub     rsp, 30h
0x1800bbd48  mov     r14, rdx
0x1800bbd4b  mov     [rbp+TokenHandle], 0
0x1800bbd53  lea     rdx, [rbp+arg_10]; int *
0x1800bbd57  mov     [rbp+ExistingTokenHandle], 0
0x1800bbd5f  mov     [rbp+arg_10], 0
0x1800bbd66  call    ?IsAuditPrivilegeEnabled@@YAHHPEAH@Z; IsAuditPrivilegeEnabled(int,int *)
0x1800bbd6b  test    eax, eax
0x1800bbd6d  jz      loc_1800BBE44
0x1800bbd73  cmp     [rbp+arg_10], 0
0x1800bbd77  jz      short loc_1800BBD8A
0x1800bbd79  mov     dword ptr [r14], 0
0x1800bbd80  mov     eax, 1
0x1800bbd85  jmp     loc_1800BBE46
0x1800bbd8a  call    cs:__imp_GetCurrentThread
0x1800bbd90  mov     edx, 28h ; '('; DesiredAccess
0x1800bbd95  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bbd99  mov     rcx, rax; ThreadHandle
0x1800bbd9c  lea     r8d, [rdx-27h]; OpenAsSelf
0x1800bbda0  call    cs:__imp_OpenThreadToken
0x1800bbda6  test    eax, eax
0x1800bbda8  jz      short loc_1800BBDBB
0x1800bbdaa  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bbdae  call    cs:__imp_CloseHandle
0x1800bbdb4  xor     ebx, ebx
0x1800bbdb6  lea     esi, [rbx+1]
0x1800bbdb9  jmp     short loc_1800BBE28
0x1800bbdbb  call    cs:__imp_GetLastError
0x1800bbdc1  cmp     eax, 3F0h
0x1800bbdc6  jnz     short loc_1800BBE44
0x1800bbdc8  call    cs:__imp_GetCurrentProcess
0x1800bbdce  lea     r8, [rbp+ExistingTokenHandle]; TokenHandle
0x1800bbdd2  mov     edx, 2Ah ; '*'; DesiredAccess
0x1800bbdd7  mov     rcx, rax; ProcessHandle
0x1800bbdda  call    cs:__imp_OpenProcessToken
0x1800bbde0  test    eax, eax
0x1800bbde2  jz      short loc_1800BBE44
0x1800bbde4  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x1800bbde8  lea     r8, [rbp+TokenHandle]; DuplicateTokenHandle
0x1800bbdec  mov     esi, 2
0x1800bbdf1  mov     edx, esi; ImpersonationLevel
0x1800bbdf3  call    cs:__imp_DuplicateToken
0x1800bbdf9  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x1800bbdfd  mov     ebx, eax
0x1800bbdff  call    cs:__imp_CloseHandle
0x1800bbe05  test    ebx, ebx
0x1800bbe07  jz      short loc_1800BBE44
0x1800bbe09  mov     rdx, [rbp+TokenHandle]; Token
0x1800bbe0d  xor     ecx, ecx; Thread
0x1800bbe0f  call    cs:__imp_SetThreadToken
0x1800bbe15  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bbe19  mov     ebx, eax
0x1800bbe1b  call    cs:__imp_CloseHandle
0x1800bbe21  test    ebx, ebx
0x1800bbe23  jz      short loc_1800BBE44
0x1800bbe25  lea     ebx, [rsi-1]
0x1800bbe28  mov     ecx, 1; int
0x1800bbe2d  call    ?EnableAuditPrivilege@@YAHH@Z; EnableAuditPrivilege(int)
0x1800bbe32  test    eax, eax
0x1800bbe34  jnz     short loc_1800BBE54
0x1800bbe36  test    ebx, ebx
0x1800bbe38  jz      short loc_1800BBE44
0x1800bbe3a  xor     edx, edx; Token
0x1800bbe3c  xor     ecx, ecx; Thread
0x1800bbe3e  call    cs:__imp_SetThreadToken
0x1800bbe44  xor     eax, eax
0x1800bbe46  mov     rbx, [rsp+30h+arg_0]
0x1800bbe4b  add     rsp, 30h
0x1800bbe4f  pop     r14
0x1800bbe51  pop     rsi
0x1800bbe52  pop     rbp
0x1800bbe53  retn
0x1800bbe54  mov     [r14], esi
0x1800bbe57  jmp     loc_1800BBD80
```
