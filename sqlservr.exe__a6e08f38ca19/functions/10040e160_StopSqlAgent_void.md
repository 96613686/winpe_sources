# StopSqlAgent(void)

- ea: `0x10040e160`
- end: `0x10040e364`
- name: `?StopSqlAgent@@YAXXZ`
- size: `516`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x100418d20`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x10040e160`
- `0x1004403d0`
- `0x100440b50`

## import_xrefs

- `KERNEL32!Sleep` at `0x10040e21e`
- `KERNEL32!Sleep` at `0x10040e21e`
- `KERNEL32!GetLastError` at `0x10040e234`
- `KERNEL32!GetLastError` at `0x10040e2a7`
- `KERNEL32!GetLastError` at `0x10040e303`
- `KERNEL32!GetLastError` at `0x10040e234`
- `KERNEL32!GetLastError` at `0x10040e2a7`
- `KERNEL32!GetLastError` at `0x10040e303`
- `ADVAPI32!CloseServiceHandle` at `0x10040e27f`
- `ADVAPI32!CloseServiceHandle` at `0x10040e2f2`
- `ADVAPI32!CloseServiceHandle` at `0x10040e27f`
- `ADVAPI32!CloseServiceHandle` at `0x10040e2f2`
- `ADVAPI32!ControlService` at `0x10040e213`
- `ADVAPI32!ControlService` at `0x10040e213`
- `ADVAPI32!QueryServiceStatusEx` at `0x10040e1ea`
- `ADVAPI32!QueryServiceStatusEx` at `0x10040e1ea`
- `ADVAPI32!OpenServiceW` at `0x10040e1b3`
- `ADVAPI32!OpenServiceW` at `0x10040e1b3`
- `ADVAPI32!OpenSCManagerW` at `0x10040e189`
- `ADVAPI32!OpenSCManagerW` at `0x10040e189`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040e247`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040e2ba`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040e316`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040e247`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040e2ba`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040e316`

## string_xrefs

- `0x10040e25f`: `QueryServiceStatusEx`
- `0x10040e1a9`: `SQLSERVERAGENT`
- `0x10040e255`: `SQLSERVERAGENT`
- `0x10040e2c8`: `SQLSERVERAGENT`
- `0x10040e2d2`: `OpenServiceW`
- `0x10040e32e`: `OpenSCManager`

## pseudocode

```c
void StopSqlAgent(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  SC_HANDLE v2; // rdi
  int v3; // ebx
  DWORD LastError; // eax
  wchar_t *OSErrString; // rax
  DWORD v6; // eax
  wchar_t *v7; // rax
  DWORD v8; // eax
  wchar_t *v9; // rax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-1048h] BYREF
  struct _SERVICE_STATUS Buffer; // [rsp+38h] [rbp-1040h] BYREF
  _BYTE v12[4096]; // [rsp+60h] [rbp-1018h] BYREF

  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"SQLSERVERAGENT", 0x24u);
    if ( v2 )
    {
      v3 = 0;
      while ( QueryServiceStatusEx(v2, SC_STATUS_PROCESS_INFO, (LPBYTE)&Buffer, 0x24u, &pcbBytesNeeded) )
      {
        if ( ((Buffer.dwCurrentState - 1) & 0xFFFFFFFD) != 0 && v3 <= 3 )
          ControlService(v2, 1u, &Buffer);
        Sleep(0x3E8u);
        ++v3;
        if ( Buffer.dwCurrentState == 1 || v3 > 10 )
          goto LABEL_12;
      }
      LastError = GetLastError();
      OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v12, 0, 0);
      scierrlog(
        0xE31u,
        OSErrString,
        L"QueryServiceStatusEx",
        L"SQLSERVERAGENT",
        "sql\\ntdbms\\ksource\\serverma.cpp",
        1098);
LABEL_12:
      CloseServiceHandle(v2);
      if ( Buffer.dwCurrentState == 1 )
        ex_callprint(45201, 10, 0);
    }
    else
    {
      v6 = GetLastError();
      v7 = GetOSErrString(v6, (struct ErrorStringHolder *)v12, 0, 0);
      scierrlog(0xE31u, v7, L"OpenServiceW", L"SQLSERVERAGENT", "sql\\ntdbms\\ksource\\serverma.cpp", 1134);
    }
    CloseServiceHandle(v1);
  }
  else
  {
    v8 = GetLastError();
    v9 = GetOSErrString(v8, (struct ErrorStringHolder *)v12, 0, 0);
    scierrlog(0xE31u, v9, L"OpenSCManager", L"SC Manager Database", "sql\\ntdbms\\ksource\\serverma.cpp", 1146);
  }
}

```

