# CUtils::StartServiceW(ushort const *,ulong,int)

- ea: `0x180031908`
- end: `0x180031a66`
- name: `?StartServiceW@CUtils@@SAJPEBGKH@Z`
- size: `350`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18004c2b8`

## callees

- `0x18000a210`
- `0x180031908`
- `0x1800321f0`
- `0x1800330c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a00`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031a30`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031a39`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031a30`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180031a39`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180031954`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180031954`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800319f6`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800319f6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003199c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003199c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800319dd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800319dd`

## string_xrefs

- `0x1800319c2`: `OpenService failed: 0x%x`
- `0x18003197a`: `OpenSCManager failed: 0x%x`
- `0x180031a18`: `StartService failed: 0x%x`

## pseudocode

```c
__int64 __fastcall CUtils::StartServiceW(LPCWSTR lpServiceName)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  signed int v4; // eax
  unsigned int v5; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rdi
  signed int v8; // eax
  signed int LastError; // eax
  _BYTE v11[80]; // [rsp+20h] [rbp-88h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  memset_0(v11, 0, sizeof(v11));
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v6 = OpenServiceW(v2, lpServiceName, 0x15u);
    v7 = v6;
    if ( v6 )
    {
      if ( QueryServiceStatus(v6, &ServiceStatus) && ServiceStatus.dwCurrentState == 4 || StartServiceW(v7, 0, 0) )
      {
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(4, "StartService failed: 0x%x", v5);
      }
      CloseServiceHandle(v7);
    }
    else
    {
      v8 = GetLastError();
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      _DbgPrintMessage(8, "OpenService failed: 0x%x", v5);
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    _DbgPrintMessage(8, "OpenSCManager failed: 0x%x", v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180031908  mov     [rsp+arg_8], rbx
0x18003190d  mov     [rsp+arg_10], rsi
0x180031912  push    rdi
0x180031913  sub     rsp, 0A0h
0x18003191a  mov     rax, cs:__security_cookie
0x180031921  xor     rax, rsp
0x180031924  mov     [rsp+0A8h+var_18], rax
0x18003192c  xorps   xmm0, xmm0
0x18003192f  xor     edx, edx; Val
0x180031931  mov     rbx, rcx
0x180031934  lea     rcx, [rsp+0A8h+var_88]; void *
0x180031939  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x18003193e  lea     r8d, [rdx+50h]; Size
0x180031942  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x180031947  call    memset_0
0x18003194c  xor     edx, edx; lpDatabaseName
0x18003194e  xor     ecx, ecx; lpMachineName
0x180031950  lea     r8d, [rdx+1]; dwDesiredAccess
0x180031954  call    cs:__imp_OpenSCManagerW
0x18003195a  mov     rsi, rax
0x18003195d  test    rax, rax
0x180031960  jnz     short loc_180031990
0x180031962  call    cs:__imp_GetLastError
0x180031968  mov     ebx, eax
0x18003196a  test    eax, eax
0x18003196c  jle     short loc_180031977
0x18003196e  movzx   ebx, ax
0x180031971  or      ebx, 80070000h
0x180031977  mov     r8d, ebx
0x18003197a  lea     rdx, aOpenscmanagerF; "OpenSCManager failed: 0x%x"
0x180031981  mov     ecx, 8; int
0x180031986  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003198b  jmp     loc_180031A3F
0x180031990  mov     r8d, 15h; dwDesiredAccess
0x180031996  mov     rdx, rbx; lpServiceName
0x180031999  mov     rcx, rsi; hSCManager
0x18003199c  call    cs:__imp_OpenServiceW
0x1800319a2  mov     rdi, rax
0x1800319a5  test    rax, rax
0x1800319a8  jnz     short loc_1800319D5
0x1800319aa  call    cs:__imp_GetLastError
0x1800319b0  mov     ebx, eax
0x1800319b2  test    eax, eax
0x1800319b4  jle     short loc_1800319BF
0x1800319b6  movzx   ebx, ax
0x1800319b9  or      ebx, 80070000h
0x1800319bf  mov     r8d, ebx
0x1800319c2  lea     rdx, aOpenserviceFai; "OpenService failed: 0x%x"
0x1800319c9  mov     ecx, 8; int
0x1800319ce  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800319d3  jmp     short loc_180031A36
0x1800319d5  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1800319da  mov     rcx, rdi; hService
0x1800319dd  call    cs:__imp_QueryServiceStatus
0x1800319e3  test    eax, eax
0x1800319e5  jz      short loc_1800319EE
0x1800319e7  cmp     [rsp+0A8h+ServiceStatus.dwCurrentState], 4
0x1800319ec  jz      short loc_180031A2B
0x1800319ee  xor     r8d, r8d; lpServiceArgVectors
0x1800319f1  xor     edx, edx; dwNumServiceArgs
0x1800319f3  mov     rcx, rdi; hService
0x1800319f6  call    cs:__imp_StartServiceW
0x1800319fc  test    eax, eax
0x1800319fe  jnz     short loc_180031A2B
0x180031a00  call    cs:__imp_GetLastError
0x180031a06  mov     ebx, eax
0x180031a08  test    eax, eax
0x180031a0a  jle     short loc_180031A15
0x180031a0c  movzx   ebx, ax
0x180031a0f  or      ebx, 80070000h
0x180031a15  mov     r8d, ebx
0x180031a18  lea     rdx, aStartserviceFa; "StartService failed: 0x%x"
0x180031a1f  mov     ecx, 4; int
0x180031a24  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031a29  jmp     short loc_180031A2D
0x180031a2b  xor     ebx, ebx
0x180031a2d  mov     rcx, rdi; hSCObject
0x180031a30  call    cs:__imp_CloseServiceHandle
0x180031a36  mov     rcx, rsi; hSCObject
0x180031a39  call    cs:__imp_CloseServiceHandle
0x180031a3f  mov     eax, ebx
0x180031a41  mov     rcx, [rsp+0A8h+var_18]
0x180031a49  xor     rcx, rsp; StackCookie
0x180031a4c  call    __security_check_cookie
0x180031a51  lea     r11, [rsp+0A8h+var_8]
0x180031a59  mov     rbx, [r11+18h]
0x180031a5d  mov     rsi, [r11+20h]
0x180031a61  mov     rsp, r11
0x180031a64  pop     rdi
0x180031a65  retn
```
