# LdapCreateSortControlWithAlloc(ldap *,ldapsortkeyW * *,uchar,ldapcontrolW * *,ulong)

- ea: `0x18004a5b4`
- end: `0x18004a6be`
- name: `?LdapCreateSortControlWithAlloc@@YAKPEAUldap@@PEAPEAUldapsortkeyW@@EPEAPEAUldapcontrolW@@K@Z`
- size: `266`
- prototype: `unsigned int __fastcall(struct ldap *, struct ldapsortkeyW **, unsigned __int8, struct ldapcontrolW **, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18004aba0`
- `0x18004abc0`

## callees

- `0x1800037a8`
- `0x18000adb0`
- `0x18000cda0`
- `0x18001ce90`
- `0x1800201e0`
- `0x18004a5b4`
- `0x18004a984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a642`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a642`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a689`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a6a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a689`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a6a4`

## pseudocode

```c
__int64 __fastcall LdapCreateSortControlWithAlloc(
        struct ldap *a1,
        struct ldapsortkeyW **a2,
        __int64 a3,
        struct ldapcontrolW **a4,
        unsigned int a5)
{
  int v6; // esi
  bool v7; // bp
  __int64 ConnectionPointer; // rax
  __int64 v9; // rbx
  struct ldapcontrolW *v10; // rdi
  int v11; // r9d
  unsigned int v12; // esi
  struct _RTL_CRITICAL_SECTION *v13; // rcx

  v6 = (int)a2;
  v7 = (_BYTE)a3 != 0;
  ConnectionPointer = GetConnectionPointer(a1, a2, a3);
  v9 = ConnectionPointer;
  if ( ConnectionPointer && a4 )
  {
    v10 = (struct ldapcontrolW *)ldapMalloc(32, 1953383244);
    if ( v10 )
    {
      LOBYTE(v11) = v7;
      v12 = LdapEncodeSortControl(v9, v6, (_DWORD)v10, v11, a5);
      if ( v12 )
      {
        ldap_control_freeW(v10);
        v10 = 0;
      }
      *a4 = v10;
    }
    else
    {
      *a4 = 0;
      v12 = 90;
    }
  }
  else
  {
    v12 = 89;
    if ( !ConnectionPointer )
      return v12;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 512));
  --*(_DWORD *)v9;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", v9, *(_DWORD *)v9);
  v13 = (struct _RTL_CRITICAL_SECTION *)(v9 + 512);
  if ( *(_DWORD *)v9 )
  {
    LeaveCriticalSection(v13);
  }
  else
  {
    LeaveCriticalSection(v13);
    DereferenceLdapConnection2(v9, 1);
  }
  return v12;
}

```

## disassembly

```asm
0x18004a5b4  push    rbx
0x18004a5b6  push    rbp
0x18004a5b7  push    rsi
0x18004a5b8  push    rdi
0x18004a5b9  push    r14
0x18004a5bb  sub     rsp, 30h
0x18004a5bf  test    r8b, r8b
0x18004a5c2  mov     r14, r9
0x18004a5c5  mov     rsi, rdx
0x18004a5c8  setnz   bpl
0x18004a5cc  call    GetConnectionPointer
0x18004a5d1  mov     rbx, rax
0x18004a5d4  test    rax, rax
0x18004a5d7  jz      short loc_18004A62E
0x18004a5d9  test    r14, r14
0x18004a5dc  jz      short loc_18004A62E
0x18004a5de  mov     edx, 746E434Ch
0x18004a5e3  mov     ecx, 20h ; ' '
0x18004a5e8  call    ldapMalloc
0x18004a5ed  mov     rdi, rax
0x18004a5f0  test    rax, rax
0x18004a5f3  jnz     short loc_18004A5FD
0x18004a5f5  mov     [r14], rax
0x18004a5f8  lea     esi, [rax+5Ah]
0x18004a5fb  jmp     short loc_18004A638
0x18004a5fd  mov     eax, [rsp+58h+arg_20]
0x18004a604  mov     r9b, bpl
0x18004a607  mov     r8, rdi
0x18004a60a  mov     [rsp+58h+var_38], eax
0x18004a60e  mov     rdx, rsi
0x18004a611  mov     rcx, rbx
0x18004a614  call    LdapEncodeSortControl
0x18004a619  mov     esi, eax
0x18004a61b  test    eax, eax
0x18004a61d  jz      short loc_18004A629
0x18004a61f  mov     rcx, rdi; Control
0x18004a622  call    ldap_control_freeW
0x18004a627  xor     edi, edi
0x18004a629  mov     [r14], rdi
0x18004a62c  jmp     short loc_18004A638
0x18004a62e  mov     esi, 59h ; 'Y'
0x18004a633  test    rbx, rbx
0x18004a636  jz      short loc_18004A6B0
0x18004a638  lea     rdi, [rbx+200h]
0x18004a63f  mov     rcx, rdi; lpCriticalSection
0x18004a642  call    cs:__imp_EnterCriticalSection
0x18004a649  nop     dword ptr [rax+rax+00h]
0x18004a64e  dec     dword ptr [rbx]
0x18004a650  cmp     cs:g_fTracingOn, 0
0x18004a657  jz      short loc_18004A681
0x18004a659  cmp     cs:g_fProviderEnabled, 0
0x18004a660  jz      short loc_18004A681
0x18004a662  mov     ecx, 4
0x18004a667  test    byte ptr cs:g_ulTraceFlags, cl
0x18004a66d  jz      short loc_18004A681
0x18004a66f  mov     r9d, [rbx]
0x18004a672  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18004a679  mov     r8, rbx
0x18004a67c  call    LDAPClientPrint
0x18004a681  cmp     dword ptr [rbx], 0
0x18004a684  mov     rcx, rdi; lpCriticalSection
0x18004a687  jnz     short loc_18004A6A4
0x18004a689  call    cs:__imp_LeaveCriticalSection
0x18004a690  nop     dword ptr [rax+rax+00h]
0x18004a695  mov     edx, 1
0x18004a69a  mov     rcx, rbx
0x18004a69d  call    DereferenceLdapConnection2
0x18004a6a2  jmp     short loc_18004A6B0
0x18004a6a4  call    cs:__imp_LeaveCriticalSection
0x18004a6ab  nop     dword ptr [rax+rax+00h]
0x18004a6b0  mov     eax, esi
0x18004a6b2  add     rsp, 30h
0x18004a6b6  pop     r14
0x18004a6b8  pop     rdi
0x18004a6b9  pop     rsi
0x18004a6ba  pop     rbp
0x18004a6bb  pop     rbx
0x18004a6bc  retn
```
