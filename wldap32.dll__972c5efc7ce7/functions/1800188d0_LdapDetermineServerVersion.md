# LdapDetermineServerVersion

- ea: `0x1800188d0`
- end: `0x180018c96`
- name: `LdapDetermineServerVersion`
- size: `966`
- prototype: `__int64 __fastcall(struct ldap_connection *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800164a0`

## callees

- `0x1800037a8`
- `0x180004740`
- `0x180005170`
- `0x1800061a0`
- `0x180006510`
- `0x18000adb0`
- `0x18000bf40`
- `0x18000cda0`
- `0x1800147f0`
- `0x180015640`
- `0x18001611c`
- `0x180016360`
- `0x1800188d0`
- `0x180018ca0`
- `0x18001ba9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018a21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018a21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a85`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018ba2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018bec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018ba2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018bec`

## pseudocode

```c
__int64 __fastcall LdapDetermineServerVersion(struct ldap_connection *a1, _DWORD *a2, PWCHAR *a3)
{
  int v3; // r13d
  LDAP *v4; // r12
  __int64 ConnectionPointer; // rax
  _DWORD *v8; // rbx
  int v9; // edx
  ULONG v10; // eax
  unsigned int v11; // r15d
  ULONG v12; // edi
  __int64 v13; // r8
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  LDAPMessage *v15; // rbx
  const WCHAR *Attribute; // rsi
  PWCHAR *v17; // r12
  ULONG v18; // r15d
  __int64 i; // rsi
  const WCHAR *v20; // r8
  bool v21; // zf
  __int64 result; // rax
  LDAPMessage *res; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int16 *v24[9]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+D0h] [rbp+67h] BYREF
  PWCHAR *vals; // [rsp+E0h] [rbp+77h] BYREF
  int v27; // [rsp+E8h] [rbp+7Fh]

  vals = a3;
  v3 = *((_DWORD *)a1 + 271);
  v4 = (LDAP *)*((_QWORD *)a1 + 56);
  v24[0] = L"supportedCapabilities";
  res = 0;
  v27 = v3;
  *((_DWORD *)a1 + 271) = v3 & 0xFFFFFF9D;
  v24[1] = 0;
  *(_BYTE *)a3 = 0;
  LODWORD(v25) = 0;
  ConnectionPointer = GetConnectionPointer(v4, a2, a3);
  v8 = (_DWORD *)ConnectionPointer;
  if ( ConnectionPointer )
  {
    res = 0;
    if ( a2 )
      v9 = *a2 + a2[1] / 1000000;
    else
      v9 = *(_DWORD *)(ConnectionPointer + 1012);
    v10 = LdapSearch(
            (struct ldap_connection *)ConnectionPointer,
            0,
            0,
            (int)L"(objectclass=*)",
            v24,
            0,
            1,
            1,
            0,
            0,
            v9,
            0,
            (__int64)&v25);
    v11 = v25;
    v12 = v10;
    if ( (_DWORD)v25 != -1 )
    {
      v12 = ldap_result_with_error((struct ldap_connection *)v8, v25, (__int64)&res, 0);
      if ( res )
      {
        v12 = ldap_result2error(v4, res, 0);
      }
      else
      {
        LOBYTE(v13) = 1;
        LdapAbandon(v8, v11, v13);
        SetConnectionError(v8, v12);
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 128));
    --*v8;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v8, *v8);
    v14 = (struct _RTL_CRITICAL_SECTION *)(v8 + 128);
    if ( *v8 )
    {
      LeaveCriticalSection(v14);
    }
    else
    {
      LeaveCriticalSection(v14);
      DereferenceLdapConnection2((__int64)v8, 1);
    }
  }
  else
  {
    v12 = 89;
    SetConnectionError(0, 89);
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 1) != 0 )
    LDAPClientPrint(
      1,
      "ldap_search returned 0x%x for connection 0x%x: DN was %S. SearchScope was 0x%x.\n",
      v12,
      (_DWORD)v8,
      0,
      0);
  v15 = res;
  if ( res )
  {
    SetConnectionError(a1, 0);
    if ( v15 != (LDAPMessage *)-1LL )
    {
      while ( v15 && v15->lm_msgtype != 100 )
        v15 = v15->lm_chain;
      if ( v15 )
      {
        v25 = 0;
        Attribute = (const WCHAR *)LdapFirstAttribute(a1, (__int64)v15, &v25, 1);
        if ( Attribute )
        {
          v17 = vals;
          do
          {
            vals = 0;
            if ( (unsigned int)LdapGetValues(a1, (__int64)v15, Attribute, 0, 1, (PCHAR **)&vals) )
              vals = 0;
            v18 = ldap_count_values_len(vals);
            if ( CompareStringW(0x400u, 1u, Attribute, -1, L"supportedCapabilities", -1) == 2 )
            {
              for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
              {
                v20 = vals[i];
                if ( v20 )
                {
                  if ( CompareStringW(0x400u, 1u, v20, -1, L"1.2.840.113556.1.4.1791", -1) == 2 )
                  {
                    v21 = g_fTracingOn == 0;
                    *(_BYTE *)v17 = 1;
                    if ( !v21 && g_fProviderEnabled && (g_ulTraceFlags & 0x80000) != 0 )
                      LDAPClientPrint(
                        0x80000,
                        "ldapBind found server is Windows 2003 or better AD on connection 0x%x\n",
                        (_DWORD)a1);
                  }
                }
              }
            }
            ldap_value_free((PCHAR *)vals);
            Attribute = (const WCHAR *)LdapNextAttribute((__int64)a1, (__int64)v15, (unsigned int *)v25, 1);
          }
          while ( Attribute );
          v3 = v27;
        }
      }
    }
    ldap_msgfree(res);
  }
  result = v12;
  *((_DWORD *)a1 + 271) = v3;
  return result;
}

