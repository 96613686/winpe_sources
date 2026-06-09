# CACHED_USER_SID::~CACHED_USER_SID(void)

- ea: `0x180002578`
- end: `0x18000257f`
- name: `??1CACHED_USER_SID@@QEAA@XZ`
- size: `7`
- prototype: `void __fastcall(CACHED_USER_SID *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180002588`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002578`

## pseudocode

```c
// attributes: thunk
void __fastcall CACHED_USER_SID::~CACHED_USER_SID(CACHED_USER_SID *this)
{
  BUFFER::~BUFFER(this);
}

```

## disassembly

```asm
0x180002578  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
