# Concurrency::details::_PPLTaskHandle_Optional_bool__Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_e0b1464aecb02ae448ff41079a9cc63a__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x14004c9a0`
- end: `0x14004cb2a`
- name: `Concurrency::details::_PPLTaskHandle_Optional_bool__Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_e0b1464aecb02ae448ff41079a9cc63a__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140046ffc`
- `0x1400470ac`
- `0x14004c52c`
- `0x14004c9a0`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x14004ca0b`
- `msvcp_win!_Mtx_unlock` at `0x14004ca3d`
- `msvcp_win!_Mtx_unlock` at `0x14004ca0b`
- `msvcp_win!_Mtx_unlock` at `0x14004ca3d`
- `msvcp_win!_Mtx_lock` at `0x14004c9c6`
- `msvcp_win!_Mtx_lock` at `0x14004c9c6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14004c9d5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14004c9f1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14004c9d5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14004c9f1`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14004cb0e`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14004cb0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_PPLTaskHandle_Optional_bool__Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_e0b1464aecb02ae448ff41079a9cc63a__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rbx
  __int64 v3; // rsi
  struct _Mtx_internal_imp_t *v4; // rcx
  __int64 v5; // rdx
  Concurrency::details::_Task_impl_base *v6; // rdi
  _BYTE *v7; // rcx
  _BYTE *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  Concurrency::details::_Task_impl_base *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int128 v14; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v15[56]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE *v16; // [rsp+78h] [rbp-60h]
  _BYTE v17[56]; // [rsp+80h] [rbp-58h] BYREF
  __int64 v18; // [rsp+B8h] [rbp-20h]
  Concurrency::details::_Task_impl_base **v20; // [rsp+E8h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
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
  v20 = v2;
  v4 = (struct _Mtx_internal_imp_t *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 8) == 2 )
  {
    _Mtx_unlock(v4);
    v5 = (__int64)*v2 + 16;
    LOBYTE(v5) = 1;
    (*(void (__fastcall **)(Concurrency::details::_Task_impl_base *, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v2 + 8LL))(
      *v2,
      v5,
      0,
      0,
      (__int64)*v2 + 16);
    return;
  }
  *(_DWORD *)(v3 + 8) = 1;
  _Mtx_unlock(v4);
  try
  {
    v6 = *v2;
    v7 = (_BYTE *)std::_Global_new_std::_Func_impl_no_alloc__lambda_e0b1464aecb02ae448ff41079a9cc63a__Optional_bool_____lambda_e0b1464aecb02ae448ff41079a9cc63a__const___((struct appids::AnyRuntimeApp *)(a1 + 24));
    v16 = v7;
    v18 = 0;
    if ( !v7 )
      goto LABEL_14;
    if ( v7 == v15 )
    {
      v18 = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v7 + 8LL))(v7, v17);
      if ( !v16 )
      {
LABEL_14:
        Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync_::_LogWorkItemAndInvokeUserLambda_std::function_Optional_bool____cdecl_void____(
          a1,
          (__int64)&v14,
          (__int64)v17);
        Concurrency::details::_Task_impl<Optional<bool>>::_FinalizeAndRunContinuations(v6);
        goto LABEL_22;
      }
      v8 = v15;
      LOBYTE(v8) = v16 != v15;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v16 + 32LL))(v16, v8);
    }
    else
    {
      v18 = (__int64)v7;
    }
    v16 = 0;
    goto LABEL_14;
  }
  catch ( Concurrency::task_canceled )
  {
    v9 = *(_QWORD *)(a1 + 8);
    v10 = v9 + 16;
    LOBYTE(v10) = 1;
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v9 + 8LL))(v9, v10, 0, 0, v9 + 16);
    v2 = v20;
  }
  catch ( Concurrency::details::_Interruption_exception )
  {
    v12 = *(_QWORD *)(a1 + 8);
    v13 = v12 + 16;
    LOBYTE(v13) = 1;
    guard_dispatch_icall_thunk_10345483385596137414(v12, v13, 0, 0, v12 + 16);
    v2 = v20;
  }
  catch ( ... )
  {
    v11 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
    v14 = 0;
    __ExceptionPtrCreate(&v14);
    __ExceptionPtrCurrentException(&v14);
    Concurrency::details::_Task_impl_base::_CancelWithException(v11, (const struct std::exception_ptr *)&v14);
    __ExceptionPtrDestroy(&v14);
    v2 = v20;
  }
LABEL_22:
  Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_Task_impl_base *)((char *)*v2 + 352));
}

