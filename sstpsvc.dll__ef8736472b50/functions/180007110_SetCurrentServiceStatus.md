# SetCurrentServiceStatus

- ea: `0x180007110`
- end: `0x1800071c4`
- name: `SetCurrentServiceStatus`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004d10`
- `0x1800056e0`

## callees

- `0x180007110`
- `0x18001d210`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007184`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007184`

## pseudocode

```c
BOOL SetCurrentServiceStatus()
{
  DWORD v0; // edx
  int v1; // ecx
  SERVICE_STATUS_HANDLE *v2; // rcx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 0;
  ServiceStatus.dwServiceType = 32;
  v0 = *(_DWORD *)SstpSvcGlobals;
  ServiceStatus.dwControlsAccepted = *((_DWORD *)SstpSvcGlobals + 1);
  ServiceStatus.dwWin32ExitCode = *((_DWORD *)SstpSvcGlobals + 3);
  ServiceStatus.dwCurrentState = v0;
  if ( v0 <= 7 && (v1 = 146, _bittest(&v1, v0)) )
  {
    _InterlockedExchange((volatile __int32 *)SstpSvcGlobals + 2, 0);
    v2 = (SERVICE_STATUS_HANDLE *)SstpSvcGlobals;
    ServiceStatus.dwWaitHint = 0;
    ServiceStatus.dwCheckPoint = *((_DWORD *)SstpSvcGlobals + 2);
  }
  else
  {
    ServiceStatus.dwWaitHint = 2000;
    ServiceStatus.dwCheckPoint = _InterlockedIncrement((volatile signed __int32 *)SstpSvcGlobals + 2);
    v2 = (SERVICE_STATUS_HANDLE *)SstpSvcGlobals;
  }
  return SetServiceStatus(v2[5], &ServiceStatus);
}

```

## disassembly

```asm
0x180007110  sub     rsp, 58h
0x180007114  mov     rax, cs:__security_cookie
0x18000711b  xor     rax, rsp
0x18000711e  mov     [rsp+58h+var_18], rax
0x180007123  mov     rax, cs:SstpSvcGlobals
0x18000712a  xor     r8d, r8d
0x18000712d  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], r8
0x180007132  mov     [rsp+58h+ServiceStatus.dwWaitHint], r8d
0x180007137  mov     [rsp+58h+ServiceStatus.dwServiceType], 20h ; ' '
0x18000713f  mov     ecx, [rax+4]
0x180007142  mov     edx, [rax]
0x180007144  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], ecx
0x180007148  mov     ecx, [rax+0Ch]
0x18000714b  mov     [rsp+58h+ServiceStatus.dwWin32ExitCode], ecx
0x18000714f  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x180007153  cmp     edx, 7
0x180007156  ja      short loc_1800071A3
0x180007158  mov     ecx, 92h
0x18000715d  bt      ecx, edx
0x180007160  jnb     short loc_1800071A3
0x180007162  mov     ecx, r8d
0x180007165  xchg    ecx, [rax+8]
0x180007168  mov     rcx, cs:SstpSvcGlobals
0x18000716f  mov     [rsp+58h+ServiceStatus.dwWaitHint], r8d
0x180007174  mov     eax, [rcx+8]
0x180007177  mov     [rsp+58h+ServiceStatus.dwCheckPoint], eax
0x18000717b  mov     rcx, [rcx+28h]; hServiceStatus
0x18000717f  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180007184  call    cs:__imp_SetServiceStatus
0x18000718b  nop     dword ptr [rax+rax+00h]
0x180007190  mov     rcx, [rsp+58h+var_18]
0x180007195  xor     rcx, rsp; StackCookie
0x180007198  call    __security_check_cookie
0x18000719d  add     rsp, 58h
0x1800071a1  retn
0x1800071a3  mov     ecx, 1
0x1800071a8  lock xadd [rax+8], ecx
0x1800071ad  inc     ecx
0x1800071af  mov     [rsp+58h+ServiceStatus.dwWaitHint], 7D0h
0x1800071b7  mov     [rsp+58h+ServiceStatus.dwCheckPoint], ecx
0x1800071bb  mov     rcx, cs:SstpSvcGlobals
0x1800071c2  jmp     short loc_18000717B
```
