# exception::~exception(void)

- ea: `0x1400018f5`
- end: `0x1400018fb`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x14000127c`
- `0x140001294`
- `0x1400012a0`
- `0x1400012e0`
- `0x1400039f4`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1400018f5`

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
0x1400018f5  jmp     cs:__imp_??1exception@@UEAA@XZ
```
