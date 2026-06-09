# Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>(std::shared_ptr<Concurrency::details::_Task_impl<Optional<bool>>> const &,std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::function<void (Optional<bool>)> const &,Concurrency::task_continuation_context const &,Concurrency::details::_TaskInliningMode)

- ea: `0x14008a270`
- end: `0x14008a3c5`
- name: `??0?$_ContinuationTaskHandle@V?$Optional@_N@@XV?$function@$$A6AXV?$Optional@_N@@@Z@std@@U?$integral_constant@_N$0A@@3@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$Optional@_N@@@Concurrency@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@V?$Optional@_N@@@details@Concurrency@@@std@@AEBV?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@4@AEBV?$function@$$A6AXV?$Optional@_N@@@Z@4@AEBVtask_continuation_context@2@W4_TaskInliningMode@details@2@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140089cc4`

## callees

- `0x14008a270`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x14008a2ac`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x14008a2ac`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14008a366`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14008a366`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x14008a372`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x14008a372`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x14008a395`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x14008a395`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14008a3a2`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14008a3a2`

## pseudocode

```c
__int64 __fastcall Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  Concurrency::details::_ContextCallback *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 (__fastcall ***v13)(_QWORD, __int64); // rcx
  char v14; // dl

  *(_QWORD *)a1 = &Concurrency::details::_ContinuationTaskHandleBase::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  v10 = (Concurrency::details::_ContextCallback *)(a1 + 16);
  Concurrency::task_continuation_context::task_continuation_context((Concurrency::task_continuation_context *)(a1 + 16));
  *(_BYTE *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  *(_QWORD *)a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  v11 = a3[1];
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)(a1 + 40) = *a3;
  *(_QWORD *)(a1 + 48) = a3[1];
  *(_QWORD *)a1 = &Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  v12 = a2[1];
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  *(_QWORD *)(a1 + 56) = *a2;
  *(_QWORD *)(a1 + 64) = a2[1];
  *(_QWORD *)(a1 + 128) = 0;
  v13 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a4 + 56);
  if ( v13 )
    *(_QWORD *)(a1 + 128) = (**v13)(v13, a1 + 72);
  *(_BYTE *)(a1 + 32) = 0;
  if ( v10 != (Concurrency::details::_ContextCallback *)a5 )
  {
    Concurrency::details::_ContextCallback::_Reset(v10);
    Concurrency::details::_ContextCallback::_Assign(v10, *(void **)a5);
  }
  *((_BYTE *)v10 + 8) = *(_BYTE *)(a5 + 8);
  if ( *(_QWORD *)v10 == 1 )
  {
    v14 = *(_BYTE *)(*a2 + 12LL);
    *(_QWORD *)v10 = 0;
    if ( v14 )
    {
      if ( (unsigned __int8)Concurrency::details::_ContextCallback::_IsCurrentOriginSTA() )
        Concurrency::details::_ContextCallback::_Capture(v10);
    }
  }
  *(_DWORD *)(a1 + 36) = a6;
  return a1;
}

```

## disassembly

