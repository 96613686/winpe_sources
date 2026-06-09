# CAccountDisplayString::~CAccountDisplayString(void)

- ea: `0x180004d50`
- end: `0x180004d58`
- name: `??1CAccountDisplayString@@QEAA@XZ`
- size: `8`
- prototype: `void __fastcall(CAccountDisplayString *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dd16`
- `0x18000dd28`
- `0x18000dd3a`
- `0x18000dd70`
- `0x18000dd94`

## callees

- `0x180003be0`

## pseudocode

```c
void __fastcall CAccountDisplayString::~CAccountDisplayString(void **this, void *a2)
{
  ProfNotif_HeapFree(*this, a2);
}

```

## disassembly

```asm
0x180004d50  mov     rcx, [rcx]; lpMem
0x180004d53  jmp     ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
```
