# ldap_rename_extA

- ea: `0x180047c30`
- end: `0x180047e6a`
- name: `ldap_rename_extA`
- size: `570`
- prototype: `ULONG __cdecl(LDAP *ld, const PSTR dn, const PSTR NewRDN, const PSTR NewParent, INT DeleteOldRdn, PLDAPControlA *ServerControls, PLDAPControlA *ClientControls, ULONG *MessageNumber)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000b440`
- `0x18000cda0`
- `0x18001ffa0`
- `0x180046f48`
- `0x180047c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047de0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047de0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047e27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047e42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047e27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047e42`

## pseudocode

```c
ULONG __cdecl ldap_rename_extA(
        LDAP *ld,
        const PSTR dn,
        const PSTR NewRDN,
        const PSTR NewParent,
        INT DeleteOldRdn,
        PLDAPControlA *ServerControls,
        PLDAPControlA *ClientControls,
        ULONG *MessageNumber)
{
  ULONG v8; // r13d
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // r14
  __int64 ConnectionPointer; // rax
  __int64 v14; // r8
  _DWORD *v15; // rbx
  ULONG v16; // edi
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  ULONG v20; // eax
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  unsigned int v23; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int16 *v24; // [rsp+58h] [rbp-20h]
  unsigned __int16 *v25; // [rsp+60h] [rbp-18h]
  unsigned __int16 *v26; // [rsp+68h] [rbp-10h]

  v8 = -1;
  v26 = 0;
  v9 = 0;
  v23 = -1;
  v10 = 0;
  v24 = 0;
  v25 = 0;
  ConnectionPointer = GetConnectionPointer(ld, dn, NewRDN);
  v15 = (_DWORD *)ConnectionPointer;
  if ( ConnectionPointer && MessageNumber )
  {
    *MessageNumber = -1;
    v16 = ToUnicodeWithAlloc(dn, 1);
    if ( v16 )
    {
      SetConnectionError((__int64)v15, 0x59u, v17);
      goto LABEL_13;
    }
    v16 = ToUnicodeWithAlloc(NewRDN, 1);
    if ( v16 )
    {
      SetConnectionError((__int64)v15, 0x59u, v18);
      v9 = v24;
      goto LABEL_13;
    }
    if ( NewParent )
    {
      v16 = ToUnicodeWithAlloc(NewParent, 1);
      if ( v16 )
      {
        SetConnectionError((__int64)v15, 0x59u, v19);
        v9 = v24;
        v10 = v25;
        goto LABEL_13;
      }
      v10 = v25;
    }
    v9 = v24;
    v20 = LdapRename(
            (struct ldap_connection *)v15,
            v26,
            v24,
            v10,
            DeleteOldRdn,
            0,
            0,
            (struct ldapcontrolW **)ServerControls,
            (struct ldapcontrolW **)ClientControls,
            &v23);
    v8 = v23;
    v16 = v20;
  }
  else
  {
    SetConnectionError(ConnectionPointer, 0x59u, v14);
    v16 = 89;
  }
LABEL_13:
  if ( v26 )
    ldapFree((__int64)v26, 1768838476);
  if ( v9 )
    ldapFree((__int64)v9, 1768838476);
  if ( v10 )
    ldapFree((__int64)v10, 1768838476);
  if ( v15 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 128));
    --*v15;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v15, *v15);
    v21 = (struct _RTL_CRITICAL_SECTION *)(v15 + 128);
    if ( *v15 )
    {
      LeaveCriticalSection(v21);
    }
    else
    {
      LeaveCriticalSection(v21);
      DereferenceLdapConnection2((__int64)v15, 1);
    }
  }
  if ( MessageNumber )
    *MessageNumber = v8;
  return v16;
}

```

## disassembly

