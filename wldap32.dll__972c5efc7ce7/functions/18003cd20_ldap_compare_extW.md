# ldap_compare_extW

- ea: `0x18003cd20`
- end: `0x18003ce27`
- name: `ldap_compare_extW`
- size: `263`
- prototype: `ULONG __cdecl(LDAP *ld, const PWSTR dn, const PWSTR Attr, const PWSTR Value, struct berval *Data, PLDAPControlW *ServerControls, PLDAPControlW *ClientControls, ULONG *MessageNumber)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000cda0`
- `0x18003c254`
- `0x18003cd20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cdad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cdad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cdf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ce0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cdf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ce0f`

## pseudocode

```c
ULONG __cdecl ldap_compare_extW(
        LDAP *ld,
        const PWSTR dn,
        const PWSTR Attr,
        const PWSTR Value,
        struct berval *Data,
        PLDAPControlW *ServerControls,
        PLDAPControlW *ClientControls,
        ULONG *MessageNumber)
{
  struct ldap_connection *ConnectionPointer; // rax
  __int64 v12; // r8
  __int64 v13; // rbx
  ULONG v15; // esi
  struct _RTL_CRITICAL_SECTION *v16; // rcx

  ConnectionPointer = (struct ldap_connection *)GetConnectionPointer(ld, dn, Attr);
  v13 = (__int64)ConnectionPointer;
  if ( ConnectionPointer )
  {
    v15 = LdapCompare(ConnectionPointer, dn, Attr, Value, Data, 1u, 0, ServerControls, ClientControls, MessageNumber);
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 512));
    --*(_DWORD *)v13;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", v13, *(_DWORD *)v13);
    v16 = (struct _RTL_CRITICAL_SECTION *)(v13 + 512);
    if ( *(_DWORD *)v13 )
    {
      LeaveCriticalSection(v16);
    }
    else
    {
      LeaveCriticalSection(v16);
      DereferenceLdapConnection2(v13, 1);
    }
    return v15;
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
0x18003cd20  push    rbx
0x18003cd22  push    rbp
0x18003cd23  push    rsi
0x18003cd24  push    rdi
0x18003cd25  sub     rsp, 58h
0x18003cd29  mov     rdi, r9
0x18003cd2c  mov     rsi, r8
0x18003cd2f  mov     rbp, rdx
0x18003cd32  call    GetConnectionPointer
0x18003cd37  mov     rbx, rax
0x18003cd3a  test    rax, rax
0x18003cd3d  jnz     short loc_18003CD52
0x18003cd3f  lea     ebx, [rax+59h]
0x18003cd42  xor     ecx, ecx
0x18003cd44  mov     edx, ebx
0x18003cd46  call    SetConnectionError
0x18003cd4b  mov     eax, ebx
0x18003cd4d  jmp     loc_18003CE1D
0x18003cd52  mov     rax, [rsp+78h+MessageNumber]
0x18003cd5a  mov     r9, rdi; unsigned __int16 *
0x18003cd5d  mov     [rsp+78h+var_30], rax; unsigned int *
0x18003cd62  mov     r8, rsi; unsigned __int16 *
0x18003cd65  mov     rax, [rsp+78h+ClientControls]
0x18003cd6d  mov     rdx, rbp; unsigned __int16 *
0x18003cd70  mov     [rsp+78h+var_38], rax; struct ldapcontrolW **
0x18003cd75  mov     rcx, rbx; struct ldap_connection *
0x18003cd78  mov     rax, [rsp+78h+ServerControls]
0x18003cd80  mov     [rsp+78h+var_40], rax; struct ldapcontrolW **
0x18003cd85  mov     rax, [rsp+78h+Data]
0x18003cd8d  mov     [rsp+78h+var_48], 0; unsigned __int8
0x18003cd92  mov     [rsp+78h+var_50], 1; unsigned __int8
0x18003cd97  mov     [rsp+78h+var_58], rax; struct berval *
0x18003cd9c  call    ?LdapCompare@@YAKPEAUldap_connection@@PEAG11PEAUberval@@EEPEAPEAUldapcontrolW@@3PEAK@Z; LdapCompare(ldap_connection *,ushort *,ushort *,ushort *,berval *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18003cda1  lea     rdi, [rbx+200h]
0x18003cda8  mov     esi, eax
0x18003cdaa  mov     rcx, rdi; lpCriticalSection
0x18003cdad  call    cs:__imp_EnterCriticalSection
0x18003cdb4  nop     dword ptr [rax+rax+00h]
0x18003cdb9  dec     dword ptr [rbx]
0x18003cdbb  cmp     cs:g_fTracingOn, 0
0x18003cdc2  jz      short loc_18003CDEC
0x18003cdc4  cmp     cs:g_fProviderEnabled, 0
0x18003cdcb  jz      short loc_18003CDEC
0x18003cdcd  mov     ecx, 4
0x18003cdd2  test    byte ptr cs:g_ulTraceFlags, cl
0x18003cdd8  jz      short loc_18003CDEC
0x18003cdda  mov     r9d, [rbx]
0x18003cddd  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18003cde4  mov     r8, rbx
0x18003cde7  call    LDAPClientPrint
0x18003cdec  cmp     dword ptr [rbx], 0
0x18003cdef  mov     rcx, rdi; lpCriticalSection
0x18003cdf2  jnz     short loc_18003CE0F
0x18003cdf4  call    cs:__imp_LeaveCriticalSection
0x18003cdfb  nop     dword ptr [rax+rax+00h]
0x18003ce00  mov     edx, 1
0x18003ce05  mov     rcx, rbx
0x18003ce08  call    DereferenceLdapConnection2
0x18003ce0d  jmp     short loc_18003CE1B
0x18003ce0f  call    cs:__imp_LeaveCriticalSection
0x18003ce16  nop     dword ptr [rax+rax+00h]
0x18003ce1b  mov     eax, esi
0x18003ce1d  add     rsp, 58h
0x18003ce21  pop     rdi
0x18003ce22  pop     rsi
0x18003ce23  pop     rbp
0x18003ce24  pop     rbx
0x18003ce25  retn
```
