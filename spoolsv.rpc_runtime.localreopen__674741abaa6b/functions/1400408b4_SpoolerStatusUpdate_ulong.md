# SpoolerStatusUpdate(ulong)

- ea: `0x1400408b4`
- end: `0x140040a73`
- name: `?SpoolerStatusUpdate@@YAKK@Z`
- size: `447`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x14003fa90`
- `0x14003feb0`
- `0x140040270`
- `0x14004c580`
- `0x14004d2d4`
- `0x14004d74c`
- `0x14004dcd8`
- `0x140054a80`

## callees

- `0x14001748c`
- `0x140040720`
- `0x1400408b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140040a54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140040a54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400408cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400408cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040a21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040a21`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140040a11`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140040a11`

## string_xrefs

- `0x1400409d0`: `No handle to call SetServiceStatus.`
- `0x140040a34`: `SetServiceStatus failed. Error 0x%x.`
- `0x1400409d7`: `SpoolerStatusUpdate`
- `0x140040a3b`: `SpoolerStatusUpdate`

## pseudocode

```c
__int64 __fastcall SpoolerStatusUpdate(int a1)
{
  int v2; // eax
  __int64 v3; // rbx
  DWORD LastError; // eax
  unsigned int v5; // ebx

  EnterCriticalSection(&ThreadCriticalSection);
  if ( a1 != 4 )
  {
    switch ( SpoolerState )
    {
      case 1u:
        v3 = 3;
        if ( a1 == 3 )
        {
          SpoolerState = 3;
        }
        else
        {
          v3 = 2;
          if ( a1 == 2 )
          {
            ServiceStatus.dwCurrentState = 4;
            ServiceStatus.dwControlsAccepted = 1217;
            *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
            goto LABEL_15;
          }
        }
        ServiceStatus.dwCheckPoint = dword_1400D2AE4++;
        ServiceStatus.dwWaitHint = 20000;
        *(_QWORD *)&ServiceStatus.dwCurrentState = v3;
        break;
      case 2u:
        LODWORD(v3) = 3;
        if ( a1 == 3 )
        {
          ServiceStatus.dwCheckPoint = dword_1400D2AE4++;
          *(_QWORD *)&ServiceStatus.dwCurrentState = 3;
          ServiceStatus.dwWaitHint = 20000;
LABEL_15:
          LogSpoolerStartStop(4u, v3);
          SpoolerState = v3;
        }
        break;
      case 3u:
        *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
        *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
        break;
      case 4u:
        goto LABEL_26;
      default:
        break;
    }
LABEL_19:
    if ( SpoolerStatusHandle )
    {
      if ( !SetServiceStatus((SERVICE_STATUS_HANDLE)SpoolerStatusHandle, &ServiceStatus) )
      {
        LastError = GetLastError();
        if ( LastError )
          SpoolerServiceTelemetry::WriteDbgTraceError(
            "SpoolerStatusUpdate",
            L"SetServiceStatus failed. Error 0x%x.",
            LastError);
      }
    }
    else
    {
      SpoolerServiceTelemetry::WriteDbgTraceError("SpoolerStatusUpdate", L"No handle to call SetServiceStatus.");
    }
    goto LABEL_26;
  }
  if ( SpoolerState == 4 )
  {
    v2 = 1;
  }
  else
  {
    v2 = 0;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  }
  SpoolerState = 4;
  if ( !v2 )
    goto LABEL_19;
LABEL_26:
  v5 = SpoolerState;
  LeaveCriticalSection(&ThreadCriticalSection);
  return v5;
}

