# GetProcessLowBoxStatus

- ea: `0x18006bb4c`
- end: `0x18006bbf2`
- name: `GetProcessLowBoxStatus`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004290`

## callees

- `0x18006bb4c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18006bbb2`
- `ntdll!NtQueryInformationToken` at `0x18006bbb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bbcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bbcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bbdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bbdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006bb77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006bb77`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006bb8a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006bb8a`

## pseudocode

```c
__int64 __fastcall GetProcessLowBoxStatus(_DWORD *a1)
{
  HANDLE CurrentProcess; // rax
  int LastError; // ebx
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  *a1 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
    if ( LastError >= 0 && TokenInformation )
      *a1 = 1;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18006bb4c  mov     rax, rsp
0x18006bb4f  mov     [rax+20h], rbx
0x18006bb53  push    rdi
0x18006bb54  sub     rsp, 30h
0x18006bb58  mov     rdi, rcx
0x18006bb5b  mov     qword ptr [rax+18h], 0
0x18006bb63  mov     dword ptr [rax+10h], 0
0x18006bb6a  mov     dword ptr [rax+8], 0
0x18006bb71  mov     dword ptr [rcx], 0
0x18006bb77  call    cs:__imp_GetCurrentProcess
0x18006bb7d  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18006bb82  mov     edx, 8; DesiredAccess
0x18006bb87  mov     rcx, rax; ProcessHandle
0x18006bb8a  call    cs:__imp_OpenProcessToken
0x18006bb90  test    eax, eax
0x18006bb92  jz      short loc_18006BBCD
0x18006bb94  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18006bb99  lea     rax, [rsp+38h+arg_8]
0x18006bb9e  mov     r9d, 4; TokenInformationLength
0x18006bba4  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18006bba9  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18006bbae  lea     edx, [r9+19h]; TokenInformationClass
0x18006bbb2  call    cs:__imp_NtQueryInformationToken
0x18006bbb8  mov     ebx, eax
0x18006bbba  test    eax, eax
0x18006bbbc  js      short loc_18006BBD5
0x18006bbbe  cmp     [rsp+38h+TokenInformation], 0
0x18006bbc3  jz      short loc_18006BBD5
0x18006bbc5  mov     dword ptr [rdi], 1
0x18006bbcb  jmp     short loc_18006BBD5
0x18006bbcd  call    cs:__imp_GetLastError
0x18006bbd3  mov     ebx, eax
0x18006bbd5  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18006bbda  test    rcx, rcx
0x18006bbdd  jz      short loc_18006BBE5
0x18006bbdf  call    cs:__imp_CloseHandle
0x18006bbe5  mov     eax, ebx
0x18006bbe7  mov     rbx, [rsp+38h+arg_18]
0x18006bbec  add     rsp, 30h
0x18006bbf0  pop     rdi
0x18006bbf1  retn
```
