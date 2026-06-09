# InternetTime_IsW32TimeServiceRunning

- ea: `0x18001704c`
- end: `0x1800170f6`
- name: `InternetTime_IsW32TimeServiceRunning`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001b618`
- `0x18001d8c0`

## callees

- `0x18001704c`
- `0x180028f60`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180017090`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180017090`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800170c8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800170d1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800170c8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800170d1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180017074`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180017074`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800170b3`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800170b3`

## pseudocode

```c
__int64 InternetTime_IsW32TimeServiceRunning()
{
  unsigned int v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v0 = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"w32time", 4u);
    v4 = v3;
    if ( v3 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v3, &ServiceStatus) )
        LOBYTE(v0) = ServiceStatus.dwCurrentState == 4;
      CloseServiceHandle(v4);
    }
    CloseServiceHandle(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18001704c  mov     [rsp+arg_0], rbx
0x180017051  mov     [rsp+arg_8], rsi
0x180017056  push    rdi
0x180017057  sub     rsp, 50h
0x18001705b  mov     rax, cs:__security_cookie
0x180017062  xor     rax, rsp
0x180017065  mov     [rsp+58h+var_18], rax
0x18001706a  xor     ebx, ebx
0x18001706c  xor     edx, edx; lpDatabaseName
0x18001706e  xor     ecx, ecx; lpMachineName
0x180017070  lea     r8d, [rbx+1]; dwDesiredAccess
0x180017074  call    cs:__imp_OpenSCManagerW
0x18001707a  mov     rdi, rax
0x18001707d  test    rax, rax
0x180017080  jz      short loc_1800170D7
0x180017082  lea     r8d, [rbx+4]; dwDesiredAccess
0x180017086  mov     rcx, rax; hSCManager
0x180017089  lea     rdx, ServiceName; "w32time"
0x180017090  call    cs:__imp_OpenServiceW
0x180017096  mov     rsi, rax
0x180017099  test    rax, rax
0x18001709c  jz      short loc_1800170CE
0x18001709e  xorps   xmm0, xmm0
0x1800170a1  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800170a6  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800170ab  mov     rcx, rax; hService
0x1800170ae  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800170b3  call    cs:__imp_QueryServiceStatus
0x1800170b9  test    eax, eax
0x1800170bb  jz      short loc_1800170C5
0x1800170bd  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x1800170c2  setz    bl
0x1800170c5  mov     rcx, rsi; hSCObject
0x1800170c8  call    cs:__imp_CloseServiceHandle
0x1800170ce  mov     rcx, rdi; hSCObject
0x1800170d1  call    cs:__imp_CloseServiceHandle
0x1800170d7  mov     eax, ebx
0x1800170d9  mov     rcx, [rsp+58h+var_18]
0x1800170de  xor     rcx, rsp; StackCookie
0x1800170e1  call    __security_check_cookie
0x1800170e6  mov     rbx, [rsp+58h+arg_0]
0x1800170eb  mov     rsi, [rsp+58h+arg_8]
0x1800170f0  add     rsp, 50h
0x1800170f4  pop     rdi
0x1800170f5  retn
```
