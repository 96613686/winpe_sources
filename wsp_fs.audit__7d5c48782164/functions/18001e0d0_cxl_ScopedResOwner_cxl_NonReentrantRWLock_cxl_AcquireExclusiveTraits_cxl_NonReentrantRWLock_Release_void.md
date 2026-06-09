# cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)

- ea: `0x18001e0d0`
- end: `0x18001e12d`
- name: `?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ`
- size: `93`
- prototype: ``
- caller_count: `38`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b198`
- `0x18001b944`
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

- `0x180016fb8`
- `0x18001e0d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e10d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e10d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e0e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e0e6`

## pseudocode

```c
void __fastcall cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    if ( *(_DWORD *)(v1 + 8) != GetCurrentThreadId() )
      cxl::Debug::StopIfIsDebuggedOrCrash(1u);
    *(_DWORD *)(v1 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v1);
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18001e0d0  mov     [rsp+arg_0], rbx
0x18001e0d5  push    rdi
0x18001e0d6  sub     rsp, 20h
0x18001e0da  mov     rbx, [rcx+8]
0x18001e0de  mov     rdi, rcx
0x18001e0e1  test    rbx, rbx
0x18001e0e4  jz      short loc_18001E121
0x18001e0e6  call    cs:__imp_GetCurrentThreadId
0x18001e0ed  nop     dword ptr [rax+rax+00h]
0x18001e0f2  mov     edx, [rbx+8]
0x18001e0f5  cmp     edx, eax
0x18001e0f7  jz      short loc_18001E103
0x18001e0f9  mov     ecx, 1; unsigned int
0x18001e0fe  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001e103  mov     rcx, rbx; SRWLock
0x18001e106  mov     dword ptr [rbx+8], 0
0x18001e10d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e114  nop     dword ptr [rax+rax+00h]
0x18001e119  mov     qword ptr [rdi+8], 0
0x18001e121  mov     rbx, [rsp+28h+arg_0]
0x18001e126  add     rsp, 20h
0x18001e12a  pop     rdi
0x18001e12b  retn
```
