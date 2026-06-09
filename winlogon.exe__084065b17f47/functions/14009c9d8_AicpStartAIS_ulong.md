# AicpStartAIS(ulong)

- ea: `0x14009c9d8`
- end: `0x14009cadb`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `259`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14009c5b8`

## callees

- `0x140053720`
- `0x140054845`
- `0x140054a09`
- `0x14009c9d8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14009ca05`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14009ca05`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009cab4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009cabd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009cab4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009cabd`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x14009ca4e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x14009ca4e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14009ca2f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14009ca2f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x14009ca75`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x14009ca75`

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
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

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
          Sleep_0(0x1F4u);
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
0x14009c9d8  push    rbx
0x14009c9da  push    rbp
0x14009c9db  push    rsi
0x14009c9dc  push    rdi
0x14009c9dd  sub     rsp, 58h
0x14009c9e1  mov     rax, cs:__security_cookie
0x14009c9e8  xor     rax, rsp
0x14009c9eb  mov     [rsp+78h+var_38], rax
0x14009c9f0  xorps   xmm0, xmm0
0x14009c9f3  xor     edx, edx; lpDatabaseName
0x14009c9f5  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x14009c9fa  xor     ecx, ecx; lpMachineName
0x14009c9fc  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x14009ca01  lea     r8d, [rdx+1]; dwDesiredAccess
0x14009ca05  call    cs:__imp_OpenSCManagerW
0x14009ca0b  mov     rbp, rax
0x14009ca0e  test    rax, rax
0x14009ca11  jnz     short loc_14009CA1F
0x14009ca13  call    GetLastError_0
0x14009ca18  mov     ebx, eax
0x14009ca1a  jmp     loc_14009CAC3
0x14009ca1f  mov     r8d, 14h; dwDesiredAccess
0x14009ca25  lea     rdx, aAppinfo; "AppInfo"
0x14009ca2c  mov     rcx, rbp; hSCManager
0x14009ca2f  call    cs:__imp_OpenServiceW
0x14009ca35  mov     rsi, rax
0x14009ca38  test    rax, rax
0x14009ca3b  jnz     short loc_14009CA46
0x14009ca3d  call    GetLastError_0
0x14009ca42  mov     ebx, eax
0x14009ca44  jmp     short loc_14009CABA
0x14009ca46  xor     r8d, r8d; lpServiceArgVectors
0x14009ca49  xor     edx, edx; dwNumServiceArgs
0x14009ca4b  mov     rcx, rsi; hService
0x14009ca4e  call    cs:__imp_StartServiceW
0x14009ca54  test    eax, eax
0x14009ca56  jnz     short loc_14009CA66
0x14009ca58  call    GetLastError_0
0x14009ca5d  mov     ebx, eax
0x14009ca5f  cmp     eax, 420h
0x14009ca64  jnz     short loc_14009CAB1
0x14009ca66  xor     edi, edi
0x14009ca68  mov     ebx, 5B4h
0x14009ca6d  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x14009ca72  mov     rcx, rsi; hService
0x14009ca75  call    cs:__imp_QueryServiceStatus
0x14009ca7b  test    eax, eax
0x14009ca7d  jz      short loc_14009CAAA
0x14009ca7f  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x14009ca84  jz      short loc_14009CAA6
0x14009ca86  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x14009ca8b  jz      short loc_14009CAA0
0x14009ca8d  mov     ecx, 1F4h; dwMilliseconds
0x14009ca92  call    Sleep_0
0x14009ca97  inc     edi
0x14009ca99  cmp     edi, 0Ah
0x14009ca9c  jbe     short loc_14009CA6D
0x14009ca9e  jmp     short loc_14009CAB1
0x14009caa0  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x14009caa4  jmp     short loc_14009CAB1
0x14009caa6  xor     ebx, ebx
0x14009caa8  jmp     short loc_14009CAB1
0x14009caaa  call    GetLastError_0
0x14009caaf  mov     ebx, eax
0x14009cab1  mov     rcx, rsi; hSCObject
0x14009cab4  call    cs:__imp_CloseServiceHandle
0x14009caba  mov     rcx, rbp; hSCObject
0x14009cabd  call    cs:__imp_CloseServiceHandle
0x14009cac3  mov     eax, ebx
0x14009cac5  mov     rcx, [rsp+78h+var_38]
0x14009caca  xor     rcx, rsp; StackCookie
0x14009cacd  call    __security_check_cookie
0x14009cad2  add     rsp, 58h
0x14009cad6  pop     rdi
0x14009cad7  pop     rsi
0x14009cad8  pop     rbp
0x14009cad9  pop     rbx
0x14009cada  retn
```
