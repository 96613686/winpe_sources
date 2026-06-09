# IsTokenInAdminGroup(void *)

- ea: `0x180015568`
- end: `0x180015626`
- name: `?IsTokenInAdminGroup@@YA_NPEAX@Z`
- size: `190`
- prototype: `bool __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001562c`

## callees

- `0x180015568`
- `0x18001b150`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800155e6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800155e6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800155ce`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800155ce`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800155f7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800155f7`

## pseudocode

```c
bool __fastcall IsTokenInAdminGroup(HANDLE TokenHandle)
{
  bool v2; // zf
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  v2 = IsMember == 0;
  if ( IsMember )
  {
    if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
      IsMember = 0;
    FreeSid(SidToCheck);
    v2 = IsMember == 0;
  }
  return !v2;
}

```

## disassembly

```asm
0x180015568  mov     [rsp-8+arg_8], rbx
0x18001556d  mov     [rsp-8+arg_10], rdi
0x180015572  push    rbp
0x180015573  mov     rbp, rsp
0x180015576  sub     rsp, 80h
0x18001557d  mov     rax, cs:__security_cookie
0x180015584  xor     rax, rsp
0x180015587  mov     [rbp+var_8], rax
0x18001558b  xor     edi, edi
0x18001558d  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180015593  lea     rax, [rbp+SidToCheck]
0x180015597  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x18001559a  mov     [rsp+80h+pSid], rax; pSid
0x18001559f  mov     rbx, rcx
0x1800155a2  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800155a6  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800155aa  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800155ae  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800155b2  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800155b6  mov     r9d, 220h; nSubAuthority1
0x1800155bc  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800155c0  mov     dl, 2; nSubAuthorityCount
0x1800155c2  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800155c6  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800155ca  mov     [rbp+SidToCheck], rdi
0x1800155ce  call    cs:__imp_AllocateAndInitializeSid
0x1800155d4  mov     [rbp+IsMember], eax
0x1800155d7  test    eax, eax
0x1800155d9  jz      short loc_180015602
0x1800155db  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800155df  lea     r8, [rbp+IsMember]; IsMember
0x1800155e3  mov     rcx, rbx; TokenHandle
0x1800155e6  call    cs:__imp_CheckTokenMembership
0x1800155ec  test    eax, eax
0x1800155ee  jnz     short loc_1800155F3
0x1800155f0  mov     [rbp+IsMember], edi
0x1800155f3  mov     rcx, [rbp+SidToCheck]; pSid
0x1800155f7  call    cs:__imp_FreeSid
0x1800155fd  mov     eax, [rbp+IsMember]
0x180015600  test    eax, eax
0x180015602  setnz   al
0x180015605  mov     rcx, [rbp+var_8]
0x180015609  xor     rcx, rsp; StackCookie
0x18001560c  call    __security_check_cookie
0x180015611  lea     r11, [rsp+80h+var_s0]
0x180015619  mov     rbx, [r11+18h]
0x18001561d  mov     rdi, [r11+20h]
0x180015621  mov     rsp, r11
0x180015624  pop     rbp
0x180015625  retn
```
