# NumaManager::SetWorkerProcessAffinity(void)

- ea: `0x14026736c`
- end: `0x140267588`
- name: `?SetWorkerProcessAffinity@NumaManager@@AEAAXXZ`
- size: `540`
- prototype: `void __fastcall(NumaManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140267160`

## callees

- `0x140007228`
- `0x14004ad1c`
- `0x140066eec`
- `0x140083990`
- `0x14009061c`
- `0x14011ea40`
- `0x140139bc0`
- `0x14026736c`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x140267425`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x140267425`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140267411`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140267411`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1402674f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1402674f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140267399`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140267399`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x14026744c`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x14026744c`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaNodeProcessorMaskEx` at `0x1402673f1`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaNodeProcessorMaskEx` at `0x1402673f1`
- `api-ms-win-core-processtopology-private-l1-1-0!SetProcessGroupAffinity` at `0x14026750f`
- `api-ms-win-core-processtopology-private-l1-1-0!SetProcessGroupAffinity` at `0x14026750f`

## string_xrefs

- `0x140267560`: `onecore\vm\common\vml\VmMemory.h`
- `0x140267576`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c

```
