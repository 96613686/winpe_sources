# LdapCompare(ldap_connection *,ushort *,ushort *,ushort *,berval *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)

- ea: `0x18003c254`
- end: `0x18003c5b4`
- name: `?LdapCompare@@YAKPEAUldap_connection@@PEAG11PEAUberval@@EEPEAPEAUldapcontrolW@@3PEAK@Z`
- size: `864`
- prototype: `unsigned int(struct ldap_connection *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct berval *, unsigned __int8, unsigned __int8, struct ldapcontrolW **, struct ldapcontrolW **, unsigned int *)`
- caller_count: `5`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003c9e0`
- `0x18003caf0`
- `0x18003cd20`
- `0x18003ce30`
- `0x18003d0d0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x180008710`
- `0x180014b60`
- `0x180015bd8`
- `0x18001ce90`
- `0x180020320`
- `0x180022e80`
- `0x18002a284`
- `0x18003c254`
- `0x18003c5bc`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c532`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c532`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c57c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c594`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c57c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c594`

## string_xrefs

- `0x18003c2e2`: `ldap_compare connection 0x%x couldn't allocate request.\n`
- `0x18003c377`: `ldap_comp connection 0x%x trouble with SControl, error 0x%x.\n`
- `0x18003c4fb`: `ldap_compare connection 0x%x errored with 0x%x.\n`

## pseudocode

```c
__int64 __fastcall LdapCompare(
        struct ldap_connection *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct berval *a5,
        unsigned __int8 a6,
        unsigned __int8 a7,
        struct ldapcontrolW **a8,
        struct ldapcontrolW **a9,
        unsigned int *a10)
{
  struct ldap_connection *v13; // rsi
  unsigned int v14; // ebx
  __int64 result; // rax
  __int64 v16; // rdx
  __int64 Request; // rax
  __int64 v18; // rdi
  unsigned int v19; // r13d
  unsigned int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 bv_len; // rcx
  void *v25; // rax
  struct _RTL_CRITICAL_SECTION *v26; // rcx

  v13 = a1;
  if ( a10 )
  {
    *a10 = -1;
    result = LdapConnect(a1, 0, 0);
    if ( (_DWORD)result )
      return result;
    SetConnectionError(v13, 0);
    LOBYTE(v16) = 110;
    Request = LdapCreateRequest(v13, v16);
    v18 = Request;
    if ( !Request )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
        LDAPClientPrint(0x4000, "ldap_compare connection 0x%x couldn't allocate request.\n", (_DWORD)v13);
      v14 = 90;
      a1 = v13;
      goto LABEL_3;
    }
    v19 = *(_DWORD *)(Request + 108);
    *(_BYTE *)(Request + 187) = a7;
    if ( a8 || (v14 = 0, a9) )
    {
      v20 = LdapCheckControls((struct ldap_request *)Request, a8, a9, a6, 0);
      v14 = v20;
      if ( v20 )
      {
        if ( !g_fTracingOn )
        {
LABEL_42:
          v19 = -1;
          SetConnectionError(v13, v14);
          CloseLdapRequest(v18);
LABEL_43:
          *a10 = v19;
          EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 48));
          --*(_DWORD *)(v18 + 16);
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
            LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v18, *(_DWORD *)(v18 + 16));
          v26 = (struct _RTL_CRITICAL_SECTION *)(v18 + 48);
          if ( *(_DWORD *)(v18 + 16) )
          {
            LeaveCriticalSection(v26);
          }
          else
          {
            LeaveCriticalSection(v26);
            DereferenceLdapRequest2((__int64 *)v18, 0);
          }
          return v14;
        }
        if ( g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
          LDAPClientPrint(0x8000, "ldap_comp connection 0x%x trouble with SControl, error 0x%x.\n", (_DWORD)v13, v20);
LABEL_38:
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
          LDAPClientPrint(0x100000, "ldap_compare connection 0x%x errored with 0x%x.\n", (_DWORD)v13, v14);
        goto LABEL_42;
      }
    }
    if ( a7 || !*(_BYTE *)(v18 + 185) )
    {
      *(_BYTE *)(v18 + 269) = 0;
      *(_QWORD *)(v18 + 192) = a2;
      *(_QWORD *)(v18 + 232) = a3;
      *(_QWORD *)(v18 + 240) = a4;
      if ( a5 )
      {
        *(_QWORD *)(v18 + 256) = a5->bv_val;
        *(_DWORD *)(v18 + 248) = a5->bv_len;
      }
      if ( v14 )
        goto LABEL_38;
    }
    else
    {
      *(_BYTE *)(v18 + 269) = 1;
      if ( a2 )
      {
        v21 = ldap_dup_stringW(a2);
        *(_QWORD *)(v18 + 192) = v21;
        if ( !v21 )
          goto LABEL_28;
      }
      if ( v14 )
        goto LABEL_38;
      if ( a4 || a5 )
      {
        v22 = ldap_dup_stringW(a3);
        *(_QWORD *)(v18 + 232) = v22;
        if ( !v22 )
          goto LABEL_28;
        if ( a4 )
        {
          v23 = ldap_dup_stringW(a4);
          *(_QWORD *)(v18 + 240) = v23;
          if ( !v23 )
            goto LABEL_28;
        }
        if ( a5 )
        {
          if ( a5->bv_val )
          {
            bv_len = a5->bv_len;
            if ( (_DWORD)bv_len )
            {
              v25 = (void *)ldapMalloc(bv_len, 1633960780);
              *(_QWORD *)(v18 + 256) = v25;
              if ( !v25 )
              {
LABEL_28:
                v14 = 90;
                goto LABEL_38;
              }
              memcpy_0(v25, a5->bv_val, a5->bv_len);
              *(_DWORD *)(v18 + 248) = a5->bv_len;
            }
          }
        }
      }
    }
    v14 = SendLdapCompare(
            (struct ldap_request *)v18,
            v13,
            (struct CLdapBer **)(v18 + 160),
            *(unsigned __int16 **)(v18 + 192),
            0);
    if ( !v14 )
      goto LABEL_43;
    goto LABEL_38;
  }
  v14 = 89;
LABEL_3:
  SetConnectionError(a1, v14);
  return v14;
}

```

