# exception::~exception(void)

- ea: `0x180003f28`
- end: `0x180003f2e`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d68`
- `0x180002d80`
- `0x180002dc0`
- `0x180002e00`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180003f28`

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
0x180003f28  jmp     cs:__imp_??1exception@@UEAA@XZ
```
