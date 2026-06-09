# cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)

- ea: `0x18001d550`
- end: `0x18001d5a0`
- name: `?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ`
- size: `80`
- prototype: ``
- caller_count: `38`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a770`
- `0x18001aed4`
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

- `0x180016830`
- `0x18001d550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d587`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d566`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d566`

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
0x18001d550  mov     [rsp+arg_0], rbx
0x18001d555  push    rdi
0x18001d556  sub     rsp, 20h
0x18001d55a  mov     rbx, [rcx+8]
0x18001d55e  mov     rdi, rcx
0x18001d561  test    rbx, rbx
0x18001d564  jz      short loc_18001D595
0x18001d566  call    cs:__imp_GetCurrentThreadId
0x18001d56c  mov     edx, [rbx+8]
0x18001d56f  cmp     edx, eax
0x18001d571  jz      short loc_18001D57D
0x18001d573  mov     ecx, 1; unsigned int
0x18001d578  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001d57d  mov     rcx, rbx; SRWLock
0x18001d580  mov     dword ptr [rbx+8], 0
0x18001d587  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d58d  mov     qword ptr [rdi+8], 0
0x18001d595  mov     rbx, [rsp+28h+arg_0]
0x18001d59a  add     rsp, 20h
0x18001d59e  pop     rdi
0x18001d59f  retn
```
