# SetCurrentPrivilege(ushort const *,int)

- ea: `0x18003b000`
- end: `0x18003b0a4`
- name: `?SetCurrentPrivilege@@YAJPEBGH@Z`
- size: `164`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800384f4`

## callees

- `0x18003b000`
- `0x18003b188`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18003b016`
- `KERNEL32!GetCurrentThread` at `0x18003b016`
- `KERNEL32!GetCurrentProcess` at `0x18003b044`
- `KERNEL32!GetCurrentProcess` at `0x18003b044`
- `KERNEL32!CloseHandle` at `0x18003b091`
- `KERNEL32!CloseHandle` at `0x18003b091`
- `KERNEL32!GetLastError` at `0x18003b035`
- `KERNEL32!GetLastError` at `0x18003b061`
- `KERNEL32!GetLastError` at `0x18003b035`
- `KERNEL32!GetLastError` at `0x18003b061`
- `ADVAPI32!OpenThreadToken` at `0x18003b02b`
- `ADVAPI32!OpenThreadToken` at `0x18003b02b`
- `ADVAPI32!OpenProcessToken` at `0x18003b057`
- `ADVAPI32!OpenProcessToken` at `0x18003b057`

## pseudocode

```c
__int64 __fastcall SetCurrentPrivilege(const unsigned __int16 *a1)
{
  HANDLE CurrentThread; // rax
  int v3; // r8d
  signed int LastError; // eax
  unsigned int v5; // ebx
  HANDLE CurrentProcess; // rax
  HANDLE TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle) )
    goto LABEL_7;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError != 1008 )
    goto LABEL_5;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
LABEL_7:
    v5 = SetPrivilege(TokenHandle, a1, v3);
    goto LABEL_8;
  }
  LastError = GetLastError();
  v5 = LastError;
LABEL_5:
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_8:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18003b000  mov     [rsp+arg_0], rbx
0x18003b005  push    rdi
0x18003b006  sub     rsp, 20h
0x18003b00a  mov     rdi, rcx
0x18003b00d  mov     [rsp+28h+TokenHandle], 0
0x18003b016  call    cs:__imp_GetCurrentThread
0x18003b01c  xor     r8d, r8d; OpenAsSelf
0x18003b01f  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18003b024  mov     rcx, rax; ThreadHandle
0x18003b027  lea     edx, [r8+28h]; DesiredAccess
0x18003b02b  call    cs:__imp_OpenThreadToken
0x18003b031  test    eax, eax
0x18003b033  jnz     short loc_18003B078
0x18003b035  call    cs:__imp_GetLastError
0x18003b03b  mov     ebx, eax
0x18003b03d  cmp     eax, 3F0h
0x18003b042  jnz     short loc_18003B069
0x18003b044  call    cs:__imp_GetCurrentProcess
0x18003b04a  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18003b04f  mov     edx, 28h ; '('; DesiredAccess
0x18003b054  mov     rcx, rax; ProcessHandle
0x18003b057  call    cs:__imp_OpenProcessToken
0x18003b05d  test    eax, eax
0x18003b05f  jnz     short loc_18003B078
0x18003b061  call    cs:__imp_GetLastError
0x18003b067  mov     ebx, eax
0x18003b069  test    eax, eax
0x18003b06b  jle     short loc_18003B087
0x18003b06d  movzx   ebx, ax
0x18003b070  or      ebx, 80070000h
0x18003b076  jmp     short loc_18003B087
0x18003b078  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18003b07d  mov     rdx, rdi; unsigned __int16 *
0x18003b080  call    ?SetPrivilege@@YAJPEAXPEBGH@Z; SetPrivilege(void *,ushort const *,int)
0x18003b085  mov     ebx, eax
0x18003b087  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18003b08c  test    rcx, rcx
0x18003b08f  jz      short loc_18003B097
0x18003b091  call    cs:__imp_CloseHandle
0x18003b097  mov     eax, ebx
0x18003b099  mov     rbx, [rsp+28h+arg_0]
0x18003b09e  add     rsp, 20h
0x18003b0a2  pop     rdi
0x18003b0a3  retn
```
