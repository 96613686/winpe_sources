# LdapCreatePageControl(ldap_connection *,ulong,berval *,uchar,ldapcontrolW * *,ulong)

- ea: `0x18001f96c`
- end: `0x18001fb71`
- name: `?LdapCreatePageControl@@YAKPEAUldap_connection@@KPEAUberval@@EPEAPEAUldapcontrolW@@K@Z`
- size: `517`
- prototype: `unsigned int(struct ldap_connection *, unsigned int, struct berval *, unsigned __int8, struct ldapcontrolW **, unsigned int)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x18001f4a0`
- `0x180044990`
- `0x180044a80`

## callees

- `0x180010ef0`
- `0x180011c80`
- `0x180014060`
- `0x180014460`
- `0x18001ce90`
- `0x18001f96c`
- `0x18001fb78`
- `0x1800201e0`
- `0x180022e80`
- `0x180029d28`
- `0x18004c76c`

## pseudocode

```c
__int64 __fastcall LdapCreatePageControl(
        struct ldap_connection *a1,
        int a2,
        struct berval *a3,
        char a4,
        struct ldapcontrolW **a5,
        unsigned int a6)
{
  bool v8; // bl
  __int64 v11; // rax
  struct ldapcontrolW *v12; // rsi
  __int64 v13; // rbx
  _QWORD *p_ldctl_oid; // rbp
  const CHAR *v15; // rax
  unsigned int v16; // edi
  void *v17; // rax
  unsigned int *v18; // rbx
  int v19; // eax
  unsigned int v20; // edi
  unsigned __int8 *bv_val; // rdx
  unsigned int v22; // eax
  __int64 v23; // rcx
  CHAR *v24; // rax

  v8 = a4 != 0;
  if ( !a5 )
    return 89;
  v11 = ldapMalloc(32, 1953383244);
  v12 = (struct ldapcontrolW *)v11;
  if ( !v11 )
  {
    *a5 = 0;
    return 90;
  }
  *(_BYTE *)(v11 + 24) = v8;
  if ( a6 )
  {
    p_ldctl_oid = (_QWORD *)v11;
    v15 = "1.2.840.113556.1.4.319";
    v16 = 1;
    while ( *v15 )
    {
      if ( v16 + 1 < v16 )
        goto LABEL_11;
      ++v16;
      ++v15;
    }
    v17 = (void *)ldapMalloc(v16, 1818318412);
    v13 = (__int64)v17;
    if ( !v17 )
    {
LABEL_11:
      v13 = 0;
      goto LABEL_14;
    }
    memcpy_0(v17, "1.2.840.113556.1.4.319", v16);
  }
  else
  {
    v13 = ldap_dup_stringW((void *)L"1.2.840.113556.1.4.319");
    p_ldctl_oid = &v12->ldctl_oid;
  }
LABEL_14:
  *p_ldctl_oid = v13;
  if ( !v13 || (v18 = (unsigned int *)ldapMalloc(872, 1816347212)) == 0 )
  {
    v18 = 0;
LABEL_28:
    v20 = 90;
    goto LABEL_29;
  }
  v19 = *((_DWORD *)a1 + 250) - 2;
  *(_QWORD *)v18 = 0;
  v18[2] = 0;
  *((_QWORD *)v18 + 2) = 0;
  *(_QWORD *)(v18 + 209) = 0;
  *((_QWORD *)v18 + 3) = 0;
  *((_BYTE *)v18 + 856) = 0;
  v18[216] = 0;
  v18[215] = v19 != 0 ? 0xFDE9 : 0;
  v18[8] = 0;
  v20 = CLdapBer::HrStartWriteSequence((CLdapBer *)v18, 48);
  if ( !v20 )
  {
    CLdapBer::HrAddValue((CLdapBer *)v18, a2, 2u);
    if ( a3 && a3->bv_len && (bv_val = (unsigned __int8 *)a3->bv_val) != 0 )
      v22 = CLdapBer::HrAddBinaryValue((CLdapBer *)v18, bv_val, a3->bv_len, 4u);
    else
      v22 = CLdapBer::HrAddValue((CLdapBer *)v18, 0, 4);
    v20 = v22;
    if ( !v22 )
    {
      CLdapBer::HrEndWriteSequence((CLdapBer *)v18);
      v23 = *v18;
      v12->ldctl_value.bv_len = v23;
      if ( !(_DWORD)v23 )
      {
        v20 = 82;
        goto LABEL_29;
      }
      v24 = (CHAR *)ldapMalloc(v23, 1953383244);
      v12->ldctl_value.bv_val = v24;
      if ( v24 )
      {
        memcpy_0(v24, *((const void **)v18 + 2), v12->ldctl_value.bv_len);
        v20 = 0;
LABEL_30:
        CLdapBer::`scalar deleting destructor'((CLdapBer *)v18);
        goto LABEL_31;
      }
      goto LABEL_28;
    }
  }
