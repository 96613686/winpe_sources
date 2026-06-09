# exception::~exception(void)

- ea: `0x18000281d`
- end: `0x180002823`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001c64`
- `0x180001ce0`
- `0x180003240`
- `0x180003250`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x18000281d`

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
0x18000281d  jmp     cs:__imp_??1exception@@UEAA@XZ
```
