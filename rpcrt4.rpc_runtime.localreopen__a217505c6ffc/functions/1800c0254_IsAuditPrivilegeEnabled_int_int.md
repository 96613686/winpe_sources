# IsAuditPrivilegeEnabled(int,int *)

- ea: `0x1800c0254`
- end: `0x1800c03a8`
- name: `?IsAuditPrivilegeEnabled@@YAHHPEAH@Z`
- size: `340`
- prototype: `__int64 __fastcall(int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800c03b0`

## callees

- `0x1800c0254`
- `0x1800ceda0`

## import_xrefs

- `ntdll!NtPrivilegeCheck` at `0x1800c0341`
- `ntdll!NtPrivilegeCheck` at `0x1800c0341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c02e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c02e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0353`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0353`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c02f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c02f9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c02d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c02d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c02ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c02ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c030e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c030e`

## pseudocode

```c
__int64 __fastcall IsAuditPrivilegeEnabled(int a1, int *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  NTSTATUS v7; // ebx
  unsigned __int8 Result[8]; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  TokenHandle = 0;
  Result[0] = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( a1 )
  {
    if ( SIDCache.SubAuthority[0] )
    {
      *a2 = SIDCache.SubAuthority[0] != 1;
      return 1;
    }
LABEL_7:
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      return 0;
    goto LABEL_8;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    goto LABEL_7;
  }
LABEL_8:
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = (LUID)21LL;
  RequiredPrivileges.Privilege[0].Attributes = 2;
  v7 = NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
  CloseHandle(TokenHandle);
  if ( v7 >= 0 )
  {
    if ( a1 )
      SIDCache.SubAuthority[0] = (Result[0] != 0) + 1;
    *a2 = Result[0];
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800c0254  mov     [rsp-18h+arg_0], rbx
0x1800c0259  mov     [rsp-18h+arg_10], rsi
0x1800c025e  push    rbp
0x1800c025f  push    rdi
0x1800c0260  push    r15
0x1800c0262  mov     rbp, rsp
0x1800c0265  sub     rsp, 50h
0x1800c0269  mov     rax, cs:__security_cookie
0x1800c0270  xor     rax, rsp
0x1800c0273  mov     [rbp+var_8], rax
0x1800c0277  xor     eax, eax
0x1800c0279  mov     [rbp+TokenHandle], 0
0x1800c0281  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x1800c0284  xorps   xmm0, xmm0
0x1800c0287  mov     [rbp+Result], al
0x1800c028a  mov     rdi, rdx
0x1800c028d  mov     esi, ecx
0x1800c028f  lea     ebx, [rax+8]
0x1800c0292  lea     r15d, [rax+1]
0x1800c0296  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x1800c029a  test    ecx, ecx
0x1800c029c  jz      short loc_1800C02BA
0x1800c029e  mov     edx, cs:?SIDCache@@3PEAVSID_CACHE@@EA.SubAuthority; SID_CACHE * SIDCache ...
0x1800c02a4  test    edx, edx
0x1800c02a6  jz      short loc_1800C02F9
0x1800c02a8  xor     ecx, ecx
0x1800c02aa  cmp     edx, r15d
0x1800c02ad  setnz   cl
0x1800c02b0  mov     [rdi], ecx
0x1800c02b2  mov     eax, r15d
0x1800c02b5  jmp     loc_1800C0386
0x1800c02ba  call    cs:__imp_GetCurrentThread
0x1800c02c1  nop     dword ptr [rax+rax+00h]
0x1800c02c6  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c02ca  mov     r8d, r15d; OpenAsSelf
0x1800c02cd  mov     rcx, rax; ThreadHandle
0x1800c02d0  mov     edx, ebx; DesiredAccess
0x1800c02d2  call    cs:__imp_OpenThreadToken
0x1800c02d9  nop     dword ptr [rax+rax+00h]
0x1800c02de  test    eax, eax
0x1800c02e0  jnz     short loc_1800C031E
0x1800c02e2  call    cs:__imp_GetLastError
0x1800c02e9  nop     dword ptr [rax+rax+00h]
0x1800c02ee  cmp     eax, 3F0h
0x1800c02f3  jnz     loc_1800C0384
0x1800c02f9  call    cs:__imp_GetCurrentProcess
0x1800c0300  nop     dword ptr [rax+rax+00h]
0x1800c0305  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800c0309  mov     edx, ebx; DesiredAccess
0x1800c030b  mov     rcx, rax; ProcessHandle
0x1800c030e  call    cs:__imp_OpenProcessToken
0x1800c0315  nop     dword ptr [rax+rax+00h]
0x1800c031a  test    eax, eax
0x1800c031c  jz      short loc_1800C0384
0x1800c031e  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800c0322  lea     r8, [rbp+Result]; Result
0x1800c0326  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1800c032a  mov     [rbp+RequiredPrivileges.PrivilegeCount], r15d
0x1800c032e  mov     [rbp+RequiredPrivileges.Control], r15d
0x1800c0332  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 15h
0x1800c033a  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x1800c0341  call    cs:__imp_NtPrivilegeCheck
0x1800c0348  nop     dword ptr [rax+rax+00h]
0x1800c034d  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c0351  mov     ebx, eax
0x1800c0353  call    cs:__imp_CloseHandle
0x1800c035a  nop     dword ptr [rax+rax+00h]
0x1800c035f  test    ebx, ebx
0x1800c0361  js      short loc_1800C0384
0x1800c0363  test    esi, esi
0x1800c0365  jz      short loc_1800C0379
0x1800c0367  mov     al, [rbp+Result]
0x1800c036a  neg     al
0x1800c036c  sbb     ecx, ecx
0x1800c036e  neg     ecx
0x1800c0370  add     ecx, r15d
0x1800c0373  mov     cs:?SIDCache@@3PEAVSID_CACHE@@EA.SubAuthority, ecx; SID_CACHE * SIDCache ...
0x1800c0379  movzx   eax, [rbp+Result]
0x1800c037d  mov     [rdi], eax
0x1800c037f  jmp     loc_1800C02B2
0x1800c0384  xor     eax, eax
0x1800c0386  mov     rcx, [rbp+var_8]
0x1800c038a  xor     rcx, rsp; StackCookie
0x1800c038d  call    __security_check_cookie
0x1800c0392  lea     r11, [rsp+50h+var_s0]
0x1800c0397  mov     rbx, [r11+20h]
0x1800c039b  mov     rsi, [r11+30h]
0x1800c039f  mov     rsp, r11
0x1800c03a2  pop     r15
0x1800c03a4  pop     rdi
0x1800c03a5  pop     rbp
0x1800c03a6  retn
```
