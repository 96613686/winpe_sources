# exception::~exception(void)

- ea: `0x18000247e`
- end: `0x180002484`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001bf0`
- `0x180001c08`
- `0x180001c50`
- `0x180001c90`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x18000247e`

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
0x18000247e  jmp     cs:__imp_??1exception@@UEAA@XZ
```
