# cxl::ScopedResOwner<ulong,cxl::tp2::WorkItemBase::SetThreadIdTraits>::ScopedResOwner<ulong,cxl::tp2::WorkItemBase::SetThreadIdTraits>(ulong *)

- ea: `0x18001af48`
- end: `0x18001af86`
- name: `??0?$ScopedResOwner@KVSetThreadIdTraits@WorkItemBase@tp2@cxl@@@cxl@@QEAA@PEAK@Z`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e230`
- `0x18001e340`

## callees

- `0x18001af48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001af65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001af65`

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
0x18001af48  mov     [rsp+arg_0], rbx
0x18001af4d  push    rdi
0x18001af4e  sub     rsp, 20h
0x18001af52  mov     qword ptr [rcx+8], 0
0x18001af5a  mov     rdi, rdx
0x18001af5d  mov     rbx, rcx
0x18001af60  test    rdx, rdx
0x18001af63  jz      short loc_18001AF77
0x18001af65  call    cs:__imp_GetCurrentThreadId
0x18001af6c  nop     dword ptr [rax+rax+00h]
0x18001af71  mov     [rdi], eax
0x18001af73  mov     [rbx+8], rdi
0x18001af77  mov     rax, rbx
0x18001af7a  mov     rbx, [rsp+28h+arg_0]
0x18001af7f  add     rsp, 20h
0x18001af83  pop     rdi
0x18001af84  retn
```
