# CUtils::StartServiceW(ushort const *,ulong,int)

- ea: `0x1800335d8`
- end: `0x18003376d`
- name: `?StartServiceW@CUtils@@SAJPEBGKH@Z`
- size: `405`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18004e8e8`

## callees

- `0x180009940`
- `0x1800335d8`
- `0x180033f60`
- `0x180034e64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003368c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003368c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336f4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003372a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180033739`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003372a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180033739`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180033624`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180033624`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800336e4`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800336e4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180033678`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180033678`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800336c5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800336c5`

## string_xrefs

- `0x1800336aa`: `OpenService failed: 0x%x`
- `0x180033656`: `OpenSCManager failed: 0x%x`
- `0x180033712`: `StartService failed: 0x%x`

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
0x1800335d8  mov     [rsp+arg_8], rbx
0x1800335dd  mov     [rsp+arg_10], rsi
0x1800335e2  push    rdi
0x1800335e3  sub     rsp, 0A0h
0x1800335ea  mov     rax, cs:__security_cookie
0x1800335f1  xor     rax, rsp
0x1800335f4  mov     [rsp+0A8h+var_18], rax
0x1800335fc  xorps   xmm0, xmm0
0x1800335ff  xor     edx, edx; Val
0x180033601  mov     rbx, rcx
0x180033604  lea     rcx, [rsp+0A8h+var_88]; void *
0x180033609  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x18003360e  lea     r8d, [rdx+50h]; Size
0x180033612  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x180033617  call    memset_0
0x18003361c  xor     edx, edx; lpDatabaseName
0x18003361e  xor     ecx, ecx; lpMachineName
0x180033620  lea     r8d, [rdx+1]; dwDesiredAccess
0x180033624  call    cs:__imp_OpenSCManagerW
0x18003362b  nop     dword ptr [rax+rax+00h]
0x180033630  mov     rsi, rax
0x180033633  test    rax, rax
0x180033636  jnz     short loc_18003366C
0x180033638  call    cs:__imp_GetLastError
0x18003363f  nop     dword ptr [rax+rax+00h]
0x180033644  mov     ebx, eax
0x180033646  test    eax, eax
0x180033648  jle     short loc_180033653
0x18003364a  movzx   ebx, ax
0x18003364d  or      ebx, 80070000h
0x180033653  mov     r8d, ebx
0x180033656  lea     rdx, aOpenscmanagerF; "OpenSCManager failed: 0x%x"
0x18003365d  mov     ecx, 8; int
0x180033662  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180033667  jmp     loc_180033745
0x18003366c  mov     r8d, 15h; dwDesiredAccess
0x180033672  mov     rdx, rbx; lpServiceName
0x180033675  mov     rcx, rsi; hSCManager
0x180033678  call    cs:__imp_OpenServiceW
0x18003367f  nop     dword ptr [rax+rax+00h]
0x180033684  mov     rdi, rax
0x180033687  test    rax, rax
0x18003368a  jnz     short loc_1800336BD
0x18003368c  call    cs:__imp_GetLastError
0x180033693  nop     dword ptr [rax+rax+00h]
0x180033698  mov     ebx, eax
0x18003369a  test    eax, eax
0x18003369c  jle     short loc_1800336A7
0x18003369e  movzx   ebx, ax
0x1800336a1  or      ebx, 80070000h
0x1800336a7  mov     r8d, ebx
0x1800336aa  lea     rdx, aOpenserviceFai; "OpenService failed: 0x%x"
0x1800336b1  mov     ecx, 8; int
0x1800336b6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800336bb  jmp     short loc_180033736
0x1800336bd  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1800336c2  mov     rcx, rdi; hService
0x1800336c5  call    cs:__imp_QueryServiceStatus
0x1800336cc  nop     dword ptr [rax+rax+00h]
0x1800336d1  test    eax, eax
0x1800336d3  jz      short loc_1800336DC
0x1800336d5  cmp     [rsp+0A8h+ServiceStatus.dwCurrentState], 4
0x1800336da  jz      short loc_180033725
0x1800336dc  xor     r8d, r8d; lpServiceArgVectors
0x1800336df  xor     edx, edx; dwNumServiceArgs
0x1800336e1  mov     rcx, rdi; hService
0x1800336e4  call    cs:__imp_StartServiceW
0x1800336eb  nop     dword ptr [rax+rax+00h]
0x1800336f0  test    eax, eax
0x1800336f2  jnz     short loc_180033725
0x1800336f4  call    cs:__imp_GetLastError
0x1800336fb  nop     dword ptr [rax+rax+00h]
0x180033700  mov     ebx, eax
0x180033702  test    eax, eax
0x180033704  jle     short loc_18003370F
0x180033706  movzx   ebx, ax
0x180033709  or      ebx, 80070000h
0x18003370f  mov     r8d, ebx
0x180033712  lea     rdx, aStartserviceFa; "StartService failed: 0x%x"
0x180033719  mov     ecx, 4; int
0x18003371e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180033723  jmp     short loc_180033727
0x180033725  xor     ebx, ebx
0x180033727  mov     rcx, rdi; hSCObject
0x18003372a  call    cs:__imp_CloseServiceHandle
0x180033731  nop     dword ptr [rax+rax+00h]
0x180033736  mov     rcx, rsi; hSCObject
0x180033739  call    cs:__imp_CloseServiceHandle
0x180033740  nop     dword ptr [rax+rax+00h]
0x180033745  mov     eax, ebx
0x180033747  mov     rcx, [rsp+0A8h+var_18]
0x18003374f  xor     rcx, rsp; StackCookie
0x180033752  call    __security_check_cookie
0x180033757  lea     r11, [rsp+0A8h+var_8]
0x18003375f  mov     rbx, [r11+18h]
0x180033763  mov     rsi, [r11+20h]
0x180033767  mov     rsp, r11
0x18003376a  pop     rdi
0x18003376b  retn
```
