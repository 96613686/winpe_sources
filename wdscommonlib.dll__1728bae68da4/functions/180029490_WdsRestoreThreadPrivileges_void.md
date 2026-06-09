# WdsRestoreThreadPrivileges(void *)

- ea: `0x180029490`
- end: `0x1800294ed`
- name: `?WdsRestoreThreadPrivileges@@YAJPEAX@Z`
- size: `93`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180029490`
- `0x180029a2c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800294b3`
- `KERNEL32!GetLastError` at `0x1800294b3`
- `ADVAPI32!SetThreadToken` at `0x1800294a3`
- `ADVAPI32!SetThreadToken` at `0x1800294a3`

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
0x180029490  push    rbx
0x180029492  sub     rsp, 20h
0x180029496  xor     ebx, ebx
0x180029498  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002949c  jz      short loc_1800294E4
0x18002949e  mov     rdx, rcx; Token
0x1800294a1  xor     ecx, ecx; Thread
0x1800294a3  call    cs:__imp_SetThreadToken
0x1800294aa  nop     dword ptr [rax+rax+00h]
0x1800294af  test    eax, eax
0x1800294b1  jnz     short loc_1800294E4
0x1800294b3  call    cs:__imp_GetLastError
0x1800294ba  nop     dword ptr [rax+rax+00h]
0x1800294bf  mov     ecx, eax
0x1800294c1  mov     r9d, 20Dh
0x1800294c7  call    ElValidateWin32_19
0x1800294cc  test    eax, eax
0x1800294ce  jle     short loc_1800294D8
0x1800294d0  movzx   eax, ax
0x1800294d3  or      eax, 80070000h
0x1800294d8  test    eax, eax
0x1800294da  mov     ecx, 80004005h
0x1800294df  cmovns  eax, ecx
0x1800294e2  mov     ebx, eax
0x1800294e4  mov     eax, ebx
0x1800294e6  add     rsp, 20h
0x1800294ea  pop     rbx
0x1800294eb  retn
```
