# GSM::_StopServiceAndWait(SC_HANDLE__ *,ushort const *)

- ea: `0x1800221a4`
- end: `0x18002229e`
- name: `?_StopServiceAndWait@GSM@@YAJPEAUSC_HANDLE__@@PEBG@Z`
- size: `250`
- prototype: `__int64 __fastcall(GSM *this, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800212f4`

## callees

- `0x18001951c`
- `0x1800221a4`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022224`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022224`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022200`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022211`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022200`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022211`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800221c8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800221c8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022270`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180022270`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800221f4`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800221f4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180022232`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180022232`

## pseudocode

```c
__int64 __fastcall GSM::_StopServiceAndWait(GSM *this, const WCHAR *a2, const unsigned __int16 *a3)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  int Error; // ebx
  DWORD TickCount; // esi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v3 = OpenServiceW((SC_HANDLE)this, a2, 0x24u);
  v4 = v3;
  if ( v3 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( ControlService(v3, 1u, &ServiceStatus) )
    {
      Error = 0;
      TickCount = GetTickCount();
      while ( ServiceStatus.dwCurrentState != 1 )
      {
        if ( GetTickCount() - TickCount < 0x2710 )
        {
          Sleep(ServiceStatus.dwWaitHint);
          if ( !QueryServiceStatus(v4, &ServiceStatus) )
            Error = ResultFromKnownLastError();
          if ( Error >= 0 )
            continue;
        }
        if ( Error >= 0 && ServiceStatus.dwCurrentState != 1 )
          Error = -2147023436;
        break;
      }
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error == -2147023834 )
        Error = 0;
    }
    CloseServiceHandle(v4);
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800221a4  mov     [rsp+arg_10], rbx
0x1800221a9  mov     [rsp+arg_18], rsi
0x1800221ae  push    rdi
0x1800221af  sub     rsp, 50h
0x1800221b3  mov     rax, cs:__security_cookie
0x1800221ba  xor     rax, rsp
0x1800221bd  mov     [rsp+58h+var_18], rax
0x1800221c2  mov     r8d, 24h ; '$'; dwDesiredAccess
0x1800221c8  call    cs:__imp_OpenServiceW
0x1800221ce  mov     rdi, rax
0x1800221d1  test    rax, rax
0x1800221d4  jz      loc_180022278
0x1800221da  xorps   xmm0, xmm0
0x1800221dd  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800221e2  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800221e7  mov     edx, 1; dwControl
0x1800221ec  mov     rcx, rax; hService
0x1800221ef  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800221f4  call    cs:__imp_ControlService
0x1800221fa  test    eax, eax
0x1800221fc  jz      short loc_18002225B
0x1800221fe  xor     ebx, ebx
0x180022200  call    cs:__imp_GetTickCount
0x180022206  mov     esi, eax
0x180022208  mov     ecx, [rsp+58h+ServiceStatus.dwCurrentState]
0x18002220c  cmp     ecx, 1
0x18002220f  jz      short loc_18002226D
0x180022211  call    cs:__imp_GetTickCount
0x180022217  sub     eax, esi
0x180022219  cmp     eax, 2710h
0x18002221e  jnb     short loc_180022247
0x180022220  mov     ecx, [rsp+58h+ServiceStatus.dwWaitHint]; dwMilliseconds
0x180022224  call    cs:__imp_Sleep
0x18002222a  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002222f  mov     rcx, rdi; hService
0x180022232  call    cs:__imp_QueryServiceStatus
0x180022238  test    eax, eax
0x18002223a  jnz     short loc_180022243
0x18002223c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022241  mov     ebx, eax
0x180022243  test    ebx, ebx
0x180022245  jns     short loc_180022208
0x180022247  test    ebx, ebx
0x180022249  js      short loc_18002226D
0x18002224b  mov     ecx, [rsp+58h+ServiceStatus.dwCurrentState]
0x18002224f  cmp     ecx, 1
0x180022252  jz      short loc_18002226D
0x180022254  mov     ebx, 800705B4h
0x180022259  jmp     short loc_18002226D
0x18002225b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022260  mov     ebx, eax
0x180022262  xor     eax, eax
0x180022264  cmp     ebx, 80070426h
0x18002226a  cmovz   ebx, eax
0x18002226d  mov     rcx, rdi; hSCObject
0x180022270  call    cs:__imp_CloseServiceHandle
0x180022276  jmp     short loc_18002227F
0x180022278  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002227d  mov     ebx, eax
0x18002227f  mov     eax, ebx
0x180022281  mov     rcx, [rsp+58h+var_18]
0x180022286  xor     rcx, rsp; StackCookie
0x180022289  call    __security_check_cookie
0x18002228e  mov     rbx, [rsp+58h+arg_10]
0x180022293  mov     rsi, [rsp+58h+arg_18]
0x180022298  add     rsp, 50h
0x18002229c  pop     rdi
0x18002229d  retn
```
