# Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync_::_LogWorkItemAndInvokeUserLambda_std::function_Optional_bool____cdecl(void)___

- ea: `0x1400470ac`
- end: `0x14004713f`
- name: `Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync_::_LogWorkItemAndInvokeUserLambda_std::function_Optional_bool____cdecl(void)___`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004c9a0`
- `0x14008c250`

## callees

- `0x1400470ac`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400470e8`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400470e8`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1400470d8`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1400470d8`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140047102`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140047102`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task_Optional_bool___::_InitialTaskHandle_Optional_bool___lambda_f3e09f59ff4f256821f7695ec4f9692e__Concurrency::details::_TypeSelectorNoAsync_::_LogWorkItemAndInvokeUserLambda_std::function_Optional_bool____cdecl_void____(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  Concurrency::details::_TaskEventLogger *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx

  v5 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
  v6 = *(_QWORD *)(a3 + 56);
  if ( !v6 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 16LL))(v6, a2);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
  v8 = *(_QWORD *)(a3 + 56);
  if ( v8 )
  {
    LOBYTE(v7) = v8 != a3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, v7);
    *(_QWORD *)(a3 + 56) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1400470ac  mov     rax, rsp
0x1400470af  mov     [rax+10h], rbx
0x1400470b3  mov     [rax+20h], rsi
0x1400470b7  mov     [rax+18h], r8
0x1400470bb  push    rdi
0x1400470bc  sub     rsp, 30h
0x1400470c0  mov     rbx, r8
0x1400470c3  mov     rdi, rdx
0x1400470c6  mov     rsi, [rcx+8]
0x1400470ca  add     rsi, 160h
0x1400470d1  mov     [rax+8], rsi
0x1400470d5  mov     rcx, rsi
0x1400470d8  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1400470de  nop
0x1400470df  mov     rcx, [rbx+38h]
0x1400470e3  test    rcx, rcx
0x1400470e6  jnz     short loc_1400470EF
0x1400470e8  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1400470ee  int     3; Trap to Debugger
0x1400470ef  mov     rax, [rcx]
0x1400470f2  mov     rdx, rdi
0x1400470f5  mov     rax, [rax+10h]
0x1400470f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400470fe  nop
0x1400470ff  mov     rcx, rsi
0x140047102  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x140047108  nop
0x140047109  mov     rcx, [rbx+38h]
0x14004710d  test    rcx, rcx
0x140047110  jz      short loc_14004712C
0x140047112  mov     rax, [rcx]
0x140047115  cmp     rcx, rbx
0x140047118  setnz   dl
0x14004711b  mov     rax, [rax+20h]
0x14004711f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047124  mov     qword ptr [rbx+38h], 0
0x14004712c  mov     rax, rdi
0x14004712f  mov     rbx, [rsp+38h+arg_8]
0x140047134  mov     rsi, [rsp+38h+arg_18]
0x140047139  add     rsp, 30h
0x14004713d  pop     rdi
0x14004713e  retn
```
