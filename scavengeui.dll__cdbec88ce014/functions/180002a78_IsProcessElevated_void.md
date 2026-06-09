# IsProcessElevated(void)

- ea: `0x180002a78`
- end: `0x180002acb`
- name: `?IsProcessElevated@@YAHXZ`
- size: `83`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180002870`
- `0x180002930`

## callees

- `0x180002a78`
- `0x18000388c`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180002a8d`
- `KERNEL32!GetCurrentProcess` at `0x180002a8d`
- `ADVAPI32!OpenProcessToken` at `0x180002a9e`
- `ADVAPI32!OpenProcessToken` at `0x180002a9e`

## pseudocode

```c
__int64 IsProcessElevated(void)
{
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    LUAIsElevatedToken(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180002a78  push    rbx
0x180002a7a  sub     rsp, 20h
0x180002a7e  xor     ebx, ebx
0x180002a80  mov     [rsp+28h+arg_0], ebx
0x180002a84  mov     [rsp+28h+arg_8], ebx
0x180002a88  mov     [rsp+28h+TokenHandle], rbx
0x180002a8d  call    cs:__imp_GetCurrentProcess
0x180002a93  mov     rcx, rax; ProcessHandle
0x180002a96  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180002a9b  lea     edx, [rbx+8]; DesiredAccess
0x180002a9e  call    cs:__imp_OpenProcessToken
0x180002aa4  test    eax, eax
0x180002aa6  jz      short loc_180002AC3
0x180002aa8  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180002aad  lea     r8, [rsp+28h+arg_8]
0x180002ab2  lea     rdx, [rsp+28h+arg_0]
0x180002ab7  call    LUAIsElevatedToken
0x180002abc  test    eax, eax
0x180002abe  cmovns  ebx, [rsp+28h+arg_0]
0x180002ac3  mov     eax, ebx
0x180002ac5  add     rsp, 20h
0x180002ac9  pop     rbx
0x180002aca  retn
```