```asm
0x180047c30  mov     [rsp-40h+lpMultiByteStr], r8; ldap_rename_ext
0x180047c35  push    rbp
0x180047c36  push    rbx
0x180047c37  push    rsi
0x180047c38  push    rdi
0x180047c39  push    r12
0x180047c3b  push    r13
0x180047c3d  push    r14
0x180047c3f  push    r15
0x180047c41  mov     rbp, rsp
0x180047c44  sub     rsp, 78h
0x180047c48  or      r13d, 0FFFFFFFFh
0x180047c4c  mov     [rbp+var_10], 0
0x180047c54  xor     esi, esi
0x180047c56  mov     [rbp+var_28], r13d
0x180047c5a  xor     r14d, r14d
0x180047c5d  mov     [rbp+var_20], rsi
0x180047c61  mov     [rbp+var_18], r14
0x180047c65  mov     r12, r9
0x180047c68  mov     rdi, rdx
0x180047c6b  call    GetConnectionPointer
0x180047c70  mov     r15, [rbp+MessageNumber]
0x180047c77  mov     rbx, rax
0x180047c7a  test    rax, rax
0x180047c7d  jz      loc_180047D88
0x180047c83  test    r15, r15
0x180047c86  jz      loc_180047D88
0x180047c8c  mov     r9d, 696E554Ch
0x180047c92  mov     [r15], r13d
0x180047c95  lea     r8, [rbp+var_10]
0x180047c99  mov     [rsp+78h+var_58], 1; int
0x180047ca1  or      edx, 0FFFFFFFFh
0x180047ca4  mov     rcx, rdi; lpMultiByteStr
0x180047ca7  call    ToUnicodeWithAlloc
0x180047cac  mov     edi, eax
0x180047cae  test    eax, eax
0x180047cb0  jz      short loc_180047CC2
0x180047cb2  lea     edx, [rsi+59h]
0x180047cb5  mov     rcx, rbx
0x180047cb8  call    SetConnectionError
0x180047cbd  jmp     loc_180047D9A
0x180047cc2  mov     rcx, [rbp+lpMultiByteStr]; lpMultiByteStr
0x180047cc6  lea     r8, [rbp+var_20]
0x180047cca  mov     esi, 696E554Ch
0x180047ccf  mov     [rsp+78h+var_58], 1; int
0x180047cd7  mov     r9d, esi
0x180047cda  or      edx, 0FFFFFFFFh
0x180047cdd  call    ToUnicodeWithAlloc
0x180047ce2  mov     edi, eax
0x180047ce4  test    eax, eax
0x180047ce6  jz      short loc_180047CFE
0x180047ce8  mov     edx, 59h ; 'Y'
0x180047ced  mov     rcx, rbx
0x180047cf0  call    SetConnectionError
0x180047cf5  mov     rsi, [rbp+var_20]
0x180047cf9  jmp     loc_180047D9A
0x180047cfe  test    r12, r12
0x180047d01  jz      short loc_180047D3E
0x180047d03  mov     r9d, esi
0x180047d06  mov     [rsp+78h+var_58], 1; int
0x180047d0e  lea     r8, [rbp+var_18]
0x180047d12  or      edx, 0FFFFFFFFh
0x180047d15  mov     rcx, r12; lpMultiByteStr
0x180047d18  call    ToUnicodeWithAlloc
0x180047d1d  mov     edi, eax
0x180047d1f  test    eax, eax
0x180047d21  jz      short loc_180047D3A
0x180047d23  mov     edx, 59h ; 'Y'
0x180047d28  mov     rcx, rbx
0x180047d2b  call    SetConnectionError
0x180047d30  mov     rsi, [rbp+var_20]
0x180047d34  mov     r14, [rbp+var_18]
0x180047d38  jmp     short loc_180047D9A
0x180047d3a  mov     r14, [rbp+var_18]
0x180047d3e  mov     rsi, [rbp+var_20]
0x180047d42  lea     rax, [rbp+var_28]
0x180047d46  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180047d4a  mov     r9, r14; unsigned __int16 *
0x180047d4d  mov     [rsp+78h+var_30], rax; unsigned int *
0x180047d52  mov     r8, rsi; unsigned __int16 *
0x180047d55  mov     rax, [rbp+ClientControls]
0x180047d59  mov     rcx, rbx; struct ldap_connection *
0x180047d5c  mov     [rsp+78h+var_38], rax; struct ldapcontrolW **
0x180047d61  mov     rax, [rbp+ServerControls]
0x180047d65  mov     [rsp+78h+var_40], rax; struct ldapcontrolW **
0x180047d6a  mov     eax, [rbp+DeleteOldRdn]
0x180047d6d  mov     [rsp+78h+var_48], 0; unsigned __int8
0x180047d72  mov     [rsp+78h+var_50], 0; unsigned __int8
0x180047d77  mov     [rsp+78h+var_58], eax; int
0x180047d7b  call    ?LdapRename@@YAKPEAUldap_connection@@PEAG11HEEPEAPEAUldapcontrolW@@2PEAK@Z; LdapRename(ldap_connection *,ushort *,ushort *,ushort *,int,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x180047d80  mov     r13d, [rbp+var_28]
0x180047d84  mov     edi, eax
0x180047d86  jmp     short loc_180047D9A
0x180047d88  mov     edx, 59h ; 'Y'
0x180047d8d  mov     rcx, rbx
0x180047d90  call    SetConnectionError
0x180047d95  mov     edi, 59h ; 'Y'
0x180047d9a  mov     rcx, [rbp+var_10]
0x180047d9e  test    rcx, rcx
0x180047da1  jz      short loc_180047DAD
0x180047da3  mov     edx, 696E554Ch
0x180047da8  call    ldapFree
0x180047dad  test    rsi, rsi
0x180047db0  jz      short loc_180047DBF
0x180047db2  mov     edx, 696E554Ch
0x180047db7  mov     rcx, rsi
0x180047dba  call    ldapFree
0x180047dbf  test    r14, r14
0x180047dc2  jz      short loc_180047DD1
0x180047dc4  mov     edx, 696E554Ch
0x180047dc9  mov     rcx, r14
0x180047dcc  call    ldapFree
0x180047dd1  test    rbx, rbx
0x180047dd4  jz      short loc_180047E4E
0x180047dd6  lea     rsi, [rbx+200h]
0x180047ddd  mov     rcx, rsi; lpCriticalSection
0x180047de0  call    cs:__imp_EnterCriticalSection
0x180047de7  nop     dword ptr [rax+rax+00h]
0x180047dec  dec     dword ptr [rbx]
0x180047dee  cmp     cs:g_fTracingOn, 0
0x180047df5  jz      short loc_180047E1F
0x180047df7  cmp     cs:g_fProviderEnabled, 0
0x180047dfe  jz      short loc_180047E1F
0x180047e00  mov     ecx, 4
0x180047e05  test    byte ptr cs:g_ulTraceFlags, cl
0x180047e0b  jz      short loc_180047E1F
0x180047e0d  mov     r9d, [rbx]
0x180047e10  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180047e17  mov     r8, rbx
0x180047e1a  call    LDAPClientPrint
0x180047e1f  cmp     dword ptr [rbx], 0
0x180047e22  mov     rcx, rsi; lpCriticalSection
0x180047e25  jnz     short loc_180047E42
0x180047e27  call    cs:__imp_LeaveCriticalSection
0x180047e2e  nop     dword ptr [rax+rax+00h]
0x180047e33  mov     edx, 1
0x180047e38  mov     rcx, rbx
0x180047e3b  call    DereferenceLdapConnection2
0x180047e40  jmp     short loc_180047E4E
0x180047e42  call    cs:__imp_LeaveCriticalSection
0x180047e49  nop     dword ptr [rax+rax+00h]
0x180047e4e  test    r15, r15
0x180047e51  jz      short loc_180047E56
0x180047e53  mov     [r15], r13d
0x180047e56  mov     eax, edi
0x180047e58  add     rsp, 78h
0x180047e5c  pop     r15
0x180047e5e  pop     r14
0x180047e60  pop     r13
0x180047e62  pop     r12
0x180047e64  pop     rdi
0x180047e65  pop     rsi
0x180047e66  pop     rbx
0x180047e67  pop     rbp
0x180047e68  retn
```
