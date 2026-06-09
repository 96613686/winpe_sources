# StartServiceIfNecessary(void)

- ea: `0x180019b1c`
- end: `0x180019d04`
- name: `?StartServiceIfNecessary@@YAJXZ`
- size: `488`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c8c0`

## callees

- `0x180019b1c`
- `0x18001e524`
- `0x180024640`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180019b67`
- `KERNEL32!GetLastError` at `0x180019ba1`
- `KERNEL32!GetLastError` at `0x180019bbb`
- `KERNEL32!GetLastError` at `0x180019be2`
- `KERNEL32!GetLastError` at `0x180019c03`
- `KERNEL32!GetLastError` at `0x180019c8d`
- `KERNEL32!GetLastError` at `0x180019ca9`
- `KERNEL32!GetLastError` at `0x180019cba`
- `KERNEL32!GetLastError` at `0x180019b67`
- `KERNEL32!GetLastError` at `0x180019ba1`
- `KERNEL32!GetLastError` at `0x180019bbb`
- `KERNEL32!GetLastError` at `0x180019be2`
- `KERNEL32!GetLastError` at `0x180019c03`
- `KERNEL32!GetLastError` at `0x180019c8d`
- `KERNEL32!GetLastError` at `0x180019ca9`
- `KERNEL32!GetLastError` at `0x180019cba`
- `KERNEL32!Sleep` at `0x180019c6e`
- `KERNEL32!Sleep` at `0x180019c6e`
- `ADVAPI32!OpenSCManagerW` at `0x180019b52`
- `ADVAPI32!OpenSCManagerW` at `0x180019b52`
- `ADVAPI32!OpenServiceW` at `0x180019b93`
- `ADVAPI32!OpenServiceW` at `0x180019b93`
- `ADVAPI32!StartServiceW` at `0x180019bd8`
- `ADVAPI32!StartServiceW` at `0x180019c5f`
- `ADVAPI32!StartServiceW` at `0x180019bd8`
- `ADVAPI32!StartServiceW` at `0x180019c5f`
- `ADVAPI32!QueryServiceStatus` at `0x180019c1e`
- `ADVAPI32!QueryServiceStatus` at `0x180019c1e`
- `ADVAPI32!CloseServiceHandle` at `0x180019cd8`
- `ADVAPI32!CloseServiceHandle` at `0x180019ce6`
- `ADVAPI32!CloseServiceHandle` at `0x180019cd8`
- `ADVAPI32!CloseServiceHandle` at `0x180019ce6`

## pseudocode

```c
__int64 StartServiceIfNecessary(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbp
  unsigned int v2; // ebx
  DWORD LastError; // eax
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  DWORD v6; // eax
  DWORD v7; // eax
  unsigned __int16 v8; // r8
  unsigned int v9; // edx
  DWORD v10; // eax
  DWORD dwCheckPoint; // ebx
  int v12; // edi
  DWORD dwWaitHint; // ecx
  DWORD v14; // eax
  LPCWSTR ServiceArgVectors; // [rsp+20h] [rbp-58h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-50h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  ServiceArgVectors = 0;
  v0 = OpenSCManagerW(0, 0, 0x80000000);
  v1 = v0;
  if ( !v0 )
  {
    v2 = 1721;
    LastError = GetLastError();
    CompRpcpErrorAddRecord(0xDu, 0x6B9u, 0x690u, LastError);
    return v2;
  }
  v4 = OpenServiceW(v0, L"RPCHTTPLBS", 0x80000010);
  v5 = v4;
  if ( !v4 )
  {
    v6 = GetLastError();
    v2 = v6;
    if ( v6 != 5 && v6 != 1060 )
      v2 = 1721;
    v7 = GetLastError();
    v8 = 1681;
LABEL_8:
    v9 = v2;
    goto LABEL_36;
  }
  if ( !StartServiceW(v4, 0, &ServiceArgVectors) )
  {
    v10 = GetLastError();
    v2 = v10;
    if ( v10 != 1056 )
    {
      if ( v10 != 5 && v10 != 1053 )
        v2 = 1721;
      v7 = GetLastError();
      v8 = 1682;
      goto LABEL_8;
    }
  }
  dwCheckPoint = 0;
  v12 = 1;
  while ( 1 )
  {
    if ( !QueryServiceStatus(v5, &ServiceStatus) )
    {
      v2 = 1721;
      v7 = GetLastError();
      v9 = 1721;
      goto LABEL_35;
    }
    if ( ServiceStatus.dwCurrentState == 1 )
      break;
    if ( ServiceStatus.dwCurrentState != 2 && ServiceStatus.dwCurrentState != 3 )
    {
      if ( ServiceStatus.dwCurrentState != 4 )
      {
        v2 = 1766;
        goto LABEL_37;
      }
      goto LABEL_28;
    }
    if ( !v12 && dwCheckPoint == ServiceStatus.dwCheckPoint )
    {
      v2 = 1053;
      goto LABEL_37;
    }
    dwCheckPoint = ServiceStatus.dwCheckPoint;
    v12 = 0;
    dwWaitHint = ServiceStatus.dwWaitHint;
LABEL_25:
    Sleep(dwWaitHint);
  }
  if ( StartServiceW(v5, 0, &ServiceArgVectors) )
  {
    dwWaitHint = 500;
    goto LABEL_25;
  }
  v14 = GetLastError();
  v2 = v14;
  if ( v14 == 1056 )
  {
LABEL_28:
    v2 = 0;
    goto LABEL_37;
  }
  if ( v14 != 1053 )
    v2 = 1721;
  v7 = GetLastError();
  v9 = v2;
LABEL_35:
  v8 = 1683;
LABEL_36:
  CompRpcpErrorAddRecord(0xDu, v9, v8, v7);
LABEL_37:
  CloseServiceHandle(v1);
  if ( v5 )
    CloseServiceHandle(v5);
  return v2;
}

```

