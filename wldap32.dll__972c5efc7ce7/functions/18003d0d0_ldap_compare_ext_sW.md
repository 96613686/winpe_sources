# ldap_compare_ext_sW

- ea: `0x18003d0d0`
- end: `0x18003d24e`
- name: `ldap_compare_ext_sW`
- size: `382`
- prototype: `ULONG __cdecl(LDAP *ld, const PWSTR dn, const PWSTR Attr, const PWSTR Value, struct berval *Data, PLDAPControlW *ServerControls, PLDAPControlW *ClientControls)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003d290`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000bf40`
- `0x18000cda0`
- `0x18001611c`
- `0x180016360`
- `0x18003c254`
- `0x18003d0d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d1d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d1d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d219`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d219`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d234`

## pseudocode

```c
ULONG __cdecl ldap_compare_ext_sW(
        LDAP *ld,
        const PWSTR dn,
        const PWSTR Attr,
        const PWSTR Value,
        struct berval *Data,
        PLDAPControlW *ServerControls,
        PLDAPControlW *ClientControls)
{
  struct ldap_connection *ConnectionPointer; // rax
  __int64 v12; // r8
  struct ldap_connection *v13; // rbx
  unsigned int v15; // eax
  unsigned int v16; // ebp
  unsigned int v17; // esi
  __int64 v18; // r8
  struct _RTL_CRITICAL_SECTION *v19; // rcx
  unsigned int v20; // [rsp+50h] [rbp-38h] BYREF
  LDAPMessage *res; // [rsp+58h] [rbp-30h] BYREF

  v20 = 0;
  res = 0;
  ConnectionPointer = (struct ldap_connection *)GetConnectionPointer(ld, dn, Attr);
  v13 = ConnectionPointer;
  if ( ConnectionPointer )
  {
    v15 = LdapCompare(ConnectionPointer, dn, Attr, Value, Data, 1u, 1u, ServerControls, ClientControls, &v20);
    v16 = v20;
    v17 = v15;
    if ( v20 != -1 )
    {
      v17 = ldap_result_with_error(v13, v20, 1u, 0, &res, 0);
      if ( res )
      {
        v17 = ldap_result2error(ld, res, 1u);
      }
      else
      {
        LdapAbandon((__int64)v13, v16, 1);
        SetConnectionError((__int64)v13, v17, v18);
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v13 + 512));
    --*(_DWORD *)v13;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v13, *(_DWORD *)v13);
    v19 = (struct _RTL_CRITICAL_SECTION *)((char *)v13 + 512);
    if ( *(_DWORD *)v13 )
    {
      LeaveCriticalSection(v19);
    }
    else
    {
      LeaveCriticalSection(v19);
      DereferenceLdapConnection2((__int64)v13, 1);
    }
    return v17;
  }
  else
  {
    SetConnectionError(0, 0x59u, v12);
    return 89;
  }
}