```

## disassembly

```asm
0x14004c9a0  mov     [rsp+arg_18], rbx
0x14004c9a5  mov     [rsp+arg_0], rcx
0x14004c9aa  push    rsi
0x14004c9ab  push    rdi
0x14004c9ac  push    r14
0x14004c9ae  sub     rsp, 0C0h
0x14004c9b5  mov     r14, rcx
0x14004c9b8  lea     rbx, [rcx+8]
0x14004c9bc  mov     rsi, [rbx]
0x14004c9bf  lea     rdi, [rsi+20h]
0x14004c9c3  mov     rcx, rdi; _Mtx_t
0x14004c9c6  call    cs:__imp__Mtx_lock
0x14004c9cc  test    eax, eax
0x14004c9ce  jz      short loc_14004C9DC
0x14004c9d0  mov     ecx, 5
0x14004c9d5  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14004c9db  int     3; Trap to Debugger
0x14004c9dc  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x14004c9e3  jnz     short loc_14004C9F8
0x14004c9e5  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x14004c9ec  mov     ecx, 6
0x14004c9f1  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14004c9f7  int     3; Trap to Debugger
0x14004c9f8  mov     [rsp+0D8h+arg_8], rbx
0x14004ca00  mov     eax, [rsi+8]
0x14004ca03  mov     rcx, rdi; _Mtx_t
0x14004ca06  cmp     eax, 2
0x14004ca09  jnz     short loc_14004CA36
0x14004ca0b  call    cs:__imp__Mtx_unlock
0x14004ca11  mov     rcx, [rbx]
0x14004ca14  mov     rax, [rcx]
0x14004ca17  lea     rdx, [rcx+10h]
0x14004ca1b  mov     [rsp+0D8h+var_B8], rdx
0x14004ca20  xor     r9d, r9d
0x14004ca23  xor     r8d, r8d
0x14004ca26  mov     dl, 1
0x14004ca28  mov     rax, [rax+8]
0x14004ca2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ca31  jmp     loc_14004CB14
0x14004ca36  mov     dword ptr [rsi+8], 1
0x14004ca3d  call    cs:__imp__Mtx_unlock
0x14004ca43  nop
0x14004ca44  mov     rdi, [rbx]
0x14004ca47  lea     rax, [rsp+0D8h+var_98]
0x14004ca4c  mov     [rsp+0D8h+arg_10], rax
0x14004ca54  mov     [rsp+0D8h+var_60], 0
0x14004ca5d  lea     rcx, [r14+18h]; struct appids::AnyRuntimeApp *
0x14004ca61  call    std___Global_new_std___Func_impl_no_alloc__lambda_e0b1464aecb02ae448ff41079a9cc63a__Optional_bool_____lambda_e0b1464aecb02ae448ff41079a9cc63a__const___
0x14004ca66  mov     rcx, rax
0x14004ca69  mov     [rsp+0D8h+var_60], rax
0x14004ca6e  mov     [rsp+0D8h+var_20], 0
0x14004ca7a  test    rax, rax
0x14004ca7d  jz      short loc_14004CAD9
0x14004ca7f  lea     rax, [rsp+0D8h+var_98]
0x14004ca84  cmp     rcx, rax
0x14004ca87  jnz     short loc_14004CAC8
0x14004ca89  mov     rax, [rcx]
0x14004ca8c  lea     rdx, [rsp+0D8h+var_58]
0x14004ca94  mov     rax, [rax+8]
0x14004ca98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ca9d  mov     [rsp+0D8h+var_20], rax
0x14004caa5  mov     rcx, [rsp+0D8h+var_60]
0x14004caaa  test    rcx, rcx
0x14004caad  jz      short loc_14004CAD9
0x14004caaf  mov     rax, [rcx]
0x14004cab2  lea     rdx, [rsp+0D8h+var_98]
0x14004cab7  cmp     rcx, rdx
0x14004caba  setnz   dl
0x14004cabd  mov     rax, [rax+20h]
0x14004cac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004cac6  jmp     short loc_14004CAD0
0x14004cac8  mov     [rsp+0D8h+var_20], rcx
0x14004cad0  mov     [rsp+0D8h+var_60], 0
0x14004cad9  lea     r8, [rsp+0D8h+var_58]
0x14004cae1  lea     rdx, [rsp+0D8h+var_A8]
0x14004cae6  mov     rcx, r14
0x14004cae9  call    Concurrency__task_Optional_bool______InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency__details___TypeSelectorNoAsync____LogWorkItemAndInvokeUserLambda_std__function_Optional_bool____cdecl_void____
0x14004caee  mov     rdx, rax
0x14004caf1  mov     rcx, rdi; this
0x14004caf4  call    ?_FinalizeAndRunContinuations@?$_Task_impl@V?$Optional@_N@@@details@Concurrency@@QEAAXV?$Optional@_N@@@Z; Concurrency::details::_Task_impl<Optional<bool>>::_FinalizeAndRunContinuations(Optional<bool>)
0x14004caf9  nop
0x14004cafa  jmp     short loc_14004CB04
0x14004cafc  mov     rbx, [rsp+0D8h+arg_8]
0x14004cb04  mov     rcx, [rbx]
0x14004cb07  add     rcx, 160h
0x14004cb0e  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x14004cb14  mov     rbx, [rsp+0D8h+arg_18]
0x14004cb1c  add     rsp, 0C0h
0x14004cb23  pop     r14
0x14004cb25  pop     rdi
0x14004cb26  pop     rsi
0x14004cb27  retn
0x14004cb28  jmp     short loc_14004CAFC
```
