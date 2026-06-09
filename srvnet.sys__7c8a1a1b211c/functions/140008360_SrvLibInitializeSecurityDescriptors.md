# SrvLibInitializeSecurityDescriptors

- ea: `0x140008360`
- end: `0x140008818`
- name: `SrvLibInitializeSecurityDescriptors`
- size: `1208`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14005b3c8`

## callees

- `0x140007360`
- `0x140007c60`
- `0x140008360`
- `0x14002a3e0`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140008394`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140008421`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140008483`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400084db`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14000853c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140008394`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140008421`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140008483`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400084db`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14000853c`
- `ntoskrnl!RtlInitializeSid` at `0x1400083df`
- `ntoskrnl!RtlInitializeSid` at `0x14000845d`
- `ntoskrnl!RtlInitializeSid` at `0x1400084b5`
- `ntoskrnl!RtlInitializeSid` at `0x140008514`
- `ntoskrnl!RtlInitializeSid` at `0x140008574`
- `ntoskrnl!RtlInitializeSid` at `0x1400083df`
- `ntoskrnl!RtlInitializeSid` at `0x14000845d`
- `ntoskrnl!RtlInitializeSid` at `0x1400084b5`
- `ntoskrnl!RtlInitializeSid` at `0x140008514`
- `ntoskrnl!RtlInitializeSid` at `0x140008574`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400083f0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000840c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000846e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400084c6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140008525`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140008585`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000859f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400085b5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400085cb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400085e1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400083f0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000840c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000846e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400084c6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140008525`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140008585`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000859f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400085b5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400085cb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400085e1`
- `ntoskrnl!RtlCreateAcl` at `0x140008630`
- `ntoskrnl!RtlCreateAcl` at `0x140008630`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000864c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140008664`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000867c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140008697`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400086b6`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000864c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140008664`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000867c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140008697`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400086b6`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400086ea`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400086ea`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140008706`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140008706`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008728`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000874d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008774`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000879b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400087c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400087eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008728`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000874d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008774`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000879b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400087c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400087eb`

## pseudocode

