# WJCloseAutoJoinTriggerEventTimer

- ea: `0x18002d974`
- end: `0x18002d9d3`
- name: `WJCloseAutoJoinTriggerEventTimer`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001eb30`
- `0x18002e6ac`

## callees

- `0x18002d974`
- `0x18002da9c`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002d990`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002d9c1`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002d990`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002d9c1`

## string_xrefs

- `0x18002d989`: `AutoJoinSvc/%s: Canceling thread pool timer to write the auto join trigger event.`
- `0x18002d9ba`: `AutoJoinSvc/%s: Thread pool timer to write the auto join trigger event is cancelled.`

## pseudocode

```c
__int64 WJCloseAutoJoinTriggerEventTimer()
{
  __int64 result; // rax

  if ( g_AutoJoinTriggerEventTimer )
  {
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Canceling thread pool timer to write the auto join trigger event.",
      L"WJCloseAutoJoinTriggerEventTimer");
    WJCloseThreadPoolTimer(g_AutoJoinTriggerEventTimer);
    g_AutoJoinTriggerEventTimer = 0;
    return DsrWriteAutoJoinSvcDebugEvent(
             L"AutoJoinSvc/%s: Thread pool timer to write the auto join trigger event is cancelled.",
             L"WJCloseAutoJoinTriggerEventTimer");
  }
  return result;
}

```

## disassembly

```asm
0x18002d974  sub     rsp, 28h
0x18002d978  cmp     cs:g_AutoJoinTriggerEventTimer, 0
0x18002d980  jz      short loc_18002D9CD
0x18002d982  lea     rdx, aWjcloseautojoi; "WJCloseAutoJoinTriggerEventTimer"
0x18002d989  lea     rcx, aAutojoinsvcSCa_0; "AutoJoinSvc/%s: Canceling thread pool t"...
0x18002d990  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002d997  nop     dword ptr [rax+rax+00h]
0x18002d99c  mov     rcx, cs:g_AutoJoinTriggerEventTimer; pti
0x18002d9a3  call    WJCloseThreadPoolTimer
0x18002d9a8  lea     rdx, aWjcloseautojoi; "WJCloseAutoJoinTriggerEventTimer"
0x18002d9af  mov     cs:g_AutoJoinTriggerEventTimer, 0
0x18002d9ba  lea     rcx, aAutojoinsvcSTh_2; "AutoJoinSvc/%s: Thread pool timer to wr"...
0x18002d9c1  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002d9c8  nop     dword ptr [rax+rax+00h]
0x18002d9cd  add     rsp, 28h
0x18002d9d1  retn
```
