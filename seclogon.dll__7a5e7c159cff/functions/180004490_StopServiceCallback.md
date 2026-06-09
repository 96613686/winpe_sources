# StopServiceCallback

- ea: `0x180004490`
- end: `0x1800044e0`
- name: `StopServiceCallback`
- size: `80`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800042d4`
- `0x180004490`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ca`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800044ad`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800044ad`

## pseudocode

```c
int StopServiceCallback()
{
  int result; // eax

  result = ServiceStop(g_fShutdown, 0);
  if ( g_waitObject )
  {
    result = UnregisterWait(g_waitObject);
    g_waitObject = 0;
  }
  if ( g_stopServiceEvent )
  {
    result = CloseHandle(g_stopServiceEvent);
    g_stopServiceEvent = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004490  sub     rsp, 28h
0x180004494  mov     ecx, cs:g_fShutdown
0x18000449a  xor     edx, edx
0x18000449c  call    ServiceStop
0x1800044a1  mov     rcx, cs:g_waitObject; WaitHandle
0x1800044a8  test    rcx, rcx
0x1800044ab  jz      short loc_1800044BE
0x1800044ad  call    cs:__imp_UnregisterWait
0x1800044b3  mov     cs:g_waitObject, 0
0x1800044be  mov     rcx, cs:g_stopServiceEvent; hObject
0x1800044c5  test    rcx, rcx
0x1800044c8  jz      short loc_1800044DB
0x1800044ca  call    cs:__imp_CloseHandle
0x1800044d0  mov     cs:g_stopServiceEvent, 0
0x1800044db  add     rsp, 28h
0x1800044df  retn
```
