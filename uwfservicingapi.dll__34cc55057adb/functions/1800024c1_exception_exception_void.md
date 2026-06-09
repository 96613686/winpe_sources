# exception::~exception(void)

- ea: `0x1800024c1`
- end: `0x1800024c7`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b40`
- `0x180001b58`
- `0x180001ba0`
- `0x180001be0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1800024c1`

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
0x1800024c1  jmp     cs:__imp_??1exception@@UEAA@XZ
```
