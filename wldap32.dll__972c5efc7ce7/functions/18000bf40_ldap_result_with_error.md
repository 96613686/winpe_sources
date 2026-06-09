# ldap_result_with_error

- ea: `0x18000bf40`
- end: `0x18000c8be`
- name: `ldap_result_with_error`
- size: `2430`
- prototype: ``
- caller_count: `22`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000bbf0`
- `0x1800153c0`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18001f1d0`
- `0x18002a4f0`
- `0x18003a9b0`
- `0x18003abb0`
- `0x18003ce30`
- `0x18003d0d0`
- `0x18003ea40`
- `0x18003ec30`
- `0x18003f760`
- `0x18003f970`
- `0x180040b10`
- `0x180040d10`
- `0x180047930`
- `0x180047a80`
- `0x180047f80`
- `0x180048210`
- `0x180048d40`
- `0x18004b28c`

## callees

- `0x1800018d0`
- `0x1800037a8`
- `0x180004e60`
- `0x180006510`
- `0x180008710`
- `0x18000adb0`
- `0x18000bf40`
- `0x18000c8c4`
- `0x18000cad0`
- `0x18000cda0`
- `0x180014460`
- `0x1800147f0`
- `0x18002a284`
- `0x180045de8`
- `0x180046aa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c0f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c19d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c1dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c83e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c0f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c19d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c1dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c3bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c83e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c128`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c1c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c206`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c409`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c424`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c463`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c574`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c64d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c88f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c8ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c128`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c1c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c206`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c409`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c424`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c463`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c574`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c64d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c88f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c8ad`

## pseudocode

