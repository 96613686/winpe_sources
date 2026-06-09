# ldap_modrdn2_s

- ea: `0x180047930`
- end: `0x180047a6e`
- name: `ldap_modrdn2_s`
- size: `318`
- prototype: `ULONG __cdecl(LDAP *ExternalHandle, const PSTR DistinguishedName, const PSTR NewDistinguishedName, INT DeleteOldRdn)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180047bf0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000bf40`
- `0x18000cda0`
- `0x18001611c`
- `0x180016360`
- `0x1800475f0`
- `0x180047930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800479f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800479f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a56`

## pseudocode

```c
ULONG __cdecl ldap_modrdn2_s(
        LDAP *ExternalHandle,
        const PSTR DistinguishedName,
        const PSTR NewDistinguishedName,
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
    v11 = ldap_modrdn2(*(LDAP **)(ConnectionPointer + 448), DistinguishedName, NewDistinguishedName, DeleteOldRdn);
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
0x180047930  push    rbx; ldap_modrdn2_s
0x180047932  push    rbp
0x180047933  push    rsi
0x180047934  push    rdi
0x180047935  sub     rsp, 48h
0x180047939  mov     edi, r9d
0x18004793c  mov     [rsp+68h+res], 0
0x180047945  mov     rsi, r8
0x180047948  mov     rbp, rdx
0x18004794b  call    GetConnectionPointer
0x180047950  mov     rbx, rax
0x180047953  test    rax, rax
0x180047956  jnz     short loc_18004796B
0x180047958  lea     ebx, [rax+59h]
0x18004795b  xor     ecx, ecx
0x18004795d  mov     edx, ebx
0x18004795f  call    SetConnectionError
0x180047964  mov     eax, ebx
0x180047966  jmp     loc_180047A64
0x18004796b  mov     rcx, [rax+1C0h]; ExternalHandle
0x180047972  mov     r9d, edi; DeleteOldRdn
0x180047975  mov     r8, rsi; NewDistinguishedName
0x180047978  mov     rdx, rbp; DistinguishedName
0x18004797b  call    ldap_modrdn2
0x180047980  mov     edi, eax
0x180047982  mov     ebp, 1
0x180047987  cmp     eax, 0FFFFFFFFh
0x18004798a  jz      short loc_1800479E7
0x18004798c  lea     rax, [rsp+68h+res]
0x180047991  mov     [rsp+68h+var_40], 0
0x18004799a  xor     r9d, r9d
0x18004799d  mov     [rsp+68h+var_48], rax
0x1800479a2  mov     r8d, ebp
0x1800479a5  mov     edx, edi
0x1800479a7  mov     rcx, rbx
0x1800479aa  call    ldap_result_with_error
0x1800479af  mov     rdx, [rsp+68h+res]; res
0x1800479b4  mov     esi, eax
0x1800479b6  test    rdx, rdx
0x1800479b9  jnz     short loc_1800479D4
0x1800479bb  mov     r8b, bpl
0x1800479be  mov     edx, edi
0x1800479c0  mov     rcx, rbx
0x1800479c3  call    LdapAbandon
0x1800479c8  mov     edx, esi
0x1800479ca  mov     rcx, rbx
0x1800479cd  call    SetConnectionError
0x1800479d2  jmp     short loc_1800479ED
0x1800479d4  mov     rcx, [rbx+1C0h]; ld
0x1800479db  mov     r8d, ebp; freeit
0x1800479de  call    ldap_result2error
0x1800479e3  mov     esi, eax
0x1800479e5  jmp     short loc_1800479ED
0x1800479e7  mov     esi, [rbx+3FCh]
0x1800479ed  lea     rdi, [rbx+200h]
0x1800479f4  mov     rcx, rdi; lpCriticalSection
0x1800479f7  call    cs:__imp_EnterCriticalSection
0x1800479fe  nop     dword ptr [rax+rax+00h]
0x180047a03  dec     dword ptr [rbx]
0x180047a05  cmp     cs:g_fTracingOn, 0
0x180047a0c  jz      short loc_180047A36
0x180047a0e  cmp     cs:g_fProviderEnabled, 0
0x180047a15  jz      short loc_180047A36
0x180047a17  mov     ecx, 4
0x180047a1c  test    byte ptr cs:g_ulTraceFlags, cl
0x180047a22  jz      short loc_180047A36
0x180047a24  mov     r9d, [rbx]
0x180047a27  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180047a2e  mov     r8, rbx
0x180047a31  call    LDAPClientPrint
0x180047a36  cmp     dword ptr [rbx], 0
0x180047a39  mov     rcx, rdi; lpCriticalSection
0x180047a3c  jnz     short loc_180047A56
0x180047a3e  call    cs:__imp_LeaveCriticalSection
0x180047a45  nop     dword ptr [rax+rax+00h]
0x180047a4a  mov     edx, ebp
0x180047a4c  mov     rcx, rbx
0x180047a4f  call    DereferenceLdapConnection2
0x180047a54  jmp     short loc_180047A62
0x180047a56  call    cs:__imp_LeaveCriticalSection
0x180047a5d  nop     dword ptr [rax+rax+00h]
0x180047a62  mov     eax, esi
0x180047a64  add     rsp, 48h
0x180047a68  pop     rdi
0x180047a69  pop     rsi
0x180047a6a  pop     rbp
0x180047a6b  pop     rbx
0x180047a6c  retn
```
