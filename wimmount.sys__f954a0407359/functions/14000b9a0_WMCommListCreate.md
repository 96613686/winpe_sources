# WMCommListCreate

- ea: `0x14000b9a0`
- end: `0x14000b9d2`
- name: `WMCommListCreate`
- size: `50`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000c078`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14000b9c0`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000b9c0`

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
0x14000b9a0  sub     rsp, 28h
0x14000b9a4  lea     rax, g_CommList
0x14000b9ab  lea     rcx, stru_1400061E0; Resource
0x14000b9b2  mov     cs:qword_1400061D8, rax
0x14000b9b9  mov     cs:g_CommList, rax
0x14000b9c0  call    cs:__imp_ExInitializeResourceLite
0x14000b9c7  nop     dword ptr [rax+rax+00h]
0x14000b9cc  add     rsp, 28h
0x14000b9d0  retn
```
