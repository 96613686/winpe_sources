# WsCSCReportStartRedir

- ea: `0x180011ccc`
- end: `0x180011e08`
- name: `WsCSCReportStartRedir`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800061d8`
- `0x18002ee64`

## callees

- `0x180011ccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d56`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011de7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011de7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011cee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011cee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011d3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011dbe`

## string_xrefs

- `0x180011d06`: `WkssvcToAgentStopEvent`
- `0x180011d2c`: `AgentToWkssvcEvent`
- `0x180011ce2`: `WkssvcToAgentStartEvent`

## pseudocode

```c
__int64 WsCSCReportStartRedir()
{
  LPSECURITY_ATTRIBUTES v0; // rcx
  DWORD LastError; // ebx

  v0 = heventWkssvcToAgentStart;
  if ( !heventWkssvcToAgentStart )
  {
    heventWkssvcToAgentStart = (LPSECURITY_ATTRIBUTES)CreateEventW(0, 0, 0, aWkssvctoagents);
    if ( !heventWkssvcToAgentStart
      || (heventWkssvcToAgentStop = CreateEventW(0, 0, 0, aWkssvctoagents_0)) == 0
      || (heventAgentToWkssvc = CreateEventW(0, 0, 0, aAgenttowkssvce)) == 0 )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( heventWkssvcToAgentStart )
        {
          CloseHandle(heventWkssvcToAgentStart);
          heventWkssvcToAgentStart = 0;
        }
        if ( heventWkssvcToAgentStop )
        {
          CloseHandle(heventWkssvcToAgentStop);
          heventWkssvcToAgentStop = 0;
        }
        if ( heventAgentToWkssvc )
        {
          CloseHandle(heventAgentToWkssvc);
          heventAgentToWkssvc = 0;
        }
      }
      return LastError;
    }
    v0 = heventWkssvcToAgentStart;
  }
  if ( !vfRedirStarted )
  {
    SetEvent(v0);
    vfRedirStarted = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180011ccc  push    rbx
0x180011cce  sub     rsp, 20h
0x180011cd2  mov     rcx, cs:heventWkssvcToAgentStart; lpEventAttributes
0x180011cd9  test    rcx, rcx
0x180011cdc  jnz     loc_180011DDE
0x180011ce2  lea     r9, aWkssvctoagents; "WkssvcToAgentStartEvent"
0x180011ce9  xor     r8d, r8d; bInitialState
0x180011cec  xor     edx, edx; bManualReset
0x180011cee  call    cs:__imp_CreateEventW
0x180011cf5  nop     dword ptr [rax+rax+00h]
0x180011cfa  mov     cs:heventWkssvcToAgentStart, rax
0x180011d01  test    rax, rax
0x180011d04  jz      short loc_180011D56
0x180011d06  lea     r9, aWkssvctoagents_0; "WkssvcToAgentStopEvent"
0x180011d0d  xor     r8d, r8d; bInitialState
0x180011d10  xor     edx, edx; bManualReset
0x180011d12  xor     ecx, ecx; lpEventAttributes
0x180011d14  call    cs:__imp_CreateEventW
0x180011d1b  nop     dword ptr [rax+rax+00h]
0x180011d20  mov     cs:heventWkssvcToAgentStop, rax
0x180011d27  test    rax, rax
0x180011d2a  jz      short loc_180011D56
0x180011d2c  lea     r9, aAgenttowkssvce; "AgentToWkssvcEvent"
0x180011d33  xor     r8d, r8d; bInitialState
0x180011d36  xor     edx, edx; bManualReset
0x180011d38  xor     ecx, ecx; lpEventAttributes
0x180011d3a  call    cs:__imp_CreateEventW
0x180011d41  nop     dword ptr [rax+rax+00h]
0x180011d46  mov     cs:heventAgentToWkssvc, rax
0x180011d4d  test    rax, rax
0x180011d50  jnz     loc_180011DD7
0x180011d56  call    cs:__imp_GetLastError
0x180011d5d  nop     dword ptr [rax+rax+00h]
0x180011d62  mov     ebx, eax
0x180011d64  test    eax, eax
0x180011d66  jz      loc_180011DFF
0x180011d6c  mov     rcx, cs:heventWkssvcToAgentStart; hObject
0x180011d73  test    rcx, rcx
0x180011d76  jz      short loc_180011D8F
0x180011d78  call    cs:__imp_CloseHandle
0x180011d7f  nop     dword ptr [rax+rax+00h]
0x180011d84  mov     cs:heventWkssvcToAgentStart, 0
0x180011d8f  mov     rcx, cs:heventWkssvcToAgentStop; hObject
0x180011d96  test    rcx, rcx
0x180011d99  jz      short loc_180011DB2
0x180011d9b  call    cs:__imp_CloseHandle
0x180011da2  nop     dword ptr [rax+rax+00h]
0x180011da7  mov     cs:heventWkssvcToAgentStop, 0
0x180011db2  mov     rcx, cs:heventAgentToWkssvc; hObject
0x180011db9  test    rcx, rcx
0x180011dbc  jz      short loc_180011DFF
0x180011dbe  call    cs:__imp_CloseHandle
0x180011dc5  nop     dword ptr [rax+rax+00h]
0x180011dca  mov     cs:heventAgentToWkssvc, 0
0x180011dd5  jmp     short loc_180011DFF
0x180011dd7  mov     rcx, cs:heventWkssvcToAgentStart; hEvent
0x180011dde  cmp     cs:vfRedirStarted, 0
0x180011de5  jnz     short loc_180011DFD
0x180011de7  call    cs:__imp_SetEvent
0x180011dee  nop     dword ptr [rax+rax+00h]
0x180011df3  mov     cs:vfRedirStarted, 1
0x180011dfd  xor     ebx, ebx
0x180011dff  mov     eax, ebx
0x180011e01  add     rsp, 20h
0x180011e05  pop     rbx
0x180011e06  retn
```
