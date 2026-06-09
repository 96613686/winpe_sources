# LdapInitSsl

- ea: `0x1800494d4`
- end: `0x18004961c`
- name: `LdapInitSsl`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180049bf0`

## callees

- `0x1800037a8`
- `0x180020910`
- `0x1800494d4`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800495ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800495ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049537`
- `SspiCli!InitSecurityInterfaceW` at `0x180049501`
- `SspiCli!InitSecurityInterfaceW` at `0x180049501`

## string_xrefs

- `0x180049543`: `LDAP client failed SSL InitSecurityInterface, error = 0x%x.\n`
- `0x1800495d1`: `Microsoft Unified Security Protocol Provider`
- `0x180049599`: `LDAP client failed SSL EnumSecurityPackages, error = 0x%x.\n`

## pseudocode

```c
char LdapInitSsl()
{
  PSecurityFunctionTableW inited; // rax
  DWORD LastError; // eax
  int v3; // eax
  __int64 v4; // rbx
  unsigned int i; // edi

  NumberSslPackagesInstalled = 0;
  SslPackagesInstalled = 0;
  if ( !SslFunctionTableW )
  {
    inited = InitSecurityInterfaceW();
    SslFunctionTableW = inited;
    if ( !inited )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      {
        LastError = GetLastError();
        LDAPClientPrint(0x10000000, "LDAP client failed SSL InitSecurityInterface, error = 0x%x.\n", LastError);
      }
      return 0;
    }
    v3 = ((__int64 (__fastcall *)(int *, __int64 *))inited->EnumerateSecurityPackagesW)(
           &NumberSslPackagesInstalled,
           &SslPackagesInstalled);
    if ( v3 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientPrint(0x10000000, "LDAP client failed SSL EnumSecurityPackages, error = 0x%x.\n", v3);
      LeaveCriticalSection(&LoadLibLock);
      return 0;
    }
    v4 = SslPackagesInstalled;
    for ( i = 0; i < NumberSslPackagesInstalled; ++i )
    {
      if ( (unsigned __int8)ldapWStringsIdentical(
                              *(PCNZWCH *)(v4 + 16),
                              -1,
                              L"Microsoft Unified Security Protocol Provider",
                              -1) )
        SspiPackageSslPct = v4;
      if ( *(_DWORD *)(v4 + 8) > SspiMaxTokenSize )
        SspiMaxTokenSize = *(_DWORD *)(v4 + 8);
      v4 += 32;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800494d4  mov     [rsp+arg_0], rbx
0x1800494d9  push    rdi
0x1800494da  sub     rsp, 20h
0x1800494de  cmp     cs:SslFunctionTableW, 0
0x1800494e6  mov     cs:NumberSslPackagesInstalled, 0
0x1800494f0  mov     cs:SslPackagesInstalled, 0
0x1800494fb  jnz     loc_18004960E
0x180049501  call    cs:__imp_InitSecurityInterfaceW
0x180049508  nop     dword ptr [rax+rax+00h]
0x18004950d  mov     cs:SslFunctionTableW, rax
0x180049514  test    rax, rax
0x180049517  jnz     short loc_18004955B
0x180049519  cmp     cs:g_fTracingOn, eax
0x18004951f  jz      short loc_180049554
0x180049521  cmp     cs:g_fProviderEnabled, eax
0x180049527  jz      short loc_180049554
0x180049529  mov     ebx, 10000000h
0x18004952e  test    cs:g_ulTraceFlags, rbx
0x180049535  jz      short loc_180049554
0x180049537  call    cs:__imp_GetLastError
0x18004953e  nop     dword ptr [rax+rax+00h]
0x180049543  lea     rdx, aLdapClientFail_7; "LDAP client failed SSL InitSecurityInte"...
0x18004954a  mov     ecx, ebx
0x18004954c  mov     r8d, eax
0x18004954f  call    LDAPClientPrint
0x180049554  xor     al, al
0x180049556  jmp     loc_180049610
0x18004955b  mov     rax, [rax+8]
0x18004955f  lea     rdx, SslPackagesInstalled
0x180049566  lea     rcx, NumberSslPackagesInstalled
0x18004956d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049572  test    eax, eax
0x180049574  jz      short loc_1800495BC
0x180049576  cmp     cs:g_fTracingOn, 0
0x18004957d  jz      short loc_1800495A7
0x18004957f  cmp     cs:g_fProviderEnabled, 0
0x180049586  jz      short loc_1800495A7
0x180049588  mov     ebx, 10000000h
0x18004958d  test    cs:g_ulTraceFlags, rbx
0x180049594  jz      short loc_1800495A7
0x180049596  mov     r8d, eax
0x180049599  lea     rdx, aLdapClientFail_3; "LDAP client failed SSL EnumSecurityPack"...
0x1800495a0  mov     ecx, ebx
0x1800495a2  call    LDAPClientPrint
0x1800495a7  lea     rcx, LoadLibLock; lpCriticalSection
0x1800495ae  call    cs:__imp_LeaveCriticalSection
0x1800495b5  nop     dword ptr [rax+rax+00h]
0x1800495ba  jmp     short loc_180049554
0x1800495bc  mov     rbx, cs:SslPackagesInstalled
0x1800495c3  xor     edi, edi
0x1800495c5  cmp     cs:NumberSslPackagesInstalled, edi
0x1800495cb  jbe     short loc_18004960E
0x1800495cd  mov     rcx, [rbx+10h]; lpString1
0x1800495d1  lea     r8, aMicrosoftUnifi; "Microsoft Unified Security Protocol Pro"...
0x1800495d8  or      r9d, 0FFFFFFFFh; cchCount2
0x1800495dc  or      edx, r9d; cchCount1
0x1800495df  call    ldapWStringsIdentical
0x1800495e4  test    al, al
0x1800495e6  jz      short loc_1800495EF
0x1800495e8  mov     cs:SspiPackageSslPct, rbx
0x1800495ef  mov     ecx, [rbx+8]
0x1800495f2  cmp     ecx, cs:SspiMaxTokenSize
0x1800495f8  jbe     short loc_180049600
0x1800495fa  mov     cs:SspiMaxTokenSize, ecx
0x180049600  add     rbx, 20h ; ' '
0x180049604  inc     edi
0x180049606  cmp     edi, cs:NumberSslPackagesInstalled
0x18004960c  jb      short loc_1800495CD
0x18004960e  mov     al, 1
0x180049610  mov     rbx, [rsp+28h+arg_0]
0x180049615  add     rsp, 20h
0x180049619  pop     rdi
0x18004961a  retn
```
