# LdapInitializeWinsock

- ea: `0x18002e24c`
- end: `0x18002e6cb`
- name: `LdapInitializeWinsock`
- size: `1151`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180026b50`

## callees

- `0x1800037a8`
- `0x18002909c`
- `0x18002d67c`
- `0x18002e24c`
- `0x180032bd8`
- `0x180034510`
- `0x180034e6c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e668`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e668`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e2a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e2a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e682`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e6a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e682`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2fa`
- `WS2_32!__imp_bind` at `0x18002e4d8`
- `WS2_32!__imp_bind` at `0x18002e4d8`
- `WS2_32!__imp_connect` at `0x18002e5ba`
- `WS2_32!__imp_connect` at `0x18002e5ba`
- `WS2_32!__imp_getsockname` at `0x18002e539`
- `WS2_32!__imp_getsockname` at `0x18002e539`
- `WS2_32!__imp_ioctlsocket` at `0x18002e611`
- `WS2_32!__imp_ioctlsocket` at `0x18002e611`
- `WS2_32!__imp_socket` at `0x18002e41b`
- `WS2_32!__imp_socket` at `0x18002e448`
- `WS2_32!__imp_socket` at `0x18002e41b`
- `WS2_32!__imp_socket` at `0x18002e448`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e3bf`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e48e`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e512`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e573`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e5ec`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e63f`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e3bf`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e48e`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e512`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e573`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e5ec`
- `WS2_32!__imp_WSAGetLastError` at `0x18002e63f`
- `WS2_32!__imp_WSAStartup` at `0x18002e385`
- `WS2_32!__imp_WSAStartup` at `0x18002e385`

## string_xrefs

- `0x18002e49a`: `Failed to create socket in LdapClientInitialize: %d\n`

## pseudocode

```c
__int64 LdapInitializeWinsock()
{
  DWORD LastError; // eax
  int v1; // eax
  unsigned int Error; // eax
  SOCKET v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  int namelen; // [rsp+20h] [rbp-69h] BYREF
  u_long argp[3]; // [rsp+24h] [rbp-65h] BYREF
  struct sockaddr name[8]; // [rsp+30h] [rbp-59h] BYREF

  argp[0] = 1;
  memset_0(name, 0, sizeof(name));
  namelen = 128;
  if ( GlobalCloseWinsock )
    return 1;
  EnterCriticalSection(&LoadLibLock);
  if ( GlobalCloseWinsock )
  {
LABEL_62:
    LeaveCriticalSection(&LoadLibLock);
    return 1;
  }
  PinDynamicLibrary();
  WinsockLibraryHandle = LoadSystem32LibraryA();
  if ( WinsockLibraryHandle )
  {
    v1 = g_fTracingOn;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000000) != 0 )
    {
      LDAPClientTraceEvent(
        0x4000000,
        (__int64)"Using Strong Scrambling APIs (CryptProtectMemory/CryptUnprotectMemory)\n");
      v1 = g_fTracingOn;
    }
    GlobalScramblingBlockSize = 16;
    if ( v1 && g_fProviderEnabled && (g_ulTraceFlags & 0x4000000) != 0 )
      LDAPClientTraceEvent(0x4000000, (__int64)"LDAP Client initializing Winsock.\n");
    if ( WSAStartup(2u, &GlobalLdapWSAData) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      {
        Error = WSAGetLastError();
        LDAPClientPrint(0x10000000, "LDAP client failed to initialize Winsock, error = 0x%x.\n", Error);
      }
      goto LABEL_58;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000000) != 0 )
      LDAPClientTraceEvent(0x4000000, (__int64)"LDAP Client initialized winsock.\n");
    memset_0(name[0].sa_data, 0, 0x7Eu);
    name[0].sa_family = 2;
    LdapGlobalWakeupSelectHandle = socket(2, 2, 0);
    v3 = LdapGlobalWakeupSelectHandle;
    if ( LdapGlobalWakeupSelectHandle == -1 )
    {
      name[0].sa_family = 23;
      LdapGlobalWakeupSelectHandle = socket(23, 2, 0);
      v3 = LdapGlobalWakeupSelectHandle;
      if ( LdapGlobalWakeupSelectHandle == -1 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        {
          v4 = WSAGetLastError();
          LDAPClientPrint(0x10000000, "Failed to create socket in LdapClientInitialize: %d\n", v4);
        }
        goto LABEL_58;
      }
    }
    if ( name[0].sa_family == 2 )
    {
      *(IN_ADDR *)&name[0].sa_data[2] = in4addr_loopback;
    }
    else if ( name[0].sa_family == 23 )
    {
      *(IN6_ADDR *)&name[0].sa_data[6] = in6addr_loopback;
    }
    *(_WORD *)name[0].sa_data = 0;
    if ( bind(v3, name, 128) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      {
        v5 = WSAGetLastError();
        LDAPClientPrint(0x10000000, "Failed to bind socket in LdapClientInitialize: %d\n", v5);
      }
      goto LABEL_58;
    }
    if ( getsockname(LdapGlobalWakeupSelectHandle, name, &namelen) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      {
        v6 = WSAGetLastError();
        LDAPClientPrint(0x10000000, "Failed in getsockname in LdapClientInitialize: %d\n", v6);
      }
      goto LABEL_58;
    }
    if ( name[0].sa_family == 2 )
      *(IN_ADDR *)&name[0].sa_data[2] = in4addr_loopback;
    else
      *(IN6_ADDR *)&name[0].sa_data[6] = in6addr_loopback;
    if ( connect(LdapGlobalWakeupSelectHandle, name, 128) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      {
        v7 = WSAGetLastError();
        LDAPClientPrint(0x10000000, "Failed to connect socket to itself in LdapClientInitialize: %d\n", v7);
      }
      goto LABEL_58;
    }
    if ( ioctlsocket(LdapGlobalWakeupSelectHandle, -2147195266, argp) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      {
        v8 = WSAGetLastError();
        LDAPClientPrint(0x10000000, "Failed to set socket to nonblocking in LdapClientInitialize: %d\n", v8);
      }
      goto LABEL_58;
    }
    GlobalCloseWinsock = 1;
    goto LABEL_62;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
  {
    LastError = GetLastError();
    LDAPClientPrint(0x10000000, "LDAP client failed to load Winsock, error = 0x%x.\n", LastError);
  }
LABEL_58:
  if ( WinsockLibraryHandle )
  {
    FreeLibrary(WinsockLibraryHandle);
    WinsockLibraryHandle = 0;
  }
  LeaveCriticalSection(&LoadLibLock);
  return 0;
}

```

