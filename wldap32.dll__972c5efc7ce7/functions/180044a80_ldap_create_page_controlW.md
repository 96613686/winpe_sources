# ldap_create_page_controlW

- ea: `0x180044a80`
- end: `0x180044b51`
- name: `ldap_create_page_controlW`
- size: `209`
- prototype: `ULONG __cdecl(PLDAP ExternalHandle, ULONG PageSize, struct berval *Cookie, UCHAR IsCritical, PLDAPControlW *Control)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800037a8`
- `0x18000adb0`
- `0x18000cda0`
- `0x18001f96c`
- `0x180044a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044ad7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044ad7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044b1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044b39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044b1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044b39`

## pseudocode

```c
ULONG __cdecl ldap_create_page_controlW(
        PLDAP ExternalHandle,
        ULONG PageSize,
        struct berval *Cookie,
        UCHAR IsCritical,
        PLDAPControlW *Control)
{
  _DWORD *ConnectionPointer; // rbx
  ULONG PageControl; // esi
  struct _RTL_CRITICAL_SECTION *v11; // rcx

  ConnectionPointer = (_DWORD *)GetConnectionPointer(ExternalHandle, PageSize, Cookie);
  if ( !ConnectionPointer )
    return 89;
  PageControl = LdapCreatePageControl(
                  (struct ldap_connection *)ConnectionPointer,
                  PageSize,
                  Cookie,
                  IsCritical,
                  Control,
                  0);
  EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 128));
  --*ConnectionPointer;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)ConnectionPointer, *ConnectionPointer);
  v11 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 128);
  if ( *ConnectionPointer )
  {
    LeaveCriticalSection(v11);
  }
  else
  {
    LeaveCriticalSection(v11);
    DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
  }
  return PageControl;
}

```

## disassembly

```asm
0x180044a80  push    rbx
0x180044a82  push    rbp
0x180044a83  push    rsi
0x180044a84  push    rdi
0x180044a85  sub     rsp, 38h
0x180044a89  mov     dil, r9b
0x180044a8c  mov     rsi, r8
0x180044a8f  mov     ebp, edx
0x180044a91  call    GetConnectionPointer
0x180044a96  mov     rbx, rax
0x180044a99  test    rax, rax
0x180044a9c  jnz     short loc_180044AA6
0x180044a9e  lea     eax, [rbx+59h]
0x180044aa1  jmp     loc_180044B47
0x180044aa6  mov     rax, [rsp+58h+Control]
0x180044aae  mov     r9b, dil; unsigned __int8
0x180044ab1  mov     [rsp+58h+var_30], 0; unsigned int
0x180044ab9  mov     r8, rsi; struct berval *
0x180044abc  mov     edx, ebp; unsigned int
0x180044abe  mov     [rsp+58h+var_38], rax; struct ldapcontrolW **
0x180044ac3  mov     rcx, rbx; struct ldap_connection *
0x180044ac6  call    ?LdapCreatePageControl@@YAKPEAUldap_connection@@KPEAUberval@@EPEAPEAUldapcontrolW@@K@Z; LdapCreatePageControl(ldap_connection *,ulong,berval *,uchar,ldapcontrolW * *,ulong)
0x180044acb  lea     rdi, [rbx+200h]
0x180044ad2  mov     esi, eax
0x180044ad4  mov     rcx, rdi; lpCriticalSection
0x180044ad7  call    cs:__imp_EnterCriticalSection
0x180044ade  nop     dword ptr [rax+rax+00h]
0x180044ae3  dec     dword ptr [rbx]
0x180044ae5  cmp     cs:g_fTracingOn, 0
0x180044aec  jz      short loc_180044B16
0x180044aee  cmp     cs:g_fProviderEnabled, 0
0x180044af5  jz      short loc_180044B16
0x180044af7  mov     ecx, 4
0x180044afc  test    byte ptr cs:g_ulTraceFlags, cl
0x180044b02  jz      short loc_180044B16
0x180044b04  mov     r9d, [rbx]
0x180044b07  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180044b0e  mov     r8, rbx
0x180044b11  call    LDAPClientPrint
0x180044b16  cmp     dword ptr [rbx], 0
0x180044b19  mov     rcx, rdi; lpCriticalSection
0x180044b1c  jnz     short loc_180044B39
0x180044b1e  call    cs:__imp_LeaveCriticalSection
0x180044b25  nop     dword ptr [rax+rax+00h]
0x180044b2a  mov     edx, 1
0x180044b2f  mov     rcx, rbx
0x180044b32  call    DereferenceLdapConnection2
0x180044b37  jmp     short loc_180044B45
0x180044b39  call    cs:__imp_LeaveCriticalSection
0x180044b40  nop     dword ptr [rax+rax+00h]
0x180044b45  mov     eax, esi
0x180044b47  add     rsp, 38h
0x180044b4b  pop     rdi
0x180044b4c  pop     rsi
0x180044b4d  pop     rbp
0x180044b4e  pop     rbx
0x180044b4f  retn
```
