# ldap_compareW

- ea: `0x18003c9e0`
- end: `0x18003cadf`
- name: `ldap_compareW`
- size: `255`
- prototype: `ULONG __cdecl(LDAP *ld, const PWSTR dn, const PWSTR attr, PWSTR value)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000cda0`
- `0x18003c254`
- `0x18003c9e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ca63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ca63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003caaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cac5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003caaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cac5`

## pseudocode

```c
ULONG __cdecl ldap_compareW(LDAP *ld, const PWSTR dn, const PWSTR attr, PWSTR value)
{
  _DWORD *ConnectionPointer; // rbx
  __int64 v8; // r8
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  unsigned int v11[14]; // [rsp+50h] [rbp-38h] BYREF

  v11[0] = 0;
  ConnectionPointer = (_DWORD *)GetConnectionPointer(ld, dn, attr);
  if ( ConnectionPointer )
  {
    LdapCompare((struct ldap_connection *)ConnectionPointer, dn, attr, value, 0, 1u, 0, 0, 0, v11);
    EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 128));
    --*ConnectionPointer;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)ConnectionPointer, *ConnectionPointer);
    v10 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 128);
    if ( *ConnectionPointer )
    {
      LeaveCriticalSection(v10);
    }
    else
    {
      LeaveCriticalSection(v10);
      DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
    }
    return v11[0];
  }
  else
  {
    SetConnectionError(0, 0x59u, v8);
    return -1;
  }
}

```

## disassembly

```asm
0x18003c9e0  push    rbx
0x18003c9e2  push    rbp
0x18003c9e3  push    rsi
0x18003c9e4  push    rdi
0x18003c9e5  sub     rsp, 68h
0x18003c9e9  mov     rdi, r9
0x18003c9ec  mov     [rsp+88h+var_38], 0
0x18003c9f4  mov     rsi, r8
0x18003c9f7  mov     rbp, rdx
0x18003c9fa  call    GetConnectionPointer
0x18003c9ff  mov     rbx, rax
0x18003ca02  test    rax, rax
0x18003ca05  jnz     short loc_18003CA19
0x18003ca07  lea     edx, [rax+59h]
0x18003ca0a  xor     ecx, ecx
0x18003ca0c  call    SetConnectionError
0x18003ca11  or      eax, 0FFFFFFFFh
0x18003ca14  jmp     loc_18003CAD5
0x18003ca19  lea     rax, [rsp+88h+var_38]
0x18003ca1e  mov     r9, rdi; unsigned __int16 *
0x18003ca21  mov     [rsp+88h+var_40], rax; unsigned int *
0x18003ca26  mov     r8, rsi; unsigned __int16 *
0x18003ca29  mov     [rsp+88h+var_48], 0; struct ldapcontrolW **
0x18003ca32  mov     rdx, rbp; unsigned __int16 *
0x18003ca35  mov     [rsp+88h+var_50], 0; struct ldapcontrolW **
0x18003ca3e  mov     rcx, rbx; struct ldap_connection *
0x18003ca41  mov     [rsp+88h+var_58], 0; unsigned __int8
0x18003ca46  mov     [rsp+88h+var_60], 1; unsigned __int8
0x18003ca4b  mov     [rsp+88h+var_68], 0; struct berval *
0x18003ca54  call    ?LdapCompare@@YAKPEAUldap_connection@@PEAG11PEAUberval@@EEPEAPEAUldapcontrolW@@3PEAK@Z; LdapCompare(ldap_connection *,ushort *,ushort *,ushort *,berval *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18003ca59  lea     rdi, [rbx+200h]
0x18003ca60  mov     rcx, rdi; lpCriticalSection
0x18003ca63  call    cs:__imp_EnterCriticalSection
0x18003ca6a  nop     dword ptr [rax+rax+00h]
0x18003ca6f  dec     dword ptr [rbx]
0x18003ca71  cmp     cs:g_fTracingOn, 0
0x18003ca78  jz      short loc_18003CAA2
0x18003ca7a  cmp     cs:g_fProviderEnabled, 0
0x18003ca81  jz      short loc_18003CAA2
0x18003ca83  mov     ecx, 4
0x18003ca88  test    byte ptr cs:g_ulTraceFlags, cl
0x18003ca8e  jz      short loc_18003CAA2
0x18003ca90  mov     r9d, [rbx]
0x18003ca93  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18003ca9a  mov     r8, rbx
0x18003ca9d  call    LDAPClientPrint
0x18003caa2  cmp     dword ptr [rbx], 0
0x18003caa5  mov     rcx, rdi; lpCriticalSection
0x18003caa8  jnz     short loc_18003CAC5
0x18003caaa  call    cs:__imp_LeaveCriticalSection
0x18003cab1  nop     dword ptr [rax+rax+00h]
0x18003cab6  mov     edx, 1
0x18003cabb  mov     rcx, rbx
0x18003cabe  call    DereferenceLdapConnection2
0x18003cac3  jmp     short loc_18003CAD1
0x18003cac5  call    cs:__imp_LeaveCriticalSection
0x18003cacc  nop     dword ptr [rax+rax+00h]
0x18003cad1  mov     eax, [rsp+88h+var_38]
0x18003cad5  add     rsp, 68h
0x18003cad9  pop     rdi
0x18003cada  pop     rsi
0x18003cadb  pop     rbp
0x18003cadc  pop     rbx
0x18003cadd  retn
```
