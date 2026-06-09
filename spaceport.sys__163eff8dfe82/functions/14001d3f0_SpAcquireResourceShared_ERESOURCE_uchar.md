# SpAcquireResourceShared(_ERESOURCE *,uchar)

- ea: `0x14001d3f0`
- end: `0x14001d469`
- name: `?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z`
- size: `121`
- prototype: `void __fastcall(PERESOURCE Resource, unsigned __int8)`
- caller_count: `51`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d738`
- `0x14002d9a0`
- `0x14002de54`
- `0x14002f680`
- `0x14003b080`
- `0x14003b6d0`
- `0x14003c778`
- `0x14008d854`
- `0x140092d74`
- `0x140094680`
- `0x140094e14`
- `0x1400951a0`
- `0x140095338`
- `0x140095a54`
- `0x140095d18`
- `0x1400963a4`
- `0x140096b90`
- `0x14009702c`
- `0x140099414`
- `0x14009b068`
- `0x14009b300`
- `0x14009c9d8`
- `0x1400a0b40`
- `0x1400a2030`
- `0x1400a3af8`
- `0x1400a5780`
- `0x1400a5d68`
- `0x1400a7294`
- `0x1400a89b0`
- `0x1400ab4f8`
- `0x1400accb8`
- `0x1400ad8d8`
- `0x1400adc34`
- `0x1400adff8`
- `0x1400ae6c4`
- `0x1400ae9f4`
- `0x1400aebc0`
- `0x1400aefcc`
- `0x1400af3dc`
- `0x1400af5a8`
- `0x1400afca4`
- `0x1400b41a0`
- `0x1400b44c0`
- `0x1400b4580`
- `0x1400b4640`
- `0x1400b4890`
- `0x1400b54c0`
- `0x1400b5ca0`
- `0x1400b5e60`
- `0x1400b7610`

## callees

- `0x14001d3f0`
- `0x14002c3ec`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d414`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d414`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14001d45b`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14001d45b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001d42a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001d42a`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001d405`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14006b40e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001d405`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14006b40e`

## pseudocode

```c

```
