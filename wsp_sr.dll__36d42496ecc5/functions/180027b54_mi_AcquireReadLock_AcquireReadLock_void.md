# mi::AcquireReadLock::~AcquireReadLock(void)

- ea: `0x180027b54`
- end: `0x180027b5e`
- name: `??1AcquireReadLock@mi@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(PSRWLOCK *this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002bf77`
- `0x18002bfed`
- `0x18002c011`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180027b57`

## pseudocode

```c
void __fastcall mi::AcquireReadLock::~AcquireReadLock(PSRWLOCK *this)
{
  ReleaseSRWLockShared(*this);
}

```

## disassembly

```asm
0x180027b54  mov     rcx, [rcx]
0x180027b57  jmp     cs:__imp_ReleaseSRWLockShared
```
