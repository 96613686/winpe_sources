# NlWaitForNetlogon(ulong)

- ea: `0x180031358`
- end: `0x18003154c`
- name: `?NlWaitForNetlogon@@YAJK@Z`
- size: `500`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18002d250`

## callees

- `0x180031358`
- `0x18003d270`
- `0x18003dd2c`
- `0x18004ffbc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003151f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003151f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003142e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003142e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031414`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800314dd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800314dd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800313aa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800313aa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800314f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003150b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800314f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003150b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800313d8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800313d8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800313fe`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003145a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800313fe`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003145a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180031481`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180031481`

## pseudocode

```c
__int64 __fastcall NlWaitForNetlogon()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // r12
  unsigned int v2; // ebx
  _QUERY_SERVICE_CONFIGW *v3; // rdi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  _QUERY_SERVICE_CONFIGW *p_ServiceConfig; // rbx
  struct _QUERY_SERVICE_CONFIGW *v7; // rax
  int v8; // r15d
  char v9; // r14
  const char *v10; // rdx
  const char *v11; // rcx
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-59h] BYREF
  unsigned int v14[3]; // [rsp+24h] [rbp-55h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+30h] [rbp-49h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp-9h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  memset_0(&ServiceConfig, 0, sizeof(ServiceConfig));
  pcbBytesNeeded = 0;
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( !v0 )
    return (unsigned int)-1073741422;
  v3 = 0;
  v4 = OpenServiceW(v0, L"NETLOGON", 5u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_24;
  if ( QueryServiceConfigW(v4, &ServiceConfig, 0x40u, &pcbBytesNeeded) )
  {
    p_ServiceConfig = &ServiceConfig;
    goto LABEL_11;
  }
  if ( GetLastError() != 122 )
  {
LABEL_24:
    v2 = -1073741422;
    goto LABEL_25;
  }
  v7 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded);
  v3 = v7;
  if ( v7 )
  {
    if ( QueryServiceConfigW(v5, v7, pcbBytesNeeded, &pcbBytesNeeded) )
    {
      p_ServiceConfig = v3;
LABEL_11:
      v8 = 1000;
      v9 = 1;
      while ( QueryServiceStatus(v5, &ServiceStatus) )
      {
        switch ( ServiceStatus.dwCurrentState )
        {
          case 1u:
            if ( ServiceStatus.dwWin32ExitCode != 1077 )
              goto LABEL_24;
            break;
          case 2u:
            break;
          case 4u:
            v2 = 0;
            goto LABEL_25;
          default:
            goto LABEL_24;
        }
        if ( v9 )
        {
          v14[0] = 0;
          if ( NlReadDwordHklmRegValue(v11, v10, v14) && v14[0] == 1 || p_ServiceConfig->dwStartType != 2 )
            goto LABEL_24;
          v9 = 0;
        }
        Sleep(0x2710u);
        if ( !--v8 )
          goto LABEL_24;
      }
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  v2 = -1073741801;
LABEL_25:
  CloseServiceHandle(v1);
  if ( v5 )
    CloseServiceHandle(v5);
  if ( v3 )
    LocalFree(v3);
  return v2;
}

```

## disassembly

```asm
0x180031358  push    rbp
0x18003135a  push    rbx
0x18003135b  push    rsi
0x18003135c  push    rdi
0x18003135d  push    r12
0x18003135f  push    r14
0x180031361  push    r15
0x180031363  lea     rbp, [rsp-27h]
0x180031368  sub     rsp, 0A0h
0x18003136f  mov     rax, cs:__security_cookie
0x180031376  xor     rax, rsp
0x180031379  mov     [rbp+57h+var_40], rax
0x18003137d  xorps   xmm0, xmm0
0x180031380  lea     rcx, [rbp+57h+ServiceConfig]; void *
0x180031384  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180031388  mov     ebx, 40h ; '@'
0x18003138d  xor     edx, edx; Val
0x18003138f  mov     r8d, ebx; Size
0x180031392  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180031396  call    memset_0
0x18003139b  xor     edx, edx; lpDatabaseName
0x18003139d  mov     [rbp+57h+pcbBytesNeeded], 0
0x1800313a4  xor     ecx, ecx; lpMachineName
0x1800313a6  lea     r8d, [rbx-3Fh]; dwDesiredAccess
0x1800313aa  call    cs:__imp_OpenSCManagerW
0x1800313b1  nop     dword ptr [rax+rax+00h]
0x1800313b6  mov     r12, rax
0x1800313b9  test    rax, rax
0x1800313bc  jnz     short loc_1800313C8
0x1800313be  mov     ebx, 0C0000192h
0x1800313c3  jmp     loc_18003152B
0x1800313c8  xor     edi, edi
0x1800313ca  lea     rdx, ServiceName; "NETLOGON"
0x1800313d1  mov     rcx, r12; hSCManager
0x1800313d4  lea     r8d, [rdi+5]; dwDesiredAccess
0x1800313d8  call    cs:__imp_OpenServiceW
0x1800313df  nop     dword ptr [rax+rax+00h]
0x1800313e4  mov     rsi, rax
0x1800313e7  test    rax, rax
0x1800313ea  jz      loc_1800314EF
0x1800313f0  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x1800313f4  mov     r8d, ebx; cbBufSize
0x1800313f7  lea     rdx, [rbp+57h+ServiceConfig]; lpServiceConfig
0x1800313fb  mov     rcx, rax; hService
0x1800313fe  call    cs:__imp_QueryServiceConfigW
0x180031405  nop     dword ptr [rax+rax+00h]
0x18003140a  test    eax, eax
0x18003140c  jz      short loc_180031414
0x18003140e  lea     rbx, [rbp+57h+ServiceConfig]
0x180031412  jmp     short loc_180031471
0x180031414  call    cs:__imp_GetLastError
0x18003141b  nop     dword ptr [rax+rax+00h]
0x180031420  cmp     eax, 7Ah ; 'z'
0x180031423  jnz     loc_1800314EF
0x180031429  mov     edx, [rbp+57h+pcbBytesNeeded]; uBytes
0x18003142c  xor     ecx, ecx; uFlags
0x18003142e  call    cs:__imp_LocalAlloc
0x180031435  nop     dword ptr [rax+rax+00h]
0x18003143a  mov     rdi, rax
0x18003143d  test    rax, rax
0x180031440  jnz     short loc_18003144C
0x180031442  mov     ebx, 0C0000017h
0x180031447  jmp     loc_1800314F4
0x18003144c  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x180031450  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180031454  mov     rdx, rdi; lpServiceConfig
0x180031457  mov     rcx, rsi; hService
0x18003145a  call    cs:__imp_QueryServiceConfigW
0x180031461  nop     dword ptr [rax+rax+00h]
0x180031466  test    eax, eax
0x180031468  jz      loc_1800314EF
0x18003146e  mov     rbx, rdi
0x180031471  mov     r15d, 3E8h
0x180031477  mov     r14b, 1
0x18003147a  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18003147e  mov     rcx, rsi; hService
0x180031481  call    cs:__imp_QueryServiceStatus
0x180031488  nop     dword ptr [rax+rax+00h]
0x18003148d  test    eax, eax
0x18003148f  jz      short loc_1800314EF
0x180031491  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x180031494  sub     eax, 1
0x180031497  jz      short loc_1800314A7
0x180031499  sub     eax, 1
0x18003149c  jz      short loc_1800314B0
0x18003149e  cmp     eax, 2
0x1800314a1  jnz     short loc_1800314EF
0x1800314a3  xor     ebx, ebx
0x1800314a5  jmp     short loc_1800314F4
0x1800314a7  cmp     [rbp+57h+ServiceStatus.dwWin32ExitCode], 435h
0x1800314ae  jnz     short loc_1800314EF
0x1800314b0  test    r14b, r14b
0x1800314b3  jz      short loc_1800314D8
0x1800314b5  lea     r8, [rbp+57h+var_AC]; unsigned int *
0x1800314b9  mov     [rbp+57h+var_AC], 0
0x1800314c0  call    ?NlReadDwordHklmRegValue@@YAEPEBD0PEAK@Z; NlReadDwordHklmRegValue(char const *,char const *,ulong *)
0x1800314c5  test    al, al
0x1800314c7  jz      short loc_1800314CF
0x1800314c9  cmp     [rbp+57h+var_AC], 1
0x1800314cd  jz      short loc_1800314EF
0x1800314cf  cmp     dword ptr [rbx+4], 2
0x1800314d3  jnz     short loc_1800314EF
0x1800314d5  xor     r14b, r14b
0x1800314d8  mov     ecx, 2710h; dwMilliseconds
0x1800314dd  call    cs:__imp_Sleep
0x1800314e4  nop     dword ptr [rax+rax+00h]
0x1800314e9  add     r15d, 0FFFFFFFFh
0x1800314ed  jnz     short loc_18003147A
0x1800314ef  mov     ebx, 0C0000192h
0x1800314f4  mov     rcx, r12; hSCObject
0x1800314f7  call    cs:__imp_CloseServiceHandle
0x1800314fe  nop     dword ptr [rax+rax+00h]
0x180031503  test    rsi, rsi
0x180031506  jz      short loc_180031517
0x180031508  mov     rcx, rsi; hSCObject
0x18003150b  call    cs:__imp_CloseServiceHandle
0x180031512  nop     dword ptr [rax+rax+00h]
0x180031517  test    rdi, rdi
0x18003151a  jz      short loc_18003152B
0x18003151c  mov     rcx, rdi; hMem
0x18003151f  call    cs:__imp_LocalFree
0x180031526  nop     dword ptr [rax+rax+00h]
0x18003152b  mov     eax, ebx
0x18003152d  mov     rcx, [rbp+57h+var_40]
0x180031531  xor     rcx, rsp; StackCookie
0x180031534  call    __security_check_cookie
0x180031539  add     rsp, 0A0h
0x180031540  pop     r15
0x180031542  pop     r14
0x180031544  pop     r12
0x180031546  pop     rdi
0x180031547  pop     rsi
0x180031548  pop     rbx
0x180031549  pop     rbp
0x18003154a  retn
```
