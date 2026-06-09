# WfpCreateNrptEventSD

- ea: `0x1401760ec`
- end: `0x1401764e1`
- name: `WfpCreateNrptEventSD`
- size: `1013`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140178450`

## callees

- `0x140014a90`
- `0x1400162f0`
- `0x1400a1330`
- `0x1400c7fe0`
- `0x1401760ec`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14017641d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14017641d`
- `ntoskrnl!RtlCreateAcl` at `0x140176366`
- `ntoskrnl!RtlCreateAcl` at `0x140176366`
- `ntoskrnl!RtlLengthSid` at `0x14017630a`
- `ntoskrnl!RtlLengthSid` at `0x14017631b`
- `ntoskrnl!RtlLengthSid` at `0x14017632c`
- `ntoskrnl!RtlLengthSid` at `0x14017630a`
- `ntoskrnl!RtlLengthSid` at `0x14017631b`
- `ntoskrnl!RtlLengthSid` at `0x14017632c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401763f9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1401763f9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140176393`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401763c0`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401763e1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140176393`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401763c0`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401763e1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401761a9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401761c5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401761dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401761f5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017620d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140176225`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140176281`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401762dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401762f5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401761a9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401761c5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401761dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401761f5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14017620d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140176225`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140176281`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401762dd`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401762f5`
- `ntoskrnl!RtlInitializeSid` at `0x140176198`
- `ntoskrnl!RtlInitializeSid` at `0x140176270`
- `ntoskrnl!RtlInitializeSid` at `0x1401762cc`
- `ntoskrnl!RtlInitializeSid` at `0x140176198`
- `ntoskrnl!RtlInitializeSid` at `0x140176270`
- `ntoskrnl!RtlInitializeSid` at `0x1401762cc`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140176164`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14017623a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140176296`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140176164`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14017623a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140176296`

## string_xrefs

- `0x1401763a3`: `RtlAddAccessAllowedAce`
- `0x140176376`: `RtlCreateAcl`
- `0x1401764b1`: `WfpCreateNrptEventSD`
- `0x14017642d`: `RtlSetDaclSecurityDescriptor`
- `0x140176409`: `RtlCreateSecurityDescriptor`

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
0x1401760ec  push    rbp
0x1401760ee  push    rbx
0x1401760ef  push    rsi
0x1401760f0  push    rdi
0x1401760f1  push    r12
0x1401760f3  push    r13
0x1401760f5  push    r14
0x1401760f7  push    r15
0x1401760f9  mov     rbp, rsp
0x1401760fc  sub     rsp, 68h
0x140176100  mov     rax, cs:__security_cookie
0x140176107  xor     rax, rsp
0x14017610a  mov     [rbp+var_18], rax
0x14017610e  xor     r15d, r15d
0x140176111  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x140176117  mov     r13, rcx
0x14017611a  mov     [rcx], r15
0x14017611d  mov     r12d, 6E707641h
0x140176123  mov     dword ptr [rbp+IdentifierAuthority.Value], r15d
0x140176127  lea     r8, [rbp+SecurityDescriptor]
0x14017612b  mov     [rbp+Sid], r15
0x14017612f  lea     ecx, [r15+48h]
0x140176133  mov     [rbp+var_48], r15
0x140176137  mov     edx, r12d
0x14017613a  mov     [rbp+var_38], r15
0x14017613e  mov     r14d, r15d
0x140176141  mov     [rbp+Acl], r15
0x140176145  mov     edi, r15d
0x140176148  mov     [rbp+SecurityDescriptor], r15
0x14017614c  call    WfpPoolAllocNonPaged
0x140176151  mov     rsi, [rbp+SecurityDescriptor]
0x140176155  mov     rbx, rax
0x140176158  test    rax, rax
0x14017615b  jnz     loc_14017649E
0x140176161  lea     ecx, [rax+6]; SubAuthorityCount
0x140176164  call    cs:__imp_RtlLengthRequiredSid
0x14017616b  nop     dword ptr [rax+rax+00h]
0x140176170  mov     ecx, eax
0x140176172  lea     r8, [rbp+Sid]
0x140176176  mov     edx, r12d
0x140176179  call    WfpPoolAllocNonPaged
0x14017617e  mov     r12, [rbp+Sid]
0x140176182  mov     rbx, rax
0x140176185  test    rax, rax
0x140176188  jnz     loc_140176474
0x14017618e  mov     r8b, 6; SubAuthorityCount
0x140176191  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140176195  mov     rcx, r12; Sid
0x140176198  call    cs:__imp_RtlInitializeSid
0x14017619f  nop     dword ptr [rax+rax+00h]
0x1401761a4  xor     edx, edx; SubAuthority
0x1401761a6  mov     rcx, r12; Sid
0x1401761a9  call    cs:__imp_RtlSubAuthoritySid
0x1401761b0  nop     dword ptr [rax+rax+00h]
0x1401761b5  lea     r14d, [r15+1]
0x1401761b9  mov     rcx, r12; Sid
0x1401761bc  mov     edx, r14d; SubAuthority
0x1401761bf  mov     dword ptr [rax], 50h ; 'P'
0x1401761c5  call    cs:__imp_RtlSubAuthoritySid
0x1401761cc  nop     dword ptr [rax+rax+00h]
0x1401761d1  lea     edx, [rbx+2]; SubAuthority
0x1401761d4  mov     rcx, r12; Sid
0x1401761d7  mov     dword ptr [rax], 333AA847h
0x1401761dd  call    cs:__imp_RtlSubAuthoritySid
0x1401761e4  nop     dword ptr [rax+rax+00h]
0x1401761e9  lea     edx, [rbx+3]; SubAuthority
0x1401761ec  mov     rcx, r12; Sid
0x1401761ef  mov     dword ptr [rax], 34726F59h
0x1401761f5  call    cs:__imp_RtlSubAuthoritySid
0x1401761fc  nop     dword ptr [rax+rax+00h]
0x140176201  lea     edx, [rbx+4]; SubAuthority
0x140176204  mov     rcx, r12; Sid
0x140176207  mov     dword ptr [rax], 33761ECDh
0x14017620d  call    cs:__imp_RtlSubAuthoritySid
0x140176214  nop     dword ptr [rax+rax+00h]
0x140176219  lea     edx, [rbx+5]; SubAuthority
0x14017621c  mov     rcx, r12; Sid
0x14017621f  mov     dword ptr [rax], 44465FF6h
0x140176225  call    cs:__imp_RtlSubAuthoritySid
0x14017622c  nop     dword ptr [rax+rax+00h]
0x140176231  mov     ecx, r14d; SubAuthorityCount
0x140176234  mov     dword ptr [rax], 8E5F6DBAh
0x14017623a  call    cs:__imp_RtlLengthRequiredSid
0x140176241  nop     dword ptr [rax+rax+00h]
0x140176246  mov     ecx, eax
0x140176248  lea     r8, [rbp+var_48]
0x14017624c  mov     edx, 6E707641h
0x140176251  call    WfpPoolAllocNonPaged
0x140176256  mov     rbx, rax
0x140176259  test    rax, rax
0x14017625c  jnz     loc_140176470
0x140176262  mov     r8b, r14b; SubAuthorityCount
0x140176265  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140176269  mov     r14, [rbp+var_48]
0x14017626d  mov     rcx, r14; Sid
0x140176270  call    cs:__imp_RtlInitializeSid
0x140176277  nop     dword ptr [rax+rax+00h]
0x14017627c  xor     edx, edx; SubAuthority
0x14017627e  mov     rcx, r14; Sid
0x140176281  call    cs:__imp_RtlSubAuthoritySid
0x140176288  nop     dword ptr [rax+rax+00h]
0x14017628d  lea     ecx, [rbx+2]; SubAuthorityCount
0x140176290  mov     dword ptr [rax], 12h
0x140176296  call    cs:__imp_RtlLengthRequiredSid
0x14017629d  nop     dword ptr [rax+rax+00h]
0x1401762a2  mov     ecx, eax
0x1401762a4  lea     r8, [rbp+var_38]
0x1401762a8  mov     edx, 6E707641h
0x1401762ad  call    WfpPoolAllocNonPaged
0x1401762b2  mov     r15, [rbp+var_38]
0x1401762b6  mov     rbx, rax
0x1401762b9  test    rax, rax
0x1401762bc  jnz     loc_140176460
0x1401762c2  mov     r8b, 2; SubAuthorityCount
0x1401762c5  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1401762c9  mov     rcx, r15; Sid
0x1401762cc  call    cs:__imp_RtlInitializeSid
0x1401762d3  nop     dword ptr [rax+rax+00h]
0x1401762d8  xor     edx, edx; SubAuthority
0x1401762da  mov     rcx, r15; Sid
0x1401762dd  call    cs:__imp_RtlSubAuthoritySid
0x1401762e4  nop     dword ptr [rax+rax+00h]
0x1401762e9  lea     edx, [rdi+1]; SubAuthority
0x1401762ec  mov     rcx, r15; Sid
0x1401762ef  mov     dword ptr [rax], 20h ; ' '
0x1401762f5  call    cs:__imp_RtlSubAuthoritySid
0x1401762fc  nop     dword ptr [rax+rax+00h]
0x140176301  mov     rcx, r15; Sid
0x140176304  mov     dword ptr [rax], 220h
0x14017630a  call    cs:__imp_RtlLengthSid
0x140176311  nop     dword ptr [rax+rax+00h]
0x140176316  mov     rcx, r14; Sid
0x140176319  mov     edi, eax
0x14017631b  call    cs:__imp_RtlLengthSid
0x140176322  nop     dword ptr [rax+rax+00h]
0x140176327  mov     rcx, r12; Sid
0x14017632a  add     edi, eax
0x14017632c  call    cs:__imp_RtlLengthSid
0x140176333  nop     dword ptr [rax+rax+00h]
0x140176338  lea     r8, [rbp+Acl]
0x14017633c  mov     edx, 6E707641h
0x140176341  add     eax, 20h ; ' '
0x140176344  add     edi, eax
0x140176346  mov     ecx, edi
0x140176348  call    WfpPoolAllocNonPaged
0x14017634d  mov     rbx, rax
0x140176350  test    rax, rax
0x140176353  jnz     loc_14017645C
0x140176359  mov     edx, edi; AclLength
0x14017635b  lea     r8d, [rax+2]; AclRevision
0x14017635f  mov     rdi, [rbp+Acl]
0x140176363  mov     rcx, rdi; Acl
0x140176366  call    cs:__imp_RtlCreateAcl
0x14017636d  nop     dword ptr [rax+rax+00h]
0x140176372  test    eax, eax
0x140176374  jns     short loc_140176382
0x140176376  lea     rdx, aRtlcreateacl; "RtlCreateAcl"
0x14017637d  jmp     loc_140176434
0x140176382  mov     r9, r12; Sid
0x140176385  mov     edx, 2; AceRevision
0x14017638a  mov     r8d, 10000000h; AccessMask
0x140176390  mov     rcx, rdi; Acl
0x140176393  call    cs:__imp_RtlAddAccessAllowedAce
0x14017639a  nop     dword ptr [rax+rax+00h]
0x14017639f  test    eax, eax
0x1401763a1  jns     short loc_1401763AF
0x1401763a3  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAce"
0x1401763aa  jmp     loc_140176434
0x1401763af  mov     r9, r14; Sid
0x1401763b2  mov     edx, 2; AceRevision
0x1401763b7  mov     r8d, 10000000h; AccessMask
0x1401763bd  mov     rcx, rdi; Acl
0x1401763c0  call    cs:__imp_RtlAddAccessAllowedAce
0x1401763c7  nop     dword ptr [rax+rax+00h]
0x1401763cc  test    eax, eax
0x1401763ce  js      short loc_1401763A3
0x1401763d0  mov     r9, r15; Sid
0x1401763d3  mov     edx, 2; AceRevision
0x1401763d8  mov     r8d, 10000000h; AccessMask
0x1401763de  mov     rcx, rdi; Acl
0x1401763e1  call    cs:__imp_RtlAddAccessAllowedAce
0x1401763e8  nop     dword ptr [rax+rax+00h]
0x1401763ed  test    eax, eax
0x1401763ef  js      short loc_1401763A3
0x1401763f1  mov     edx, 1; Revision
0x1401763f6  mov     rcx, rsi; SecurityDescriptor
0x1401763f9  call    cs:__imp_RtlCreateSecurityDescriptor
0x140176400  nop     dword ptr [rax+rax+00h]
0x140176405  test    eax, eax
0x140176407  jns     short loc_140176412
0x140176409  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x140176410  jmp     short loc_140176434
0x140176412  xor     r9d, r9d; DaclDefaulted
0x140176415  mov     r8, rdi; Dacl
0x140176418  mov     dl, 1; DaclPresent
0x14017641a  mov     rcx, rsi; SecurityDescriptor
0x14017641d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140176424  nop     dword ptr [rax+rax+00h]
0x140176429  test    eax, eax
0x14017642b  jns     short loc_140176446
0x14017642d  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x140176434  mov     r8d, eax
0x140176437  call    WfpReportSysErrorAsNtStatus
0x14017643c  mov     rbx, rax
0x14017643f  test    rax, rax
0x140176442  jz      short loc_1401764C0
0x140176444  jmp     short loc_140176460
0x140176446  mov     [rsi+40h], r15
0x14017644a  mov     [rsi+30h], r12
0x14017644e  mov     [rsi+38h], r14
0x140176452  mov     [rsi+28h], rdi
0x140176456  mov     [r13+0], rsi
0x14017645a  jmp     short loc_1401764C0
0x14017645c  mov     rdi, [rbp+Acl]
0x140176460  test    r15, r15
0x140176463  jz      short loc_140176474
0x140176465  lea     rcx, [rbp+var_38]
0x140176469  call    WfpPoolFree
0x14017646e  jmp     short loc_140176474
0x140176470  mov     r14, [rbp+var_48]
0x140176474  test    r12, r12
0x140176477  jz      short loc_140176482
0x140176479  lea     rcx, [rbp+Sid]
0x14017647d  call    WfpPoolFree
0x140176482  test    r14, r14
0x140176485  jz      short loc_140176490
0x140176487  lea     rcx, [rbp+var_48]
0x14017648b  call    WfpPoolFree
0x140176490  test    rdi, rdi
0x140176493  jz      short loc_14017649E
0x140176495  lea     rcx, [rbp+Acl]
0x140176499  call    WfpPoolFree
0x14017649e  test    rsi, rsi
0x1401764a1  jz      short loc_1401764AC
0x1401764a3  lea     rcx, [rbp+SecurityDescriptor]
0x1401764a7  call    WfpPoolFree
0x1401764ac  test    rbx, rbx
0x1401764af  jz      short loc_1401764C0
0x1401764b1  lea     rdx, aWfpcreatenrpte; "WfpCreateNrptEventSD"
0x1401764b8  mov     rcx, rbx
0x1401764bb  call    WfpReportError
0x1401764c0  mov     rax, rbx
0x1401764c3  mov     rcx, [rbp+var_18]
0x1401764c7  xor     rcx, rsp; StackCookie
0x1401764ca  call    __security_check_cookie
0x1401764cf  add     rsp, 68h
0x1401764d3  pop     r15
0x1401764d5  pop     r14
0x1401764d7  pop     r13
0x1401764d9  pop     r12
0x1401764db  pop     rdi
0x1401764dc  pop     rsi
0x1401764dd  pop     rbx
0x1401764de  pop     rbp
0x1401764df  retn
```
