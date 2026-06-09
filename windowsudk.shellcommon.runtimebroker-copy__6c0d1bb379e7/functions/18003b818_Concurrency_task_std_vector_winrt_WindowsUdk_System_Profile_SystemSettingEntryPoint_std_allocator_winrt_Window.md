# Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint,std::allocator<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>>::_ContinuationTaskHandle<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint,std::allocator<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>,void,std::function<void (Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint,std::allocator<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<uchar (Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint,std::allocator<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>>)>,Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint,std::allocator<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>>>(std::function<uchar (Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint,std::allocator<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>>)> &&,Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint,std::allocator<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>> &&)

- ea: `0x18003b818`
- end: `0x18003b8c0`
- name: `??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6AEV?$task@V?$vector@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@V?$allocator@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@@std@@@std@@@Concurrency@@@Z@std@@V?$task@V?$vector@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@V?$allocator@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@@std@@@std@@@Concurrency@@@?$_ContinuationTaskHandle@V?$vector@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@V?$allocator@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@@std@@@std@@XV?$function@$$A6AXV?$task@V?$vector@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@V?$allocator@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@@std@@@std@@@Concurrency@@@Z@2@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$vector@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@V?$allocator@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@@std@@@std@@@Concurrency@@QEBAE$$QEAV?$function@$$A6AEV?$task@V?$vector@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@V?$allocator@USystemSettingEntryPoint@Profile@System@WindowsUdk@winrt@@@std@@@std@@@Concurrency@@@Z@std@@$$QEAV12@@Z`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b14c`

## callees

- `0x180028978`
- `0x18003b818`
- `0x1804a2010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b840`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b840`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b8a7`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18003b8a7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003b87a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003b87a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>::_ContinuationTaskHandle<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>,void,std::function<void (Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<unsigned char (Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>)>,Concurrency::task<std::vector<winrt::WindowsUdk::System::Profile::SystemSettingEntryPoint>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  Concurrency::details::_TaskEventLogger *v5; // rsi
  __int64 v6; // rcx
  char v7; // bl
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-10h]

  v5 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
  v9 = *a3;
  v10 = (std::_Ref_count_base *)a3[1];
  *a3 = 0;
  a3[1] = 0;
  v6 = *(_QWORD *)(a2 + 56);
  if ( !v6 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 16LL))(v6, &v9);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
  return v7;
}

```

## disassembly

```asm
0x18003b818  mov     [rsp+arg_10], rbx
0x18003b81d  mov     [rsp+arg_18], rsi
0x18003b822  push    rdi
0x18003b823  sub     rsp, 30h
0x18003b827  mov     rbx, r8
0x18003b82a  mov     rdi, rdx
0x18003b82d  mov     rsi, [rcx+28h]
0x18003b831  add     rsi, 160h
0x18003b838  mov     [rsp+38h+arg_0], rsi
0x18003b83d  mov     rcx, rsi
0x18003b840  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18003b846  nop
0x18003b847  mov     rax, [rbx]
0x18003b84a  mov     [rsp+38h+var_18], rax
0x18003b84f  mov     rax, [rbx+8]
0x18003b853  mov     [rsp+38h+var_10], rax
0x18003b858  mov     qword ptr [rbx], 0
0x18003b85f  mov     qword ptr [rbx+8], 0
0x18003b867  lea     rax, [rsp+38h+var_18]
0x18003b86c  mov     [rsp+38h+arg_8], rax
0x18003b871  mov     rcx, [rdi+38h]
0x18003b875  test    rcx, rcx
0x18003b878  jnz     short loc_18003B881
0x18003b87a  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003b880  int     3; Trap to Debugger
0x18003b881  mov     rax, [rcx]
0x18003b884  lea     rdx, [rsp+38h+var_18]
0x18003b889  mov     rax, [rax+10h]
0x18003b88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b892  mov     bl, al
0x18003b894  mov     rcx, [rsp+38h+var_10]; this
0x18003b899  test    rcx, rcx
0x18003b89c  jz      short loc_18003B8A4
0x18003b89e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b8a3  nop
0x18003b8a4  mov     rcx, rsi
0x18003b8a7  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18003b8ad  nop
0x18003b8ae  mov     al, bl
0x18003b8b0  mov     rbx, [rsp+38h+arg_10]
0x18003b8b5  mov     rsi, [rsp+38h+arg_18]
0x18003b8ba  add     rsp, 30h
0x18003b8be  pop     rdi
0x18003b8bf  retn
```