## disassembly

```asm
0x10040e160  push    rsi
0x10040e162  mov     eax, 1070h
0x10040e167  call    _alloca_probe
0x10040e16c  sub     rsp, rax
0x10040e16f  mov     rax, cs:__security_cookie
0x10040e176  xor     rax, rsp
0x10040e179  mov     [rsp+1078h+var_18], rax
0x10040e181  xor     edx, edx; lpDatabaseName
0x10040e183  xor     ecx, ecx; lpMachineName
0x10040e185  lea     r8d, [rdx+1]; dwDesiredAccess
0x10040e189  call    cs:__imp_OpenSCManagerW
0x10040e18f  mov     rsi, rax
0x10040e192  test    rax, rax
0x10040e195  jz      loc_10040E303
0x10040e19b  mov     r8d, 24h ; '$'; dwDesiredAccess
0x10040e1a1  mov     [rsp+1078h+arg_8], rdi
0x10040e1a9  lea     rdx, aSqlserveragent; "SQLSERVERAGENT"
0x10040e1b0  mov     rcx, rax; hSCManager
0x10040e1b3  call    cs:__imp_OpenServiceW
0x10040e1b9  mov     rdi, rax
0x10040e1bc  test    rax, rax
0x10040e1bf  jz      loc_10040E2A7
0x10040e1c5  mov     [rsp+1078h+arg_0], rbx
0x10040e1cd  xor     ebx, ebx
0x10040e1cf  nop
0x10040e1d0  lea     rax, [rsp+1078h+var_1048]
0x10040e1d5  mov     r9d, 24h ; '$'; cbBufSize
0x10040e1db  lea     r8, [rsp+1078h+Buffer]; lpBuffer
0x10040e1e0  mov     [rsp+1078h+pcbBytesNeeded], rax; pcbBytesNeeded
0x10040e1e5  xor     edx, edx; InfoLevel
0x10040e1e7  mov     rcx, rdi; hService
0x10040e1ea  call    cs:__imp_QueryServiceStatusEx
0x10040e1f0  test    eax, eax
0x10040e1f2  jz      short loc_10040E234
0x10040e1f4  mov     eax, [rsp+1078h+var_103C]
0x10040e1f8  dec     eax
0x10040e1fa  test    eax, 0FFFFFFFDh
0x10040e1ff  jz      short loc_10040E219
0x10040e201  cmp     ebx, 3
0x10040e204  jg      short loc_10040E219
0x10040e206  lea     r8, [rsp+1078h+Buffer]; lpServiceStatus
0x10040e20b  mov     edx, 1; dwControl
0x10040e210  mov     rcx, rdi; hService
0x10040e213  call    cs:__imp_ControlService
0x10040e219  mov     ecx, 3E8h; dwMilliseconds
0x10040e21e  call    cs:__imp_Sleep
0x10040e224  inc     ebx
0x10040e226  cmp     [rsp+1078h+var_103C], 1
0x10040e22b  jz      short loc_10040E27C
0x10040e22d  cmp     ebx, 0Ah
0x10040e230  jle     short loc_10040E1D0
0x10040e232  jmp     short loc_10040E27C
0x10040e234  call    cs:__imp_GetLastError
0x10040e23a  xor     r9d, r9d
0x10040e23d  lea     rdx, [rsp+1078h+var_1018]
0x10040e242  mov     ecx, eax
0x10040e244  xor     r8d, r8d
0x10040e247  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040e24d  mov     [rsp+1078h+var_1050], 44Ah
0x10040e255  lea     r9, aSqlserveragent; "SQLSERVERAGENT"
0x10040e25c  mov     rdx, rax
0x10040e25f  lea     r8, aQueryservicest; "QueryServiceStatusEx"
0x10040e266  lea     rax, aSqlNtdbmsKsour_1; "sql\\ntdbms\\ksource\\serverma.cpp"
0x10040e26d  mov     ecx, 0E31h; unsigned int
0x10040e272  mov     [rsp+1078h+pcbBytesNeeded], rax
0x10040e277  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040e27c  mov     rcx, rdi; hSCObject
0x10040e27f  call    cs:__imp_CloseServiceHandle
0x10040e285  cmp     [rsp+1078h+var_103C], 1
0x10040e28a  mov     rbx, [rsp+1078h+arg_0]
0x10040e292  jnz     short loc_10040E2EF
0x10040e294  xor     r8d, r8d; int
0x10040e297  mov     ecx, 0B091h; int
0x10040e29c  lea     edx, [r8+0Ah]; int
0x10040e2a0  call    ?ex_callprint@@YAXHHHZZ; ex_callprint(int,int,int,...)
0x10040e2a5  jmp     short loc_10040E2EF
0x10040e2a7  call    cs:__imp_GetLastError
0x10040e2ad  xor     r9d, r9d
0x10040e2b0  lea     rdx, [rsp+1078h+var_1018]
0x10040e2b5  mov     ecx, eax
0x10040e2b7  xor     r8d, r8d
0x10040e2ba  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040e2c0  mov     [rsp+1078h+var_1050], 46Eh
0x10040e2c8  lea     r9, aSqlserveragent; "SQLSERVERAGENT"
0x10040e2cf  mov     rdx, rax
0x10040e2d2  lea     r8, aOpenservicew; "OpenServiceW"
0x10040e2d9  lea     rax, aSqlNtdbmsKsour_1; "sql\\ntdbms\\ksource\\serverma.cpp"
0x10040e2e0  mov     ecx, 0E31h; unsigned int
0x10040e2e5  mov     [rsp+1078h+pcbBytesNeeded], rax
0x10040e2ea  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040e2ef  mov     rcx, rsi; hSCObject
0x10040e2f2  call    cs:__imp_CloseServiceHandle
0x10040e2f8  mov     rdi, [rsp+1078h+arg_8]
0x10040e300  jmp     short loc_10040E34B
0x10040e303  call    cs:__imp_GetLastError
0x10040e309  xor     r9d, r9d
0x10040e30c  lea     rdx, [rsp+1078h+var_1018]
0x10040e311  mov     ecx, eax
0x10040e313  xor     r8d, r8d
0x10040e316  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040e31c  mov     [rsp+1078h+var_1050], 47Ah
0x10040e324  lea     r9, aScManagerDatab; "SC Manager Database"
0x10040e32b  mov     rdx, rax
0x10040e32e  lea     r8, aOpenscmanager; "OpenSCManager"
0x10040e335  lea     rax, aSqlNtdbmsKsour_1; "sql\\ntdbms\\ksource\\serverma.cpp"
0x10040e33c  mov     ecx, 0E31h; unsigned int
0x10040e341  mov     [rsp+1078h+pcbBytesNeeded], rax
0x10040e346  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040e34b  mov     rcx, [rsp+1078h+var_18]
0x10040e353  xor     rcx, rsp; StackCookie
0x10040e356  call    __security_check_cookie
0x10040e35b  add     rsp, 1070h
0x10040e362  pop     rsi
0x10040e363  retn
```
