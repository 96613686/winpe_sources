# LdapParseVlvControl(ldap_connection *,ldapcontrolW * *,ulong *,ulong *,berval * *,int *,ulong)

- ea: `0x18004459c`
- end: `0x18004498a`
- name: `?LdapParseVlvControl@@YAKPEAUldap_connection@@PEAPEAUldapcontrolW@@PEAK2PEAPEAUberval@@PEAHK@Z`
- size: `1006`
- prototype: `unsigned int __fastcall(struct ldap_connection *, struct ldapcontrolW **, unsigned int *, unsigned int *, struct berval **, int *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800450a0`
- `0x180045190`

## callees

- `0x180001550`
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
- `0x18004459c`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18004465c`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18004465c`

## string_xrefs

- `0x180044915`: `LdapParseVlvControl: TargetPos read error of 0x%x for 0x%x.\n`
- `0x1800448ec`: `LdapParseVlvControl: ListCount read error of 0x%x for 0x%x.\n`

## pseudocode

```c
__int64 __fastcall LdapParseVlvControl(
        struct ldap_connection *a1,
        struct ldapcontrolW **a2,
        unsigned int *a3,
        unsigned int *a4,
        struct berval **a5,
        int *a6,
        unsigned int a7)
{
  struct ldapcontrolW **v9; // rsi
  unsigned int v10; // ebx
  int *v11; // rdi
  struct berval **v12; // r12
  struct ldapcontrolW *v13; // r13
  bool v14; // zf
  __int64 v15; // rax
  CLdapBer *v16; // rsi
  int v17; // ecx
  unsigned int v18; // edx
  unsigned int v19; // r13d
  unsigned int *v20; // rax
  struct berval *v21; // rdi
  void *v22; // rbx
  CHAR *v23; // rax
  int v25; // [rsp+78h] [rbp+48h] BYREF
  void *Src; // [rsp+80h] [rbp+50h] BYREF
  unsigned int v27; // [rsp+88h] [rbp+58h] BYREF

  Src = a3;
  v9 = a2;
  v10 = 93;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v11 = a6;
  if ( a6 )
    *a6 = 0;
  v12 = a5;
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
    goto LABEL_68;
  v27 = 0;
  v25 = 0;
  LODWORD(a6) = 0;
  LODWORD(a5) = 0;
  while ( 1 )
  {
    v13 = *v9;
    if ( !*v9 )
      goto LABEL_68;
    if ( a7 )
    {
      if ( a7 != 1 )
        goto LABEL_17;
      v14 = CompareStringA(0x400u, 1u, (PCNZCH)v13->ldctl_oid, -1, "2.16.840.1.113730.3.4.10", 25) == 2;
    }
    else
    {
      v14 = (unsigned __int8)ldapWStringsIdentical(v13->ldctl_oid, -1, L"2.16.840.1.113730.3.4.10", -1) == 1;
    }
    if ( v14 )
      break;
LABEL_17:
    ++v9;
  }
  v15 = ldapMalloc(872, 1816347212);
  v16 = (CLdapBer *)v15;
  if ( v15 )
  {
    v17 = *((_DWORD *)a1 + 250);
    *(_QWORD *)v15 = 0;
    *(_DWORD *)(v15 + 8) = 0;
    *(_QWORD *)(v15 + 16) = 0;
    *(_QWORD *)(v15 + 836) = 0;
    *(_QWORD *)(v15 + 24) = 0;
    *(_BYTE *)(v15 + 856) = 0;
    *(_DWORD *)(v15 + 864) = 0;
    *(_DWORD *)(v15 + 860) = v17 != 2 ? 0xFDE9 : 0;
    *(_DWORD *)(v15 + 32) = 0;
    if ( CLdapBer::HrLoadBer(
           (CLdapBer *)v15,
           (const unsigned __int8 *)v13->ldctl_value.bv_val,
           v13->ldctl_value.bv_len,
           &v27,
           1u,
           0)
      || CLdapBer::HrStartReadSequence(v16, 0x30u, 0) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "LdapParseVlvControl: loadBer error of 0x%x for 0x%x.\n", 93, a1);
    }
    else if ( CLdapBer::HrGetValue(v16, (int *)&a6, 2u, 0) || (int)a6 < 0 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "LdapParseVlvControl: TargetPos read error of 0x%x for 0x%x.\n", 93, a1);
    }
    else
    {
      if ( !CLdapBer::HrGetValue(v16, (int *)&a5, 2u, 0) )
      {
        v19 = (unsigned int)a5;
        if ( (int)a5 >= 0 )
        {
          if ( CLdapBer::HrGetEnumValue(v16, &v25) )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
              LDAPClientPrint(0x400000, "LdapParseVlvControl: getEnumValue error of 0x%x for 0x%x.\n", 93, a1);
            goto LABEL_61;
          }
          if ( Src )
            *(_DWORD *)Src = (_DWORD)a6;
          if ( a4 )
            *a4 = v19;
          if ( v11 )
            *v11 = v25;
          if ( v12 )
          {
            Src = 0;
            v20 = (unsigned int *)ldapMalloc(16, 1819689548);
            v21 = (struct berval *)v20;
            if ( !v20 )
            {
              v10 = 90;
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                LDAPClientPrint(0x400000, "LdapParseVlvControl: couldn't allocate berval for 0x%x.\n", (_DWORD)a1);
              goto LABEL_62;
            }
            CLdapBer::HrGetBinaryValuePointer(v16, (unsigned __int8 **)&Src, v20, 4u, 0);
            v22 = Src;
            if ( Src )
            {
              v23 = (CHAR *)ldapMalloc(v21->bv_len, 1953383244);
              v21->bv_val = v23;
              if ( !v23 )
              {
                v10 = 90;
                ber_bvfree(v21);
LABEL_62:
                CLdapBer::`scalar deleting destructor'(v16, v18);
                goto LABEL_68;
              }
              memcpy_0(v23, v22, v21->bv_len);
            }
            else
            {
              ber_bvfree(v21);
              v21 = 0;
            }
            *v12 = v21;
          }
          v10 = 0;
          goto LABEL_62;
        }
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "LdapParseVlvControl: ListCount read error of 0x%x for 0x%x.\n", 93, a1);
    }