```

## disassembly

```asm
0x1400408b4  mov     [rsp+arg_0], rbx
0x1400408b9  mov     [rsp+arg_8], rsi
0x1400408be  push    rdi
0x1400408bf  sub     rsp, 20h
0x1400408c3  mov     edi, ecx
0x1400408c5  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400408cc  call    cs:__imp_EnterCriticalSection
0x1400408d3  nop     dword ptr [rax+rax+00h]
0x1400408d8  xor     esi, esi
0x1400408da  lea     ecx, [rsi+4]; unsigned int
0x1400408dd  cmp     edi, ecx
0x1400408df  jnz     short loc_14004091C
0x1400408e1  cmp     cs:?SpoolerState@@3KA, ecx; ulong SpoolerState
0x1400408e7  jnz     short loc_1400408EE
0x1400408e9  lea     eax, [rsi+1]
0x1400408ec  jmp     short loc_140040909
0x1400408ee  mov     eax, esi
0x1400408f0  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x1400408fb  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rsi
0x140040902  mov     qword ptr cs:ServiceStatus.dwWin32ExitCode, rsi
0x140040909  mov     cs:?SpoolerState@@3KA, ecx; ulong SpoolerState
0x14004090f  test    eax, eax
0x140040911  jnz     loc_140040A47
0x140040917  jmp     loc_1400409C4
0x14004091c  mov     eax, cs:?SpoolerState@@3KA; ulong SpoolerState
0x140040922  sub     eax, 1
0x140040925  jz      short loc_140040990
0x140040927  sub     eax, 1
0x14004092a  jz      short loc_140040953
0x14004092c  sub     eax, 1
0x14004092f  jz      short loc_14004093F
0x140040931  cmp     eax, 1
0x140040934  jz      loc_140040A47
0x14004093a  jmp     loc_1400409C4
0x14004093f  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x14004094a  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rsi
0x140040951  jmp     short loc_1400409C4
0x140040953  mov     ebx, 3
0x140040958  cmp     edi, ebx
0x14004095a  jnz     short loc_1400409C4
0x14004095c  mov     eax, cs:dword_1400D2AE4
0x140040962  mov     cs:ServiceStatus.dwCheckPoint, eax
0x140040968  inc     eax
0x14004096a  mov     cs:dword_1400D2AE4, eax
0x140040970  mov     qword ptr cs:ServiceStatus.dwCurrentState, rbx
0x140040977  mov     cs:ServiceStatus.dwWaitHint, 4E20h
0x140040981  mov     edx, ebx; unsigned int
0x140040983  call    ?LogSpoolerStartStop@@YAXKK@Z; LogSpoolerStartStop(ulong,ulong)
0x140040988  mov     cs:?SpoolerState@@3KA, ebx; ulong SpoolerState
0x14004098e  jmp     short loc_1400409C4
0x140040990  mov     ebx, 3
0x140040995  cmp     edi, ebx
0x140040997  jnz     short loc_1400409E5
0x140040999  mov     cs:?SpoolerState@@3KA, ebx; ulong SpoolerState
0x14004099f  mov     eax, cs:dword_1400D2AE4
0x1400409a5  mov     cs:ServiceStatus.dwCheckPoint, eax
0x1400409ab  inc     eax
0x1400409ad  mov     cs:dword_1400D2AE4, eax
0x1400409b3  mov     cs:ServiceStatus.dwWaitHint, 4E20h
0x1400409bd  mov     qword ptr cs:ServiceStatus.dwCurrentState, rbx
0x1400409c4  mov     rcx, cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1400409cb  test    rcx, rcx
0x1400409ce  jnz     short loc_140040A0A
0x1400409d0  lea     rdx, aNoHandleToCall; "No handle to call SetServiceStatus."
0x1400409d7  lea     rcx, aSpoolerstatusu; "SpoolerStatusUpdate"
0x1400409de  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400409e3  jmp     short loc_140040A47
0x1400409e5  mov     ebx, 2
0x1400409ea  cmp     edi, ebx
0x1400409ec  jnz     short loc_14004099F
0x1400409ee  mov     cs:ServiceStatus.dwCurrentState, ecx
0x1400409f4  mov     cs:ServiceStatus.dwControlsAccepted, 4C1h
0x1400409fe  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rsi
0x140040a05  jmp     loc_140040981
0x140040a0a  lea     rdx, ServiceStatus; lpServiceStatus
0x140040a11  call    cs:__imp_SetServiceStatus
0x140040a18  nop     dword ptr [rax+rax+00h]
0x140040a1d  test    eax, eax
0x140040a1f  jnz     short loc_140040A47
0x140040a21  call    cs:__imp_GetLastError
0x140040a28  nop     dword ptr [rax+rax+00h]
0x140040a2d  test    eax, eax
0x140040a2f  jz      short loc_140040A47
0x140040a31  mov     r8d, eax
0x140040a34  lea     rdx, aSetservicestat; "SetServiceStatus failed. Error 0x%x."
0x140040a3b  lea     rcx, aSpoolerstatusu; "SpoolerStatusUpdate"
0x140040a42  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140040a47  mov     ebx, cs:?SpoolerState@@3KA; ulong SpoolerState
0x140040a4d  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140040a54  call    cs:__imp_LeaveCriticalSection
0x140040a5b  nop     dword ptr [rax+rax+00h]
0x140040a60  mov     rsi, [rsp+28h+arg_8]
0x140040a65  mov     eax, ebx
0x140040a67  mov     rbx, [rsp+28h+arg_0]
0x140040a6c  add     rsp, 20h
0x140040a70  pop     rdi
0x140040a71  retn
```