```c
__int64 __fastcall ldap_result_with_error(
        struct ldap_connection *a1,
        unsigned int a2,
        unsigned int a3,
        int *a4,
        LDAPMessage **a5,
        LDAPMessage **a6)
{
  LDAPMessage **v6; // rbx
  __int64 v7; // r13
  struct ldap_connection *v11; // r12
  LDAPMessage **v12; // r15
  unsigned int v13; // esi
  unsigned int v14; // ebp
  __int64 v15; // rax
  __int64 v16; // rdi
  struct ldap_connection *v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // esi
  bool v22; // zf
  LDAPMessage *v23; // rdx
  LDAPMessage *v25; // rsi
  struct ldap_connection *v26; // rbp
  CLdapBer *v27; // rcx
  int v28; // ecx
  __int64 LdapRequest; // rax
  __int64 v30; // rbp
  struct _RTL_CRITICAL_SECTION *v31; // rcx
  struct _RTL_CRITICAL_SECTION *v32; // rcx
  LDAPMessage *v33; // r9
  LDAPMessage *v34; // rcx
  ULONG lm_msgtype; // eax
  unsigned int v36; // esi
  struct _RTL_CRITICAL_SECTION *v37; // rcx
  struct ldap_connection *ConnectionPointer; // rax
  __int64 v39; // r8
  unsigned int v40; // r8d
  __int64 v41; // rcx
  struct _RTL_CRITICAL_SECTION *v42; // rcx
  unsigned int v43; // [rsp+50h] [rbp-68h]
  LDAPMessage *res; // [rsp+58h] [rbp-60h] BYREF
  struct ldap_connection *v45; // [rsp+60h] [rbp-58h]
  LDAPMessage *v46; // [rsp+68h] [rbp-50h]

  v6 = a5;
  v7 = 0;
  res = 0;
  v11 = a1;
  if ( !a5 )
    return 89;
  v12 = a6;
  *a5 = 0;
  if ( v12 )
    *v12 = 0;
  if ( a3 < 2 || (v43 = 1, a3 == 2) )
    v43 = a3;
  if ( a1 )
  {
    if ( a2 != -1 )
    {
      LdapRequest = FindLdapRequest(a2);
      v30 = LdapRequest;
      if ( LdapRequest )
      {
        if ( *(_QWORD *)(LdapRequest + 216) )
        {
          v39 = *(_QWORD *)(LdapRequest + 40);
          if ( v39 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
              LDAPClientPrint(0x8000, "Getting data for connection 0x%x instead of 0x%x\n", v39, (_DWORD)v11);
            v11 = *(struct ldap_connection **)(v30 + 40);
          }
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v30 + 48));
        --*(_DWORD *)(v30 + 16);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v30, *(_DWORD *)(v30 + 16));
        v31 = (struct _RTL_CRITICAL_SECTION *)(v30 + 48);
        if ( *(_DWORD *)(v30 + 16) )
        {
          LeaveCriticalSection(v31);
        }
        else
        {
          LeaveCriticalSection(v31);
          DereferenceLdapRequest2((__int64 *)v30, 0);
        }
      }
    }
  }
  if ( a4 )
  {
    v28 = *a4;
    if ( *a4 || a4[1] )
    {
      v36 = (int)((unsigned __int64)(274877907LL * a4[1]) >> 32) >> 6;
      v13 = 1000 * v28 + (v36 >> 31) + v36;
    }
    else
    {
      v13 = 0;
    }
  }
  else
  {
    v13 = -1;
  }
  LODWORD(a5) = v13;
  v14 = 0;
  if ( a2 != -1 )
    v14 = a2;
  v15 = FindLdapRequest(v14);
  v16 = v15;
  if ( v14 && !v15 )
  {
    SetConnectionError(v11, 89);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
      LDAPClientPrint(1024, "ldap_result couldn't find request for msgid 0x%x\n", v14);
    return 89;
  }
  while ( 1 )
  {
    if ( !v16 || (v17 = *(struct ldap_connection **)(v16 + 40)) == 0 || *(_QWORD *)(v16 + 216) )
      v17 = v11;
    v18 = LdapWaitForResponseFromServer(v17, (struct ldap_request *)v16, v13, v43, &res, 0);
    v21 = v18;
    if ( !res )
      break;
    v25 = 0;
    v46 = 0;
    if ( v11 )
    {
      v45 = v11;
    }
    else
    {
      ConnectionPointer = (struct ldap_connection *)GetConnectionPointer(res->Connection, v19, v20);
      v45 = ConnectionPointer;
      v7 = (__int64)ConnectionPointer;
      if ( !ConnectionPointer && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
        LDAPClientPrint(1024, "resultConn NULL because connection handle 0x%x was unbound\n", res->Connection);
      else
        v45 = ConnectionPointer;
    }
    if ( !v16 )
      v16 = FindLdapRequest(res->lm_msgid);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
      LDAPClientPrint(1024, "ldap_result found results at 0x%x for request 0x%x msgid 0x%x\n", (_DWORD)res, v16, v14);
    if ( !v16 || !*(_BYTE *)(v16 + 185) || !v45 )
      goto LABEL_28;
    if ( !a3 && res->lm_msgtype == 101 && *(_WORD *)(v16 + 182) )
    {
      ldap_msgfree(res);
      res = 0;
      v13 = (unsigned int)a5;
    }
    else
    {
      v13 = (unsigned int)a5;
      if ( (unsigned int)HandleReferrals(v45, &res, v16, (unsigned int)a5) && res )
      {
        v25 = v46;
LABEL_28:
        if ( v12 || v16 )
        {
          v33 = res;
          v34 = 0;
          while ( v33 )
          {
            lm_msgtype = v33->lm_msgtype;
            if ( lm_msgtype != 100 && lm_msgtype != 115 )
            {
              v25 = v33;
              if ( v33->lm_eom )
              {
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000) != 0 )
                  LDAPClientPrint(4096, "ldap_result found EOM marker for req 0x%x, message 0x%x\n", v16, (_DWORD)v33);
                goto LABEL_64;
              }
            }
            v34 = v33;
            v33 = v33->lm_chain;
          }
          if ( !v25 )
            v25 = v34;
LABEL_64:
          if ( v12 )
            *v12 = v25;
        }
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40) != 0 )
        {
          v40 = v14;
          v26 = v45;
          LdapSpewSearchResults((struct ldap_request *)v16, v45, v40, res);
        }
        else
        {
          v26 = v45;
        }
        if ( v16 )
        {
          if ( !*(_BYTE *)(v16 + 190) )
          {
            v27 = (CLdapBer *)_InterlockedExchange64((volatile __int64 *)(v16 + 160), 0);
            if ( v27 )
              CLdapBer::`scalar deleting destructor'(v27);
          }
        }
        if ( v25 && v25->lm_eom == 1 && v16 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000) != 0 )
            LDAPClientPrint(4096, "ldap_result checking to close request 0x%x, message 0x%x\n", v16, (_DWORD)v25);
          EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 48));
          if ( *(_WORD *)(v16 + 182) || *(_QWORD *)(v16 + 24) )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000) != 0 )
              LDAPClientPrint(4096, "ldap_result responses outstanding for request 0x%x\n", v16);
            LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 48));
          }
          else
          {
            if ( g_fTracingOn && g_fProviderEnabled )
            {
              if ( (g_ulTraceFlags & 0x1000000) != 0 )
              {
                v41 = 0x1000000;
                goto LABEL_141;
              }
              if ( g_fProviderEnabled && (g_ulTraceFlags & 0x1000) != 0 )
              {
                v41 = 4096;
LABEL_141:
                LDAPClientPrint(v41, "ldap_result closing request 0x%x for message 0x%x\n", v16, *(_DWORD *)(v16 + 108));
              }
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 48));
            CloseLdapRequest(v16);
          }
        }
        SetConnectionError(v26, 0);
        v21 = 0;
        *v6 = res;
        goto LABEL_17;
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x800000) != 0 )
        LDAPClientPrint(0x800000, "ldap_result chasing referral for message 0x%x\n", v16);
      if ( !v14 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 48));
        --*(_DWORD *)(v16 + 16);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v16, *(_DWORD *)(v16 + 16));
        v37 = (struct _RTL_CRITICAL_SECTION *)(v16 + 48);
        if ( *(_DWORD *)(v16 + 16) )
        {
          LeaveCriticalSection(v37);
        }
        else
        {
          LeaveCriticalSection(v37);
          DereferenceLdapRequest2((__int64 *)v16, 0);
        }
        v16 = 0;
      }
    }
  }
  v22 = g_fTracingOn == 0;
  *v6 = 0;
  if ( !v22 && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
    LDAPClientPrint(0x2000000, "ldap_result connection 0x%x failed with 0x%x.\n", (_DWORD)v11, v18);
  if ( v21 == 81 )
  {
    v21 = 81;
    if ( v11 && !*((_BYTE *)v11 + 554) )
      v21 = 52;
    SetConnectionError(v11, v21);
  }
LABEL_17:
  if ( v16 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 48));
    --*(_DWORD *)(v16 + 16);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v16, *(_DWORD *)(v16 + 16));
    v32 = (struct _RTL_CRITICAL_SECTION *)(v16 + 48);
    if ( *(_DWORD *)(v16 + 16) )
    {
      LeaveCriticalSection(v32);
    }
    else
    {
      LeaveCriticalSection(v32);
      DereferenceLdapRequest2((__int64 *)v16, 0);
    }
  }
  v23 = *v6;
  if ( *v6 && v11 )
  {
    a5 = 0;
    LdapParseResult(v11, v23, 0, 0, &a5, 0, 0, 0, 0);
    InsertErrorMessage((__int64)v11, (__int64)a5);
  }
  if ( v7 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 512));
    --*(_DWORD *)v7;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", v7, *(_DWORD *)v7);
    v42 = (struct _RTL_CRITICAL_SECTION *)(v7 + 512);
    if ( *(_DWORD *)v7 )
    {
      LeaveCriticalSection(v42);
    }
    else
    {
      LeaveCriticalSection(v42);
      DereferenceLdapConnection2(v7, 1);
    }
  }
  return v21;
}