```

## disassembly

```asm
0x1800188d0  mov     [rsp-8+arg_8], rbx
0x1800188d5  mov     [rsp-8+vals], r8
0x1800188da  push    rbp
0x1800188db  push    rsi
0x1800188dc  push    rdi
0x1800188dd  push    r12
0x1800188df  push    r13
0x1800188e1  push    r14
0x1800188e3  push    r15
0x1800188e5  lea     rbp, [rsp-27h]
0x1800188ea  sub     rsp, 90h
0x1800188f1  mov     r13d, [rcx+43Ch]
0x1800188f8  lea     rax, aSupportedcapab; "supportedCapabilities"
0x1800188ff  mov     r12, [rcx+1C0h]
0x180018906  xor     r15d, r15d
0x180018909  mov     [rbp+57h+var_48], rax
0x18001890d  mov     r14, rcx
0x180018910  mov     eax, r13d
0x180018913  mov     [rbp+57h+res], r15
0x180018917  and     eax, 0FFFFFF9Dh
0x18001891a  mov     [rbp+57h+arg_18], r13d
0x18001891e  mov     [rcx+43Ch], eax
0x180018924  mov     rsi, rdx
0x180018927  mov     rcx, r12
0x18001892a  mov     [rbp+57h+var_40], r15
0x18001892e  mov     [r8], r15b
0x180018931  mov     dword ptr [rbp+57h+arg_0], r15d
0x180018935  call    GetConnectionPointer
0x18001893a  mov     rbx, rax
0x18001893d  test    rax, rax
0x180018940  jz      loc_180018A93
0x180018946  mov     [rbp+57h+res], r15
0x18001894a  test    rsi, rsi
0x18001894d  jz      short loc_180018965
0x18001894f  mov     eax, 431BDE83h
0x180018954  imul    dword ptr [rsi+4]
0x180018957  sar     edx, 12h
0x18001895a  mov     eax, edx
0x18001895c  shr     eax, 1Fh
0x18001895f  add     edx, eax
0x180018961  add     edx, [rsi]
0x180018963  jmp     short loc_18001896B
0x180018965  mov     edx, [rax+3F4h]
0x18001896b  lea     rax, [rbp+57h+arg_0]
0x18001896f  xor     r8d, r8d; int
0x180018972  mov     [rsp+0C0h+var_60], rax; __int64
0x180018977  lea     r9, aObjectclass; "(objectclass=*)"
0x18001897e  mov     [rsp+0C0h+var_68], r15d; int
0x180018983  lea     rax, [rbp+57h+var_48]
0x180018987  mov     [rsp+0C0h+var_70], edx; int
0x18001898b  mov     rcx, rbx; struct ldap_connection *
0x18001898e  mov     [rsp+0C0h+var_78], r15; struct ldapcontrolW **
0x180018993  xor     edx, edx; int
0x180018995  mov     [rsp+0C0h+var_80], r15; struct ldapcontrolW **
0x18001899a  mov     [rsp+0C0h+var_88], 1; char
0x18001899f  mov     [rsp+0C0h+var_90], 1; char
0x1800189a4  mov     [rsp+0C0h+cchCount2], r15d; int
0x1800189a9  mov     [rsp+0C0h+lpString2], rax; unsigned __int16 **
0x1800189ae  call    LdapSearch
0x1800189b3  mov     r15d, dword ptr [rbp+57h+arg_0]
0x1800189b7  mov     edi, eax
0x1800189b9  cmp     r15d, 0FFFFFFFFh
0x1800189bd  jz      short loc_180018A17
0x1800189bf  lea     rax, [rbp+57h+res]
0x1800189c3  mov     qword ptr [rsp+0C0h+cchCount2], 0
0x1800189cc  mov     r9, rsi
0x1800189cf  mov     [rsp+0C0h+lpString2], rax
0x1800189d4  mov     r8d, 1
0x1800189da  mov     edx, r15d
0x1800189dd  mov     rcx, rbx
0x1800189e0  call    ldap_result_with_error
0x1800189e5  mov     rdx, [rbp+57h+res]; res
0x1800189e9  mov     edi, eax
0x1800189eb  test    rdx, rdx
0x1800189ee  jnz     short loc_180018A0A
0x1800189f0  mov     r8b, 1
0x1800189f3  mov     edx, r15d
0x1800189f6  mov     rcx, rbx
0x1800189f9  call    LdapAbandon
0x1800189fe  mov     edx, edi
0x180018a00  mov     rcx, rbx
0x180018a03  call    SetConnectionError
0x180018a08  jmp     short loc_180018A17
0x180018a0a  xor     r8d, r8d; freeit
0x180018a0d  mov     rcx, r12; ld
0x180018a10  call    ldap_result2error
0x180018a15  mov     edi, eax
0x180018a17  lea     rsi, [rbx+200h]
0x180018a1e  mov     rcx, rsi; lpCriticalSection
0x180018a21  call    cs:__imp_EnterCriticalSection
0x180018a28  nop     dword ptr [rax+rax+00h]
0x180018a2d  dec     dword ptr [rbx]
0x180018a2f  xor     r15d, r15d
0x180018a32  cmp     cs:g_fTracingOn, r15d
0x180018a39  jz      short loc_180018A62
0x180018a3b  cmp     cs:g_fProviderEnabled, r15d
0x180018a42  jz      short loc_180018A62
0x180018a44  lea     ecx, [r15+4]
0x180018a48  test    byte ptr cs:g_ulTraceFlags, cl
0x180018a4e  jz      short loc_180018A62
0x180018a50  mov     r9d, [rbx]
0x180018a53  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180018a5a  mov     r8, rbx
0x180018a5d  call    LDAPClientPrint
0x180018a62  mov     rcx, rsi; lpCriticalSection
0x180018a65  cmp     [rbx], r15d
0x180018a68  jnz     short loc_180018A85
0x180018a6a  call    cs:__imp_LeaveCriticalSection
0x180018a71  nop     dword ptr [rax+rax+00h]
0x180018a76  mov     edx, 1
0x180018a7b  mov     rcx, rbx
0x180018a7e  call    DereferenceLdapConnection2
0x180018a83  jmp     short loc_180018AA2
0x180018a85  call    cs:__imp_LeaveCriticalSection
0x180018a8c  nop     dword ptr [rax+rax+00h]
0x180018a91  jmp     short loc_180018AA2
0x180018a93  mov     edi, 59h ; 'Y'
0x180018a98  mov     rcx, rbx
0x180018a9b  mov     edx, edi
0x180018a9d  call    SetConnectionError
0x180018aa2  cmp     cs:g_fTracingOn, r15d
0x180018aa9  jz      short loc_180018ADE
0x180018aab  cmp     cs:g_fProviderEnabled, r15d
0x180018ab2  jz      short loc_180018ADE
0x180018ab4  test    byte ptr cs:g_ulTraceFlags, 1
0x180018abb  jz      short loc_180018ADE
0x180018abd  mov     [rsp+0C0h+cchCount2], r15d
0x180018ac2  lea     rdx, aLdapSearchRetu; "ldap_search returned 0x%x for connectio"...
0x180018ac9  mov     r9, rbx
0x180018acc  mov     [rsp+0C0h+lpString2], r15
0x180018ad1  mov     r8d, edi
0x180018ad4  mov     ecx, 1
0x180018ad9  call    LDAPClientPrint
0x180018ade  mov     rbx, [rbp+57h+res]
0x180018ae2  test    rbx, rbx
0x180018ae5  jz      loc_180018C71
0x180018aeb  xor     edx, edx
0x180018aed  mov     rcx, r14
0x180018af0  call    SetConnectionError
0x180018af5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180018af9  jnz     short loc_180018B0A
0x180018afb  jmp     loc_180018C68
0x180018b00  cmp     dword ptr [rbx+4], 64h ; 'd'
0x180018b04  jz      short loc_180018B0F
0x180018b06  mov     rbx, [rbx+10h]
0x180018b0a  test    rbx, rbx
0x180018b0d  jnz     short loc_180018B00
0x180018b0f  test    rbx, rbx
0x180018b12  jz      loc_180018C68
0x180018b18  mov     r9b, 1
0x180018b1b  mov     [rbp+57h+arg_0], r15
0x180018b1f  lea     r8, [rbp+57h+arg_0]
0x180018b23  mov     rdx, rbx
0x180018b26  mov     rcx, r14; struct ldap_connection *
0x180018b29  call    LdapFirstAttribute
0x180018b2e  mov     rsi, rax
0x180018b31  test    rax, rax
0x180018b34  jz      loc_180018C68
0x180018b3a  mov     r12, [rbp+57h+vals]
0x180018b3e  lea     r13, aSupportedcapab; "supportedCapabilities"
0x180018b45  lea     rax, [rbp+57h+vals]
0x180018b49  mov     [rbp+57h+vals], r15
0x180018b4d  mov     qword ptr [rsp+0C0h+cchCount2], rax; __int64
0x180018b52  xor     r9d, r9d
0x180018b55  mov     r8, rsi
0x180018b58  mov     byte ptr [rsp+0C0h+lpString2], 1; char
0x180018b5d  mov     rdx, rbx
0x180018b60  mov     rcx, r14; struct ldap_connection *
0x180018b63  call    LdapGetValues
0x180018b68  test    eax, eax
0x180018b6a  jz      short loc_180018B70
0x180018b6c  mov     [rbp+57h+vals], r15
0x180018b70  mov     rcx, [rbp+57h+vals]; vals
0x180018b74  call    ldap_count_values_len
0x180018b79  mov     r15d, eax
0x180018b7c  test    rsi, rsi
0x180018b7f  jz      loc_180018C3A
0x180018b85  or      r9d, 0FFFFFFFFh; cchCount1
0x180018b89  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x180018b91  mov     r8, rsi; lpString1
0x180018b94  mov     [rsp+0C0h+lpString2], r13; lpString2
0x180018b99  mov     ecx, 400h; Locale
0x180018b9e  lea     edx, [r9+2]; dwCmpFlags
0x180018ba2  call    cs:__imp_CompareStringW
0x180018ba9  nop     dword ptr [rax+rax+00h]
0x180018bae  cmp     eax, 2
0x180018bb1  jnz     loc_180018C3A
0x180018bb7  xor     esi, esi
0x180018bb9  test    r15d, r15d
0x180018bbc  jz      short loc_180018C3A
0x180018bbe  mov     rax, [rbp+57h+vals]
0x180018bc2  mov     r8, [rax+rsi*8]; lpString1
0x180018bc6  test    r8, r8
0x180018bc9  jz      short loc_180018C33
0x180018bcb  or      r9d, 0FFFFFFFFh; cchCount1
0x180018bcf  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x180018bd7  lea     rax, a12840113556141; "1.2.840.113556.1.4.1791"
0x180018bde  mov     ecx, 400h; Locale
0x180018be3  mov     [rsp+0C0h+lpString2], rax; lpString2
0x180018be8  lea     edx, [r9+2]; dwCmpFlags
0x180018bec  call    cs:__imp_CompareStringW
0x180018bf3  nop     dword ptr [rax+rax+00h]
0x180018bf8  cmp     eax, 2
0x180018bfb  jnz     short loc_180018C33
0x180018bfd  cmp     cs:g_fTracingOn, 0
0x180018c04  mov     byte ptr [r12], 1
0x180018c09  jz      short loc_180018C33
0x180018c0b  cmp     cs:g_fProviderEnabled, 0
0x180018c12  jz      short loc_180018C33
0x180018c14  mov     eax, 80000h
0x180018c19  test    cs:g_ulTraceFlags, rax
0x180018c20  jz      short loc_180018C33
0x180018c22  mov     r8, r14
0x180018c25  lea     rdx, aLdapbindFoundS; "ldapBind found server is Windows 2003 o"...
0x180018c2c  mov     ecx, eax
0x180018c2e  call    LDAPClientPrint
0x180018c33  inc     esi
0x180018c35  cmp     esi, r15d
0x180018c38  jb      short loc_180018BBE
0x180018c3a  mov     rcx, [rbp+57h+vals]; vals
0x180018c3e  call    ldap_value_free
0x180018c43  mov     r8, [rbp+57h+arg_0]
0x180018c47  mov     r9b, 1
0x180018c4a  mov     rdx, rbx
0x180018c4d  mov     rcx, r14
0x180018c50  call    LdapNextAttribute
0x180018c55  xor     r15d, r15d
0x180018c58  mov     rsi, rax
0x180018c5b  test    rax, rax
0x180018c5e  jnz     loc_180018B45
0x180018c64  mov     r13d, [rbp+57h+arg_18]
0x180018c68  mov     rcx, [rbp+57h+res]; res
0x180018c6c  call    ldap_msgfree
0x180018c71  mov     rbx, [rsp+0C0h+arg_8]
0x180018c79  mov     eax, edi
0x180018c7b  mov     [r14+43Ch], r13d
0x180018c82  add     rsp, 90h
0x180018c89  pop     r15
0x180018c8b  pop     r14
0x180018c8d  pop     r13
0x180018c8f  pop     r12
0x180018c91  pop     rdi
0x180018c92  pop     rsi
0x180018c93  pop     rbp
0x180018c94  retn
```
