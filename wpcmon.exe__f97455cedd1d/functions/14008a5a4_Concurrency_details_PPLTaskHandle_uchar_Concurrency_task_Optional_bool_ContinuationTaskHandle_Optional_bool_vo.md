# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<uchar,Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(void)

- ea: `0x14008a5a4`
- end: `0x14008a636`
- name: `??1?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$Optional@_N@@XV?$function@$$A6AXV?$Optional@_N@@@Z@std@@U?$integral_constant@_N$0A@@3@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$Optional@_N@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEAA@XZ`
- size: `146`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14008a50c`
- `0x14008aa20`
- `0x1400a5db6`

## callees

- `0x14008a5a4`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14008a61a`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14008a61a`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008a5c6`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008a5c6`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::~_PPLTaskHandle<unsigned char,Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rbx
  void **result; // rax

  *a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[5] + 352LL));
  v2 = (volatile signed __int32 *)a1[6];
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  *a1 = &Concurrency::details::_ContinuationTaskHandleBase::`vftable';
  Concurrency::details::_ContextCallback::_Reset((Concurrency::details::_ContextCallback *)(a1 + 2));
  result = &Concurrency::details::_TaskProcHandle::`vftable';
  *a1 = &Concurrency::details::_TaskProcHandle::`vftable';
  return result;
}

```

## disassembly

```asm
0x14008a5a4  mov     [rsp+arg_0], rbx
0x14008a5a9  push    rdi
0x14008a5aa  sub     rsp, 20h
0x14008a5ae  mov     rdi, rcx
0x14008a5b1  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$Optional@_N@@XV?$function@$$A6AXV?$Optional@_N@@@Z@std@@U?$integral_constant@_N$0A@@3@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$Optional@_N@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x14008a5b8  mov     [rcx], rax
0x14008a5bb  mov     rcx, [rcx+28h]
0x14008a5bf  add     rcx, 160h
0x14008a5c6  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x14008a5cc  mov     rbx, [rdi+30h]
0x14008a5d0  test    rbx, rbx
0x14008a5d3  jz      short loc_14008A60C
0x14008a5d5  or      eax, 0FFFFFFFFh
0x14008a5d8  lock xadd [rbx+8], eax
0x14008a5dd  cmp     eax, 1
0x14008a5e0  jnz     short loc_14008A60C
0x14008a5e2  mov     rax, [rbx]
0x14008a5e5  mov     rcx, rbx
0x14008a5e8  mov     rax, [rax]
0x14008a5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008a5f0  or      eax, 0FFFFFFFFh
0x14008a5f3  lock xadd [rbx+0Ch], eax
0x14008a5f8  cmp     eax, 1
0x14008a5fb  jnz     short loc_14008A60C
0x14008a5fd  mov     rax, [rbx]
0x14008a600  mov     rcx, rbx
0x14008a603  mov     rax, [rax+8]
0x14008a607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008a60c  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x14008a613  mov     [rdi], rax
0x14008a616  lea     rcx, [rdi+10h]
0x14008a61a  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x14008a620  nop
0x14008a621  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x14008a628  mov     [rdi], rax
0x14008a62b  mov     rbx, [rsp+28h+arg_0]
0x14008a630  add     rsp, 20h
0x14008a634  pop     rdi
0x14008a635  retn
```
