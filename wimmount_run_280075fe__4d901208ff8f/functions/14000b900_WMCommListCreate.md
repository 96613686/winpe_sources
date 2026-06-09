# WMCommListCreate

- ea: `0x14000b900`
- end: `0x14000b932`
- name: `WMCommListCreate`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000c078`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14000b920`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000b920`

## pseudocode

```c
NTSTATUS WMCommListCreate()
{
  qword_1400061D8 = (__int64)&g_CommList;
  g_CommList = &g_CommList;
  return ExInitializeResourceLite(&stru_1400061E0);
}

```

## disassembly

```asm
0x14000b900  sub     rsp, 28h
0x14000b904  lea     rax, g_CommList
0x14000b90b  lea     rcx, stru_1400061E0; Resource
0x14000b912  mov     cs:qword_1400061D8, rax
0x14000b919  mov     cs:g_CommList, rax
0x14000b920  call    cs:__imp_ExInitializeResourceLite
0x14000b927  nop     dword ptr [rax+rax+00h]
0x14000b92c  add     rsp, 28h
0x14000b930  retn
```
