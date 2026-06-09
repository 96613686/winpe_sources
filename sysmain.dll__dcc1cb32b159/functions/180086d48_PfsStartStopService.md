# PfsStartStopService

- ea: `0x180086d48`
- end: `0x180086e5e`
- name: `PfsStartStopService`
- size: `278`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180085bd4`
- `0x180086cac`

## callees

- `0x180086d48`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180086e01`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180086e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086dae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086dae`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180086dcf`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180086dcf`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180086da4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180086de1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180086e15`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180086da4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180086de1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180086e15`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180086e2b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180086e2b`

## pseudocode

```c
DWORD __fastcall PfsStartStopService(SC_HANDLE hService, int a2)
{
  int v4; // r14d
  int v5; // esi
  int v6; // ebp
  DWORD result; // eax
  BOOL v8; // eax
  unsigned int i; // edi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-48h] BYREF

  v4 = 3 - (a2 != 0);
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v5 = a2 != 0 ? 4 : 1;
  v6 = (a2 != 0) + 351;
  if ( !QueryServiceStatus(hService, &ServiceStatus) )
    return GetLastError();
  if ( ServiceStatus.dwCurrentState == v5 )
    return 0;
  if ( a2 )
  {
    if ( !StartServiceW(hService, 0, 0) )
      return GetLastError();
    v8 = QueryServiceStatus(hService, &ServiceStatus);
  }
  else
  {
    v8 = ControlService(hService, 1u, &ServiceStatus);
  }
  if ( !v8 )
    return GetLastError();
  for ( i = 0; ServiceStatus.dwCurrentState == v4 && i < 0x3A98; i += 1000 )
  {
    Sleep(0x3E8u);
    if ( !QueryServiceStatus(hService, &ServiceStatus) )
      return GetLastError();
  }
  result = 0;
  if ( ServiceStatus.dwCurrentState != v5 )
    return v6;
  return result;
}

```

## disassembly

```asm
0x180086d48  mov     [rsp+arg_8], rbx
0x180086d4d  mov     [rsp+arg_10], rbp
0x180086d52  push    rsi
0x180086d53  push    rdi
0x180086d54  push    r14
0x180086d56  sub     rsp, 50h
0x180086d5a  mov     rax, cs:__security_cookie
0x180086d61  xor     rax, rsp
0x180086d64  mov     [rsp+68h+var_28], rax
0x180086d69  mov     eax, edx
0x180086d6b  xorps   xmm0, xmm0
0x180086d6e  neg     eax
0x180086d70  mov     edi, edx
0x180086d72  mov     eax, edx
0x180086d74  mov     rbx, rcx
0x180086d77  sbb     r14d, r14d
0x180086d7a  add     r14d, 3
0x180086d7e  neg     eax
0x180086d80  mov     eax, edx
0x180086d82  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180086d87  sbb     esi, esi
0x180086d89  and     esi, 3
0x180086d8c  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x180086d91  inc     esi
0x180086d93  neg     eax
0x180086d95  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x180086d9a  sbb     ebp, ebp
0x180086d9c  neg     ebp
0x180086d9e  add     ebp, 15Fh
0x180086da4  call    cs:__imp_QueryServiceStatus
0x180086daa  test    eax, eax
0x180086dac  jnz     short loc_180086DB9
0x180086dae  call    cs:__imp_GetLastError
0x180086db4  jmp     loc_180086E3C
0x180086db9  cmp     [rsp+68h+ServiceStatus.dwCurrentState], esi
0x180086dbd  jnz     short loc_180086DC3
0x180086dbf  xor     eax, eax
0x180086dc1  jmp     short loc_180086E3C
0x180086dc3  mov     rcx, rbx; hService
0x180086dc6  test    edi, edi
0x180086dc8  jz      short loc_180086E21
0x180086dca  xor     r8d, r8d; lpServiceArgVectors
0x180086dcd  xor     edx, edx; dwNumServiceArgs
0x180086dcf  call    cs:__imp_StartServiceW
0x180086dd5  test    eax, eax
0x180086dd7  jz      short loc_180086DAE
0x180086dd9  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180086dde  mov     rcx, rbx; hService
0x180086de1  call    cs:__imp_QueryServiceStatus
0x180086de7  test    eax, eax
0x180086de9  jz      short loc_180086DAE
0x180086deb  xor     edi, edi
0x180086ded  cmp     [rsp+68h+ServiceStatus.dwCurrentState], r14d
0x180086df2  jnz     short loc_180086E33
0x180086df4  cmp     edi, 3A98h
0x180086dfa  jnb     short loc_180086E33
0x180086dfc  mov     ecx, 3E8h; dwMilliseconds
0x180086e01  call    cs:__imp_Sleep
0x180086e07  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180086e0c  mov     rcx, rbx; hService
0x180086e0f  add     edi, 3E8h
0x180086e15  call    cs:__imp_QueryServiceStatus
0x180086e1b  test    eax, eax
0x180086e1d  jnz     short loc_180086DED
0x180086e1f  jmp     short loc_180086DAE
0x180086e21  lea     r8, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180086e26  mov     edx, 1; dwControl
0x180086e2b  call    cs:__imp_ControlService
0x180086e31  jmp     short loc_180086DE7
0x180086e33  xor     eax, eax
0x180086e35  cmp     [rsp+68h+ServiceStatus.dwCurrentState], esi
0x180086e39  cmovnz  eax, ebp
0x180086e3c  mov     rcx, [rsp+68h+var_28]
0x180086e41  xor     rcx, rsp; StackCookie
0x180086e44  call    __security_check_cookie
0x180086e49  lea     r11, [rsp+68h+var_18]
0x180086e4e  mov     rbx, [r11+28h]
0x180086e52  mov     rbp, [r11+30h]
0x180086e56  mov     rsp, r11
0x180086e59  pop     r14
0x180086e5b  pop     rdi
0x180086e5c  pop     rsi
0x180086e5d  retn
```
