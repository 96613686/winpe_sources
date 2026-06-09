# WsCSCWantToStopRedir

- ea: `0x18002ea78`
- end: `0x18002ebee`
- name: `WsCSCWantToStopRedir`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002ee64`

## callees

- `0x18002ea78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002eae5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002eae5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002eb5e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002eb5e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002eaa0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002eafd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002eaa0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002eafd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002eb3c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002eb3c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002eaba`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002eaba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ead2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eba5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ebc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ead2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eba5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ebc8`

## string_xrefs

- `0x18002eaac`: `AgentExistsEvent`

## pseudocode

```c
__int64 WsCSCWantToStopRedir()
{
  HANDLE v0; // rax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( !vfRedirStarted || !heventWkssvcToAgentStop )
    return 31;
  WaitForSingleObject(heventAgentToWkssvc, 0);
  v0 = OpenEventW(0x100000u, 0, aAgentexistseve);
  if ( v0 )
  {
    CloseHandle(v0);
    SetEvent(heventWkssvcToAgentStop);
    if ( WaitForSingleObject(heventAgentToWkssvc, 0x3A98u) )
    {
      Handles[0] = heventWkssvcToAgentStop;
      Handles[1] = heventAgentToWkssvc;
      if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0, 0) == 1 )
        vfRedirStarted = 0;
      ResetEvent(heventWkssvcToAgentStop);
    }
    else
    {
      vfRedirStarted = 0;
    }
  }
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
  return 0;
}

```

## disassembly

```asm
0x18002ea78  sub     rsp, 48h
0x18002ea7c  cmp     cs:vfRedirStarted, 0
0x18002ea83  jz      loc_18002EBE3
0x18002ea89  cmp     cs:heventWkssvcToAgentStop, 0
0x18002ea91  jz      loc_18002EBE3
0x18002ea97  mov     rcx, cs:heventAgentToWkssvc; hHandle
0x18002ea9e  xor     edx, edx; dwMilliseconds
0x18002eaa0  call    cs:__imp_WaitForSingleObject
0x18002eaa7  nop     dword ptr [rax+rax+00h]
0x18002eaac  lea     r8, aAgentexistseve; "AgentExistsEvent"
0x18002eab3  xor     edx, edx; bInheritHandle
0x18002eab5  mov     ecx, 100000h; dwDesiredAccess
0x18002eaba  call    cs:__imp_OpenEventW
0x18002eac1  nop     dword ptr [rax+rax+00h]
0x18002eac6  test    rax, rax
0x18002eac9  jz      loc_18002EB76
0x18002eacf  mov     rcx, rax; hObject
0x18002ead2  call    cs:__imp_CloseHandle
0x18002ead9  nop     dword ptr [rax+rax+00h]
0x18002eade  mov     rcx, cs:heventWkssvcToAgentStop; hEvent
0x18002eae5  call    cs:__imp_SetEvent
0x18002eaec  nop     dword ptr [rax+rax+00h]
0x18002eaf1  mov     rcx, cs:heventAgentToWkssvc; hHandle
0x18002eaf8  mov     edx, 3A98h; dwMilliseconds
0x18002eafd  call    cs:__imp_WaitForSingleObject
0x18002eb04  nop     dword ptr [rax+rax+00h]
0x18002eb09  test    eax, eax
0x18002eb0b  jz      short loc_18002EB6C
0x18002eb0d  mov     rax, cs:heventWkssvcToAgentStop
0x18002eb14  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18002eb19  xor     r9d, r9d; dwMilliseconds
0x18002eb1c  mov     [rsp+48h+Handles], rax
0x18002eb21  mov     rax, cs:heventAgentToWkssvc
0x18002eb28  xor     r8d, r8d; bWaitAll
0x18002eb2b  mov     [rsp+48h+var_10], rax
0x18002eb30  mov     [rsp+48h+bAlertable], 0; bAlertable
0x18002eb38  lea     ecx, [r9+2]; nCount
0x18002eb3c  call    cs:__imp_WaitForMultipleObjectsEx
0x18002eb43  nop     dword ptr [rax+rax+00h]
0x18002eb48  cmp     eax, 1
0x18002eb4b  jnz     short loc_18002EB57
0x18002eb4d  mov     cs:vfRedirStarted, 0
0x18002eb57  mov     rcx, cs:heventWkssvcToAgentStop; hEvent
0x18002eb5e  call    cs:__imp_ResetEvent
0x18002eb65  nop     dword ptr [rax+rax+00h]
0x18002eb6a  jmp     short loc_18002EB76
0x18002eb6c  mov     cs:vfRedirStarted, 0
0x18002eb76  mov     rcx, cs:heventWkssvcToAgentStart; hObject
0x18002eb7d  test    rcx, rcx
0x18002eb80  jz      short loc_18002EB99
0x18002eb82  call    cs:__imp_CloseHandle
0x18002eb89  nop     dword ptr [rax+rax+00h]
0x18002eb8e  mov     cs:heventWkssvcToAgentStart, 0
0x18002eb99  mov     rcx, cs:heventWkssvcToAgentStop; hObject
0x18002eba0  test    rcx, rcx
0x18002eba3  jz      short loc_18002EBBC
0x18002eba5  call    cs:__imp_CloseHandle
0x18002ebac  nop     dword ptr [rax+rax+00h]
0x18002ebb1  mov     cs:heventWkssvcToAgentStop, 0
0x18002ebbc  mov     rcx, cs:heventAgentToWkssvc; hObject
0x18002ebc3  test    rcx, rcx
0x18002ebc6  jz      short loc_18002EBDF
0x18002ebc8  call    cs:__imp_CloseHandle
0x18002ebcf  nop     dword ptr [rax+rax+00h]
0x18002ebd4  mov     cs:heventAgentToWkssvc, 0
0x18002ebdf  xor     eax, eax
0x18002ebe1  jmp     short loc_18002EBE8
0x18002ebe3  mov     eax, 1Fh
0x18002ebe8  add     rsp, 48h
0x18002ebec  retn
```
