# ldap_delete_extW

- ea: `0x18003e950`
- end: `0x18003ea30`
- name: `ldap_delete_extW`
- size: `224`
- prototype: `ULONG __cdecl(LDAP *ld, const PWSTR dn, PLDAPControlW *ServerControls, PLDAPControlW *ClientControls, ULONG *MessageNumber)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003e7b0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000cda0`
- `0x18003e250`
- `0x18003e950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e9b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e9b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e9fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ea18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e9fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ea18`

## pseudocode

```c
ULONG __cdecl ldap_delete_extW(
        LDAP *ld,
        const PWSTR dn,
        PLDAPControlW *ServerControls,
        PLDAPControlW *ClientControls,
        ULONG *MessageNumber)
{
  _DWORD *ConnectionPointer; // rbx
  __int64 v9; // r8
  ULONG v11; // esi
  struct _RTL_CRITICAL_SECTION *v12; // rcx

  ConnectionPointer = (_DWORD *)GetConnectionPointer(ld, dn, ServerControls);
  if ( ConnectionPointer )
  {
    v11 = LdapDelete(
            (struct ldap_connection *)ConnectionPointer,
            dn,
            1u,
            0,
            ServerControls,
            ClientControls,
            MessageNumber);
    EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 128));
    --*ConnectionPointer;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)ConnectionPointer, *ConnectionPointer);
    v12 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 128);
    if ( *ConnectionPointer )
    {
      LeaveCriticalSection(v12);
    }
    else
    {
      LeaveCriticalSection(v12);
      DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
    }
    return v11;
  }
  else
  {
    SetConnectionError(0, 0x59u, v9);
    return 89;
  }
}

```

## disassembly

```asm
0x18003e950  push    rbx
0x18003e952  push    rbp
0x18003e953  push    rsi
0x18003e954  push    rdi
0x18003e955  sub     rsp, 48h
0x18003e959  mov     rdi, r9
0x18003e95c  mov     rsi, r8
0x18003e95f  mov     rbp, rdx
0x18003e962  call    GetConnectionPointer
0x18003e967  mov     rbx, rax
0x18003e96a  test    rax, rax
0x18003e96d  jnz     short loc_18003E982
0x18003e96f  lea     ebx, [rax+59h]
0x18003e972  xor     ecx, ecx
0x18003e974  mov     edx, ebx
0x18003e976  call    SetConnectionError
0x18003e97b  mov     eax, ebx
0x18003e97d  jmp     loc_18003EA26
0x18003e982  mov     rax, [rsp+68h+MessageNumber]
0x18003e98a  xor     r9d, r9d; unsigned __int8
0x18003e98d  mov     [rsp+68h+var_38], rax; unsigned int *
0x18003e992  mov     r8b, 1; unsigned __int8
0x18003e995  mov     [rsp+68h+var_40], rdi; struct ldapcontrolW **
0x18003e99a  mov     rdx, rbp; unsigned __int16 *
0x18003e99d  mov     rcx, rbx; struct ldap_connection *
0x18003e9a0  mov     [rsp+68h+var_48], rsi; struct ldapcontrolW **
0x18003e9a5  call    ?LdapDelete@@YAKPEAUldap_connection@@PEAGEEPEAPEAUldapcontrolW@@2PEAK@Z; LdapDelete(ldap_connection *,ushort *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18003e9aa  lea     rdi, [rbx+200h]
0x18003e9b1  mov     esi, eax
0x18003e9b3  mov     rcx, rdi; lpCriticalSection
0x18003e9b6  call    cs:__imp_EnterCriticalSection
0x18003e9bd  nop     dword ptr [rax+rax+00h]
0x18003e9c2  dec     dword ptr [rbx]
0x18003e9c4  cmp     cs:g_fTracingOn, 0
0x18003e9cb  jz      short loc_18003E9F5
0x18003e9cd  cmp     cs:g_fProviderEnabled, 0
0x18003e9d4  jz      short loc_18003E9F5
0x18003e9d6  mov     ecx, 4
0x18003e9db  test    byte ptr cs:g_ulTraceFlags, cl
0x18003e9e1  jz      short loc_18003E9F5
0x18003e9e3  mov     r9d, [rbx]
0x18003e9e6  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18003e9ed  mov     r8, rbx
0x18003e9f0  call    LDAPClientPrint
0x18003e9f5  cmp     dword ptr [rbx], 0
0x18003e9f8  mov     rcx, rdi; lpCriticalSection
0x18003e9fb  jnz     short loc_18003EA18
0x18003e9fd  call    cs:__imp_LeaveCriticalSection
0x18003ea04  nop     dword ptr [rax+rax+00h]
0x18003ea09  mov     edx, 1
0x18003ea0e  mov     rcx, rbx
0x18003ea11  call    DereferenceLdapConnection2
0x18003ea16  jmp     short loc_18003EA24
0x18003ea18  call    cs:__imp_LeaveCriticalSection
0x18003ea1f  nop     dword ptr [rax+rax+00h]
0x18003ea24  mov     eax, esi
0x18003ea26  add     rsp, 48h
0x18003ea2a  pop     rdi
0x18003ea2b  pop     rsi
0x18003ea2c  pop     rbp
0x18003ea2d  pop     rbx
0x18003ea2e  retn
```
