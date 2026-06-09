# StopWorkers

- ea: `0x18000a4a0`
- end: `0x18000a51e`
- name: `StopWorkers`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dd0`

## callees

- `0x18000a4a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000a506`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000a506`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a513`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4e9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a4f4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a4f4`

## pseudocode

```c
void StopWorkers()
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
0x18000a4a0  sub     rsp, 28h
0x18000a4a4  mov     eax, cs:WorkersInitialized
0x18000a4aa  cmp     eax, 1
0x18000a4ad  jnz     short loc_18000A519
0x18000a4af  mov     rcx, cs:WorkQueueTimer; hObject
0x18000a4b6  mov     cs:WorkersInitialized, 0
0x18000a4c0  test    rcx, rcx
0x18000a4c3  jz      short loc_18000A4CB
0x18000a4c5  call    cs:__imp_CloseHandle
0x18000a4cb  mov     rcx, cs:WorkQueuePort; hObject
0x18000a4d2  test    rcx, rcx
0x18000a4d5  jz      short loc_18000A4DD
0x18000a4d7  call    cs:__imp_CloseHandle
0x18000a4dd  mov     rcx, cs:AlertableThreadSemaphore; hObject
0x18000a4e4  test    rcx, rcx
0x18000a4e7  jz      short loc_18000A4EF
0x18000a4e9  call    cs:__imp_CloseHandle
0x18000a4ef  mov     ecx, 3E8h; dwMilliseconds
0x18000a4f4  call    cs:__imp_Sleep
0x18000a4fa  mov     rcx, cs:AlertableWorkerHeap; hHeap
0x18000a501  test    rcx, rcx
0x18000a504  jz      short loc_18000A50C
0x18000a506  call    cs:__imp_HeapDestroy
0x18000a50c  lea     rcx, AlertableWorkQueueLock; lpCriticalSection
0x18000a513  call    cs:__imp_DeleteCriticalSection
0x18000a519  add     rsp, 28h
0x18000a51d  retn
```
