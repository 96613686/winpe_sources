# WsCSCWantToStopRedir

- ea: `0x18002c224`
- end: `0x18002c35d`
- name: `WsCSCWantToStopRedir`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002c59c`

## callees

- `0x18002c224`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c27f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c27f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002c2e6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002c2e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c24c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c291`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c24c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c291`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002c2ca`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002c2ca`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002c260`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002c260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c272`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c321`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c33e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c272`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c321`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c33e`

## string_xrefs

- `0x18002c252`: `AgentExistsEvent`

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
0x18002c224  sub     rsp, 48h
0x18002c228  cmp     cs:vfRedirStarted, 0
0x18002c22f  jz      loc_18002C353
0x18002c235  cmp     cs:heventWkssvcToAgentStop, 0
0x18002c23d  jz      loc_18002C353
0x18002c243  mov     rcx, cs:heventAgentToWkssvc; hHandle
0x18002c24a  xor     edx, edx; dwMilliseconds
0x18002c24c  call    cs:__imp_WaitForSingleObject
0x18002c252  lea     r8, aAgentexistseve; "AgentExistsEvent"
0x18002c259  xor     edx, edx; bInheritHandle
0x18002c25b  mov     ecx, 100000h; dwDesiredAccess
0x18002c260  call    cs:__imp_OpenEventW
0x18002c266  test    rax, rax
0x18002c269  jz      loc_18002C2F8
0x18002c26f  mov     rcx, rax; hObject
0x18002c272  call    cs:__imp_CloseHandle
0x18002c278  mov     rcx, cs:heventWkssvcToAgentStop; hEvent
0x18002c27f  call    cs:__imp_SetEvent
0x18002c285  mov     rcx, cs:heventAgentToWkssvc; hHandle
0x18002c28c  mov     edx, 3A98h; dwMilliseconds
0x18002c291  call    cs:__imp_WaitForSingleObject
0x18002c297  test    eax, eax
0x18002c299  jz      short loc_18002C2EE
0x18002c29b  mov     rax, cs:heventWkssvcToAgentStop
0x18002c2a2  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18002c2a7  xor     r9d, r9d; dwMilliseconds
0x18002c2aa  mov     [rsp+48h+Handles], rax
0x18002c2af  mov     rax, cs:heventAgentToWkssvc
0x18002c2b6  xor     r8d, r8d; bWaitAll
0x18002c2b9  mov     [rsp+48h+var_10], rax
0x18002c2be  mov     [rsp+48h+bAlertable], 0; bAlertable
0x18002c2c6  lea     ecx, [r9+2]; nCount
0x18002c2ca  call    cs:__imp_WaitForMultipleObjectsEx
0x18002c2d0  cmp     eax, 1
0x18002c2d3  jnz     short loc_18002C2DF
0x18002c2d5  mov     cs:vfRedirStarted, 0
0x18002c2df  mov     rcx, cs:heventWkssvcToAgentStop; hEvent
0x18002c2e6  call    cs:__imp_ResetEvent
0x18002c2ec  jmp     short loc_18002C2F8
0x18002c2ee  mov     cs:vfRedirStarted, 0
0x18002c2f8  mov     rcx, cs:heventWkssvcToAgentStart; hObject
0x18002c2ff  test    rcx, rcx
0x18002c302  jz      short loc_18002C315
0x18002c304  call    cs:__imp_CloseHandle
0x18002c30a  mov     cs:heventWkssvcToAgentStart, 0
0x18002c315  mov     rcx, cs:heventWkssvcToAgentStop; hObject
0x18002c31c  test    rcx, rcx
0x18002c31f  jz      short loc_18002C332
0x18002c321  call    cs:__imp_CloseHandle
0x18002c327  mov     cs:heventWkssvcToAgentStop, 0
0x18002c332  mov     rcx, cs:heventAgentToWkssvc; hObject
0x18002c339  test    rcx, rcx
0x18002c33c  jz      short loc_18002C34F
0x18002c33e  call    cs:__imp_CloseHandle
0x18002c344  mov     cs:heventAgentToWkssvc, 0
0x18002c34f  xor     eax, eax
0x18002c351  jmp     short loc_18002C358
0x18002c353  mov     eax, 1Fh
0x18002c358  add     rsp, 48h
0x18002c35c  retn
```
