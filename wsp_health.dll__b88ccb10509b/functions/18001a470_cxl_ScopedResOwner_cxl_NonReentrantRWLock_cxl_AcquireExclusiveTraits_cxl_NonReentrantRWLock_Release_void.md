# cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)

- ea: `0x18001a470`
- end: `0x18001a4c0`
- name: `?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `45`
- callee_count: `2`
- tags: ``

## callers

- `0x180017688`
- `0x180017dec`
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

- `0x180014dc0`
- `0x18001a470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a4a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a4a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a486`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a486`

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
0x18001a470  mov     [rsp+arg_0], rbx
0x18001a475  push    rdi
0x18001a476  sub     rsp, 20h
0x18001a47a  mov     rbx, [rcx+8]
0x18001a47e  mov     rdi, rcx
0x18001a481  test    rbx, rbx
0x18001a484  jz      short loc_18001A4B5
0x18001a486  call    cs:__imp_GetCurrentThreadId
0x18001a48c  mov     edx, [rbx+8]
0x18001a48f  cmp     edx, eax
0x18001a491  jz      short loc_18001A49D
0x18001a493  mov     ecx, 1; unsigned int
0x18001a498  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001a49d  mov     rcx, rbx; SRWLock
0x18001a4a0  mov     dword ptr [rbx+8], 0
0x18001a4a7  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a4ad  mov     qword ptr [rdi+8], 0
0x18001a4b5  mov     rbx, [rsp+28h+arg_0]
0x18001a4ba  add     rsp, 20h
0x18001a4be  pop     rdi
0x18001a4bf  retn
```
