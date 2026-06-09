# WfpCreateNrptEventSD

- ea: `0x1401743ec`
- end: `0x1401747e1`
- name: `WfpCreateNrptEventSD`
- size: `1013`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140176750`

## callees

- `0x14001b280`
- `0x140053f20`
- `0x140055780`
- `0x1400be890`
- `0x1401743ec`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14017471d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14017471d`
- `ntoskrnl!RtlCreateAcl` at `0x140174666`
- `ntoskrnl!RtlCreateAcl` at `0x140174666`
- `ntoskrnl!RtlLengthSid` at `0x14017460a`
- `ntoskrnl!RtlLengthSid` at `0x14017461b`
- `ntoskrnl!RtlLengthSid` at `0x14017462c`
- `ntoskrnl!RtlLengthSid` at `0x14017460a`
- `ntoskrnl!RtlLengthSid` at `0x14017461b`
- `ntoskrnl!RtlLengthSid` at `0x14017462c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401746f9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401746f9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140174693`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401746c0`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401746e1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140174693`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401746c0`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401746e1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401744a9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401744c5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401744dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401744f5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017450d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174525`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174581`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401745dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401745f5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401744a9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401744c5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401744dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401744f5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017450d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174525`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174581`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401745dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401745f5`
- `ntoskrnl!RtlInitializeSid` at `0x140174498`
- `ntoskrnl!RtlInitializeSid` at `0x140174570`
- `ntoskrnl!RtlInitializeSid` at `0x1401745cc`
- `ntoskrnl!RtlInitializeSid` at `0x140174498`
- `ntoskrnl!RtlInitializeSid` at `0x140174570`
- `ntoskrnl!RtlInitializeSid` at `0x1401745cc`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140174464`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14017453a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140174596`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140174464`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14017453a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140174596`

## string_xrefs

