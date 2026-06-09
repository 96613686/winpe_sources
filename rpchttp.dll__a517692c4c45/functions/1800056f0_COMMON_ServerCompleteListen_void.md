# COMMON_ServerCompleteListen(void *)

- ea: `0x1800056f0`
- end: `0x180005703`
- name: `?COMMON_ServerCompleteListen@@YAXPEAX@Z`
- size: `19`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025010`

## pseudocode

```c
void __fastcall COMMON_ServerCompleteListen(void *a1)
{
  (*((void (__fastcall **)(void *))pRuntimeImportTable + 82))(a1);
}

```

## disassembly

```asm
0x1800056f0  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800056f7  mov     rax, [rax+290h]
0x1800056fe  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
