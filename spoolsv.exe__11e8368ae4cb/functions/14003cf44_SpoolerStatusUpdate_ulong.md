# SpoolerStatusUpdate(ulong)

- ea: `0x14003cf44`
- end: `0x14003d0ea`
- name: `?SpoolerStatusUpdate@@YAKK@Z`
- size: `422`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x14003c240`
- `0x14003c630`
- `0x14003c9d0`
- `0x140048140`
- `0x140048cac`
- `0x1400490bc`
- `0x140049590`
- `0x14004fdd0`

## callees

- `0x1400160a0`
- `0x14003cdd8`
- `0x14003cf44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d0d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d0d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003cf5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003cf5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d0a5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003d09b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003d09b`

## string_xrefs

- `0x14003d05a`: `No handle to call SetServiceStatus.`
- `0x14003d0b2`: `SetServiceStatus failed. Error 0x%x.`
- `0x14003d061`: `SpoolerStatusUpdate`
- `0x14003d0b9`: `SpoolerStatusUpdate`

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
        ServiceStatus.dwCheckPoint = dword_1400CB974++;
        ServiceStatus.dwWaitHint = 20000;
        *(_QWORD *)&ServiceStatus.dwCurrentState = v3;
        break;
      case 2u:
        LODWORD(v3) = 3;
        if ( a1 == 3 )
        {
          ServiceStatus.dwCheckPoint = dword_1400CB974++;
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
0x14003cf44  mov     [rsp+arg_0], rbx
0x14003cf49  mov     [rsp+arg_8], rsi
0x14003cf4e  push    rdi
0x14003cf4f  sub     rsp, 20h
0x14003cf53  mov     edi, ecx
0x14003cf55  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003cf5c  call    cs:__imp_EnterCriticalSection
0x14003cf62  xor     esi, esi
0x14003cf64  lea     ecx, [rsi+4]; unsigned int
0x14003cf67  cmp     edi, ecx
0x14003cf69  jnz     short loc_14003CFA6
0x14003cf6b  cmp     cs:?SpoolerState@@3KA, ecx; ulong SpoolerState
0x14003cf71  jnz     short loc_14003CF78
0x14003cf73  lea     eax, [rsi+1]
0x14003cf76  jmp     short loc_14003CF93
0x14003cf78  mov     eax, esi
0x14003cf7a  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x14003cf85  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rsi
0x14003cf8c  mov     qword ptr cs:ServiceStatus.dwWin32ExitCode, rsi
0x14003cf93  mov     cs:?SpoolerState@@3KA, ecx; ulong SpoolerState
0x14003cf99  test    eax, eax
0x14003cf9b  jnz     loc_14003D0C5
0x14003cfa1  jmp     loc_14003D04E
0x14003cfa6  mov     eax, cs:?SpoolerState@@3KA; ulong SpoolerState
0x14003cfac  sub     eax, 1
0x14003cfaf  jz      short loc_14003D01A
0x14003cfb1  sub     eax, 1
0x14003cfb4  jz      short loc_14003CFDD
0x14003cfb6  sub     eax, 1
0x14003cfb9  jz      short loc_14003CFC9
0x14003cfbb  cmp     eax, 1
0x14003cfbe  jz      loc_14003D0C5
0x14003cfc4  jmp     loc_14003D04E
0x14003cfc9  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x14003cfd4  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rsi
0x14003cfdb  jmp     short loc_14003D04E
0x14003cfdd  mov     ebx, 3
0x14003cfe2  cmp     edi, ebx
0x14003cfe4  jnz     short loc_14003D04E
0x14003cfe6  mov     eax, cs:dword_1400CB974
0x14003cfec  mov     cs:ServiceStatus.dwCheckPoint, eax
0x14003cff2  inc     eax
0x14003cff4  mov     cs:dword_1400CB974, eax
0x14003cffa  mov     qword ptr cs:ServiceStatus.dwCurrentState, rbx
0x14003d001  mov     cs:ServiceStatus.dwWaitHint, 4E20h
0x14003d00b  mov     edx, ebx; unsigned int
0x14003d00d  call    ?LogSpoolerStartStop@@YAXKK@Z; LogSpoolerStartStop(ulong,ulong)
0x14003d012  mov     cs:?SpoolerState@@3KA, ebx; ulong SpoolerState
0x14003d018  jmp     short loc_14003D04E
0x14003d01a  mov     ebx, 3
0x14003d01f  cmp     edi, ebx
0x14003d021  jnz     short loc_14003D06F
0x14003d023  mov     cs:?SpoolerState@@3KA, ebx; ulong SpoolerState
0x14003d029  mov     eax, cs:dword_1400CB974
0x14003d02f  mov     cs:ServiceStatus.dwCheckPoint, eax
0x14003d035  inc     eax
0x14003d037  mov     cs:dword_1400CB974, eax
0x14003d03d  mov     cs:ServiceStatus.dwWaitHint, 4E20h
0x14003d047  mov     qword ptr cs:ServiceStatus.dwCurrentState, rbx
0x14003d04e  mov     rcx, cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14003d055  test    rcx, rcx
0x14003d058  jnz     short loc_14003D094
0x14003d05a  lea     rdx, aNoHandleToCall; "No handle to call SetServiceStatus."
0x14003d061  lea     rcx, aSpoolerstatusu; "SpoolerStatusUpdate"
0x14003d068  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003d06d  jmp     short loc_14003D0C5
0x14003d06f  mov     ebx, 2
0x14003d074  cmp     edi, ebx
0x14003d076  jnz     short loc_14003D029
0x14003d078  mov     cs:ServiceStatus.dwCurrentState, ecx
0x14003d07e  mov     cs:ServiceStatus.dwControlsAccepted, 4C1h
0x14003d088  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rsi
0x14003d08f  jmp     loc_14003D00B
0x14003d094  lea     rdx, ServiceStatus; lpServiceStatus
0x14003d09b  call    cs:__imp_SetServiceStatus
0x14003d0a1  test    eax, eax
0x14003d0a3  jnz     short loc_14003D0C5
0x14003d0a5  call    cs:__imp_GetLastError
0x14003d0ab  test    eax, eax
0x14003d0ad  jz      short loc_14003D0C5
0x14003d0af  mov     r8d, eax
0x14003d0b2  lea     rdx, aSetservicestat; "SetServiceStatus failed. Error 0x%x."
0x14003d0b9  lea     rcx, aSpoolerstatusu; "SpoolerStatusUpdate"
0x14003d0c0  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003d0c5  mov     ebx, cs:?SpoolerState@@3KA; ulong SpoolerState
0x14003d0cb  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003d0d2  call    cs:__imp_LeaveCriticalSection
0x14003d0d8  mov     rsi, [rsp+28h+arg_8]
0x14003d0dd  mov     eax, ebx
0x14003d0df  mov     rbx, [rsp+28h+arg_0]
0x14003d0e4  add     rsp, 20h
0x14003d0e8  pop     rdi
0x14003d0e9  retn
```
