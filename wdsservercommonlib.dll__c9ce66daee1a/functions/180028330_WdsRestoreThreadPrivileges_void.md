# WdsRestoreThreadPrivileges(void *)

- ea: `0x180028330`
- end: `0x18002838d`
- name: `?WdsRestoreThreadPrivileges@@YAJPEAX@Z`
- size: `93`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180028330`
- `0x1800288c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028353`
- `KERNEL32!GetLastError` at `0x180028353`
- `ADVAPI32!SetThreadToken` at `0x180028343`
- `ADVAPI32!SetThreadToken` at `0x180028343`

## pseudocode

```c
__int64 __fastcall WdsRestoreThreadPrivileges(HANDLE Token)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  signed int v5; // eax

  v1 = 0;
  if ( Token != (HANDLE)-1LL && !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    v5 = ElValidateWin32_19(LastError, v3, v4, 525);
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)v5;
  }
  return v1;
}

```

## disassembly

```asm
0x180028330  push    rbx
0x180028332  sub     rsp, 20h
0x180028336  xor     ebx, ebx
0x180028338  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002833c  jz      short loc_180028384
0x18002833e  mov     rdx, rcx; Token
0x180028341  xor     ecx, ecx; Thread
0x180028343  call    cs:__imp_SetThreadToken
0x18002834a  nop     dword ptr [rax+rax+00h]
0x18002834f  test    eax, eax
0x180028351  jnz     short loc_180028384
0x180028353  call    cs:__imp_GetLastError
0x18002835a  nop     dword ptr [rax+rax+00h]
0x18002835f  mov     ecx, eax
0x180028361  mov     r9d, 20Dh
0x180028367  call    ElValidateWin32_19
0x18002836c  test    eax, eax
0x18002836e  jle     short loc_180028378
0x180028370  movzx   eax, ax
0x180028373  or      eax, 80070000h
0x180028378  test    eax, eax
0x18002837a  mov     ecx, 80004005h
0x18002837f  cmovns  eax, ecx
0x180028382  mov     ebx, eax
0x180028384  mov     eax, ebx
0x180028386  add     rsp, 20h
0x18002838a  pop     rbx
0x18002838b  retn
```
