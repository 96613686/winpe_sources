# IsUserAdmin(void)

- ea: `0x1800041c8`
- end: `0x180004280`
- name: `?IsUserAdmin@@YAHXZ`
- size: `184`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003e14`
- `0x1800047d0`

## callees

- `0x1800041c8`
- `0x18003c560`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004253`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004253`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004229`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004229`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004243`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004243`

## pseudocode

```c
_BOOL8 IsUserAdmin(void)
{
  BOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    CheckTokenMembership(0, SidToCheck, &IsMember);
    FreeSid(SidToCheck);
  }
  return IsMember;
}

```

## disassembly

```asm
0x1800041c8  mov     [rsp-8+arg_0], rbx
0x1800041cd  push    rbp
0x1800041ce  mov     rbp, rsp
0x1800041d1  sub     rsp, 80h
0x1800041d8  mov     rax, cs:__security_cookie
0x1800041df  xor     rax, rsp
0x1800041e2  mov     [rbp+var_8], rax
0x1800041e6  xor     ebx, ebx
0x1800041e8  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800041ee  lea     rax, [rbp+SidToCheck]
0x1800041f2  mov     [rbp+IsMember], ebx
0x1800041f5  mov     [rsp+80h+pSid], rax; pSid
0x1800041fa  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800041fe  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x180004202  mov     r9d, 220h; nSubAuthority1
0x180004208  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x18000420c  lea     r8d, [rbx+20h]; nSubAuthority0
0x180004210  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x180004214  mov     dl, 2; nSubAuthorityCount
0x180004216  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x18000421a  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x18000421e  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x180004222  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x180004225  mov     [rbp+SidToCheck], rbx
0x180004229  call    cs:__imp_AllocateAndInitializeSid
0x180004230  nop     dword ptr [rax+rax+00h]
0x180004235  test    eax, eax
0x180004237  jz      short loc_18000425F
0x180004239  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18000423d  lea     r8, [rbp+IsMember]; IsMember
0x180004241  xor     ecx, ecx; TokenHandle
0x180004243  call    cs:__imp_CheckTokenMembership
0x18000424a  nop     dword ptr [rax+rax+00h]
0x18000424f  mov     rcx, [rbp+SidToCheck]; pSid
0x180004253  call    cs:__imp_FreeSid
0x18000425a  nop     dword ptr [rax+rax+00h]
0x18000425f  mov     eax, [rbp+IsMember]
0x180004262  mov     rcx, [rbp+var_8]
0x180004266  xor     rcx, rsp; StackCookie
0x180004269  call    __security_check_cookie
0x18000426e  mov     rbx, [rsp+80h+arg_0]
0x180004276  add     rsp, 80h
0x18000427d  pop     rbp
0x18000427e  retn
```
