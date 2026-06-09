# StopWorkers()

- ea: `0x1000a518`
- end: `0x1000a582`
- name: `_StopWorkers@0`
- size: `106`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10004fe6`

## callees

- `0x1000a518`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1000a570`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1000a570`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1000a57b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1000a57b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000a535`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000a545`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000a555`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000a535`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000a545`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000a555`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1000a560`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1000a560`

## pseudocode

```c
void __stdcall StopWorkers()
{
  if ( WorkersInitialized == 1 )
  {
    WorkersInitialized = 0;
    if ( WorkQueueTimer )
      CloseHandle(WorkQueueTimer);
    if ( WorkQueuePort )
      CloseHandle(WorkQueuePort);
    if ( AlertableThreadSemaphore )
      CloseHandle(AlertableThreadSemaphore);
    Sleep(0x3E8u);
    if ( AlertableWorkerHeap )
      HeapDestroy(AlertableWorkerHeap);
    DeleteCriticalSection(&AlertableWorkQueueLock);
  }
}

```

## disassembly

```asm
0x1000a518  cmp     _WorkersInitialized, 1
0x1000a51f  jnz     short locret_1000A581
0x1000a521  mov     eax, _WorkQueueTimer
0x1000a526  mov     _WorkersInitialized, 0
0x1000a530  test    eax, eax
0x1000a532  jz      short loc_1000A53B
0x1000a534  push    eax; hObject
0x1000a535  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000a53b  mov     eax, _WorkQueuePort
0x1000a540  test    eax, eax
0x1000a542  jz      short loc_1000A54B
0x1000a544  push    eax; hObject
0x1000a545  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000a54b  mov     eax, _AlertableThreadSemaphore
0x1000a550  test    eax, eax
0x1000a552  jz      short loc_1000A55B
0x1000a554  push    eax; hObject
0x1000a555  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000a55b  push    3E8h; dwMilliseconds
0x1000a560  call    ds:__imp__Sleep@4; Sleep(x)
0x1000a566  mov     eax, _AlertableWorkerHeap
0x1000a56b  test    eax, eax
0x1000a56d  jz      short loc_1000A576
0x1000a56f  push    eax; hHeap
0x1000a570  call    ds:__imp__HeapDestroy@4; HeapDestroy(x)
0x1000a576  push    offset _AlertableWorkQueueLock; lpCriticalSection
0x1000a57b  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1000a581  retn
```
