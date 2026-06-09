# _CoCreateAU_::_1_::dtor$0

- ea: `0x1400217c5`
- end: `0x1400217d1`
- name: `_CoCreateAU_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001b38`

## pseudocode

```c
__int64 __fastcall CoCreateAU_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return XInterface<IUnknown>::~XInterface<IUnknown>(a2 + 48);
}

```

## disassembly

```asm
0x1400217c5  lea     rcx, [rdx+30h]
0x1400217cc  jmp     ??1?$XInterface@UIUnknown@@@@QEAA@XZ; XInterface<IUnknown>::~XInterface<IUnknown>(void)
```
