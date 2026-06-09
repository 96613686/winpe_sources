# LdapDelete(ldap_connection *,ushort *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)

- ea: `0x18003e250`
- end: `0x18003e4ff`
- name: `?LdapDelete@@YAKPEAUldap_connection@@PEAGEEPEAPEAUldapcontrolW@@2PEAK@Z`
- size: `687`
- prototype: `unsigned int(struct ldap_connection *, unsigned __int16 *, unsigned __int8, unsigned __int8, struct ldapcontrolW **, struct ldapcontrolW **, unsigned int *)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18003e7f0`
- `0x18003e950`
- `0x18003ea40`
- `0x18003ec30`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x180008710`
- `0x180014b60`
- `0x180015bd8`
- `0x180020320`
- `0x180022e80`
- `0x18002a284`
- `0x18003e250`
- `0x18003e508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e47d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e47d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e4c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e4df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e4c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e4df`

## string_xrefs

- `0x18003e293`: `ldap_delete called for connection 0x%x: DN is %S. Synchronous is 0x%x.\n`
- `0x18003e31a`: `ldap_delete connection 0x%x couldn't allocate request.\n`
- `0x18003e3a6`: `ldap_delete connection 0x%x trouble with SControl, err 0x%x.\n`
- `0x18003e44e`: `ldap_delete connection 0x%x errored with 0x%x.\n`

## pseudocode

```c
__int64 __fastcall LdapDelete(
        struct ldap_connection *a1,
        unsigned __int16 *a2,
        unsigned __int8 a3,
        unsigned __int8 a4,
        struct ldapcontrolW **a5,
        struct ldapcontrolW **a6,
        unsigned int *a7)
{
  unsigned int v7; // edi
  __int64 result; // rax
  __int64 v13; // rdx
  __int64 Request; // rax
  __int64 v15; // rbx
  unsigned int v16; // r12d
  unsigned int v17; // eax
  __int64 v18; // rax
  struct _RTL_CRITICAL_SECTION *v19; // rcx

  v7 = 0;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 2) != 0 )
    LDAPClientPrint(2, "ldap_delete called for connection 0x%x: DN is %S. Synchronous is 0x%x.\n", (_DWORD)a1, a2, a4);
  if ( !a7 )
  {
    SetConnectionError(a1, 89);
    return 89;
  }
  *a7 = -1;
  result = LdapConnect(a1, 0, 0);
  if ( !(_DWORD)result )
  {
    SetConnectionError(a1, 0);
    LOBYTE(v13) = 74;
    Request = LdapCreateRequest(a1, v13);
    v15 = Request;
    if ( !Request )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
        LDAPClientPrint(0x4000, "ldap_delete connection 0x%x couldn't allocate request.\n", (_DWORD)a1);
      v7 = 90;
      SetConnectionError(a1, 90);
      return v7;
    }
    v16 = *(_DWORD *)(Request + 108);
    *(_BYTE *)(Request + 187) = a4;
    if ( a5 || a6 )
    {
      v17 = LdapCheckControls((struct ldap_request *)Request, a5, a6, a3, 0);
      v7 = v17;
      if ( v17 )
      {
        if ( !g_fTracingOn )
        {
LABEL_33:
          v16 = -1;
          SetConnectionError(a1, v7);
          CloseLdapRequest(v15);
LABEL_34:
          *a7 = v16;
          EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 48));
          --*(_DWORD *)(v15 + 16);
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
            LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v15, *(_DWORD *)(v15 + 16));
          v19 = (struct _RTL_CRITICAL_SECTION *)(v15 + 48);
          if ( *(_DWORD *)(v15 + 16) )
          {
            LeaveCriticalSection(v19);
          }
          else
          {
            LeaveCriticalSection(v19);
            DereferenceLdapRequest2((__int64 *)v15, 0);
          }
          return v7;
        }
        if ( g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
          LDAPClientPrint(0x8000, "ldap_delete connection 0x%x trouble with SControl, err 0x%x.\n", (_DWORD)a1, v17);
LABEL_29:
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
          LDAPClientPrint(0x100000, "ldap_delete connection 0x%x errored with 0x%x.\n", (_DWORD)a1, v7);
        goto LABEL_33;
      }
    }
    if ( a4 || !*(_BYTE *)(v15 + 185) )
    {
      *(_BYTE *)(v15 + 269) = 0;
      *(_QWORD *)(v15 + 192) = a2;
    }
    else
    {
      *(_BYTE *)(v15 + 269) = 1;
      if ( a2 )
      {
        v18 = ldap_dup_stringW(a2);
        *(_QWORD *)(v15 + 192) = v18;
        if ( !v18 )
        {
          v7 = 90;
          goto LABEL_29;
        }
      }
    }
    if ( !v7 )
    {
      v7 = SendLdapDelete(
             (struct ldap_request *)v15,
             a1,
             *(unsigned __int16 **)(v15 + 192),
             (struct CLdapBer **)(v15 + 160),
             0);
      if ( !v7 )
        goto LABEL_34;
    }
    goto LABEL_29;
  }
  return result;
}

```

