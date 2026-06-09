# mlib::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>::operator delete(void *)

- ea: `0x18000de18`
- end: `0x18000de1f`
- name: `??3?$mstring_buf@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@CAXPEAX@Z`
- size: `7`
- prototype: `void __fastcall(void *)`
- caller_count: `18`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18002e000`
- `0x18002e040`
- `0x18002e1da`
- `0x18002e220`
- `0x18002e281`
- `0x18002e2b2`
- `0x18002e350`
- `0x18002e450`
- `0x18002e570`
- `0x18002e74e`
- `0x18002e760`
- `0x18002e8f0`
- `0x18002e9a0`
- `0x18002ea60`
- `0x18002eae0`
- `0x18002ebb0`
- `0x18002ec02`
- `0x18002f172`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000de18`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
// attributes: thunk
void __fastcall mlib::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>::operator delete(void *a1)
{
  operator delete(a1);
}

```

## disassembly

```asm
0x18000de18  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
