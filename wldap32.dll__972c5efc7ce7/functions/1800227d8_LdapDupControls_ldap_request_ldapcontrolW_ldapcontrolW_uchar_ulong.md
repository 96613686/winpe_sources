# LdapDupControls(ldap_request *,ldapcontrolW * * *,ldapcontrolW * *,uchar,ulong)

- ea: `0x1800227d8`
- end: `0x180022a52`
- name: `?LdapDupControls@@YAKPEAUldap_request@@PEAPEAPEAUldapcontrolW@@PEAPEAU2@EK@Z`
- size: `634`
- prototype: `unsigned int __fastcall(struct ldap_request *, struct ldapcontrolW ***, struct ldapcontrolW **, unsigned __int8, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180020320`

## callees

- `0x18001ce90`
- `0x18001ffa0`
- `0x1800227d8`
- `0x180022e80`
- `0x180022fe4`
- `0x180024580`
- `0x180032bd8`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022945`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022945`

## pseudocode

```c
__int64 __fastcall LdapDupControls(
        struct ldap_request *a1,
        struct ldapcontrolW ***a2,
        struct ldapcontrolW **a3,
        char a4,
        unsigned int a5)
{
  struct ldapcontrolW **v5; // r15
  int v7; // esi
  struct ldapcontrolW *v8; // rax
  struct ldapcontrolW **v9; // r10
  __int64 v10; // rsi
  __int64 v12; // r14
  unsigned __int64 v13; // rcx
  __int64 v14; // rcx
  struct ldapcontrolW **v15; // rax
  struct ldapcontrolW **v16; // rdi
  unsigned int v17; // ebx
  struct ldapcontrolW **i; // r14
  struct ldapcontrolW *v19; // r12
  PWCHAR ldctl_oid; // rcx
  __int64 v21; // rax
  __int64 bv_len; // rcx
  struct ldapcontrolW *v23; // rax

  v5 = a3;
  v7 = 1;
  if ( a3 )
  {
    v8 = *a3;
    v9 = a3;
    while ( v8 && v8->ldctl_oid )
    {
      ++v7;
      v8 = *++v9;
    }
  }
  v10 = a5 + v7;
  if ( (_DWORD)v10 == 1 )
  {
    *a2 = 0;
    return 0;
  }
  v12 = 8 * v10;
  if ( (unsigned __int64)(8 * v10) > 0xFFFFFFFF
    || (v13 = 32LL * (unsigned int)(v10 - 1), v13 > 0xFFFFFFFF)
    || (v14 = (unsigned int)(v12 + v13), (unsigned int)v14 < (unsigned int)v12) )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientTraceEvent(0x10000000, (__int64)"Integer overflow while calculating buffer size for controls\n");
    return 82;
  }
  v15 = (struct ldapcontrolW **)ldapMalloc(v14, 1819427660);
  v16 = v15;
  if ( !v15 )
    return 90;
  v17 = 0;
  *a2 = v15;
  for ( i = &v15[(unsigned __int64)v12 / 8]; ; i += 4 )
  {
    LODWORD(v10) = v10 - 1;
    if ( !(_DWORD)v10 )
    {
      *v16 = 0;
      return v17;
    }
    if ( v5 )
      break;
    *v16 = (struct ldapcontrolW *)i;
LABEL_35:
    ++v16;
  }
  v19 = *v5;
  *v16 = (struct ldapcontrolW *)i;
  if ( !v19 )
    goto LABEL_35;
  *((_BYTE *)i + 24) = v19->ldctl_iscritical;
  ldctl_oid = v19->ldctl_oid;
  if ( a4 )
  {
    v21 = ldap_dup_stringW(ldctl_oid);
LABEL_21:
    *i = (struct ldapcontrolW *)v21;
    v17 = v21 == 0 ? 0x5A : 0;
    goto LABEL_23;
  }
  if ( a5 )
  {
    v21 = ldap_dup_string(ldctl_oid);
    goto LABEL_21;
  }
  v17 = ToUnicodeWithAlloc((LPCCH)ldctl_oid, 1);
LABEL_23:
  if ( v17 )
    goto LABEL_38;
  if ( *i && CompareStringW(0x400u, 1u, (PCNZWCH)*i, -1, L"1.2.840.113556.1.4.528", -1) == 2 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
      LDAPClientTraceEvent(0x8000, (__int64)"Detected a notifications request\n");
    *((_BYTE *)a1 + 190) = 1;
  }
  bv_len = v19->ldctl_value.bv_len;
  *((_DWORD *)i + 2) = bv_len;
  if ( !(_DWORD)bv_len )
    goto LABEL_34;
  v23 = (struct ldapcontrolW *)ldapMalloc(bv_len, 1953383244);
  i[2] = v23;
  if ( v23 )
  {
    memcpy_0(v23, v19->ldctl_value.bv_val, *((unsigned int *)i + 2));
LABEL_34:
    ++v5;
    goto LABEL_35;
  }
  v17 = 90;
LABEL_38:
  *v16 = 0;
  ldap_controls_freeW(*a2);
  *a2 = 0;
  return v17;
}

```