```asm
0x14008a270  mov     [rsp+arg_10], rbx
0x14008a275  mov     [rsp+arg_18], rbp
0x14008a27a  mov     [rsp+arg_0], rcx
0x14008a27f  push    rsi
0x14008a280  push    rdi
0x14008a281  push    r14
0x14008a283  sub     rsp, 20h
0x14008a287  mov     rbp, r9
0x14008a28a  mov     rsi, r8
0x14008a28d  mov     r14, rdx
0x14008a290  mov     rbx, rcx
0x14008a293  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x14008a29a  mov     [rcx], rax
0x14008a29d  mov     qword ptr [rcx+8], 0
0x14008a2a5  lea     rdi, [rcx+10h]
0x14008a2a9  mov     rcx, rdi
0x14008a2ac  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x14008a2b2  mov     byte ptr [rbx+20h], 0
0x14008a2b6  mov     dword ptr [rbx+24h], 0
0x14008a2bd  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$Optional@_N@@XV?$function@$$A6AXV?$Optional@_N@@@Z@std@@U?$integral_constant@_N$0A@@3@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$Optional@_N@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x14008a2c4  mov     [rbx], rax
0x14008a2c7  mov     qword ptr [rbx+28h], 0
0x14008a2cf  mov     qword ptr [rbx+30h], 0
0x14008a2d7  mov     rax, [rsi+8]
0x14008a2db  test    rax, rax
0x14008a2de  jz      short loc_14008A2E4
0x14008a2e0  lock inc dword ptr [rax+8]
0x14008a2e4  mov     rax, [rsi]
0x14008a2e7  mov     [rbx+28h], rax
0x14008a2eb  mov     rax, [rsi+8]
0x14008a2ef  mov     [rbx+30h], rax
0x14008a2f3  lea     rax, ??_7?$_ContinuationTaskHandle@V?$Optional@_N@@XV?$function@$$A6AXV?$Optional@_N@@@Z@std@@U?$integral_constant@_N$0A@@3@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$Optional@_N@@@Concurrency@@6B@; const Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x14008a2fa  mov     [rbx], rax
0x14008a2fd  mov     qword ptr [rbx+38h], 0
0x14008a305  mov     qword ptr [rbx+40h], 0
0x14008a30d  mov     rax, [r14+8]
0x14008a311  test    rax, rax
0x14008a314  jz      short loc_14008A31A
0x14008a316  lock inc dword ptr [rax+8]
0x14008a31a  mov     rax, [r14]
0x14008a31d  mov     [rbx+38h], rax
0x14008a321  mov     rax, [r14+8]
0x14008a325  mov     [rbx+40h], rax
0x14008a329  lea     rsi, [rbx+48h]
0x14008a32d  mov     [rsp+38h+arg_8], rsi
0x14008a332  mov     qword ptr [rsi+38h], 0
0x14008a33a  mov     rcx, [rbp+38h]
0x14008a33e  test    rcx, rcx
0x14008a341  jz      short loc_14008A355
0x14008a343  mov     rax, [rcx]
0x14008a346  mov     rdx, rsi
0x14008a349  mov     rax, [rax]
0x14008a34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008a351  mov     [rsi+38h], rax
0x14008a355  mov     byte ptr [rbx+20h], 0
0x14008a359  mov     rsi, [rsp+38h+arg_20]
0x14008a35e  cmp     rdi, rsi
0x14008a361  jz      short loc_14008A378
0x14008a363  mov     rcx, rdi
0x14008a366  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x14008a36c  mov     rdx, [rsi]
0x14008a36f  mov     rcx, rdi
0x14008a372  call    cs:__imp_?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z; Concurrency::details::_ContextCallback::_Assign(void *)
0x14008a378  mov     al, [rsi+8]
0x14008a37b  mov     [rdi+8], al
0x14008a37e  cmp     qword ptr [rdi], 1
0x14008a382  jnz     short loc_14008A3A8
0x14008a384  mov     rax, [r14]
0x14008a387  mov     dl, [rax+0Ch]
0x14008a38a  mov     qword ptr [rdi], 0
0x14008a391  test    dl, dl
0x14008a393  jz      short loc_14008A3A8
0x14008a395  call    cs:__imp_?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ; Concurrency::details::_ContextCallback::_IsCurrentOriginSTA(void)
0x14008a39b  test    al, al
0x14008a39d  jz      short loc_14008A3A8
0x14008a39f  mov     rcx, rdi
0x14008a3a2  call    cs:__imp_?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Capture(void)
0x14008a3a8  mov     eax, [rsp+38h+arg_28]
0x14008a3ac  mov     [rbx+24h], eax
0x14008a3af  mov     rax, rbx
0x14008a3b2  mov     rbx, [rsp+38h+arg_10]
0x14008a3b7  mov     rbp, [rsp+38h+arg_18]
0x14008a3bc  add     rsp, 20h
0x14008a3c0  pop     r14
0x14008a3c2  pop     rdi
0x14008a3c3  pop     rsi
0x14008a3c4  retn
```
