# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x18000c830`
- end: `0x18000c838`
- name: `?SvchostPushServiceGlobals@@YAXPEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `8`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(struct _SVCHOST_GLOBAL_DATA *a1)
{
  g_svcHostGlobalData = a1;
}

```

## disassembly

```asm
0x18000c830  mov     cs:?g_svcHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rcx; _SVCHOST_GLOBAL_DATA * g_svcHostGlobalData
0x18000c837  retn
```
