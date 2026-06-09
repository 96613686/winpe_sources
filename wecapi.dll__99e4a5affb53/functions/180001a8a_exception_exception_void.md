# exception::~exception(void)

- ea: `0x180001a8a`
- end: `0x180001a90`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001230`
- `0x180001248`
- `0x180001260`
- `0x1800012a0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001a8a`

## pseudocode

```c
// attributes: thunk
void __fastcall exception::~exception(exception *this)
{
  __imp_??1exception@@UEAA@XZ(this);
}

```

## disassembly

```asm
0x180001a8a  jmp     cs:__imp_??1exception@@UEAA@XZ
```
