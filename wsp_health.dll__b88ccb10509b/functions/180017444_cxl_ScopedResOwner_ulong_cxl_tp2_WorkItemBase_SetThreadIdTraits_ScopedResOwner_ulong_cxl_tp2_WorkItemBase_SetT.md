# cxl::ScopedResOwner<ulong,cxl::tp2::WorkItemBase::SetThreadIdTraits>::ScopedResOwner<ulong,cxl::tp2::WorkItemBase::SetThreadIdTraits>(ulong *)

- ea: `0x180017444`
- end: `0x18001747b`
- name: `??0?$ScopedResOwner@KVSetThreadIdTraits@WorkItemBase@tp2@cxl@@@cxl@@QEAA@PEAK@Z`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a5b0`
- `0x18001a6c0`

## callees

- `0x180017444`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017461`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017461`

## pseudocode

```c
__int64 __fastcall cxl::ScopedResOwner<unsigned long,cxl::tp2::WorkItemBase::SetThreadIdTraits>::ScopedResOwner<unsigned long,cxl::tp2::WorkItemBase::SetThreadIdTraits>(
        __int64 a1,
        DWORD *a2)
{
  *(_QWORD *)(a1 + 8) = 0;
  if ( a2 )
  {
    *a2 = GetCurrentThreadId();
    *(_QWORD *)(a1 + 8) = a2;
  }
  return a1;
}

```

## disassembly

```asm
0x180017444  mov     [rsp+arg_0], rbx
0x180017449  push    rdi
0x18001744a  sub     rsp, 20h
0x18001744e  mov     qword ptr [rcx+8], 0
0x180017456  mov     rdi, rdx
0x180017459  mov     rbx, rcx
0x18001745c  test    rdx, rdx
0x18001745f  jz      short loc_18001746D
0x180017461  call    cs:__imp_GetCurrentThreadId
0x180017467  mov     [rdi], eax
0x180017469  mov     [rbx+8], rdi
0x18001746d  mov     rax, rbx
0x180017470  mov     rbx, [rsp+28h+arg_0]
0x180017475  add     rsp, 20h
0x180017479  pop     rdi
0x18001747a  retn
```
