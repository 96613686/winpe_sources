# Concurrency::details::_PPLTaskHandle_Optional_bool__Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x14008c250`
- end: `0x14008c3da`
- name: `Concurrency::details::_PPLTaskHandle_Optional_bool__Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400470ac`
- `0x14004c52c`
- `0x140089b18`
- `0x14008c250`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x14008c2bb`
- `msvcp_win!_Mtx_unlock` at `0x14008c2ed`
- `msvcp_win!_Mtx_unlock` at `0x14008c2bb`
- `msvcp_win!_Mtx_unlock` at `0x14008c2ed`
- `msvcp_win!_Mtx_lock` at `0x14008c276`
- `msvcp_win!_Mtx_lock` at `0x14008c276`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14008c285`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14008c2a1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14008c285`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14008c2a1`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008c3be`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008c3be`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_Optional_bool__Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rbx
  __int64 v3; // rsi
  struct _Mtx_internal_imp_t *v4; // rcx
  __int64 v5; // rdx
  Concurrency::details::_Task_impl_base *v6; // rdi
  _BYTE *v7; // rcx
  _BYTE *v8; // rdx
  char v9[16]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v10[56]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE *v11; // [rsp+78h] [rbp-60h]
  _BYTE v12[56]; // [rsp+80h] [rbp-58h] BYREF
  __int64 v13; // [rsp+B8h] [rbp-20h]

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
  v6 = *v2;
  v7 = (_BYTE *)std::_Global_new_std::_Func_impl_no_alloc__lambda_f3e09f59ff4f256821f7695ec4f9692e__Optional_bool_____lambda_f3e09f59ff4f256821f7695ec4f9692e__const___(a1 + 24);
  v11 = v7;
  v13 = 0;
  if ( v7 )
  {
    if ( v7 != v10 )
    {
      v13 = (__int64)v7;
      goto LABEL_12;
    }
    v13 = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v7 + 8LL))(v7, v12);
    if ( v11 )
    {
      v8 = v10;
      LOBYTE(v8) = v11 != v10;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v11 + 32LL))(v11, v8);
LABEL_12:
      v11 = 0;
    }
  }
  Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync_::_LogWorkItemAndInvokeUserLambda_std::function_Optional_bool____cdecl_void____(
    a1,
    (__int64)v9,
    (__int64)v12);
  Concurrency::details::_Task_impl<Optional<bool>>::_FinalizeAndRunContinuations(v6);
  Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_Task_impl_base *)((char *)*v2 + 352));
}

