# IsNetworkServiceRunning

- ea: `0x18007d0a8`
- end: `0x18007d15e`
- name: `IsNetworkServiceRunning`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180052b2c`
- `0x180052cec`

## callees

- `0x18007d0a8`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007d12f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007d138`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007d12f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007d138`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007d0f6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007d0f6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007d0d8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007d0d8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18007d119`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18007d119`

## string_xrefs

- `0x18007d0cc`: `ServicesActive`

## pseudocode

```c
bool IsNetworkServiceRunning()
{
  bool v0; // di
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v0 = 0;
  v1 = OpenSCManagerW(0, L"ServicesActive", 0x20001u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"netprofm", 4u);
    v4 = v3;
    if ( v3 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v3, &ServiceStatus) )
        v0 = ServiceStatus.dwCurrentState == 4;
      CloseServiceHandle(v4);
    }
    CloseServiceHandle(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18007d0a8  mov     [rsp+arg_0], rbx
0x18007d0ad  mov     [rsp+arg_8], rsi
0x18007d0b2  push    rdi
0x18007d0b3  sub     rsp, 50h
0x18007d0b7  mov     rax, cs:__security_cookie
0x18007d0be  xor     rax, rsp
0x18007d0c1  mov     [rsp+58h+var_18], rax
0x18007d0c6  mov     r8d, 20001h; dwDesiredAccess
0x18007d0cc  lea     rdx, DatabaseName; "ServicesActive"
0x18007d0d3  xor     ecx, ecx; lpMachineName
0x18007d0d5  xor     dil, dil
0x18007d0d8  call    cs:__imp_OpenSCManagerW
0x18007d0de  mov     rbx, rax
0x18007d0e1  test    rax, rax
0x18007d0e4  jz      short loc_18007D13E
0x18007d0e6  mov     r8d, 4; dwDesiredAccess
0x18007d0ec  lea     rdx, aNetprofm; "netprofm"
0x18007d0f3  mov     rcx, rax; hSCManager
0x18007d0f6  call    cs:__imp_OpenServiceW
0x18007d0fc  mov     rsi, rax
0x18007d0ff  test    rax, rax
0x18007d102  jz      short loc_18007D135
0x18007d104  xorps   xmm0, xmm0
0x18007d107  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18007d10c  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18007d111  mov     rcx, rax; hService
0x18007d114  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18007d119  call    cs:__imp_QueryServiceStatus
0x18007d11f  test    eax, eax
0x18007d121  jz      short loc_18007D12C
0x18007d123  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18007d128  setz    dil
0x18007d12c  mov     rcx, rsi; hSCObject
0x18007d12f  call    cs:__imp_CloseServiceHandle
0x18007d135  mov     rcx, rbx; hSCObject
0x18007d138  call    cs:__imp_CloseServiceHandle
0x18007d13e  mov     al, dil
0x18007d141  mov     rcx, [rsp+58h+var_18]
0x18007d146  xor     rcx, rsp; StackCookie
0x18007d149  call    __security_check_cookie
0x18007d14e  mov     rbx, [rsp+58h+arg_0]
0x18007d153  mov     rsi, [rsp+58h+arg_8]
0x18007d158  add     rsp, 50h
0x18007d15c  pop     rdi
0x18007d15d  retn
```
