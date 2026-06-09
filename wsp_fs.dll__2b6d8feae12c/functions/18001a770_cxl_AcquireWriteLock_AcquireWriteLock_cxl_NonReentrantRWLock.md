# cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)

- ea: `0x18001a770`
- end: `0x18001a7b6`
- name: `??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z`
- size: `70`
- prototype: `_QWORD(cxl::AcquireWriteLock *__hidden this, struct cxl::NonReentrantRWLock *)`
- caller_count: `36`
- callee_count: `2`
- tags: ``

## callers

- `0x18001af20`
- `0x18001b550`
- `0x18001b8ec`
- `0x18001bbcc`
- `0x18001bd3c`
- `0x18001cb40`
- `0x18001d25c`
- `0x18001e3f0`
- `0x18001fa84`
- `0x18001fe50`
- `0x1800203e0`
- `0x180021108`
- `0x18002119c`
- `0x1800211ec`
- `0x1800212f0`
- `0x180022410`
- `0x18002a690`
- `0x18002a7e0`
- `0x18002a930`
- `0x18002aa80`
- `0x18002abd0`
- `0x18002ad20`
- `0x18002ae70`
- `0x18002afd0`
- `0x18002c3e0`
- `0x180035818`
- `0x180042e70`
- `0x1800439d4`
- `0x180044494`
- `0x180047084`
- `0x180047854`
- `0x18004f16c`
- `0x18004f310`
- `0x18004f470`
- `0x180091de0`
- `0x18009669c`

## callees

- `0x18001a770`
- `0x18001d550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a795`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a795`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a79b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a79b`

## pseudocode

```c
cxl::AcquireWriteLock *__fastcall cxl::AcquireWriteLock::AcquireWriteLock(cxl::AcquireWriteLock *this, RTL_SRWLOCK *a2)
{
  *((_QWORD *)this + 1) = 0;
  if ( a2 )
  {
    cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release();
    AcquireSRWLockExclusive(a2);
    LODWORD(a2[1].Ptr) = GetCurrentThreadId();
    *((_QWORD *)this + 1) = a2;
  }
  return this;
}

```

## disassembly

```asm
0x18001a770  mov     [rsp+arg_0], rbx
0x18001a775  push    rdi
0x18001a776  sub     rsp, 20h
0x18001a77a  mov     qword ptr [rcx+8], 0
0x18001a782  mov     rdi, rdx
0x18001a785  mov     rbx, rcx
0x18001a788  test    rdx, rdx
0x18001a78b  jz      short loc_18001A7A8
0x18001a78d  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001a792  mov     rcx, rdi; SRWLock
0x18001a795  call    cs:__imp_AcquireSRWLockExclusive
0x18001a79b  call    cs:__imp_GetCurrentThreadId
0x18001a7a1  mov     [rdi+8], eax
0x18001a7a4  mov     [rbx+8], rdi
0x18001a7a8  mov     rax, rbx
0x18001a7ab  mov     rbx, [rsp+28h+arg_0]
0x18001a7b0  add     rsp, 20h
0x18001a7b4  pop     rdi
0x18001a7b5  retn
```
