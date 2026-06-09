# OnRestart(void)

- ea: `0x18000741c`
- end: `0x180007506`
- name: `?OnRestart@@YA_NXZ`
- size: `234`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006520`

## callees

- `0x18000741c`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180007455`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180007455`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007442`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007442`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b2`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000749b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000749b`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x1800074da`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x1800074da`

## pseudocode

```c
bool OnRestart(void)
{
  HANDLE CurrentProcess; // rax
  BOOL v1; // ebx
  bool v2; // zf
  DWORD v3; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = (void *)-1LL;
  NewState = 0;
  CurrentProcess = GetCurrentProcess();
  v1 = OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle);
  if ( v1 )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = (LUID)19LL;
    NewState.Privileges[0].Attributes = 2;
    v1 = AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0);
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  v2 = !v1;
  if ( v1 )
  {
    v3 = InitiateShutdownW(0, 0, 0, 4u, 0x80020004);
    if ( v3 && v3 != 1115 )
      v1 = 0;
    v2 = !v1;
  }
  return !v2;
}

```

## disassembly

```asm
0x18000741c  push    rbx
0x18000741e  sub     rsp, 50h
0x180007422  mov     rax, cs:__security_cookie
0x180007429  xor     rax, rsp
0x18000742c  mov     [rsp+58h+var_10], rax
0x180007431  xorps   xmm0, xmm0
0x180007434  mov     [rsp+58h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000743d  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x180007442  call    cs:__imp_GetCurrentProcess
0x180007448  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18000744d  mov     edx, 2000000h; DesiredAccess
0x180007452  mov     rcx, rax; ProcessHandle
0x180007455  call    cs:__imp_OpenProcessToken
0x18000745b  mov     ebx, eax
0x18000745d  test    eax, eax
0x18000745f  jz      short loc_1800074A3
0x180007461  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180007466  lea     r8, [rsp+58h+NewState]; NewState
0x18000746b  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x180007474  xor     r9d, r9d; BufferLength
0x180007477  xor     edx, edx; DisableAllPrivileges
0x180007479  mov     [rsp+58h+PreviousState], 0; PreviousState
0x180007482  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x18000748a  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 13h
0x180007493  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x18000749b  call    cs:__imp_AdjustTokenPrivileges
0x1800074a1  mov     ebx, eax
0x1800074a3  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800074a8  lea     rax, [rcx-1]
0x1800074ac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800074b0  ja      short loc_1800074C1
0x1800074b2  call    cs:__imp_CloseHandle
0x1800074b8  mov     [rsp+58h+TokenHandle], 0
0x1800074c1  test    ebx, ebx
0x1800074c3  jz      short loc_1800074F0
0x1800074c5  mov     r9d, 4; dwShutdownFlags
0x1800074cb  mov     dword ptr [rsp+58h+PreviousState], 80020004h; dwReason
0x1800074d3  xor     r8d, r8d; dwGracePeriod
0x1800074d6  xor     edx, edx; lpMessage
0x1800074d8  xor     ecx, ecx; lpMachineName
0x1800074da  call    cs:__imp_InitiateShutdownW
0x1800074e0  test    eax, eax
0x1800074e2  jz      short loc_1800074EE
0x1800074e4  xor     ecx, ecx
0x1800074e6  cmp     eax, 45Bh
0x1800074eb  cmovnz  ebx, ecx
0x1800074ee  test    ebx, ebx
0x1800074f0  setnz   al
0x1800074f3  mov     rcx, [rsp+58h+var_10]
0x1800074f8  xor     rcx, rsp; StackCookie
0x1800074fb  call    __security_check_cookie
0x180007500  add     rsp, 50h
0x180007504  pop     rbx
0x180007505  retn
```