## disassembly

```asm
0x180019b1c  push    rbx
0x180019b1e  push    rbp
0x180019b1f  push    rsi
0x180019b20  push    rdi
0x180019b21  sub     rsp, 58h
0x180019b25  mov     rax, cs:__security_cookie
0x180019b2c  xor     rax, rsp
0x180019b2f  mov     [rsp+78h+var_30], rax
0x180019b34  xorps   xmm0, xmm0
0x180019b37  xor     eax, eax
0x180019b39  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180019b3e  xor     edx, edx; lpDatabaseName
0x180019b40  mov     [rsp+78h+ServiceArgVectors], rax
0x180019b45  xor     ecx, ecx; lpMachineName
0x180019b47  mov     r8d, 80000000h; dwDesiredAccess
0x180019b4d  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180019b52  call    cs:__imp_OpenSCManagerW
0x180019b58  mov     rbp, rax
0x180019b5b  test    rax, rax
0x180019b5e  jnz     short loc_180019B83
0x180019b60  mov     edi, 6B9h
0x180019b65  mov     ebx, edi
0x180019b67  call    cs:__imp_GetLastError
0x180019b6d  lea     r8d, [rdi-29h]; unsigned __int16
0x180019b71  mov     edx, edi; unsigned int
0x180019b73  mov     r9d, eax; unsigned int
0x180019b76  lea     ecx, [rbp+0Dh]; unsigned int
0x180019b79  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x180019b7e  jmp     loc_180019CEC
0x180019b83  mov     r8d, 80000010h; dwDesiredAccess
0x180019b89  lea     rdx, ServiceName; "RPCHTTPLBS"
0x180019b90  mov     rcx, rbp; hSCManager
0x180019b93  call    cs:__imp_OpenServiceW
0x180019b99  mov     rsi, rax
0x180019b9c  test    rax, rax
0x180019b9f  jnz     short loc_180019BCE
0x180019ba1  call    cs:__imp_GetLastError
0x180019ba7  mov     ebx, eax
0x180019ba9  cmp     eax, 5
0x180019bac  jz      short loc_180019BBB
0x180019bae  cmp     eax, 424h
0x180019bb3  mov     edi, 6B9h
0x180019bb8  cmovnz  ebx, edi
0x180019bbb  call    cs:__imp_GetLastError
0x180019bc1  mov     r8d, 691h
0x180019bc7  mov     edx, ebx
0x180019bc9  jmp     loc_180019CC8
0x180019bce  lea     r8, [rsp+78h+ServiceArgVectors]; lpServiceArgVectors
0x180019bd3  xor     edx, edx; dwNumServiceArgs
0x180019bd5  mov     rcx, rsi; hService
0x180019bd8  call    cs:__imp_StartServiceW
0x180019bde  test    eax, eax
0x180019be0  jnz     short loc_180019C11
0x180019be2  call    cs:__imp_GetLastError
0x180019be8  mov     ebx, eax
0x180019bea  cmp     eax, 420h
0x180019bef  jz      short loc_180019C11
0x180019bf1  cmp     eax, 5
0x180019bf4  jz      short loc_180019C03
0x180019bf6  cmp     eax, 41Dh
0x180019bfb  mov     edi, 6B9h
0x180019c00  cmovnz  ebx, edi
0x180019c03  call    cs:__imp_GetLastError
0x180019c09  mov     r8d, 692h
0x180019c0f  jmp     short loc_180019BC7
0x180019c11  xor     ebx, ebx
0x180019c13  lea     edi, [rbx+1]
0x180019c16  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180019c1b  mov     rcx, rsi; hService
0x180019c1e  call    cs:__imp_QueryServiceStatus
0x180019c24  test    eax, eax
0x180019c26  jz      loc_180019CB3
0x180019c2c  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x180019c30  sub     eax, 1
0x180019c33  jz      short loc_180019C55
0x180019c35  sub     eax, 1
0x180019c38  jz      short loc_180019C3F
0x180019c3a  sub     eax, 1
0x180019c3d  jnz     short loc_180019C76
0x180019c3f  test    edi, edi
0x180019c41  jnz     short loc_180019C49
0x180019c43  cmp     ebx, [rsp+78h+ServiceStatus.dwCheckPoint]
0x180019c47  jz      short loc_180019C86
0x180019c49  mov     ebx, [rsp+78h+ServiceStatus.dwCheckPoint]
0x180019c4d  xor     edi, edi
0x180019c4f  mov     ecx, [rsp+78h+ServiceStatus.dwWaitHint]
0x180019c53  jmp     short loc_180019C6E
0x180019c55  lea     r8, [rsp+78h+ServiceArgVectors]; lpServiceArgVectors
0x180019c5a  xor     edx, edx; dwNumServiceArgs
0x180019c5c  mov     rcx, rsi; hService
0x180019c5f  call    cs:__imp_StartServiceW
0x180019c65  test    eax, eax
0x180019c67  jz      short loc_180019C8D
0x180019c69  mov     ecx, 1F4h; dwMilliseconds
0x180019c6e  call    cs:__imp_Sleep
0x180019c74  jmp     short loc_180019C16
0x180019c76  cmp     eax, 1
0x180019c79  jz      short loc_180019C82
0x180019c7b  mov     ebx, 6E6h
0x180019c80  jmp     short loc_180019CD5
0x180019c82  xor     ebx, ebx
0x180019c84  jmp     short loc_180019CD5
0x180019c86  mov     ebx, 41Dh
0x180019c8b  jmp     short loc_180019CD5
0x180019c8d  call    cs:__imp_GetLastError
0x180019c93  mov     ebx, eax
0x180019c95  cmp     eax, 420h
0x180019c9a  jz      short loc_180019C82
0x180019c9c  cmp     eax, 41Dh
0x180019ca1  mov     edi, 6B9h
0x180019ca6  cmovnz  ebx, edi
0x180019ca9  call    cs:__imp_GetLastError
0x180019caf  mov     edx, ebx
0x180019cb1  jmp     short loc_180019CC2
0x180019cb3  mov     edi, 6B9h
0x180019cb8  mov     ebx, edi
0x180019cba  call    cs:__imp_GetLastError
0x180019cc0  mov     edx, edi; unsigned int
0x180019cc2  mov     r8d, 693h; unsigned __int16
0x180019cc8  mov     r9d, eax; unsigned int
0x180019ccb  mov     ecx, 0Dh; unsigned int
0x180019cd0  call    ?CompRpcpErrorAddRecord@@YAXKKGK@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)
0x180019cd5  mov     rcx, rbp; hSCObject
0x180019cd8  call    cs:__imp_CloseServiceHandle
0x180019cde  test    rsi, rsi
0x180019ce1  jz      short loc_180019CEC
0x180019ce3  mov     rcx, rsi; hSCObject
0x180019ce6  call    cs:__imp_CloseServiceHandle
0x180019cec  mov     eax, ebx
0x180019cee  mov     rcx, [rsp+78h+var_30]
0x180019cf3  xor     rcx, rsp; StackCookie
0x180019cf6  call    __security_check_cookie
0x180019cfb  add     rsp, 58h
0x180019cff  pop     rdi
0x180019d00  pop     rsi
0x180019d01  pop     rbp
0x180019d02  pop     rbx
0x180019d03  retn
```
