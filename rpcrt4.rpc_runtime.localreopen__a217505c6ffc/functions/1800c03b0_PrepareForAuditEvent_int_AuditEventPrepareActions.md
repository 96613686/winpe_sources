# PrepareForAuditEvent(int,_AuditEventPrepareActions *)

- ea: `0x1800c03b0`
- end: `0x1800c051e`
- name: `?PrepareForAuditEvent@@YAHHPEAW4_AuditEventPrepareActions@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(int, enum _AuditEventPrepareActions *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c0524`
- `0x1800c07b8`

## callees

- `0x1800c0134`
- `0x1800c0254`
- `0x1800c03b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0432`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c04a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c04d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0432`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c04a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c04d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c045f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c045f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c041e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c041e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c0402`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c0402`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c0477`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c0477`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c04be`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c04f9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c04be`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c04f9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800c0496`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800c0496`

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
0x1800c03b0  mov     [rsp-18h+arg_0], rbx
0x1800c03b5  push    rbp
0x1800c03b6  push    rsi
0x1800c03b7  push    r14
0x1800c03b9  mov     rbp, rsp
0x1800c03bc  sub     rsp, 30h
0x1800c03c0  mov     r14, rdx
0x1800c03c3  mov     [rbp+TokenHandle], 0
0x1800c03cb  lea     rdx, [rbp+arg_10]; int *
0x1800c03cf  mov     [rbp+ExistingTokenHandle], 0
0x1800c03d7  mov     [rbp+arg_10], 0
0x1800c03de  call    ?IsAuditPrivilegeEnabled@@YAHHPEAH@Z; IsAuditPrivilegeEnabled(int,int *)
0x1800c03e3  test    eax, eax
0x1800c03e5  jz      loc_1800C0505
0x1800c03eb  cmp     [rbp+arg_10], 0
0x1800c03ef  jz      short loc_1800C0402
0x1800c03f1  mov     dword ptr [r14], 0
0x1800c03f8  mov     eax, 1
0x1800c03fd  jmp     loc_1800C0507
0x1800c0402  call    cs:__imp_GetCurrentThread
0x1800c0409  nop     dword ptr [rax+rax+00h]
0x1800c040e  mov     edx, 28h ; '('; DesiredAccess
0x1800c0413  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c0417  mov     rcx, rax; ThreadHandle
0x1800c041a  lea     r8d, [rdx-27h]; OpenAsSelf
0x1800c041e  call    cs:__imp_OpenThreadToken
0x1800c0425  nop     dword ptr [rax+rax+00h]
0x1800c042a  test    eax, eax
0x1800c042c  jz      short loc_1800C0448
0x1800c042e  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c0432  call    cs:__imp_CloseHandle
0x1800c0439  nop     dword ptr [rax+rax+00h]
0x1800c043e  xor     ebx, ebx
0x1800c0440  lea     esi, [rbx+1]
0x1800c0443  jmp     loc_1800C04E3
0x1800c0448  call    cs:__imp_GetLastError
0x1800c044f  nop     dword ptr [rax+rax+00h]
0x1800c0454  cmp     eax, 3F0h
0x1800c0459  jnz     loc_1800C0505
0x1800c045f  call    cs:__imp_GetCurrentProcess
0x1800c0466  nop     dword ptr [rax+rax+00h]
0x1800c046b  lea     r8, [rbp+ExistingTokenHandle]; TokenHandle
0x1800c046f  mov     edx, 2Ah ; '*'; DesiredAccess
0x1800c0474  mov     rcx, rax; ProcessHandle
0x1800c0477  call    cs:__imp_OpenProcessToken
0x1800c047e  nop     dword ptr [rax+rax+00h]
0x1800c0483  test    eax, eax
0x1800c0485  jz      short loc_1800C0505
0x1800c0487  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x1800c048b  lea     r8, [rbp+TokenHandle]; DuplicateTokenHandle
0x1800c048f  mov     esi, 2
0x1800c0494  mov     edx, esi; ImpersonationLevel
0x1800c0496  call    cs:__imp_DuplicateToken
0x1800c049d  nop     dword ptr [rax+rax+00h]
0x1800c04a2  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x1800c04a6  mov     ebx, eax
0x1800c04a8  call    cs:__imp_CloseHandle
0x1800c04af  nop     dword ptr [rax+rax+00h]
0x1800c04b4  test    ebx, ebx
0x1800c04b6  jz      short loc_1800C0505
0x1800c04b8  mov     rdx, [rbp+TokenHandle]; Token
0x1800c04bc  xor     ecx, ecx; Thread
0x1800c04be  call    cs:__imp_SetThreadToken
0x1800c04c5  nop     dword ptr [rax+rax+00h]
0x1800c04ca  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c04ce  mov     ebx, eax
0x1800c04d0  call    cs:__imp_CloseHandle
0x1800c04d7  nop     dword ptr [rax+rax+00h]
0x1800c04dc  test    ebx, ebx
0x1800c04de  jz      short loc_1800C0505
0x1800c04e0  lea     ebx, [rsi-1]
0x1800c04e3  mov     ecx, 1; int
0x1800c04e8  call    ?EnableAuditPrivilege@@YAHH@Z; EnableAuditPrivilege(int)
0x1800c04ed  test    eax, eax
0x1800c04ef  jnz     short loc_1800C0516
0x1800c04f1  test    ebx, ebx
0x1800c04f3  jz      short loc_1800C0505
0x1800c04f5  xor     edx, edx; Token
0x1800c04f7  xor     ecx, ecx; Thread
0x1800c04f9  call    cs:__imp_SetThreadToken
0x1800c0500  nop     dword ptr [rax+rax+00h]
0x1800c0505  xor     eax, eax
0x1800c0507  mov     rbx, [rsp+30h+arg_0]
0x1800c050c  add     rsp, 30h
0x1800c0510  pop     r14
0x1800c0512  pop     rsi
0x1800c0513  pop     rbp
0x1800c0514  retn
0x1800c0516  mov     [r14], esi
0x1800c0519  jmp     loc_1800C03F8
```
