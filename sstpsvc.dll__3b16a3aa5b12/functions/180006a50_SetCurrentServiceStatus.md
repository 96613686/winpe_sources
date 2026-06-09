# SetCurrentServiceStatus

- ea: `0x180006a50`
- end: `0x180006afd`
- name: `SetCurrentServiceStatus`
- size: `173`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004940`
- `0x180005280`

## callees

- `0x180006a50`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006ac4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006ac4`

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
0x180006a50  sub     rsp, 58h
0x180006a54  mov     rax, cs:__security_cookie
0x180006a5b  xor     rax, rsp
0x180006a5e  mov     [rsp+58h+var_18], rax
0x180006a63  mov     rax, cs:SstpSvcGlobals
0x180006a6a  xor     r8d, r8d
0x180006a6d  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], r8
0x180006a72  mov     [rsp+58h+ServiceStatus.dwWaitHint], r8d
0x180006a77  mov     [rsp+58h+ServiceStatus.dwServiceType], 20h ; ' '
0x180006a7f  mov     ecx, [rax+4]
0x180006a82  mov     edx, [rax]
0x180006a84  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], ecx
0x180006a88  mov     ecx, [rax+0Ch]
0x180006a8b  mov     [rsp+58h+ServiceStatus.dwWin32ExitCode], ecx
0x180006a8f  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x180006a93  cmp     edx, 7
0x180006a96  ja      short loc_180006ADC
0x180006a98  mov     ecx, 92h
0x180006a9d  bt      ecx, edx
0x180006aa0  jnb     short loc_180006ADC
0x180006aa2  mov     ecx, r8d
0x180006aa5  xchg    ecx, [rax+8]
0x180006aa8  mov     rcx, cs:SstpSvcGlobals
0x180006aaf  mov     [rsp+58h+ServiceStatus.dwWaitHint], r8d
0x180006ab4  mov     eax, [rcx+8]
0x180006ab7  mov     [rsp+58h+ServiceStatus.dwCheckPoint], eax
0x180006abb  mov     rcx, [rcx+28h]; hServiceStatus
0x180006abf  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180006ac4  call    cs:__imp_SetServiceStatus
0x180006aca  mov     rcx, [rsp+58h+var_18]
0x180006acf  xor     rcx, rsp; StackCookie
0x180006ad2  call    __security_check_cookie
0x180006ad7  add     rsp, 58h
0x180006adb  retn
0x180006adc  mov     ecx, 1
0x180006ae1  lock xadd [rax+8], ecx
0x180006ae6  inc     ecx
0x180006ae8  mov     [rsp+58h+ServiceStatus.dwWaitHint], 7D0h
0x180006af0  mov     [rsp+58h+ServiceStatus.dwCheckPoint], ecx
0x180006af4  mov     rcx, cs:SstpSvcGlobals
0x180006afb  jmp     short loc_180006ABB
```
