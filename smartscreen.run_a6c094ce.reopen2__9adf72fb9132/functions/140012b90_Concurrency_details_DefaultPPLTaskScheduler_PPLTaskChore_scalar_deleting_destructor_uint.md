# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x140012b90`
- end: `0x140012bcb`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `59`
- prototype: `void *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x14000832c`
- `0x140012b60`
- `0x1400136fc`

## callees

- `0x140012b90`
- `0x140027084`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140012ba1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140012ba1`

## pseudocode

```c
Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(
        struct _TP_WORK **this)
{
  struct _TP_WORK *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    CloseThreadpoolWork(v2);
    *this = 0;
  }
  operator delete(this, (const struct std::nothrow_t *)0x28);
  return (Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *)this;
}

```

## disassembly

```asm
0x140012b90  push    rbx
0x140012b92  sub     rsp, 20h
0x140012b96  mov     rbx, rcx
0x140012b99  mov     rcx, [rcx]; pwk
0x140012b9c  test    rcx, rcx
0x140012b9f  jz      short loc_140012BB4
0x140012ba1  call    cs:__imp_CloseThreadpoolWork
0x140012ba8  nop     dword ptr [rax+rax+00h]
0x140012bad  mov     qword ptr [rbx], 0
0x140012bb4  mov     edx, 28h ; '('; struct std::nothrow_t *
0x140012bb9  mov     rcx, rbx; void *
0x140012bbc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012bc1  mov     rax, rbx
0x140012bc4  add     rsp, 20h
0x140012bc8  pop     rbx
0x140012bc9  retn
```
