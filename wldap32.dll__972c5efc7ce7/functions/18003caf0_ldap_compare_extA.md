# ldap_compare_extA

- ea: `0x18003caf0`
- end: `0x18003cd1a`
- name: `ldap_compare_extA`
- size: `554`
- prototype: `ULONG __cdecl(LDAP *ld, const PSTR dn, const PSTR Attr, const PSTR Value, struct berval *Data, PLDAPControlA *ServerControls, PLDAPControlA *ClientControls, ULONG *MessageNumber)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003c9a0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000b440`
- `0x18000cda0`
- `0x18001ffa0`
- `0x18003c254`
- `0x18003caf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cc98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cc98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ccdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ccfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ccdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ccfa`

## pseudocode

```c
ULONG __cdecl ldap_compare_extA(
        LDAP *ld,
        const PSTR dn,
        const PSTR Attr,
        const PSTR Value,
        struct berval *Data,
        PLDAPControlA *ServerControls,
        PLDAPControlA *ClientControls,
        ULONG *MessageNumber)
{
  __int64 ConnectionPointer; // rax
  __int64 v12; // r8
  _DWORD *v13; // rbx
  ULONG v14; // esi
  __int64 v15; // r8
  struct _RTL_CRITICAL_SECTION *v16; // rcx

  ConnectionPointer = GetConnectionPointer(ld, dn, Attr);
  v13 = (_DWORD *)ConnectionPointer;
  if ( ConnectionPointer && MessageNumber )
  {
    *MessageNumber = -1;
    v14 = ToUnicodeWithAlloc(dn, 1);
    if ( v14 || (v14 = ToUnicodeWithAlloc(Attr, 1)) != 0 || Value && !Data && (v14 = ToUnicodeWithAlloc(Value, 1)) != 0 )
      SetConnectionError((__int64)v13, 0x59u, v15);
    else
      v14 = LdapCompare(
              (struct ldap_connection *)v13,
              0,
              0,
              0,
              Data,
              0,
              0,
              (struct ldapcontrolW **)ServerControls,
              (struct ldapcontrolW **)ClientControls,
              MessageNumber);
  }
  else
  {
    SetConnectionError(ConnectionPointer, 0x59u, v12);
    v14 = 89;
  }
  if ( v13 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 128));
    --*v13;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v13, *v13);
    v16 = (struct _RTL_CRITICAL_SECTION *)(v13 + 128);
    if ( *v13 )
    {
      LeaveCriticalSection(v16);
    }
    else
    {
      LeaveCriticalSection(v16);
      DereferenceLdapConnection2((__int64)v13, 1);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18003caf0  push    rbp; ldap_compare_ext
0x18003caf2  push    rbx
0x18003caf3  push    rsi
0x18003caf4  push    rdi
0x18003caf5  push    r12
0x18003caf7  push    r13
0x18003caf9  push    r14
0x18003cafb  push    r15
0x18003cafd  mov     rbp, rsp
0x18003cb00  sub     rsp, 78h
0x18003cb04  xor     edi, edi
0x18003cb06  mov     [rbp+var_18], 0
0x18003cb0e  xor     r14d, r14d
0x18003cb11  mov     [rbp+var_28], rdi
0x18003cb15  mov     [rbp+var_20], r14
0x18003cb19  mov     r12, r9
0x18003cb1c  mov     r13, r8
0x18003cb1f  mov     rsi, rdx
0x18003cb22  call    GetConnectionPointer
0x18003cb27  mov     rbx, rax
0x18003cb2a  test    rax, rax
0x18003cb2d  jz      loc_18003CC40
0x18003cb33  mov     r15, [rbp+MessageNumber]
0x18003cb3a  test    r15, r15
0x18003cb3d  jz      loc_18003CC40
0x18003cb43  mov     r9d, 696E554Ch
0x18003cb49  mov     dword ptr [r15], 0FFFFFFFFh
0x18003cb50  lea     r8, [rbp+var_18]
0x18003cb54  mov     dword ptr [rsp+78h+var_58], 1; int
0x18003cb5c  or      edx, 0FFFFFFFFh
0x18003cb5f  mov     rcx, rsi; lpMultiByteStr
0x18003cb62  call    ToUnicodeWithAlloc
0x18003cb67  mov     esi, eax
0x18003cb69  test    eax, eax
0x18003cb6b  jz      short loc_18003CB7D
0x18003cb6d  lea     edx, [rdi+59h]
0x18003cb70  mov     rcx, rbx
0x18003cb73  call    SetConnectionError
0x18003cb78  jmp     loc_18003CC52
0x18003cb7d  mov     r9d, 696E554Ch
0x18003cb83  mov     dword ptr [rsp+78h+var_58], 1; int
0x18003cb8b  lea     r8, [rbp+var_28]
0x18003cb8f  or      edx, 0FFFFFFFFh
0x18003cb92  mov     rcx, r13; lpMultiByteStr
0x18003cb95  call    ToUnicodeWithAlloc
0x18003cb9a  mov     esi, eax
0x18003cb9c  test    eax, eax
0x18003cb9e  jz      short loc_18003CBB6
0x18003cba0  mov     edx, 59h ; 'Y'
0x18003cba5  mov     rcx, rbx
0x18003cba8  call    SetConnectionError
0x18003cbad  mov     rdi, [rbp+var_28]
0x18003cbb1  jmp     loc_18003CC52
0x18003cbb6  mov     rdi, [rbp+Data]
0x18003cbba  test    r12, r12
0x18003cbbd  jz      short loc_18003CC00
0x18003cbbf  test    rdi, rdi
0x18003cbc2  jnz     short loc_18003CC00
0x18003cbc4  mov     r9d, 696E554Ch
0x18003cbca  mov     dword ptr [rsp+78h+var_58], 1; int
0x18003cbd2  lea     r8, [rbp+var_20]
0x18003cbd6  or      edx, 0FFFFFFFFh
0x18003cbd9  mov     rcx, r12; lpMultiByteStr
0x18003cbdc  call    ToUnicodeWithAlloc
0x18003cbe1  mov     esi, eax
0x18003cbe3  test    eax, eax
0x18003cbe5  jz      short loc_18003CBFC
0x18003cbe7  lea     edx, [rdi+59h]
0x18003cbea  mov     rcx, rbx
0x18003cbed  call    SetConnectionError
0x18003cbf2  mov     rdi, [rbp+var_28]
0x18003cbf6  mov     r14, [rbp+var_20]
0x18003cbfa  jmp     short loc_18003CC52
0x18003cbfc  mov     r14, [rbp+var_20]
0x18003cc00  mov     rax, [rbp+ClientControls]
0x18003cc04  mov     r9, r14; unsigned __int16 *
0x18003cc07  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18003cc0b  mov     rcx, rbx; struct ldap_connection *
0x18003cc0e  mov     [rsp+78h+var_30], r15; unsigned int *
0x18003cc13  mov     [rsp+78h+var_38], rax; struct ldapcontrolW **
0x18003cc18  mov     rax, [rbp+ServerControls]
0x18003cc1c  mov     [rsp+78h+var_40], rax; struct ldapcontrolW **
0x18003cc21  mov     [rsp+78h+var_48], 0; unsigned __int8
0x18003cc26  mov     [rsp+78h+var_50], 0; unsigned __int8
0x18003cc2b  mov     [rsp+78h+var_58], rdi; struct berval *
0x18003cc30  mov     rdi, [rbp+var_28]
0x18003cc34  mov     r8, rdi; unsigned __int16 *
0x18003cc37  call    ?LdapCompare@@YAKPEAUldap_connection@@PEAG11PEAUberval@@EEPEAPEAUldapcontrolW@@3PEAK@Z; LdapCompare(ldap_connection *,ushort *,ushort *,ushort *,berval *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18003cc3c  mov     esi, eax
0x18003cc3e  jmp     short loc_18003CC52
0x18003cc40  mov     edx, 59h ; 'Y'
0x18003cc45  mov     rcx, rbx
0x18003cc48  call    SetConnectionError
0x18003cc4d  mov     esi, 59h ; 'Y'
0x18003cc52  mov     rcx, [rbp+var_18]
0x18003cc56  test    rcx, rcx
0x18003cc59  jz      short loc_18003CC65
0x18003cc5b  mov     edx, 696E554Ch
0x18003cc60  call    ldapFree
0x18003cc65  test    r14, r14
0x18003cc68  jz      short loc_18003CC77
0x18003cc6a  mov     edx, 696E554Ch
0x18003cc6f  mov     rcx, r14
0x18003cc72  call    ldapFree
0x18003cc77  test    rdi, rdi
0x18003cc7a  jz      short loc_18003CC89
0x18003cc7c  mov     edx, 696E554Ch
0x18003cc81  mov     rcx, rdi
0x18003cc84  call    ldapFree
0x18003cc89  test    rbx, rbx
0x18003cc8c  jz      short loc_18003CD06
0x18003cc8e  lea     rdi, [rbx+200h]
0x18003cc95  mov     rcx, rdi; lpCriticalSection
0x18003cc98  call    cs:__imp_EnterCriticalSection
0x18003cc9f  nop     dword ptr [rax+rax+00h]
0x18003cca4  dec     dword ptr [rbx]
0x18003cca6  cmp     cs:g_fTracingOn, 0
0x18003ccad  jz      short loc_18003CCD7
0x18003ccaf  cmp     cs:g_fProviderEnabled, 0
0x18003ccb6  jz      short loc_18003CCD7
0x18003ccb8  mov     ecx, 4
0x18003ccbd  test    byte ptr cs:g_ulTraceFlags, cl
0x18003ccc3  jz      short loc_18003CCD7
0x18003ccc5  mov     r9d, [rbx]
0x18003ccc8  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18003cccf  mov     r8, rbx
0x18003ccd2  call    LDAPClientPrint
0x18003ccd7  cmp     dword ptr [rbx], 0
0x18003ccda  mov     rcx, rdi; lpCriticalSection
0x18003ccdd  jnz     short loc_18003CCFA
0x18003ccdf  call    cs:__imp_LeaveCriticalSection
0x18003cce6  nop     dword ptr [rax+rax+00h]
0x18003cceb  mov     edx, 1
0x18003ccf0  mov     rcx, rbx
0x18003ccf3  call    DereferenceLdapConnection2
0x18003ccf8  jmp     short loc_18003CD06
0x18003ccfa  call    cs:__imp_LeaveCriticalSection
0x18003cd01  nop     dword ptr [rax+rax+00h]
0x18003cd06  mov     eax, esi
0x18003cd08  add     rsp, 78h
0x18003cd0c  pop     r15
0x18003cd0e  pop     r14
0x18003cd10  pop     r13
0x18003cd12  pop     r12
0x18003cd14  pop     rdi
0x18003cd15  pop     rsi
0x18003cd16  pop     rbx
0x18003cd17  pop     rbp
0x18003cd18  retn
```
