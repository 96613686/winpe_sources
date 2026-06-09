# IsSpoolerEnabled(void)

- ea: `0x1800164c8`
- end: `0x1800165c0`
- name: `?IsSpoolerEnabled@@YAHXZ`
- size: `248`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180015428`

## callees

- `0x1800164c8`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001650d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001657c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001650d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001657c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180016528`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180016528`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016593`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001659c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180016593`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001659c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800164ff`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800164ff`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180016546`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180016546`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180016572`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180016572`

## pseudocode

```c
__int64 IsSpoolerEnabled(void)
{
  unsigned int v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-268h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-260h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+50h] [rbp-238h] BYREF

  v0 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"Spooler", 5u);
    v4 = v3;
    if ( v3 )
    {
      if ( QueryServiceStatus(v3, &ServiceStatus) && ServiceStatus.dwCurrentState == 4 )
      {
        v0 = 1;
      }
      else
      {
        pcbBytesNeeded = 0;
        if ( QueryServiceConfigW(v4, &ServiceConfig, 0x200u, &pcbBytesNeeded) )
        {
          if ( ServiceConfig.dwStartType - 3 > 1 )
            v0 = 1;
        }
        else
        {
          GetLastError();
        }
      }
      CloseServiceHandle(v4);
    }
    else
    {
      GetLastError();
    }
    CloseServiceHandle(v2);
  }
  else
  {
    GetLastError();
  }
  return v0;
}

```

## disassembly

```asm
0x1800164c8  push    rbx
0x1800164ca  push    rbp
0x1800164cb  push    rsi
0x1800164cc  push    rdi
0x1800164cd  sub     rsp, 268h
0x1800164d4  mov     rax, cs:__security_cookie
0x1800164db  xor     rax, rsp
0x1800164de  mov     [rsp+288h+var_38], rax
0x1800164e6  xorps   xmm0, xmm0
0x1800164e9  xor     ebx, ebx
0x1800164eb  movups  xmmword ptr [rsp+288h+ServiceStatus.dwServiceType], xmm0
0x1800164f0  xor     edx, edx; lpDatabaseName
0x1800164f2  xor     ecx, ecx; lpMachineName
0x1800164f4  movups  xmmword ptr [rsp+288h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800164f9  lea     ebp, [rbx+1]
0x1800164fc  mov     r8d, ebp; dwDesiredAccess
0x1800164ff  call    cs:__imp_OpenSCManagerW
0x180016505  mov     rsi, rax
0x180016508  test    rax, rax
0x18001650b  jnz     short loc_180016518
0x18001650d  call    cs:__imp_GetLastError
0x180016513  jmp     loc_1800165A2
0x180016518  mov     r8d, 5; dwDesiredAccess
0x18001651e  lea     rdx, aSpooler; "Spooler"
0x180016525  mov     rcx, rsi; hSCManager
0x180016528  call    cs:__imp_OpenServiceW
0x18001652e  mov     rdi, rax
0x180016531  test    rax, rax
0x180016534  jnz     short loc_18001653E
0x180016536  call    cs:__imp_GetLastError
0x18001653c  jmp     short loc_180016599
0x18001653e  lea     rdx, [rsp+288h+ServiceStatus]; lpServiceStatus
0x180016543  mov     rcx, rdi; hService
0x180016546  call    cs:__imp_QueryServiceStatus
0x18001654c  test    eax, eax
0x18001654e  jz      short loc_18001655B
0x180016550  cmp     [rsp+288h+ServiceStatus.dwCurrentState], 4
0x180016555  jnz     short loc_18001655B
0x180016557  mov     ebx, ebp
0x180016559  jmp     short loc_180016590
0x18001655b  lea     r9, [rsp+288h+pcbBytesNeeded]; pcbBytesNeeded
0x180016560  mov     [rsp+288h+pcbBytesNeeded], ebx
0x180016564  mov     r8d, 200h; cbBufSize
0x18001656a  lea     rdx, [rsp+288h+ServiceConfig]; lpServiceConfig
0x18001656f  mov     rcx, rdi; hService
0x180016572  call    cs:__imp_QueryServiceConfigW
0x180016578  test    eax, eax
0x18001657a  jnz     short loc_180016584
0x18001657c  call    cs:__imp_GetLastError
0x180016582  jmp     short loc_180016590
0x180016584  mov     eax, [rsp+288h+ServiceConfig.dwStartType]
0x180016588  add     eax, 0FFFFFFFDh
0x18001658b  cmp     eax, ebp
0x18001658d  cmova   ebx, ebp
0x180016590  mov     rcx, rdi; hSCObject
0x180016593  call    cs:__imp_CloseServiceHandle
0x180016599  mov     rcx, rsi; hSCObject
0x18001659c  call    cs:__imp_CloseServiceHandle
0x1800165a2  mov     eax, ebx
0x1800165a4  mov     rcx, [rsp+288h+var_38]
0x1800165ac  xor     rcx, rsp; StackCookie
0x1800165af  call    __security_check_cookie
0x1800165b4  add     rsp, 268h
0x1800165bb  pop     rdi
0x1800165bc  pop     rsi
0x1800165bd  pop     rbp
0x1800165be  pop     rbx
0x1800165bf  retn
```
