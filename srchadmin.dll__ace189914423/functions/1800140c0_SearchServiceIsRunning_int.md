# SearchServiceIsRunning(int *)

- ea: `0x1800140c0`
- end: `0x18001418a`
- name: `?SearchServiceIsRunning@@YAJPEAH@Z`
- size: `202`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800134b0`

## callees

- `0x180005cc0`
- `0x18000d4dc`
- `0x1800140c0`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014150`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014162`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014150`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014162`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800140ed`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800140ed`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180014109`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180014109`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001412c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001412c`

## string_xrefs

- `0x1800140db`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall SearchServiceIsRunning(int *a1)
{
  unsigned int Error; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  Error = 0;
  *a1 = 0;
  v3 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, L"WSearch", 4u);
    v6 = v5;
    if ( v5 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v5, &ServiceStatus) && (ServiceStatus.dwCurrentState & 4) != 0 )
        *a1 = 1;
      else
        Error = ResultFromKnownLastError();
      CloseServiceHandle(v6);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    CloseServiceHandle(v4);
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return Error;
}

```

## disassembly

```asm
0x1800140c0  push    rbx
0x1800140c2  push    rsi
0x1800140c3  push    rdi
0x1800140c4  push    r14
0x1800140c6  sub     rsp, 58h
0x1800140ca  mov     rax, cs:__security_cookie
0x1800140d1  xor     rax, rsp
0x1800140d4  mov     [rsp+78h+var_38], rax
0x1800140d9  xor     ebx, ebx
0x1800140db  lea     rdx, DatabaseName; "ServicesActive"
0x1800140e2  mov     r14, rcx
0x1800140e5  mov     [rcx], ebx
0x1800140e7  xor     ecx, ecx; lpMachineName
0x1800140e9  lea     r8d, [rbx+1]; dwDesiredAccess
0x1800140ed  call    cs:__imp_OpenSCManagerW
0x1800140f3  mov     rsi, rax
0x1800140f6  test    rax, rax
0x1800140f9  jz      short loc_18001416A
0x1800140fb  lea     r8d, [rbx+4]; dwDesiredAccess
0x1800140ff  mov     rcx, rax; hSCManager
0x180014102  lea     rdx, ServiceName; "WSearch"
0x180014109  call    cs:__imp_OpenServiceW
0x18001410f  mov     rdi, rax
0x180014112  test    rax, rax
0x180014115  jz      short loc_180014158
0x180014117  xorps   xmm0, xmm0
0x18001411a  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18001411f  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180014124  mov     rcx, rax; hService
0x180014127  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001412c  call    cs:__imp_QueryServiceStatus
0x180014132  test    eax, eax
0x180014134  jz      short loc_180014146
0x180014136  test    byte ptr [rsp+78h+ServiceStatus.dwCurrentState], 4
0x18001413b  jz      short loc_180014146
0x18001413d  mov     dword ptr [r14], 1
0x180014144  jmp     short loc_18001414D
0x180014146  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001414b  mov     ebx, eax
0x18001414d  mov     rcx, rdi; hSCObject
0x180014150  call    cs:__imp_CloseServiceHandle
0x180014156  jmp     short loc_18001415F
0x180014158  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001415d  mov     ebx, eax
0x18001415f  mov     rcx, rsi; hSCObject
0x180014162  call    cs:__imp_CloseServiceHandle
0x180014168  jmp     short loc_180014171
0x18001416a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001416f  mov     ebx, eax
0x180014171  mov     eax, ebx
0x180014173  mov     rcx, [rsp+78h+var_38]
0x180014178  xor     rcx, rsp; StackCookie
0x18001417b  call    __security_check_cookie
0x180014180  add     rsp, 58h
0x180014184  pop     r14
0x180014186  pop     rdi
0x180014187  pop     rsi
0x180014188  pop     rbx
0x180014189  retn
```
