# exception::exception(char const * const &)

- ea: `0x180001fcd`
- end: `0x180001fd3`
- name: `??0exception@@QEAA@AEBQEBD@Z_0`
- size: `6`
- prototype: `exception *__fastcall(exception *this, const char *const *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001134`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180001fcd`

## pseudocode

```c
// attributes: thunk
exception *__fastcall exception::exception(exception *this, const char *const *a2)
{
  return __imp_??0exception@@QEAA@AEBQEBD@Z(this, a2);
}

```

## disassembly

```asm
0x180001fcd  jmp     cs:__imp_??0exception@@QEAA@AEBQEBD@Z
```