LABEL_29:
  ldap_control_freeW(v12);
  v12 = 0;
  if ( v18 )
    goto LABEL_30;
LABEL_31:
  *a5 = v12;
  return v20;
}

```

## disassembly

```asm
0x18001f96c  push    rbx
0x18001f96e  push    rbp
0x18001f96f  push    rsi
0x18001f970  push    rdi
0x18001f971  push    r12
0x18001f973  push    r13
0x18001f975  push    r14
0x18001f977  push    r15
0x18001f979  sub     rsp, 28h
0x18001f97d  mov     r15, [rsp+68h+arg_20]
0x18001f985  test    r9b, r9b
0x18001f988  mov     r14, r8
0x18001f98b  mov     r12d, edx
0x18001f98e  setnz   bl
0x18001f991  mov     r13, rcx
0x18001f994  test    r15, r15
0x18001f997  jnz     short loc_18001F9A2
0x18001f999  lea     eax, [r15+59h]
0x18001f99d  jmp     loc_18001FB5F
0x18001f9a2  mov     edx, 746E434Ch
0x18001f9a7  mov     ecx, 20h ; ' '
0x18001f9ac  call    ldapMalloc
0x18001f9b1  mov     rsi, rax
0x18001f9b4  test    rax, rax
0x18001f9b7  jnz     short loc_18001F9C4
0x18001f9b9  mov     [r15], rax
0x18001f9bc  lea     eax, [rsi+5Ah]
0x18001f9bf  jmp     loc_18001FB5F
0x18001f9c4  cmp     [rsp+68h+arg_28], 0
0x18001f9cc  mov     [rax+18h], bl
0x18001f9cf  jnz     short loc_18001F9ED
0x18001f9d1  xor     edx, edx
0x18001f9d3  lea     rcx, a12840113556143; "1.2.840.113556.1.4.319"
0x18001f9da  mov     r8d, 6C61564Ch
0x18001f9e0  call    ldap_dup_stringW
0x18001f9e5  mov     rbx, rax
0x18001f9e8  mov     rbp, rsi
0x18001f9eb  jmp     short loc_18001FA39
0x18001f9ed  mov     rbp, rsi
0x18001f9f0  lea     rax, Src; "1.2.840.113556.1.4.319"
0x18001f9f7  mov     edi, 1
0x18001f9fc  cmp     byte ptr [rax], 0
0x18001f9ff  jz      short loc_18001FA13
0x18001fa01  lea     ecx, [rdi+1]
0x18001fa04  cmp     ecx, edi
0x18001fa06  jb      short loc_18001FA0F
0x18001fa08  mov     edi, ecx
0x18001fa0a  inc     rax
0x18001fa0d  jmp     short loc_18001F9FC
0x18001fa0f  xor     ebx, ebx
0x18001fa11  jmp     short loc_18001FA39
0x18001fa13  mov     edx, 6C61564Ch
0x18001fa18  mov     ecx, edi
0x18001fa1a  call    ldapMalloc
0x18001fa1f  mov     rbx, rax
0x18001fa22  test    rax, rax
0x18001fa25  jz      short loc_18001FA0F
0x18001fa27  mov     r8d, edi; Size
0x18001fa2a  lea     rdx, Src; "1.2.840.113556.1.4.319"
0x18001fa31  mov     rcx, rax; void *
0x18001fa34  call    memcpy_0
0x18001fa39  mov     [rbp+0], rbx
0x18001fa3d  xor     ebp, ebp
0x18001fa3f  test    rbx, rbx
0x18001fa42  jz      loc_18001FB3A
0x18001fa48  mov     edx, 6C43424Ch
0x18001fa4d  mov     ecx, 368h
0x18001fa52  call    ldapMalloc
0x18001fa57  mov     rbx, rax
0x18001fa5a  test    rax, rax
0x18001fa5d  jz      loc_18001FB3A
0x18001fa63  mov     eax, [r13+3E8h]
0x18001fa6a  lea     edx, [rbp+30h]; unsigned int
0x18001fa6d  sub     eax, 2
0x18001fa70  mov     [rbx], rbp
0x18001fa73  neg     eax
0x18001fa75  mov     [rbx+8], ebp
0x18001fa78  mov     [rbx+10h], rbp
0x18001fa7c  mov     rcx, rbx; this
0x18001fa7f  sbb     eax, eax
0x18001fa81  mov     [rbx+344h], rbp
0x18001fa88  and     eax, 0FDE9h
0x18001fa8d  mov     [rbx+18h], rbp
0x18001fa91  mov     [rbx+358h], bpl
0x18001fa98  mov     [rbx+360h], ebp
0x18001fa9e  mov     [rbx+35Ch], eax
0x18001faa4  mov     [rbx+20h], ebp
0x18001faa7  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x18001faac  mov     edi, eax
0x18001faae  test    eax, eax
0x18001fab0  jnz     loc_18001FB42
0x18001fab6  lea     r8d, [rbp+2]; unsigned int
0x18001faba  mov     edx, r12d; int
0x18001fabd  mov     rcx, rbx; this
0x18001fac0  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x18001fac5  test    r14, r14
0x18001fac8  jz      short loc_18001FAE9
0x18001faca  mov     r8d, [r14]; unsigned int
0x18001facd  test    r8d, r8d
0x18001fad0  jz      short loc_18001FAE9
0x18001fad2  mov     rdx, [r14+8]; unsigned __int8 *
0x18001fad6  test    rdx, rdx
0x18001fad9  jz      short loc_18001FAE9
0x18001fadb  lea     r9d, [rbp+4]; unsigned int
0x18001fadf  mov     rcx, rbx; this
0x18001fae2  call    ?HrAddBinaryValue@CLdapBer@@QEAAKPEAEKK@Z; CLdapBer::HrAddBinaryValue(uchar *,ulong,ulong)
0x18001fae7  jmp     short loc_18001FAF7
0x18001fae9  xor     edx, edx; lpMultiByteStr
0x18001faeb  mov     rcx, rbx; this
0x18001faee  lea     r8d, [rdx+4]; unsigned int
0x18001faf2  call    ?HrAddValue@CLdapBer@@QEAAKPEBDK@Z; CLdapBer::HrAddValue(char const *,ulong)
0x18001faf7  mov     edi, eax
0x18001faf9  test    eax, eax
0x18001fafb  jnz     short loc_18001FB42
0x18001fafd  mov     rcx, rbx; this
0x18001fb00  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18001fb05  mov     ecx, [rbx]
0x18001fb07  mov     [rsi+8], ecx
0x18001fb0a  test    ecx, ecx
0x18001fb0c  jnz     short loc_18001FB13
0x18001fb0e  lea     edi, [rcx+52h]
0x18001fb11  jmp     short loc_18001FB42
0x18001fb13  mov     edx, 746E434Ch
0x18001fb18  call    ldapMalloc
0x18001fb1d  mov     [rsi+10h], rax
0x18001fb21  test    rax, rax
0x18001fb24  jz      short loc_18001FB3D
0x18001fb26  mov     r8d, [rsi+8]; Size
0x18001fb2a  mov     rcx, rax; void *
0x18001fb2d  mov     rdx, [rbx+10h]; Src
0x18001fb31  call    memcpy_0
0x18001fb36  mov     edi, ebp
0x18001fb38  jmp     short loc_18001FB52
0x18001fb3a  mov     rbx, rbp
0x18001fb3d  mov     edi, 5Ah ; 'Z'
0x18001fb42  mov     rcx, rsi; Control
0x18001fb45  call    ldap_control_freeW
0x18001fb4a  mov     rsi, rbp
0x18001fb4d  test    rbx, rbx
0x18001fb50  jz      short loc_18001FB5A
0x18001fb52  mov     rcx, rbx; this
0x18001fb55  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x18001fb5a  mov     [r15], rsi
0x18001fb5d  mov     eax, edi
0x18001fb5f  add     rsp, 28h
0x18001fb63  pop     r15
0x18001fb65  pop     r14
0x18001fb67  pop     r13
0x18001fb69  pop     r12
0x18001fb6b  pop     rdi
0x18001fb6c  pop     rsi
0x18001fb6d  pop     rbp
0x18001fb6e  pop     rbx
0x18001fb6f  retn
```
