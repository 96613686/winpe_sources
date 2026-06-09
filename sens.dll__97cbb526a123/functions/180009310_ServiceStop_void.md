# ServiceStop(void)

- ea: `0x180009310`
- end: `0x18000933b`
- name: `?ServiceStop@@YAXXZ`
- size: `43`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007840`
- `0x180009360`

## callees

- `0x180009310`
- `0x1800093d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009325`

## pseudocode

```c
void ServiceStop(void)
{
  SensUninitialize();
  if ( g_svchostShutdownEvent )
  {
    CloseHandle(g_svchostShutdownEvent);
    g_svchostShutdownEvent = 0;
  }
}

```

## disassembly

```asm
0x180009310  sub     rsp, 28h
0x180009314  call    ?SensUninitialize@@YAHXZ; SensUninitialize(void)
0x180009319  mov     rcx, cs:?g_svchostShutdownEvent@@3PEAXEA; hObject
0x180009320  test    rcx, rcx
0x180009323  jz      short loc_180009336
0x180009325  call    cs:__imp_CloseHandle
0x18000932b  mov     cs:?g_svchostShutdownEvent@@3PEAXEA, 0; void * g_svchostShutdownEvent
0x180009336  add     rsp, 28h
0x18000933a  retn
```
