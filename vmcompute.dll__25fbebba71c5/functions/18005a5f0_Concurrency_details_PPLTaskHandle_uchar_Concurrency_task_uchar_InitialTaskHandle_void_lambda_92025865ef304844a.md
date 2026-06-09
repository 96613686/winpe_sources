# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18005a5f0`
- end: `0x18005a6dc`
- name: `?invoke@?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_92025865ef304844afd880c1a9e1f846_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEBAXXZ`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18005965c`
- `0x18005a5f0`
- `0x180086010`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a6c1`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a6c1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005a625`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005a647`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005a625`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005a647`
- `msvcp_win!_Mtx_lock` at `0x18005a610`
- `msvcp_win!_Mtx_lock` at `0x18005a610`
- `msvcp_win!_Mtx_unlock` at `0x18005a65f`
- `msvcp_win!_Mtx_unlock` at `0x18005a69c`
- `msvcp_win!_Mtx_unlock` at `0x18005a65f`
- `msvcp_win!_Mtx_unlock` at `0x18005a69c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
        __int64 a1)
{
  _QWORD *v2; // r14
  __int64 v3; // rdi
  struct _Mtx_internal_imp_t *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  Concurrency::details::_Task_impl_base *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int128 v11; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v12; // [rsp+40h] [rbp-38h]

  *(_QWORD *)&v11 = a1;
  v2 = (_QWORD *)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 8);
  if ( _Mtx_lock((_Mtx_t)(v3 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v3 + 108) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v3 + 108) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v4 = (struct _Mtx_internal_imp_t *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 8) == 2 )
  {
    _Mtx_unlock(v4);
    LOBYTE(v5) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v2 + 8LL))(*v2, v5, 0, 0, *v2 + 16LL);
  }
  else
  {
    v12 = v2;
    *(_DWORD *)(v3 + 8) = 1;
    _Mtx_unlock(v4);
    try
    {
      Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      v6 = *(_QWORD *)(v11 + 8);
      v7 = v6 + 16;
      LOBYTE(v7) = 1;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v6 + 8LL))(v6, v7, 0, 0, v6 + 16);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v9 = *(_QWORD *)(v11 + 8);
      v10 = v9 + 16;
      LOBYTE(v10) = 1;
      guard_dispatch_icall_thunk_10345483385596137414(v9, v10, 0, 0, v9 + 16);
    }
    catch ( ... )
    {
      v8 = *(Concurrency::details::_Task_impl_base **)(v11 + 8);
      v11 = 0;
      __ExceptionPtrCreate(&v11);
      __ExceptionPtrCurrentException(&v11);
      Concurrency::details::_Task_impl_base::_CancelWithException(v8, (const struct std::exception_ptr *)&v11);
      __ExceptionPtrDestroy(&v11);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*v12 + 352LL));
  }
}

```

## disassembly

```asm
0x18005a5f0  push    rbx
0x18005a5f2  push    rsi
0x18005a5f3  push    rdi
0x18005a5f4  push    r14
0x18005a5f6  sub     rsp, 58h
0x18005a5fa  mov     rsi, rcx
0x18005a5fd  mov     qword ptr [rsp+78h+var_48], rcx
0x18005a602  lea     r14, [rcx+8]
0x18005a606  mov     rdi, [r14]
0x18005a609  lea     rbx, [rdi+20h]
0x18005a60d  mov     rcx, rbx; _Mtx_t
0x18005a610  call    cs:__imp__Mtx_lock
0x18005a617  nop     dword ptr [rax+rax+00h]
0x18005a61c  test    eax, eax
0x18005a61e  jz      short loc_18005A632
0x18005a620  mov     ecx, 5
0x18005a625  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005a62c  nop     dword ptr [rax+rax+00h]
0x18005a631  int     3; Trap to Debugger
0x18005a632  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18005a639  jnz     short loc_18005A654
0x18005a63b  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18005a642  mov     ecx, 6
0x18005a647  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005a64e  nop     dword ptr [rax+rax+00h]
0x18005a653  int     3; Trap to Debugger
0x18005a654  mov     eax, [rdi+8]
0x18005a657  mov     rcx, rbx; _Mtx_t
0x18005a65a  cmp     eax, 2
0x18005a65d  jnz     short loc_18005A690
0x18005a65f  call    cs:__imp__Mtx_unlock
0x18005a666  nop     dword ptr [rax+rax+00h]
0x18005a66b  mov     r10, [r14]
0x18005a66e  mov     rax, [r10]
0x18005a671  lea     rcx, [r10+10h]
0x18005a675  mov     [rsp+78h+var_58], rcx
0x18005a67a  xor     r9d, r9d
0x18005a67d  xor     r8d, r8d
0x18005a680  mov     dl, 1
0x18005a682  mov     rcx, r10
0x18005a685  mov     rax, [rax+8]
0x18005a689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a68e  jmp     short loc_18005A6CD
0x18005a690  mov     [rsp+78h+var_38], r14
0x18005a695  mov     dword ptr [rdi+8], 1
0x18005a69c  call    cs:__imp__Mtx_unlock
0x18005a6a3  nop     dword ptr [rax+rax+00h]
0x18005a6a8  nop
0x18005a6a9  mov     rcx, rsi
0x18005a6ac  call    ?_Init@?$_InitialTaskHandle@XV_lambda_92025865ef304844afd880c1a9e1f846_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18005a6b1  nop
0x18005a6b2  mov     rax, [rsp+78h+var_38]
0x18005a6b7  mov     rcx, [rax]
0x18005a6ba  add     rcx, 160h
0x18005a6c1  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18005a6c8  nop     dword ptr [rax+rax+00h]
0x18005a6cd  add     rsp, 58h
0x18005a6d1  pop     r14
0x18005a6d3  pop     rdi
0x18005a6d4  pop     rsi
0x18005a6d5  pop     rbx
0x18005a6d6  retn
0x18005a6d8  jmp     short loc_18005A6B2
0x18005a6da  jmp     short loc_18005A6B2
```
