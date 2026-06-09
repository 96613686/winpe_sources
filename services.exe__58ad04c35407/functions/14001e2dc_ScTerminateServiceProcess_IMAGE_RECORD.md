# ScTerminateServiceProcess(_IMAGE_RECORD *)

- ea: `0x14001e2dc`
- end: `0x14001e4cc`
- name: `?ScTerminateServiceProcess@@YAKPEAU_IMAGE_RECORD@@@Z`
- size: `496`
- prototype: `unsigned int __fastcall(struct _IMAGE_RECORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14002a54c`

## callees

- `0x140004c58`
- `0x14001e2dc`
- `0x14001e4d4`
- `0x14001f99c`
- `0x140071b8c`
- `0x140071c2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001e332`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001e3fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001e48f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001e332`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001e3fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001e48f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14001e3ee`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14001e480`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14001e3ee`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14001e480`

## pseudocode

```c

```
