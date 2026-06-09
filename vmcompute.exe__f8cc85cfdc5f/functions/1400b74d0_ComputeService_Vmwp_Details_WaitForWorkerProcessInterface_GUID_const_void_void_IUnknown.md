# ComputeService::Vmwp::Details::WaitForWorkerProcessInterface(_GUID const &,void *,void *,IUnknown * *)

- ea: `0x1400b74d0`
- end: `0x1400b75fc`
- name: `?WaitForWorkerProcessInterface@Details@Vmwp@ComputeService@@YAXAEBU_GUID@@PEAX1PEAPEAUIUnknown@@@Z`
- size: `300`
- prototype: `void __fastcall(ComputeService::Vmwp::Details *__hidden this, HANDLE hProcess, void *, void *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400b6a4c`

## callees

- `0x140043ebc`
- `0x140080180`
- `0x1400b74d0`
- `0x1400c4154`
- `0x1401332f0`
- `0x140139e24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1400b75a9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1400b75a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400b74fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400b74fc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400b7543`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400b7543`

## string_xrefs

- `0x1400b7572`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x1400b758f`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x1400b75d3`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c

```
