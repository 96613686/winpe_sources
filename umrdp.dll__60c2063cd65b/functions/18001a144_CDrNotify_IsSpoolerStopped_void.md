# CDrNotify::IsSpoolerStopped(void)

- ea: `0x18001a144`
- end: `0x18001a219`
- name: `?IsSpoolerStopped@CDrNotify@@IEAAHXZ`
- size: `213`
- prototype: `__int64 __fastcall(CDrNotify *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800072f0`

## callees

- `0x18001a144`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1e2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001a19b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001a19b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a1b4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a1f0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a1b4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a1f0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001a172`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001a172`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001a1d8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001a1d8`

## string_xrefs

- `0x18001a161`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CDrNotify::IsSpoolerStopped(CDrNotify *this)
{
  unsigned int v1; // edi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  SC_HANDLE v4; // rbx
  DWORD LastError; // esi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  v1 = 1;
  v2 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v3 = v2;
  if ( v2 )
  {
    LastError = 0;
    v4 = OpenServiceW(v2, L"Spooler", 0x80000000);
    if ( !v4 )
      LastError = GetLastError();
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = 0;
    LastError = GetLastError();
  }
  if ( !LastError )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !v4 )
      return v1;
    if ( QueryServiceStatus(v4, &ServiceStatus) )
    {
      if ( ServiceStatus.dwCurrentState == 4 )
      {
        v1 = 0;
        goto LABEL_11;
      }
    }
    else
    {
      GetLastError();
    }
  }
  if ( v4 )
LABEL_11:
    CloseServiceHandle(v4);
  return v1;
}

```

## disassembly

```asm
0x18001a144  push    rbx
0x18001a146  push    rbp
0x18001a147  push    rsi
0x18001a148  push    rdi
0x18001a149  sub     rsp, 58h
0x18001a14d  mov     rax, cs:__security_cookie
0x18001a154  xor     rax, rsp
0x18001a157  mov     [rsp+78h+var_38], rax
0x18001a15c  mov     ebx, 80000000h
0x18001a161  lea     rdx, DatabaseName; "ServicesActive"
0x18001a168  mov     r8d, ebx; dwDesiredAccess
0x18001a16b  xor     ecx, ecx; lpMachineName
0x18001a16d  mov     edi, 1
0x18001a172  call    cs:__imp_OpenSCManagerW
0x18001a178  mov     rbp, rax
0x18001a17b  test    rax, rax
0x18001a17e  jnz     short loc_18001A18C
0x18001a180  xor     ebx, ebx
0x18001a182  call    cs:__imp_GetLastError
0x18001a188  mov     esi, eax
0x18001a18a  jmp     short loc_18001A1BA
0x18001a18c  mov     r8d, ebx; dwDesiredAccess
0x18001a18f  lea     rdx, aSpooler; "Spooler"
0x18001a196  mov     rcx, rbp; hSCManager
0x18001a199  xor     esi, esi
0x18001a19b  call    cs:__imp_OpenServiceW
0x18001a1a1  mov     rbx, rax
0x18001a1a4  test    rax, rax
0x18001a1a7  jnz     short loc_18001A1B1
0x18001a1a9  call    cs:__imp_GetLastError
0x18001a1af  mov     esi, eax
0x18001a1b1  mov     rcx, rbp; hSCObject
0x18001a1b4  call    cs:__imp_CloseServiceHandle
0x18001a1ba  test    esi, esi
0x18001a1bc  jnz     short loc_18001A1E8
0x18001a1be  xorps   xmm0, xmm0
0x18001a1c1  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18001a1c6  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001a1cb  test    rbx, rbx
0x18001a1ce  jz      short loc_18001A1F6
0x18001a1d0  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18001a1d5  mov     rcx, rbx; hService
0x18001a1d8  call    cs:__imp_QueryServiceStatus
0x18001a1de  test    eax, eax
0x18001a1e0  jnz     short loc_18001A20E
0x18001a1e2  call    cs:__imp_GetLastError
0x18001a1e8  test    rbx, rbx
0x18001a1eb  jz      short loc_18001A1F6
0x18001a1ed  mov     rcx, rbx; hSCObject
0x18001a1f0  call    cs:__imp_CloseServiceHandle
0x18001a1f6  mov     eax, edi
0x18001a1f8  mov     rcx, [rsp+78h+var_38]
0x18001a1fd  xor     rcx, rsp; StackCookie
0x18001a200  call    __security_check_cookie
0x18001a205  add     rsp, 58h
0x18001a209  pop     rdi
0x18001a20a  pop     rsi
0x18001a20b  pop     rbp
0x18001a20c  pop     rbx
0x18001a20d  retn
0x18001a20e  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x18001a213  jnz     short loc_18001A1E8
0x18001a215  xor     edi, edi
0x18001a217  jmp     short loc_18001A1ED
```
