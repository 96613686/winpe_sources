# ldap_delete_ext_sA

- ea: `0x18003ea40`
- end: `0x18003ec24`
- name: `ldap_delete_ext_sA`
- size: `484`
- prototype: `ULONG __cdecl(LDAP *ld, const PSTR dn, PLDAPControlA *ServerControls, PLDAPControlA *ClientControls)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18003edc0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000b440`
- `0x18000bf40`
- `0x18000cda0`
- `0x18001611c`
- `0x180016360`
- `0x18001ffa0`
- `0x18003e250`
- `0x18003ea40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eb6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eb6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ebb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ebd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ebb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ebd0`

## string_xrefs

- `0x18003ec06`: `ldap_delete returned 0x%x for connection 0x%x; DN was %s.\n`

## pseudocode

```c
ULONG __cdecl ldap_delete_ext_sA(LDAP *ld, const PSTR dn, PLDAPControlA *ServerControls, PLDAPControlA *ClientControls)
{
  _DWORD *ConnectionPointer; // rbx
  ULONG v10; // eax
  ULONG v11; // edi
  _DWORD *v12; // rcx
  __int64 v13; // rdx
  ULONG v14; // eax
  unsigned int v15; // r14d
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  unsigned int v17; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int16 *v18; // [rsp+48h] [rbp-50h]
  LDAPMessage *res; // [rsp+50h] [rbp-48h] BYREF

  v18 = 0;
  v17 = 0;
  res = 0;
  ConnectionPointer = (_DWORD *)GetConnectionPointer(ld, dn, ServerControls);
  if ( !ConnectionPointer )
  {
    SetConnectionError(0, 89);
    return 89;
  }
  v10 = ToUnicodeWithAlloc(dn, 1);
  v11 = v10;
  v12 = ConnectionPointer;
  if ( v10 )
  {
    v13 = v10;
LABEL_5:
    SetConnectionError(v12, v13);
    goto LABEL_10;
  }
  v14 = LdapDelete(
          (struct ldap_connection *)ConnectionPointer,
          v18,
          0,
          1u,
          (struct ldapcontrolW **)ServerControls,
          (struct ldapcontrolW **)ClientControls,
          &v17);
  v15 = v17;
  v11 = v14;
  if ( v17 != -1 )
  {
    v11 = ldap_result_with_error((struct ldap_connection *)ConnectionPointer, v17, (__int64)&res, 0);
    if ( !res )
    {
      LdapAbandon((__int64)ConnectionPointer, v15, 1);
      v13 = v11;
      v12 = ConnectionPointer;
      goto LABEL_5;
    }
    v11 = ldap_result2error(ld, res, 1u);
  }
LABEL_10:
  EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 128));
  --*ConnectionPointer;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)ConnectionPointer, *ConnectionPointer);
  v16 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 128);
  if ( *ConnectionPointer )
  {
    LeaveCriticalSection(v16);
  }
  else
  {
    LeaveCriticalSection(v16);
    DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 2) != 0 )
    LDAPClientPrint(
      2,
      "ldap_delete returned 0x%x for connection 0x%x; DN was %s.\n",
      v11,
      (_DWORD)ConnectionPointer,
      dn);
  return v11;
}

```

## disassembly

