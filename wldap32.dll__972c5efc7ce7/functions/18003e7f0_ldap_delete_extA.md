# ldap_delete_extA

- ea: `0x18003e7f0`
- end: `0x18003e93b`
- name: `ldap_delete_extA`
- size: `331`
- prototype: `ULONG __cdecl(LDAP *ld, const PSTR dn, PLDAPControlA *ServerControls, PLDAPControlA *ClientControls, ULONG *MessageNumber)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003e770`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000b440`
- `0x18000cda0`
- `0x18001ffa0`
- `0x18003e250`
- `0x18003e7f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e8bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e8bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e904`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e91f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e904`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e91f`

## pseudocode

```c
ULONG __cdecl ldap_delete_extA(
        LDAP *ld,
        const PSTR dn,
        PLDAPControlA *ServerControls,
        PLDAPControlA *ClientControls,
        ULONG *MessageNumber)
{
  __int64 ConnectionPointer; // rax
  __int64 v9; // r8
  _DWORD *v10; // rbx
  ULONG v11; // esi
  __int64 v12; // r8
  struct _RTL_CRITICAL_SECTION *v13; // rcx

  ConnectionPointer = GetConnectionPointer(ld, dn, ServerControls);
  v10 = (_DWORD *)ConnectionPointer;
  if ( ConnectionPointer && MessageNumber )
  {
    *MessageNumber = -1;
    v11 = ToUnicodeWithAlloc(dn, 1);
    if ( v11 )
      SetConnectionError((__int64)v10, 0x59u, v12);
    else
      v11 = LdapDelete(
              (struct ldap_connection *)v10,
              0,
              0,
              0,
              (struct ldapcontrolW **)ServerControls,
              (struct ldapcontrolW **)ClientControls,
              MessageNumber);
  }
  else
  {
    SetConnectionError(ConnectionPointer, 0x59u, v9);
    v11 = 89;
  }
  if ( v10 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 128));
    --*v10;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v10, *v10);
    v13 = (struct _RTL_CRITICAL_SECTION *)(v10 + 128);
    if ( *v10 )
    {
      LeaveCriticalSection(v13);
    }
    else
    {
      LeaveCriticalSection(v13);
      DereferenceLdapConnection2((__int64)v10, 1);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18003e7f0  push    rbx; ldap_delete_ext
0x18003e7f2  push    rbp
0x18003e7f3  push    rsi
0x18003e7f4  push    rdi
0x18003e7f5  push    r14
0x18003e7f7  push    r15
0x18003e7f9  sub     rsp, 58h
0x18003e7fd  xor     edi, edi
0x18003e7ff  mov     rbp, r9
0x18003e802  mov     [rsp+88h+var_48], rdi
0x18003e807  mov     r15, r8
0x18003e80a  mov     rsi, rdx
0x18003e80d  call    GetConnectionPointer
0x18003e812  mov     rbx, rax
0x18003e815  test    rax, rax
0x18003e818  jz      short loc_18003E88A
0x18003e81a  mov     r14, [rsp+88h+MessageNumber]
0x18003e822  test    r14, r14
0x18003e825  jz      short loc_18003E88A
0x18003e827  mov     r9d, 696E554Ch
0x18003e82d  mov     dword ptr [r14], 0FFFFFFFFh
0x18003e834  lea     r8, [rsp+88h+var_48]
0x18003e839  mov     dword ptr [rsp+88h+var_68], 1; int
0x18003e841  or      edx, 0FFFFFFFFh
0x18003e844  mov     rcx, rsi; lpMultiByteStr
0x18003e847  call    ToUnicodeWithAlloc
0x18003e84c  mov     esi, eax
0x18003e84e  mov     rcx, rbx; struct ldap_connection *
0x18003e851  test    eax, eax
0x18003e853  jz      short loc_18003E864
0x18003e855  lea     edx, [rdi+59h]
0x18003e858  call    SetConnectionError
0x18003e85d  mov     rdi, [rsp+88h+var_48]
0x18003e862  jmp     short loc_18003E89C
0x18003e864  mov     rdi, [rsp+88h+var_48]
0x18003e869  xor     r9d, r9d; unsigned __int8
0x18003e86c  mov     [rsp+88h+var_58], r14; unsigned int *
0x18003e871  mov     rdx, rdi; unsigned __int16 *
0x18003e874  mov     [rsp+88h+var_60], rbp; struct ldapcontrolW **
0x18003e879  xor     r8d, r8d; unsigned __int8
0x18003e87c  mov     [rsp+88h+var_68], r15; struct ldapcontrolW **
0x18003e881  call    ?LdapDelete@@YAKPEAUldap_connection@@PEAGEEPEAPEAUldapcontrolW@@2PEAK@Z; LdapDelete(ldap_connection *,ushort *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18003e886  mov     esi, eax
0x18003e888  jmp     short loc_18003E89C
0x18003e88a  mov     edx, 59h ; 'Y'
0x18003e88f  mov     rcx, rbx
0x18003e892  call    SetConnectionError
0x18003e897  mov     esi, 59h ; 'Y'
0x18003e89c  test    rdi, rdi
0x18003e89f  jz      short loc_18003E8AE
0x18003e8a1  mov     edx, 696E554Ch
0x18003e8a6  mov     rcx, rdi
0x18003e8a9  call    ldapFree
0x18003e8ae  test    rbx, rbx
0x18003e8b1  jz      short loc_18003E92B
0x18003e8b3  lea     rdi, [rbx+200h]
0x18003e8ba  mov     rcx, rdi; lpCriticalSection
0x18003e8bd  call    cs:__imp_EnterCriticalSection
0x18003e8c4  nop     dword ptr [rax+rax+00h]
0x18003e8c9  dec     dword ptr [rbx]
0x18003e8cb  cmp     cs:g_fTracingOn, 0
0x18003e8d2  jz      short loc_18003E8FC
0x18003e8d4  cmp     cs:g_fProviderEnabled, 0
0x18003e8db  jz      short loc_18003E8FC
0x18003e8dd  mov     ecx, 4
0x18003e8e2  test    byte ptr cs:g_ulTraceFlags, cl
0x18003e8e8  jz      short loc_18003E8FC
0x18003e8ea  mov     r9d, [rbx]
0x18003e8ed  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18003e8f4  mov     r8, rbx
0x18003e8f7  call    LDAPClientPrint
0x18003e8fc  cmp     dword ptr [rbx], 0
0x18003e8ff  mov     rcx, rdi; lpCriticalSection
0x18003e902  jnz     short loc_18003E91F
0x18003e904  call    cs:__imp_LeaveCriticalSection
0x18003e90b  nop     dword ptr [rax+rax+00h]
0x18003e910  mov     edx, 1
0x18003e915  mov     rcx, rbx
0x18003e918  call    DereferenceLdapConnection2
0x18003e91d  jmp     short loc_18003E92B
0x18003e91f  call    cs:__imp_LeaveCriticalSection
0x18003e926  nop     dword ptr [rax+rax+00h]
0x18003e92b  mov     eax, esi
0x18003e92d  add     rsp, 58h
0x18003e931  pop     r15
0x18003e933  pop     r14
0x18003e935  pop     rdi
0x18003e936  pop     rsi
0x18003e937  pop     rbp
0x18003e938  pop     rbx
0x18003e939  retn
```
