# exception::~exception(void)

- ea: `0x180002b2c`
- end: `0x180002b32`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001bfc`
- `0x180001c14`
- `0x180001c50`
- `0x180001c90`
- `0x18000dae4`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180002b2c`

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
0x180002b2c  jmp     cs:__imp_??1exception@@UEAA@XZ
```