- `0x1401747b1`: `WfpCreateNrptEventSD`
- `0x140174676`: `RtlCreateAcl`
- `0x1401746a3`: `RtlAddAccessAllowedAce`
- `0x140174709`: `RtlCreateSecurityDescriptor`
- `0x14017472d`: `RtlSetDaclSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall WfpCreateNrptEventSD(_QWORD *a1)
{
  PSID v2; // r14
  struct _ACL *v3; // rdi
  __int64 v4; // rax
  _QWORD *v5; // rsi
  __int64 v6; // rbx
  ULONG v7; // eax
  __int64 v8; // rax
  PSID v9; // r12
  ULONG v10; // eax
  ULONG v11; // eax
  __int64 v12; // rax
  PSID v13; // r15
  ULONG v14; // edi
  ULONG v15; // edi
  ULONG v16; // edi
  ULONG v17; // edx
  NTSTATUS v18; // eax
  __int64 v19; // rcx
  const char *v20; // rdx
  PSID v22; // [rsp+20h] [rbp-48h] BYREF
  PACL Acl; // [rsp+28h] [rbp-40h] BYREF
  PSID v24; // [rsp+30h] [rbp-38h] BYREF
  PSID Sid; // [rsp+38h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+48h] [rbp-20h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *a1 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  Sid = 0;
  v22 = 0;
  v24 = 0;
  v2 = 0;
  Acl = 0;
  v3 = 0;
  SecurityDescriptor = 0;
  v4 = WfpPoolAllocNonPaged(72, 1852864065, &SecurityDescriptor);
  v5 = SecurityDescriptor;
  v6 = v4;
  if ( v4 )
  {
LABEL_29:
    if ( v5 )
      WfpPoolFree(&SecurityDescriptor);
    if ( v6 )
      WfpReportError(v6, "WfpCreateNrptEventSD");
    return v6;
  }
  v7 = RtlLengthRequiredSid(6u);
  v8 = WfpPoolAllocNonPaged(v7, 1852864065, &Sid);
  v9 = Sid;
  v6 = v8;
  if ( v8 )
  {
LABEL_23:
    if ( v9 )
      WfpPoolFree(&Sid);
    if ( v2 )
      WfpPoolFree(&v22);
    if ( v3 )
      WfpPoolFree(&Acl);
    goto LABEL_29;
  }
  RtlInitializeSid(Sid, &IdentifierAuthority, 6u);
  *RtlSubAuthoritySid(v9, 0) = 80;
  *RtlSubAuthoritySid(v9, 1u) = 859482183;
  *RtlSubAuthoritySid(v9, 2u) = 879914841;
  *RtlSubAuthoritySid(v9, 3u) = 863379149;
  *RtlSubAuthoritySid(v9, 4u) = 1145462774;
  *RtlSubAuthoritySid(v9, 5u) = -1906348614;
  v10 = RtlLengthRequiredSid(1u);
  v6 = WfpPoolAllocNonPaged(v10, 1852864065, &v22);
  if ( v6 )
  {
    v2 = v22;
    goto LABEL_23;
  }
  v2 = v22;
  RtlInitializeSid(v22, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v2, 0) = 18;
  v11 = RtlLengthRequiredSid(2u);
  v12 = WfpPoolAllocNonPaged(v11, 1852864065, &v24);
  v13 = v24;
  v6 = v12;
  if ( v12 )
    goto LABEL_20;
  RtlInitializeSid(v24, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v13, 0) = 32;
  *RtlSubAuthoritySid(v13, 1u) = 544;
  v14 = RtlLengthSid(v13);
  v15 = RtlLengthSid(v2) + v14;
  v16 = RtlLengthSid(v9) + 32 + v15;
  v6 = WfpPoolAllocNonPaged(v16, 1852864065, &Acl);
  if ( v6 )
  {
    v3 = Acl;
LABEL_20:
    if ( v13 )
      WfpPoolFree(&v24);
    goto LABEL_23;
  }
  v17 = v16;
  v3 = Acl;
  v18 = RtlCreateAcl(Acl, v17, 2u);
  if ( v18 >= 0 )
  {
    v18 = RtlAddAccessAllowedAce(v3, 2u, 0x10000000u, v9);
    if ( v18 < 0
      || (v18 = RtlAddAccessAllowedAce(v3, 2u, 0x10000000u, v2), v18 < 0)
      || (v18 = RtlAddAccessAllowedAce(v3, 2u, 0x10000000u, v13), v18 < 0) )
    {
      v20 = "RtlAddAccessAllowedAce";
    }
    else
    {
      v18 = RtlCreateSecurityDescriptor(v5, 1u);
      if ( v18 >= 0 )
      {
        v18 = RtlSetDaclSecurityDescriptor(v5, 1u, v3, 0);
        if ( v18 >= 0 )
        {
          v5[8] = v13;
          v5[6] = v9;
          v5[7] = v2;
          v5[5] = v3;
          *a1 = v5;
          return v6;
        }
        v20 = "RtlSetDaclSecurityDescriptor";
      }
      else
      {
        v20 = "RtlCreateSecurityDescriptor";
      }
    }
  }
  else
  {
    v20 = "RtlCreateAcl";
  }
  v6 = WfpReportSysErrorAsNtStatus(v19, v20, (unsigned int)v18);
  if ( v6 )
    goto LABEL_20;
  return v6;
}

```

## disassembly

