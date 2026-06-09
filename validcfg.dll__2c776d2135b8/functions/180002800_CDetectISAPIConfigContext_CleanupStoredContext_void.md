# CDetectISAPIConfigContext::CleanupStoredContext(void)

- ea: `0x180002800`
- end: `0x180002805`
- name: `?CleanupStoredContext@CDetectISAPIConfigContext@@UEAAXXZ`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x180001820`

## pseudocode

```c
// attributes: thunk
void __cdecl CDetectISAPIConfigContext::CleanupStoredContext(void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180002800  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
