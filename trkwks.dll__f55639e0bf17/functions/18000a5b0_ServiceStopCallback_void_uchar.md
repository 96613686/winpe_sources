# ServiceStopCallback(void *,uchar)

- ea: `0x18000a5b0`
- end: `0x18000a610`
- name: `?ServiceStopCallback@@YAXPEAXE@Z`
- size: `96`
- prototype: `void __fastcall(CTrkWksSvc *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001d4c`
- `0x18000f730`

## callees

- `0x18000a5b0`
- `0x18000a618`
- `0x18000d864`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5f3`
- `KERNEL32!UnregisterWaitEx` at `0x18000a5d6`
- `KERNEL32!UnregisterWaitEx` at `0x18000a5d6`

## pseudocode

```c
void __fastcall ServiceStopCallback(CTrkWksSvc *a1)
{
  int *v1; // rcx

  if ( a1 )
  {
    CTrkRpcConfig::_fInitialized = 0;
    CTrkWksSvc::Release(a1);
  }
  if ( g_waitObject )
  {
    UnregisterWaitEx(g_waitObject, 0);
    g_waitObject = 0;
  }
  v1 = (int *)g_stopServiceEvent;
  if ( g_stopServiceEvent )
  {
    CloseHandle(g_stopServiceEvent);
    g_stopServiceEvent = 0;
  }
  CommonDllUnInit(v1);
}

```

## disassembly

```asm
0x18000a5b0  sub     rsp, 38h
0x18000a5b4  test    rcx, rcx
0x18000a5b7  jz      short loc_18000A5C8
0x18000a5b9  mov     cs:?_fInitialized@CTrkRpcConfig@@1HA, 0; int CTrkRpcConfig::_fInitialized
0x18000a5c3  call    ?Release@CTrkWksSvc@@QEAAKXZ; CTrkWksSvc::Release(void)
0x18000a5c8  mov     rcx, cs:?g_waitObject@@3PEAXEA; WaitHandle
0x18000a5cf  test    rcx, rcx
0x18000a5d2  jz      short loc_18000A5E7
0x18000a5d4  xor     edx, edx; CompletionEvent
0x18000a5d6  call    cs:__imp_UnregisterWaitEx
0x18000a5dc  mov     cs:?g_waitObject@@3PEAXEA, 0; void * g_waitObject
0x18000a5e7  mov     rcx, cs:?g_stopServiceEvent@@3PEAXEA; hObject
0x18000a5ee  test    rcx, rcx
0x18000a5f1  jz      short loc_18000A604
0x18000a5f3  call    cs:__imp_CloseHandle
0x18000a5f9  mov     cs:?g_stopServiceEvent@@3PEAXEA, 0; void * g_stopServiceEvent
0x18000a604  call    ?CommonDllUnInit@@YAXPEAJ@Z; CommonDllUnInit(long *)
0x18000a609  jmp     short $+2
0x18000a60b  add     rsp, 38h
0x18000a60f  retn
0x1800116fc  push    rbp
0x1800116fe  sub     rsp, 20h
0x180011702  mov     rbp, rdx
0x180011705  mov     eax, 1
0x18001170a  add     rsp, 20h
0x18001170e  pop     rbp
0x18001170f  retn
```
