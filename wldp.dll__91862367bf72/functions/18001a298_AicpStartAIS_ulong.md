# AicpStartAIS(ulong)

- ea: `0x18001a298`
- end: `0x18001a39c`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `260`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001a038`

## callees

- `0x18001a298`
- `0x180021ec0`
- `0x180022b9d`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a352`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a352`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a375`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a37e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a375`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a37e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001a30e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001a30e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001a2ef`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001a2ef`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001a2c5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001a2c5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001a335`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001a335`

## pseudocode

```c
__int64 __fastcall AicpStartAIS()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbp
  DWORD dwWin32ExitCode; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  int v5; // edi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"AppInfo", 0x14u);
    v4 = v3;
    if ( v3 )
    {
      if ( StartServiceW(v3, 0, 0) || (dwWin32ExitCode = GetLastError_0(), dwWin32ExitCode == 1056) )
      {
        v5 = 0;
        dwWin32ExitCode = 1460;
        while ( QueryServiceStatus(v4, &ServiceStatus) )
        {
          if ( ServiceStatus.dwCurrentState == 4 )
          {
            dwWin32ExitCode = 0;
            goto LABEL_16;
          }
          if ( ServiceStatus.dwCurrentState == 1 )
          {
            dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
            goto LABEL_16;
          }
          Sleep(0x1F4u);
          if ( (unsigned int)++v5 > 0xA )
            goto LABEL_16;
        }
        dwWin32ExitCode = GetLastError_0();
      }
LABEL_16:
      CloseServiceHandle(v4);
    }
    else
    {
      dwWin32ExitCode = GetLastError_0();
    }
    CloseServiceHandle(v1);
  }
  else
  {
    return GetLastError_0();
  }
  return dwWin32ExitCode;
}

```

## disassembly

```asm
0x18001a298  push    rbx
0x18001a29a  push    rbp
0x18001a29b  push    rsi
0x18001a29c  push    rdi
0x18001a29d  sub     rsp, 58h
0x18001a2a1  mov     rax, cs:__security_cookie
0x18001a2a8  xor     rax, rsp
0x18001a2ab  mov     [rsp+78h+var_38], rax
0x18001a2b0  xorps   xmm0, xmm0
0x18001a2b3  xor     edx, edx; lpDatabaseName
0x18001a2b5  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18001a2ba  xor     ecx, ecx; lpMachineName
0x18001a2bc  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001a2c1  lea     r8d, [rdx+1]; dwDesiredAccess
0x18001a2c5  call    cs:__imp_OpenSCManagerW
0x18001a2cb  mov     rbp, rax
0x18001a2ce  test    rax, rax
0x18001a2d1  jnz     short loc_18001A2DF
0x18001a2d3  call    GetLastError_0
0x18001a2d8  mov     ebx, eax
0x18001a2da  jmp     loc_18001A384
0x18001a2df  mov     r8d, 14h; dwDesiredAccess
0x18001a2e5  lea     rdx, ServiceName; "AppInfo"
0x18001a2ec  mov     rcx, rbp; hSCManager
0x18001a2ef  call    cs:__imp_OpenServiceW
0x18001a2f5  mov     rsi, rax
0x18001a2f8  test    rax, rax
0x18001a2fb  jnz     short loc_18001A306
0x18001a2fd  call    GetLastError_0
0x18001a302  mov     ebx, eax
0x18001a304  jmp     short loc_18001A37B
0x18001a306  xor     r8d, r8d; lpServiceArgVectors
0x18001a309  xor     edx, edx; dwNumServiceArgs
0x18001a30b  mov     rcx, rsi; hService
0x18001a30e  call    cs:__imp_StartServiceW
0x18001a314  test    eax, eax
0x18001a316  jnz     short loc_18001A326
0x18001a318  call    GetLastError_0
0x18001a31d  mov     ebx, eax
0x18001a31f  cmp     eax, 420h
0x18001a324  jnz     short loc_18001A372
0x18001a326  xor     edi, edi
0x18001a328  mov     ebx, 5B4h
0x18001a32d  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18001a332  mov     rcx, rsi; hService
0x18001a335  call    cs:__imp_QueryServiceStatus
0x18001a33b  test    eax, eax
0x18001a33d  jz      short loc_18001A36B
0x18001a33f  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x18001a344  jz      short loc_18001A367
0x18001a346  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x18001a34b  jz      short loc_18001A361
0x18001a34d  mov     ecx, 1F4h; dwMilliseconds
0x18001a352  call    cs:__imp_Sleep
0x18001a358  inc     edi
0x18001a35a  cmp     edi, 0Ah
0x18001a35d  jbe     short loc_18001A32D
0x18001a35f  jmp     short loc_18001A372
0x18001a361  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x18001a365  jmp     short loc_18001A372
0x18001a367  xor     ebx, ebx
0x18001a369  jmp     short loc_18001A372
0x18001a36b  call    GetLastError_0
0x18001a370  mov     ebx, eax
0x18001a372  mov     rcx, rsi; hSCObject
0x18001a375  call    cs:__imp_CloseServiceHandle
0x18001a37b  mov     rcx, rbp; hSCObject
0x18001a37e  call    cs:__imp_CloseServiceHandle
0x18001a384  mov     eax, ebx
0x18001a386  mov     rcx, [rsp+78h+var_38]
0x18001a38b  xor     rcx, rsp; StackCookie
0x18001a38e  call    __security_check_cookie
0x18001a393  add     rsp, 58h
0x18001a397  pop     rdi
0x18001a398  pop     rsi
0x18001a399  pop     rbp
0x18001a39a  pop     rbx
0x18001a39b  retn
```
