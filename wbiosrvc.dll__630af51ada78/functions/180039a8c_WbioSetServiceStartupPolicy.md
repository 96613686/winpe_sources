# WbioSetServiceStartupPolicy

- ea: `0x180039a8c`
- end: `0x180039c1e`
- name: `WbioSetServiceStartupPolicy`
- size: `402`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800447b0`
- `0x180045d10`

## callees

- `0x180034914`
- `0x180039a8c`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bd0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039b07`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039b07`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180039be8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180039bf1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180039be8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180039bf1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180039acb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180039acb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180039b3b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180039b3b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180039bc6`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180039bc6`

## pseudocode

```c
__int64 WbioSetServiceStartupPolicy()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  signed int v2; // eax
  signed int ServiceStartType; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  signed int v6; // eax
  signed int LastError; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-30h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"wbiosrvc", 7u);
    v5 = v4;
    if ( v4 )
    {
      if ( !QueryServiceStatus(v4, &ServiceStatus)
        || (ServiceStartType = 0, ServiceStatus.dwCurrentState != 2)
        && (ServiceStartType = GetServiceStartType(v5), ServiceStartType >= 0)
        && !ChangeServiceConfigW(v5, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        LastError = GetLastError();
        ServiceStartType = LastError;
        if ( LastError > 0 )
          ServiceStartType = (unsigned __int16)LastError | 0x80070000;
      }
      CloseServiceHandle(v5);
    }
    else
    {
      v6 = GetLastError();
      ServiceStartType = v6;
      if ( v6 > 0 )
        ServiceStartType = (unsigned __int16)v6 | 0x80070000;
    }
    CloseServiceHandle(v1);
  }
  else
  {
    v2 = GetLastError();
    ServiceStartType = v2;
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  return (unsigned int)ServiceStartType;
}

```

## disassembly

```asm
0x180039a8c  mov     [rsp+arg_0], rbx
0x180039a91  mov     [rsp+arg_8], rsi
0x180039a96  push    rdi
0x180039a97  sub     rsp, 90h
0x180039a9e  mov     rax, cs:__security_cookie
0x180039aa5  xor     rax, rsp
0x180039aa8  mov     [rsp+98h+var_10], rax
0x180039ab0  xor     eax, eax
0x180039ab2  xorps   xmm0, xmm0
0x180039ab5  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x180039aba  xor     edx, edx; lpDatabaseName
0x180039abc  mov     [rsp+98h+var_38], eax
0x180039ac0  xor     ecx, ecx; lpMachineName
0x180039ac2  lea     r8d, [rax+1]; dwDesiredAccess
0x180039ac6  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x180039acb  call    cs:__imp_OpenSCManagerW
0x180039ad1  mov     rsi, rax
0x180039ad4  test    rax, rax
0x180039ad7  jnz     short loc_180039AF7
0x180039ad9  call    cs:__imp_GetLastError
0x180039adf  mov     ebx, eax
0x180039ae1  test    eax, eax
0x180039ae3  jle     loc_180039BF7
0x180039ae9  movzx   ebx, ax
0x180039aec  or      ebx, 80070000h
0x180039af2  jmp     loc_180039BF7
0x180039af7  mov     r8d, 7; dwDesiredAccess
0x180039afd  lea     rdx, ServiceName; "wbiosrvc"
0x180039b04  mov     rcx, rsi; hSCManager
0x180039b07  call    cs:__imp_OpenServiceW
0x180039b0d  mov     rdi, rax
0x180039b10  test    rax, rax
0x180039b13  jnz     short loc_180039B33
0x180039b15  call    cs:__imp_GetLastError
0x180039b1b  mov     ebx, eax
0x180039b1d  test    eax, eax
0x180039b1f  jle     loc_180039BEE
0x180039b25  movzx   ebx, ax
0x180039b28  or      ebx, 80070000h
0x180039b2e  jmp     loc_180039BEE
0x180039b33  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x180039b38  mov     rcx, rdi; hService
0x180039b3b  call    cs:__imp_QueryServiceStatus
0x180039b41  test    eax, eax
0x180039b43  jz      loc_180039BD0
0x180039b49  xor     ebx, ebx
0x180039b4b  cmp     [rsp+98h+ServiceStatus.dwCurrentState], 2
0x180039b50  jz      loc_180039BE5
0x180039b56  lea     rdx, [rsp+98h+var_38]
0x180039b5b  mov     rcx, rdi; hService
0x180039b5e  call    _GetServiceStartType
0x180039b63  mov     ebx, eax
0x180039b65  test    eax, eax
0x180039b67  js      short loc_180039BE5
0x180039b69  mov     ecx, [rsp+98h+var_38]
0x180039b6d  add     ecx, 0FFFFFFFEh
0x180039b70  test    ecx, 0FFFFFFFDh
0x180039b76  jz      short loc_180039BE5
0x180039b78  mov     [rsp+98h+lpDisplayName], 0; lpDisplayName
0x180039b81  or      edx, 0FFFFFFFFh; dwServiceType
0x180039b84  mov     [rsp+98h+lpPassword], 0; lpPassword
0x180039b8d  mov     r9d, edx; dwErrorControl
0x180039b90  mov     [rsp+98h+lpServiceStartName], 0; lpServiceStartName
0x180039b99  mov     r8d, 2; dwStartType
0x180039b9f  mov     [rsp+98h+lpDependencies], 0; lpDependencies
0x180039ba8  mov     rcx, rdi; hService
0x180039bab  mov     [rsp+98h+lpdwTagId], 0; lpdwTagId
0x180039bb4  mov     [rsp+98h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180039bbd  mov     [rsp+98h+lpBinaryPathName], 0; lpBinaryPathName
0x180039bc6  call    cs:__imp_ChangeServiceConfigW
0x180039bcc  test    eax, eax
0x180039bce  jnz     short loc_180039BE5
0x180039bd0  call    cs:__imp_GetLastError
0x180039bd6  mov     ebx, eax
0x180039bd8  test    eax, eax
0x180039bda  jle     short loc_180039BE5
0x180039bdc  movzx   ebx, ax
0x180039bdf  or      ebx, 80070000h
0x180039be5  mov     rcx, rdi; hSCObject
0x180039be8  call    cs:__imp_CloseServiceHandle
0x180039bee  mov     rcx, rsi; hSCObject
0x180039bf1  call    cs:__imp_CloseServiceHandle
0x180039bf7  mov     eax, ebx
0x180039bf9  mov     rcx, [rsp+98h+var_10]
0x180039c01  xor     rcx, rsp; StackCookie
0x180039c04  call    __security_check_cookie
0x180039c09  lea     r11, [rsp+98h+var_8]
0x180039c11  mov     rbx, [r11+10h]
0x180039c15  mov     rsi, [r11+18h]
0x180039c19  mov     rsp, r11
0x180039c1c  pop     rdi
0x180039c1d  retn
```
