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
- `0x14002f610`
- `0x14003afc0`
- `0x14003b610`
- `0x14003c6b8`
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
- `0x14009c9bc`
- `0x1400a0a10`
- `0x1400a1f00`
- `0x1400a39c8`
- `0x1400a5650`
- `0x1400a5c38`
- `0x1400a7164`
- `0x1400a8820`
- `0x1400ab358`
- `0x1400acb18`
- `0x1400ad738`
- `0x1400ada94`
- `0x1400ade58`
- `0x1400ae524`
- `0x1400ae854`
- `0x1400aea20`
- `0x1400aee2c`
- `0x1400af23c`
- `0x1400af408`
- `0x1400afb04`
- `0x1400b4000`
- `0x1400b4320`
- `0x1400b43e0`
- `0x1400b44a0`
- `0x1400b46f0`
- `0x1400b5320`
- `0x1400b5b00`
- `0x1400b5cc0`
- `0x1400b7470`

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
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14006b2ce`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001d405`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14006b2ce`

## pseudocode

```c

```
