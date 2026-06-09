# SsIsFirewallServiceRunning

- ea: `0x18002b3bc`
- end: `0x18002b51a`
- name: `SsIsFirewallServiceRunning`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002b5d8`

## callees

- `0x18001deb0`
- `0x18002b3bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b41d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b41d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b492`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b463`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b4ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b4ea`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b4d4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b4d4`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002b437`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002b488`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002b437`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002b488`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002b40f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002b40f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002b3e4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002b3e4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b4f3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b4fc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b4f3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b4fc`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b4be`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b4be`

## pseudocode

```c
__int64 SsIsFirewallServiceRunning()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbp
  DWORD LastError; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  struct _QUERY_SERVICE_CONFIGW *v5; // rax
  struct _QUERY_SERVICE_CONFIGW *v6; // rdi
  unsigned int v7; // ebx
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-58h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-50h] BYREF

  pcbBytesNeeded = 0;
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"MpsSvc", 5u);
    v4 = v3;
    if ( v3 )
    {
      if ( QueryServiceConfigW(v3, 0, 0, &pcbBytesNeeded) )
      {
        LastError = 1359;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError == 122 )
        {
          v5 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
          v6 = v5;
          if ( v5 )
          {
            if ( QueryServiceConfigW(v4, v5, pcbBytesNeeded, &pcbBytesNeeded) )
            {
              if ( v6->dwStartType != 4 )
              {
                v7 = 0;
                memset(&ServiceStatus, 0, sizeof(ServiceStatus));
                while ( v7 < 5 )
                {
                  if ( QueryServiceStatus(v4, &ServiceStatus) && ServiceStatus.dwCurrentState == 4 )
                  {
                    LastError = 0;
                    goto LABEL_20;
                  }
                  Sleep(0xC8u);
                  ++v7;
                }
              }
              LastError = 1077;
            }
            else
            {
              LastError = GetLastError();
            }
LABEL_20:
            LocalFree(v6);
          }
          else
          {
            LastError = 1450;
          }
        }
      }
      CloseServiceHandle(v4);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v1);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18002b3bc  push    rbx
0x18002b3be  push    rbp
0x18002b3bf  push    rsi
0x18002b3c0  push    rdi
0x18002b3c1  sub     rsp, 58h
0x18002b3c5  mov     rax, cs:__security_cookie
0x18002b3cc  xor     rax, rsp
0x18002b3cf  mov     [rsp+78h+var_30], rax
0x18002b3d4  xor     edx, edx; lpDatabaseName
0x18002b3d6  mov     [rsp+78h+pcbBytesNeeded], 0
0x18002b3de  xor     ecx, ecx; lpMachineName
0x18002b3e0  lea     r8d, [rdx+1]; dwDesiredAccess
0x18002b3e4  call    cs:__imp_OpenSCManagerW
0x18002b3ea  mov     rbp, rax
0x18002b3ed  test    rax, rax
0x18002b3f0  jnz     short loc_18002B3FF
0x18002b3f2  call    cs:__imp_GetLastError
0x18002b3f8  mov     ebx, eax
0x18002b3fa  jmp     loc_18002B502
0x18002b3ff  mov     r8d, 5; dwDesiredAccess
0x18002b405  lea     rdx, aMpssvc; "MpsSvc"
0x18002b40c  mov     rcx, rbp; hSCManager
0x18002b40f  call    cs:__imp_OpenServiceW
0x18002b415  mov     rsi, rax
0x18002b418  test    rax, rax
0x18002b41b  jnz     short loc_18002B42A
0x18002b41d  call    cs:__imp_GetLastError
0x18002b423  mov     ebx, eax
0x18002b425  jmp     loc_18002B4F9
0x18002b42a  lea     r9, [rsp+78h+pcbBytesNeeded]; pcbBytesNeeded
0x18002b42f  xor     r8d, r8d; cbBufSize
0x18002b432  xor     edx, edx; lpServiceConfig
0x18002b434  mov     rcx, rsi; hService
0x18002b437  call    cs:__imp_QueryServiceConfigW
0x18002b43d  test    eax, eax
0x18002b43f  jz      short loc_18002B44B
0x18002b441  mov     ebx, 54Fh
0x18002b446  jmp     loc_18002B4F0
0x18002b44b  call    cs:__imp_GetLastError
0x18002b451  mov     ebx, eax
0x18002b453  cmp     eax, 7Ah ; 'z'
0x18002b456  jnz     loc_18002B4F0
0x18002b45c  mov     edx, [rsp+78h+pcbBytesNeeded]; uBytes
0x18002b460  lea     ecx, [rax-3Ah]; uFlags
0x18002b463  call    cs:__imp_LocalAlloc
0x18002b469  mov     rdi, rax
0x18002b46c  test    rax, rax
0x18002b46f  jnz     short loc_18002B478
0x18002b471  mov     ebx, 5AAh
0x18002b476  jmp     short loc_18002B4F0
0x18002b478  mov     r8d, [rsp+78h+pcbBytesNeeded]; cbBufSize
0x18002b47d  lea     r9, [rsp+78h+pcbBytesNeeded]; pcbBytesNeeded
0x18002b482  mov     rdx, rdi; lpServiceConfig
0x18002b485  mov     rcx, rsi; hService
0x18002b488  call    cs:__imp_QueryServiceConfigW
0x18002b48e  test    eax, eax
0x18002b490  jnz     short loc_18002B49C
0x18002b492  call    cs:__imp_GetLastError
0x18002b498  mov     ebx, eax
0x18002b49a  jmp     short loc_18002B4E7
0x18002b49c  cmp     dword ptr [rdi+4], 4
0x18002b4a0  jz      short loc_18002B4E2
0x18002b4a2  xorps   xmm0, xmm0
0x18002b4a5  xor     ebx, ebx
0x18002b4a7  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18002b4ac  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002b4b1  cmp     ebx, 5
0x18002b4b4  jnb     short loc_18002B4E2
0x18002b4b6  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18002b4bb  mov     rcx, rsi; hService
0x18002b4be  call    cs:__imp_QueryServiceStatus
0x18002b4c4  test    eax, eax
0x18002b4c6  jz      short loc_18002B4CF
0x18002b4c8  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x18002b4cd  jz      short loc_18002B4DE
0x18002b4cf  mov     ecx, 0C8h; dwMilliseconds
0x18002b4d4  call    cs:__imp_Sleep
0x18002b4da  inc     ebx
0x18002b4dc  jmp     short loc_18002B4B1
0x18002b4de  xor     ebx, ebx
0x18002b4e0  jmp     short loc_18002B4E7
0x18002b4e2  mov     ebx, 435h
0x18002b4e7  mov     rcx, rdi; hMem
0x18002b4ea  call    cs:__imp_LocalFree
0x18002b4f0  mov     rcx, rsi; hSCObject
0x18002b4f3  call    cs:__imp_CloseServiceHandle
0x18002b4f9  mov     rcx, rbp; hSCObject
0x18002b4fc  call    cs:__imp_CloseServiceHandle
0x18002b502  mov     eax, ebx
0x18002b504  mov     rcx, [rsp+78h+var_30]
0x18002b509  xor     rcx, rsp; StackCookie
0x18002b50c  call    __security_check_cookie
0x18002b511  add     rsp, 58h
0x18002b515  pop     rdi
0x18002b516  pop     rsi
0x18002b517  pop     rbp
0x18002b518  pop     rbx
0x18002b519  retn
```