```asm
0x1401743ec  push    rbp
0x1401743ee  push    rbx
0x1401743ef  push    rsi
0x1401743f0  push    rdi
0x1401743f1  push    r12
0x1401743f3  push    r13
0x1401743f5  push    r14
0x1401743f7  push    r15
0x1401743f9  mov     rbp, rsp
0x1401743fc  sub     rsp, 68h
0x140174400  mov     rax, cs:__security_cookie
0x140174407  xor     rax, rsp
0x14017440a  mov     [rbp+var_18], rax
0x14017440e  xor     r15d, r15d
0x140174411  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x140174417  mov     r13, rcx
0x14017441a  mov     [rcx], r15
0x14017441d  mov     r12d, 6E707641h
0x140174423  mov     dword ptr [rbp+IdentifierAuthority.Value], r15d
0x140174427  lea     r8, [rbp+SecurityDescriptor]
0x14017442b  mov     [rbp+Sid], r15
0x14017442f  lea     ecx, [r15+48h]
0x140174433  mov     [rbp+var_48], r15
0x140174437  mov     edx, r12d
0x14017443a  mov     [rbp+var_38], r15
0x14017443e  mov     r14d, r15d
0x140174441  mov     [rbp+Acl], r15
0x140174445  mov     edi, r15d
0x140174448  mov     [rbp+SecurityDescriptor], r15
0x14017444c  call    WfpPoolAllocNonPaged
0x140174451  mov     rsi, [rbp+SecurityDescriptor]
0x140174455  mov     rbx, rax
0x140174458  test    rax, rax
0x14017445b  jnz     loc_14017479E
0x140174461  lea     ecx, [rax+6]; SubAuthorityCount
0x140174464  call    cs:__imp_RtlLengthRequiredSid
0x14017446b  nop     dword ptr [rax+rax+00h]
0x140174470  mov     ecx, eax
0x140174472  lea     r8, [rbp+Sid]
0x140174476  mov     edx, r12d
0x140174479  call    WfpPoolAllocNonPaged
0x14017447e  mov     r12, [rbp+Sid]
0x140174482  mov     rbx, rax
0x140174485  test    rax, rax
0x140174488  jnz     loc_140174774
0x14017448e  mov     r8b, 6; SubAuthorityCount
0x140174491  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140174495  mov     rcx, r12; Sid
0x140174498  call    cs:__imp_RtlInitializeSid
0x14017449f  nop     dword ptr [rax+rax+00h]
0x1401744a4  xor     edx, edx; SubAuthority
0x1401744a6  mov     rcx, r12; Sid
0x1401744a9  call    cs:__imp_RtlSubAuthoritySid
0x1401744b0  nop     dword ptr [rax+rax+00h]
0x1401744b5  lea     r14d, [r15+1]
0x1401744b9  mov     rcx, r12; Sid
0x1401744bc  mov     edx, r14d; SubAuthority
0x1401744bf  mov     dword ptr [rax], 50h ; 'P'
0x1401744c5  call    cs:__imp_RtlSubAuthoritySid
0x1401744cc  nop     dword ptr [rax+rax+00h]
0x1401744d1  lea     edx, [rbx+2]; SubAuthority
0x1401744d4  mov     rcx, r12; Sid
0x1401744d7  mov     dword ptr [rax], 333AA847h
0x1401744dd  call    cs:__imp_RtlSubAuthoritySid
0x1401744e4  nop     dword ptr [rax+rax+00h]
0x1401744e9  lea     edx, [rbx+3]; SubAuthority
0x1401744ec  mov     rcx, r12; Sid
0x1401744ef  mov     dword ptr [rax], 34726F59h
0x1401744f5  call    cs:__imp_RtlSubAuthoritySid
0x1401744fc  nop     dword ptr [rax+rax+00h]
0x140174501  lea     edx, [rbx+4]; SubAuthority
0x140174504  mov     rcx, r12; Sid
0x140174507  mov     dword ptr [rax], 33761ECDh
0x14017450d  call    cs:__imp_RtlSubAuthoritySid
0x140174514  nop     dword ptr [rax+rax+00h]
0x140174519  lea     edx, [rbx+5]; SubAuthority
0x14017451c  mov     rcx, r12; Sid
0x14017451f  mov     dword ptr [rax], 44465FF6h
0x140174525  call    cs:__imp_RtlSubAuthoritySid
0x14017452c  nop     dword ptr [rax+rax+00h]
0x140174531  mov     ecx, r14d; SubAuthorityCount
0x140174534  mov     dword ptr [rax], 8E5F6DBAh
0x14017453a  call    cs:__imp_RtlLengthRequiredSid
0x140174541  nop     dword ptr [rax+rax+00h]
0x140174546  mov     ecx, eax
0x140174548  lea     r8, [rbp+var_48]
0x14017454c  mov     edx, 6E707641h
0x140174551  call    WfpPoolAllocNonPaged
0x140174556  mov     rbx, rax
0x140174559  test    rax, rax
0x14017455c  jnz     loc_140174770
0x140174562  mov     r8b, r14b; SubAuthorityCount
0x140174565  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140174569  mov     r14, [rbp+var_48]
0x14017456d  mov     rcx, r14; Sid
0x140174570  call    cs:__imp_RtlInitializeSid
0x140174577  nop     dword ptr [rax+rax+00h]
0x14017457c  xor     edx, edx; SubAuthority
0x14017457e  mov     rcx, r14; Sid
0x140174581  call    cs:__imp_RtlSubAuthoritySid
0x140174588  nop     dword ptr [rax+rax+00h]
0x14017458d  lea     ecx, [rbx+2]; SubAuthorityCount
0x140174590  mov     dword ptr [rax], 12h
0x140174596  call    cs:__imp_RtlLengthRequiredSid
0x14017459d  nop     dword ptr [rax+rax+00h]
0x1401745a2  mov     ecx, eax
0x1401745a4  lea     r8, [rbp+var_38]
0x1401745a8  mov     edx, 6E707641h
0x1401745ad  call    WfpPoolAllocNonPaged
0x1401745b2  mov     r15, [rbp+var_38]
0x1401745b6  mov     rbx, rax
0x1401745b9  test    rax, rax
0x1401745bc  jnz     loc_140174760
0x1401745c2  mov     r8b, 2; SubAuthorityCount
0x1401745c5  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1401745c9  mov     rcx, r15; Sid
0x1401745cc  call    cs:__imp_RtlInitializeSid
0x1401745d3  nop     dword ptr [rax+rax+00h]
0x1401745d8  xor     edx, edx; SubAuthority
0x1401745da  mov     rcx, r15; Sid
0x1401745dd  call    cs:__imp_RtlSubAuthoritySid
0x1401745e4  nop     dword ptr [rax+rax+00h]
0x1401745e9  lea     edx, [rdi+1]; SubAuthority
0x1401745ec  mov     rcx, r15; Sid
0x1401745ef  mov     dword ptr [rax], 20h ; ' '
0x1401745f5  call    cs:__imp_RtlSubAuthoritySid
0x1401745fc  nop     dword ptr [rax+rax+00h]
0x140174601  mov     rcx, r15; Sid
0x140174604  mov     dword ptr [rax], 220h
0x14017460a  call    cs:__imp_RtlLengthSid
0x140174611  nop     dword ptr [rax+rax+00h]
0x140174616  mov     rcx, r14; Sid
0x140174619  mov     edi, eax
0x14017461b  call    cs:__imp_RtlLengthSid
0x140174622  nop     dword ptr [rax+rax+00h]
0x140174627  mov     rcx, r12; Sid
0x14017462a  add     edi, eax
0x14017462c  call    cs:__imp_RtlLengthSid
0x140174633  nop     dword ptr [rax+rax+00h]
0x140174638  lea     r8, [rbp+Acl]
0x14017463c  mov     edx, 6E707641h
0x140174641  add     eax, 20h ; ' '
0x140174644  add     edi, eax
0x140174646  mov     ecx, edi
0x140174648  call    WfpPoolAllocNonPaged
0x14017464d  mov     rbx, rax
0x140174650  test    rax, rax
0x140174653  jnz     loc_14017475C
0x140174659  mov     edx, edi; AclLength
0x14017465b  lea     r8d, [rax+2]; AclRevision
0x14017465f  mov     rdi, [rbp+Acl]
0x140174663  mov     rcx, rdi; Acl
0x140174666  call    cs:__imp_RtlCreateAcl
0x14017466d  nop     dword ptr [rax+rax+00h]
0x140174672  test    eax, eax
0x140174674  jns     short loc_140174682
0x140174676  lea     rdx, aRtlcreateacl; "RtlCreateAcl"
0x14017467d  jmp     loc_140174734
0x140174682  mov     r9, r12; Sid
0x140174685  mov     edx, 2; AceRevision
0x14017468a  mov     r8d, 10000000h; AccessMask
0x140174690  mov     rcx, rdi; Acl
0x140174693  call    cs:__imp_RtlAddAccessAllowedAce
0x14017469a  nop     dword ptr [rax+rax+00h]
0x14017469f  test    eax, eax
0x1401746a1  jns     short loc_1401746AF
0x1401746a3  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAce"
0x1401746aa  jmp     loc_140174734
0x1401746af  mov     r9, r14; Sid
0x1401746b2  mov     edx, 2; AceRevision
0x1401746b7  mov     r8d, 10000000h; AccessMask
0x1401746bd  mov     rcx, rdi; Acl
0x1401746c0  call    cs:__imp_RtlAddAccessAllowedAce
0x1401746c7  nop     dword ptr [rax+rax+00h]
0x1401746cc  test    eax, eax
0x1401746ce  js      short loc_1401746A3
0x1401746d0  mov     r9, r15; Sid
0x1401746d3  mov     edx, 2; AceRevision
0x1401746d8  mov     r8d, 10000000h; AccessMask
0x1401746de  mov     rcx, rdi; Acl
0x1401746e1  call    cs:__imp_RtlAddAccessAllowedAce
0x1401746e8  nop     dword ptr [rax+rax+00h]
0x1401746ed  test    eax, eax
0x1401746ef  js      short loc_1401746A3
0x1401746f1  mov     edx, 1; Revision
0x1401746f6  mov     rcx, rsi; SecurityDescriptor
0x1401746f9  call    cs:__imp_RtlCreateSecurityDescriptor
0x140174700  nop     dword ptr [rax+rax+00h]
0x140174705  test    eax, eax
0x140174707  jns     short loc_140174712
0x140174709  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x140174710  jmp     short loc_140174734
0x140174712  xor     r9d, r9d; DaclDefaulted
0x140174715  mov     r8, rdi; Dacl
0x140174718  mov     dl, 1; DaclPresent
0x14017471a  mov     rcx, rsi; SecurityDescriptor
0x14017471d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140174724  nop     dword ptr [rax+rax+00h]
0x140174729  test    eax, eax
0x14017472b  jns     short loc_140174746
0x14017472d  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x140174734  mov     r8d, eax
0x140174737  call    WfpReportSysErrorAsNtStatus
0x14017473c  mov     rbx, rax
0x14017473f  test    rax, rax
0x140174742  jz      short loc_1401747C0
0x140174744  jmp     short loc_140174760
0x140174746  mov     [rsi+40h], r15
0x14017474a  mov     [rsi+30h], r12
0x14017474e  mov     [rsi+38h], r14
0x140174752  mov     [rsi+28h], rdi
0x140174756  mov     [r13+0], rsi
0x14017475a  jmp     short loc_1401747C0
0x14017475c  mov     rdi, [rbp+Acl]
0x140174760  test    r15, r15
0x140174763  jz      short loc_140174774
0x140174765  lea     rcx, [rbp+var_38]
0x140174769  call    WfpPoolFree
0x14017476e  jmp     short loc_140174774
0x140174770  mov     r14, [rbp+var_48]
0x140174774  test    r12, r12
0x140174777  jz      short loc_140174782
0x140174779  lea     rcx, [rbp+Sid]
0x14017477d  call    WfpPoolFree
0x140174782  test    r14, r14
0x140174785  jz      short loc_140174790
0x140174787  lea     rcx, [rbp+var_48]
0x14017478b  call    WfpPoolFree
0x140174790  test    rdi, rdi
0x140174793  jz      short loc_14017479E
0x140174795  lea     rcx, [rbp+Acl]
0x140174799  call    WfpPoolFree
0x14017479e  test    rsi, rsi
0x1401747a1  jz      short loc_1401747AC
0x1401747a3  lea     rcx, [rbp+SecurityDescriptor]
0x1401747a7  call    WfpPoolFree
0x1401747ac  test    rbx, rbx
0x1401747af  jz      short loc_1401747C0
0x1401747b1  lea     rdx, aWfpcreatenrpte; "WfpCreateNrptEventSD"
0x1401747b8  mov     rcx, rbx
0x1401747bb  call    WfpReportError
0x1401747c0  mov     rax, rbx
0x1401747c3  mov     rcx, [rbp+var_18]
0x1401747c7  xor     rcx, rsp; StackCookie
0x1401747ca  call    __security_check_cookie
0x1401747cf  add     rsp, 68h
0x1401747d3  pop     r15
0x1401747d5  pop     r14
0x1401747d7  pop     r13
0x1401747d9  pop     r12
0x1401747db  pop     rdi
0x1401747dc  pop     rsi
0x1401747dd  pop     rbx
0x1401747de  pop     rbp
0x1401747df  retn
```
