# cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)

- ea: `0x18001b198`
- end: `0x18001b1eb`
- name: `??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z`
- size: `83`
- prototype: `_QWORD(cxl::AcquireWriteLock *__hidden this, struct cxl::NonReentrantRWLock *)`
- caller_count: `36`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b990`
- `0x18001bfe0`
- `0x18001c3a0`
- `0x18001c68c`
- `0x18001c7fc`
- `0x18001d64c`
- `0x18001ddc0`
- `0x18001eff0`
- `0x1800206dc`
- `0x180020ab0`
- `0x180021070`
- `0x180021db0`
- `0x180021e4c`
- `0x180021ea0`
- `0x180021fa4`
- `0x1800230f0`
- `0x18002b3e0`
- `0x18002b530`
- `0x18002b680`
- `0x18002b7d0`
- `0x18002b920`
- `0x18002ba70`
- `0x18002bbc0`
- `0x18002bd20`
- `0x18002d144`
- `0x1800369b8`
- `0x1800440e4`
- `0x180044bf4`
- `0x180045634`
- `0x180048224`
- `0x180048a14`
- `0x1800501fc`
- `0x1800503a0`
- `0x180050510`
- `0x180093f40`
- `0x18009883c`

## callees

- `0x18001b198`
- `0x18001e0d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b1bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b1bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b1c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b1c9`

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
0x18001b198  mov     [rsp+arg_0], rbx
0x18001b19d  push    rdi
0x18001b19e  sub     rsp, 20h
0x18001b1a2  mov     qword ptr [rcx+8], 0
0x18001b1aa  mov     rdi, rdx
0x18001b1ad  mov     rbx, rcx
0x18001b1b0  test    rdx, rdx
0x18001b1b3  jz      short loc_18001B1DC
0x18001b1b5  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001b1ba  mov     rcx, rdi; SRWLock
0x18001b1bd  call    cs:__imp_AcquireSRWLockExclusive
0x18001b1c4  nop     dword ptr [rax+rax+00h]
0x18001b1c9  call    cs:__imp_GetCurrentThreadId
0x18001b1d0  nop     dword ptr [rax+rax+00h]
0x18001b1d5  mov     [rdi+8], eax
0x18001b1d8  mov     [rbx+8], rdi
0x18001b1dc  mov     rax, rbx
0x18001b1df  mov     rbx, [rsp+28h+arg_0]
0x18001b1e4  add     rsp, 20h
0x18001b1e8  pop     rdi
0x18001b1e9  retn
```