```

## disassembly

```asm
0x14008c250  mov     [rsp+arg_18], rbx
0x14008c255  mov     [rsp+arg_0], rcx
0x14008c25a  push    rsi
0x14008c25b  push    rdi
0x14008c25c  push    r14
0x14008c25e  sub     rsp, 0C0h
0x14008c265  mov     r14, rcx
0x14008c268  lea     rbx, [rcx+8]
0x14008c26c  mov     rsi, [rbx]
0x14008c26f  lea     rdi, [rsi+20h]
0x14008c273  mov     rcx, rdi; _Mtx_t
0x14008c276  call    cs:__imp__Mtx_lock
0x14008c27c  test    eax, eax
0x14008c27e  jz      short loc_14008C28C
0x14008c280  mov     ecx, 5
0x14008c285  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14008c28b  int     3; Trap to Debugger
0x14008c28c  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x14008c293  jnz     short loc_14008C2A8
0x14008c295  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x14008c29c  mov     ecx, 6
0x14008c2a1  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14008c2a7  int     3; Trap to Debugger
0x14008c2a8  mov     [rsp+0D8h+arg_8], rbx
0x14008c2b0  mov     eax, [rsi+8]
0x14008c2b3  mov     rcx, rdi; _Mtx_t
0x14008c2b6  cmp     eax, 2
0x14008c2b9  jnz     short loc_14008C2E6
0x14008c2bb  call    cs:__imp__Mtx_unlock
0x14008c2c1  mov     rcx, [rbx]
0x14008c2c4  mov     rax, [rcx]
0x14008c2c7  lea     rdx, [rcx+10h]
0x14008c2cb  mov     [rsp+0D8h+var_B8], rdx
0x14008c2d0  xor     r9d, r9d
0x14008c2d3  xor     r8d, r8d
0x14008c2d6  mov     dl, 1
0x14008c2d8  mov     rax, [rax+8]
0x14008c2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c2e1  jmp     loc_14008C3C4
0x14008c2e6  mov     dword ptr [rsi+8], 1
0x14008c2ed  call    cs:__imp__Mtx_unlock
0x14008c2f3  nop
0x14008c2f4  mov     rdi, [rbx]
0x14008c2f7  lea     rax, [rsp+0D8h+var_98]
0x14008c2fc  mov     [rsp+0D8h+arg_10], rax
0x14008c304  mov     [rsp+0D8h+var_60], 0
0x14008c30d  lea     rcx, [r14+18h]
0x14008c311  call    std___Global_new_std___Func_impl_no_alloc__lambda_f3e09f59ff4f256821f7695ec4f9692e__Optional_bool_____lambda_f3e09f59ff4f256821f7695ec4f9692e__const___
0x14008c316  mov     rcx, rax
0x14008c319  mov     [rsp+0D8h+var_60], rax
0x14008c31e  mov     [rsp+0D8h+var_20], 0
0x14008c32a  test    rax, rax
0x14008c32d  jz      short loc_14008C389
0x14008c32f  lea     rax, [rsp+0D8h+var_98]
0x14008c334  cmp     rcx, rax
0x14008c337  jnz     short loc_14008C378
0x14008c339  mov     rax, [rcx]
0x14008c33c  lea     rdx, [rsp+0D8h+var_58]
0x14008c344  mov     rax, [rax+8]
0x14008c348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c34d  mov     [rsp+0D8h+var_20], rax
0x14008c355  mov     rcx, [rsp+0D8h+var_60]
0x14008c35a  test    rcx, rcx
0x14008c35d  jz      short loc_14008C389
0x14008c35f  mov     rax, [rcx]
0x14008c362  lea     rdx, [rsp+0D8h+var_98]
0x14008c367  cmp     rcx, rdx
0x14008c36a  setnz   dl
0x14008c36d  mov     rax, [rax+20h]
0x14008c371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c376  jmp     short loc_14008C380
0x14008c378  mov     [rsp+0D8h+var_20], rcx
0x14008c380  mov     [rsp+0D8h+var_60], 0
0x14008c389  lea     r8, [rsp+0D8h+var_58]
0x14008c391  lea     rdx, [rsp+0D8h+var_A8]
0x14008c396  mov     rcx, r14
0x14008c399  call    Concurrency__task_Optional_bool______InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency__details___TypeSelectorNoAsync____LogWorkItemAndInvokeUserLambda_std__function_Optional_bool____cdecl_void____
0x14008c39e  mov     rdx, rax
0x14008c3a1  mov     rcx, rdi; this
0x14008c3a4  call    ?_FinalizeAndRunContinuations@?$_Task_impl@V?$Optional@_N@@@details@Concurrency@@QEAAXV?$Optional@_N@@@Z; Concurrency::details::_Task_impl<Optional<bool>>::_FinalizeAndRunContinuations(Optional<bool>)
0x14008c3a9  nop
0x14008c3aa  jmp     short loc_14008C3B4
0x14008c3ac  mov     rbx, [rsp+0D8h+arg_8]
0x14008c3b4  mov     rcx, [rbx]
0x14008c3b7  add     rcx, 160h
0x14008c3be  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x14008c3c4  mov     rbx, [rsp+0D8h+arg_18]
0x14008c3cc  add     rsp, 0C0h
0x14008c3d3  pop     r14
0x14008c3d5  pop     rdi
0x14008c3d6  pop     rsi
0x14008c3d7  retn
0x14008c3d8  jmp     short loc_14008C3AC
```