## disassembly

```asm
0x18002e24c  push    rbp
0x18002e24e  push    rbx
0x18002e24f  push    rdi
0x18002e250  push    r14
0x18002e252  lea     rbp, [rsp-3Fh]
0x18002e257  sub     rsp, 0C8h
0x18002e25e  mov     rax, cs:__security_cookie
0x18002e265  xor     rax, rsp
0x18002e268  mov     [rbp+57h+var_30], rax
0x18002e26c  xor     edx, edx; Val
0x18002e26e  mov     [rbp+57h+argp], 1
0x18002e275  mov     r8d, 80h; Size
0x18002e27b  lea     rcx, [rbp+57h+name]; void *
0x18002e27f  call    memset_0
0x18002e284  xor     edi, edi
0x18002e286  mov     [rbp+57h+namelen], 80h
0x18002e28d  cmp     cs:?GlobalCloseWinsock@@3EA, dil; uchar GlobalCloseWinsock
0x18002e294  jnz     loc_18002E6AC
0x18002e29a  lea     rcx, LoadLibLock; lpCriticalSection
0x18002e2a1  call    cs:__imp_EnterCriticalSection
0x18002e2a8  nop     dword ptr [rax+rax+00h]
0x18002e2ad  cmp     cs:?GlobalCloseWinsock@@3EA, dil; uchar GlobalCloseWinsock
0x18002e2b4  jnz     loc_18002E699
0x18002e2ba  call    ?PinDynamicLibrary@@YAXXZ; PinDynamicLibrary(void)
0x18002e2bf  call    LoadSystem32LibraryA
0x18002e2c4  mov     cs:?WinsockLibraryHandle@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * WinsockLibraryHandle
0x18002e2cb  test    rax, rax
0x18002e2ce  jnz     short loc_18002E312
0x18002e2d0  cmp     cs:g_fTracingOn, edi
0x18002e2d6  jz      loc_18002E65C
0x18002e2dc  cmp     cs:g_fProviderEnabled, edi
0x18002e2e2  jz      loc_18002E65C
0x18002e2e8  mov     ebx, 10000000h
0x18002e2ed  test    cs:g_ulTraceFlags, rbx
0x18002e2f4  jz      loc_18002E65C
0x18002e2fa  call    cs:__imp_GetLastError
0x18002e301  nop     dword ptr [rax+rax+00h]
0x18002e306  lea     rdx, aLdapClientFail; "LDAP client failed to load Winsock, err"...
0x18002e30d  jmp     loc_18002E652
0x18002e312  mov     eax, cs:g_fTracingOn
0x18002e318  mov     ebx, 4000000h
0x18002e31d  test    eax, eax
0x18002e31f  jz      short loc_18002E346
0x18002e321  cmp     cs:g_fProviderEnabled, edi
0x18002e327  jz      short loc_18002E346
0x18002e329  test    cs:g_ulTraceFlags, rbx
0x18002e330  jz      short loc_18002E346
0x18002e332  lea     rdx, aUsingStrongScr; "Using Strong Scrambling APIs (CryptProt"...
0x18002e339  mov     ecx, ebx
0x18002e33b  call    LDAPClientTraceEvent
0x18002e340  mov     eax, cs:g_fTracingOn
0x18002e346  mov     ecx, 10h
0x18002e34b  mov     cs:GlobalScramblingBlockSize, cx
0x18002e352  test    eax, eax
0x18002e354  jz      short loc_18002E375
0x18002e356  cmp     cs:g_fProviderEnabled, edi
0x18002e35c  jz      short loc_18002E375
0x18002e35e  test    cs:g_ulTraceFlags, rbx
0x18002e365  jz      short loc_18002E375
0x18002e367  lea     rdx, aLdapClientInit_0; "LDAP Client initializing Winsock.\n"
0x18002e36e  mov     ecx, ebx
0x18002e370  call    LDAPClientTraceEvent
0x18002e375  mov     r14d, 2
0x18002e37b  lea     rdx, ?GlobalLdapWSAData@@3UWSAData@@A; lpWSAData
0x18002e382  mov     ecx, r14d; wVersionRequested
0x18002e385  call    cs:__imp_WSAStartup
0x18002e38c  nop     dword ptr [rax+rax+00h]
0x18002e391  test    eax, eax
0x18002e393  jz      short loc_18002E3D7
0x18002e395  cmp     cs:g_fTracingOn, edi
0x18002e39b  jz      loc_18002E65C
0x18002e3a1  cmp     cs:g_fProviderEnabled, edi
0x18002e3a7  jz      loc_18002E65C
0x18002e3ad  mov     ebx, 10000000h
0x18002e3b2  test    cs:g_ulTraceFlags, rbx
0x18002e3b9  jz      loc_18002E65C
0x18002e3bf  call    cs:__imp_WSAGetLastError
0x18002e3c6  nop     dword ptr [rax+rax+00h]
0x18002e3cb  lea     rdx, aLdapClientFail_6; "LDAP client failed to initialize Winsoc"...
0x18002e3d2  jmp     loc_18002E652
0x18002e3d7  cmp     cs:g_fTracingOn, edi
0x18002e3dd  jz      short loc_18002E3FE
0x18002e3df  cmp     cs:g_fProviderEnabled, edi
0x18002e3e5  jz      short loc_18002E3FE
0x18002e3e7  test    cs:g_ulTraceFlags, rbx
0x18002e3ee  jz      short loc_18002E3FE
0x18002e3f0  lea     rdx, aLdapClientInit; "LDAP Client initialized winsock.\n"
0x18002e3f7  mov     ecx, ebx
0x18002e3f9  call    LDAPClientTraceEvent
0x18002e3fe  xor     edx, edx; Val
0x18002e400  lea     rcx, [rbp+57h+name+2]; void *
0x18002e404  lea     r8d, [rdx+7Eh]; Size
0x18002e408  call    memset_0
0x18002e40d  xor     r8d, r8d; protocol
0x18002e410  mov     word ptr [rbp+57h+name], r14w
0x18002e415  mov     edx, r14d; type
0x18002e418  mov     ecx, r14d; af
0x18002e41b  call    cs:__imp_socket
0x18002e422  nop     dword ptr [rax+rax+00h]
0x18002e427  mov     cs:LdapGlobalWakeupSelectHandle, rax
0x18002e42e  mov     rcx, rax; s
0x18002e431  mov     ebx, 17h
0x18002e436  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e43a  jnz     short loc_18002E4A6
0x18002e43c  xor     r8d, r8d; protocol
0x18002e43f  mov     word ptr [rbp+57h+name], bx
0x18002e443  mov     edx, r14d; type
0x18002e446  mov     ecx, ebx; af
0x18002e448  call    cs:__imp_socket
0x18002e44f  nop     dword ptr [rax+rax+00h]
0x18002e454  mov     cs:LdapGlobalWakeupSelectHandle, rax
0x18002e45b  mov     rcx, rax
0x18002e45e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e462  jnz     short loc_18002E4A6
0x18002e464  cmp     cs:g_fTracingOn, edi
0x18002e46a  jz      loc_18002E65C
0x18002e470  cmp     cs:g_fProviderEnabled, edi
0x18002e476  jz      loc_18002E65C
0x18002e47c  mov     ebx, 10000000h
0x18002e481  test    cs:g_ulTraceFlags, rbx
0x18002e488  jz      loc_18002E65C
0x18002e48e  call    cs:__imp_WSAGetLastError
0x18002e495  nop     dword ptr [rax+rax+00h]
0x18002e49a  lea     rdx, aFailedToCreate; "Failed to create socket in LdapClientIn"...
0x18002e4a1  jmp     loc_18002E652
0x18002e4a6  cmp     word ptr [rbp+57h+name], r14w
0x18002e4ab  jnz     short loc_18002E4B8
0x18002e4ad  mov     eax, dword ptr cs:in4addr_loopback.S_un
0x18002e4b3  mov     dword ptr [rbp+57h+name+4], eax
0x18002e4b6  jmp     short loc_18002E4CA
0x18002e4b8  cmp     word ptr [rbp+57h+name], bx
0x18002e4bc  jnz     short loc_18002E4CA
0x18002e4be  movups  xmm0, xmmword ptr cs:in6addr_loopback.u
0x18002e4c5  movdqu  xmmword ptr [rbp+57h+name+8], xmm0
0x18002e4ca  mov     r8d, 80h; namelen
0x18002e4d0  mov     word ptr [rbp+57h+name+2], di
0x18002e4d4  lea     rdx, [rbp+57h+name]; name
0x18002e4d8  call    cs:__imp_bind
0x18002e4df  nop     dword ptr [rax+rax+00h]
0x18002e4e4  test    eax, eax
0x18002e4e6  jz      short loc_18002E52A
0x18002e4e8  cmp     cs:g_fTracingOn, edi
0x18002e4ee  jz      loc_18002E65C
0x18002e4f4  cmp     cs:g_fProviderEnabled, edi
0x18002e4fa  jz      loc_18002E65C
0x18002e500  mov     ebx, 10000000h
0x18002e505  test    cs:g_ulTraceFlags, rbx
0x18002e50c  jz      loc_18002E65C
0x18002e512  call    cs:__imp_WSAGetLastError
0x18002e519  nop     dword ptr [rax+rax+00h]
0x18002e51e  lea     rdx, aFailedToBindSo; "Failed to bind socket in LdapClientInit"...
0x18002e525  jmp     loc_18002E652
0x18002e52a  mov     rcx, cs:LdapGlobalWakeupSelectHandle; s
0x18002e531  lea     r8, [rbp+57h+namelen]; namelen
0x18002e535  lea     rdx, [rbp+57h+name]; name
0x18002e539  call    cs:__imp_getsockname
0x18002e540  nop     dword ptr [rax+rax+00h]
0x18002e545  test    eax, eax
0x18002e547  jz      short loc_18002E58B
0x18002e549  cmp     cs:g_fTracingOn, edi
0x18002e54f  jz      loc_18002E65C
0x18002e555  cmp     cs:g_fProviderEnabled, edi
0x18002e55b  jz      loc_18002E65C
0x18002e561  mov     ebx, 10000000h
0x18002e566  test    cs:g_ulTraceFlags, rbx
0x18002e56d  jz      loc_18002E65C
0x18002e573  call    cs:__imp_WSAGetLastError
0x18002e57a  nop     dword ptr [rax+rax+00h]
0x18002e57f  lea     rdx, aFailedInGetsoc; "Failed in getsockname in LdapClientInit"...
0x18002e586  jmp     loc_18002E652
0x18002e58b  cmp     word ptr [rbp+57h+name], r14w
0x18002e590  jnz     short loc_18002E59D
0x18002e592  mov     eax, dword ptr cs:in4addr_loopback.S_un
0x18002e598  mov     dword ptr [rbp+57h+name+4], eax
0x18002e59b  jmp     short loc_18002E5A9
0x18002e59d  movups  xmm0, xmmword ptr cs:in6addr_loopback.u
0x18002e5a4  movdqu  xmmword ptr [rbp+57h+name+8], xmm0
0x18002e5a9  mov     rcx, cs:LdapGlobalWakeupSelectHandle; s
0x18002e5b0  lea     rdx, [rbp+57h+name]; name
0x18002e5b4  mov     r8d, 80h; namelen
0x18002e5ba  call    cs:__imp_connect
0x18002e5c1  nop     dword ptr [rax+rax+00h]
0x18002e5c6  test    eax, eax
0x18002e5c8  jz      short loc_18002E601
0x18002e5ca  cmp     cs:g_fTracingOn, edi
0x18002e5d0  jz      loc_18002E65C
0x18002e5d6  cmp     cs:g_fProviderEnabled, edi
0x18002e5dc  jz      short loc_18002E65C
0x18002e5de  mov     ebx, 10000000h
0x18002e5e3  test    cs:g_ulTraceFlags, rbx
0x18002e5ea  jz      short loc_18002E65C
0x18002e5ec  call    cs:__imp_WSAGetLastError
0x18002e5f3  nop     dword ptr [rax+rax+00h]
0x18002e5f8  lea     rdx, aFailedToConnec; "Failed to connect socket to itself in L"...
0x18002e5ff  jmp     short loc_18002E652
0x18002e601  mov     rcx, cs:LdapGlobalWakeupSelectHandle; s
0x18002e608  lea     r8, [rbp+57h+argp]; argp
0x18002e60c  mov     edx, 8004667Eh; cmd
0x18002e611  call    cs:__imp_ioctlsocket
0x18002e618  nop     dword ptr [rax+rax+00h]
0x18002e61d  test    eax, eax
0x18002e61f  jz      short loc_18002E692
0x18002e621  cmp     cs:g_fTracingOn, edi
0x18002e627  jz      short loc_18002E65C
0x18002e629  cmp     cs:g_fProviderEnabled, edi
0x18002e62f  jz      short loc_18002E65C
0x18002e631  mov     ebx, 10000000h
0x18002e636  test    cs:g_ulTraceFlags, rbx
0x18002e63d  jz      short loc_18002E65C
0x18002e63f  call    cs:__imp_WSAGetLastError
0x18002e646  nop     dword ptr [rax+rax+00h]
0x18002e64b  lea     rdx, aFailedToSetSoc; "Failed to set socket to nonblocking in "...
0x18002e652  mov     r8d, eax
0x18002e655  mov     ecx, ebx
0x18002e657  call    LDAPClientPrint
0x18002e65c  mov     rcx, cs:?WinsockLibraryHandle@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002e663  test    rcx, rcx
0x18002e666  jz      short loc_18002E67B
0x18002e668  call    cs:__imp_FreeLibrary
0x18002e66f  nop     dword ptr [rax+rax+00h]
0x18002e674  mov     cs:?WinsockLibraryHandle@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * WinsockLibraryHandle
0x18002e67b  lea     rcx, LoadLibLock; lpCriticalSection
0x18002e682  call    cs:__imp_LeaveCriticalSection
0x18002e689  nop     dword ptr [rax+rax+00h]
0x18002e68e  xor     eax, eax
0x18002e690  jmp     short loc_18002E6B1
0x18002e692  mov     cs:?GlobalCloseWinsock@@3EA, 1; uchar GlobalCloseWinsock
0x18002e699  lea     rcx, LoadLibLock; lpCriticalSection
0x18002e6a0  call    cs:__imp_LeaveCriticalSection
0x18002e6a7  nop     dword ptr [rax+rax+00h]
0x18002e6ac  mov     eax, 1
0x18002e6b1  mov     rcx, [rbp+57h+var_30]
0x18002e6b5  xor     rcx, rsp; StackCookie
0x18002e6b8  call    __security_check_cookie
0x18002e6bd  add     rsp, 0C8h
0x18002e6c4  pop     r14
0x18002e6c6  pop     rdi
0x18002e6c7  pop     rbx
0x18002e6c8  pop     rbp
0x18002e6c9  retn
```