## disassembly

```asm
0x18003c254  push    rbx
0x18003c256  push    rbp
0x18003c257  push    rsi
0x18003c258  push    rdi
0x18003c259  push    r12
0x18003c25b  push    r13
0x18003c25d  push    r14
0x18003c25f  push    r15
0x18003c261  sub     rsp, 38h
0x18003c265  mov     rax, [rsp+78h+arg_48]
0x18003c26d  mov     rbp, r9
0x18003c270  mov     r12, r8
0x18003c273  mov     r14, rdx
0x18003c276  mov     rsi, rcx
0x18003c279  test    rax, rax
0x18003c27c  jnz     short loc_18003C28D
0x18003c27e  lea     ebx, [rax+59h]
0x18003c281  mov     edx, ebx
0x18003c283  call    SetConnectionError
0x18003c288  jmp     loc_18003C5A0
0x18003c28d  xor     r8d, r8d
0x18003c290  mov     dword ptr [rax], 0FFFFFFFFh
0x18003c296  xor     edx, edx
0x18003c298  call    LdapConnect
0x18003c29d  test    eax, eax
0x18003c29f  jnz     loc_18003C5A2
0x18003c2a5  xor     edx, edx
0x18003c2a7  mov     rcx, rsi
0x18003c2aa  call    SetConnectionError
0x18003c2af  mov     dl, 6Eh ; 'n'
0x18003c2b1  mov     rcx, rsi
0x18003c2b4  call    LdapCreateRequest
0x18003c2b9  mov     rdi, rax
0x18003c2bc  test    rax, rax
0x18003c2bf  jnz     short loc_18003C2F8
0x18003c2c1  cmp     cs:g_fTracingOn, eax
0x18003c2c7  jz      short loc_18003C2EE
0x18003c2c9  cmp     cs:g_fProviderEnabled, eax
0x18003c2cf  jz      short loc_18003C2EE
0x18003c2d1  mov     ecx, 4000h
0x18003c2d6  test    cs:g_ulTraceFlags, rcx
0x18003c2dd  jz      short loc_18003C2EE
0x18003c2df  mov     r8, rsi
0x18003c2e2  lea     rdx, aLdapCompareCon; "ldap_compare connection 0x%x couldn't a"...
0x18003c2e9  call    LDAPClientPrint
0x18003c2ee  mov     ebx, 5Ah ; 'Z'
0x18003c2f3  mov     rcx, rsi
0x18003c2f6  jmp     short loc_18003C281
0x18003c2f8  mov     rdx, [rsp+78h+arg_38]; struct ldapcontrolW **
0x18003c300  mov     r15b, [rsp+78h+arg_30]
0x18003c308  mov     r13d, [rax+6Ch]
0x18003c30c  mov     r8, [rsp+78h+arg_40]; struct ldapcontrolW **
0x18003c314  mov     [rax+0BBh], r15b
0x18003c31b  test    rdx, rdx
0x18003c31e  jnz     short loc_18003C327
0x18003c320  xor     ebx, ebx
0x18003c322  test    r8, r8
0x18003c325  jz      short loc_18003C38B
0x18003c327  mov     r9b, [rsp+78h+arg_28]; unsigned __int8
0x18003c32f  mov     rcx, rdi; struct ldap_request *
0x18003c332  mov     [rsp+78h+var_58], 0; unsigned int
0x18003c33a  call    LdapCheckControls
0x18003c33f  mov     ebx, eax
0x18003c341  test    eax, eax
0x18003c343  jz      short loc_18003C38B
0x18003c345  xor     r15d, r15d
0x18003c348  cmp     cs:g_fTracingOn, r15d
0x18003c34f  jz      loc_18003C50A
0x18003c355  cmp     cs:g_fProviderEnabled, r15d
0x18003c35c  jz      loc_18003C4D8
0x18003c362  mov     ecx, 8000h
0x18003c367  test    cs:g_ulTraceFlags, rcx
0x18003c36e  jz      loc_18003C4D8
0x18003c374  mov     r9d, eax
0x18003c377  lea     rdx, aLdapCompConnec; "ldap_comp connection 0x%x trouble with "...
0x18003c37e  mov     r8, rsi
0x18003c381  call    LDAPClientPrint
0x18003c386  jmp     loc_18003C4D8
0x18003c38b  test    r15b, r15b
0x18003c38e  jnz     loc_18003C471
0x18003c394  xor     r15d, r15d
0x18003c397  cmp     [rdi+0B9h], r15b
0x18003c39e  jz      loc_18003C474
0x18003c3a4  mov     byte ptr [rdi+10Dh], 1
0x18003c3ab  test    r14, r14
0x18003c3ae  jz      short loc_18003C3CC
0x18003c3b0  xor     edx, edx
0x18003c3b2  mov     r8d, 696E554Ch
0x18003c3b8  mov     rcx, r14; Src
0x18003c3bb  call    ldap_dup_stringW
0x18003c3c0  mov     [rdi+0C0h], rax
0x18003c3c7  test    rax, rax
0x18003c3ca  jz      short loc_18003C427
0x18003c3cc  test    ebx, ebx
0x18003c3ce  jnz     loc_18003C4D8
0x18003c3d4  mov     rbx, [rsp+78h+arg_20]
0x18003c3dc  test    rbp, rbp
0x18003c3df  jnz     short loc_18003C3EA
0x18003c3e1  test    rbx, rbx
0x18003c3e4  jz      loc_18003C4B4
0x18003c3ea  xor     edx, edx
0x18003c3ec  mov     r8d, 696E554Ch
0x18003c3f2  mov     rcx, r12; Src
0x18003c3f5  call    ldap_dup_stringW
0x18003c3fa  mov     [rdi+0E8h], rax
0x18003c401  test    rax, rax
0x18003c404  jz      short loc_18003C427
0x18003c406  test    rbp, rbp
0x18003c409  jz      short loc_18003C431
0x18003c40b  xor     edx, edx
0x18003c40d  mov     r8d, 696E554Ch
0x18003c413  mov     rcx, rbp; Src
0x18003c416  call    ldap_dup_stringW
0x18003c41b  mov     [rdi+0F0h], rax
0x18003c422  test    rax, rax
0x18003c425  jnz     short loc_18003C431
0x18003c427  mov     ebx, 5Ah ; 'Z'
0x18003c42c  jmp     loc_18003C4D8
0x18003c431  test    rbx, rbx
0x18003c434  jz      short loc_18003C4B4
0x18003c436  cmp     [rbx+8], r15
0x18003c43a  jz      short loc_18003C4B4
0x18003c43c  mov     ecx, [rbx]
0x18003c43e  test    ecx, ecx
0x18003c440  jz      short loc_18003C4B4
0x18003c442  mov     edx, 6164434Ch
0x18003c447  call    ldapMalloc
0x18003c44c  mov     [rdi+100h], rax
0x18003c453  test    rax, rax
0x18003c456  jz      short loc_18003C427
0x18003c458  mov     r8d, [rbx]; Size
0x18003c45b  mov     rcx, rax; void *
0x18003c45e  mov     rdx, [rbx+8]; Src
0x18003c462  call    memcpy_0
0x18003c467  mov     eax, [rbx]
0x18003c469  mov     [rdi+0F8h], eax
0x18003c46f  jmp     short loc_18003C4B4
0x18003c471  xor     r15d, r15d
0x18003c474  mov     rcx, [rsp+78h+arg_20]
0x18003c47c  mov     [rdi+10Dh], r15b
0x18003c483  mov     [rdi+0C0h], r14
0x18003c48a  mov     [rdi+0E8h], r12
0x18003c491  mov     [rdi+0F0h], rbp
0x18003c498  test    rcx, rcx
0x18003c49b  jz      short loc_18003C4B0
0x18003c49d  mov     rax, [rcx+8]
0x18003c4a1  mov     [rdi+100h], rax
0x18003c4a8  mov     eax, [rcx]
0x18003c4aa  mov     [rdi+0F8h], eax
0x18003c4b0  test    ebx, ebx
0x18003c4b2  jnz     short loc_18003C4D8
0x18003c4b4  mov     r9, [rdi+0C0h]; unsigned __int16 *
0x18003c4bb  lea     r8, [rdi+0A0h]; struct CLdapBer **
0x18003c4c2  mov     rdx, rsi; struct ldap_connection *
0x18003c4c5  mov     [rsp+78h+var_58], r15d; int
0x18003c4ca  mov     rcx, rdi; struct ldap_request *
0x18003c4cd  call    ?SendLdapCompare@@YAKPEAUldap_request@@PEAUldap_connection@@PEAPEAVCLdapBer@@PEAGJ@Z; SendLdapCompare(ldap_request *,ldap_connection *,CLdapBer * *,ushort *,long)
0x18003c4d2  mov     ebx, eax
0x18003c4d4  test    eax, eax
0x18003c4d6  jz      short loc_18003C520
0x18003c4d8  cmp     cs:g_fTracingOn, r15d
0x18003c4df  jz      short loc_18003C50A
0x18003c4e1  cmp     cs:g_fProviderEnabled, r15d
0x18003c4e8  jz      short loc_18003C50A
0x18003c4ea  mov     ecx, 100000h
0x18003c4ef  test    cs:g_ulTraceFlags, rcx
0x18003c4f6  jz      short loc_18003C50A
0x18003c4f8  mov     r9d, ebx
0x18003c4fb  lea     rdx, aLdapCompareCon_0; "ldap_compare connection 0x%x errored wi"...
0x18003c502  mov     r8, rsi
0x18003c505  call    LDAPClientPrint
0x18003c50a  mov     edx, ebx
0x18003c50c  mov     rcx, rsi
0x18003c50f  or      r13d, 0FFFFFFFFh
0x18003c513  call    SetConnectionError
0x18003c518  mov     rcx, rdi
0x18003c51b  call    CloseLdapRequest
0x18003c520  mov     rax, [rsp+78h+arg_48]
0x18003c528  lea     rsi, [rdi+30h]
0x18003c52c  mov     rcx, rsi; lpCriticalSection
0x18003c52f  mov     [rax], r13d
0x18003c532  call    cs:__imp_EnterCriticalSection
0x18003c539  nop     dword ptr [rax+rax+00h]
0x18003c53e  dec     dword ptr [rdi+10h]
0x18003c541  cmp     cs:g_fTracingOn, r15d
0x18003c548  jz      short loc_18003C573
0x18003c54a  cmp     cs:g_fProviderEnabled, r15d
0x18003c551  jz      short loc_18003C573
0x18003c553  mov     ecx, 4
0x18003c558  test    byte ptr cs:g_ulTraceFlags, cl
0x18003c55e  jz      short loc_18003C573
0x18003c560  mov     r9d, [rdi+10h]
0x18003c564  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x18003c56b  mov     r8, rdi
0x18003c56e  call    LDAPClientPrint
0x18003c573  mov     rcx, rsi; lpCriticalSection
0x18003c576  cmp     [rdi+10h], r15d
0x18003c57a  jnz     short loc_18003C594
0x18003c57c  call    cs:__imp_LeaveCriticalSection
0x18003c583  nop     dword ptr [rax+rax+00h]
0x18003c588  xor     edx, edx
0x18003c58a  mov     rcx, rdi
0x18003c58d  call    DereferenceLdapRequest2
0x18003c592  jmp     short loc_18003C5A0
0x18003c594  call    cs:__imp_LeaveCriticalSection
0x18003c59b  nop     dword ptr [rax+rax+00h]
0x18003c5a0  mov     eax, ebx
0x18003c5a2  add     rsp, 38h
0x18003c5a6  pop     r15
0x18003c5a8  pop     r14
0x18003c5aa  pop     r13
0x18003c5ac  pop     r12
0x18003c5ae  pop     rdi
0x18003c5af  pop     rsi
0x18003c5b0  pop     rbp
0x18003c5b1  pop     rbx
0x18003c5b2  retn
```
