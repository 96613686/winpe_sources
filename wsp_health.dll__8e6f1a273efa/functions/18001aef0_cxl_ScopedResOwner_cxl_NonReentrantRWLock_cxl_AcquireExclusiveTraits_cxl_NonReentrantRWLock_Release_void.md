# cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)

- ea: `0x18001aef0`
- end: `0x18001af4d`
- name: `?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ`
- size: `93`
- prototype: ``
- caller_count: `45`
- callee_count: `2`
- tags: ``

## callers

- `0x180017fcc`
- `0x180018778`
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

- `0x180015578`
- `0x18001aef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001af2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001af2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001af06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001af06`

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
0x18001aef0  mov     [rsp+arg_0], rbx
0x18001aef5  push    rdi
0x18001aef6  sub     rsp, 20h
0x18001aefa  mov     rbx, [rcx+8]
0x18001aefe  mov     rdi, rcx
0x18001af01  test    rbx, rbx
0x18001af04  jz      short loc_18001AF41
0x18001af06  call    cs:__imp_GetCurrentThreadId
0x18001af0d  nop     dword ptr [rax+rax+00h]
0x18001af12  mov     edx, [rbx+8]
0x18001af15  cmp     edx, eax
0x18001af17  jz      short loc_18001AF23
0x18001af19  mov     ecx, 1; unsigned int
0x18001af1e  call    ?StopIfIsDebuggedOrCrash@Debug@cxl@@SAXK@Z; cxl::Debug::StopIfIsDebuggedOrCrash(ulong)
0x18001af23  mov     rcx, rbx; SRWLock
0x18001af26  mov     dword ptr [rbx+8], 0
0x18001af2d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001af34  nop     dword ptr [rax+rax+00h]
0x18001af39  mov     qword ptr [rdi+8], 0
0x18001af41  mov     rbx, [rsp+28h+arg_0]
0x18001af46  add     rsp, 20h
0x18001af4a  pop     rdi
0x18001af4b  retn
```
