# EnableAuditPrivilege(int)

- ea: `0x1800c0134`
- end: `0x1800c0219`
- name: `?EnableAuditPrivilege@@YAHH@Z`
- size: `229`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800c0220`
- `0x1800c03b0`

## callees

- `0x1800c0134`
- `0x1800ceda0`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x1800c01d5`
- `ntdll!NtAdjustPrivilegesToken` at `0x1800c01d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c01e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c01e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c018a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c018a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c016e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c016e`

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
0x1800c0134  mov     [rsp-8+arg_0], rbx
0x1800c0139  push    rbp
0x1800c013a  mov     rbp, rsp
0x1800c013d  sub     rsp, 70h
0x1800c0141  mov     rax, cs:__security_cookie
0x1800c0148  xor     rax, rsp
0x1800c014b  mov     [rbp+var_10], rax
0x1800c014f  xorps   xmm0, xmm0
0x1800c0152  mov     [rbp+TokenHandle], 0
0x1800c015a  xorps   xmm1, xmm1
0x1800c015d  mov     [rbp+var_40], 0
0x1800c0164  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800c0168  mov     ebx, ecx
0x1800c016a  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x1800c016e  call    cs:__imp_GetCurrentThread
0x1800c0175  nop     dword ptr [rax+rax+00h]
0x1800c017a  mov     edx, 28h ; '('; DesiredAccess
0x1800c017f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c0183  mov     rcx, rax; ThreadHandle
0x1800c0186  lea     r8d, [rdx-27h]; OpenAsSelf
0x1800c018a  call    cs:__imp_OpenThreadToken
0x1800c0191  nop     dword ptr [rax+rax+00h]
0x1800c0196  test    eax, eax
0x1800c0198  jz      short loc_1800C01FC
0x1800c019a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800c019e  lea     r8, [rbp+NewState]; NewState
0x1800c01a2  neg     ebx
0x1800c01a4  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 15h
0x1800c01ac  mov     r9d, 10h; BufferLength
0x1800c01b2  mov     [rbp+NewState.PrivilegeCount], 1
0x1800c01b9  sbb     eax, eax
0x1800c01bb  xor     edx, edx; DisableAllPrivileges
0x1800c01bd  and     eax, 2
0x1800c01c0  mov     [rbp+NewState.Privileges.Attributes], eax
0x1800c01c3  lea     rax, [rbp+var_40]
0x1800c01c7  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800c01cc  lea     rax, [rbp+var_20]
0x1800c01d0  mov     [rsp+70h+PreviousState], rax; PreviousState
0x1800c01d5  call    cs:__imp_NtAdjustPrivilegesToken
0x1800c01dc  nop     dword ptr [rax+rax+00h]
0x1800c01e1  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c01e5  mov     ebx, eax
0x1800c01e7  call    cs:__imp_CloseHandle
0x1800c01ee  nop     dword ptr [rax+rax+00h]
0x1800c01f3  xor     eax, eax
0x1800c01f5  test    ebx, ebx
0x1800c01f7  setns   al
0x1800c01fa  jmp     short loc_1800C01FE
0x1800c01fc  xor     eax, eax
0x1800c01fe  mov     rcx, [rbp+var_10]
0x1800c0202  xor     rcx, rsp; StackCookie
0x1800c0205  call    __security_check_cookie
0x1800c020a  mov     rbx, [rsp+70h+arg_0]
0x1800c0212  add     rsp, 70h
0x1800c0216  pop     rbp
0x1800c0217  retn
```
