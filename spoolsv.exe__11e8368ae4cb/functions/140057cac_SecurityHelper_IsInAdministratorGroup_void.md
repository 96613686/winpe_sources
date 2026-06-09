# SecurityHelper::IsInAdministratorGroup(void *)

- ea: `0x140057cac`
- end: `0x140057e24`
- name: `?IsInAdministratorGroup@SecurityHelper@@YAHPEAX@Z`
- size: `376`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003a044`

## callees

- `0x14002abc0`
- `0x14002b810`
- `0x140057cac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140057cfe`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140057d4b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140057d98`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140057de1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140057cfe`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140057d4b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140057d98`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140057de1`
- `ADVAPI32!CheckTokenMembership` at `0x140057d13`
- `ADVAPI32!CheckTokenMembership` at `0x140057d60`
- `ADVAPI32!CheckTokenMembership` at `0x140057dad`
- `ADVAPI32!CheckTokenMembership` at `0x140057df6`
- `ADVAPI32!CheckTokenMembership` at `0x140057d13`
- `ADVAPI32!CheckTokenMembership` at `0x140057d60`
- `ADVAPI32!CheckTokenMembership` at `0x140057dad`
- `ADVAPI32!CheckTokenMembership` at `0x140057df6`

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
0x140057cac  mov     [rsp-8+arg_8], rbx
0x140057cb1  mov     [rsp-8+arg_10], rdi
0x140057cb6  push    rbp
0x140057cb7  lea     rbp, [rsp-57h]
0x140057cbc  sub     rsp, 90h
0x140057cc3  mov     rax, cs:__security_cookie
0x140057cca  xor     rax, rsp
0x140057ccd  mov     [rbp+57h+var_10], rax
0x140057cd1  mov     rbx, rcx
0x140057cd4  mov     [rbp+57h+IsMember], 0
0x140057cdb  mov     edi, 44h ; 'D'
0x140057ce0  lea     rcx, [rbp+57h+pSid]; void *
0x140057ce4  mov     r8d, edi; Size
0x140057ce7  xor     edx, edx; Val
0x140057ce9  call    memset_0
0x140057cee  lea     r9, [rbp+57h+cbSid]; cbSid
0x140057cf2  mov     [rbp+57h+cbSid], edi
0x140057cf5  lea     r8, [rbp+57h+pSid]; pSid
0x140057cf9  xor     edx, edx; DomainSid
0x140057cfb  lea     ecx, [rdi-2Ah]; WellKnownSidType
0x140057cfe  call    cs:__imp_CreateWellKnownSid
0x140057d04  test    eax, eax
0x140057d06  jz      short loc_140057D22
0x140057d08  lea     r8, [rbp+57h+IsMember]; IsMember
0x140057d0c  mov     rcx, rbx; TokenHandle
0x140057d0f  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x140057d13  call    cs:__imp_CheckTokenMembership
0x140057d19  test    eax, eax
0x140057d1b  jnz     short loc_140057D22
0x140057d1d  mov     [rbp+57h+IsMember], eax
0x140057d20  jmp     short loc_140057D25
0x140057d22  mov     eax, [rbp+57h+IsMember]
0x140057d25  test    eax, eax
0x140057d27  jnz     loc_140057E03
0x140057d2d  mov     r8, rdi; Size
0x140057d30  lea     rcx, [rbp+57h+pSid]; void *
0x140057d34  xor     edx, edx; Val
0x140057d36  call    memset_0
0x140057d3b  xor     edx, edx; DomainSid
0x140057d3d  mov     [rbp+57h+cbSid], edi
0x140057d40  lea     r9, [rbp+57h+cbSid]; cbSid
0x140057d44  lea     r8, [rbp+57h+pSid]; pSid
0x140057d48  lea     ecx, [rdx+26h]; WellKnownSidType
0x140057d4b  call    cs:__imp_CreateWellKnownSid
0x140057d51  test    eax, eax
0x140057d53  jz      short loc_140057D6F
0x140057d55  lea     r8, [rbp+57h+IsMember]; IsMember
0x140057d59  mov     rcx, rbx; TokenHandle
0x140057d5c  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x140057d60  call    cs:__imp_CheckTokenMembership
0x140057d66  test    eax, eax
0x140057d68  jnz     short loc_140057D6F
0x140057d6a  mov     [rbp+57h+IsMember], eax
0x140057d6d  jmp     short loc_140057D72
0x140057d6f  mov     eax, [rbp+57h+IsMember]
0x140057d72  test    eax, eax
0x140057d74  jnz     loc_140057E03
0x140057d7a  mov     r8, rdi; Size
0x140057d7d  lea     rcx, [rbp+57h+pSid]; void *
0x140057d81  xor     edx, edx; Val
0x140057d83  call    memset_0
0x140057d88  xor     edx, edx; DomainSid
0x140057d8a  mov     [rbp+57h+cbSid], edi
0x140057d8d  lea     r9, [rbp+57h+cbSid]; cbSid
0x140057d91  lea     r8, [rbp+57h+pSid]; pSid
0x140057d95  lea     ecx, [rdx+29h]; WellKnownSidType
0x140057d98  call    cs:__imp_CreateWellKnownSid
0x140057d9e  test    eax, eax
0x140057da0  jz      short loc_140057DBC
0x140057da2  lea     r8, [rbp+57h+IsMember]; IsMember
0x140057da6  mov     rcx, rbx; TokenHandle
0x140057da9  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x140057dad  call    cs:__imp_CheckTokenMembership
0x140057db3  test    eax, eax
0x140057db5  jnz     short loc_140057DBC
0x140057db7  mov     [rbp+57h+IsMember], eax
0x140057dba  jmp     short loc_140057DBF
0x140057dbc  mov     eax, [rbp+57h+IsMember]
0x140057dbf  test    eax, eax
0x140057dc1  jnz     short loc_140057E03
0x140057dc3  mov     r8, rdi; Size
0x140057dc6  lea     rcx, [rbp+57h+pSid]; void *
0x140057dca  xor     edx, edx; Val
0x140057dcc  call    memset_0
0x140057dd1  xor     edx, edx; DomainSid
0x140057dd3  mov     [rbp+57h+cbSid], edi
0x140057dd6  lea     r9, [rbp+57h+cbSid]; cbSid
0x140057dda  lea     r8, [rbp+57h+pSid]; pSid
0x140057dde  lea     ecx, [rdx+30h]; WellKnownSidType
0x140057de1  call    cs:__imp_CreateWellKnownSid
0x140057de7  test    eax, eax
0x140057de9  jz      short loc_140057E00
0x140057deb  lea     r8, [rbp+57h+IsMember]; IsMember
0x140057def  mov     rcx, rbx; TokenHandle
0x140057df2  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x140057df6  call    cs:__imp_CheckTokenMembership
0x140057dfc  test    eax, eax
0x140057dfe  jz      short loc_140057E03
0x140057e00  mov     eax, [rbp+57h+IsMember]
0x140057e03  mov     rcx, [rbp+57h+var_10]
0x140057e07  xor     rcx, rsp; StackCookie
0x140057e0a  call    __security_check_cookie
0x140057e0f  lea     r11, [rsp+90h+var_s0]
0x140057e17  mov     rbx, [r11+18h]
0x140057e1b  mov     rdi, [r11+20h]
0x140057e1f  mov     rsp, r11
0x140057e22  pop     rbp
0x140057e23  retn
```
