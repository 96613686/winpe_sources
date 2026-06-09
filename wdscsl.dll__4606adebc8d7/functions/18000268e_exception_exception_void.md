# exception::~exception(void)

- ea: `0x18000268e`
- end: `0x180002694`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e00`
- `0x180001e18`
- `0x180001e60`
- `0x180001ea0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x18000268e`

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
0x18000268e  jmp     cs:__imp_??1exception@@UEAA@XZ
```