```c
__int64 SrvLibInitializeSecurityDescriptors()
{
  ULONG v0; // edi
  unsigned int *PoolWithTag; // rax
  unsigned int *v2; // rbx
  NTSTATUS v3; // edi
  unsigned int *v4; // r14
  unsigned int *v5; // r15
  struct _ACL *v6; // rbp
  unsigned int *v7; // rax
  unsigned int *v8; // r13
  unsigned int *v9; // rsi
  unsigned int *v10; // rax
  unsigned int *v11; // rax
  __int64 v12; // r12
  unsigned int *v13; // rax
  ULONG v14; // edi
  struct _ACL *v15; // rax
  void *v16; // rax
  ULONG v18; // [rsp+20h] [rbp-68h]
  ULONG v19; // [rsp+24h] [rbp-64h]
  ULONG v20; // [rsp+28h] [rbp-60h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+2Ch] [rbp-5Ch] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v0 = RtlLengthRequiredSid(2u);
  PoolWithTag = (unsigned int *)SrvNetAllocatePoolWithTag(258, v0, 1280529228);
  v2 = PoolWithTag;
  if ( !PoolWithTag )
    return (unsigned int)-1073741670;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v2, 0) = 32;
  *RtlSubAuthoritySid(v2, 1u) = 544;
  v20 = RtlLengthRequiredSid(1u);
  v7 = (unsigned int *)SrvNetAllocatePoolWithTag(258, v20, 1280529228);
  v8 = v7;
  if ( v7 )
  {
    RtlInitializeSid(v7, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(v8, 0) = 7;
    v19 = RtlLengthRequiredSid(1u);
    v10 = (unsigned int *)SrvNetAllocatePoolWithTag(258, v19, 1280529228);
    v9 = v10;
    if ( v10 )
    {
      RtlInitializeSid(v10, &IdentifierAuthority, 1u);
      *RtlSubAuthoritySid(v9, 0) = 4;
      v18 = RtlLengthRequiredSid(1u);
      v11 = (unsigned int *)SrvNetAllocatePoolWithTag(258, v18, 1280529228);
      v4 = v11;
      if ( v11 )
      {
        RtlInitializeSid(v11, &IdentifierAuthority, 1u);
        *RtlSubAuthoritySid(v4, 0) = 2;
        v12 = RtlLengthRequiredSid(5u);
        v13 = (unsigned int *)SrvNetAllocatePoolWithTag(258, v12, 1280529228);
        v5 = v13;
        if ( v13 )
        {
          RtlInitializeSid(v13, &IdentifierAuthority, 5u);
          *RtlSubAuthoritySid(v5, 0) = 21;
          *RtlSubAuthoritySid(v5, 1u) = 0;
          *RtlSubAuthoritySid(v5, 2u) = 0;
          *RtlSubAuthoritySid(v5, 3u) = 0;
          *RtlSubAuthoritySid(v5, 4u) = 497;
          v14 = v20 + v19 + v12 + v18 + 48 + v0;
          v15 = (struct _ACL *)SrvNetAllocatePoolWithTag(258, v14, 1280529228);
          v6 = v15;
          if ( v15 )
          {
            RtlCreateAcl(v15, v14, 2u);
            RtlAddAccessAllowedAce(v6, 2u, 2u, v2);
            RtlAddAccessAllowedAce(v6, 2u, 0x80u, v8);
            RtlAddAccessAllowedAce(v6, 2u, 4u, v9);
            RtlAddAccessAllowedAce(v6, 2u, 1u, v4);
            RtlAddAccessAllowedAce(v6, 2u, 0x100u, v5);
            v16 = (void *)SrvNetAllocatePoolWithTag(256, 40, 1280529228);
            SrvLibCommonGroupSD = v16;
            if ( v16 )
            {
              RtlCreateSecurityDescriptor(v16, 1u);
              v3 = RtlSetDaclSecurityDescriptor(SrvLibCommonGroupSD, 1u, v6, 0);
              goto LABEL_12;
            }
          }
        }
      }
    }
  }
  else
  {
    v9 = 0;
  }
  v3 = -1073741670;
LABEL_12:
  SrvNetUpdateMemStatistics(*(v2 - 3), *(v2 - 4), 0);
  ExFreePoolWithTag(v2 - 4, 0);
  if ( v9 )
  {
    SrvNetUpdateMemStatistics(*(v9 - 3), *(v9 - 4), 0);
    ExFreePoolWithTag(v9 - 4, 0);
  }
  if ( v4 )
  {
    SrvNetUpdateMemStatistics(*(v4 - 3), *(v4 - 4), 0);
    ExFreePoolWithTag(v4 - 4, 0);
  }
  if ( v8 )
  {
    SrvNetUpdateMemStatistics(*(v8 - 3), *(v8 - 4), 0);
    ExFreePoolWithTag(v8 - 4, 0);
  }
  if ( v5 )
  {
    SrvNetUpdateMemStatistics(*(v5 - 3), *(v5 - 4), 0);
    ExFreePoolWithTag(v5 - 4, 0);
  }
  if ( v3 < 0 && v6 )
  {
    SrvNetUpdateMemStatistics(*(unsigned int *)&v6[-2].AceCount, *(unsigned int *)&v6[-2].AclRevision, 0);
    ExFreePoolWithTag(&v6[-2], 0);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140008360  push    rbx
0x140008362  push    rbp
0x140008363  push    rsi
0x140008364  push    rdi
0x140008365  push    r12
0x140008367  push    r13
0x140008369  push    r14
0x14000836b  push    r15
0x14000836d  sub     rsp, 48h
0x140008371  mov     rax, cs:__security_cookie
0x140008378  xor     rax, rsp
0x14000837b  mov     [rsp+88h+var_50], rax
0x140008380  mov     ecx, 2; SubAuthorityCount
0x140008385  mov     dword ptr [rsp+88h+IdentifierAuthority.Value], 0
0x14000838d  mov     word ptr [rsp+88h+IdentifierAuthority.Value+4], 500h
0x140008394  call    cs:__imp_RtlLengthRequiredSid
0x14000839b  nop     dword ptr [rax+rax+00h]
0x1400083a0  mov     esi, 4C53534Ch
0x1400083a5  mov     r13d, 102h
0x1400083ab  mov     edx, eax
0x1400083ad  mov     r8d, esi
0x1400083b0  mov     ecx, r13d
0x1400083b3  mov     edi, eax
0x1400083b5  call    SrvNetAllocatePoolWithTag
0x1400083ba  mov     rbx, rax
0x1400083bd  test    rax, rax
0x1400083c0  jnz     short loc_1400083CC
0x1400083c2  mov     edi, 0C000009Ah
0x1400083c7  jmp     loc_1400087F7
0x1400083cc  mov     r8b, 2; SubAuthorityCount
0x1400083cf  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x1400083d4  mov     rcx, rbx; Sid
0x1400083d7  xor     r14d, r14d
0x1400083da  xor     r15d, r15d
0x1400083dd  xor     ebp, ebp
0x1400083df  call    cs:__imp_RtlInitializeSid
0x1400083e6  nop     dword ptr [rax+rax+00h]
0x1400083eb  xor     edx, edx; SubAuthority
0x1400083ed  mov     rcx, rbx; Sid
0x1400083f0  call    cs:__imp_RtlSubAuthoritySid
0x1400083f7  nop     dword ptr [rax+rax+00h]
0x1400083fc  lea     r12d, [r14+1]
0x140008400  mov     rcx, rbx; Sid
0x140008403  mov     edx, r12d; SubAuthority
0x140008406  mov     dword ptr [rax], 20h ; ' '
0x14000840c  call    cs:__imp_RtlSubAuthoritySid
0x140008413  nop     dword ptr [rax+rax+00h]
0x140008418  mov     ecx, r12d; SubAuthorityCount
0x14000841b  mov     dword ptr [rax], 220h
0x140008421  call    cs:__imp_RtlLengthRequiredSid
0x140008428  nop     dword ptr [rax+rax+00h]
0x14000842d  mov     edx, eax
0x14000842f  mov     r8d, esi
0x140008432  mov     rcx, r13
0x140008435  mov     [rsp+88h+var_60], eax
0x140008439  call    SrvNetAllocatePoolWithTag
0x14000843e  mov     r13, rax
0x140008441  test    rax, rax
0x140008444  jnz     short loc_140008452
0x140008446  xor     esi, esi
0x140008448  mov     edi, 0C000009Ah
0x14000844d  jmp     loc_140008714
0x140008452  mov     r8b, r12b; SubAuthorityCount
0x140008455  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x14000845a  mov     rcx, r13; Sid
0x14000845d  call    cs:__imp_RtlInitializeSid
0x140008464  nop     dword ptr [rax+rax+00h]
0x140008469  xor     edx, edx; SubAuthority
0x14000846b  mov     rcx, r13; Sid
0x14000846e  call    cs:__imp_RtlSubAuthoritySid
0x140008475  nop     dword ptr [rax+rax+00h]
0x14000847a  mov     ecx, r12d; SubAuthorityCount
0x14000847d  mov     dword ptr [rax], 7
0x140008483  call    cs:__imp_RtlLengthRequiredSid
0x14000848a  nop     dword ptr [rax+rax+00h]
0x14000848f  mov     edx, eax
0x140008491  mov     r8d, esi
0x140008494  mov     ecx, 102h
0x140008499  mov     [rsp+88h+var_64], eax
0x14000849d  call    SrvNetAllocatePoolWithTag
0x1400084a2  mov     rsi, rax
0x1400084a5  test    rax, rax
0x1400084a8  jz      short loc_140008448
0x1400084aa  mov     r8b, r12b; SubAuthorityCount
0x1400084ad  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x1400084b2  mov     rcx, rax; Sid
0x1400084b5  call    cs:__imp_RtlInitializeSid
0x1400084bc  nop     dword ptr [rax+rax+00h]
0x1400084c1  xor     edx, edx; SubAuthority
0x1400084c3  mov     rcx, rsi; Sid
0x1400084c6  call    cs:__imp_RtlSubAuthoritySid
0x1400084cd  nop     dword ptr [rax+rax+00h]
0x1400084d2  mov     ecx, r12d; SubAuthorityCount
0x1400084d5  mov     dword ptr [rax], 4
0x1400084db  call    cs:__imp_RtlLengthRequiredSid
0x1400084e2  nop     dword ptr [rax+rax+00h]
0x1400084e7  mov     edx, eax
0x1400084e9  mov     ecx, 102h
0x1400084ee  mov     r8d, 4C53534Ch
0x1400084f4  mov     [rsp+88h+var_68], eax
0x1400084f8  call    SrvNetAllocatePoolWithTag
0x1400084fd  mov     r14, rax
0x140008500  test    rax, rax
0x140008503  jz      loc_140008448
0x140008509  mov     r8b, r12b; SubAuthorityCount
0x14000850c  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x140008511  mov     rcx, rax; Sid
0x140008514  call    cs:__imp_RtlInitializeSid
0x14000851b  nop     dword ptr [rax+rax+00h]
0x140008520  xor     edx, edx; SubAuthority
0x140008522  mov     rcx, r14; Sid
0x140008525  call    cs:__imp_RtlSubAuthoritySid
0x14000852c  nop     dword ptr [rax+rax+00h]
0x140008531  mov     ecx, 5; SubAuthorityCount
0x140008536  mov     dword ptr [rax], 2
0x14000853c  call    cs:__imp_RtlLengthRequiredSid
0x140008543  nop     dword ptr [rax+rax+00h]
0x140008548  mov     edx, eax
0x14000854a  mov     ecx, 102h
0x14000854f  mov     r8d, 4C53534Ch
0x140008555  mov     r12d, eax
0x140008558  call    SrvNetAllocatePoolWithTag
0x14000855d  mov     r15, rax
0x140008560  test    rax, rax
0x140008563  jz      loc_140008448
0x140008569  mov     r8b, 5; SubAuthorityCount
0x14000856c  lea     rdx, [rsp+88h+IdentifierAuthority]; IdentifierAuthority
0x140008571  mov     rcx, rax; Sid
0x140008574  call    cs:__imp_RtlInitializeSid
0x14000857b  nop     dword ptr [rax+rax+00h]
0x140008580  xor     edx, edx; SubAuthority
0x140008582  mov     rcx, r15; Sid
0x140008585  call    cs:__imp_RtlSubAuthoritySid
0x14000858c  nop     dword ptr [rax+rax+00h]
0x140008591  mov     edx, 1; SubAuthority
0x140008596  mov     rcx, r15; Sid
0x140008599  mov     dword ptr [rax], 15h
0x14000859f  call    cs:__imp_RtlSubAuthoritySid
0x1400085a6  nop     dword ptr [rax+rax+00h]
0x1400085ab  mov     edx, 2; SubAuthority
0x1400085b0  mov     rcx, r15; Sid
0x1400085b3  mov     [rax], ebp
0x1400085b5  call    cs:__imp_RtlSubAuthoritySid
0x1400085bc  nop     dword ptr [rax+rax+00h]
0x1400085c1  mov     edx, 3; SubAuthority
0x1400085c6  mov     rcx, r15; Sid
0x1400085c9  mov     [rax], ebp
0x1400085cb  call    cs:__imp_RtlSubAuthoritySid
0x1400085d2  nop     dword ptr [rax+rax+00h]
0x1400085d7  mov     edx, 4; SubAuthority
0x1400085dc  mov     rcx, r15; Sid
0x1400085df  mov     [rax], ebp
0x1400085e1  call    cs:__imp_RtlSubAuthoritySid
0x1400085e8  nop     dword ptr [rax+rax+00h]
0x1400085ed  mov     ecx, 102h
0x1400085f2  mov     r8d, 4C53534Ch
0x1400085f8  mov     dword ptr [rax], 1F1h
0x1400085fe  mov     eax, [rsp+88h+var_68]
0x140008602  add     eax, 30h ; '0'
0x140008605  add     eax, r12d
0x140008608  add     eax, [rsp+88h+var_64]
0x14000860c  add     eax, [rsp+88h+var_60]
0x140008610  add     edi, eax
0x140008612  mov     edx, edi
0x140008614  call    SrvNetAllocatePoolWithTag
0x140008619  mov     rbp, rax
0x14000861c  test    rax, rax
0x14000861f  jz      loc_140008448
0x140008625  mov     r8d, 2; AclRevision
0x14000862b  mov     edx, edi; AclLength
0x14000862d  mov     rcx, rax; Acl
0x140008630  call    cs:__imp_RtlCreateAcl
0x140008637  nop     dword ptr [rax+rax+00h]
0x14000863c  mov     edi, 2
0x140008641  mov     r9, rbx; Sid
0x140008644  mov     r8d, edi; AccessMask
0x140008647  mov     edx, edi; AceRevision
0x140008649  mov     rcx, rbp; Acl
0x14000864c  call    cs:__imp_RtlAddAccessAllowedAce
0x140008653  nop     dword ptr [rax+rax+00h]
0x140008658  mov     r9, r13; Sid
0x14000865b  lea     r8d, [rdi+7Eh]; AccessMask
0x14000865f  mov     edx, edi; AceRevision
0x140008661  mov     rcx, rbp; Acl
0x140008664  call    cs:__imp_RtlAddAccessAllowedAce
0x14000866b  nop     dword ptr [rax+rax+00h]
0x140008670  mov     r9, rsi; Sid
0x140008673  lea     r8d, [rdi+2]; AccessMask
0x140008677  mov     edx, edi; AceRevision
0x140008679  mov     rcx, rbp; Acl
0x14000867c  call    cs:__imp_RtlAddAccessAllowedAce
0x140008683  nop     dword ptr [rax+rax+00h]
0x140008688  lea     r12d, [rdi-1]
0x14000868c  mov     r9, r14; Sid
0x14000868f  mov     r8d, r12d; AccessMask
0x140008692  mov     edx, edi; AceRevision
0x140008694  mov     rcx, rbp; Acl
0x140008697  call    cs:__imp_RtlAddAccessAllowedAce
0x14000869e  nop     dword ptr [rax+rax+00h]
0x1400086a3  mov     edi, 100h
0x1400086a8  lea     edx, [r12+1]; AceRevision
0x1400086ad  mov     r8d, edi; AccessMask
0x1400086b0  mov     r9, r15; Sid
0x1400086b3  mov     rcx, rbp; Acl
0x1400086b6  call    cs:__imp_RtlAddAccessAllowedAce
0x1400086bd  nop     dword ptr [rax+rax+00h]
0x1400086c2  lea     edx, [r12+27h]
0x1400086c7  mov     r8d, 4C53534Ch
0x1400086cd  mov     ecx, edi
0x1400086cf  call    SrvNetAllocatePoolWithTag
0x1400086d4  mov     cs:SrvLibCommonGroupSD, rax
0x1400086db  test    rax, rax
0x1400086de  jz      loc_140008448
0x1400086e4  mov     edx, r12d; Revision
0x1400086e7  mov     rcx, rax; SecurityDescriptor
0x1400086ea  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400086f1  nop     dword ptr [rax+rax+00h]
0x1400086f6  mov     rcx, cs:SrvLibCommonGroupSD; SecurityDescriptor
0x1400086fd  xor     r9d, r9d; DaclDefaulted
0x140008700  mov     r8, rbp; Dacl
0x140008703  mov     dl, r12b; DaclPresent
0x140008706  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000870d  nop     dword ptr [rax+rax+00h]
0x140008712  mov     edi, eax
0x140008714  mov     ecx, [rbx-0Ch]
0x140008717  xor     r8d, r8d
0x14000871a  mov     edx, [rbx-10h]
0x14000871d  call    SrvNetUpdateMemStatistics
0x140008722  xor     edx, edx; Tag
0x140008724  lea     rcx, [rbx-10h]; P
0x140008728  call    cs:__imp_ExFreePoolWithTag
0x14000872f  nop     dword ptr [rax+rax+00h]
0x140008734  test    rsi, rsi
0x140008737  jz      short loc_140008759
0x140008739  mov     ecx, [rsi-0Ch]
0x14000873c  xor     r8d, r8d
0x14000873f  mov     edx, [rsi-10h]
0x140008742  call    SrvNetUpdateMemStatistics
0x140008747  xor     edx, edx; Tag
0x140008749  lea     rcx, [rsi-10h]; P
0x14000874d  call    cs:__imp_ExFreePoolWithTag
0x140008754  nop     dword ptr [rax+rax+00h]
0x140008759  test    r14, r14
0x14000875c  jz      short loc_140008780
0x14000875e  mov     ecx, [r14-0Ch]
0x140008762  xor     r8d, r8d
0x140008765  mov     edx, [r14-10h]
0x140008769  call    SrvNetUpdateMemStatistics
0x14000876e  xor     edx, edx; Tag
0x140008770  lea     rcx, [r14-10h]; P
0x140008774  call    cs:__imp_ExFreePoolWithTag
0x14000877b  nop     dword ptr [rax+rax+00h]
0x140008780  test    r13, r13
0x140008783  jz      short loc_1400087A7
0x140008785  mov     ecx, [r13-0Ch]
0x140008789  xor     r8d, r8d
0x14000878c  mov     edx, [r13-10h]
0x140008790  call    SrvNetUpdateMemStatistics
0x140008795  xor     edx, edx; Tag
0x140008797  lea     rcx, [r13-10h]; P
0x14000879b  call    cs:__imp_ExFreePoolWithTag
0x1400087a2  nop     dword ptr [rax+rax+00h]
0x1400087a7  test    r15, r15
0x1400087aa  jz      short loc_1400087CE
0x1400087ac  mov     ecx, [r15-0Ch]
0x1400087b0  xor     r8d, r8d
0x1400087b3  mov     edx, [r15-10h]
0x1400087b7  call    SrvNetUpdateMemStatistics
0x1400087bc  xor     edx, edx; Tag
0x1400087be  lea     rcx, [r15-10h]; P
0x1400087c2  call    cs:__imp_ExFreePoolWithTag
0x1400087c9  nop     dword ptr [rax+rax+00h]
0x1400087ce  test    edi, edi
0x1400087d0  jns     short loc_1400087F7
0x1400087d2  test    rbp, rbp
0x1400087d5  jz      short loc_1400087F7
0x1400087d7  mov     ecx, [rbp-0Ch]
0x1400087da  xor     r8d, r8d
0x1400087dd  mov     edx, [rbp-10h]
0x1400087e0  call    SrvNetUpdateMemStatistics
0x1400087e5  xor     edx, edx; Tag
0x1400087e7  lea     rcx, [rbp-10h]; P
0x1400087eb  call    cs:__imp_ExFreePoolWithTag
0x1400087f2  nop     dword ptr [rax+rax+00h]
0x1400087f7  mov     eax, edi
0x1400087f9  mov     rcx, [rsp+88h+var_50]
0x1400087fe  xor     rcx, rsp; StackCookie
0x140008801  call    __security_check_cookie
0x140008806  add     rsp, 48h
0x14000880a  pop     r15
0x14000880c  pop     r14
0x14000880e  pop     r13
0x140008810  pop     r12
0x140008812  pop     rdi
0x140008813  pop     rsi
0x140008814  pop     rbp
0x140008815  pop     rbx
0x140008816  retn
```
