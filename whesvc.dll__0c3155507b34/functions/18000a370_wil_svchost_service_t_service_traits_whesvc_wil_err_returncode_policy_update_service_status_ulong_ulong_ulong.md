# wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(ulong,ulong,ulong)

- ea: `0x18000a370`
- end: `0x18000a3fa`
- name: `?update_service_status@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAXKKK@Z`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180006900`
- `0x180009160`
- `0x180009e30`
- `0x18000a14c`

## callees

- `0x1800032e0`
- `0x180009dd4`
- `0x18000a370`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000a3d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000a3d4`

## pseudocode

```c
void __fastcall wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(
        __int64 a1,
        DWORD a2,
        DWORD a3,
        DWORD a4)
{
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  ServiceStatus.dwServiceType = 96;
  ServiceStatus.dwCurrentState = a2;
  memset(&ServiceStatus.dwControlsAccepted, 0, 20);
  ServiceStatus.dwWin32ExitCode = a3;
  if ( a2 == 4 || a2 == 1 )
  {
    ServiceStatus.dwControlsAccepted = a4;
  }
  else
  {
    ServiceStatus.dwWaitHint = 5000;
    ServiceStatus.dwCheckPoint = _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
  }
  if ( !SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(a1 + 32), &ServiceStatus) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, v4, v5, v6);
}

```

## disassembly

```asm
0x18000a370  sub     rsp, 58h
0x18000a374  mov     rax, cs:__security_cookie
0x18000a37b  xor     rax, rsp
0x18000a37e  mov     [rsp+58h+var_18], rax
0x18000a383  xor     eax, eax
0x18000a385  mov     [rsp+58h+ServiceStatus.dwServiceType], 60h ; '`'
0x18000a38d  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x18000a391  xorps   xmm0, xmm0
0x18000a394  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18000a398  movups  xmmword ptr [rsp+58h+ServiceStatus.dwControlsAccepted], xmm0
0x18000a39d  mov     [rsp+58h+ServiceStatus.dwWin32ExitCode], r8d
0x18000a3a2  cmp     edx, 4
0x18000a3a5  jz      short loc_18000A3C6
0x18000a3a7  cmp     edx, 1
0x18000a3aa  jz      short loc_18000A3C6
0x18000a3ac  mov     eax, 1
0x18000a3b1  lock xadd [rcx+28h], eax
0x18000a3b6  inc     eax
0x18000a3b8  mov     [rsp+58h+ServiceStatus.dwWaitHint], 1388h
0x18000a3c0  mov     [rsp+58h+ServiceStatus.dwCheckPoint], eax
0x18000a3c4  jmp     short loc_18000A3CB
0x18000a3c6  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], r9d
0x18000a3cb  mov     rcx, [rcx+20h]; hServiceStatus
0x18000a3cf  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18000a3d4  call    cs:__imp_SetServiceStatus
0x18000a3da  test    eax, eax
0x18000a3dc  jnz     short loc_18000A3E8
0x18000a3de  mov     rcx, [rsp+58h]; this
0x18000a3e3  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000a3e8  mov     rcx, [rsp+58h+var_18]
0x18000a3ed  xor     rcx, rsp; StackCookie
0x18000a3f0  call    __security_check_cookie
0x18000a3f5  add     rsp, 58h
0x18000a3f9  retn
```