## disassembly

```asm
0x18003e250  push    rbx
0x18003e252  push    rbp
0x18003e253  push    rsi
0x18003e254  push    rdi
0x18003e255  push    r12
0x18003e257  push    r13
0x18003e259  push    r14
0x18003e25b  push    r15
0x18003e25d  sub     rsp, 38h
0x18003e261  xor     edi, edi
0x18003e263  movzx   r14d, r9b
0x18003e267  cmp     cs:g_fTracingOn, edi
0x18003e26d  mov     r13b, r8b
0x18003e270  mov     rbp, rdx
0x18003e273  mov     rsi, rcx
0x18003e276  jz      short loc_18003E2A2
0x18003e278  cmp     cs:g_fProviderEnabled, edi
0x18003e27e  jz      short loc_18003E2A2
0x18003e280  lea     ecx, [rdi+2]
0x18003e283  test    byte ptr cs:g_ulTraceFlags, cl
0x18003e289  jz      short loc_18003E2A2
0x18003e28b  mov     r9, rdx
0x18003e28e  mov     [rsp+78h+var_58], r14d
0x18003e293  lea     rdx, aLdapDeleteCall; "ldap_delete called for connection 0x%x:"...
0x18003e29a  mov     r8, rsi
0x18003e29d  call    LDAPClientPrint
0x18003e2a2  mov     r15, [rsp+78h+arg_30]
0x18003e2aa  mov     rcx, rsi
0x18003e2ad  test    r15, r15
0x18003e2b0  jnz     short loc_18003E2C4
0x18003e2b2  lea     ebx, [r15+59h]
0x18003e2b6  mov     edx, ebx
0x18003e2b8  call    SetConnectionError
0x18003e2bd  mov     eax, ebx
0x18003e2bf  jmp     loc_18003E4ED
0x18003e2c4  xor     r8d, r8d
0x18003e2c7  mov     dword ptr [r15], 0FFFFFFFFh
0x18003e2ce  xor     edx, edx
0x18003e2d0  call    LdapConnect
0x18003e2d5  test    eax, eax
0x18003e2d7  jnz     loc_18003E4ED
0x18003e2dd  xor     edx, edx
0x18003e2df  mov     rcx, rsi
0x18003e2e2  call    SetConnectionError
0x18003e2e7  mov     dl, 4Ah ; 'J'
0x18003e2e9  mov     rcx, rsi
0x18003e2ec  call    LdapCreateRequest
0x18003e2f1  mov     rbx, rax
0x18003e2f4  test    rax, rax
0x18003e2f7  jnz     short loc_18003E33A
0x18003e2f9  cmp     cs:g_fTracingOn, edi
0x18003e2ff  jz      short loc_18003E326
0x18003e301  cmp     cs:g_fProviderEnabled, edi
0x18003e307  jz      short loc_18003E326
0x18003e309  mov     ecx, 4000h
0x18003e30e  test    cs:g_ulTraceFlags, rcx
0x18003e315  jz      short loc_18003E326
0x18003e317  mov     r8, rsi
0x18003e31a  lea     rdx, aLdapDeleteConn_1; "ldap_delete connection 0x%x couldn't al"...
0x18003e321  call    LDAPClientPrint
0x18003e326  mov     edi, 5Ah ; 'Z'
0x18003e32b  mov     rcx, rsi
0x18003e32e  mov     edx, edi
0x18003e330  call    SetConnectionError
0x18003e335  jmp     loc_18003E4EB
0x18003e33a  mov     rdx, [rsp+78h+arg_20]; struct ldapcontrolW **
0x18003e342  mov     r12d, [rax+6Ch]
0x18003e346  mov     r8, [rsp+78h+arg_28]; struct ldapcontrolW **
0x18003e34e  mov     [rax+0BBh], r14b
0x18003e355  test    rdx, rdx
0x18003e358  jnz     short loc_18003E35F
0x18003e35a  test    r8, r8
0x18003e35d  jz      short loc_18003E3B7
0x18003e35f  mov     r9b, r13b; unsigned __int8
0x18003e362  mov     [rsp+78h+var_58], edi; unsigned int
0x18003e366  mov     rcx, rbx; struct ldap_request *
0x18003e369  call    LdapCheckControls
0x18003e36e  xor     r13d, r13d
0x18003e371  mov     edi, eax
0x18003e373  test    eax, eax
0x18003e375  jz      short loc_18003E3BA
0x18003e377  cmp     cs:g_fTracingOn, r13d
0x18003e37e  jz      loc_18003E45D
0x18003e384  cmp     cs:g_fProviderEnabled, r13d
0x18003e38b  jz      loc_18003E42B
0x18003e391  mov     ecx, 8000h
0x18003e396  test    cs:g_ulTraceFlags, rcx
0x18003e39d  jz      loc_18003E42B
0x18003e3a3  mov     r9d, eax
0x18003e3a6  lea     rdx, aLdapDeleteConn_2; "ldap_delete connection 0x%x trouble wit"...
0x18003e3ad  mov     r8, rsi
0x18003e3b0  call    LDAPClientPrint
0x18003e3b5  jmp     short loc_18003E42B
0x18003e3b7  xor     r13d, r13d
0x18003e3ba  test    r14b, r14b
0x18003e3bd  jnz     short loc_18003E3F5
0x18003e3bf  cmp     [rbx+0B9h], r13b
0x18003e3c6  jz      short loc_18003E3F5
0x18003e3c8  mov     byte ptr [rbx+10Dh], 1
0x18003e3cf  test    rbp, rbp
0x18003e3d2  jz      short loc_18003E403
0x18003e3d4  xor     edx, edx
0x18003e3d6  mov     r8d, 696E554Ch
0x18003e3dc  mov     rcx, rbp; Src
0x18003e3df  call    ldap_dup_stringW
0x18003e3e4  mov     [rbx+0C0h], rax
0x18003e3eb  test    rax, rax
0x18003e3ee  jnz     short loc_18003E403
0x18003e3f0  lea     edi, [rax+5Ah]
0x18003e3f3  jmp     short loc_18003E42B
0x18003e3f5  mov     [rbx+10Dh], r13b
0x18003e3fc  mov     [rbx+0C0h], rbp
0x18003e403  test    edi, edi
0x18003e405  jnz     short loc_18003E42B
0x18003e407  mov     r8, [rbx+0C0h]; unsigned __int16 *
0x18003e40e  lea     r9, [rbx+0A0h]; struct CLdapBer **
0x18003e415  mov     rdx, rsi; struct ldap_connection *
0x18003e418  mov     [rsp+78h+var_58], r13d; int
0x18003e41d  mov     rcx, rbx; struct ldap_request *
0x18003e420  call    ?SendLdapDelete@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAVCLdapBer@@J@Z; SendLdapDelete(ldap_request *,ldap_connection *,ushort *,CLdapBer * *,long)
0x18003e425  mov     edi, eax
0x18003e427  test    eax, eax
0x18003e429  jz      short loc_18003E473
0x18003e42b  cmp     cs:g_fTracingOn, r13d
0x18003e432  jz      short loc_18003E45D
0x18003e434  cmp     cs:g_fProviderEnabled, r13d
0x18003e43b  jz      short loc_18003E45D
0x18003e43d  mov     ecx, 100000h
0x18003e442  test    cs:g_ulTraceFlags, rcx
0x18003e449  jz      short loc_18003E45D
0x18003e44b  mov     r9d, edi
0x18003e44e  lea     rdx, aLdapDeleteConn; "ldap_delete connection 0x%x errored wit"...
0x18003e455  mov     r8, rsi
0x18003e458  call    LDAPClientPrint
0x18003e45d  mov     edx, edi
0x18003e45f  mov     rcx, rsi
0x18003e462  or      r12d, 0FFFFFFFFh
0x18003e466  call    SetConnectionError
0x18003e46b  mov     rcx, rbx
0x18003e46e  call    CloseLdapRequest
0x18003e473  lea     rsi, [rbx+30h]
0x18003e477  mov     [r15], r12d
0x18003e47a  mov     rcx, rsi; lpCriticalSection
0x18003e47d  call    cs:__imp_EnterCriticalSection
0x18003e484  nop     dword ptr [rax+rax+00h]
0x18003e489  dec     dword ptr [rbx+10h]
0x18003e48c  cmp     cs:g_fTracingOn, r13d
0x18003e493  jz      short loc_18003E4BE
0x18003e495  cmp     cs:g_fProviderEnabled, r13d
0x18003e49c  jz      short loc_18003E4BE
0x18003e49e  mov     ecx, 4
0x18003e4a3  test    byte ptr cs:g_ulTraceFlags, cl
0x18003e4a9  jz      short loc_18003E4BE
0x18003e4ab  mov     r9d, [rbx+10h]
0x18003e4af  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x18003e4b6  mov     r8, rbx
0x18003e4b9  call    LDAPClientPrint
0x18003e4be  mov     rcx, rsi; lpCriticalSection
0x18003e4c1  cmp     [rbx+10h], r13d
0x18003e4c5  jnz     short loc_18003E4DF
0x18003e4c7  call    cs:__imp_LeaveCriticalSection
0x18003e4ce  nop     dword ptr [rax+rax+00h]
0x18003e4d3  xor     edx, edx
0x18003e4d5  mov     rcx, rbx
0x18003e4d8  call    DereferenceLdapRequest2
0x18003e4dd  jmp     short loc_18003E4EB
0x18003e4df  call    cs:__imp_LeaveCriticalSection
0x18003e4e6  nop     dword ptr [rax+rax+00h]
0x18003e4eb  mov     eax, edi
0x18003e4ed  add     rsp, 38h
0x18003e4f1  pop     r15
0x18003e4f3  pop     r14
0x18003e4f5  pop     r13
0x18003e4f7  pop     r12
0x18003e4f9  pop     rdi
0x18003e4fa  pop     rsi
0x18003e4fb  pop     rbp
0x18003e4fc  pop     rbx
0x18003e4fd  retn
```