LABEL_61:
    v10 = 84;
    goto LABEL_62;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
    LDAPClientPrint(0x4000, "LdapParseVlvControl: unable to allocate message for 0x%x.\n", (_DWORD)a1);
  v10 = 90;
LABEL_68:
  SetConnectionError(a1, v10);
  return v10;
}

```

## disassembly

```asm
0x18004459c  mov     [rsp-38h+arg_0], rbx
0x1800445a1  mov     [rsp-38h+Src], r8
0x1800445a6  push    rbp
0x1800445a7  push    rsi
0x1800445a8  push    rdi
0x1800445a9  push    r12
0x1800445ab  push    r13
0x1800445ad  push    r14
0x1800445af  push    r15
0x1800445b1  mov     rbp, rsp
0x1800445b4  sub     rsp, 30h
0x1800445b8  mov     r14, rcx
0x1800445bb  mov     r15, r9
0x1800445be  xor     ecx, ecx
0x1800445c0  mov     rsi, rdx
0x1800445c3  mov     ebx, 5Dh ; ']'
0x1800445c8  test    r8, r8
0x1800445cb  jz      short loc_1800445D0
0x1800445cd  mov     [r8], ecx
0x1800445d0  test    r15, r15
0x1800445d3  jz      short loc_1800445D8
0x1800445d5  mov     [r9], ecx
0x1800445d8  mov     rdi, [rbp+arg_28]
0x1800445dc  test    rdi, rdi
0x1800445df  jz      short loc_1800445E3
0x1800445e1  mov     [rdi], ecx
0x1800445e3  mov     r12, [rbp+arg_20]
0x1800445e7  test    r12, r12
0x1800445ea  jz      short loc_1800445F0
0x1800445ec  mov     [r12], rcx
0x1800445f0  test    rdx, rdx
0x1800445f3  jz      loc_180044968
0x1800445f9  mov     [rbp+arg_18], ecx
0x1800445fc  mov     [rbp+arg_8], ecx
0x1800445ff  mov     dword ptr [rbp+arg_28], ecx
0x180044602  mov     dword ptr [rbp+arg_20], ecx
0x180044605  mov     r13, [rsi]
0x180044608  test    r13, r13
0x18004460b  jz      loc_180044968
0x180044611  cmp     [rbp+arg_30], ecx
0x180044614  jnz     short loc_180044631
0x180044616  mov     rcx, [r13+0]; lpString1
0x18004461a  lea     r8, a21684011137303_1; "2.16.840.1.113730.3.4.10"
0x180044621  or      r9d, 0FFFFFFFFh; cchCount2
0x180044625  or      edx, r9d; cchCount1
0x180044628  call    ldapWStringsIdentical
0x18004462d  cmp     al, 1
0x18004462f  jmp     short loc_18004466B
0x180044631  cmp     [rbp+arg_30], 1
0x180044635  jnz     short loc_18004466F
0x180044637  mov     r8, [r13+0]; lpString1
0x18004463b  lea     rax, a21684011137303; "2.16.840.1.113730.3.4.10"
0x180044642  or      r9d, 0FFFFFFFFh; cchCount1
0x180044646  mov     [rsp+30h+cchCount2], 19h; cchCount2
0x18004464e  mov     ecx, 400h; Locale
0x180044653  mov     [rsp+30h+lpString2], rax; lpString2
0x180044658  lea     edx, [r9+2]; dwCmpFlags
0x18004465c  call    cs:__imp_CompareStringA
0x180044663  nop     dword ptr [rax+rax+00h]
0x180044668  cmp     eax, 2
0x18004466b  jz      short loc_180044675
0x18004466d  xor     ecx, ecx
0x18004466f  add     rsi, 8
0x180044673  jmp     short loc_180044605
0x180044675  mov     edx, 6C43424Ch
0x18004467a  mov     ecx, 368h
0x18004467f  call    ldapMalloc
0x180044684  xor     edx, edx
0x180044686  mov     rsi, rax
0x180044689  test    rax, rax
0x18004468c  jz      loc_180044936
0x180044692  mov     ecx, [r14+3E8h]
0x180044699  lea     r9, [rbp+arg_18]; unsigned int *
0x18004469d  mov     [rax], rdx
0x1800446a0  sub     ecx, 2
0x1800446a3  mov     [rax+8], edx
0x1800446a6  neg     ecx
0x1800446a8  mov     [rax+10h], rdx
0x1800446ac  mov     rcx, rsi; this
0x1800446af  mov     [rax+344h], rdx
0x1800446b6  mov     [rax+18h], rdx
0x1800446ba  mov     [rax+358h], dl
0x1800446c0  mov     [rax+360h], edx
0x1800446c6  sbb     eax, eax
0x1800446c8  mov     byte ptr [rsp+30h+cchCount2], dl; unsigned __int8
0x1800446cc  and     eax, 0FDE9h
0x1800446d1  mov     [rsi+35Ch], eax
0x1800446d7  mov     [rsi+20h], edx
0x1800446da  mov     r8d, [r13+8]; unsigned int
0x1800446de  mov     rdx, [r13+10h]; Src
0x1800446e2  mov     byte ptr [rsp+30h+lpString2], 1; unsigned __int8
0x1800446e7  call    ?HrLoadBer@CLdapBer@@QEAAKPEBEKPEAKEE@Z; CLdapBer::HrLoadBer(uchar const *,ulong,ulong *,uchar,uchar)
0x1800446ec  xor     r13d, r13d
0x1800446ef  test    eax, eax
0x1800446f1  jz      short loc_18004472B
0x1800446f3  cmp     cs:g_fTracingOn, r13d
0x1800446fa  jz      loc_180044927
0x180044700  cmp     cs:g_fProviderEnabled, r13d
0x180044707  jz      loc_180044927
0x18004470d  mov     ecx, 400000h
0x180044712  test    cs:g_ulTraceFlags, rcx
0x180044719  jz      loc_180044927
0x18004471f  lea     rdx, aLdapparsevlvco_3; "LdapParseVlvControl: loadBer error of 0"...
0x180044726  jmp     loc_18004491C
0x18004472b  xor     r8d, r8d; unsigned __int8
0x18004472e  mov     rcx, rsi; this
0x180044731  lea     edx, [r8+30h]; unsigned int
0x180044735  call    ?HrStartReadSequence@CLdapBer@@QEAAKKE@Z; CLdapBer::HrStartReadSequence(ulong,uchar)
0x18004473a  test    eax, eax
0x18004473c  jnz     short loc_1800446F3
0x18004473e  xor     r9d, r9d; unsigned __int8
0x180044741  lea     r8d, [rax+2]; unsigned int
0x180044745  lea     rdx, [rbp+arg_28]; int *
0x180044749  mov     rcx, rsi; this
0x18004474c  call    ?HrGetValue@CLdapBer@@QEAAKPEAJKE@Z; CLdapBer::HrGetValue(long *,ulong,uchar)
0x180044751  test    eax, eax
0x180044753  jnz     loc_1800448F5
0x180044759  cmp     dword ptr [rbp+arg_28], r13d
0x18004475d  jl      loc_1800448F5
0x180044763  xor     r9d, r9d; unsigned __int8
0x180044766  lea     r8d, [rax+2]; unsigned int
0x18004476a  lea     rdx, [rbp+arg_20]; int *
0x18004476e  mov     rcx, rsi; this
0x180044771  call    ?HrGetValue@CLdapBer@@QEAAKPEAJKE@Z; CLdapBer::HrGetValue(long *,ulong,uchar)
0x180044776  test    eax, eax
0x180044778  jnz     loc_1800448CC
0x18004477e  mov     r13d, dword ptr [rbp+arg_20]
0x180044782  test    r13d, r13d
0x180044785  js      loc_1800448C9
0x18004478b  lea     rdx, [rbp+arg_8]; int *
0x18004478f  mov     rcx, rsi; this
0x180044792  call    ?HrGetEnumValue@CLdapBer@@QEAAKPEAJ@Z; CLdapBer::HrGetEnumValue(long *)
0x180044797  test    eax, eax
0x180044799  jz      short loc_1800447D3
0x18004479b  cmp     cs:g_fTracingOn, 0
0x1800447a2  jz      loc_180044927
0x1800447a8  cmp     cs:g_fProviderEnabled, 0
0x1800447af  jz      loc_180044927
0x1800447b5  mov     ecx, 400000h
0x1800447ba  test    cs:g_ulTraceFlags, rcx
0x1800447c1  jz      loc_180044927
0x1800447c7  lea     rdx, aLdapparsevlvco_2; "LdapParseVlvControl: getEnumValue error"...
0x1800447ce  jmp     loc_18004491C
0x1800447d3  mov     rcx, [rbp+Src]
0x1800447d7  test    rcx, rcx
0x1800447da  jz      short loc_1800447E1
0x1800447dc  mov     eax, dword ptr [rbp+arg_28]
0x1800447df  mov     [rcx], eax
0x1800447e1  test    r15, r15
0x1800447e4  jz      short loc_1800447E9
0x1800447e6  mov     [r15], r13d
0x1800447e9  xor     r15d, r15d
0x1800447ec  test    rdi, rdi
0x1800447ef  jz      short loc_1800447F6
0x1800447f1  mov     eax, [rbp+arg_8]
0x1800447f4  mov     [rdi], eax
0x1800447f6  test    r12, r12
0x1800447f9  jz      loc_1800448C4
0x1800447ff  mov     edx, 6C76424Ch
0x180044804  mov     [rbp+Src], r15
0x180044808  mov     ecx, 10h
0x18004480d  call    ldapMalloc
0x180044812  mov     rdi, rax
0x180044815  test    rax, rax
0x180044818  jnz     short loc_18004485D
0x18004481a  cmp     cs:g_fTracingOn, r15d
0x180044821  lea     ebx, [rax+5Ah]
0x180044824  jz      loc_18004492C
0x18004482a  cmp     cs:g_fProviderEnabled, r15d
0x180044831  jz      loc_18004492C
0x180044837  mov     ecx, 400000h
0x18004483c  test    cs:g_ulTraceFlags, rcx
0x180044843  jz      loc_18004492C
0x180044849  mov     r8, r14
0x18004484c  lea     rdx, aLdapparsevlvco_1; "LdapParseVlvControl: couldn't allocate "...
0x180044853  call    LDAPClientPrint
0x180044858  jmp     loc_18004492C
0x18004485d  mov     r9d, 4; unsigned int
0x180044863  mov     byte ptr [rsp+30h+lpString2], r15b; char
0x180044868  mov     r8, rdi; unsigned int *
0x18004486b  lea     rdx, [rbp+Src]; unsigned __int8 **
0x18004486f  mov     rcx, rsi; this
0x180044872  call    ?HrGetBinaryValuePointer@CLdapBer@@QEAAKPEAPEAEPEAKKE@Z; CLdapBer::HrGetBinaryValuePointer(uchar * *,ulong *,ulong,uchar)
0x180044877  mov     rbx, [rbp+Src]
0x18004487b  test    rbx, rbx
0x18004487e  jz      short loc_1800448B5
0x180044880  mov     ecx, [rdi]
0x180044882  mov     edx, 746E434Ch
0x180044887  call    ldapMalloc
0x18004488c  mov     [rdi+8], rax
0x180044890  test    rax, rax
0x180044893  jnz     short loc_1800448A5
0x180044895  mov     rcx, rdi; bv
0x180044898  lea     ebx, [rax+5Ah]
0x18004489b  call    ber_bvfree
0x1800448a0  jmp     loc_18004492C
0x1800448a5  mov     r8d, [rdi]; Size
0x1800448a8  mov     rdx, rbx; Src
0x1800448ab  mov     rcx, rax; void *
0x1800448ae  call    memcpy_0
0x1800448b3  jmp     short loc_1800448C0
0x1800448b5  mov     rcx, rdi; bv
0x1800448b8  call    ber_bvfree
0x1800448bd  mov     rdi, r15
0x1800448c0  mov     [r12], rdi
0x1800448c4  mov     ebx, r15d
0x1800448c7  jmp     short loc_18004492C
0x1800448c9  xor     r13d, r13d
0x1800448cc  cmp     cs:g_fTracingOn, r13d
0x1800448d3  jz      short loc_180044927
0x1800448d5  cmp     cs:g_fProviderEnabled, r13d
0x1800448dc  jz      short loc_180044927
0x1800448de  mov     ecx, 400000h
0x1800448e3  test    cs:g_ulTraceFlags, rcx
0x1800448ea  jz      short loc_180044927
0x1800448ec  lea     rdx, aLdapparsevlvco; "LdapParseVlvControl: ListCount read err"...
0x1800448f3  jmp     short loc_18004491C
0x1800448f5  cmp     cs:g_fTracingOn, r13d
0x1800448fc  jz      short loc_180044927
0x1800448fe  cmp     cs:g_fProviderEnabled, r13d
0x180044905  jz      short loc_180044927
0x180044907  mov     ecx, 400000h
0x18004490c  test    cs:g_ulTraceFlags, rcx
0x180044913  jz      short loc_180044927
0x180044915  lea     rdx, aLdapparsevlvco_0; "LdapParseVlvControl: TargetPos read err"...
0x18004491c  mov     r9, r14
0x18004491f  mov     r8d, ebx
0x180044922  call    LDAPClientPrint
0x180044927  mov     ebx, 54h ; 'T'
0x18004492c  mov     rcx, rsi; this
0x18004492f  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x180044934  jmp     short loc_180044968
0x180044936  cmp     cs:g_fTracingOn, edx
0x18004493c  jz      short loc_180044963
0x18004493e  cmp     cs:g_fProviderEnabled, edx
0x180044944  jz      short loc_180044963
0x180044946  mov     ecx, 4000h
0x18004494b  test    cs:g_ulTraceFlags, rcx
0x180044952  jz      short loc_180044963
0x180044954  mov     r8, r14
0x180044957  lea     rdx, aLdapparsevlvco_4; "LdapParseVlvControl: unable to allocate"...
0x18004495e  call    LDAPClientPrint
0x180044963  mov     ebx, 5Ah ; 'Z'
0x180044968  mov     edx, ebx
0x18004496a  mov     rcx, r14
0x18004496d  call    SetConnectionError
0x180044972  mov     eax, ebx
0x180044974  mov     rbx, [rsp+30h+arg_0]
0x180044979  add     rsp, 30h
0x18004497d  pop     r15
0x18004497f  pop     r14
0x180044981  pop     r13
0x180044983  pop     r12
0x180044985  pop     rdi
0x180044986  pop     rsi
0x180044987  pop     rbp
0x180044988  retn
```
