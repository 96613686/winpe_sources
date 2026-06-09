# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x140012220`
- end: `0x140012254`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x140007f34`
- `0x1400121f0`
- `0x140012d54`

## callees

- `0x140012220`
- `0x140025f04`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140012231`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140012231`

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
0x140012220  push    rbx
0x140012222  sub     rsp, 20h
0x140012226  mov     rbx, rcx
0x140012229  mov     rcx, [rcx]; pwk
0x14001222c  test    rcx, rcx
0x14001222f  jz      short loc_14001223E
0x140012231  call    cs:__imp_CloseThreadpoolWork
0x140012237  mov     qword ptr [rbx], 0
0x14001223e  mov     edx, 28h ; '('; struct std::nothrow_t *
0x140012243  mov     rcx, rbx; void *
0x140012246  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001224b  mov     rax, rbx
0x14001224e  add     rsp, 20h
0x140012252  pop     rbx
0x140012253  retn
```
