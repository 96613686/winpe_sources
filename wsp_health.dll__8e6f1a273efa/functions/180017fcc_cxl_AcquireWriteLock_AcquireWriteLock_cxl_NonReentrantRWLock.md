# cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)

- ea: `0x180017fcc`
- end: `0x18001801f`
- name: `??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z`
- size: `83`
- prototype: `_QWORD(cxl::AcquireWriteLock *__hidden this, struct cxl::NonReentrantRWLock *)`
- caller_count: `43`
- callee_count: `2`
- tags: ``

## callers

- `0x1800187c4`
- `0x180018e10`
- `0x1800191d0`
- `0x1800194bc`
- `0x18001962c`
- `0x18001a474`
- `0x18001abe0`
- `0x18001bd80`
- `0x18001d398`
- `0x18001d770`
- `0x18001dd30`
- `0x18001ea44`
- `0x18001eae0`
- `0x18001eb34`
- `0x18001ec38`
- `0x18001f2e0`
- `0x1800275a0`
- `0x1800276f0`
- `0x180027840`
- `0x180027990`
- `0x180027ae0`
- `0x180027c30`
- `0x180027d80`
- `0x180027ee0`
- `0x180029304`
- `0x180032b38`
- `0x180034fd0`
- `0x1800362fc`
- `0x1800394b4`
- `0x18003b874`
- `0x180055fc0`
- `0x180058e44`
- `0x180071464`
- `0x180075728`
- `0x180075854`
- `0x180075980`
- `0x180075a68`
- `0x18007c88c`
- `0x18007c994`
- `0x18007d2f0`
- `0x18007d7e8`
- `0x18007d9f8`
- `0x18007db24`

## callees

- `0x180017fcc`
- `0x18001aef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017ff1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017ff1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ffd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017ffd`

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
0x180017fcc  mov     [rsp+arg_0], rbx
0x180017fd1  push    rdi
0x180017fd2  sub     rsp, 20h
0x180017fd6  mov     qword ptr [rcx+8], 0
0x180017fde  mov     rdi, rdx
0x180017fe1  mov     rbx, rcx
0x180017fe4  test    rdx, rdx
0x180017fe7  jz      short loc_180018010
0x180017fe9  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x180017fee  mov     rcx, rdi; SRWLock
0x180017ff1  call    cs:__imp_AcquireSRWLockExclusive
0x180017ff8  nop     dword ptr [rax+rax+00h]
0x180017ffd  call    cs:__imp_GetCurrentThreadId
0x180018004  nop     dword ptr [rax+rax+00h]
0x180018009  mov     [rdi+8], eax
0x18001800c  mov     [rbx+8], rdi
0x180018010  mov     rax, rbx
0x180018013  mov     rbx, [rsp+28h+arg_0]
0x180018018  add     rsp, 20h
0x18001801c  pop     rdi
0x18001801d  retn
```
