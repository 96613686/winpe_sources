# exception::~exception(void)

- ea: `0x180002106`
- end: `0x18000210c`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ff4`
- `0x180002090`
- `0x180002670`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180002106`

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
0x180002106  jmp     cs:__imp_??1exception@@UEAA@XZ
```
