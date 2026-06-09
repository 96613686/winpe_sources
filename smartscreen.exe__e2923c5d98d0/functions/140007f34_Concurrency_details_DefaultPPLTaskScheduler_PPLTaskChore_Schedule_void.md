# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Schedule(void)

- ea: `0x140007f34`
- end: `0x140007f9c`
- name: `?_Schedule@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAXXZ`
- size: `104`
- prototype: `void __fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140007e50`
- `0x140007edc`

## callees

- `0x140007f34`
- `0x140012220`
- `0x14002771c`
- `0x14002f3bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007f67`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140007f5b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140007f5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140007f4a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140007f4a`

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
0x140007f34  push    rbx
0x140007f36  sub     rsp, 40h
0x140007f3a  mov     rbx, rcx
0x140007f3d  mov     rdx, rcx; pv
0x140007f40  lea     rcx, Concurrency__details___anonymous_namespace____Task_scheduler_callback; pfnwk
0x140007f47  xor     r8d, r8d; pcbe
0x140007f4a  call    cs:__imp_CreateThreadpoolWork
0x140007f50  mov     [rbx], rax
0x140007f53  test    rax, rax
0x140007f56  jz      short loc_140007F67
0x140007f58  mov     rcx, rax; pwk
0x140007f5b  call    cs:__imp_SubmitThreadpoolWork
0x140007f61  add     rsp, 40h
0x140007f65  pop     rbx
0x140007f66  retn
0x140007f67  call    cs:__imp_GetLastError
0x140007f6d  test    eax, eax
0x140007f6f  jz      short loc_140007F61
0x140007f71  mov     rcx, rbx; this
0x140007f74  call    ??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z; Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)
0x140007f79  lea     rdx, aFailToSchedule; "Fail to schedule the chore!"
0x140007f80  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140007f85  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x140007f8a  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x140007f91  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140007f96  call    _CxxThrowException
```
