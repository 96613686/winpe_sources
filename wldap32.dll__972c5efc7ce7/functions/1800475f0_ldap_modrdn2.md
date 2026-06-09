# ldap_modrdn2

- ea: `0x1800475f0`
- end: `0x18004775b`
- name: `ldap_modrdn2`
- size: `363`
- prototype: `ULONG __cdecl(LDAP *ExternalHandle, const PSTR DistinguishedName, const PSTR NewDistinguishedName, INT DeleteOldRdn)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800475d0`
- `0x180047930`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000b440`
- `0x18000cda0`
- `0x18001ffa0`
- `0x1800475f0`
- `0x180047770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800476df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800476df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047726`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047741`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047726`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047741`

## pseudocode

```c
ULONG __cdecl ldap_modrdn2(
        LDAP *ExternalHandle,
        const PSTR DistinguishedName,
        const PSTR NewDistinguishedName,
        INT DeleteOldRdn)
{
  __int64 ConnectionPointer; // rbx
  unsigned int v9; // eax
  __int64 v10; // r8
  ULONG v11; // edi
  struct _RTL_CRITICAL_SECTION *v12; // rcx

  ConnectionPointer = GetConnectionPointer(ExternalHandle, DistinguishedName, NewDistinguishedName);
  if ( !ConnectionPointer )
    return -1;
  v9 = ToUnicodeWithAlloc(DistinguishedName, 1);
  if ( v9 || (v9 = ToUnicodeWithAlloc(NewDistinguishedName, 1)) != 0 )
  {
    SetConnectionError(ConnectionPointer, v9, v10);
    v11 = -1;
  }
  else
  {
    v11 = ldap_modrdn2W(*(LDAP **)(ConnectionPointer + 448), 0, 0, DeleteOldRdn);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 512));
  --*(_DWORD *)ConnectionPointer;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", ConnectionPointer, *(_DWORD *)ConnectionPointer);
  v12 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 512);
  if ( *(_DWORD *)ConnectionPointer )
  {
    LeaveCriticalSection(v12);
  }
  else
  {
    LeaveCriticalSection(v12);
    DereferenceLdapConnection2(ConnectionPointer, 1);
  }
  return v11;
}

```

## disassembly

```asm
0x1800475f0  push    rbx; ldap_modrdn2
0x1800475f2  push    rbp
0x1800475f3  push    rsi
0x1800475f4  push    rdi
0x1800475f5  push    r14
0x1800475f7  sub     rsp, 40h
0x1800475fb  xor     esi, esi
0x1800475fd  mov     [rsp+68h+DistinguishedName], 0
0x180047606  mov     [rsp+68h+NewDistinguishedName], rsi
0x18004760b  mov     r14d, r9d
0x18004760e  mov     rdi, r8
0x180047611  mov     rbp, rdx
0x180047614  call    GetConnectionPointer
0x180047619  mov     rbx, rax
0x18004761c  test    rax, rax
0x18004761f  jnz     short loc_180047629
0x180047621  or      eax, 0FFFFFFFFh
0x180047624  jmp     loc_18004774F
0x180047629  mov     r9d, 696E554Ch
0x18004762f  mov     [rsp+68h+var_48], 1; int
0x180047637  lea     r8, [rsp+68h+DistinguishedName]
0x18004763c  or      edx, 0FFFFFFFFh
0x18004763f  mov     rcx, rbp; lpMultiByteStr
0x180047642  call    ToUnicodeWithAlloc
0x180047647  mov     rbp, [rsp+68h+DistinguishedName]
0x18004764c  test    eax, eax
0x18004764e  jz      short loc_18004765F
0x180047650  mov     edx, eax
0x180047652  mov     rcx, rbx
0x180047655  call    SetConnectionError
0x18004765a  or      edi, 0FFFFFFFFh
0x18004765d  jmp     short loc_1800476B1
0x18004765f  mov     r9d, 696E554Ch
0x180047665  mov     [rsp+68h+var_48], 1; int
0x18004766d  lea     r8, [rsp+68h+NewDistinguishedName]
0x180047672  or      edx, 0FFFFFFFFh
0x180047675  mov     rcx, rdi; lpMultiByteStr
0x180047678  call    ToUnicodeWithAlloc
0x18004767d  test    eax, eax
0x18004767f  jz      short loc_180047695
0x180047681  mov     edx, eax
0x180047683  mov     rcx, rbx
0x180047686  call    SetConnectionError
0x18004768b  mov     rsi, [rsp+68h+NewDistinguishedName]
0x180047690  or      edi, 0FFFFFFFFh
0x180047693  jmp     short loc_1800476B1
0x180047695  mov     rsi, [rsp+68h+NewDistinguishedName]
0x18004769a  mov     r9d, r14d; DeleteOldRdn
0x18004769d  mov     rcx, [rbx+1C0h]; ExternalHandle
0x1800476a4  mov     r8, rsi; NewDistinguishedName
0x1800476a7  mov     rdx, rbp; DistinguishedName
0x1800476aa  call    ldap_modrdn2W
0x1800476af  mov     edi, eax
0x1800476b1  test    rbp, rbp
0x1800476b4  jz      short loc_1800476C3
0x1800476b6  mov     edx, 696E554Ch
0x1800476bb  mov     rcx, rbp
0x1800476be  call    ldapFree
0x1800476c3  test    rsi, rsi
0x1800476c6  jz      short loc_1800476D5
0x1800476c8  mov     edx, 696E554Ch
0x1800476cd  mov     rcx, rsi
0x1800476d0  call    ldapFree
0x1800476d5  lea     rsi, [rbx+200h]
0x1800476dc  mov     rcx, rsi; lpCriticalSection
0x1800476df  call    cs:__imp_EnterCriticalSection
0x1800476e6  nop     dword ptr [rax+rax+00h]
0x1800476eb  dec     dword ptr [rbx]
0x1800476ed  cmp     cs:g_fTracingOn, 0
0x1800476f4  jz      short loc_18004771E
0x1800476f6  cmp     cs:g_fProviderEnabled, 0
0x1800476fd  jz      short loc_18004771E
0x1800476ff  mov     ecx, 4
0x180047704  test    byte ptr cs:g_ulTraceFlags, cl
0x18004770a  jz      short loc_18004771E
0x18004770c  mov     r9d, [rbx]
0x18004770f  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180047716  mov     r8, rbx
0x180047719  call    LDAPClientPrint
0x18004771e  cmp     dword ptr [rbx], 0
0x180047721  mov     rcx, rsi; lpCriticalSection
0x180047724  jnz     short loc_180047741
0x180047726  call    cs:__imp_LeaveCriticalSection
0x18004772d  nop     dword ptr [rax+rax+00h]
0x180047732  mov     edx, 1
0x180047737  mov     rcx, rbx
0x18004773a  call    DereferenceLdapConnection2
0x18004773f  jmp     short loc_18004774D
0x180047741  call    cs:__imp_LeaveCriticalSection
0x180047748  nop     dword ptr [rax+rax+00h]
0x18004774d  mov     eax, edi
0x18004774f  add     rsp, 40h
0x180047753  pop     r14
0x180047755  pop     rdi
0x180047756  pop     rsi
0x180047757  pop     rbp
0x180047758  pop     rbx
0x180047759  retn
```
