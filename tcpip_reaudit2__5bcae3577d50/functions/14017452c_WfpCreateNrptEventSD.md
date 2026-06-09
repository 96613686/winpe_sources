# WfpCreateNrptEventSD

- ea: `0x14017452c`
- end: `0x140174921`
- name: `WfpCreateNrptEventSD`
- size: `1013`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140176890`

## callees

- `0x14001b520`
- `0x1400541c0`
- `0x140055a20`
- `0x1400be690`
- `0x14017452c`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14017485d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14017485d`
- `ntoskrnl!RtlCreateAcl` at `0x1401747a6`
- `ntoskrnl!RtlCreateAcl` at `0x1401747a6`
- `ntoskrnl!RtlLengthSid` at `0x14017474a`
- `ntoskrnl!RtlLengthSid` at `0x14017475b`
- `ntoskrnl!RtlLengthSid` at `0x14017476c`
- `ntoskrnl!RtlLengthSid` at `0x14017474a`
- `ntoskrnl!RtlLengthSid` at `0x14017475b`
- `ntoskrnl!RtlLengthSid` at `0x14017476c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140174839`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140174839`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401747d3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140174800`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140174821`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401747d3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140174800`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140174821`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401745e9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174605`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017461d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174635`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017464d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174665`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401746c1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017471d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174735`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401745e9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174605`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017461d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174635`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017464d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174665`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401746c1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017471d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140174735`
- `ntoskrnl!RtlInitializeSid` at `0x1401745d8`
- `ntoskrnl!RtlInitializeSid` at `0x1401746b0`
- `ntoskrnl!RtlInitializeSid` at `0x14017470c`
- `ntoskrnl!RtlInitializeSid` at `0x1401745d8`
- `ntoskrnl!RtlInitializeSid` at `0x1401746b0`
- `ntoskrnl!RtlInitializeSid` at `0x14017470c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401745a4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14017467a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401746d6`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401745a4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14017467a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401746d6`

## string_xrefs

