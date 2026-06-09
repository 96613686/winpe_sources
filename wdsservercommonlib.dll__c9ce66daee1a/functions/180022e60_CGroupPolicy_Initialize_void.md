# CGroupPolicy::Initialize(void *)

- ea: `0x180022e60`
- end: `0x180022f57`
- name: `?Initialize@CGroupPolicy@@QEAAKPEAX@Z`
- size: `247`
- prototype: `unsigned int __fastcall(PGROUP_POLICY_OBJECTW *pGPOList, HANDLE hToken)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180022e60`
- `0x1800230a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180022eb6`
- `KERNEL32!GetLastError` at `0x180022f20`
- `KERNEL32!GetLastError` at `0x180022eb6`
- `KERNEL32!GetLastError` at `0x180022f20`
- `KERNEL32!CloseHandle` at `0x180022f38`
- `KERNEL32!CloseHandle` at `0x180022f38`
- `KERNEL32!GetCurrentThread` at `0x180022e85`
- `KERNEL32!GetCurrentThread` at `0x180022e85`
- `KERNEL32!GetCurrentProcess` at `0x180022ecb`
- `KERNEL32!GetCurrentProcess` at `0x180022ecb`
- `ADVAPI32!OpenThreadToken` at `0x180022ea6`
- `ADVAPI32!OpenThreadToken` at `0x180022ea6`
- `ADVAPI32!OpenProcessToken` at `0x180022ee1`
- `ADVAPI32!OpenProcessToken` at `0x180022ee1`
- `USERENV!GetGPOListW` at `0x180022f10`
- `USERENV!GetGPOListW` at `0x180022f10`

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
0x180022e60  mov     [rsp+arg_0], rbx
0x180022e65  mov     [rsp+arg_10], rsi
0x180022e6a  push    rdi
0x180022e6b  sub     rsp, 30h
0x180022e6f  and     [rsp+38h+TokenHandle], 0
0x180022e75  mov     rdi, rdx
0x180022e78  mov     rsi, rcx
0x180022e7b  call    ?Shutdown@CGroupPolicy@@QEAAKXZ; CGroupPolicy::Shutdown(void)
0x180022e80  test    rdi, rdi
0x180022e83  jnz     short loc_180022EF6
0x180022e85  call    cs:__imp_GetCurrentThread
0x180022e8c  nop     dword ptr [rax+rax+00h]
0x180022e91  mov     edi, 2000Ch
0x180022e96  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180022e9b  mov     rcx, rax; ThreadHandle
0x180022e9e  mov     edx, edi; DesiredAccess
0x180022ea0  mov     r8d, 1; OpenAsSelf
0x180022ea6  call    cs:__imp_OpenThreadToken
0x180022ead  nop     dword ptr [rax+rax+00h]
0x180022eb2  test    eax, eax
0x180022eb4  jnz     short loc_180022EF1
0x180022eb6  call    cs:__imp_GetLastError
0x180022ebd  nop     dword ptr [rax+rax+00h]
0x180022ec2  mov     ebx, eax
0x180022ec4  cmp     eax, 3F0h
0x180022ec9  jnz     short loc_180022F2E
0x180022ecb  call    cs:__imp_GetCurrentProcess
0x180022ed2  nop     dword ptr [rax+rax+00h]
0x180022ed7  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180022edc  mov     edx, edi; DesiredAccess
0x180022ede  mov     rcx, rax; ProcessHandle
0x180022ee1  call    cs:__imp_OpenProcessToken
0x180022ee8  nop     dword ptr [rax+rax+00h]
0x180022eed  test    eax, eax
0x180022eef  jz      short loc_180022F20
0x180022ef1  mov     rdi, [rsp+38h+TokenHandle]
0x180022ef6  mov     [rsp+38h+pGPOList], rsi; pGPOList
0x180022efb  xor     r9d, r9d; lpComputerName
0x180022efe  xor     r8d, r8d; lpHostName
0x180022f01  mov     [rsp+38h+dwFlags], 4; dwFlags
0x180022f09  xor     edx, edx; lpName
0x180022f0b  mov     rcx, rdi; hToken
0x180022f0e  xor     ebx, ebx
0x180022f10  call    cs:__imp_GetGPOListW
0x180022f17  nop     dword ptr [rax+rax+00h]
0x180022f1c  test    eax, eax
0x180022f1e  jnz     short loc_180022F2E
0x180022f20  call    cs:__imp_GetLastError
0x180022f27  nop     dword ptr [rax+rax+00h]
0x180022f2c  mov     ebx, eax
0x180022f2e  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180022f33  test    rcx, rcx
0x180022f36  jz      short loc_180022F44
0x180022f38  call    cs:__imp_CloseHandle
0x180022f3f  nop     dword ptr [rax+rax+00h]
0x180022f44  mov     rsi, [rsp+38h+arg_10]
0x180022f49  mov     eax, ebx
0x180022f4b  mov     rbx, [rsp+38h+arg_0]
0x180022f50  add     rsp, 30h
0x180022f54  pop     rdi
0x180022f55  retn
```
