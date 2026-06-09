# CWerCplSupportService::_SetServiceStatus(ulong,ulong)

- ea: `0x180007c9c`
- end: `0x180007d19`
- name: `?_SetServiceStatus@CWerCplSupportService@@AEAAXKK@Z`
- size: `125`
- prototype: `void __fastcall(CWerCplSupportService *__hidden this, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007624`
- `0x1800076c8`
- `0x18000773c`
- `0x180007b00`
- `0x180007b9c`

## callees

- `0x180007c9c`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007d01`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007d01`

## pseudocode

```c
void __fastcall CWerCplSupportService::_SetServiceStatus(CWerCplSupportService *this, DWORD a2)
{
  int v3; // ecx
  SERVICE_STATUS_HANDLE v4; // rcx
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  *((_DWORD *)this + 10) = a2;
  ServiceStatus.dwControlsAccepted = 0;
  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 0;
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwCurrentState = a2;
  if ( a2 <= 7 )
  {
    v3 = 146;
    ServiceStatus.dwControlsAccepted = _bittest(&v3, a2);
  }
  v4 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 6);
  ServiceStatus.dwWin32ExitCode = 0;
  if ( a2 == 1 )
    *((_QWORD *)this + 6) = 0;
  SetServiceStatus(v4, &ServiceStatus);
}

```

## disassembly

```asm
0x180007c9c  sub     rsp, 58h
0x180007ca0  mov     rax, cs:__security_cookie
0x180007ca7  xor     rax, rsp
0x180007caa  mov     [rsp+58h+var_18], rax
0x180007caf  xor     r8d, r8d
0x180007cb2  mov     [rcx+28h], edx
0x180007cb5  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], r8d
0x180007cba  mov     rax, rcx
0x180007cbd  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], r8
0x180007cc2  mov     [rsp+58h+ServiceStatus.dwWaitHint], r8d
0x180007cc7  mov     [rsp+58h+ServiceStatus.dwServiceType], 20h ; ' '
0x180007ccf  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x180007cd3  cmp     edx, 7
0x180007cd6  ja      short loc_180007CEA
0x180007cd8  mov     ecx, 92h
0x180007cdd  bt      ecx, edx
0x180007ce0  jnb     short loc_180007CEA
0x180007ce2  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], 1
0x180007cea  mov     rcx, [rax+30h]; hServiceStatus
0x180007cee  cmp     edx, 1
0x180007cf1  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180007cf6  mov     [rsp+58h+ServiceStatus.dwWin32ExitCode], r8d
0x180007cfb  jnz     short loc_180007D01
0x180007cfd  mov     [rax+30h], r8
0x180007d01  call    cs:__imp_SetServiceStatus
0x180007d07  mov     rcx, [rsp+58h+var_18]
0x180007d0c  xor     rcx, rsp; StackCookie
0x180007d0f  call    __security_check_cookie
0x180007d14  add     rsp, 58h
0x180007d18  retn
```
