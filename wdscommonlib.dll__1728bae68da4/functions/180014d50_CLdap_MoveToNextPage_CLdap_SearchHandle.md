# CLdap::MoveToNextPage(CLdap::SearchHandle *)

- ea: `0x180014d50`
- end: `0x180014e2e`
- name: `?MoveToNextPage@CLdap@@AEAAPEAXPEAUSearchHandle@1@@Z`
- size: `222`
- prototype: `void *__fastcall(CLdap *__hidden this, struct CLdap::SearchHandle *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180014640`
- `0x1800148d0`

## callees

- `0x180014690`
- `0x180014d50`
- `0x1800154f8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180014e0b`
- `KERNEL32!SetLastError` at `0x180014e0b`
- `WLDAP32!__imp_ldap_first_entry` at `0x180014de0`
- `WLDAP32!__imp_ldap_first_entry` at `0x180014de0`
- `WLDAP32!__imp_ldap_msgfree` at `0x180014d85`
- `WLDAP32!__imp_ldap_msgfree` at `0x180014d85`
- `WLDAP32!__imp_ldap_get_next_page_s` at `0x180014db6`
- `WLDAP32!__imp_ldap_get_next_page_s` at `0x180014db6`

## pseudocode

```c
LDAPMessage *__fastcall CLdap::MoveToNextPage(PLDAP *this, PLDAPSearch *a2)
{
  LDAPMessage *entry; // rsi
  LDAPMessage **Results; // rdi
  ULONG next_page_s; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int LdapErrorCode; // ebx
  ULONG TotalCount; // [rsp+50h] [rbp+8h] BYREF
  struct l_timeval timeout; // [rsp+58h] [rbp+10h] BYREF

  entry = 0;
  Results = (LDAPMessage **)(a2 + 2);
  TotalCount = 0;
  timeout = (struct l_timeval)58LL;
  while ( 1 )
  {
    if ( *Results )
    {
      ldap_msgfree(*Results);
      *Results = 0;
    }
    next_page_s = ldap_get_next_page_s(*this, a2[1], &timeout, 0x9C4u, &TotalCount, Results);
    LdapErrorCode = next_page_s;
    if ( next_page_s == 94 )
      break;
    if ( (unsigned int)ElValidateWin32_5(next_page_s, v7, v8, 0x299u) )
    {
      LdapErrorCode = CLdap::GetLdapErrorCode((CLdap *)this, LdapErrorCode);
      goto LABEL_10;
    }
    entry = ldap_first_entry(*this, *Results);
    if ( entry )
      goto LABEL_10;
  }
  LdapErrorCode = 259;
LABEL_10:
  SetLastError(LdapErrorCode);
  return entry;
}

```

## disassembly

```asm
0x180014d50  mov     rax, rsp
0x180014d53  mov     [rax+18h], rbx
0x180014d57  mov     [rax+20h], rbp
0x180014d5b  push    rsi
0x180014d5c  push    rdi
0x180014d5d  push    r14
0x180014d5f  sub     rsp, 30h
0x180014d63  xor     esi, esi
0x180014d65  lea     rdi, [rdx+10h]
0x180014d69  and     [rax+8], esi
0x180014d6c  mov     rbp, rdx
0x180014d6f  and     [rax+10h], rsi
0x180014d73  mov     r14, rcx
0x180014d76  mov     dword ptr [rax+10h], 3Ah ; ':'
0x180014d7d  mov     rcx, [rdi]; res
0x180014d80  test    rcx, rcx
0x180014d83  jz      short loc_180014D95
0x180014d85  call    cs:__imp_ldap_msgfree
0x180014d8c  nop     dword ptr [rax+rax+00h]
0x180014d91  and     qword ptr [rdi], 0
0x180014d95  mov     rdx, [rbp+8]; SearchHandle
0x180014d99  lea     rax, [rsp+48h+arg_0]
0x180014d9e  mov     rcx, [r14]; ExternalHandle
0x180014da1  lea     r8, [rsp+48h+timeout]; timeout
0x180014da6  mov     [rsp+48h+Results], rdi; Results
0x180014dab  mov     r9d, 9C4h; PageSize
0x180014db1  mov     [rsp+48h+TotalCount], rax; TotalCount
0x180014db6  call    cs:__imp_ldap_get_next_page_s
0x180014dbd  nop     dword ptr [rax+rax+00h]
0x180014dc2  mov     ebx, eax
0x180014dc4  cmp     eax, 5Eh ; '^'
0x180014dc7  jz      short loc_180014E04
0x180014dc9  mov     r9d, 299h
0x180014dcf  mov     ecx, eax
0x180014dd1  call    ElValidateWin32_5
0x180014dd6  test    eax, eax
0x180014dd8  jnz     short loc_180014DF6
0x180014dda  mov     rdx, [rdi]; res
0x180014ddd  mov     rcx, [r14]; ld
0x180014de0  call    cs:__imp_ldap_first_entry
0x180014de7  nop     dword ptr [rax+rax+00h]
0x180014dec  mov     rsi, rax
0x180014def  test    rax, rax
0x180014df2  jz      short loc_180014D7D
0x180014df4  jmp     short loc_180014E09
0x180014df6  mov     edx, ebx; unsigned int
0x180014df8  mov     rcx, r14; this
0x180014dfb  call    ?GetLdapErrorCode@CLdap@@AEAAKK@Z; CLdap::GetLdapErrorCode(ulong)
0x180014e00  mov     ebx, eax
0x180014e02  jmp     short loc_180014E09
0x180014e04  mov     ebx, 103h
0x180014e09  mov     ecx, ebx; dwErrCode
0x180014e0b  call    cs:__imp_SetLastError
0x180014e12  nop     dword ptr [rax+rax+00h]
0x180014e17  mov     rbx, [rsp+48h+arg_10]
0x180014e1c  mov     rax, rsi
0x180014e1f  mov     rbp, [rsp+48h+arg_18]
0x180014e24  add     rsp, 30h
0x180014e28  pop     r14
0x180014e2a  pop     rdi
0x180014e2b  pop     rsi
0x180014e2c  retn
```
