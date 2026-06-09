# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Schedule(void)

- ea: `0x14000832c`
- end: `0x1400083a7`
- name: `?_Schedule@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140008248`
- `0x1400082d4`

## callees

- `0x14000832c`
- `0x140012b90`
- `0x1400288dc`
- `0x14003067c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000836c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000836c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140008359`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140008359`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140008342`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140008342`

## pseudocode

```c
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Schedule(
        Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *this)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  unsigned int v3; // edx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  ThreadpoolWork = CreateThreadpoolWork(Concurrency::details::_anonymous_namespace_::_Task_scheduler_callback, this, 0);
  *(_QWORD *)this = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  else if ( GetLastError() )
  {
    Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(this, v3);
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Fail to schedule the chore!");
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x14000832c  push    rbx
0x14000832e  sub     rsp, 40h
0x140008332  mov     rbx, rcx
0x140008335  mov     rdx, rcx; pv
0x140008338  lea     rcx, Concurrency__details___anonymous_namespace____Task_scheduler_callback; pfnwk
0x14000833f  xor     r8d, r8d; pcbe
0x140008342  call    cs:__imp_CreateThreadpoolWork
0x140008349  nop     dword ptr [rax+rax+00h]
0x14000834e  mov     [rbx], rax
0x140008351  test    rax, rax
0x140008354  jz      short loc_14000836C
0x140008356  mov     rcx, rax; pwk
0x140008359  call    cs:__imp_SubmitThreadpoolWork
0x140008360  nop     dword ptr [rax+rax+00h]
0x140008365  add     rsp, 40h
0x140008369  pop     rbx
0x14000836a  retn
0x14000836c  call    cs:__imp_GetLastError
0x140008373  nop     dword ptr [rax+rax+00h]
0x140008378  test    eax, eax
0x14000837a  jz      short loc_140008365
0x14000837c  mov     rcx, rbx; this
0x14000837f  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x140008384  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x14000838b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140008390  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x140008395  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x14000839c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400083a1  call    _CxxThrowException
```
