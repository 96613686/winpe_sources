# ldap_rename_ext_sW

- ea: `0x180048210`
- end: `0x180048389`
- name: `ldap_rename_ext_sW`
- size: `377`
- prototype: `ULONG __cdecl(LDAP *ld, const PWSTR dn, const PWSTR NewRDN, const PWSTR NewParent, INT DeleteOldRdn, PLDAPControlW *ServerControls, PLDAPControlW *ClientControls)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000bf40`
- `0x18000cda0`
- `0x18001611c`
- `0x180016360`
- `0x180046f48`
- `0x180048210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004830f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004830f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048356`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048371`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048356`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048371`

## pseudocode

```c
ULONG __cdecl ldap_rename_ext_sW(
        LDAP *ld,
        const PWSTR dn,
        const PWSTR NewRDN,
        const PWSTR NewParent,
        INT DeleteOldRdn,
        PLDAPControlW *ServerControls,
        PLDAPControlW *ClientControls)
{
  struct ldap_connection *ConnectionPointer; // rax
  __int64 v11; // r8
  struct ldap_connection *v12; // rbx
  unsigned int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // esi
  __int64 v17; // r8
  struct _RTL_CRITICAL_SECTION *v18; // rcx
  unsigned int v19; // [rsp+50h] [rbp-38h] BYREF
  LDAPMessage *res; // [rsp+58h] [rbp-30h] BYREF

  v19 = 0;
  res = 0;
  ConnectionPointer = (struct ldap_connection *)GetConnectionPointer(ld, dn, NewRDN);
  v12 = ConnectionPointer;
  if ( ConnectionPointer )
  {
    v14 = LdapRename(
            ConnectionPointer,
            dn,
            NewRDN,
            NewParent,
            DeleteOldRdn,
            1u,
            1u,
            ServerControls,
            ClientControls,
            &v19);
    v15 = v19;
    v16 = v14;
    if ( v19 != -1 )
    {
      v16 = ldap_result_with_error(v12, v19, 1u, 0, &res, 0);
      if ( res )
      {
        v16 = ldap_result2error(*((LDAP **)v12 + 56), res, 1u);
      }
      else
      {
        LdapAbandon((__int64)v12, v15, 1);
        SetConnectionError((__int64)v12, v16, v17);
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 512));
    --*(_DWORD *)v12;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v12, *(_DWORD *)v12);
    v18 = (struct _RTL_CRITICAL_SECTION *)((char *)v12 + 512);
    if ( *(_DWORD *)v12 )
    {
      LeaveCriticalSection(v18);
    }
    else
    {
      LeaveCriticalSection(v18);
      DereferenceLdapConnection2((__int64)v12, 1);
    }
    return v16;
  }
  else
  {
    SetConnectionError(0, 0x59u, v11);
    return 89;
  }
}

