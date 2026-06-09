# RunningAsAdministrator

- ea: `0x180005650`
- end: `0x1800056fc`
- name: `RunningAsAdministrator`
- size: `172`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a80`
- `0x180003cd8`
- `0x180003e40`
- `0x180003f80`
- `0x180005308`
- `0x18003d620`

## callees

- `0x180005650`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800056b3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800056b3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800056c9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800056c9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800056dc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800056dc`

## pseudocode

```c
__int64 RunningAsAdministrator()
{
  WINBOOL IsMember; // [rsp+60h] [rbp-28h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-18h] BYREF

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
0x180005650  push    rbx
0x180005652  sub     rsp, 80h
0x180005659  mov     rax, cs:__security_cookie
0x180005660  xor     rax, rsp
0x180005663  mov     [rsp+88h+var_10], rax
0x180005668  xor     ebx, ebx
0x18000566a  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 500h
0x180005671  lea     rax, [rsp+88h+SidToCheck]
0x180005676  mov     [rsp+88h+IsMember], ebx
0x18000567a  mov     [rsp+88h+pSid], rax; pSid
0x18000567f  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x180005684  mov     [rsp+88h+nSubAuthority7], ebx; nSubAuthority7
0x180005688  mov     r9d, 220h; nSubAuthority1
0x18000568e  mov     [rsp+88h+nSubAuthority6], ebx; nSubAuthority6
0x180005692  mov     r8d, 20h ; ' '; nSubAuthority0
0x180005698  mov     [rsp+88h+nSubAuthority5], ebx; nSubAuthority5
0x18000569c  mov     dl, 2; nSubAuthorityCount
0x18000569e  mov     [rsp+88h+nSubAuthority4], ebx; nSubAuthority4
0x1800056a2  mov     [rsp+88h+nSubAuthority3], ebx; nSubAuthority3
0x1800056a6  mov     [rsp+88h+nSubAuthority2], ebx; nSubAuthority2
0x1800056aa  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], ebx
0x1800056ae  mov     [rsp+88h+SidToCheck], rbx
0x1800056b3  call    cs:__imp_AllocateAndInitializeSid
0x1800056b9  test    eax, eax
0x1800056bb  jz      short loc_1800056E2
0x1800056bd  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x1800056c2  lea     r8, [rsp+88h+IsMember]; IsMember
0x1800056c7  xor     ecx, ecx; TokenHandle
0x1800056c9  call    cs:__imp_CheckTokenMembership
0x1800056cf  test    eax, eax
0x1800056d1  jnz     short loc_1800056D7
0x1800056d3  mov     [rsp+88h+IsMember], ebx
0x1800056d7  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x1800056dc  call    cs:__imp_FreeSid
0x1800056e2  mov     eax, [rsp+88h+IsMember]
0x1800056e6  mov     rcx, [rsp+88h+var_10]
0x1800056eb  xor     rcx, rsp; StackCookie
0x1800056ee  call    __security_check_cookie
0x1800056f3  add     rsp, 80h
0x1800056fa  pop     rbx
0x1800056fb  retn
```
