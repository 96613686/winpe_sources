# CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)

- ea: `0x18002eb30`
- end: `0x18002eb90`
- name: `?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z`
- size: `96`
- prototype: `__int64 __fastcall(CSecurityDescriptor *__hidden this, const struct CSecurityDescriptor::SecurityId *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014d40`

## callees

- `0x18002e998`
- `0x18002eb30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002eb5f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002eb5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb69`

## pseudocode

```c
__int64 __fastcall CSecurityDescriptor::Allow(struct _ACL **this, struct _SID_IDENTIFIER_AUTHORITY *a2, DWORD a3)
{
  int v4; // ebx
  signed int LastError; // eax

  v4 = CSecurityDescriptor::AddAccessAllowedACEToACL(this + 3, a2, a3);
  if ( v4 >= 0 && !SetSecurityDescriptorDacl(*this, 1, this[3], 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002eb30  mov     [rsp+arg_0], rbx
0x18002eb35  mov     [rsp+arg_8], rsi
0x18002eb3a  push    rdi
0x18002eb3b  sub     rsp, 20h
0x18002eb3f  mov     rdi, rcx
0x18002eb42  add     rcx, 18h; struct _ACL **
0x18002eb46  call    ?AddAccessAllowedACEToACL@CSecurityDescriptor@@SAJPEAPEAU_ACL@@PEBUSecurityId@1@K@Z; CSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,CSecurityDescriptor::SecurityId const *,ulong)
0x18002eb4b  mov     ebx, eax
0x18002eb4d  test    eax, eax
0x18002eb4f  js      short loc_18002EB7E
0x18002eb51  mov     r8, [rdi+18h]; pDacl
0x18002eb55  xor     r9d, r9d; bDaclDefaulted
0x18002eb58  mov     rcx, [rdi]; pSecurityDescriptor
0x18002eb5b  lea     edx, [r9+1]; bDaclPresent
0x18002eb5f  call    cs:__imp_SetSecurityDescriptorDacl
0x18002eb65  test    eax, eax
0x18002eb67  jnz     short loc_18002EB7E
0x18002eb69  call    cs:__imp_GetLastError
0x18002eb6f  mov     ebx, eax
0x18002eb71  test    eax, eax
0x18002eb73  jle     short loc_18002EB7E
0x18002eb75  movzx   ebx, ax
0x18002eb78  or      ebx, 80070000h
0x18002eb7e  mov     rsi, [rsp+28h+arg_8]
0x18002eb83  mov     eax, ebx
0x18002eb85  mov     rbx, [rsp+28h+arg_0]
0x18002eb8a  add     rsp, 20h
0x18002eb8e  pop     rdi
0x18002eb8f  retn
```
