# IsCurrentLocalSystem(void)

- ea: `0x1800390e4`
- end: `0x180039174`
- name: `?IsCurrentLocalSystem@@YAJXZ`
- size: `144`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180037344`
- `0x18003a9ec`
- `0x18003bcc8`

## callees

- `0x1800390e4`
- `0x18003cb8c`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800390f3`
- `KERNEL32!GetCurrentThread` at `0x1800390f3`
- `KERNEL32!GetCurrentProcess` at `0x180039121`
- `KERNEL32!GetCurrentProcess` at `0x180039121`
- `KERNEL32!CloseHandle` at `0x180039166`
- `KERNEL32!CloseHandle` at `0x180039166`
- `KERNEL32!GetLastError` at `0x180039112`
- `KERNEL32!GetLastError` at `0x18003913e`
- `KERNEL32!GetLastError` at `0x180039112`
- `KERNEL32!GetLastError` at `0x18003913e`
- `ADVAPI32!OpenThreadToken` at `0x180039108`
- `ADVAPI32!OpenThreadToken` at `0x180039108`
- `ADVAPI32!OpenProcessToken` at `0x180039134`
- `ADVAPI32!OpenProcessToken` at `0x180039134`

## pseudocode

```c
__int64 IsCurrentLocalSystem(void)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v2; // ebx
  HANDLE CurrentProcess; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_7;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError != 1008 )
    goto LABEL_5;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_7:
    v2 = IsLocalSystem(TokenHandle);
    CloseHandle(TokenHandle);
    return v2;
  }
  LastError = GetLastError();
  v2 = LastError;
LABEL_5:
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v2;
}

```

## disassembly

```asm
0x1800390e4  push    rbx
0x1800390e6  sub     rsp, 20h
0x1800390ea  mov     [rsp+28h+TokenHandle], 0
0x1800390f3  call    cs:__imp_GetCurrentThread
0x1800390f9  xor     r8d, r8d; OpenAsSelf
0x1800390fc  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180039101  mov     rcx, rax; ThreadHandle
0x180039104  lea     edx, [r8+8]; DesiredAccess
0x180039108  call    cs:__imp_OpenThreadToken
0x18003910e  test    eax, eax
0x180039110  jnz     short loc_180039155
0x180039112  call    cs:__imp_GetLastError
0x180039118  mov     ebx, eax
0x18003911a  cmp     eax, 3F0h
0x18003911f  jnz     short loc_180039146
0x180039121  call    cs:__imp_GetCurrentProcess
0x180039127  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18003912c  mov     edx, 8; DesiredAccess
0x180039131  mov     rcx, rax; ProcessHandle
0x180039134  call    cs:__imp_OpenProcessToken
0x18003913a  test    eax, eax
0x18003913c  jnz     short loc_180039155
0x18003913e  call    cs:__imp_GetLastError
0x180039144  mov     ebx, eax
0x180039146  test    eax, eax
0x180039148  jle     short loc_18003916C
0x18003914a  movzx   ebx, ax
0x18003914d  or      ebx, 80070000h
0x180039153  jmp     short loc_18003916C
0x180039155  mov     rcx, [rsp+28h+TokenHandle]
0x18003915a  call    IsLocalSystem
0x18003915f  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180039164  mov     ebx, eax
0x180039166  call    cs:__imp_CloseHandle
0x18003916c  mov     eax, ebx
0x18003916e  add     rsp, 20h
0x180039172  pop     rbx
0x180039173  retn
```
