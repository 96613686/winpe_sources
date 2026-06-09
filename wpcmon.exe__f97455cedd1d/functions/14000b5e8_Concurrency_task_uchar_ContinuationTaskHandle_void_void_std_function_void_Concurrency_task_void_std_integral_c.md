# Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::function<void (Concurrency::task<void>)> const &,Concurrency::task_continuation_context const &,Concurrency::details::_TaskInliningMode)

- ea: `0x14000b5e8`
- end: `0x14000b73d`
- name: `??0?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@0AEBV?$function@$$A6AXV?$task@X@Concurrency@@@Z@4@AEBVtask_continuation_context@2@W4_TaskInliningMode@details@2@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000a334`

## callees

- `0x14000b5e8`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x14000b624`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x14000b624`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14000b6de`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14000b6de`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x14000b6ea`
- `msvcp_win!?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z` at `0x14000b6ea`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x14000b70d`
- `msvcp_win!?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ` at `0x14000b70d`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14000b71a`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x14000b71a`

## pseudocode

```c
__int64 __fastcall Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(
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
  *(_QWORD *)a1 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable';
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  v11 = a3[1];
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)(a1 + 40) = *a3;
  *(_QWORD *)(a1 + 48) = a3[1];
  *(_QWORD *)a1 = &Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
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
  *(_BYTE *)(a1 + 32) = 1;
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
0x14000b5e8  mov     [rsp+arg_10], rbx
0x14000b5ed  mov     [rsp+arg_18], rbp
0x14000b5f2  mov     [rsp+arg_0], rcx
0x14000b5f7  push    rsi
0x14000b5f8  push    rdi
0x14000b5f9  push    r14
0x14000b5fb  sub     rsp, 20h
0x14000b5ff  mov     rbp, r9
0x14000b602  mov     rsi, r8
0x14000b605  mov     r14, rdx
0x14000b608  mov     rbx, rcx
0x14000b60b  lea     rax, ??_7_ContinuationTaskHandleBase@details@Concurrency@@6B@; const Concurrency::details::_ContinuationTaskHandleBase::`vftable'
0x14000b612  mov     [rcx], rax
0x14000b615  mov     qword ptr [rcx+8], 0
0x14000b61d  lea     rdi, [rcx+10h]
0x14000b621  mov     rcx, rdi
0x14000b624  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x14000b62a  mov     byte ptr [rbx+20h], 0
0x14000b62e  mov     dword ptr [rbx+24h], 0
0x14000b635  lea     rax, ??_7?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::`vftable'
0x14000b63c  mov     [rbx], rax
0x14000b63f  mov     qword ptr [rbx+28h], 0
0x14000b647  mov     qword ptr [rbx+30h], 0
0x14000b64f  mov     rax, [rsi+8]
0x14000b653  test    rax, rax
0x14000b656  jz      short loc_14000B65C
0x14000b658  lock inc dword ptr [rax+8]
0x14000b65c  mov     rax, [rsi]
0x14000b65f  mov     [rbx+28h], rax
0x14000b663  mov     rax, [rsi+8]
0x14000b667  mov     [rbx+30h], rax
0x14000b66b  lea     rax, ??_7?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@6B@; const Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x14000b672  mov     [rbx], rax
0x14000b675  mov     qword ptr [rbx+38h], 0
0x14000b67d  mov     qword ptr [rbx+40h], 0
0x14000b685  mov     rax, [r14+8]
0x14000b689  test    rax, rax
0x14000b68c  jz      short loc_14000B692
0x14000b68e  lock inc dword ptr [rax+8]
0x14000b692  mov     rax, [r14]
0x14000b695  mov     [rbx+38h], rax
0x14000b699  mov     rax, [r14+8]
0x14000b69d  mov     [rbx+40h], rax
0x14000b6a1  lea     rsi, [rbx+48h]
0x14000b6a5  mov     [rsp+38h+arg_8], rsi
0x14000b6aa  mov     qword ptr [rsi+38h], 0
0x14000b6b2  mov     rcx, [rbp+38h]
0x14000b6b6  test    rcx, rcx
0x14000b6b9  jz      short loc_14000B6CD
0x14000b6bb  mov     rax, [rcx]
0x14000b6be  mov     rdx, rsi
0x14000b6c1  mov     rax, [rax]
0x14000b6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b6c9  mov     [rsi+38h], rax
0x14000b6cd  mov     byte ptr [rbx+20h], 1
0x14000b6d1  mov     rsi, [rsp+38h+arg_20]
0x14000b6d6  cmp     rdi, rsi
0x14000b6d9  jz      short loc_14000B6F0
0x14000b6db  mov     rcx, rdi
0x14000b6de  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x14000b6e4  mov     rdx, [rsi]
0x14000b6e7  mov     rcx, rdi
0x14000b6ea  call    cs:__imp_?_Assign@_ContextCallback@details@Concurrency@@AEAAXPEAX@Z; Concurrency::details::_ContextCallback::_Assign(void *)
0x14000b6f0  mov     al, [rsi+8]
0x14000b6f3  mov     [rdi+8], al
0x14000b6f6  cmp     qword ptr [rdi], 1
0x14000b6fa  jnz     short loc_14000B720
0x14000b6fc  mov     rax, [r14]
0x14000b6ff  mov     dl, [rax+0Ch]
0x14000b702  mov     qword ptr [rdi], 0
0x14000b709  test    dl, dl
0x14000b70b  jz      short loc_14000B720
0x14000b70d  call    cs:__imp_?_IsCurrentOriginSTA@_ContextCallback@details@Concurrency@@CA_NXZ; Concurrency::details::_ContextCallback::_IsCurrentOriginSTA(void)
0x14000b713  test    al, al
0x14000b715  jz      short loc_14000B720
0x14000b717  mov     rcx, rdi
0x14000b71a  call    cs:__imp_?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Capture(void)
0x14000b720  mov     eax, [rsp+38h+arg_28]
0x14000b724  mov     [rbx+24h], eax
0x14000b727  mov     rax, rbx
0x14000b72a  mov     rbx, [rsp+38h+arg_10]
0x14000b72f  mov     rbp, [rsp+38h+arg_18]
0x14000b734  add     rsp, 20h
0x14000b738  pop     r14
0x14000b73a  pop     rdi
0x14000b73b  pop     rsi
0x14000b73c  retn
```
