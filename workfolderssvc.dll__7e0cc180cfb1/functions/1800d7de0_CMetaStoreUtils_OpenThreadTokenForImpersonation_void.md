# CMetaStoreUtils::OpenThreadTokenForImpersonation(void * *)

- ea: `0x1800d7de0`
- end: `0x1800d7e57`
- name: `?OpenThreadTokenForImpersonation@CMetaStoreUtils@@SAJPEAPEAX@Z`
- size: `119`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800e8120`
- `0x1800e93ec`

## callees

- `0x1800d7de0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800d7def`
- `KERNEL32!GetCurrentThread` at `0x1800d7e18`
- `KERNEL32!GetCurrentThread` at `0x1800d7def`
- `KERNEL32!GetCurrentThread` at `0x1800d7e18`
- `KERNEL32!GetLastError` at `0x1800d7e0b`
- `KERNEL32!GetLastError` at `0x1800d7e35`
- `KERNEL32!GetLastError` at `0x1800d7e0b`
- `KERNEL32!GetLastError` at `0x1800d7e35`
- `ADVAPI32!OpenThreadToken` at `0x1800d7e01`
- `ADVAPI32!OpenThreadToken` at `0x1800d7e2b`
- `ADVAPI32!OpenThreadToken` at `0x1800d7e01`
- `ADVAPI32!OpenThreadToken` at `0x1800d7e2b`

## pseudocode

```c
__int64 __fastcall CMetaStoreUtils::OpenThreadTokenForImpersonation(PHANDLE TokenHandle)
{
  signed int LastError; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v4; // rax

  LastError = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 0, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 5 )
    {
      v4 = GetCurrentThread();
      if ( OpenThreadToken(v4, 4u, 1, TokenHandle) )
        return (unsigned __int16)LastError | 0x80070000;
      LastError = GetLastError();
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800d7de0  mov     [rsp+arg_0], rbx
0x1800d7de5  push    rdi
0x1800d7de6  sub     rsp, 20h
0x1800d7dea  mov     rdi, rcx
0x1800d7ded  xor     ebx, ebx
0x1800d7def  call    cs:__imp_GetCurrentThread
0x1800d7df5  mov     r9, rdi; TokenHandle
0x1800d7df8  lea     edx, [rbx+4]; DesiredAccess
0x1800d7dfb  mov     rcx, rax; ThreadHandle
0x1800d7dfe  xor     r8d, r8d; OpenAsSelf
0x1800d7e01  call    cs:__imp_OpenThreadToken
0x1800d7e07  test    eax, eax
0x1800d7e09  jnz     short loc_1800D7E4A
0x1800d7e0b  call    cs:__imp_GetLastError
0x1800d7e11  mov     ebx, eax
0x1800d7e13  cmp     eax, 5
0x1800d7e16  jnz     short loc_1800D7E3D
0x1800d7e18  call    cs:__imp_GetCurrentThread
0x1800d7e1e  mov     r9, rdi; TokenHandle
0x1800d7e21  lea     edx, [rbx-1]; DesiredAccess
0x1800d7e24  mov     rcx, rax; ThreadHandle
0x1800d7e27  lea     r8d, [rbx-4]; OpenAsSelf
0x1800d7e2b  call    cs:__imp_OpenThreadToken
0x1800d7e31  test    eax, eax
0x1800d7e33  jnz     short loc_1800D7E41
0x1800d7e35  call    cs:__imp_GetLastError
0x1800d7e3b  mov     ebx, eax
0x1800d7e3d  test    ebx, ebx
0x1800d7e3f  jle     short loc_1800D7E4A
0x1800d7e41  movzx   ebx, bx
0x1800d7e44  or      ebx, 80070000h
0x1800d7e4a  mov     eax, ebx
0x1800d7e4c  mov     rbx, [rsp+28h+arg_0]
0x1800d7e51  add     rsp, 20h
0x1800d7e55  pop     rdi
0x1800d7e56  retn
```
