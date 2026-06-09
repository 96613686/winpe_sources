# mi::AcquireReadLock::~AcquireReadLock(void)

- ea: `0x180027ed4`
- end: `0x180027ede`
- name: `??1AcquireReadLock@mi@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(mi::AcquireReadLock *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002c46e`
- `0x18002c4e4`
- `0x18002c508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180027ed7`

## pseudocode

```c
void __fastcall mi::AcquireReadLock::~AcquireReadLock(PSRWLOCK *this)
{
  ReleaseSRWLockShared(*this);
}

```

## disassembly

```asm
0x180027ed4  mov     rcx, [rcx]
0x180027ed7  jmp     cs:__imp_ReleaseSRWLockShared
```