## disassembly

```asm
0x1800227d8  mov     rax, rsp
0x1800227db  mov     [rax+10h], rbx
0x1800227df  mov     [rax+18h], rbp
0x1800227e3  mov     [rax+20h], r9b
0x1800227e7  mov     [rax+8], rcx
0x1800227eb  push    rsi
0x1800227ec  push    rdi
0x1800227ed  push    r12
0x1800227ef  push    r14
0x1800227f1  push    r15
0x1800227f3  sub     rsp, 30h
0x1800227f7  mov     r15, r8
0x1800227fa  mov     rbp, rdx
0x1800227fd  mov     esi, 1
0x180022802  test    r8, r8
0x180022805  jz      short loc_180022823
0x180022807  mov     rax, [r8]
0x18002280a  mov     r10, r8
0x18002280d  jmp     short loc_18002281E
0x18002280f  cmp     qword ptr [rax], 0
0x180022813  jz      short loc_180022823
0x180022815  inc     esi
0x180022817  add     r10, 8
0x18002281b  mov     rax, [r10]
0x18002281e  test    rax, rax
0x180022821  jnz     short loc_18002280F
0x180022823  add     esi, [rsp+58h+arg_20]
0x18002282a  cmp     esi, 1
0x18002282d  jnz     short loc_18002283D
0x18002282f  mov     qword ptr [rdx], 0
0x180022836  xor     eax, eax
0x180022838  jmp     loc_180022A3A
0x18002283d  lea     r14, ds:0[rsi*8]
0x180022845  mov     r12d, 0FFFFFFFFh
0x18002284b  cmp     r14, r12
0x18002284e  ja      loc_180022A09
0x180022854  lea     ecx, [rsi-1]
0x180022857  shl     rcx, 5
0x18002285b  cmp     rcx, r12
0x18002285e  ja      loc_180022A09
0x180022864  add     ecx, r14d
0x180022867  cmp     ecx, r14d
0x18002286a  jb      loc_180022A09
0x180022870  mov     edx, 6C72434Ch
0x180022875  call    ldapMalloc
0x18002287a  mov     rdi, rax
0x18002287d  test    rax, rax
0x180022880  jnz     short loc_18002288A
0x180022882  lea     eax, [rdi+5Ah]
0x180022885  jmp     loc_180022A3A
0x18002288a  xor     ebx, ebx
0x18002288c  mov     [rbp+0], rax
0x180022890  add     r14, rax
0x180022893  mov     eax, ebx
0x180022895  add     esi, r12d
0x180022898  jz      loc_1800229E9
0x18002289e  test    r15, r15
0x1800228a1  jz      loc_1800229D6
0x1800228a7  mov     r12, [r15]
0x1800228aa  mov     [rdi], r14
0x1800228ad  test    r12, r12
0x1800228b0  jz      loc_1800229C3
0x1800228b6  cmp     [rsp+58h+arg_18], 0
0x1800228bb  mov     al, [r12+18h]
0x1800228c0  mov     [r14+18h], al
0x1800228c4  mov     rcx, [r12]; lpMultiByteStr
0x1800228c8  jz      short loc_1800228D9
0x1800228ca  xor     edx, edx
0x1800228cc  mov     r8d, 6C61564Ch
0x1800228d2  call    ldap_dup_stringW
0x1800228d7  jmp     short loc_1800228EE
0x1800228d9  cmp     [rsp+58h+arg_20], 0
0x1800228e1  jbe     short loc_1800228FD
0x1800228e3  mov     r8d, 6C61564Ch
0x1800228e9  call    ldap_dup_string
0x1800228ee  mov     [r14], rax
0x1800228f1  neg     rax
0x1800228f4  sbb     ebx, ebx
0x1800228f6  not     ebx
0x1800228f8  and     ebx, 5Ah
0x1800228fb  jmp     short loc_180022918
0x1800228fd  mov     r9d, 6C61564Ch
0x180022903  mov     dword ptr [rsp+58h+lpString2], 1; int
0x18002290b  mov     r8, r14
0x18002290e  or      edx, 0FFFFFFFFh
0x180022911  call    ToUnicodeWithAlloc
0x180022916  mov     ebx, eax
0x180022918  test    ebx, ebx
0x18002291a  jnz     loc_1800229E0
0x180022920  mov     r8, [r14]; lpString1
0x180022923  test    r8, r8
0x180022926  jz      short loc_18002298E
0x180022928  or      r9d, 0FFFFFFFFh; cchCount1
0x18002292c  lea     rax, a12840113556145; "1.2.840.113556.1.4.528"
0x180022933  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x180022938  lea     edx, [rbx+1]; dwCmpFlags
0x18002293b  mov     ecx, 400h; Locale
0x180022940  mov     [rsp+58h+lpString2], rax; lpString2
0x180022945  call    cs:__imp_CompareStringW
0x18002294c  nop     dword ptr [rax+rax+00h]
0x180022951  cmp     eax, 2
0x180022954  jnz     short loc_18002298E
0x180022956  cmp     cs:g_fTracingOn, ebx
0x18002295c  jz      short loc_180022982
0x18002295e  cmp     cs:g_fProviderEnabled, ebx
0x180022964  jz      short loc_180022982
0x180022966  mov     eax, 8000h
0x18002296b  test    cs:g_ulTraceFlags, rax
0x180022972  jz      short loc_180022982
0x180022974  lea     rdx, aDetectedANotif; "Detected a notifications request\n"
0x18002297b  mov     ecx, eax
0x18002297d  call    LDAPClientTraceEvent
0x180022982  mov     rax, [rsp+58h+arg_0]
0x180022987  mov     byte ptr [rax+0BEh], 1
0x18002298e  mov     ecx, [r12+8]
0x180022993  mov     [r14+8], ecx
0x180022997  test    ecx, ecx
0x180022999  jz      short loc_1800229BF
0x18002299b  mov     edx, 746E434Ch
0x1800229a0  call    ldapMalloc
0x1800229a5  mov     [r14+10h], rax
0x1800229a9  test    rax, rax
0x1800229ac  jz      short loc_1800229DB
0x1800229ae  mov     r8d, [r14+8]; Size
0x1800229b2  mov     rcx, rax; void *
0x1800229b5  mov     rdx, [r12+10h]; Src
0x1800229ba  call    memcpy_0
0x1800229bf  add     r15, 8
0x1800229c3  mov     r12d, 0FFFFFFFFh
0x1800229c9  add     rdi, 8
0x1800229cd  add     r14, 20h ; ' '
0x1800229d1  jmp     loc_180022893
0x1800229d6  mov     [rdi], r14
0x1800229d9  jmp     short loc_1800229C9
0x1800229db  mov     ebx, 5Ah ; 'Z'
0x1800229e0  mov     qword ptr [rdi], 0
0x1800229e7  jmp     short loc_1800229F4
0x1800229e9  mov     qword ptr [rdi], 0
0x1800229f0  test    eax, eax
0x1800229f2  jz      short loc_180022A05
0x1800229f4  mov     rcx, [rbp+0]; Control
0x1800229f8  call    ldap_controls_freeW
0x1800229fd  mov     qword ptr [rbp+0], 0
0x180022a05  mov     eax, ebx
0x180022a07  jmp     short loc_180022A3A
0x180022a09  cmp     cs:g_fTracingOn, 0
0x180022a10  jz      short loc_180022A35
0x180022a12  cmp     cs:g_fProviderEnabled, 0
0x180022a19  jz      short loc_180022A35
0x180022a1b  mov     ecx, 10000000h
0x180022a20  test    cs:g_ulTraceFlags, rcx
0x180022a27  jz      short loc_180022A35
0x180022a29  lea     rdx, aIntegerOverflo_1; "Integer overflow while calculating buff"...
0x180022a30  call    LDAPClientTraceEvent
0x180022a35  mov     eax, 52h ; 'R'
0x180022a3a  mov     rbx, [rsp+58h+arg_8]
0x180022a3f  mov     rbp, [rsp+58h+arg_10]
0x180022a44  add     rsp, 30h
0x180022a48  pop     r15
0x180022a4a  pop     r14
0x180022a4c  pop     r12
0x180022a4e  pop     rdi
0x180022a4f  pop     rsi
0x180022a50  retn
```
