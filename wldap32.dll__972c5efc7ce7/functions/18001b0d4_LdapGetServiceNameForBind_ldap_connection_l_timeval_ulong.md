# LdapGetServiceNameForBind(ldap_connection *,l_timeval *,ulong)

- ea: `0x18001b0d4`
- end: `0x18001b960`
- name: `?LdapGetServiceNameForBind@@YAKPEAUldap_connection@@PEAUl_timeval@@K@Z`
- size: `2188`
- prototype: `unsigned int __fastcall(struct ldap_connection *, struct l_timeval *, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800164a0`

## callees

- `0x1800037a8`
- `0x180004740`
- `0x180005170`
- `0x1800061a0`
- `0x180006510`
- `0x18000adb0`
- `0x18000b440`
- `0x18000bf40`
- `0x18000cda0`
- `0x1800147f0`
- `0x180015640`
- `0x18001611c`
- `0x180016360`
- `0x18001b0d4`
- `0x18001ba9c`
- `0x18001ce90`
- `0x180020970`
- `0x180022e80`
- `0x18002b754`
- `0x180032bd8`
- `0x180034510`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsupr_s` at `0x18001b204`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr_s` at `0x18001b204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b459`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b459`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4bb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b5fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b649`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b6c1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b732`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b5fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b649`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b6c1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001b732`
- `DSPARSE!DsMakeSpnW` at `0x18001b2fb`
- `DSPARSE!DsMakeSpnW` at `0x18001b2fb`

## pseudocode

```c
__int64 __fastcall LdapGetServiceNameForBind(struct ldap_connection *a1, struct l_timeval *a2, int a3)
{
  WCHAR *v3; // rsi
  LDAP *v6; // r13
  __int64 v8; // rdx
  WCHAR *pszSpn; // r14
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // eax
  size_t v13; // rbx
  int v14; // r14d
  WCHAR *v15; // rax
  size_t v16; // rsi
  size_t v17; // r8
  WCHAR *v18; // rbx
  __int16 v19; // cx
  USHORT v20; // bx
  DWORD SpnW; // eax
  const wchar_t *v22; // rax
  bool v23; // zf
  __int64 ConnectionPointer; // rax
  _DWORD *v25; // rbx
  int v26; // edx
  ULONG v27; // eax
  unsigned int v28; // esi
  ULONG v29; // r15d
  __int64 v30; // r8
  struct _RTL_CRITICAL_SECTION *v31; // rcx
  int v32; // edx
  int v33; // ecx
  int v34; // eax
  __int64 record; // r12
  const WCHAR *Attribute; // rbx
  __int64 v37; // rsi
  unsigned int v38; // r14d
  __int64 v39; // rbx
  const WCHAR *v40; // r8
  const WCHAR *v41; // r8
  const WCHAR *v42; // r8
  __int64 v43; // r9
  const char *v44; // rdx
  char v46; // [rsp+70h] [rbp-49h]
  char v47; // [rsp+71h] [rbp-48h]
  char v48; // [rsp+72h] [rbp-47h]
  PCHAR *vals; // [rsp+78h] [rbp-41h] BYREF
  int v50; // [rsp+80h] [rbp-39h]
  LDAPMessage *res; // [rsp+88h] [rbp-31h] BYREF
  WCHAR *v52; // [rsp+90h] [rbp-29h]
  DWORD pcSpnLength; // [rsp+98h] [rbp-21h] BYREF
  int v54; // [rsp+9Ch] [rbp-1Dh]
  __int64 v55; // [rsp+A0h] [rbp-19h]
  LPWSTR v56; // [rsp+A8h] [rbp-11h]
  unsigned __int16 *v57[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v58; // [rsp+C0h] [rbp+7h]

  v3 = 0;
  res = 0;
  v46 = 0;
  pcSpnLength = 4096;
  v6 = (LDAP *)*((_QWORD *)a1 + 56);
  v54 = *((_DWORD *)a1 + 271);
  v57[0] = L"supportedSASLMechanisms";
  v47 = 0;
  v48 = 0;
  v52 = 0;
  v57[1] = 0;
  v58 = 0;
  v56 = (LPWSTR)ldapMalloc(4096, 1718960716);
  pszSpn = v56;
  v10 = 1;
  if ( v56 )
  {
    v11 = *((_QWORD *)a1 + 53);
    if ( v11 )
    {
      v12 = strlenW(v11, v8, 1);
      v13 = v12;
      if ( v12 >= 512 )
        goto LABEL_25;
      v14 = 2 * v12 + 2;
      v15 = (WCHAR *)ldapMalloc((unsigned int)(2 * v14), 1718960716);
      v52 = v15;
      if ( !v15 )
        goto LABEL_25;
      v16 = v13;
      v17 = 2 * v13;
      v18 = v15;
      memcpy_0(v15, *((const void **)a1 + 53), v17);
      if ( (*((_DWORD *)a1 + 117) & 0x400) == 0 && a3 != 16518 )
      {
        v18[v16] = 64;
        memcpy_0(&v18[v16 + 1], *((const void **)a1 + 53), v16 * 2);
        _o__wcsupr_s(&v18[v16 + 1], v14);
      }
      pszSpn = v56;
      v3 = v18;
      v10 = 1;
    }
    else
    {
      v3 = (WCHAR *)*((_QWORD *)a1 + 52);
      v52 = v3;
    }
    v19 = *((_WORD *)a1 + 253);
    v20 = 0;
    if ( v19 != 389 && v19 != 636 )
    {
      v8 = 3268;
      if ( (unsigned __int16)(v19 - 3268) > 1u && a3 != 16518 )
        v20 = *((_WORD *)a1 + 253);
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
    {
      LDAPClientPrint(0x80000, "Connection->hostname is '%s'\n", *((const char **)a1 + 124));
      LDAPClientPrint(0x80000, "Connection->DnsSuppliedNAme is '%S'\n ", *((const wchar_t **)a1 + 52));
      LDAPClientPrint(0x80000, "Connection->DomainName is '%S'\n ", *((const wchar_t **)a1 + 53));
    }
    if ( v3 )
    {
      SpnW = DsMakeSpnW(L"ldap", v3, *((LPCWSTR *)a1 + 52), v20, 0, &pcSpnLength, pszSpn);
      v3 = 0;
      if ( !SpnW )
      {
        v22 = (const wchar_t *)ldap_dup_stringW(pszSpn);
        v23 = g_fTracingOn == 0;
        *((_QWORD *)a1 + 50) = v22;
        if ( !v23 && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
          LDAPClientPrint(0x80000, "LDAP: make spn returned '%S' with error %d\n", v22, 0);
      }
    }
  }
LABEL_25:
  *((_DWORD *)a1 + 271) &= 0xFFFFFF9D;
  LODWORD(vals) = (_DWORD)v3;
  ConnectionPointer = GetConnectionPointer(v6, v8, v10);
  v25 = (_DWORD *)ConnectionPointer;
  if ( ConnectionPointer )
  {
    res = (LDAPMessage *)v3;
    if ( a2 )
      v26 = a2->tv_sec + a2->tv_usec / 1000000;
    else
      v26 = *(_DWORD *)(ConnectionPointer + 1012);
    v27 = LdapSearch(
            (struct ldap_connection *)ConnectionPointer,
            0,
            0,
            (int)L"(objectclass=*)",
            v57,
            (int)v3,
            1,
            1,
            (struct ldapcontrolW **)v3,
            (struct ldapcontrolW **)v3,
            v26,
            (int)v3,
            (__int64)&vals);
    v28 = (unsigned int)vals;
    v29 = v27;
    v50 = v27;
    if ( (_DWORD)vals != -1 )
    {
      v29 = ldap_result_with_error((struct ldap_connection *)v25, (unsigned int)vals, (__int64)&res, 0);
      v50 = v29;
      if ( res )
      {
        v29 = ldap_result2error(v6, res, 0);
        v50 = v29;
      }
      else
      {
        LOBYTE(v30) = 1;
        LdapAbandon(v25, v28, v30);
        SetConnectionError(v25, v29);
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v25 + 128));
    --*v25;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v25, *v25);
    v31 = (struct _RTL_CRITICAL_SECTION *)(v25 + 128);
    if ( *v25 )
    {
      LeaveCriticalSection(v31);
      v50 = v29;
    }
    else
    {
      LeaveCriticalSection(v31);
      DereferenceLdapConnection2((__int64)v25, 1);
    }
  }
  else
  {
    v29 = 89;
    v50 = 89;
    SetConnectionError(0, 89);
  }
  v32 = g_fTracingOn;
  v33 = g_fProviderEnabled;
  v34 = g_ulTraceFlags;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 1) != 0 )
  {
    LDAPClientPrint(
      1,
      "ldap_search returned 0x%x for connection 0x%x: DN was %S. SearchScope was 0x%x.\n",
      v29,
      (_DWORD)v25,
      0,
      0);
    v32 = g_fTracingOn;
    v33 = g_fProviderEnabled;
    v34 = g_ulTraceFlags;
  }
  if ( res )
  {
    record = ldap_first_record(a1, res, 100);
    if ( record )
    {
      v55 = 0;
      Attribute = (const WCHAR *)LdapFirstAttribute(a1);
      if ( Attribute )
      {
        do
        {
          vals = 0;
          if ( (unsigned int)LdapGetValues(a1, 1, (__int64)&vals) )
            vals = 0;
          LODWORD(v37) = 0;
          if ( vals && *vals )
          {
            do
              v37 = (unsigned int)(v37 + 1);
            while ( vals[v37] );
          }
          if ( CompareStringW(0x400u, 1u, Attribute, -1, L"supportedSASLMechanisms", -1) == 2 )
          {
            v38 = 0;
            if ( (_DWORD)v37 )
            {
              v39 = 0;
              do
              {
                v40 = (const WCHAR *)vals[v39];
                if ( v40 && CompareStringW(0x400u, 1u, v40, -1, L"GSSAPI", -1) == 2 )
                {
                  v46 = 1;
                  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
                    LDAPClientPrint(0x80000, "ldapBind found GSSAPI auth type on connection 0x%x\n", a1);
                }
                else
                {
                  v41 = (const WCHAR *)vals[v39];
                  if ( v41 && CompareStringW(0x400u, 1u, v41, -1, L"GSS-SPNEGO", -1) == 2 )
                  {
                    v47 = 1;
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
                      LDAPClientPrint(0x80000, "ldapBind found GSS-SPNEGO auth type on connection 0x%x\n", a1);
                  }
                  else
                  {
                    v42 = (const WCHAR *)vals[v39];
                    if ( v42 )
                    {
                      if ( CompareStringW(0x400u, 1u, v42, -1, L"DIGEST-MD5", -1) == 2 )
                      {
                        v48 = 1;
                        if ( g_fTracingOn )
                        {
                          if ( g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
                            LDAPClientPrint(0x80000, "ldapBind found DIGEST auth type on connection 0x%x\n", a1);
                        }
                      }
                    }
                  }
                }
                ++v38;
                ++v39;
              }
              while ( v38 < (unsigned int)v37 );
            }
          }
          ldap_value_free(vals);
          LOBYTE(v43) = 1;
          Attribute = (const WCHAR *)LdapNextAttribute(a1, record, v55, v43);
        }
        while ( Attribute );
        v29 = v50;
      }
    }
    ldap_msgfree(res);
    v32 = g_fTracingOn;
    v33 = g_fProviderEnabled;
    v34 = g_ulTraceFlags;
  }
  *((_DWORD *)a1 + 271) = v54;
  if ( !v29 )
  {
    if ( v32 && v33 && (*(_QWORD *)&v34 & 0x80000LL) != 0 )
    {
      LDAPClientTraceEvent(0x80000, "ldap bind: Server is v3\n");
      v32 = g_fTracingOn;
      v33 = g_fProviderEnabled;
      v34 = g_ulTraceFlags;
    }
    *((_DWORD *)a1 + 50) = 3;
    if ( v47 )
    {
      if ( v46 )
      {
        *(_WORD *)((char *)a1 + 197) = 257;
        if ( !v32 || !v33 || (*(_QWORD *)&v34 & 0x80000LL) == 0 )
          goto LABEL_103;
        v44 = "ldap bind: Server supports both GSS-SPNEGO and GSSAPI\n";
      }
      else
      {
        *((_BYTE *)a1 + 198) = 1;
        if ( !v32 || !v33 || (*(_QWORD *)&v34 & 0x80000LL) == 0 )
          goto LABEL_103;
        v44 = "ldap bind: Server supports GSS-SPNEGO but not GSSAPI\n";
      }
    }
    else if ( v46 )
    {
      *((_BYTE *)a1 + 197) = 1;
      if ( !v32 || !v33 || (*(_QWORD *)&v34 & 0x80000LL) == 0 )
        goto LABEL_103;
      v44 = "ldap bind: Server supports GSSAPI but not GSS-SPNEGO\n";
    }
    else
    {
      if ( !v32 || !v33 || (*(_QWORD *)&v34 & 0x80000LL) == 0 )
        goto LABEL_103;
      v44 = "ldap bind: Server does not support GSSAPI or GSS-SPNEGO\n";
    }
    LDAPClientTraceEvent(0x80000, v44);
LABEL_103:
    *((_BYTE *)a1 + 199) = v48;
    goto LABEL_109;
  }
  if ( v32 && v33 && (*(_QWORD *)&v34 & 0x80000LL) != 0 )
    LDAPClientTraceEvent(0x80000, "ldap bind: Server is v2\n");
  *((_DWORD *)a1 + 50) = 2;
LABEL_109:
  if ( *((_QWORD *)a1 + 53) )
    ldapFree(v52, 1718960716);
  if ( v56 )
    ldapFree(v56, 1718960716);
  return v29;
}

```

## disassembly

```asm
0x18001b0d4  mov     [rsp-8+arg_10], rbx
0x18001b0d9  push    rbp
0x18001b0da  push    rsi
0x18001b0db  push    rdi
0x18001b0dc  push    r12
0x18001b0de  push    r13
0x18001b0e0  push    r14
0x18001b0e2  push    r15
0x18001b0e4  lea     rbp, [rsp-27h]
0x18001b0e9  sub     rsp, 0E0h
0x18001b0f0  mov     rax, cs:__security_cookie
0x18001b0f7  xor     rax, rsp
0x18001b0fa  mov     [rbp+57h+var_40], rax
0x18001b0fe  xor     esi, esi
0x18001b100  mov     rdi, rcx
0x18001b103  mov     r12, rdx
0x18001b106  mov     [rbp+57h+res], rsi
0x18001b10a  mov     ecx, 1000h
0x18001b10f  mov     [rbp+57h+var_A0], sil
0x18001b113  xorps   xmm0, xmm0
0x18001b116  mov     [rbp+57h+var_78], ecx
0x18001b119  mov     eax, [rdi+43Ch]
0x18001b11f  mov     edx, 6675424Ch
0x18001b124  mov     r13, [rdi+1C0h]
0x18001b12b  mov     r15d, r8d
0x18001b12e  mov     [rbp+57h+var_74], eax
0x18001b131  lea     rax, aSupportedsaslm; "supportedSASLMechanisms"
0x18001b138  mov     [rbp+57h+var_60], rax
0x18001b13c  mov     [rbp+57h+var_9F], sil
0x18001b140  mov     [rbp+57h+var_9E], sil
0x18001b144  mov     [rbp+57h+var_80], rsi
0x18001b148  mov     [rbp+57h+var_58], rsi
0x18001b14c  movups  [rbp+57h+var_50], xmm0
0x18001b150  call    ldapMalloc
0x18001b155  mov     [rbp+57h+var_68], rax
0x18001b159  mov     r14, rax
0x18001b15c  lea     r8d, [rsi+1]
0x18001b160  test    rax, rax
0x18001b163  jz      loc_18001B352
0x18001b169  mov     rcx, [rdi+1A8h]
0x18001b170  test    rcx, rcx
0x18001b173  jz      loc_18001B21F
0x18001b179  call    strlenW
0x18001b17e  movsxd  rbx, eax
0x18001b181  cmp     ebx, 200h
0x18001b187  jge     loc_18001B352
0x18001b18d  lea     r14d, ds:2[rbx*2]
0x18001b195  mov     edx, 6675424Ch
0x18001b19a  lea     ecx, [r14+r14]
0x18001b19e  call    ldapMalloc
0x18001b1a3  mov     [rbp+57h+var_80], rax
0x18001b1a7  test    rax, rax
0x18001b1aa  jz      loc_18001B352
0x18001b1b0  mov     rdx, [rdi+1A8h]; Src
0x18001b1b7  lea     rsi, [rbx+rbx]
0x18001b1bb  mov     r8, rsi; Size
0x18001b1be  mov     rcx, rax; void *
0x18001b1c1  mov     rbx, rax
0x18001b1c4  call    memcpy_0
0x18001b1c9  test    dword ptr [rdi+1D4h], 400h
0x18001b1d3  jnz     short loc_18001B210
0x18001b1d5  cmp     r15d, 4086h
0x18001b1dc  jz      short loc_18001B210
0x18001b1de  mov     word ptr [rsi+rbx], 40h ; '@'
0x18001b1e4  lea     rcx, [rbx+2]
0x18001b1e8  mov     rdx, [rdi+1A8h]; Src
0x18001b1ef  add     rcx, rsi; void *
0x18001b1f2  mov     r8, rsi; Size
0x18001b1f5  call    memcpy_0
0x18001b1fa  lea     rcx, [rbx+2]
0x18001b1fe  movsxd  rdx, r14d
0x18001b201  add     rcx, rsi
0x18001b204  call    cs:__imp__o__wcsupr_s
0x18001b20b  nop     dword ptr [rax+rax+00h]
0x18001b210  mov     r14, [rbp+57h+var_68]
0x18001b214  mov     rsi, rbx
0x18001b217  mov     r8d, 1
0x18001b21d  jmp     short loc_18001B22A
0x18001b21f  mov     rsi, [rdi+1A0h]
0x18001b226  mov     [rbp+57h+var_80], rsi
0x18001b22a  movzx   ecx, word ptr [rdi+1FAh]
0x18001b231  xor     ebx, ebx
0x18001b233  mov     eax, 185h
0x18001b238  cmp     cx, ax
0x18001b23b  jz      short loc_18001B263
0x18001b23d  mov     eax, 27Ch
0x18001b242  cmp     cx, ax
0x18001b245  jz      short loc_18001B263
0x18001b247  mov     edx, 0CC4h
0x18001b24c  movzx   eax, cx
0x18001b24f  sub     ax, dx
0x18001b252  cmp     ax, r8w
0x18001b256  jbe     short loc_18001B263
0x18001b258  cmp     r15d, 4086h
0x18001b25f  cmovnz  bx, cx
0x18001b263  cmp     cs:g_fTracingOn, 0
0x18001b26a  mov     r15d, 80000h
0x18001b270  jz      short loc_18001B2C6
0x18001b272  cmp     cs:g_fProviderEnabled, 0
0x18001b279  jz      short loc_18001B2C6
0x18001b27b  test    cs:g_ulTraceFlags, r15
0x18001b282  jz      short loc_18001B2C6
0x18001b284  mov     r8, [rdi+3E0h]
0x18001b28b  lea     rdx, aConnectionHost; "Connection->hostname is '%s'\n"
0x18001b292  mov     ecx, r15d
0x18001b295  call    LDAPClientPrint
0x18001b29a  mov     r8, [rdi+1A0h]
0x18001b2a1  lea     rdx, aConnectionDnss; "Connection->DnsSuppliedNAme is '%S'\n "
0x18001b2a8  mov     ecx, r15d
0x18001b2ab  call    LDAPClientPrint
0x18001b2b0  mov     r8, [rdi+1A8h]
0x18001b2b7  lea     rdx, aConnectionDoma; "Connection->DomainName is '%S'\n "
0x18001b2be  mov     ecx, r15d
0x18001b2c1  call    LDAPClientPrint
0x18001b2c6  test    rsi, rsi
0x18001b2c9  jz      loc_18001B352
0x18001b2cf  mov     r8, [rdi+1A0h]; InstanceName
0x18001b2d6  lea     rax, [rbp+57h+var_78]
0x18001b2da  mov     [rsp+110h+pszSpn], r14; pszSpn
0x18001b2df  lea     rcx, ServiceClass; "ldap"
0x18001b2e6  mov     [rsp+110h+pcSpnLength], rax; pcSpnLength
0x18001b2eb  movzx   r9d, bx; InstancePort
0x18001b2ef  mov     rdx, rsi; ServiceName
0x18001b2f2  mov     [rsp+110h+Referrer], 0; Referrer
0x18001b2fb  call    cs:__imp_DsMakeSpnW
0x18001b302  nop     dword ptr [rax+rax+00h]
0x18001b307  xor     esi, esi
0x18001b309  test    eax, eax
0x18001b30b  jnz     short loc_18001B352
0x18001b30d  xor     edx, edx
0x18001b30f  mov     r8d, 7672534Ch
0x18001b315  mov     rcx, r14; Src
0x18001b318  call    ldap_dup_stringW
0x18001b31d  cmp     cs:g_fTracingOn, esi
0x18001b323  mov     [rdi+190h], rax
0x18001b32a  jz      short loc_18001B352
0x18001b32c  cmp     cs:g_fProviderEnabled, esi
0x18001b332  jz      short loc_18001B352
0x18001b334  test    cs:g_ulTraceFlags, r15
0x18001b33b  jz      short loc_18001B352
0x18001b33d  xor     r9d, r9d
0x18001b340  lea     rdx, aLdapMakeSpnRet; "LDAP: make spn returned '%S' with error"...
0x18001b347  mov     r8, rax
0x18001b34a  mov     ecx, r15d
0x18001b34d  call    LDAPClientPrint
0x18001b352  and     dword ptr [rdi+43Ch], 0FFFFFF9Dh
0x18001b359  mov     rcx, r13
0x18001b35c  mov     dword ptr [rbp+57h+vals], esi
0x18001b35f  call    GetConnectionPointer
0x18001b364  mov     rbx, rax
0x18001b367  test    rax, rax
0x18001b36a  jz      loc_18001B4CD
0x18001b370  mov     [rbp+57h+res], rsi
0x18001b374  test    r12, r12
0x18001b377  jz      short loc_18001B393
0x18001b379  mov     eax, 431BDE83h
0x18001b37e  imul    dword ptr [r12+4]
0x18001b383  sar     edx, 12h
0x18001b386  mov     eax, edx
0x18001b388  shr     eax, 1Fh
0x18001b38b  add     edx, eax
0x18001b38d  add     edx, [r12]
0x18001b391  jmp     short loc_18001B399
0x18001b393  mov     edx, [rax+3F4h]
0x18001b399  lea     rax, [rbp+57h+vals]
0x18001b39d  mov     r14d, 1
0x18001b3a3  mov     [rsp+110h+var_B0], rax; __int64
0x18001b3a8  lea     r9, aObjectclass; "(objectclass=*)"
0x18001b3af  mov     [rsp+110h+var_B8], esi; int
0x18001b3b3  lea     rax, [rbp+57h+var_60]
0x18001b3b7  mov     [rsp+110h+var_C0], edx; int
0x18001b3bb  xor     r8d, r8d; int
0x18001b3be  mov     [rsp+110h+var_C8], rsi; struct ldapcontrolW **
0x18001b3c3  xor     edx, edx; int
0x18001b3c5  mov     [rsp+110h+var_D0], rsi; struct ldapcontrolW **
0x18001b3ca  mov     rcx, rbx; struct ldap_connection *
0x18001b3cd  mov     [rsp+110h+var_D8], r14b; char
0x18001b3d2  mov     byte ptr [rsp+110h+pszSpn], r14b; char
0x18001b3d7  mov     dword ptr [rsp+110h+pcSpnLength], esi; int
0x18001b3db  mov     [rsp+110h+Referrer], rax; unsigned __int16 **
0x18001b3e0  call    LdapSearch
0x18001b3e5  mov     esi, dword ptr [rbp+57h+vals]
0x18001b3e8  mov     r15d, eax
0x18001b3eb  mov     [rbp+57h+var_90], eax
0x18001b3ee  cmp     esi, 0FFFFFFFFh
0x18001b3f1  jz      short loc_18001B44F
0x18001b3f3  lea     rax, [rbp+57h+res]
0x18001b3f7  mov     [rsp+110h+pcSpnLength], 0
0x18001b400  mov     r9, r12
0x18001b403  mov     [rsp+110h+Referrer], rax
0x18001b408  mov     r8d, r14d
0x18001b40b  mov     edx, esi
0x18001b40d  mov     rcx, rbx
0x18001b410  call    ldap_result_with_error
0x18001b415  mov     rdx, [rbp+57h+res]; res
0x18001b419  mov     r15d, eax
0x18001b41c  mov     [rbp+57h+var_90], eax
0x18001b41f  test    rdx, rdx
0x18001b422  jnz     short loc_18001B43E
0x18001b424  mov     r8b, r14b
0x18001b427  mov     edx, esi
0x18001b429  mov     rcx, rbx
0x18001b42c  call    LdapAbandon
0x18001b431  mov     edx, r15d
0x18001b434  mov     rcx, rbx
0x18001b437  call    SetConnectionError
0x18001b43c  jmp     short loc_18001B44F
0x18001b43e  xor     r8d, r8d; freeit
0x18001b441  mov     rcx, r13; ld
0x18001b444  call    ldap_result2error
0x18001b449  mov     r15d, eax
0x18001b44c  mov     [rbp+57h+var_90], eax
0x18001b44f  lea     rsi, [rbx+200h]
0x18001b456  mov     rcx, rsi; lpCriticalSection
0x18001b459  call    cs:__imp_EnterCriticalSection
0x18001b460  nop     dword ptr [rax+rax+00h]
0x18001b465  dec     dword ptr [rbx]
0x18001b467  xor     r13d, r13d
0x18001b46a  cmp     cs:g_fTracingOn, r13d
0x18001b471  jz      short loc_18001B49A
0x18001b473  cmp     cs:g_fProviderEnabled, r13d
0x18001b47a  jz      short loc_18001B49A
0x18001b47c  lea     ecx, [r13+4]
0x18001b480  test    byte ptr cs:g_ulTraceFlags, cl
0x18001b486  jz      short loc_18001B49A
0x18001b488  mov     r9d, [rbx]
0x18001b48b  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18001b492  mov     r8, rbx
0x18001b495  call    LDAPClientPrint
0x18001b49a  mov     rcx, rsi; lpCriticalSection
0x18001b49d  cmp     [rbx], r13d
0x18001b4a0  jnz     short loc_18001B4BB
0x18001b4a2  call    cs:__imp_LeaveCriticalSection
0x18001b4a9  nop     dword ptr [rax+rax+00h]
0x18001b4ae  mov     edx, r14d
0x18001b4b1  mov     rcx, rbx
0x18001b4b4  call    DereferenceLdapConnection2
0x18001b4b9  jmp     short loc_18001B4E9
0x18001b4bb  call    cs:__imp_LeaveCriticalSection
0x18001b4c2  nop     dword ptr [rax+rax+00h]
0x18001b4c7  mov     [rbp+57h+var_90], r15d
0x18001b4cb  jmp     short loc_18001B4E9
0x18001b4cd  mov     r15d, 59h ; 'Y'
0x18001b4d3  mov     rcx, rbx
0x18001b4d6  mov     edx, r15d
0x18001b4d9  mov     [rbp+57h+var_90], r15d
0x18001b4dd  call    SetConnectionError
0x18001b4e2  xor     r13d, r13d
0x18001b4e5  lea     r14d, [r15-58h]
0x18001b4e9  mov     edx, cs:g_fTracingOn
0x18001b4ef  mov     ecx, cs:g_fProviderEnabled
0x18001b4f5  mov     rax, cs:g_ulTraceFlags
0x18001b4fc  test    edx, edx
0x18001b4fe  jz      short loc_18001B53B
0x18001b500  test    ecx, ecx
0x18001b502  jz      short loc_18001B53B
0x18001b504  test    r14b, al
0x18001b507  jz      short loc_18001B53B
0x18001b509  mov     dword ptr [rsp+110h+pcSpnLength], r13d
0x18001b50e  lea     rdx, aLdapSearchRetu; "ldap_search returned 0x%x for connectio"...
0x18001b515  mov     r9, rbx
0x18001b518  mov     [rsp+110h+Referrer], r13
0x18001b51d  mov     r8d, r15d
0x18001b520  mov     ecx, r14d
0x18001b523  call    LDAPClientPrint
0x18001b528  mov     edx, cs:g_fTracingOn
0x18001b52e  mov     ecx, cs:g_fProviderEnabled
0x18001b534  mov     rax, cs:g_ulTraceFlags
0x18001b53b  mov     r9, [rbp+57h+res]
0x18001b53f  test    r9, r9
0x18001b542  jz      loc_18001B7D4
0x18001b548  mov     r8d, 64h ; 'd'
0x18001b54e  mov     rdx, r9
0x18001b551  mov     rcx, rdi
0x18001b554  call    ldap_first_record
0x18001b559  mov     r12, rax
0x18001b55c  test    rax, rax
0x18001b55f  jz      loc_18001B7B8
0x18001b565  mov     r9b, r14b
0x18001b568  mov     [rbp+57h+var_70], r13
0x18001b56c  lea     r8, [rbp+57h+var_70]
0x18001b570  mov     rdx, rax
0x18001b573  mov     rcx, rdi; struct ldap_connection *
0x18001b576  call    LdapFirstAttribute
0x18001b57b  mov     rbx, rax
0x18001b57e  test    rax, rax
0x18001b581  jz      loc_18001B7B8
0x18001b587  lea     r15, aSupportedsaslm; "supportedSASLMechanisms"
0x18001b58e  lea     rax, [rbp+57h+vals]
0x18001b592  mov     [rbp+57h+vals], r13
0x18001b596  mov     [rsp+110h+pcSpnLength], rax; __int64
0x18001b59b  xor     r9d, r9d
0x18001b59e  mov     r8, rbx
0x18001b5a1  mov     byte ptr [rsp+110h+Referrer], r14b; char
0x18001b5a6  mov     rdx, r12
0x18001b5a9  mov     rcx, rdi; struct ldap_connection *
0x18001b5ac  call    LdapGetValues
0x18001b5b1  test    eax, eax
0x18001b5b3  jz      short loc_18001B5B9
0x18001b5b5  mov     [rbp+57h+vals], r13
  ... truncated ...
```