```

## disassembly

```asm
0x18003d0d0  push    rbx
0x18003d0d2  push    rbp
0x18003d0d3  push    rsi
0x18003d0d4  push    rdi
0x18003d0d5  push    r14
0x18003d0d7  sub     rsp, 60h
0x18003d0db  mov     rsi, r9
0x18003d0de  mov     [rsp+88h+var_38], 0
0x18003d0e6  mov     rbp, r8
0x18003d0e9  mov     [rsp+88h+res], 0
0x18003d0f2  mov     r14, rdx
0x18003d0f5  mov     rdi, rcx
0x18003d0f8  call    GetConnectionPointer
0x18003d0fd  mov     rbx, rax
0x18003d100  test    rax, rax
0x18003d103  jnz     short loc_18003D118
0x18003d105  lea     ebx, [rax+59h]
0x18003d108  xor     ecx, ecx
0x18003d10a  mov     edx, ebx
0x18003d10c  call    SetConnectionError
0x18003d111  mov     eax, ebx
0x18003d113  jmp     loc_18003D242
0x18003d118  lea     rax, [rsp+88h+var_38]
0x18003d11d  mov     r9, rsi; unsigned __int16 *
0x18003d120  mov     [rsp+88h+var_40], rax; unsigned int *
0x18003d125  mov     r8, rbp; unsigned __int16 *
0x18003d128  mov     rax, [rsp+88h+ClientControls]
0x18003d130  mov     rdx, r14; unsigned __int16 *
0x18003d133  mov     [rsp+88h+var_48], rax; struct ldapcontrolW **
0x18003d138  mov     rcx, rbx; struct ldap_connection *
0x18003d13b  mov     rax, [rsp+88h+ServerControls]
0x18003d143  mov     [rsp+88h+var_50], rax; struct ldapcontrolW **
0x18003d148  mov     rax, [rsp+88h+Data]
0x18003d150  mov     [rsp+88h+var_58], 1; unsigned __int8
0x18003d155  mov     [rsp+88h+var_60], 1; unsigned __int8
0x18003d15a  mov     [rsp+88h+var_68], rax; struct berval *
0x18003d15f  call    ?LdapCompare@@YAKPEAUldap_connection@@PEAG11PEAUberval@@EEPEAPEAUldapcontrolW@@3PEAK@Z; LdapCompare(ldap_connection *,ushort *,ushort *,ushort *,berval *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18003d164  mov     ebp, [rsp+88h+var_38]
0x18003d168  mov     esi, eax
0x18003d16a  cmp     ebp, 0FFFFFFFFh
0x18003d16d  jz      short loc_18003D1C8
0x18003d16f  xor     r9d, r9d
0x18003d172  mov     qword ptr [rsp+88h+var_60], 0
0x18003d17b  lea     rax, [rsp+88h+res]
0x18003d180  mov     edx, ebp
0x18003d182  mov     rcx, rbx
0x18003d185  mov     [rsp+88h+var_68], rax
0x18003d18a  lea     r8d, [r9+1]
0x18003d18e  call    ldap_result_with_error
0x18003d193  mov     rdx, [rsp+88h+res]; res
0x18003d198  mov     esi, eax
0x18003d19a  test    rdx, rdx
0x18003d19d  jnz     short loc_18003D1B8
0x18003d19f  mov     r8b, 1
0x18003d1a2  mov     edx, ebp
0x18003d1a4  mov     rcx, rbx
0x18003d1a7  call    LdapAbandon
0x18003d1ac  mov     edx, esi
0x18003d1ae  mov     rcx, rbx
0x18003d1b1  call    SetConnectionError
0x18003d1b6  jmp     short loc_18003D1C8
0x18003d1b8  mov     r8d, 1; freeit
0x18003d1be  mov     rcx, rdi; ld
0x18003d1c1  call    ldap_result2error
0x18003d1c6  mov     esi, eax
0x18003d1c8  lea     rdi, [rbx+200h]
0x18003d1cf  mov     rcx, rdi; lpCriticalSection
0x18003d1d2  call    cs:__imp_EnterCriticalSection
0x18003d1d9  nop     dword ptr [rax+rax+00h]
0x18003d1de  dec     dword ptr [rbx]
0x18003d1e0  cmp     cs:g_fTracingOn, 0
0x18003d1e7  jz      short loc_18003D211
0x18003d1e9  cmp     cs:g_fProviderEnabled, 0
0x18003d1f0  jz      short loc_18003D211
0x18003d1f2  mov     ecx, 4
0x18003d1f7  test    byte ptr cs:g_ulTraceFlags, cl
0x18003d1fd  jz      short loc_18003D211
0x18003d1ff  mov     r9d, [rbx]
0x18003d202  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18003d209  mov     r8, rbx
0x18003d20c  call    LDAPClientPrint
0x18003d211  cmp     dword ptr [rbx], 0
0x18003d214  mov     rcx, rdi; lpCriticalSection
0x18003d217  jnz     short loc_18003D234
0x18003d219  call    cs:__imp_LeaveCriticalSection
0x18003d220  nop     dword ptr [rax+rax+00h]
0x18003d225  mov     edx, 1
0x18003d22a  mov     rcx, rbx
0x18003d22d  call    DereferenceLdapConnection2
0x18003d232  jmp     short loc_18003D240
0x18003d234  call    cs:__imp_LeaveCriticalSection
0x18003d23b  nop     dword ptr [rax+rax+00h]
0x18003d240  mov     eax, esi
0x18003d242  add     rsp, 60h
0x18003d246  pop     r14
0x18003d248  pop     rdi
0x18003d249  pop     rsi
0x18003d24a  pop     rbp
0x18003d24b  pop     rbx
0x18003d24c  retn
```