```

## disassembly

```asm
0x18000bf40  push    rbx
0x18000bf42  push    rbp
0x18000bf43  push    rsi
0x18000bf44  push    rdi
0x18000bf45  push    r12
0x18000bf47  push    r13
0x18000bf49  push    r14
0x18000bf4b  push    r15
0x18000bf4d  sub     rsp, 78h
0x18000bf51  mov     rbx, [rsp+0B8h+arg_20]
0x18000bf59  xor     r13d, r13d
0x18000bf5c  mov     [rsp+0B8h+res], r13
0x18000bf61  mov     rsi, r9
0x18000bf64  mov     r14d, r8d
0x18000bf67  mov     edi, edx
0x18000bf69  mov     r12, rcx
0x18000bf6c  test    rbx, rbx
0x18000bf6f  jz      loc_18000C337
0x18000bf75  mov     r15, [rsp+0B8h+arg_28]
0x18000bf7d  mov     [rbx], r13
0x18000bf80  test    r15, r15
0x18000bf83  jz      short loc_18000BF88
0x18000bf85  mov     [r15], r13
0x18000bf88  cmp     r14d, 2
0x18000bf8c  jnb     loc_18000C43F
0x18000bf92  mov     [rsp+0B8h+var_68], r14d
0x18000bf97  test    r12, r12
0x18000bf9a  jnz     loc_18000C170
0x18000bfa0  test    rsi, rsi
0x18000bfa3  jnz     loc_18000C155
0x18000bfa9  mov     esi, 0FFFFFFFFh
0x18000bfae  cmp     edi, 0FFFFFFFFh
0x18000bfb1  mov     dword ptr [rsp+0B8h+arg_20], esi
0x18000bfb8  mov     ebp, r13d
0x18000bfbb  cmovnz  ebp, edi
0x18000bfbe  mov     ecx, ebp
0x18000bfc0  call    FindLdapRequest
0x18000bfc5  mov     rdi, rax
0x18000bfc8  test    ebp, ebp
0x18000bfca  jnz     loc_18000C2EE
0x18000bfd0  test    rdi, rdi
0x18000bfd3  jnz     loc_18000C341
0x18000bfd9  mov     rcx, r12; struct ldap_connection *
0x18000bfdc  mov     r9d, [rsp+0B8h+var_68]; unsigned int
0x18000bfe1  lea     rax, [rsp+0B8h+res]
0x18000bfe6  mov     [rsp+0B8h+var_90], 0; char
0x18000bfeb  mov     r8d, esi; unsigned int
0x18000bfee  mov     rdx, rdi; struct ldap_request *
0x18000bff1  mov     [rsp+0B8h+var_98], rax; struct ldapmsg **
0x18000bff6  call    ?LdapWaitForResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@E@Z; LdapWaitForResponseFromServer(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar)
0x18000bffb  mov     rcx, [rsp+0B8h+res]
0x18000c000  mov     esi, eax
0x18000c002  test    rcx, rcx
0x18000c005  jnz     short loc_18000C051
0x18000c007  cmp     cs:g_fTracingOn, ecx
0x18000c00d  mov     [rbx], rcx
0x18000c010  jnz     loc_18000C79C
0x18000c016  cmp     esi, 51h ; 'Q'
0x18000c019  jz      loc_18000C7D6
0x18000c01f  test    rdi, rdi
0x18000c022  jnz     loc_18000C1D8
0x18000c028  mov     rdx, [rbx]
0x18000c02b  test    rdx, rdx
0x18000c02e  jnz     loc_18000C269
0x18000c034  test    r13, r13
0x18000c037  jnz     loc_18000C837
0x18000c03d  mov     eax, esi
0x18000c03f  add     rsp, 78h
0x18000c043  pop     r15
0x18000c045  pop     r14
0x18000c047  pop     r13
0x18000c049  pop     r12
0x18000c04b  pop     rdi
0x18000c04c  pop     rsi
0x18000c04d  pop     rbp
0x18000c04e  pop     rbx
0x18000c04f  retn
0x18000c051  xor     esi, esi
0x18000c053  mov     [rsp+0B8h+var_50], rsi
0x18000c058  test    r12, r12
0x18000c05b  jz      loc_18000C4D0
0x18000c061  mov     [rsp+0B8h+var_58], r12
0x18000c066  test    rdi, rdi
0x18000c069  jz      loc_18000C47E
0x18000c06f  cmp     cs:g_fTracingOn, esi
0x18000c075  jnz     loc_18000C5D7
0x18000c07b  test    rdi, rdi
0x18000c07e  jz      short loc_18000C08D
0x18000c080  cmp     [rdi+0B9h], sil
0x18000c087  jnz     loc_18000C361
0x18000c08d  test    r15, r15
0x18000c090  jnz     loc_18000C217
0x18000c096  test    rdi, rdi
0x18000c099  jnz     loc_18000C217
0x18000c09f  cmp     cs:g_fTracingOn, 0
0x18000c0a6  jnz     loc_18000C697
0x18000c0ac  mov     rbp, [rsp+0B8h+var_58]
0x18000c0b1  test    rdi, rdi
0x18000c0b4  jz      short loc_18000C0D1
0x18000c0b6  cmp     byte ptr [rdi+0BEh], 0
0x18000c0bd  jnz     short loc_18000C0D1
0x18000c0bf  xor     ecx, ecx
0x18000c0c1  xchg    rcx, [rdi+0A0h]; this
0x18000c0c8  test    rcx, rcx
0x18000c0cb  jnz     loc_18000C6CE
0x18000c0d1  test    rsi, rsi
0x18000c0d4  jz      short loc_18000C13C
0x18000c0d6  cmp     byte ptr [rsi+3Fh], 1
0x18000c0da  jnz     short loc_18000C13C
0x18000c0dc  test    rdi, rdi
0x18000c0df  jz      short loc_18000C13C
0x18000c0e1  cmp     cs:g_fTracingOn, 0
0x18000c0e8  jnz     loc_18000C6D8
0x18000c0ee  lea     rcx, [rdi+30h]; lpCriticalSection
0x18000c0f2  call    cs:__imp_EnterCriticalSection
0x18000c0f9  nop     dword ptr [rax+rax+00h]
0x18000c0fe  cmp     word ptr [rdi+0B6h], 0
0x18000c106  jnz     loc_18000C452
0x18000c10c  cmp     qword ptr [rdi+18h], 0
0x18000c111  jnz     loc_18000C452
0x18000c117  cmp     cs:g_fTracingOn, 0
0x18000c11e  jnz     loc_18000C712
0x18000c124  lea     rcx, [rdi+30h]; lpCriticalSection
0x18000c128  call    cs:__imp_LeaveCriticalSection
0x18000c12f  nop     dword ptr [rax+rax+00h]
0x18000c134  mov     rcx, rdi
0x18000c137  call    CloseLdapRequest
0x18000c13c  xor     edx, edx
0x18000c13e  mov     rcx, rbp
0x18000c141  call    SetConnectionError
0x18000c146  mov     rax, [rsp+0B8h+res]
0x18000c14b  xor     esi, esi
0x18000c14d  mov     [rbx], rax
0x18000c150  jmp     loc_18000C01F
0x18000c155  mov     ecx, [rsi]
0x18000c157  test    ecx, ecx
0x18000c159  jnz     loc_18000C2CD
0x18000c15f  cmp     [rsi+4], ecx
0x18000c162  jnz     loc_18000C2CD
0x18000c168  mov     esi, r13d
0x18000c16b  jmp     loc_18000BFAE
0x18000c170  cmp     edi, 0FFFFFFFFh
0x18000c173  jz      loc_18000BFA0
0x18000c179  mov     ecx, edi
0x18000c17b  call    FindLdapRequest
0x18000c180  mov     rbp, rax
0x18000c183  test    rax, rax
0x18000c186  jz      loc_18000BFA0
0x18000c18c  cmp     [rax+0D8h], r13
0x18000c193  jnz     loc_18000C4F4
0x18000c199  lea     rcx, [rbp+30h]; lpCriticalSection
0x18000c19d  call    cs:__imp_EnterCriticalSection
0x18000c1a4  nop     dword ptr [rax+rax+00h]
0x18000c1a9  dec     dword ptr [rbp+10h]
0x18000c1ac  cmp     cs:g_fTracingOn, r13d
0x18000c1b3  jnz     loc_18000C53D
0x18000c1b9  lea     rcx, [rbp+30h]; lpCriticalSection
0x18000c1bd  cmp     [rbp+10h], r13d
0x18000c1c1  jz      loc_18000C574
0x18000c1c7  call    cs:__imp_LeaveCriticalSection
0x18000c1ce  nop     dword ptr [rax+rax+00h]
0x18000c1d3  jmp     loc_18000BFA0
0x18000c1d8  lea     rcx, [rdi+30h]; lpCriticalSection
0x18000c1dc  call    cs:__imp_EnterCriticalSection
0x18000c1e3  nop     dword ptr [rax+rax+00h]
0x18000c1e8  dec     dword ptr [rdi+10h]
0x18000c1eb  cmp     cs:g_fTracingOn, 0
0x18000c1f2  jnz     loc_18000C800
0x18000c1f8  cmp     dword ptr [rdi+10h], 0
0x18000c1fc  lea     rcx, [rdi+30h]; lpCriticalSection
0x18000c200  jz      loc_18000C424
0x18000c206  call    cs:__imp_LeaveCriticalSection
0x18000c20d  nop     dword ptr [rax+rax+00h]
0x18000c212  jmp     loc_18000C028
0x18000c217  mov     r9, [rsp+0B8h+res]
0x18000c21c  xor     ecx, ecx
0x18000c21e  mov     rax, rsi
0x18000c221  test    r9, r9
0x18000c224  jz      loc_18000C4C4
0x18000c22a  mov     eax, [r9+4]
0x18000c22e  cmp     eax, 64h ; 'd'
0x18000c231  jnz     short loc_18000C23C
0x18000c233  mov     rcx, r9
0x18000c236  mov     r9, [r9+10h]
0x18000c23a  jmp     short loc_18000C21E
0x18000c23c  cmp     eax, 73h ; 's'
0x18000c23f  jz      short loc_18000C233
0x18000c241  cmp     byte ptr [r9+3Fh], 0
0x18000c246  mov     rsi, r9
0x18000c249  jz      short loc_18000C233
0x18000c24b  cmp     cs:g_fTracingOn, 0
0x18000c252  jnz     loc_18000C660
0x18000c258  test    r15, r15
0x18000c25b  jz      loc_18000C09F
0x18000c261  mov     [r15], rsi
0x18000c264  jmp     loc_18000C09F
0x18000c269  test    r12, r12
0x18000c26c  jz      loc_18000C034
0x18000c272  mov     [rsp+0B8h+var_78], 0
0x18000c27a  lea     rax, [rsp+0B8h+arg_20]
0x18000c282  mov     [rsp+0B8h+var_80], 0
0x18000c287  xor     r9d, r9d
0x18000c28a  mov     [rsp+0B8h+var_88], 0
0x18000c293  xor     r8d, r8d
0x18000c296  mov     qword ptr [rsp+0B8h+var_90], 0
0x18000c29f  mov     rcx, r12
0x18000c2a2  mov     [rsp+0B8h+var_98], rax
0x18000c2a7  mov     [rsp+0B8h+arg_20], 0
0x18000c2b3  call    LdapParseResult
0x18000c2b8  mov     rdx, [rsp+0B8h+arg_20]
0x18000c2c0  mov     rcx, r12
0x18000c2c3  call    InsertErrorMessage
0x18000c2c8  jmp     loc_18000C034
0x18000c2cd  mov     eax, 10624DD3h
0x18000c2d2  imul    dword ptr [rsi+4]
0x18000c2d5  mov     esi, edx
0x18000c2d7  sar     esi, 6
0x18000c2da  mov     eax, esi
0x18000c2dc  shr     eax, 1Fh
0x18000c2df  add     esi, eax
0x18000c2e1  imul    eax, ecx, 3E8h
0x18000c2e7  add     esi, eax
0x18000c2e9  jmp     loc_18000BFAE
0x18000c2ee  test    rax, rax
0x18000c2f1  jnz     loc_18000BFD0
0x18000c2f7  mov     edx, 59h ; 'Y'
0x18000c2fc  mov     rcx, r12
0x18000c2ff  call    SetConnectionError
0x18000c304  cmp     cs:g_fTracingOn, 0
0x18000c30b  jz      short loc_18000C337
0x18000c30d  cmp     cs:g_fProviderEnabled, 0
0x18000c314  jz      short loc_18000C337
0x18000c316  test    cs:g_ulTraceFlags, 400h
0x18000c321  jz      short loc_18000C337
0x18000c323  mov     r8d, ebp
0x18000c326  lea     rdx, aLdapResultCoul; "ldap_result couldn't find request for m"...
0x18000c32d  mov     ecx, 400h
0x18000c332  call    LDAPClientPrint
0x18000c337  mov     eax, 59h ; 'Y'
0x18000c33c  jmp     loc_18000C03F
0x18000c341  mov     rcx, [rdi+28h]
0x18000c345  test    rcx, rcx
0x18000c348  jz      loc_18000BFD9
0x18000c34e  cmp     qword ptr [rdi+0D8h], 0
0x18000c356  jz      loc_18000BFDC
0x18000c35c  jmp     loc_18000BFD9
0x18000c361  mov     rax, [rsp+0B8h+var_58]
0x18000c366  test    rax, rax
0x18000c369  jz      loc_18000C08D
0x18000c36f  test    r14d, r14d
0x18000c372  jz      loc_18000C492
0x18000c378  mov     esi, dword ptr [rsp+0B8h+arg_20]
0x18000c37f  lea     rdx, [rsp+0B8h+res]
0x18000c384  mov     r9d, esi
0x18000c387  mov     r8, rdi
0x18000c38a  mov     rcx, rax; struct ldap_connection *
0x18000c38d  call    HandleReferrals
0x18000c392  test    eax, eax
0x18000c394  jz      short loc_18000C3A2
0x18000c396  cmp     [rsp+0B8h+res], 0
0x18000c39c  jnz     loc_18000C474
0x18000c3a2  cmp     cs:g_fTracingOn, 0
0x18000c3a9  jnz     loc_18000C616
0x18000c3af  test    ebp, ebp
0x18000c3b1  jnz     loc_18000BFD0
0x18000c3b7  lea     rcx, [rdi+30h]; lpCriticalSection
0x18000c3bb  call    cs:__imp_EnterCriticalSection
0x18000c3c2  nop     dword ptr [rax+rax+00h]
0x18000c3c7  dec     dword ptr [rdi+10h]
0x18000c3ca  cmp     cs:g_fTracingOn, ebp
0x18000c3d0  jz      short loc_18000C3FB
0x18000c3d2  cmp     cs:g_fProviderEnabled, ebp
0x18000c3d8  jz      short loc_18000C3FB
0x18000c3da  test    byte ptr cs:g_ulTraceFlags, 4
0x18000c3e1  jz      short loc_18000C3FB
0x18000c3e3  mov     r9d, [rdi+10h]
0x18000c3e7  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x18000c3ee  mov     r8, rdi
0x18000c3f1  mov     ecx, 4
0x18000c3f6  call    LDAPClientPrint
0x18000c3fb  cmp     dword ptr [rdi+10h], 0
0x18000c3ff  lea     rcx, [rdi+30h]; lpCriticalSection
0x18000c403  jnz     loc_18000C64D
0x18000c409  call    cs:__imp_LeaveCriticalSection
0x18000c410  nop     dword ptr [rax+rax+00h]
0x18000c415  xor     edx, edx
0x18000c417  mov     rcx, rdi
0x18000c41a  call    DereferenceLdapRequest2
0x18000c41f  jmp     loc_18000C659
0x18000c424  call    cs:__imp_LeaveCriticalSection
0x18000c42b  nop     dword ptr [rax+rax+00h]
0x18000c430  xor     edx, edx
0x18000c432  mov     rcx, rdi
0x18000c435  call    DereferenceLdapRequest2
0x18000c43a  jmp     loc_18000C028
0x18000c43f  mov     [rsp+0B8h+var_68], 1
0x18000c447  jnz     loc_18000BF97
0x18000c44d  jmp     loc_18000BF92
0x18000c452  cmp     cs:g_fTracingOn, 0
0x18000c459  jnz     loc_18000C765
  ... truncated ...
```
