# CObjectPathParser::~CObjectPathParser(void)

- ea: `0x1800144b0`
- end: `0x1800144b5`
- name: `??1CObjectPathParser@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(CObjectPathParser *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016968`

## callees

- `0x1800146fc`

## pseudocode

```c
// attributes: thunk
void __fastcall CObjectPathParser::~CObjectPathParser(CObjectPathParser *this)
{
  CObjectPathParser::Empty(this);
}

```

## disassembly

```asm
0x1800144b0  jmp     ?Empty@CObjectPathParser@@AEAAXXZ; CObjectPathParser::Empty(void)
```
