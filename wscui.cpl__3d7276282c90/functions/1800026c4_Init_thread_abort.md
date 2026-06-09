# _Init_thread_abort

- ea: `0x1800026c4`
- end: `0x180002700`
- name: `_Init_thread_abort`
- size: `60`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ae0c`
- `0x18000ae1e`
- `0x18000ae30`
- `0x18000ae42`
- `0x18000ae54`
- `0x18000ae66`
- `0x18000ae78`
- `0x18000ae8a`
- `0x18000ae9c`
- `0x18000aeae`
- `0x18000aec0`
- `0x18000aed2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800026e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800026e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800026d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800026d4`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800026f9`

## pseudocode

```c
void __fastcall Init_thread_abort(_DWORD *a1)
{
  AcquireSRWLockExclusive(&SRWLock);
  *a1 = 0;
  ReleaseSRWLockExclusive(&SRWLock);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x1800026c4  push    rbx
0x1800026c6  sub     rsp, 20h
0x1800026ca  mov     rbx, rcx
0x1800026cd  lea     rcx, SRWLock; SRWLock
0x1800026d4  call    cs:__imp_AcquireSRWLockExclusive
0x1800026da  lea     rcx, SRWLock; SRWLock
0x1800026e1  mov     dword ptr [rbx], 0
0x1800026e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800026ed  lea     rcx, ConditionVariable
0x1800026f4  add     rsp, 20h
0x1800026f8  pop     rbx
0x1800026f9  jmp     cs:__imp_WakeAllConditionVariable
```
