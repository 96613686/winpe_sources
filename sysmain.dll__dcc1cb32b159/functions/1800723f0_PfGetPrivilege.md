# PfGetPrivilege

- ea: `0x1800723f0`
- end: `0x180072456`
- name: `PfGetPrivilege`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002341c`
- `0x180090134`

## callees

- `0x18006168c`
- `0x1800723f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007241e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007241e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072448`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180072414`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180072414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800723ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800723ff`

## pseudocode

```c
__int64 PfGetPrivilege()
{
  HANDLE CurrentThread; // rax
  __int64 v1; // rdx
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20u, 0, &TokenHandle) && (unsigned int)PfSvSetPrivilege(TokenHandle, v1, 14) )
    LastError = 0;
  else
    LastError = GetLastError();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800723f0  push    rbx
0x1800723f2  sub     rsp, 20h
0x1800723f6  mov     [rsp+28h+TokenHandle], 0
0x1800723ff  call    cs:__imp_GetCurrentThread
0x180072405  xor     r8d, r8d; OpenAsSelf
0x180072408  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18007240d  mov     rcx, rax; ThreadHandle
0x180072410  lea     edx, [r8+20h]; DesiredAccess
0x180072414  call    cs:__imp_OpenThreadToken
0x18007241a  test    eax, eax
0x18007241c  jnz     short loc_180072428
0x18007241e  call    cs:__imp_GetLastError
0x180072424  mov     ebx, eax
0x180072426  jmp     short loc_18007243E
0x180072428  mov     rcx, [rsp+28h+TokenHandle]
0x18007242d  mov     r8d, 0Eh
0x180072433  call    PfSvSetPrivilege
0x180072438  test    eax, eax
0x18007243a  jz      short loc_18007241E
0x18007243c  xor     ebx, ebx
0x18007243e  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180072443  test    rcx, rcx
0x180072446  jz      short loc_18007244E
0x180072448  call    cs:__imp_CloseHandle
0x18007244e  mov     eax, ebx
0x180072450  add     rsp, 20h
0x180072454  pop     rbx
0x180072455  retn
```
