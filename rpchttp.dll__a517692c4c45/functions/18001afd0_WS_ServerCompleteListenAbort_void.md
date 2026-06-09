# WS_ServerCompleteListenAbort(void *)

- ea: `0x18001afd0`
- end: `0x18001afe3`
- name: `?WS_ServerCompleteListenAbort@@YAXPEAX@Z`
- size: `19`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025010`

## pseudocode

```c
void __fastcall WS_ServerCompleteListenAbort(void *a1)
{
  (*((void (__fastcall **)(void *))pRuntimeImportTable + 85))(a1);
}

```

## disassembly

```asm
0x18001afd0  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18001afd7  mov     rax, [rax+2A8h]
0x18001afde  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
