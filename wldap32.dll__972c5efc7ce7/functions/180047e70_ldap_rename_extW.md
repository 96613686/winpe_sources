# ldap_rename_extW

- ea: `0x180047e70`
- end: `0x180047f75`
- name: `ldap_rename_extW`
- size: `261`
- prototype: `ULONG __cdecl(LDAP *ld, const PWSTR dn, const PWSTR NewRDN, const PWSTR NewParent, INT DeleteOldRdn, PLDAPControlW *ServerControls, PLDAPControlW *ClientControls, ULONG *MessageNumber)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000cda0`
- `0x180046f48`
- `0x180047e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047efb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047efb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047f42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047f5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047f42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047f5d`

## pseudocode

```c
ULONG __cdecl ldap_rename_extW(
        LDAP *ld,
        const PWSTR dn,
        const PWSTR NewRDN,
        const PWSTR NewParent,
        INT DeleteOldRdn,
        PLDAPControlW *ServerControls,
        PLDAPControlW *ClientControls,
        ULONG *MessageNumber)
{
  struct ldap_connection *ConnectionPointer; // rax
  __int64 v12; // r8
  __int64 v13; // rbx
  ULONG v15; // esi
  struct _RTL_CRITICAL_SECTION *v16; // rcx

  ConnectionPointer = (struct ldap_connection *)GetConnectionPointer(ld, dn, NewRDN);
  v13 = (__int64)ConnectionPointer;
  if ( ConnectionPointer )
  {
    v15 = LdapRename(
            ConnectionPointer,
            dn,
            NewRDN,
            NewParent,
            DeleteOldRdn,
            1u,
            0,
            ServerControls,
            ClientControls,
            MessageNumber);
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
0x180047e70  push    rbx
0x180047e72  push    rbp
0x180047e73  push    rsi
0x180047e74  push    rdi
0x180047e75  sub     rsp, 58h
0x180047e79  mov     rdi, r9
0x180047e7c  mov     rsi, r8
0x180047e7f  mov     rbp, rdx
0x180047e82  call    GetConnectionPointer
0x180047e87  mov     rbx, rax
0x180047e8a  test    rax, rax
0x180047e8d  jnz     short loc_180047EA2
0x180047e8f  lea     ebx, [rax+59h]
0x180047e92  xor     ecx, ecx
0x180047e94  mov     edx, ebx
0x180047e96  call    SetConnectionError
0x180047e9b  mov     eax, ebx
0x180047e9d  jmp     loc_180047F6B
0x180047ea2  mov     rax, [rsp+78h+MessageNumber]
0x180047eaa  mov     r9, rdi; unsigned __int16 *
0x180047ead  mov     [rsp+78h+var_30], rax; unsigned int *
0x180047eb2  mov     r8, rsi; unsigned __int16 *
0x180047eb5  mov     rax, [rsp+78h+ClientControls]
0x180047ebd  mov     rdx, rbp; unsigned __int16 *
0x180047ec0  mov     [rsp+78h+var_38], rax; struct ldapcontrolW **
0x180047ec5  mov     rcx, rbx; struct ldap_connection *
0x180047ec8  mov     rax, [rsp+78h+ServerControls]
0x180047ed0  mov     [rsp+78h+var_40], rax; struct ldapcontrolW **
0x180047ed5  mov     eax, [rsp+78h+DeleteOldRdn]
0x180047edc  mov     [rsp+78h+var_48], 0; unsigned __int8
0x180047ee1  mov     [rsp+78h+var_50], 1; unsigned __int8
0x180047ee6  mov     [rsp+78h+var_58], eax; int
0x180047eea  call    ?LdapRename@@YAKPEAUldap_connection@@PEAG11HEEPEAPEAUldapcontrolW@@2PEAK@Z; LdapRename(ldap_connection *,ushort *,ushort *,ushort *,int,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x180047eef  lea     rdi, [rbx+200h]
0x180047ef6  mov     esi, eax
0x180047ef8  mov     rcx, rdi; lpCriticalSection
0x180047efb  call    cs:__imp_EnterCriticalSection
0x180047f02  nop     dword ptr [rax+rax+00h]
0x180047f07  dec     dword ptr [rbx]
0x180047f09  cmp     cs:g_fTracingOn, 0
0x180047f10  jz      short loc_180047F3A
0x180047f12  cmp     cs:g_fProviderEnabled, 0
0x180047f19  jz      short loc_180047F3A
0x180047f1b  mov     ecx, 4
0x180047f20  test    byte ptr cs:g_ulTraceFlags, cl
0x180047f26  jz      short loc_180047F3A
0x180047f28  mov     r9d, [rbx]
0x180047f2b  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180047f32  mov     r8, rbx
0x180047f35  call    LDAPClientPrint
0x180047f3a  cmp     dword ptr [rbx], 0
0x180047f3d  mov     rcx, rdi; lpCriticalSection
0x180047f40  jnz     short loc_180047F5D
0x180047f42  call    cs:__imp_LeaveCriticalSection
0x180047f49  nop     dword ptr [rax+rax+00h]
0x180047f4e  mov     edx, 1
0x180047f53  mov     rcx, rbx
0x180047f56  call    DereferenceLdapConnection2
0x180047f5b  jmp     short loc_180047F69
0x180047f5d  call    cs:__imp_LeaveCriticalSection
0x180047f64  nop     dword ptr [rax+rax+00h]
0x180047f69  mov     eax, esi
0x180047f6b  add     rsp, 58h
0x180047f6f  pop     rdi
0x180047f70  pop     rsi
0x180047f71  pop     rbp
0x180047f72  pop     rbx
0x180047f73  retn
```