```asm
0x18003ea40  push    rbx; ldap_delete_ext_s
0x18003ea42  push    rbp
0x18003ea43  push    rsi
0x18003ea44  push    rdi
0x18003ea45  push    r12
0x18003ea47  push    r14
0x18003ea49  push    r15
0x18003ea4b  sub     rsp, 60h
0x18003ea4f  mov     r14, r9
0x18003ea52  mov     [rsp+98h+var_50], 0
0x18003ea5b  mov     r15, r8
0x18003ea5e  mov     [rsp+98h+var_58], 0
0x18003ea66  mov     r12, rdx
0x18003ea69  mov     [rsp+98h+res], 0
0x18003ea72  mov     rbp, rcx
0x18003ea75  call    GetConnectionPointer
0x18003ea7a  mov     rbx, rax
0x18003ea7d  test    rax, rax
0x18003ea80  jnz     short loc_18003EA95
0x18003ea82  lea     ebx, [rax+59h]
0x18003ea85  xor     ecx, ecx
0x18003ea87  mov     edx, ebx
0x18003ea89  call    SetConnectionError
0x18003ea8e  mov     eax, ebx
0x18003ea90  jmp     loc_18003EC14
0x18003ea95  mov     r9d, 696E554Ch
0x18003ea9b  mov     dword ptr [rsp+98h+var_78], 1; int
0x18003eaa3  lea     r8, [rsp+98h+var_50]
0x18003eaa8  or      edx, 0FFFFFFFFh
0x18003eaab  mov     rcx, r12; lpMultiByteStr
0x18003eaae  call    ToUnicodeWithAlloc
0x18003eab3  mov     rsi, [rsp+98h+var_50]
0x18003eab8  mov     edi, eax
0x18003eaba  mov     rcx, rbx; struct ldap_connection *
0x18003eabd  test    eax, eax
0x18003eabf  jz      short loc_18003EACD
0x18003eac1  mov     edx, eax
0x18003eac3  call    SetConnectionError
0x18003eac8  jmp     loc_18003EB52
0x18003eacd  lea     rax, [rsp+98h+var_58]
0x18003ead2  mov     r9b, 1; unsigned __int8
0x18003ead5  mov     [rsp+98h+var_68], rax; unsigned int *
0x18003eada  xor     r8d, r8d; unsigned __int8
0x18003eadd  mov     [rsp+98h+var_70], r14; struct ldapcontrolW **
0x18003eae2  mov     rdx, rsi; unsigned __int16 *
0x18003eae5  mov     [rsp+98h+var_78], r15; struct ldapcontrolW **
0x18003eaea  call    ?LdapDelete@@YAKPEAUldap_connection@@PEAGEEPEAPEAUldapcontrolW@@2PEAK@Z; LdapDelete(ldap_connection *,ushort *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18003eaef  mov     r14d, [rsp+98h+var_58]
0x18003eaf4  mov     edi, eax
0x18003eaf6  cmp     r14d, 0FFFFFFFFh
0x18003eafa  jz      short loc_18003EB52
0x18003eafc  xor     r9d, r9d
0x18003eaff  mov     [rsp+98h+var_70], 0
0x18003eb08  lea     rax, [rsp+98h+res]
0x18003eb0d  mov     edx, r14d
0x18003eb10  mov     rcx, rbx
0x18003eb13  mov     [rsp+98h+var_78], rax
0x18003eb18  lea     r8d, [r9+1]
0x18003eb1c  call    ldap_result_with_error
0x18003eb21  mov     rdx, [rsp+98h+res]; res
0x18003eb26  mov     edi, eax
0x18003eb28  test    rdx, rdx
0x18003eb2b  jnz     short loc_18003EB42
0x18003eb2d  mov     r8b, 1
0x18003eb30  mov     edx, r14d
0x18003eb33  mov     rcx, rbx
0x18003eb36  call    LdapAbandon
0x18003eb3b  mov     edx, edi
0x18003eb3d  mov     rcx, rbx
0x18003eb40  jmp     short loc_18003EAC3
0x18003eb42  mov     r8d, 1; freeit
0x18003eb48  mov     rcx, rbp; ld
0x18003eb4b  call    ldap_result2error
0x18003eb50  mov     edi, eax
0x18003eb52  test    rsi, rsi
0x18003eb55  jz      short loc_18003EB64
0x18003eb57  mov     edx, 696E554Ch
0x18003eb5c  mov     rcx, rsi
0x18003eb5f  call    ldapFree
0x18003eb64  lea     rsi, [rbx+200h]
0x18003eb6b  mov     rcx, rsi; lpCriticalSection
0x18003eb6e  call    cs:__imp_EnterCriticalSection
0x18003eb75  nop     dword ptr [rax+rax+00h]
0x18003eb7a  dec     dword ptr [rbx]
0x18003eb7c  cmp     cs:g_fTracingOn, 0
0x18003eb83  jz      short loc_18003EBAD
0x18003eb85  cmp     cs:g_fProviderEnabled, 0
0x18003eb8c  jz      short loc_18003EBAD
0x18003eb8e  mov     ecx, 4
0x18003eb93  test    byte ptr cs:g_ulTraceFlags, cl
0x18003eb99  jz      short loc_18003EBAD
0x18003eb9b  mov     r9d, [rbx]
0x18003eb9e  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18003eba5  mov     r8, rbx
0x18003eba8  call    LDAPClientPrint
0x18003ebad  cmp     dword ptr [rbx], 0
0x18003ebb0  mov     rcx, rsi; lpCriticalSection
0x18003ebb3  jnz     short loc_18003EBD0
0x18003ebb5  call    cs:__imp_LeaveCriticalSection
0x18003ebbc  nop     dword ptr [rax+rax+00h]
0x18003ebc1  mov     edx, 1
0x18003ebc6  mov     rcx, rbx
0x18003ebc9  call    DereferenceLdapConnection2
0x18003ebce  jmp     short loc_18003EBDC
0x18003ebd0  call    cs:__imp_LeaveCriticalSection
0x18003ebd7  nop     dword ptr [rax+rax+00h]
0x18003ebdc  cmp     cs:g_fTracingOn, 0
0x18003ebe3  jz      short loc_18003EC12
0x18003ebe5  cmp     cs:g_fProviderEnabled, 0
0x18003ebec  jz      short loc_18003EC12
0x18003ebee  mov     ecx, 2
0x18003ebf3  test    byte ptr cs:g_ulTraceFlags, cl
0x18003ebf9  jz      short loc_18003EC12
0x18003ebfb  mov     r9, rbx
0x18003ebfe  mov     [rsp+98h+var_78], r12
0x18003ec03  mov     r8d, edi
0x18003ec06  lea     rdx, aLdapDeleteRetu; "ldap_delete returned 0x%x for connectio"...
0x18003ec0d  call    LDAPClientPrint
0x18003ec12  mov     eax, edi
0x18003ec14  add     rsp, 60h
0x18003ec18  pop     r15
0x18003ec1a  pop     r14
0x18003ec1c  pop     r12
0x18003ec1e  pop     rdi
0x18003ec1f  pop     rsi
0x18003ec20  pop     rbp
0x18003ec21  pop     rbx
0x18003ec22  retn
```
