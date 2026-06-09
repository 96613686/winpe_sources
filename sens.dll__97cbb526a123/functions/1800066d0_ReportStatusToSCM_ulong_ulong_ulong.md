# ReportStatusToSCM(ulong,ulong,ulong)

- ea: `0x1800066d0`
- end: `0x18000672c`
- name: `?ReportStatusToSCM@@YAHKKK@Z`
- size: `92`
- prototype: `BOOL __fastcall(DWORD, __int64, DWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180007840`
- `0x180009360`

## callees

- `0x1800066d0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006714`

## pseudocode

```c
BOOL __fastcall ReportStatusToSCM(DWORD a1, __int64 a2, DWORD a3)
{
  gServiceStatus.dwCurrentState = a1;
  gServiceStatus.dwWin32ExitCode = 0;
  gServiceStatus.dwWaitHint = a3;
  gServiceStatus.dwControlsAccepted = a1 != 2 ? 0x41 : 0;
  if ( a1 == 4 || (gServiceStatus.dwCheckPoint = 1, a1 == 1) )
    gServiceStatus.dwCheckPoint = 0;
  return SetServiceStatus(ghStatusHandle, &gServiceStatus);
}

```

## disassembly

```asm
0x1800066d0  lea     eax, [rcx-2]
0x1800066d3  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ecx; _SERVICE_STATUS gServiceStatus ...
0x1800066d9  neg     eax
0x1800066db  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS gServiceStatus ...
0x1800066e5  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, r8d; _SERVICE_STATUS gServiceStatus ...
0x1800066ec  sbb     eax, eax
0x1800066ee  and     eax, 41h
0x1800066f1  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, eax; _SERVICE_STATUS gServiceStatus ...
0x1800066f7  cmp     ecx, 4
0x1800066fa  jnz     short loc_18000671B
0x1800066fc  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS gServiceStatus ...
0x180006706  mov     rcx, cs:?ghStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * ghStatusHandle
0x18000670d  lea     rdx, ?gServiceStatus@@3U_SERVICE_STATUS@@A; _SERVICE_STATUS gServiceStatus
0x180006714  jmp     cs:__imp_SetServiceStatus
0x18000671b  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS gServiceStatus ...
0x180006725  cmp     ecx, 1
0x180006728  jnz     short loc_180006706
0x18000672a  jmp     short loc_1800066FC
```