```

## disassembly

```asm
0x180048210  push    rbx
0x180048212  push    rbp
0x180048213  push    rsi
0x180048214  push    rdi
0x180048215  sub     rsp, 68h
0x180048219  mov     rdi, r9
0x18004821c  mov     [rsp+88h+var_38], 0
0x180048224  mov     rsi, r8
0x180048227  mov     [rsp+88h+res], 0
0x180048230  mov     rbp, rdx
0x180048233  call    GetConnectionPointer
0x180048238  mov     rbx, rax
0x18004823b  test    rax, rax
0x18004823e  jnz     short loc_180048253
0x180048240  lea     ebx, [rax+59h]
0x180048243  xor     ecx, ecx
0x180048245  mov     edx, ebx
0x180048247  call    SetConnectionError
0x18004824c  mov     eax, ebx
0x18004824e  jmp     loc_18004837F
0x180048253  lea     rax, [rsp+88h+var_38]
0x180048258  mov     r9, rdi; unsigned __int16 *
0x18004825b  mov     [rsp+88h+var_40], rax; unsigned int *
0x180048260  mov     r8, rsi; unsigned __int16 *
0x180048263  mov     rax, [rsp+88h+ClientControls]
0x18004826b  mov     rdx, rbp; unsigned __int16 *
0x18004826e  mov     [rsp+88h+var_48], rax; struct ldapcontrolW **
0x180048273  mov     rcx, rbx; struct ldap_connection *
0x180048276  mov     rax, [rsp+88h+ServerControls]
0x18004827e  mov     [rsp+88h+var_50], rax; struct ldapcontrolW **
0x180048283  mov     eax, [rsp+88h+DeleteOldRdn]
0x18004828a  mov     [rsp+88h+var_58], 1; unsigned __int8
0x18004828f  mov     [rsp+88h+var_60], 1; unsigned __int8
0x180048294  mov     [rsp+88h+var_68], eax; int
0x180048298  call    ?LdapRename@@YAKPEAUldap_connection@@PEAG11HEEPEAPEAUldapcontrolW@@2PEAK@Z; LdapRename(ldap_connection *,ushort *,ushort *,ushort *,int,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18004829d  mov     edi, [rsp+88h+var_38]
0x1800482a1  mov     esi, eax
0x1800482a3  cmp     edi, 0FFFFFFFFh
0x1800482a6  jz      short loc_180048305
0x1800482a8  xor     r9d, r9d
0x1800482ab  mov     qword ptr [rsp+88h+var_60], 0
0x1800482b4  lea     rax, [rsp+88h+res]
0x1800482b9  mov     edx, edi
0x1800482bb  mov     rcx, rbx
0x1800482be  mov     qword ptr [rsp+88h+var_68], rax
0x1800482c3  lea     r8d, [r9+1]
0x1800482c7  call    ldap_result_with_error
0x1800482cc  mov     rdx, [rsp+88h+res]; res
0x1800482d1  mov     esi, eax
0x1800482d3  test    rdx, rdx
0x1800482d6  jnz     short loc_1800482F1
0x1800482d8  mov     r8b, 1
0x1800482db  mov     edx, edi
0x1800482dd  mov     rcx, rbx
0x1800482e0  call    LdapAbandon
0x1800482e5  mov     edx, esi
0x1800482e7  mov     rcx, rbx
0x1800482ea  call    SetConnectionError
0x1800482ef  jmp     short loc_180048305
0x1800482f1  mov     rcx, [rbx+1C0h]; ld
0x1800482f8  mov     r8d, 1; freeit
0x1800482fe  call    ldap_result2error
0x180048303  mov     esi, eax
0x180048305  lea     rdi, [rbx+200h]
0x18004830c  mov     rcx, rdi; lpCriticalSection
0x18004830f  call    cs:__imp_EnterCriticalSection
0x180048316  nop     dword ptr [rax+rax+00h]
0x18004831b  dec     dword ptr [rbx]
0x18004831d  cmp     cs:g_fTracingOn, 0
0x180048324  jz      short loc_18004834E
0x180048326  cmp     cs:g_fProviderEnabled, 0
0x18004832d  jz      short loc_18004834E
0x18004832f  mov     ecx, 4
0x180048334  test    byte ptr cs:g_ulTraceFlags, cl
0x18004833a  jz      short loc_18004834E
0x18004833c  mov     r9d, [rbx]
0x18004833f  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180048346  mov     r8, rbx
0x180048349  call    LDAPClientPrint
0x18004834e  cmp     dword ptr [rbx], 0
0x180048351  mov     rcx, rdi; lpCriticalSection
0x180048354  jnz     short loc_180048371
0x180048356  call    cs:__imp_LeaveCriticalSection
0x18004835d  nop     dword ptr [rax+rax+00h]
0x180048362  mov     edx, 1
0x180048367  mov     rcx, rbx
0x18004836a  call    DereferenceLdapConnection2
0x18004836f  jmp     short loc_18004837D
0x180048371  call    cs:__imp_LeaveCriticalSection
0x180048378  nop     dword ptr [rax+rax+00h]
0x18004837d  mov     eax, esi
0x18004837f  add     rsp, 68h
0x180048383  pop     rdi
0x180048384  pop     rsi
0x180048385  pop     rbp
0x180048386  pop     rbx
0x180048387  retn
```
