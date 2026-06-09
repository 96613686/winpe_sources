# ldap_create_page_controlA

- ea: `0x180044990`
- end: `0x180044a6f`
- name: `ldap_create_page_controlA`
- size: `223`
- prototype: `ULONG __cdecl(PLDAP ExternalHandle, ULONG PageSize, struct berval *Cookie, UCHAR IsCritical, PLDAPControlA *Control)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800037a8`
- `0x18000adb0`
- `0x18000cda0`
- `0x18001f96c`
- `0x180044990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800449f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800449f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044a3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044a57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044a3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044a57`

## pseudocode

```c
ULONG __cdecl ldap_create_page_controlA(
        PLDAP ExternalHandle,
        ULONG PageSize,
        struct berval *Cookie,
        UCHAR IsCritical,
        PLDAPControlA *Control)
{
  _DWORD *ConnectionPointer; // rbx
  ULONG PageControl; // esi
  struct _RTL_CRITICAL_SECTION *v11; // rcx

  ConnectionPointer = (_DWORD *)GetConnectionPointer(ExternalHandle, PageSize, Cookie);
  if ( ConnectionPointer )
  {
    PageControl = LdapCreatePageControl(
                    (struct ldap_connection *)ConnectionPointer,
                    PageSize,
                    Cookie,
                    IsCritical,
                    (struct ldapcontrolW **)Control,
                    1u);
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
  else
  {
    if ( Control )
      *Control = 0;
    return 89;
  }
}

```

## disassembly

```asm
0x180044990  push    rbx; ldap_create_page_control
0x180044992  push    rbp
0x180044993  push    rsi
0x180044994  push    rdi
0x180044995  sub     rsp, 38h
0x180044999  mov     dil, r9b
0x18004499c  mov     rsi, r8
0x18004499f  mov     ebp, edx
0x1800449a1  call    GetConnectionPointer
0x1800449a6  mov     rbx, rax
0x1800449a9  test    rax, rax
0x1800449ac  mov     rax, [rsp+58h+Control]
0x1800449b4  jnz     short loc_1800449CC
0x1800449b6  test    rax, rax
0x1800449b9  jz      short loc_1800449C2
0x1800449bb  mov     qword ptr [rax], 0
0x1800449c2  mov     eax, 59h ; 'Y'
0x1800449c7  jmp     loc_180044A65
0x1800449cc  mov     [rsp+58h+var_30], 1; unsigned int
0x1800449d4  mov     r9b, dil; unsigned __int8
0x1800449d7  mov     r8, rsi; struct berval *
0x1800449da  mov     [rsp+58h+var_38], rax; struct ldapcontrolW **
0x1800449df  mov     edx, ebp; unsigned int
0x1800449e1  mov     rcx, rbx; struct ldap_connection *
0x1800449e4  call    ?LdapCreatePageControl@@YAKPEAUldap_connection@@KPEAUberval@@EPEAPEAUldapcontrolW@@K@Z; LdapCreatePageControl(ldap_connection *,ulong,berval *,uchar,ldapcontrolW * *,ulong)
0x1800449e9  lea     rdi, [rbx+200h]
0x1800449f0  mov     esi, eax
0x1800449f2  mov     rcx, rdi; lpCriticalSection
0x1800449f5  call    cs:__imp_EnterCriticalSection
0x1800449fc  nop     dword ptr [rax+rax+00h]
0x180044a01  dec     dword ptr [rbx]
0x180044a03  cmp     cs:g_fTracingOn, 0
0x180044a0a  jz      short loc_180044A34
0x180044a0c  cmp     cs:g_fProviderEnabled, 0
0x180044a13  jz      short loc_180044A34
0x180044a15  mov     ecx, 4
0x180044a1a  test    byte ptr cs:g_ulTraceFlags, cl
0x180044a20  jz      short loc_180044A34
0x180044a22  mov     r9d, [rbx]
0x180044a25  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180044a2c  mov     r8, rbx
0x180044a2f  call    LDAPClientPrint
0x180044a34  cmp     dword ptr [rbx], 0
0x180044a37  mov     rcx, rdi; lpCriticalSection
0x180044a3a  jnz     short loc_180044A57
0x180044a3c  call    cs:__imp_LeaveCriticalSection
0x180044a43  nop     dword ptr [rax+rax+00h]
0x180044a48  mov     edx, 1
0x180044a4d  mov     rcx, rbx
0x180044a50  call    DereferenceLdapConnection2
0x180044a55  jmp     short loc_180044A63
0x180044a57  call    cs:__imp_LeaveCriticalSection
0x180044a5e  nop     dword ptr [rax+rax+00h]
0x180044a63  mov     eax, esi
0x180044a65  add     rsp, 38h
0x180044a69  pop     rdi
0x180044a6a  pop     rsi
0x180044a6b  pop     rbp
0x180044a6c  pop     rbx
0x180044a6d  retn
```
