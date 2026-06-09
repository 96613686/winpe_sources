# Concurrency::get_ambient_scheduler(void)

- ea: `0x14001d56c`
- end: `0x14001d620`
- name: `?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ`
- size: `180`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000c448`
- `0x14001beb4`
- `0x14009363c`

## callees

- `0x1400051e8`
- `0x140005670`
- `0x1400056d8`
- `0x140005a84`
- `0x14001d56c`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x14001d5d5`
- `KERNEL32!InitOnceComplete` at `0x14001d5d5`
- `KERNEL32!InitOnceBeginInitialize` at `0x14001d589`
- `KERNEL32!InitOnceBeginInitialize` at `0x14001d589`

## pseudocode

```c
__int64 Concurrency::get_ambient_scheduler()
{
  WINBOOL fPending; // [rsp+40h] [rbp+8h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(
          &`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_Flag,
          0,
          &fPending,
          0) )
    __fastfail(5u);
  if ( fPending )
  {
    if ( __TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
    {
      Init_thread_header(&__TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA);
      if ( __TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA == -1 )
      {
        atexit(`Concurrency::details::_GetStaticAmbientSchedulerStorage'::`2'::`dynamic atexit destructor for '_S_scheduler'');
        Init_thread_footer(&__TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA);
      }
    }
    `Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_S_scheduler_address = (__int64)&`Concurrency::details::_GetStaticAmbientSchedulerStorage'::`2'::_S_scheduler;
    if ( !InitOnceComplete(&`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_Flag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  return `Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_S_scheduler_address;
}

```

## disassembly

```asm
0x14001d56c  sub     rsp, 38h
0x14001d570  xor     r9d, r9d; lpContext
0x14001d573  mov     [rsp+38h+fPending], 0
0x14001d57b  lea     r8, [rsp+38h+fPending]; fPending
0x14001d580  xor     edx, edx; dwFlags
0x14001d582  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x14001d589  call    cs:__imp___std_init_once_begin_initialize
0x14001d58f  test    eax, eax
0x14001d591  jnz     short loc_14001D598
0x14001d593  lea     ecx, [rax+5]
0x14001d596  int     29h; Win8: RtlFailFast(ecx)
0x14001d598  cmp     [rsp+38h+fPending], 0
0x14001d59d  jz      short loc_14001D5DF
0x14001d59f  mov     rax, gs:58h
0x14001d5a8  mov     ecx, 4
0x14001d5ad  mov     rax, [rax]
0x14001d5b0  mov     eax, [rcx+rax]
0x14001d5b3  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, eax
0x14001d5b9  jg      short loc_14001D5F1
0x14001d5bb  lea     rax, ?_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4V45@A; std::shared_ptr<Concurrency::scheduler_interface> `Concurrency::details::_GetStaticAmbientSchedulerStorage(void)'::`2'::_S_scheduler
0x14001d5c2  xor     r8d, r8d; lpContext
0x14001d5c5  xor     edx, edx; dwFlags
0x14001d5c7  mov     cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA, rax; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x14001d5ce  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x14001d5d5  call    cs:__imp_InitOnceComplete
0x14001d5db  test    eax, eax
0x14001d5dd  jz      short loc_14001D5EB
0x14001d5df  mov     rax, cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x14001d5e6  add     rsp, 38h
0x14001d5ea  retn
0x14001d5eb  call    __std_init_once_link_alternate_names_and_abort
0x14001d5f1  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x14001d5f8  call    _Init_thread_header
0x14001d5fd  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, 0FFFFFFFFh
0x14001d604  jnz     short loc_14001D5BB
0x14001d606  lea     rcx, ??__F_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@YAXXZ; void (__cdecl *)()
0x14001d60d  call    atexit
0x14001d612  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x14001d619  call    _Init_thread_footer
0x14001d61e  jmp     short loc_14001D5BB
```
