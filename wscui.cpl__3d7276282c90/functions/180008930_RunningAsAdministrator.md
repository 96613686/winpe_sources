# RunningAsAdministrator

- ea: `0x180008930`
- end: `0x1800089dc`
- name: `RunningAsAdministrator`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003ba0`
- `0x180005bf0`
- `0x180006520`

## callees

- `0x180008930`
- `0x18000a640`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008991`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180008991`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800089b6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800089b6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800089a5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800089a5`

## pseudocode

```c
__int64 RunningAsAdministrator()
{
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
      IsMember = 0;
    FreeSid(SidToCheck);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180008930  mov     [rsp-8+arg_0], rbx
0x180008935  push    rbp
0x180008936  mov     rbp, rsp
0x180008939  sub     rsp, 80h
0x180008940  mov     rax, cs:__security_cookie
0x180008947  xor     rax, rsp
0x18000894a  mov     [rbp+var_8], rax
0x18000894e  xor     ebx, ebx
0x180008950  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180008956  lea     rax, [rbp+SidToCheck]
0x18000895a  mov     [rbp+IsMember], ebx
0x18000895d  mov     [rsp+80h+pSid], rax; pSid
0x180008962  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180008966  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x18000896a  mov     r9d, 220h; nSubAuthority1
0x180008970  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x180008974  lea     r8d, [rbx+20h]; nSubAuthority0
0x180008978  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x18000897c  mov     dl, 2; nSubAuthorityCount
0x18000897e  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x180008982  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x180008986  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x18000898a  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x18000898d  mov     [rbp+SidToCheck], rbx
0x180008991  call    cs:__imp_AllocateAndInitializeSid
0x180008997  test    eax, eax
0x180008999  jz      short loc_1800089BC
0x18000899b  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18000899f  lea     r8, [rbp+IsMember]; IsMember
0x1800089a3  xor     ecx, ecx; TokenHandle
0x1800089a5  call    cs:__imp_CheckTokenMembership
0x1800089ab  test    eax, eax
0x1800089ad  jnz     short loc_1800089B2
0x1800089af  mov     [rbp+IsMember], ebx
0x1800089b2  mov     rcx, [rbp+SidToCheck]; pSid
0x1800089b6  call    cs:__imp_FreeSid
0x1800089bc  mov     eax, [rbp+IsMember]
0x1800089bf  mov     rcx, [rbp+var_8]
0x1800089c3  xor     rcx, rsp; StackCookie
0x1800089c6  call    __security_check_cookie
0x1800089cb  mov     rbx, [rsp+80h+arg_0]
0x1800089d3  add     rsp, 80h
0x1800089da  pop     rbp
0x1800089db  retn
```
