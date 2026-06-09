# ldap_modrdn2_sW

- ea: `0x180047a80`
- end: `0x180047bbe`
- name: `ldap_modrdn2_sW`
- size: `318`
- prototype: `ULONG __cdecl(LDAP *ExternalHandle, const PWSTR DistinguishedName, const PWSTR NewDistinguishedName, INT DeleteOldRdn)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180047c10`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000bf40`
- `0x18000cda0`
- `0x18001611c`
- `0x180016360`
- `0x180047770`
- `0x180047a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047b47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047b47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047ba6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047ba6`

## pseudocode

```c
ULONG __cdecl ldap_modrdn2_sW(
        LDAP *ExternalHandle,
        const PWSTR DistinguishedName,
        const PWSTR NewDistinguishedName,
        INT DeleteOldRdn)
{
  __int64 ConnectionPointer; // rax
  __int64 v8; // r8
  _DWORD *v9; // rbx
  ULONG v11; // edi
  unsigned int v12; // esi
  __int64 v13; // r8
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  LDAPMessage *res; // [rsp+30h] [rbp-38h] BYREF

  res = 0;
  ConnectionPointer = GetConnectionPointer(ExternalHandle, DistinguishedName, NewDistinguishedName);
  v9 = (_DWORD *)ConnectionPointer;
  if ( ConnectionPointer )
  {
    v11 = ldap_modrdn2W(*(LDAP **)(ConnectionPointer + 448), DistinguishedName, NewDistinguishedName, DeleteOldRdn);
    if ( v11 == -1 )
    {
      v12 = v9[255];
    }
    else
    {
      v12 = ldap_result_with_error((struct ldap_connection *)v9, v11, 1u, 0, &res, 0);
      if ( res )
      {
        v12 = ldap_result2error(*((LDAP **)v9 + 56), res, 1u);
      }
      else
      {
        LdapAbandon((__int64)v9, v11, 1);
        SetConnectionError((__int64)v9, v12, v13);
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 128));
    --*v9;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v9, *v9);
    v14 = (struct _RTL_CRITICAL_SECTION *)(v9 + 128);
    if ( *v9 )
    {
      LeaveCriticalSection(v14);
    }
    else
    {
      LeaveCriticalSection(v14);
      DereferenceLdapConnection2((__int64)v9, 1);
    }
    return v12;
  }
  else
  {
    SetConnectionError(0, 0x59u, v8);
    return 89;
  }
}

```

## disassembly

```asm
0x180047a80  push    rbx
0x180047a82  push    rbp
0x180047a83  push    rsi
0x180047a84  push    rdi
0x180047a85  sub     rsp, 48h
0x180047a89  mov     edi, r9d
0x180047a8c  mov     [rsp+68h+res], 0
0x180047a95  mov     rsi, r8
0x180047a98  mov     rbp, rdx
0x180047a9b  call    GetConnectionPointer
0x180047aa0  mov     rbx, rax
0x180047aa3  test    rax, rax
0x180047aa6  jnz     short loc_180047ABB
0x180047aa8  lea     ebx, [rax+59h]
0x180047aab  xor     ecx, ecx
0x180047aad  mov     edx, ebx
0x180047aaf  call    SetConnectionError
0x180047ab4  mov     eax, ebx
0x180047ab6  jmp     loc_180047BB4
0x180047abb  mov     rcx, [rax+1C0h]; ExternalHandle
0x180047ac2  mov     r9d, edi; DeleteOldRdn
0x180047ac5  mov     r8, rsi; NewDistinguishedName
0x180047ac8  mov     rdx, rbp; DistinguishedName
0x180047acb  call    ldap_modrdn2W
0x180047ad0  mov     edi, eax
0x180047ad2  mov     ebp, 1
0x180047ad7  cmp     eax, 0FFFFFFFFh
0x180047ada  jz      short loc_180047B37
0x180047adc  lea     rax, [rsp+68h+res]
0x180047ae1  mov     [rsp+68h+var_40], 0
0x180047aea  xor     r9d, r9d
0x180047aed  mov     [rsp+68h+var_48], rax
0x180047af2  mov     r8d, ebp
0x180047af5  mov     edx, edi
0x180047af7  mov     rcx, rbx
0x180047afa  call    ldap_result_with_error
0x180047aff  mov     rdx, [rsp+68h+res]; res
0x180047b04  mov     esi, eax
0x180047b06  test    rdx, rdx
0x180047b09  jnz     short loc_180047B24
0x180047b0b  mov     r8b, bpl
0x180047b0e  mov     edx, edi
0x180047b10  mov     rcx, rbx
0x180047b13  call    LdapAbandon
0x180047b18  mov     edx, esi
0x180047b1a  mov     rcx, rbx
0x180047b1d  call    SetConnectionError
0x180047b22  jmp     short loc_180047B3D
0x180047b24  mov     rcx, [rbx+1C0h]; ld
0x180047b2b  mov     r8d, ebp; freeit
0x180047b2e  call    ldap_result2error
0x180047b33  mov     esi, eax
0x180047b35  jmp     short loc_180047B3D
0x180047b37  mov     esi, [rbx+3FCh]
0x180047b3d  lea     rdi, [rbx+200h]
0x180047b44  mov     rcx, rdi; lpCriticalSection
0x180047b47  call    cs:__imp_EnterCriticalSection
0x180047b4e  nop     dword ptr [rax+rax+00h]
0x180047b53  dec     dword ptr [rbx]
0x180047b55  cmp     cs:g_fTracingOn, 0
0x180047b5c  jz      short loc_180047B86
0x180047b5e  cmp     cs:g_fProviderEnabled, 0
0x180047b65  jz      short loc_180047B86
0x180047b67  mov     ecx, 4
0x180047b6c  test    byte ptr cs:g_ulTraceFlags, cl
0x180047b72  jz      short loc_180047B86
0x180047b74  mov     r9d, [rbx]
0x180047b77  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180047b7e  mov     r8, rbx
0x180047b81  call    LDAPClientPrint
0x180047b86  cmp     dword ptr [rbx], 0
0x180047b89  mov     rcx, rdi; lpCriticalSection
0x180047b8c  jnz     short loc_180047BA6
0x180047b8e  call    cs:__imp_LeaveCriticalSection
0x180047b95  nop     dword ptr [rax+rax+00h]
0x180047b9a  mov     edx, ebp
0x180047b9c  mov     rcx, rbx
0x180047b9f  call    DereferenceLdapConnection2
0x180047ba4  jmp     short loc_180047BB2
0x180047ba6  call    cs:__imp_LeaveCriticalSection
0x180047bad  nop     dword ptr [rax+rax+00h]
0x180047bb2  mov     eax, esi
0x180047bb4  add     rsp, 48h
0x180047bb8  pop     rdi
0x180047bb9  pop     rsi
0x180047bba  pop     rbp
0x180047bbb  pop     rbx
0x180047bbc  retn
```
