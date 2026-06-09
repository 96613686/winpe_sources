# cxl::ScopedResOwner<ulong,cxl::tp2::WorkItemBase::SetThreadIdTraits>::ScopedResOwner<ulong,cxl::tp2::WorkItemBase::SetThreadIdTraits>(ulong *)

- ea: `0x180017d7c`
- end: `0x180017dba`
- name: `??0?$ScopedResOwner@KVSetThreadIdTraits@WorkItemBase@tp2@cxl@@@cxl@@QEAA@PEAK@Z`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b050`
- `0x18001b160`

## callees

- `0x180017d7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017d99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017d99`

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
0x180017d7c  mov     [rsp+arg_0], rbx
0x180017d81  push    rdi
0x180017d82  sub     rsp, 20h
0x180017d86  mov     qword ptr [rcx+8], 0
0x180017d8e  mov     rdi, rdx
0x180017d91  mov     rbx, rcx
0x180017d94  test    rdx, rdx
0x180017d97  jz      short loc_180017DAB
0x180017d99  call    cs:__imp_GetCurrentThreadId
0x180017da0  nop     dword ptr [rax+rax+00h]
0x180017da5  mov     [rdi], eax
0x180017da7  mov     [rbx+8], rdi
0x180017dab  mov     rax, rbx
0x180017dae  mov     rbx, [rsp+28h+arg_0]
0x180017db3  add     rsp, 20h
0x180017db7  pop     rdi
0x180017db8  retn
```
