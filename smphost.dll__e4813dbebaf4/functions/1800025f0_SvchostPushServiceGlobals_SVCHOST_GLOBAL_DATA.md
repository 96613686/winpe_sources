# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x1800025f0`
- end: `0x1800025f8`
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
  g_SvchostGlobals = a1;
}

```

## disassembly

```asm
0x1800025f0  mov     cs:?g_SvchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rcx; _SVCHOST_GLOBAL_DATA * g_SvchostGlobals
0x1800025f7  retn
```
