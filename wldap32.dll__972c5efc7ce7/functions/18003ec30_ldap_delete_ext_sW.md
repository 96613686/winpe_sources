# ldap_delete_ext_sW

- ea: `0x18003ec30`
- end: `0x18003edb2`
- name: `ldap_delete_ext_sW`
- size: `386`
- prototype: `ULONG __cdecl(LDAP *ld, const PWSTR dn, PLDAPControlW *ServerControls, PLDAPControlW *ClientControls)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003ede0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000bf40`
- `0x18000cda0`
- `0x18001611c`
- `0x180016360`
- `0x18003e250`
- `0x18003ec30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ed00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ed00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed62`

## string_xrefs

- `0x18003ed98`: `ldap_delete returned 0x%x for connection 0x%x; DN was %S.\n`

## pseudocode

```c
ULONG __cdecl ldap_delete_ext_sW(
        LDAP *ld,
        const PWSTR dn,
        PLDAPControlW *ServerControls,
        PLDAPControlW *ClientControls)
{
  _DWORD *ConnectionPointer; // rbx
  ULONG v10; // eax
  unsigned int v11; // esi
  ULONG v12; // edi
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  unsigned int v14; // [rsp+40h] [rbp-38h] BYREF
  LDAPMessage *res; // [rsp+48h] [rbp-30h] BYREF

  v14 = 0;
  res = 0;
  ConnectionPointer = (_DWORD *)GetConnectionPointer(ld, dn, ServerControls);
  if ( !ConnectionPointer )
    return 89;
  v10 = LdapDelete((struct ldap_connection *)ConnectionPointer, dn, 1u, 1u, ServerControls, ClientControls, &v14);
  v11 = v14;
  v12 = v10;
  if ( v14 != -1 )
  {
    v12 = ldap_result_with_error((struct ldap_connection *)ConnectionPointer, v14, (__int64)&res, 0);
    if ( res )
    {
      v12 = ldap_result2error(ld, res, 1u);
    }
    else
    {
      LdapAbandon((__int64)ConnectionPointer, v11, 1);
      SetConnectionError(ConnectionPointer, v12);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 128));
  --*ConnectionPointer;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)ConnectionPointer, *ConnectionPointer);
  v13 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 128);
  if ( *ConnectionPointer )
  {
    LeaveCriticalSection(v13);
  }
  else
  {
    LeaveCriticalSection(v13);
    DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 2) != 0 )
    LDAPClientPrint(
      2,
      "ldap_delete returned 0x%x for connection 0x%x; DN was %S.\n",
      v12,
      (_DWORD)ConnectionPointer,
      dn);
  return v12;
}

```

## disassembly

