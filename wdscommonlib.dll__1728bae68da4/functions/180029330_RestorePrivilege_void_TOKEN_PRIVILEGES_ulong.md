# RestorePrivilege(void *,_TOKEN_PRIVILEGES *,ulong)

- ea: `0x180029330`
- end: `0x180029386`
- name: `?RestorePrivilege@@YAKPEAXPEAU_TOKEN_PRIVILEGES@@K@Z`
- size: `86`
- prototype: `unsigned int(void *, struct _TOKEN_PRIVILEGES *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180029330`
- `0x180029a2c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002935a`
- `KERNEL32!GetLastError` at `0x18002935a`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18002934a`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18002934a`

## pseudocode

```c
__int64 __fastcall RestorePrivilege(void *a1, struct _TOKEN_PRIVILEGES *a2, DWORD a3)
{
  unsigned int v3; // ebx
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // eax

  v3 = 0;
  if ( !AdjustTokenPrivileges(a1, 0, a2, a3, 0, 0) )
  {
    LastError = GetLastError();
    v7 = ElValidateWin32_19(LastError, v5, v6, 134);
    if ( !v7 )
      return 31;
    return v7;
  }
  return v3;
}

```

## disassembly

```asm
0x180029330  push    rbx
0x180029332  sub     rsp, 30h
0x180029336  xor     ebx, ebx
0x180029338  mov     r9d, r8d; BufferLength
0x18002933b  mov     r8, rdx; NewState
0x18002933e  mov     [rsp+38h+ReturnLength], rbx; ReturnLength
0x180029343  xor     edx, edx; DisableAllPrivileges
0x180029345  mov     [rsp+38h+PreviousState], rbx; PreviousState
0x18002934a  call    cs:__imp_AdjustTokenPrivileges
0x180029351  nop     dword ptr [rax+rax+00h]
0x180029356  test    eax, eax
0x180029358  jnz     short loc_18002937D
0x18002935a  call    cs:__imp_GetLastError
0x180029361  nop     dword ptr [rax+rax+00h]
0x180029366  mov     ecx, eax
0x180029368  mov     r9d, 86h
0x18002936e  call    ElValidateWin32_19
0x180029373  lea     ecx, [rbx+1Fh]
0x180029376  test    eax, eax
0x180029378  cmovz   eax, ecx
0x18002937b  mov     ebx, eax
0x18002937d  mov     eax, ebx
0x18002937f  add     rsp, 30h
0x180029383  pop     rbx
0x180029384  retn
```
