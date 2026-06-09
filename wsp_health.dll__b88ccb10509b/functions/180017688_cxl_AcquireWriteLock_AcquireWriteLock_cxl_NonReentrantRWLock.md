# cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)

- ea: `0x180017688`
- end: `0x1800176ce`
- name: `??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z`
- size: `70`
- prototype: `_QWORD(cxl::AcquireWriteLock *__hidden this, struct cxl::NonReentrantRWLock *)`
- caller_count: `43`
- callee_count: `2`
- tags: ``

## callers

- `0x180017e38`
- `0x180018470`
- `0x18001880c`
- `0x180018aec`
- `0x180018c5c`
- `0x180019a5c`
- `0x18001a17c`
- `0x18001b280`
- `0x18001c840`
- `0x18001cc00`
- `0x18001d190`
- `0x18001de8c`
- `0x18001df20`
- `0x18001df70`
- `0x18001e074`
- `0x18001e6f8`
- `0x180026950`
- `0x180026aa0`
- `0x180026bf0`
- `0x180026d40`
- `0x180026e90`
- `0x180026fe0`
- `0x180027130`
- `0x180027290`
- `0x1800286a0`
- `0x180031aa8`
- `0x180033ea0`
- `0x18003516c`
- `0x1800380d4`
- `0x18003a434`
- `0x1800545b0`
- `0x180057754`
- `0x18006fb34`
- `0x180073910`
- `0x180073a34`
- `0x180073b60`
- `0x180073c48`
- `0x18007a724`
- `0x18007a824`
- `0x18007b158`
- `0x18007b5f8`
- `0x18007b7c4`
- `0x18007b8f0`

## callees

- `0x180017688`
- `0x18001a470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800176ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800176ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800176b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800176b3`

## pseudocode

```c
cxl::AcquireWriteLock *__fastcall cxl::AcquireWriteLock::AcquireWriteLock(cxl::AcquireWriteLock *this, RTL_SRWLOCK *a2)
{
  *((_QWORD *)this + 1) = 0;
  if ( a2 )
  {
    cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(this);
    AcquireSRWLockExclusive(a2);
    LODWORD(a2[1].Ptr) = GetCurrentThreadId();
    *((_QWORD *)this + 1) = a2;
  }
  return this;
}

```

## disassembly

```asm
0x180017688  mov     [rsp+arg_0], rbx
0x18001768d  push    rdi
0x18001768e  sub     rsp, 20h
0x180017692  mov     qword ptr [rcx+8], 0
0x18001769a  mov     rdi, rdx
0x18001769d  mov     rbx, rcx
0x1800176a0  test    rdx, rdx
0x1800176a3  jz      short loc_1800176C0
0x1800176a5  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x1800176aa  mov     rcx, rdi; SRWLock
0x1800176ad  call    cs:__imp_AcquireSRWLockExclusive
0x1800176b3  call    cs:__imp_GetCurrentThreadId
0x1800176b9  mov     [rdi+8], eax
0x1800176bc  mov     [rbx+8], rdi
0x1800176c0  mov     rax, rbx
0x1800176c3  mov     rbx, [rsp+28h+arg_0]
0x1800176c8  add     rsp, 20h
0x1800176cc  pop     rdi
0x1800176cd  retn
```