```asm
0x18003ec30  push    rbx
0x18003ec32  push    rbp
0x18003ec33  push    rsi
0x18003ec34  push    rdi
0x18003ec35  push    r14
0x18003ec37  sub     rsp, 50h
0x18003ec3b  mov     rdi, r9
0x18003ec3e  mov     [rsp+78h+var_38], 0
0x18003ec46  mov     rsi, r8
0x18003ec49  mov     [rsp+78h+res], 0
0x18003ec52  mov     r14, rdx
0x18003ec55  mov     rbp, rcx
0x18003ec58  call    GetConnectionPointer
0x18003ec5d  mov     rbx, rax
0x18003ec60  test    rax, rax
0x18003ec63  jnz     short loc_18003EC6D
0x18003ec65  lea     eax, [rbx+59h]
0x18003ec68  jmp     loc_18003EDA6
0x18003ec6d  lea     rax, [rsp+78h+var_38]
0x18003ec72  mov     r9b, 1; unsigned __int8
0x18003ec75  mov     [rsp+78h+var_48], rax; unsigned int *
0x18003ec7a  mov     r8b, r9b; unsigned __int8
0x18003ec7d  mov     [rsp+78h+var_50], rdi; struct ldapcontrolW **
0x18003ec82  mov     rdx, r14; unsigned __int16 *
0x18003ec85  mov     rcx, rbx; struct ldap_connection *
0x18003ec88  mov     [rsp+78h+var_58], rsi; struct ldapcontrolW **
0x18003ec8d  call    ?LdapDelete@@YAKPEAUldap_connection@@PEAGEEPEAPEAUldapcontrolW@@2PEAK@Z; LdapDelete(ldap_connection *,ushort *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18003ec92  mov     esi, [rsp+78h+var_38]
0x18003ec96  mov     edi, eax
0x18003ec98  cmp     esi, 0FFFFFFFFh
0x18003ec9b  jz      short loc_18003ECF6
0x18003ec9d  xor     r9d, r9d
0x18003eca0  mov     [rsp+78h+var_50], 0
0x18003eca9  lea     rax, [rsp+78h+res]
0x18003ecae  mov     edx, esi
0x18003ecb0  mov     rcx, rbx
0x18003ecb3  mov     [rsp+78h+var_58], rax
0x18003ecb8  lea     r8d, [r9+1]
0x18003ecbc  call    ldap_result_with_error
0x18003ecc1  mov     rdx, [rsp+78h+res]; res
0x18003ecc6  mov     edi, eax
0x18003ecc8  test    rdx, rdx
0x18003eccb  jnz     short loc_18003ECE6
0x18003eccd  mov     r8b, 1
0x18003ecd0  mov     edx, esi
0x18003ecd2  mov     rcx, rbx
0x18003ecd5  call    LdapAbandon
0x18003ecda  mov     edx, edi
0x18003ecdc  mov     rcx, rbx
0x18003ecdf  call    SetConnectionError
0x18003ece4  jmp     short loc_18003ECF6
0x18003ece6  mov     r8d, 1; freeit
0x18003ecec  mov     rcx, rbp; ld
0x18003ecef  call    ldap_result2error
0x18003ecf4  mov     edi, eax
0x18003ecf6  lea     rsi, [rbx+200h]
0x18003ecfd  mov     rcx, rsi; lpCriticalSection
0x18003ed00  call    cs:__imp_EnterCriticalSection
0x18003ed07  nop     dword ptr [rax+rax+00h]
0x18003ed0c  dec     dword ptr [rbx]
0x18003ed0e  cmp     cs:g_fTracingOn, 0
0x18003ed15  jz      short loc_18003ED3F
0x18003ed17  cmp     cs:g_fProviderEnabled, 0
0x18003ed1e  jz      short loc_18003ED3F
0x18003ed20  mov     ecx, 4
0x18003ed25  test    byte ptr cs:g_ulTraceFlags, cl
0x18003ed2b  jz      short loc_18003ED3F
0x18003ed2d  mov     r9d, [rbx]
0x18003ed30  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18003ed37  mov     r8, rbx
0x18003ed3a  call    LDAPClientPrint
0x18003ed3f  cmp     dword ptr [rbx], 0
0x18003ed42  mov     rcx, rsi; lpCriticalSection
0x18003ed45  jnz     short loc_18003ED62
0x18003ed47  call    cs:__imp_LeaveCriticalSection
0x18003ed4e  nop     dword ptr [rax+rax+00h]
0x18003ed53  mov     edx, 1
0x18003ed58  mov     rcx, rbx
0x18003ed5b  call    DereferenceLdapConnection2
0x18003ed60  jmp     short loc_18003ED6E
0x18003ed62  call    cs:__imp_LeaveCriticalSection
0x18003ed69  nop     dword ptr [rax+rax+00h]
0x18003ed6e  cmp     cs:g_fTracingOn, 0
0x18003ed75  jz      short loc_18003EDA4
0x18003ed77  cmp     cs:g_fProviderEnabled, 0
0x18003ed7e  jz      short loc_18003EDA4
0x18003ed80  mov     ecx, 2
0x18003ed85  test    byte ptr cs:g_ulTraceFlags, cl
0x18003ed8b  jz      short loc_18003EDA4
0x18003ed8d  mov     r9, rbx
0x18003ed90  mov     [rsp+78h+var_58], r14
0x18003ed95  mov     r8d, edi
0x18003ed98  lea     rdx, aLdapDeleteRetu_0; "ldap_delete returned 0x%x for connectio"...
0x18003ed9f  call    LDAPClientPrint
0x18003eda4  mov     eax, edi
0x18003eda6  add     rsp, 50h
0x18003edaa  pop     r14
0x18003edac  pop     rdi
0x18003edad  pop     rsi
0x18003edae  pop     rbp
0x18003edaf  pop     rbx
0x18003edb0  retn
```
