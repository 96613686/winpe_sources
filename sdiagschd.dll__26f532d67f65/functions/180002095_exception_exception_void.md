# exception::~exception(void)

- ea: `0x180002095`
- end: `0x18000209b`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001288`
- `0x1800012a0`
- `0x1800012e0`
- `0x180001320`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180002095`

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
0x180002095  jmp     cs:__imp_??1exception@@UEAA@XZ
```
