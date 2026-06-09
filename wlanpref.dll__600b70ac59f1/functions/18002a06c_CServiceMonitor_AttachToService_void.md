# CServiceMonitor::AttachToService(void)

- ea: `0x18002a06c`
- end: `0x18002a175`
- name: `?AttachToService@CServiceMonitor@@IEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002c558`

## callees

- `0x18002a06c`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a133`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a0ce`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a0ce`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a09c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a09c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a0f8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a0f8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a125`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a125`

## string_xrefs

- `0x18002a08d`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CServiceMonitor::AttachToService(const WCHAR *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  signed int v4; // eax
  signed int v5; // ebx
  SC_HANDLE v6; // rax
  signed int LastError; // eax
  SC_HANDLE v8; // rcx
  signed int v9; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = 0;
    v6 = OpenServiceW(v2, this + 4, 4u);
    *((_QWORD *)this + 67) = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  if ( v5 >= 0 )
  {
    v8 = (SC_HANDLE)*((_QWORD *)this + 67);
    v5 = -2147467259;
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( v8 )
    {
      if ( QueryServiceStatus(v8, &ServiceStatus) )
      {
        v5 = 0;
LABEL_15:
        *((_DWORD *)this + 131) = ServiceStatus.dwCurrentState;
        return (unsigned int)v5;
      }
      v9 = GetLastError();
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
    }
    if ( v5 >= 0 )
      goto LABEL_15;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a06c  mov     [rsp+arg_8], rbx
0x18002a071  mov     [rsp+arg_10], rbp
0x18002a076  push    rsi
0x18002a077  sub     rsp, 50h
0x18002a07b  mov     rax, cs:__security_cookie
0x18002a082  xor     rax, rsp
0x18002a085  mov     [rsp+58h+var_18], rax
0x18002a08a  mov     rsi, rcx
0x18002a08d  lea     rdx, DatabaseName; "ServicesActive"
0x18002a094  xor     ecx, ecx; lpMachineName
0x18002a096  mov     r8d, 1; dwDesiredAccess
0x18002a09c  call    cs:__imp_OpenSCManagerW
0x18002a0a2  mov     rbp, rax
0x18002a0a5  test    rax, rax
0x18002a0a8  jnz     short loc_18002A0C1
0x18002a0aa  call    cs:__imp_GetLastError
0x18002a0b0  mov     ebx, eax
0x18002a0b2  test    eax, eax
0x18002a0b4  jle     short loc_18002A0FE
0x18002a0b6  movzx   ebx, ax
0x18002a0b9  or      ebx, 80070000h
0x18002a0bf  jmp     short loc_18002A0FE
0x18002a0c1  xor     ebx, ebx
0x18002a0c3  lea     rdx, [rsi+8]; lpServiceName
0x18002a0c7  mov     rcx, rbp; hSCManager
0x18002a0ca  lea     r8d, [rbx+4]; dwDesiredAccess
0x18002a0ce  call    cs:__imp_OpenServiceW
0x18002a0d4  mov     [rsi+218h], rax
0x18002a0db  test    rax, rax
0x18002a0de  jnz     short loc_18002A0F5
0x18002a0e0  call    cs:__imp_GetLastError
0x18002a0e6  mov     ebx, eax
0x18002a0e8  test    eax, eax
0x18002a0ea  jle     short loc_18002A0F5
0x18002a0ec  movzx   ebx, ax
0x18002a0ef  or      ebx, 80070000h
0x18002a0f5  mov     rcx, rbp; hSCObject
0x18002a0f8  call    cs:__imp_CloseServiceHandle
0x18002a0fe  test    ebx, ebx
0x18002a100  js      short loc_18002A156
0x18002a102  mov     rcx, [rsi+218h]; hService
0x18002a109  xorps   xmm0, xmm0
0x18002a10c  mov     ebx, 80004005h
0x18002a111  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18002a116  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002a11b  test    rcx, rcx
0x18002a11e  jz      short loc_18002A148
0x18002a120  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002a125  call    cs:__imp_QueryServiceStatus
0x18002a12b  test    eax, eax
0x18002a12d  jz      short loc_18002A133
0x18002a12f  xor     ebx, ebx
0x18002a131  jmp     short loc_18002A14C
0x18002a133  call    cs:__imp_GetLastError
0x18002a139  mov     ebx, eax
0x18002a13b  test    eax, eax
0x18002a13d  jle     short loc_18002A148
0x18002a13f  movzx   ebx, ax
0x18002a142  or      ebx, 80070000h
0x18002a148  test    ebx, ebx
0x18002a14a  js      short loc_18002A156
0x18002a14c  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x18002a150  mov     [rsi+20Ch], eax
0x18002a156  mov     eax, ebx
0x18002a158  mov     rcx, [rsp+58h+var_18]
0x18002a15d  xor     rcx, rsp; StackCookie
0x18002a160  call    __security_check_cookie
0x18002a165  mov     rbx, [rsp+58h+arg_8]
0x18002a16a  mov     rbp, [rsp+58h+arg_10]
0x18002a16f  add     rsp, 50h
0x18002a173  pop     rsi
0x18002a174  retn
```
