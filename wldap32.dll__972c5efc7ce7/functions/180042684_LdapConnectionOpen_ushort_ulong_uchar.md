# LdapConnectionOpen(ushort *,ulong,uchar)

- ea: `0x180042684`
- end: `0x180042945`
- name: `?LdapConnectionOpen@@YAPEAUldap@@PEAGKE@Z`
- size: `705`
- prototype: `struct ldap *__fastcall(unsigned __int16 *Src, unsigned int, unsigned __int8)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x18002b800`
- `0x180043e20`
- `0x180043e40`
- `0x180043eb0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x180015bd8`
- `0x1800230a0`
- `0x1800236f0`
- `0x180026b50`
- `0x180028da0`
- `0x180042684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042795`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042864`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800428be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042795`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042864`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800428be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800427dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800427f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004289a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042906`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042921`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800427dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800427f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004289a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042906`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042921`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042816`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042751`

## string_xrefs

- `0x1800426c9`: `ldap_open called with HostName '%S' PortNumber %lu.\n`
- `0x180042700`: `cldap_open called with HostName '%S' PortNumber %lu.\n`
- `0x180042760`: `ldap_open failed to create connection, error = 0x%x.\n`
- `0x180042845`: `ldap_open failed to open connection, error = 0x%x.\n`

## pseudocode

```c
struct ldap *__fastcall LdapConnectionOpen(unsigned __int16 *Src, int a2, char a3)
{
  int v3; // r9d
  int v7; // eax
  struct ldap_connection *Connection; // rax
  struct ldap_connection *v9; // rbx
  __int64 LastError; // r8
  ULONG v11; // edi
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  DWORD v13; // eax
  _QWORD *v15; // rax
  struct _RTL_CRITICAL_SECTION *v16; // rcx

  v3 = g_fTracingOn;
  if ( g_fTracingOn )
  {
    v7 = g_fProviderEnabled;
    if ( g_fProviderEnabled && (g_ulTraceFlags & 0x100) != 0 && !a3 )
    {
      LDAPClientPrint(256, "ldap_open called with HostName '%S' PortNumber %lu.\n", Src, a2);
      v3 = g_fTracingOn;
      v7 = g_fProviderEnabled;
    }
    if ( v3 && v7 && (g_ulTraceFlags & 0x20000) != 0 && a3 )
      LDAPClientPrint(0x20000, "cldap_open called with HostName '%S' PortNumber %lu.\n", Src, a2);
  }
  Connection = (struct ldap_connection *)LdapAllocateConnection(Src, a2, 0, a3);
  v9 = Connection;
  if ( !Connection )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
    {
      LastError = GetLastError();
      LDAPClientPrint(0x2000000, "ldap_open failed to create connection, error = 0x%x.\n", LastError);
    }
    return 0;
  }
  v11 = LdapConnect(Connection, 0, 0);
  if ( v11 )
  {
    CloseLdapConnection(v9);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 512));
    --*(_DWORD *)v9;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v9, *(_DWORD *)v9);
    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)v9 + 512);
    if ( *(_DWORD *)v9 )
    {
      LeaveCriticalSection(v12);
    }
    else
    {
      LeaveCriticalSection(v12);
      DereferenceLdapConnection2((__int64)v9, 1);
    }
    SetConnectionError(0, v11);
    v13 = LdapMapErrorToWin32(v11);
    SetLastError(v13);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
      LDAPClientPrint(0x2000000, "ldap_open failed to open connection, error = 0x%x.\n", v11);
    return 0;
  }
  ++*((_DWORD *)v9 + 17);
  EnterCriticalSection(&ConnectionListLock);
  v15 = (_QWORD *)qword_180065830;
  *((_QWORD *)v9 + 2) = qword_180065830;
  *((_QWORD *)v9 + 1) = &GlobalListActiveConnections;
  *v15 = (char *)v9 + 8;
  qword_180065830 = (__int64)v9 + 8;
  LeaveCriticalSection(&ConnectionListLock);
  if ( !GlobalParallelRecvMode )
    LdapWakeupSelect();
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 512));
  --*(_DWORD *)v9;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v9, *(_DWORD *)v9);
  v16 = (struct _RTL_CRITICAL_SECTION *)((char *)v9 + 512);
  if ( *(_DWORD *)v9 )
  {
    LeaveCriticalSection(v16);
  }
  else
  {
    LeaveCriticalSection(v16);
    DereferenceLdapConnection2((__int64)v9, 1);
  }
  return (struct ldap *)*((_QWORD *)v9 + 56);
}