- `0x1401747e3`: `RtlAddAccessAllowedAce`
- `0x140174849`: `RtlCreateSecurityDescriptor`
- `0x14017486d`: `RtlSetDaclSecurityDescriptor`
- `0x1401748f1`: `WfpCreateNrptEventSD`
- `0x1401747b6`: `RtlCreateAcl`

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
0x14017452c  push    rbp
0x14017452e  push    rbx
0x14017452f  push    rsi
0x140174530  push    rdi
0x140174531  push    r12
0x140174533  push    r13
0x140174535  push    r14
0x140174537  push    r15
0x140174539  mov     rbp, rsp
0x14017453c  sub     rsp, 68h
0x140174540  mov     rax, cs:__security_cookie
0x140174547  xor     rax, rsp
0x14017454a  mov     [rbp+var_18], rax
0x14017454e  xor     r15d, r15d
0x140174551  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x140174557  mov     r13, rcx
0x14017455a  mov     [rcx], r15
0x14017455d  mov     r12d, 6E707641h
0x140174563  mov     dword ptr [rbp+IdentifierAuthority.Value], r15d
0x140174567  lea     r8, [rbp+SecurityDescriptor]
0x14017456b  mov     [rbp+Sid], r15
0x14017456f  lea     ecx, [r15+48h]
0x140174573  mov     [rbp+var_48], r15
0x140174577  mov     edx, r12d
0x14017457a  mov     [rbp+var_38], r15
0x14017457e  mov     r14d, r15d
0x140174581  mov     [rbp+Acl], r15
0x140174585  mov     edi, r15d
0x140174588  mov     [rbp+SecurityDescriptor], r15
0x14017458c  call    WfpPoolAllocNonPaged
0x140174591  mov     rsi, [rbp+SecurityDescriptor]
0x140174595  mov     rbx, rax
0x140174598  test    rax, rax
0x14017459b  jnz     loc_1401748DE
0x1401745a1  lea     ecx, [rax+6]; SubAuthorityCount
0x1401745a4  call    cs:__imp_RtlLengthRequiredSid
0x1401745ab  nop     dword ptr [rax+rax+00h]
0x1401745b0  mov     ecx, eax
0x1401745b2  lea     r8, [rbp+Sid]
0x1401745b6  mov     edx, r12d
0x1401745b9  call    WfpPoolAllocNonPaged
0x1401745be  mov     r12, [rbp+Sid]
0x1401745c2  mov     rbx, rax
0x1401745c5  test    rax, rax
0x1401745c8  jnz     loc_1401748B4
0x1401745ce  mov     r8b, 6; SubAuthorityCount
0x1401745d1  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1401745d5  mov     rcx, r12; Sid
0x1401745d8  call    cs:__imp_RtlInitializeSid
0x1401745df  nop     dword ptr [rax+rax+00h]
0x1401745e4  xor     edx, edx; SubAuthority
0x1401745e6  mov     rcx, r12; Sid
0x1401745e9  call    cs:__imp_RtlSubAuthoritySid
0x1401745f0  nop     dword ptr [rax+rax+00h]
0x1401745f5  lea     r14d, [r15+1]
0x1401745f9  mov     rcx, r12; Sid
0x1401745fc  mov     edx, r14d; SubAuthority
0x1401745ff  mov     dword ptr [rax], 50h ; 'P'
0x140174605  call    cs:__imp_RtlSubAuthoritySid
0x14017460c  nop     dword ptr [rax+rax+00h]
0x140174611  lea     edx, [rbx+2]; SubAuthority
0x140174614  mov     rcx, r12; Sid
0x140174617  mov     dword ptr [rax], 333AA847h
0x14017461d  call    cs:__imp_RtlSubAuthoritySid
0x140174624  nop     dword ptr [rax+rax+00h]
0x140174629  lea     edx, [rbx+3]; SubAuthority
0x14017462c  mov     rcx, r12; Sid
0x14017462f  mov     dword ptr [rax], 34726F59h
0x140174635  call    cs:__imp_RtlSubAuthoritySid
0x14017463c  nop     dword ptr [rax+rax+00h]
0x140174641  lea     edx, [rbx+4]; SubAuthority
0x140174644  mov     rcx, r12; Sid
0x140174647  mov     dword ptr [rax], 33761ECDh
0x14017464d  call    cs:__imp_RtlSubAuthoritySid
0x140174654  nop     dword ptr [rax+rax+00h]
0x140174659  lea     edx, [rbx+5]; SubAuthority
0x14017465c  mov     rcx, r12; Sid
0x14017465f  mov     dword ptr [rax], 44465FF6h
0x140174665  call    cs:__imp_RtlSubAuthoritySid
0x14017466c  nop     dword ptr [rax+rax+00h]
0x140174671  mov     ecx, r14d; SubAuthorityCount
0x140174674  mov     dword ptr [rax], 8E5F6DBAh
0x14017467a  call    cs:__imp_RtlLengthRequiredSid
0x140174681  nop     dword ptr [rax+rax+00h]
0x140174686  mov     ecx, eax
0x140174688  lea     r8, [rbp+var_48]
0x14017468c  mov     edx, 6E707641h
0x140174691  call    WfpPoolAllocNonPaged
0x140174696  mov     rbx, rax
0x140174699  test    rax, rax
0x14017469c  jnz     loc_1401748B0
0x1401746a2  mov     r8b, r14b; SubAuthorityCount
0x1401746a5  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1401746a9  mov     r14, [rbp+var_48]
0x1401746ad  mov     rcx, r14; Sid
0x1401746b0  call    cs:__imp_RtlInitializeSid
0x1401746b7  nop     dword ptr [rax+rax+00h]
0x1401746bc  xor     edx, edx; SubAuthority
0x1401746be  mov     rcx, r14; Sid
0x1401746c1  call    cs:__imp_RtlSubAuthoritySid
0x1401746c8  nop     dword ptr [rax+rax+00h]
0x1401746cd  lea     ecx, [rbx+2]; SubAuthorityCount
0x1401746d0  mov     dword ptr [rax], 12h
0x1401746d6  call    cs:__imp_RtlLengthRequiredSid
0x1401746dd  nop     dword ptr [rax+rax+00h]
0x1401746e2  mov     ecx, eax
0x1401746e4  lea     r8, [rbp+var_38]
0x1401746e8  mov     edx, 6E707641h
0x1401746ed  call    WfpPoolAllocNonPaged
0x1401746f2  mov     r15, [rbp+var_38]
0x1401746f6  mov     rbx, rax
0x1401746f9  test    rax, rax
0x1401746fc  jnz     loc_1401748A0
0x140174702  mov     r8b, 2; SubAuthorityCount
0x140174705  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140174709  mov     rcx, r15; Sid
0x14017470c  call    cs:__imp_RtlInitializeSid
0x140174713  nop     dword ptr [rax+rax+00h]
0x140174718  xor     edx, edx; SubAuthority
0x14017471a  mov     rcx, r15; Sid
0x14017471d  call    cs:__imp_RtlSubAuthoritySid
0x140174724  nop     dword ptr [rax+rax+00h]
0x140174729  lea     edx, [rdi+1]; SubAuthority
0x14017472c  mov     rcx, r15; Sid
0x14017472f  mov     dword ptr [rax], 20h ; ' '
0x140174735  call    cs:__imp_RtlSubAuthoritySid
0x14017473c  nop     dword ptr [rax+rax+00h]
0x140174741  mov     rcx, r15; Sid
0x140174744  mov     dword ptr [rax], 220h
0x14017474a  call    cs:__imp_RtlLengthSid
0x140174751  nop     dword ptr [rax+rax+00h]
0x140174756  mov     rcx, r14; Sid
0x140174759  mov     edi, eax
0x14017475b  call    cs:__imp_RtlLengthSid
0x140174762  nop     dword ptr [rax+rax+00h]
0x140174767  mov     rcx, r12; Sid
0x14017476a  add     edi, eax
0x14017476c  call    cs:__imp_RtlLengthSid
0x140174773  nop     dword ptr [rax+rax+00h]
0x140174778  lea     r8, [rbp+Acl]
0x14017477c  mov     edx, 6E707641h
0x140174781  add     eax, 20h ; ' '
0x140174784  add     edi, eax
0x140174786  mov     ecx, edi
0x140174788  call    WfpPoolAllocNonPaged
0x14017478d  mov     rbx, rax
0x140174790  test    rax, rax
0x140174793  jnz     loc_14017489C
0x140174799  mov     edx, edi; AclLength
0x14017479b  lea     r8d, [rax+2]; AclRevision
0x14017479f  mov     rdi, [rbp+Acl]
0x1401747a3  mov     rcx, rdi; Acl
0x1401747a6  call    cs:__imp_RtlCreateAcl
0x1401747ad  nop     dword ptr [rax+rax+00h]
0x1401747b2  test    eax, eax
0x1401747b4  jns     short loc_1401747C2
0x1401747b6  lea     rdx, aRtlcreateacl; "RtlCreateAcl"
0x1401747bd  jmp     loc_140174874
0x1401747c2  mov     r9, r12; Sid
0x1401747c5  mov     edx, 2; AceRevision
0x1401747ca  mov     r8d, 10000000h; AccessMask
0x1401747d0  mov     rcx, rdi; Acl
0x1401747d3  call    cs:__imp_RtlAddAccessAllowedAce
0x1401747da  nop     dword ptr [rax+rax+00h]
0x1401747df  test    eax, eax
0x1401747e1  jns     short loc_1401747EF
0x1401747e3  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAce"
0x1401747ea  jmp     loc_140174874
0x1401747ef  mov     r9, r14; Sid
0x1401747f2  mov     edx, 2; AceRevision
0x1401747f7  mov     r8d, 10000000h; AccessMask
0x1401747fd  mov     rcx, rdi; Acl
0x140174800  call    cs:__imp_RtlAddAccessAllowedAce
0x140174807  nop     dword ptr [rax+rax+00h]
0x14017480c  test    eax, eax
0x14017480e  js      short loc_1401747E3
0x140174810  mov     r9, r15; Sid
0x140174813  mov     edx, 2; AceRevision
0x140174818  mov     r8d, 10000000h; AccessMask
0x14017481e  mov     rcx, rdi; Acl
0x140174821  call    cs:__imp_RtlAddAccessAllowedAce
0x140174828  nop     dword ptr [rax+rax+00h]
0x14017482d  test    eax, eax
0x14017482f  js      short loc_1401747E3
0x140174831  mov     edx, 1; Revision
0x140174836  mov     rcx, rsi; SecurityDescriptor
0x140174839  call    cs:__imp_RtlCreateSecurityDescriptor
0x140174840  nop     dword ptr [rax+rax+00h]
0x140174845  test    eax, eax
0x140174847  jns     short loc_140174852
0x140174849  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x140174850  jmp     short loc_140174874
0x140174852  xor     r9d, r9d; DaclDefaulted
0x140174855  mov     r8, rdi; Dacl
0x140174858  mov     dl, 1; DaclPresent
0x14017485a  mov     rcx, rsi; SecurityDescriptor
0x14017485d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140174864  nop     dword ptr [rax+rax+00h]
0x140174869  test    eax, eax
0x14017486b  jns     short loc_140174886
0x14017486d  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x140174874  mov     r8d, eax
0x140174877  call    WfpReportSysErrorAsNtStatus
0x14017487c  mov     rbx, rax
0x14017487f  test    rax, rax
0x140174882  jz      short loc_140174900
0x140174884  jmp     short loc_1401748A0
0x140174886  mov     [rsi+40h], r15
0x14017488a  mov     [rsi+30h], r12
0x14017488e  mov     [rsi+38h], r14
0x140174892  mov     [rsi+28h], rdi
0x140174896  mov     [r13+0], rsi
0x14017489a  jmp     short loc_140174900
0x14017489c  mov     rdi, [rbp+Acl]
0x1401748a0  test    r15, r15
0x1401748a3  jz      short loc_1401748B4
0x1401748a5  lea     rcx, [rbp+var_38]
0x1401748a9  call    WfpPoolFree
0x1401748ae  jmp     short loc_1401748B4
0x1401748b0  mov     r14, [rbp+var_48]
0x1401748b4  test    r12, r12
0x1401748b7  jz      short loc_1401748C2
0x1401748b9  lea     rcx, [rbp+Sid]
0x1401748bd  call    WfpPoolFree
0x1401748c2  test    r14, r14
0x1401748c5  jz      short loc_1401748D0
0x1401748c7  lea     rcx, [rbp+var_48]
0x1401748cb  call    WfpPoolFree
0x1401748d0  test    rdi, rdi
0x1401748d3  jz      short loc_1401748DE
0x1401748d5  lea     rcx, [rbp+Acl]
0x1401748d9  call    WfpPoolFree
0x1401748de  test    rsi, rsi
0x1401748e1  jz      short loc_1401748EC
0x1401748e3  lea     rcx, [rbp+SecurityDescriptor]
0x1401748e7  call    WfpPoolFree
0x1401748ec  test    rbx, rbx
0x1401748ef  jz      short loc_140174900
0x1401748f1  lea     rdx, aWfpcreatenrpte; "WfpCreateNrptEventSD"
0x1401748f8  mov     rcx, rbx
0x1401748fb  call    WfpReportError
0x140174900  mov     rax, rbx
0x140174903  mov     rcx, [rbp+var_18]
0x140174907  xor     rcx, rsp; StackCookie
0x14017490a  call    __security_check_cookie
0x14017490f  add     rsp, 68h
0x140174913  pop     r15
0x140174915  pop     r14
0x140174917  pop     r13
0x140174919  pop     r12
0x14017491b  pop     rdi
0x14017491c  pop     rsi
0x14017491d  pop     rbx
0x14017491e  pop     rbp
0x14017491f  retn
```
