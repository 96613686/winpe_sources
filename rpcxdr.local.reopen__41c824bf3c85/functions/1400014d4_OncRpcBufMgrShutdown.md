# OncRpcBufMgrShutdown

- ea: `0x1400014d4`
- end: `0x140001517`
- name: `OncRpcBufMgrShutdown`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140020640`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400014df`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400014f2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140001505`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400014df`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400014f2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140001505`

## pseudocode

```c
void OncRpcBufMgrShutdown()
{
  ExDeleteNPagedLookasideList(&Lookaside);
  ExDeleteNPagedLookasideList(&stru_14001A580);
  ExDeleteNPagedLookasideList(&stru_14001A600);
}

```

## disassembly

```asm
0x1400014d4  sub     rsp, 28h
0x1400014d8  lea     rcx, Lookaside; Lookaside
0x1400014df  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400014e6  nop     dword ptr [rax+rax+00h]
0x1400014eb  lea     rcx, stru_14001A580; Lookaside
0x1400014f2  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400014f9  nop     dword ptr [rax+rax+00h]
0x1400014fe  lea     rcx, stru_14001A600; Lookaside
0x140001505  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000150c  nop     dword ptr [rax+rax+00h]
0x140001511  add     rsp, 28h
0x140001515  retn
```
