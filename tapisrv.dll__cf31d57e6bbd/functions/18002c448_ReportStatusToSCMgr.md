# ReportStatusToSCMgr

- ea: `0x18002c448`
- end: `0x18002c4c7`
- name: `ReportStatusToSCMgr`
- size: `127`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002c4d0`
- `0x18002d570`
- `0x18002d6d0`
- `0x18002e9b0`

## callees

- `0x180001600`
- `0x18002c448`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002c4aa`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002c4aa`

## pseudocode

```c
__int64 __fastcall ReportStatusToSCMgr(DWORD a1, __int64 a2, DWORD a3, DWORD a4)
{
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  if ( hServiceStatus )
  {
    ServiceStatus.dwServiceType = 32;
    ServiceStatus.dwCurrentState = a1;
    *(_QWORD *)&ServiceStatus.dwControlsAccepted = 3;
    ServiceStatus.dwServiceSpecificExitCode = 0;
    ServiceStatus.dwCheckPoint = a3;
    ServiceStatus.dwWaitHint = a4;
    SetServiceStatus(hServiceStatus, &ServiceStatus);
    return 1;
  }
  else
  {
    TRACELogPrint(0x10002u, "sshStatusHandle is NULL in ReportStatusToSCMgr");
    return 0;
  }
}

```

## disassembly

```asm
0x18002c448  sub     rsp, 58h
0x18002c44c  mov     rax, cs:__security_cookie
0x18002c453  xor     rax, rsp
0x18002c456  mov     [rsp+58h+var_18], rax
0x18002c45b  mov     eax, ecx
0x18002c45d  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18002c464  test    rcx, rcx
0x18002c467  jnz     short loc_18002C47E
0x18002c469  lea     rdx, aSshstatushandl; "sshStatusHandle is NULL in ReportStatus"...
0x18002c470  mov     ecx, 10002h
0x18002c475  call    TRACELogPrint
0x18002c47a  xor     eax, eax
0x18002c47c  jmp     short loc_18002C4B5
0x18002c47e  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002c483  mov     [rsp+58h+ServiceStatus.dwServiceType], 20h ; ' '
0x18002c48b  mov     [rsp+58h+ServiceStatus.dwCurrentState], eax
0x18002c48f  mov     qword ptr [rsp+58h+ServiceStatus.dwControlsAccepted], 3
0x18002c498  mov     [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], 0
0x18002c4a0  mov     [rsp+58h+ServiceStatus.dwCheckPoint], r8d
0x18002c4a5  mov     [rsp+58h+ServiceStatus.dwWaitHint], r9d
0x18002c4aa  call    cs:__imp_SetServiceStatus
0x18002c4b0  mov     eax, 1
0x18002c4b5  mov     rcx, [rsp+58h+var_18]
0x18002c4ba  xor     rcx, rsp; StackCookie
0x18002c4bd  call    __security_check_cookie
0x18002c4c2  add     rsp, 58h
0x18002c4c6  retn
```
