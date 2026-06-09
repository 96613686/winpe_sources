# PnPServiceStatusUpdate

- ea: `0x18000de70`
- end: `0x18000df07`
- name: `PnPServiceStatusUpdate`
- size: `151`
- prototype: `BOOL __fastcall(__int64, DWORD, DWORD, DWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18000cf30`
- `0x18000e890`
- `0x18000ea20`

## callees

- `0x18000de70`
- `0x180018970`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000deef`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000deef`

## pseudocode

```c
BOOL __fastcall PnPServiceStatusUpdate(__int64 a1, DWORD a2, DWORD a3, DWORD a4)
{
  BOOL result; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  PnpServiceCurrentState = a2;
  if ( PnPServiceStatusHandle )
  {
    ServiceStatus.dwServiceType = 48;
    ServiceStatus.dwCurrentState = a2;
    ServiceStatus.dwCheckPoint = a3;
    if ( a2 == 4 )
    {
      ServiceStatus.dwControlsAccepted = 1289;
LABEL_4:
      ServiceStatus.dwWaitHint = 0;
LABEL_10:
      ServiceStatus.dwWin32ExitCode = a4;
      ServiceStatus.dwServiceSpecificExitCode = 0;
      return SetServiceStatus(PnPServiceStatusHandle, &ServiceStatus);
    }
    ServiceStatus.dwControlsAccepted = 0;
    if ( a2 != 2 )
    {
      if ( a2 != 3 )
        goto LABEL_4;
      if ( PnpServiceStopWaitHint )
      {
        ServiceStatus.dwWaitHint = PnpServiceStopWaitHint;
        goto LABEL_10;
      }
    }
    ServiceStatus.dwWaitHint = 45000;
    goto LABEL_10;
  }
  return result;
}

```

## disassembly

```asm
0x18000de70  sub     rsp, 58h
0x18000de74  mov     rax, cs:__security_cookie
0x18000de7b  xor     rax, rsp
0x18000de7e  mov     [rsp+58h+var_18], rax
0x18000de83  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000de8a  mov     cs:PnpServiceCurrentState, edx
0x18000de90  test    rcx, rcx
0x18000de93  jz      short loc_18000DEF5
0x18000de95  xor     eax, eax
0x18000de97  mov     [rsp+58h+ServiceStatus.dwServiceType], 30h ; '0'
0x18000de9f  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x18000dea3  mov     [rsp+58h+ServiceStatus.dwCheckPoint], r8d
0x18000dea8  cmp     edx, 4
0x18000deab  jnz     short loc_18000DEBB
0x18000dead  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], 509h
0x18000deb5  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x18000deb9  jmp     short loc_18000DEE1
0x18000debb  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], eax
0x18000debf  cmp     edx, 2
0x18000dec2  jz      short loc_18000DED9
0x18000dec4  cmp     edx, 3
0x18000dec7  jnz     short loc_18000DEB5
0x18000dec9  mov     edx, cs:PnpServiceStopWaitHint
0x18000decf  test    edx, edx
0x18000ded1  jz      short loc_18000DED9
0x18000ded3  mov     [rsp+58h+ServiceStatus.dwWaitHint], edx
0x18000ded7  jmp     short loc_18000DEE1
0x18000ded9  mov     [rsp+58h+ServiceStatus.dwWaitHint], 0AFC8h
0x18000dee1  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18000dee6  mov     [rsp+58h+ServiceStatus.dwWin32ExitCode], r9d
0x18000deeb  mov     [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], eax
0x18000deef  call    cs:__imp_SetServiceStatus
0x18000def5  mov     rcx, [rsp+58h+var_18]
0x18000defa  xor     rcx, rsp; StackCookie
0x18000defd  call    __security_check_cookie
0x18000df02  add     rsp, 58h
0x18000df06  retn
```