```

## disassembly

```asm
0x180042684  mov     [rsp+arg_0], rbx
0x180042689  mov     [rsp+arg_8], rsi
0x18004268e  push    rdi
0x18004268f  sub     rsp, 20h
0x180042693  mov     r9d, cs:g_fTracingOn
0x18004269a  mov     bl, r8b
0x18004269d  mov     edi, edx
0x18004269f  mov     rsi, rcx
0x1800426a2  test    r9d, r9d
0x1800426a5  jz      short loc_18004270F
0x1800426a7  mov     eax, cs:g_fProviderEnabled
0x1800426ad  test    eax, eax
0x1800426af  jz      short loc_1800426E2
0x1800426b1  mov     ecx, 100h
0x1800426b6  test    cs:g_ulTraceFlags, rcx
0x1800426bd  jz      short loc_1800426E2
0x1800426bf  test    bl, bl
0x1800426c1  jnz     short loc_1800426E2
0x1800426c3  mov     r9d, edx
0x1800426c6  mov     r8, rsi
0x1800426c9  lea     rdx, aLdapOpenCalled; "ldap_open called with HostName '%S' Por"...
0x1800426d0  call    LDAPClientPrint
0x1800426d5  mov     r9d, cs:g_fTracingOn
0x1800426dc  mov     eax, cs:g_fProviderEnabled
0x1800426e2  test    r9d, r9d
0x1800426e5  jz      short loc_18004270F
0x1800426e7  test    eax, eax
0x1800426e9  jz      short loc_18004270F
0x1800426eb  mov     ecx, 20000h
0x1800426f0  test    cs:g_ulTraceFlags, rcx
0x1800426f7  jz      short loc_18004270F
0x1800426f9  test    bl, bl
0x1800426fb  jz      short loc_18004270F
0x1800426fd  mov     r9d, edi
0x180042700  lea     rdx, aCldapOpenCalle; "cldap_open called with HostName '%S' Po"...
0x180042707  mov     r8, rsi
0x18004270a  call    LDAPClientPrint
0x18004270f  mov     r9b, bl
0x180042712  xor     r8d, r8d
0x180042715  mov     edx, edi
0x180042717  mov     rcx, rsi; Src
0x18004271a  call    LdapAllocateConnection
0x18004271f  mov     rbx, rax
0x180042722  test    rax, rax
0x180042725  jnz     short loc_18004276C
0x180042727  cmp     cs:g_fTracingOn, eax
0x18004272d  jz      loc_180042853
0x180042733  cmp     cs:g_fProviderEnabled, eax
0x180042739  jz      loc_180042853
0x18004273f  mov     ebx, 2000000h
0x180042744  test    cs:g_ulTraceFlags, rbx
0x18004274b  jz      loc_180042853
0x180042751  call    cs:__imp_GetLastError
0x180042758  nop     dword ptr [rax+rax+00h]
0x18004275d  mov     r8d, eax
0x180042760  lea     rdx, aLdapOpenFailed_0; "ldap_open failed to create connection, "...
0x180042767  jmp     loc_18004284C
0x18004276c  xor     r8d, r8d
0x18004276f  xor     edx, edx
0x180042771  mov     rcx, rbx
0x180042774  call    LdapConnect
0x180042779  mov     edi, eax
0x18004277b  test    eax, eax
0x18004277d  jz      loc_18004285A
0x180042783  mov     rcx, rbx; struct ldap_connection *
0x180042786  call    CloseLdapConnection
0x18004278b  lea     rsi, [rbx+200h]
0x180042792  mov     rcx, rsi; lpCriticalSection
0x180042795  call    cs:__imp_EnterCriticalSection
0x18004279c  nop     dword ptr [rax+rax+00h]
0x1800427a1  dec     dword ptr [rbx]
0x1800427a3  cmp     cs:g_fTracingOn, 0
0x1800427aa  jz      short loc_1800427D5
0x1800427ac  cmp     cs:g_fProviderEnabled, 0
0x1800427b3  jz      short loc_1800427D5
0x1800427b5  test    byte ptr cs:g_ulTraceFlags, 4
0x1800427bc  jz      short loc_1800427D5
0x1800427be  mov     r9d, [rbx]
0x1800427c1  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x1800427c8  mov     r8, rbx
0x1800427cb  mov     ecx, 4
0x1800427d0  call    LDAPClientPrint
0x1800427d5  cmp     dword ptr [rbx], 0
0x1800427d8  mov     rcx, rsi; lpCriticalSection
0x1800427db  jnz     short loc_1800427F8
0x1800427dd  call    cs:__imp_LeaveCriticalSection
0x1800427e4  nop     dword ptr [rax+rax+00h]
0x1800427e9  mov     edx, 1
0x1800427ee  mov     rcx, rbx
0x1800427f1  call    DereferenceLdapConnection2
0x1800427f6  jmp     short loc_180042804
0x1800427f8  call    cs:__imp_LeaveCriticalSection
0x1800427ff  nop     dword ptr [rax+rax+00h]
0x180042804  mov     edx, edi
0x180042806  xor     ecx, ecx
0x180042808  call    SetConnectionError
0x18004280d  mov     ecx, edi; LdapError
0x18004280f  call    LdapMapErrorToWin32
0x180042814  mov     ecx, eax; dwErrCode
0x180042816  call    cs:__imp_SetLastError
0x18004281d  nop     dword ptr [rax+rax+00h]
0x180042822  cmp     cs:g_fTracingOn, 0
0x180042829  jz      short loc_180042853
0x18004282b  cmp     cs:g_fProviderEnabled, 0
0x180042832  jz      short loc_180042853
0x180042834  mov     ebx, 2000000h
0x180042839  test    cs:g_ulTraceFlags, rbx
0x180042840  jz      short loc_180042853
0x180042842  mov     r8d, edi
0x180042845  lea     rdx, aLdapOpenFailed; "ldap_open failed to open connection, er"...
0x18004284c  mov     ecx, ebx
0x18004284e  call    LDAPClientPrint
0x180042853  xor     eax, eax
0x180042855  jmp     loc_180042934
0x18004285a  inc     dword ptr [rbx+44h]
0x18004285d  lea     rcx, ConnectionListLock; lpCriticalSection
0x180042864  call    cs:__imp_EnterCriticalSection
0x18004286b  nop     dword ptr [rax+rax+00h]
0x180042870  mov     rax, cs:qword_180065830
0x180042877  lea     rdx, [rbx+8]
0x18004287b  mov     [rbx+10h], rax
0x18004287f  lea     r8, GlobalListActiveConnections
0x180042886  mov     [rdx], r8
0x180042889  lea     rcx, ConnectionListLock; lpCriticalSection
0x180042890  mov     [rax], rdx
0x180042893  mov     cs:qword_180065830, rdx
0x18004289a  call    cs:__imp_LeaveCriticalSection
0x1800428a1  nop     dword ptr [rax+rax+00h]
0x1800428a6  cmp     cs:GlobalParallelRecvMode, 0
0x1800428ad  jnz     short loc_1800428B4
0x1800428af  call    LdapWakeupSelect
0x1800428b4  lea     rdi, [rbx+200h]
0x1800428bb  mov     rcx, rdi; lpCriticalSection
0x1800428be  call    cs:__imp_EnterCriticalSection
0x1800428c5  nop     dword ptr [rax+rax+00h]
0x1800428ca  dec     dword ptr [rbx]
0x1800428cc  cmp     cs:g_fTracingOn, 0
0x1800428d3  jz      short loc_1800428FE
0x1800428d5  cmp     cs:g_fProviderEnabled, 0
0x1800428dc  jz      short loc_1800428FE
0x1800428de  test    byte ptr cs:g_ulTraceFlags, 4
0x1800428e5  jz      short loc_1800428FE
0x1800428e7  mov     r9d, [rbx]
0x1800428ea  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x1800428f1  mov     r8, rbx
0x1800428f4  mov     ecx, 4
0x1800428f9  call    LDAPClientPrint
0x1800428fe  cmp     dword ptr [rbx], 0
0x180042901  mov     rcx, rdi; lpCriticalSection
0x180042904  jnz     short loc_180042921
0x180042906  call    cs:__imp_LeaveCriticalSection
0x18004290d  nop     dword ptr [rax+rax+00h]
0x180042912  mov     edx, 1
0x180042917  mov     rcx, rbx
0x18004291a  call    DereferenceLdapConnection2
0x18004291f  jmp     short loc_18004292D
0x180042921  call    cs:__imp_LeaveCriticalSection
0x180042928  nop     dword ptr [rax+rax+00h]
0x18004292d  mov     rax, [rbx+1C0h]
0x180042934  mov     rbx, [rsp+28h+arg_0]
0x180042939  mov     rsi, [rsp+28h+arg_8]
0x18004293e  add     rsp, 20h
0x180042942  pop     rdi
0x180042943  retn
```
