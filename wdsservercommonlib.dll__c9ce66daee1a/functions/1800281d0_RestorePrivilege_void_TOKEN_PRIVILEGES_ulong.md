# RestorePrivilege(void *,_TOKEN_PRIVILEGES *,ulong)

- ea: `0x1800281d0`
- end: `0x180028226`
- name: `?RestorePrivilege@@YAKPEAXPEAU_TOKEN_PRIVILEGES@@K@Z`
- size: `86`
- prototype: `unsigned int(void *, struct _TOKEN_PRIVILEGES *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800281d0`
- `0x1800288c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800281fa`
- `KERNEL32!GetLastError` at `0x1800281fa`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800281ea`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800281ea`

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
0x1800281d0  push    rbx
0x1800281d2  sub     rsp, 30h
0x1800281d6  xor     ebx, ebx
0x1800281d8  mov     r9d, r8d; BufferLength
0x1800281db  mov     r8, rdx; NewState
0x1800281de  mov     [rsp+38h+ReturnLength], rbx; ReturnLength
0x1800281e3  xor     edx, edx; DisableAllPrivileges
0x1800281e5  mov     [rsp+38h+PreviousState], rbx; PreviousState
0x1800281ea  call    cs:__imp_AdjustTokenPrivileges
0x1800281f1  nop     dword ptr [rax+rax+00h]
0x1800281f6  test    eax, eax
0x1800281f8  jnz     short loc_18002821D
0x1800281fa  call    cs:__imp_GetLastError
0x180028201  nop     dword ptr [rax+rax+00h]
0x180028206  mov     ecx, eax
0x180028208  mov     r9d, 86h
0x18002820e  call    ElValidateWin32_19
0x180028213  lea     ecx, [rbx+1Fh]
0x180028216  test    eax, eax
0x180028218  cmovz   eax, ecx
0x18002821b  mov     ebx, eax
0x18002821d  mov     eax, ebx
0x18002821f  add     rsp, 30h
0x180028223  pop     rbx
0x180028224  retn
```
