# LdapParsePageControl(ldap_connection *,ldapcontrolW * *,ulong *,berval * *,ulong)

- ea: `0x1800442b0`
- end: `0x180044596`
- name: `?LdapParsePageControl@@YAKPEAUldap_connection@@PEAPEAUldapcontrolW@@PEAKPEAPEAUberval@@K@Z`
- size: `742`
- prototype: `unsigned int __fastcall(struct ldap_connection *, struct ldapcontrolW **, unsigned int *, struct berval **, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f7bc`
- `0x180044f00`
- `0x180044fd0`

## callees

- `0x1800030f0`
- `0x1800037a8`
- `0x180006510`
- `0x180014460`
- `0x18001ce90`
- `0x180020910`
- `0x18002884c`
- `0x180029360`
- `0x18002cb90`
- `0x18002dec0`
- `0x1800442b0`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18004435b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18004435b`

## pseudocode

```c
__int64 __fastcall LdapParsePageControl(
        struct ldap_connection *a1,
        struct ldapcontrolW **a2,
        unsigned int *a3,
        struct berval **a4,
        unsigned int a5)
{
  struct ldapcontrolW **v7; // rsi
  unsigned int v9; // ebx
  struct ldapcontrolW *v10; // r15
  bool v11; // zf
  __int64 v12; // rax
  CLdapBer *v13; // rsi
  int v14; // ecx
  unsigned int Sequence; // eax
  unsigned int v16; // edx
  unsigned int *v17; // rax
  struct berval *v18; // rdi
  void *v19; // rbx
  CHAR *v20; // rax
  void *Src; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v23; // [rsp+70h] [rbp+18h] BYREF

  v7 = a2;
  v9 = 93;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    goto LABEL_43;
  v23 = 0;
  LODWORD(Src) = 0;
  while ( 1 )
  {
    v10 = *v7;
    if ( !*v7 )
      goto LABEL_43;
    if ( a5 )
    {
      if ( a5 != 1 )
        goto LABEL_13;
      v11 = CompareStringA(0x400u, 1u, (PCNZCH)v10->ldctl_oid, -1, "1.2.840.113556.1.4.319", 23) == 2;
    }
    else
    {
      v11 = ldapWStringsIdentical(v10->ldctl_oid, -1, L"1.2.840.113556.1.4.319", -1);
    }
    if ( v11 )
      break;
LABEL_13:
    ++v7;
  }
  v12 = ldapMalloc(872, 1816347212);
  v13 = (CLdapBer *)v12;
  if ( v12 )
  {
    v14 = *((_DWORD *)a1 + 250);
    *(_QWORD *)v12 = 0;
    *(_DWORD *)(v12 + 8) = 0;
    *(_QWORD *)(v12 + 16) = 0;
    *(_QWORD *)(v12 + 836) = 0;
    *(_QWORD *)(v12 + 24) = 0;
    *(_BYTE *)(v12 + 856) = 0;
    *(_DWORD *)(v12 + 864) = 0;
    *(_DWORD *)(v12 + 860) = v14 != 2 ? 0xFDE9 : 0;
    *(_DWORD *)(v12 + 32) = 0;
    Sequence = CLdapBer::HrLoadBer(
                 (CLdapBer *)v12,
                 (const unsigned __int8 *)v10->ldctl_value.bv_val,
                 v10->ldctl_value.bv_len,
                 &v23,
                 1u,
                 0);
    v9 = Sequence;
    if ( Sequence
      || (Sequence = CLdapBer::HrStartReadSequence(v13, 0x30u, 0), (v9 = Sequence) != 0)
      || (Sequence = CLdapBer::HrGetValue(v13, (int *)&Src, 2u, 0), (v9 = Sequence) != 0) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "LdapParsePageControl: loadBer error of 0x%x for 0x%x.\n", Sequence, (_DWORD)a1);
      goto LABEL_37;
    }
    if ( a3 )
      *a3 = (unsigned int)Src;
    if ( a4 )
    {
      Src = 0;
      v17 = (unsigned int *)ldapMalloc(16, 1819689548);
      v18 = (struct berval *)v17;
      if ( !v17 )
      {
        v9 = 90;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
          LDAPClientPrint(0x400000, "LdapParsePageControl: couldn't allocate berval for 0x%x.\n", (_DWORD)a1);
        goto LABEL_37;
      }
      CLdapBer::HrGetBinaryValuePointer(v13, (unsigned __int8 **)&Src, v17, 4u, 0);
      v19 = Src;
      if ( Src )
      {
        v20 = (CHAR *)ldapMalloc(v18->bv_len, 1953383244);
        v18->bv_val = v20;
        if ( !v20 )
        {
          v9 = 90;
          ber_bvfree(v18);
LABEL_37:
          CLdapBer::`scalar deleting destructor'(v13, v16);
          goto LABEL_43;
        }
        memcpy_0(v20, v19, v18->bv_len);
      }
      else
      {
        v18->bv_len = 0;
        v18->bv_val = 0;
      }
      *a4 = v18;
    }
    v9 = 0;
    goto LABEL_37;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
    LDAPClientPrint(0x4000, "LdapParsePageControl: unable to allocate message for 0x%x.\n", (_DWORD)a1);
  v9 = 90;
LABEL_43:
  SetConnectionError(a1, v9);
  return v9;
}

```

## disassembly

```asm
0x1800442b0  mov     [rsp+arg_0], rbx
0x1800442b5  mov     [rsp+arg_18], rbp
0x1800442ba  push    rsi
0x1800442bb  push    rdi
0x1800442bc  push    r13
0x1800442be  push    r14
0x1800442c0  push    r15
0x1800442c2  sub     rsp, 30h
0x1800442c6  xor     r13d, r13d
0x1800442c9  mov     r14, r9
0x1800442cc  mov     rdi, r8
0x1800442cf  mov     rsi, rdx
0x1800442d2  mov     rbp, rcx
0x1800442d5  mov     ebx, 5Dh ; ']'
0x1800442da  test    r8, r8
0x1800442dd  jz      short loc_1800442E2
0x1800442df  mov     [r8], r13d
0x1800442e2  test    r14, r14
0x1800442e5  jz      short loc_1800442EA
0x1800442e7  mov     [r9], r13
0x1800442ea  test    rdx, rdx
0x1800442ed  jz      loc_180044572
0x1800442f3  mov     [rsp+58h+arg_10], r13d
0x1800442f8  mov     dword ptr [rsp+58h+Src], r13d
0x1800442fd  mov     r15, [rsi]
0x180044300  test    r15, r15
0x180044303  jz      loc_180044572
0x180044309  cmp     [rsp+58h+arg_20], r13d
0x180044311  jnz     short loc_18004432D
0x180044313  mov     rcx, [r15]; lpString1
0x180044316  lea     r8, a12840113556143; "1.2.840.113556.1.4.319"
0x18004431d  or      r9d, 0FFFFFFFFh; cchCount2
0x180044321  or      edx, r9d; cchCount1
0x180044324  call    ldapWStringsIdentical
0x180044329  cmp     al, 1
0x18004432b  jmp     short loc_18004436A
0x18004432d  cmp     [rsp+58h+arg_20], 1
0x180044335  jnz     short loc_18004436C
0x180044337  mov     r8, [r15]; lpString1
0x18004433a  lea     rax, Src; "1.2.840.113556.1.4.319"
0x180044341  or      r9d, 0FFFFFFFFh; cchCount1
0x180044345  mov     [rsp+58h+cchCount2], 17h; cchCount2
0x18004434d  mov     ecx, 400h; Locale
0x180044352  mov     [rsp+58h+lpString2], rax; lpString2
0x180044357  lea     edx, [r9+2]; dwCmpFlags
0x18004435b  call    cs:__imp_CompareStringA
0x180044362  nop     dword ptr [rax+rax+00h]
0x180044367  cmp     eax, 2
0x18004436a  jz      short loc_180044372
0x18004436c  add     rsi, 8
0x180044370  jmp     short loc_1800442FD
0x180044372  mov     edx, 6C43424Ch
0x180044377  mov     ecx, 368h
0x18004437c  call    ldapMalloc
0x180044381  mov     rsi, rax
0x180044384  test    rax, rax
0x180044387  jz      loc_18004453E
0x18004438d  mov     ecx, [rbp+3E8h]
0x180044393  lea     r9, [rsp+58h+arg_10]; unsigned int *
0x180044398  mov     [rax], r13
0x18004439b  sub     ecx, 2
0x18004439e  mov     [rax+8], r13d
0x1800443a2  neg     ecx
0x1800443a4  mov     [rax+10h], r13
0x1800443a8  mov     rcx, rsi; this
0x1800443ab  mov     [rax+344h], r13
0x1800443b2  mov     [rax+18h], r13
0x1800443b6  mov     [rax+358h], r13b
0x1800443bd  mov     [rax+360h], r13d
0x1800443c4  sbb     eax, eax
0x1800443c6  and     eax, 0FDE9h
0x1800443cb  mov     byte ptr [rsp+58h+cchCount2], r13b; unsigned __int8
0x1800443d0  mov     [rsi+35Ch], eax
0x1800443d6  mov     [rsi+20h], r13d
0x1800443da  mov     r8d, [r15+8]; unsigned int
0x1800443de  mov     rdx, [r15+10h]; Src
0x1800443e2  mov     byte ptr [rsp+58h+lpString2], 1; unsigned __int8
0x1800443e7  call    ?HrLoadBer@CLdapBer@@QEAAKPEBEKPEAKEE@Z; CLdapBer::HrLoadBer(uchar const *,ulong,ulong *,uchar,uchar)
0x1800443ec  mov     ebx, eax
0x1800443ee  test    eax, eax
0x1800443f0  jz      short loc_180044435
0x1800443f2  cmp     cs:g_fTracingOn, r13d
0x1800443f9  jz      loc_180044534
0x1800443ff  cmp     cs:g_fProviderEnabled, r13d
0x180044406  jz      loc_180044534
0x18004440c  mov     ecx, 400000h
0x180044411  test    cs:g_ulTraceFlags, rcx
0x180044418  jz      loc_180044534
0x18004441e  mov     r9, rbp
0x180044421  lea     rdx, aLdapparsepagec_1; "LdapParsePageControl: loadBer error of "...
0x180044428  mov     r8d, eax
0x18004442b  call    LDAPClientPrint
0x180044430  jmp     loc_180044534
0x180044435  xor     r8d, r8d; unsigned __int8
0x180044438  mov     rcx, rsi; this
0x18004443b  lea     edx, [r8+30h]; unsigned int
0x18004443f  call    ?HrStartReadSequence@CLdapBer@@QEAAKKE@Z; CLdapBer::HrStartReadSequence(ulong,uchar)
0x180044444  mov     ebx, eax
0x180044446  test    eax, eax
0x180044448  jnz     short loc_1800443F2
0x18004444a  xor     r9d, r9d; unsigned __int8
0x18004444d  lea     r8d, [rax+2]; unsigned int
0x180044451  lea     rdx, [rsp+58h+Src]; int *
0x180044456  mov     rcx, rsi; this
0x180044459  call    ?HrGetValue@CLdapBer@@QEAAKPEAJKE@Z; CLdapBer::HrGetValue(long *,ulong,uchar)
0x18004445e  mov     ebx, eax
0x180044460  test    eax, eax
0x180044462  jnz     short loc_1800443F2
0x180044464  test    rdi, rdi
0x180044467  jz      short loc_18004446F
0x180044469  mov     eax, dword ptr [rsp+58h+Src]
0x18004446d  mov     [rdi], eax
0x18004446f  test    r14, r14
0x180044472  jz      loc_180044531
0x180044478  mov     edx, 6C76424Ch
0x18004447d  mov     [rsp+58h+Src], r13
0x180044482  mov     ecx, 10h
0x180044487  call    ldapMalloc
0x18004448c  mov     rdi, rax
0x18004448f  test    rax, rax
0x180044492  jnz     short loc_1800444D0
0x180044494  cmp     cs:g_fTracingOn, r13d
0x18004449b  lea     ebx, [rax+5Ah]
0x18004449e  jz      loc_180044534
0x1800444a4  cmp     cs:g_fProviderEnabled, r13d
0x1800444ab  jz      loc_180044534
0x1800444b1  mov     ecx, 400000h
0x1800444b6  test    cs:g_ulTraceFlags, rcx
0x1800444bd  jz      short loc_180044534
0x1800444bf  mov     r8, rbp
0x1800444c2  lea     rdx, aLdapparsepagec; "LdapParsePageControl: couldn't allocate"...
0x1800444c9  call    LDAPClientPrint
0x1800444ce  jmp     short loc_180044534
0x1800444d0  mov     r9d, 4; unsigned int
0x1800444d6  mov     byte ptr [rsp+58h+lpString2], r13b; char
0x1800444db  mov     r8, rdi; unsigned int *
0x1800444de  lea     rdx, [rsp+58h+Src]; unsigned __int8 **
0x1800444e3  mov     rcx, rsi; this
0x1800444e6  call    ?HrGetBinaryValuePointer@CLdapBer@@QEAAKPEAPEAEPEAKKE@Z; CLdapBer::HrGetBinaryValuePointer(uchar * *,ulong *,ulong,uchar)
0x1800444eb  mov     rbx, [rsp+58h+Src]
0x1800444f0  test    rbx, rbx
0x1800444f3  jz      short loc_180044527
0x1800444f5  mov     ecx, [rdi]
0x1800444f7  mov     edx, 746E434Ch
0x1800444fc  call    ldapMalloc
0x180044501  mov     [rdi+8], rax
0x180044505  test    rax, rax
0x180044508  jnz     short loc_180044517
0x18004450a  mov     rcx, rdi; bv
0x18004450d  lea     ebx, [rax+5Ah]
0x180044510  call    ber_bvfree
0x180044515  jmp     short loc_180044534
0x180044517  mov     r8d, [rdi]; Size
0x18004451a  mov     rdx, rbx; Src
0x18004451d  mov     rcx, rax; void *
0x180044520  call    memcpy_0
0x180044525  jmp     short loc_18004452E
0x180044527  mov     [rdi], r13d
0x18004452a  mov     [rdi+8], r13
0x18004452e  mov     [r14], rdi
0x180044531  mov     ebx, r13d
0x180044534  mov     rcx, rsi; this
0x180044537  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18004453c  jmp     short loc_180044572
0x18004453e  cmp     cs:g_fTracingOn, r13d
0x180044545  jz      short loc_18004456D
0x180044547  cmp     cs:g_fProviderEnabled, r13d
0x18004454e  jz      short loc_18004456D
0x180044550  mov     ecx, 4000h
0x180044555  test    cs:g_ulTraceFlags, rcx
0x18004455c  jz      short loc_18004456D
0x18004455e  mov     r8, rbp
0x180044561  lea     rdx, aLdapparsepagec_0; "LdapParsePageControl: unable to allocat"...
0x180044568  call    LDAPClientPrint
0x18004456d  mov     ebx, 5Ah ; 'Z'
0x180044572  mov     edx, ebx
0x180044574  mov     rcx, rbp
0x180044577  call    SetConnectionError
0x18004457c  mov     rbp, [rsp+58h+arg_18]
0x180044581  mov     eax, ebx
0x180044583  mov     rbx, [rsp+58h+arg_0]
0x180044588  add     rsp, 30h
0x18004458c  pop     r15
0x18004458e  pop     r14
0x180044590  pop     r13
0x180044592  pop     rdi
0x180044593  pop     rsi
0x180044594  retn
```
