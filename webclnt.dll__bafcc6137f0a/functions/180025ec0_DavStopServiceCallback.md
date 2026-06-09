# DavStopServiceCallback

- ea: `0x180025ec0`
- end: `0x180025f08`
- name: `DavStopServiceCallback`
- size: `72`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180025bf8`
- `0x180025ec0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025ef2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025ef2`
- `KERNEL32!UnregisterWait` at `0x180025ed5`
- `KERNEL32!UnregisterWait` at `0x180025ed5`

## pseudocode

```c
int DavStopServiceCallback()
{
  int result; // eax

  result = DavServiceStop();
  if ( g_DavwaitObject )
  {
    result = UnregisterWait(g_DavwaitObject);
    g_DavwaitObject = 0;
  }
  if ( g_DavstopServiceEvent )
  {
    result = CloseHandle(g_DavstopServiceEvent);
    g_DavstopServiceEvent = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180025ec0  sub     rsp, 28h
0x180025ec4  call    DavServiceStop
0x180025ec9  mov     rcx, cs:g_DavwaitObject; WaitHandle
0x180025ed0  test    rcx, rcx
0x180025ed3  jz      short loc_180025EE6
0x180025ed5  call    cs:__imp_UnregisterWait
0x180025edb  mov     cs:g_DavwaitObject, 0
0x180025ee6  mov     rcx, cs:g_DavstopServiceEvent; hObject
0x180025eed  test    rcx, rcx
0x180025ef0  jz      short loc_180025F03
0x180025ef2  call    cs:__imp_CloseHandle
0x180025ef8  mov     cs:g_DavstopServiceEvent, 0
0x180025f03  add     rsp, 28h
0x180025f07  retn
```
