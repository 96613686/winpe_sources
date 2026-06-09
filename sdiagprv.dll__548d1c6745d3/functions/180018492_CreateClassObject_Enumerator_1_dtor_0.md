# _CreateClassObject_Enumerator__::_1_::dtor$0

- ea: `0x180018492`
- end: `0x18001849e`
- name: `_CreateClassObject_Enumerator__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800010b4`

## pseudocode

```c
void __fastcall CreateClassObject_Enumerator__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
}

```

## disassembly

```asm
0x180018492  mov     rcx, [rdx+30h]; Block
0x180018499  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
