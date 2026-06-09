# IsInteractiveUser(void)

- ea: `0x14000e550`
- end: `0x14000e61e`
- name: `?IsInteractiveUser@@YAHXZ`
- size: `206`
- prototype: `int(void)`
- caller_count: `10`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140012f54`
- `0x140015300`
- `0x140015fb8`
- `0x1400170a8`
- `0x1400172b0`
- `0x140017698`
- `0x140017904`
- `0x14001bcec`
- `0x14001bf80`
- `0x14001c64c`

## callees

- `0x140002480`
- `0x14000e550`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x14000e5b3`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000e5b3`
- `ADVAPI32!CheckTokenMembership` at `0x14000e5da`
- `ADVAPI32!CheckTokenMembership` at `0x14000e5da`
- `ADVAPI32!FreeSid` at `0x14000e5ec`
- `ADVAPI32!FreeSid` at `0x14000e5ec`

## pseudocode

```c
__int64 IsInteractiveUser(void)
{
  unsigned int v0; // edi
  PSID v1; // rdx
  BOOL v2; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  v0 = 1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v1 = SidToCheck;
  }
  else
  {
    v1 = 0;
    SidToCheck = 0;
  }
  if ( !v1 )
    return 0;
  v2 = CheckTokenMembership(0, v1, &IsMember);
  FreeSid(SidToCheck);
  if ( !v2 || !IsMember )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x14000e550  push    rbp
0x14000e552  push    rbx
0x14000e553  push    rsi
0x14000e554  push    rdi
0x14000e555  lea     rbp, [rsp-3Fh]
0x14000e55a  sub     rsp, 88h
0x14000e561  mov     rax, cs:__security_cookie
0x14000e568  xor     rax, rsp
0x14000e56b  mov     [rbp+57h+var_28], rax
0x14000e56f  xor     esi, esi
0x14000e571  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14000e577  lea     rax, [rbp+57h+SidToCheck]
0x14000e57b  mov     [rbp+57h+IsMember], esi
0x14000e57e  mov     [rsp+0A0h+pSid], rax; pSid
0x14000e583  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000e587  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x14000e58b  xor     r9d, r9d; nSubAuthority1
0x14000e58e  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x14000e592  lea     edi, [rsi+1]
0x14000e595  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x14000e599  lea     r8d, [rsi+4]; nSubAuthority0
0x14000e59d  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x14000e5a1  mov     dl, dil; nSubAuthorityCount
0x14000e5a4  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x14000e5a8  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x14000e5ac  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x14000e5af  mov     [rbp+57h+SidToCheck], rsi
0x14000e5b3  call    cs:__imp_AllocateAndInitializeSid
0x14000e5ba  nop     dword ptr [rax+rax+00h]
0x14000e5bf  test    eax, eax
0x14000e5c1  jnz     short loc_14000E5CB
0x14000e5c3  mov     edx, esi
0x14000e5c5  mov     [rbp+57h+SidToCheck], rdx
0x14000e5c9  jmp     short loc_14000E5CF
0x14000e5cb  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x14000e5cf  test    rdx, rdx
0x14000e5d2  jz      short loc_14000E601
0x14000e5d4  lea     r8, [rbp+57h+IsMember]; IsMember
0x14000e5d8  xor     ecx, ecx; TokenHandle
0x14000e5da  call    cs:__imp_CheckTokenMembership
0x14000e5e1  nop     dword ptr [rax+rax+00h]
0x14000e5e6  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x14000e5ea  mov     ebx, eax
0x14000e5ec  call    cs:__imp_FreeSid
0x14000e5f3  nop     dword ptr [rax+rax+00h]
0x14000e5f8  test    ebx, ebx
0x14000e5fa  jz      short loc_14000E601
0x14000e5fc  cmp     [rbp+57h+IsMember], esi
0x14000e5ff  jnz     short loc_14000E603
0x14000e601  mov     edi, esi
0x14000e603  mov     eax, edi
0x14000e605  mov     rcx, [rbp+57h+var_28]
0x14000e609  xor     rcx, rsp; StackCookie
0x14000e60c  call    __security_check_cookie
0x14000e611  add     rsp, 88h
0x14000e618  pop     rdi
0x14000e619  pop     rsi
0x14000e61a  pop     rbx
0x14000e61b  pop     rbp
0x14000e61c  retn
```
