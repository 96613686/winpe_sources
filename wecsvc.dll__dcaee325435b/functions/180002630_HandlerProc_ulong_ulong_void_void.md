# HandlerProc(ulong,ulong,void *,void *)

- ea: `0x180002630`
- end: `0x18000268b`
- name: `?HandlerProc@@YAKKKPEAX0@Z`
- size: `91`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000267b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000267b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002671`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002671`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002664`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002664`

## pseudocode

```c
__int64 __fastcall HandlerProc(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v4; // ebx
  DWORD v5; // ecx
  DWORD v6; // ecx

  v4 = 0;
  v5 = dwControl - 1;
  if ( !v5 )
  {
LABEL_5:
    g_serviceStatus.dwCurrentState = 3;
    SetServiceStatus(g_serviceControl, &g_serviceStatus);
    if ( !SetEvent(g_svchostShutdownEvent) )
      return GetLastError();
    return v4;
  }
  v6 = v5 - 3;
  if ( v6 )
  {
    if ( v6 != 1 )
      return 120;
    goto LABEL_5;
  }
  return v4;
}

```

## disassembly

```asm
0x180002630  push    rbx
0x180002632  sub     rsp, 20h
0x180002636  xor     ebx, ebx
0x180002638  sub     ecx, 1
0x18000263b  jz      short loc_18000264C
0x18000263d  sub     ecx, 3
0x180002640  jz      short loc_180002683
0x180002642  cmp     ecx, 1
0x180002645  jz      short loc_18000264C
0x180002647  lea     eax, [rbx+78h]
0x18000264a  jmp     short loc_180002685
0x18000264c  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180002653  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18000265a  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_serviceStatus ...
0x180002664  call    cs:__imp_SetServiceStatus
0x18000266a  mov     rcx, cs:?g_svchostShutdownEvent@@3PEAXEA; hEvent
0x180002671  call    cs:__imp_SetEvent
0x180002677  test    eax, eax
0x180002679  jnz     short loc_180002683
0x18000267b  call    cs:__imp_GetLastError
0x180002681  mov     ebx, eax
0x180002683  mov     eax, ebx
0x180002685  add     rsp, 20h
0x180002689  pop     rbx
0x18000268a  retn
```
