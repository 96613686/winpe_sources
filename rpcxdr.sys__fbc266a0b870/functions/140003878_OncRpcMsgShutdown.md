# OncRpcMsgShutdown

- ea: `0x140003878`
- end: `0x1400038c0`
- name: `OncRpcMsgShutdown`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140020640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400038ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400038ae`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140003883`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140003896`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140003883`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140003896`

## pseudocode

```c
void OncRpcMsgShutdown()
{
  ExDeleteNPagedLookasideList(&stru_14001A700);
  ExDeleteNPagedLookasideList(&stru_14001A780);
  ExFreePoolWithTag(P, 0x544D6458u);
}

```

## disassembly

```asm
0x140003878  sub     rsp, 28h
0x14000387c  lea     rcx, stru_14001A700; Lookaside
0x140003883  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000388a  nop     dword ptr [rax+rax+00h]
0x14000388f  lea     rcx, stru_14001A780; Lookaside
0x140003896  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000389d  nop     dword ptr [rax+rax+00h]
0x1400038a2  mov     rcx, cs:P; P
0x1400038a9  mov     edx, 544D6458h; Tag
0x1400038ae  call    cs:__imp_ExFreePoolWithTag
0x1400038b5  nop     dword ptr [rax+rax+00h]
0x1400038ba  add     rsp, 28h
0x1400038be  retn
```
