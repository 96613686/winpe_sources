# SecurityHelper::IsInAdministratorGroup(void *)

- ea: `0x14005d330`
- end: `0x14005d4d9`
- name: `?IsInAdministratorGroup@SecurityHelper@@YAHPEAX@Z`
- size: `425`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003d53c`

## callees

- `0x14002d0a0`
- `0x14002dd20`
- `0x14005d330`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14005d382`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14005d3db`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14005d434`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14005d489`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14005d382`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14005d3db`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14005d434`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14005d489`
- `ADVAPI32!CheckTokenMembership` at `0x14005d39d`
- `ADVAPI32!CheckTokenMembership` at `0x14005d3f6`
- `ADVAPI32!CheckTokenMembership` at `0x14005d44f`
- `ADVAPI32!CheckTokenMembership` at `0x14005d4a4`
- `ADVAPI32!CheckTokenMembership` at `0x14005d39d`
- `ADVAPI32!CheckTokenMembership` at `0x14005d3f6`
- `ADVAPI32!CheckTokenMembership` at `0x14005d44f`
- `ADVAPI32!CheckTokenMembership` at `0x14005d4a4`

## pseudocode

```c
WINBOOL __fastcall SecurityHelper::IsInAdministratorGroup(HANDLE TokenHandle, void *a2)
{
  WINBOOL result; // eax
  WINBOOL IsMember; // [rsp+20h] [rbp-19h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-15h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-9h] BYREF

  IsMember = 0;
  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid)
    || (result = CheckTokenMembership(TokenHandle, pSid, &IsMember)) != 0 )
  {
    result = IsMember;
  }
  else
  {
    IsMember = 0;
  }
  if ( !result )
  {
    memset_0(pSid, 0, 0x44u);
    cbSid[0] = 68;
    if ( !CreateWellKnownSid(WinAccountAdministratorSid, 0, pSid, cbSid)
      || (result = CheckTokenMembership(TokenHandle, pSid, &IsMember)) != 0 )
    {
      result = IsMember;
    }
    else
    {
      IsMember = 0;
    }
    if ( !result )
    {
      memset_0(pSid, 0, 0x44u);
      cbSid[0] = 68;
      if ( !CreateWellKnownSid(WinAccountDomainAdminsSid, 0, pSid, cbSid)
        || (result = CheckTokenMembership(TokenHandle, pSid, &IsMember)) != 0 )
      {
        result = IsMember;
      }
      else
      {
        IsMember = 0;
      }
      if ( !result )
      {
        memset_0(pSid, 0, 0x44u);
        cbSid[0] = 68;
        if ( !CreateWellKnownSid(WinAccountEnterpriseAdminsSid, 0, pSid, cbSid) )
          return IsMember;
        result = CheckTokenMembership(TokenHandle, pSid, &IsMember);
        if ( result )
          return IsMember;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14005d330  mov     [rsp-8+arg_8], rbx
0x14005d335  mov     [rsp-8+arg_10], rdi
0x14005d33a  push    rbp
0x14005d33b  lea     rbp, [rsp-57h]
0x14005d340  sub     rsp, 90h
0x14005d347  mov     rax, cs:__security_cookie
0x14005d34e  xor     rax, rsp
0x14005d351  mov     [rbp+57h+var_10], rax
0x14005d355  mov     rbx, rcx
0x14005d358  mov     [rbp+57h+IsMember], 0
0x14005d35f  mov     edi, 44h ; 'D'
0x14005d364  lea     rcx, [rbp+57h+pSid]; void *
0x14005d368  mov     r8d, edi; Size
0x14005d36b  xor     edx, edx; Val
0x14005d36d  call    memset_0
0x14005d372  lea     r9, [rbp+57h+cbSid]; cbSid
0x14005d376  mov     [rbp+57h+cbSid], edi
0x14005d379  lea     r8, [rbp+57h+pSid]; pSid
0x14005d37d  xor     edx, edx; DomainSid
0x14005d37f  lea     ecx, [rdi-2Ah]; WellKnownSidType
0x14005d382  call    cs:__imp_CreateWellKnownSid
0x14005d389  nop     dword ptr [rax+rax+00h]
0x14005d38e  test    eax, eax
0x14005d390  jz      short loc_14005D3B2
0x14005d392  lea     r8, [rbp+57h+IsMember]; IsMember
0x14005d396  mov     rcx, rbx; TokenHandle
0x14005d399  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x14005d39d  call    cs:__imp_CheckTokenMembership
0x14005d3a4  nop     dword ptr [rax+rax+00h]
0x14005d3a9  test    eax, eax
0x14005d3ab  jnz     short loc_14005D3B2
0x14005d3ad  mov     [rbp+57h+IsMember], eax
0x14005d3b0  jmp     short loc_14005D3B5
0x14005d3b2  mov     eax, [rbp+57h+IsMember]
0x14005d3b5  test    eax, eax
0x14005d3b7  jnz     loc_14005D4B7
0x14005d3bd  mov     r8, rdi; Size
0x14005d3c0  lea     rcx, [rbp+57h+pSid]; void *
0x14005d3c4  xor     edx, edx; Val
0x14005d3c6  call    memset_0
0x14005d3cb  xor     edx, edx; DomainSid
0x14005d3cd  mov     [rbp+57h+cbSid], edi
0x14005d3d0  lea     r9, [rbp+57h+cbSid]; cbSid
0x14005d3d4  lea     r8, [rbp+57h+pSid]; pSid
0x14005d3d8  lea     ecx, [rdx+26h]; WellKnownSidType
0x14005d3db  call    cs:__imp_CreateWellKnownSid
0x14005d3e2  nop     dword ptr [rax+rax+00h]
0x14005d3e7  test    eax, eax
0x14005d3e9  jz      short loc_14005D40B
0x14005d3eb  lea     r8, [rbp+57h+IsMember]; IsMember
0x14005d3ef  mov     rcx, rbx; TokenHandle
0x14005d3f2  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x14005d3f6  call    cs:__imp_CheckTokenMembership
0x14005d3fd  nop     dword ptr [rax+rax+00h]
0x14005d402  test    eax, eax
0x14005d404  jnz     short loc_14005D40B
0x14005d406  mov     [rbp+57h+IsMember], eax
0x14005d409  jmp     short loc_14005D40E
0x14005d40b  mov     eax, [rbp+57h+IsMember]
0x14005d40e  test    eax, eax
0x14005d410  jnz     loc_14005D4B7
0x14005d416  mov     r8, rdi; Size
0x14005d419  lea     rcx, [rbp+57h+pSid]; void *
0x14005d41d  xor     edx, edx; Val
0x14005d41f  call    memset_0
0x14005d424  xor     edx, edx; DomainSid
0x14005d426  mov     [rbp+57h+cbSid], edi
0x14005d429  lea     r9, [rbp+57h+cbSid]; cbSid
0x14005d42d  lea     r8, [rbp+57h+pSid]; pSid
0x14005d431  lea     ecx, [rdx+29h]; WellKnownSidType
0x14005d434  call    cs:__imp_CreateWellKnownSid
0x14005d43b  nop     dword ptr [rax+rax+00h]
0x14005d440  test    eax, eax
0x14005d442  jz      short loc_14005D464
0x14005d444  lea     r8, [rbp+57h+IsMember]; IsMember
0x14005d448  mov     rcx, rbx; TokenHandle
0x14005d44b  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x14005d44f  call    cs:__imp_CheckTokenMembership
0x14005d456  nop     dword ptr [rax+rax+00h]
0x14005d45b  test    eax, eax
0x14005d45d  jnz     short loc_14005D464
0x14005d45f  mov     [rbp+57h+IsMember], eax
0x14005d462  jmp     short loc_14005D467
0x14005d464  mov     eax, [rbp+57h+IsMember]
0x14005d467  test    eax, eax
0x14005d469  jnz     short loc_14005D4B7
0x14005d46b  mov     r8, rdi; Size
0x14005d46e  lea     rcx, [rbp+57h+pSid]; void *
0x14005d472  xor     edx, edx; Val
0x14005d474  call    memset_0
0x14005d479  xor     edx, edx; DomainSid
0x14005d47b  mov     [rbp+57h+cbSid], edi
0x14005d47e  lea     r9, [rbp+57h+cbSid]; cbSid
0x14005d482  lea     r8, [rbp+57h+pSid]; pSid
0x14005d486  lea     ecx, [rdx+30h]; WellKnownSidType
0x14005d489  call    cs:__imp_CreateWellKnownSid
0x14005d490  nop     dword ptr [rax+rax+00h]
0x14005d495  test    eax, eax
0x14005d497  jz      short loc_14005D4B4
0x14005d499  lea     r8, [rbp+57h+IsMember]; IsMember
0x14005d49d  mov     rcx, rbx; TokenHandle
0x14005d4a0  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x14005d4a4  call    cs:__imp_CheckTokenMembership
0x14005d4ab  nop     dword ptr [rax+rax+00h]
0x14005d4b0  test    eax, eax
0x14005d4b2  jz      short loc_14005D4B7
0x14005d4b4  mov     eax, [rbp+57h+IsMember]
0x14005d4b7  mov     rcx, [rbp+57h+var_10]
0x14005d4bb  xor     rcx, rsp; StackCookie
0x14005d4be  call    __security_check_cookie
0x14005d4c3  lea     r11, [rsp+90h+var_s0]
0x14005d4cb  mov     rbx, [r11+18h]
0x14005d4cf  mov     rdi, [r11+20h]
0x14005d4d3  mov     rsp, r11
0x14005d4d6  pop     rbp
0x14005d4d7  retn
```
