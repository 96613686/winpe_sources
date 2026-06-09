# CGroupPolicy::Initialize(void *)

- ea: `0x180023ee0`
- end: `0x180023fd7`
- name: `?Initialize@CGroupPolicy@@QEAAKPEAX@Z`
- size: `247`
- prototype: `unsigned int __fastcall(PGROUP_POLICY_OBJECTW *pGPOList, HANDLE hToken)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180023ee0`
- `0x180024130`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180023f36`
- `KERNEL32!GetLastError` at `0x180023fa0`
- `KERNEL32!GetLastError` at `0x180023f36`
- `KERNEL32!GetLastError` at `0x180023fa0`
- `KERNEL32!CloseHandle` at `0x180023fb8`
- `KERNEL32!CloseHandle` at `0x180023fb8`
- `KERNEL32!GetCurrentThread` at `0x180023f05`
- `KERNEL32!GetCurrentThread` at `0x180023f05`
- `KERNEL32!GetCurrentProcess` at `0x180023f4b`
- `KERNEL32!GetCurrentProcess` at `0x180023f4b`
- `ADVAPI32!OpenProcessToken` at `0x180023f61`
- `ADVAPI32!OpenProcessToken` at `0x180023f61`
- `ADVAPI32!OpenThreadToken` at `0x180023f26`
- `ADVAPI32!OpenThreadToken` at `0x180023f26`
- `USERENV!GetGPOListW` at `0x180023f90`
- `USERENV!GetGPOListW` at `0x180023f90`

## pseudocode

```c
__int64 __fastcall CGroupPolicy::Initialize(PGROUP_POLICY_OBJECTW *pGPOList, HANDLE hToken)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  CGroupPolicy::Shutdown((CGroupPolicy *)pGPOList);
  if ( hToken )
  {
LABEL_6:
    LastError = 0;
    if ( GetGPOListW(hToken, 0, 0, 0, 4u, pGPOList) )
      goto LABEL_8;
    goto LABEL_7;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    goto LABEL_5;
  LastError = GetLastError();
  if ( LastError != 1008 )
    goto LABEL_8;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x2000Cu, &TokenHandle) )
  {
LABEL_5:
    hToken = TokenHandle;
    goto LABEL_6;
  }
LABEL_7:
  LastError = GetLastError();
LABEL_8:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180023ee0  mov     [rsp+arg_0], rbx
0x180023ee5  mov     [rsp+arg_10], rsi
0x180023eea  push    rdi
0x180023eeb  sub     rsp, 30h
0x180023eef  and     [rsp+38h+TokenHandle], 0
0x180023ef5  mov     rdi, rdx
0x180023ef8  mov     rsi, rcx
0x180023efb  call    ?Shutdown@CGroupPolicy@@QEAAKXZ; CGroupPolicy::Shutdown(void)
0x180023f00  test    rdi, rdi
0x180023f03  jnz     short loc_180023F76
0x180023f05  call    cs:__imp_GetCurrentThread
0x180023f0c  nop     dword ptr [rax+rax+00h]
0x180023f11  mov     edi, 2000Ch
0x180023f16  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180023f1b  mov     rcx, rax; ThreadHandle
0x180023f1e  mov     edx, edi; DesiredAccess
0x180023f20  mov     r8d, 1; OpenAsSelf
0x180023f26  call    cs:__imp_OpenThreadToken
0x180023f2d  nop     dword ptr [rax+rax+00h]
0x180023f32  test    eax, eax
0x180023f34  jnz     short loc_180023F71
0x180023f36  call    cs:__imp_GetLastError
0x180023f3d  nop     dword ptr [rax+rax+00h]
0x180023f42  mov     ebx, eax
0x180023f44  cmp     eax, 3F0h
0x180023f49  jnz     short loc_180023FAE
0x180023f4b  call    cs:__imp_GetCurrentProcess
0x180023f52  nop     dword ptr [rax+rax+00h]
0x180023f57  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180023f5c  mov     edx, edi; DesiredAccess
0x180023f5e  mov     rcx, rax; ProcessHandle
0x180023f61  call    cs:__imp_OpenProcessToken
0x180023f68  nop     dword ptr [rax+rax+00h]
0x180023f6d  test    eax, eax
0x180023f6f  jz      short loc_180023FA0
0x180023f71  mov     rdi, [rsp+38h+TokenHandle]
0x180023f76  mov     [rsp+38h+pGPOList], rsi; pGPOList
0x180023f7b  xor     r9d, r9d; lpComputerName
0x180023f7e  xor     r8d, r8d; lpHostName
0x180023f81  mov     [rsp+38h+dwFlags], 4; dwFlags
0x180023f89  xor     edx, edx; lpName
0x180023f8b  mov     rcx, rdi; hToken
0x180023f8e  xor     ebx, ebx
0x180023f90  call    cs:__imp_GetGPOListW
0x180023f97  nop     dword ptr [rax+rax+00h]
0x180023f9c  test    eax, eax
0x180023f9e  jnz     short loc_180023FAE
0x180023fa0  call    cs:__imp_GetLastError
0x180023fa7  nop     dword ptr [rax+rax+00h]
0x180023fac  mov     ebx, eax
0x180023fae  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180023fb3  test    rcx, rcx
0x180023fb6  jz      short loc_180023FC4
0x180023fb8  call    cs:__imp_CloseHandle
0x180023fbf  nop     dword ptr [rax+rax+00h]
0x180023fc4  mov     rsi, [rsp+38h+arg_10]
0x180023fc9  mov     eax, ebx
0x180023fcb  mov     rbx, [rsp+38h+arg_0]
0x180023fd0  add     rsp, 30h
0x180023fd4  pop     rdi
0x180023fd5  retn
```
