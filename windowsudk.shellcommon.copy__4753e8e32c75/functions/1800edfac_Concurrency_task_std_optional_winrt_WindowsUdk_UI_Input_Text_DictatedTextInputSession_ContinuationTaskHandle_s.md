# Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>::_ContinuationTaskHandle<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>,void,std::function<void (Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<uchar (Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>)>,Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>>(std::function<uchar (Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>)> &&,Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>> &&)

- ea: `0x1800edfac`
- end: `0x1800ee054`
- name: `??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6AEV?$task@V?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@@Concurrency@@@Z@std@@V?$task@V?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@@Concurrency@@@?$_ContinuationTaskHandle@V?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@XV?$function@$$A6AXV?$task@V?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@@Concurrency@@@Z@2@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@@Concurrency@@QEBAE$$QEAV?$function@$$A6AEV?$task@V?$optional@UDictatedTextInputSession@Text@Input@UI@WindowsUdk@winrt@@@std@@@Concurrency@@@Z@std@@$$QEAV12@@Z`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800edeb8`
- `0x1800ee268`

## callees

- `0x180028978`
- `0x1800edfac`
- `0x1804a2010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800edfd4`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800edfd4`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800ee03b`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800ee03b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800ee00e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800ee00e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>::_ContinuationTaskHandle<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>,void,std::function<void (Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<unsigned char (Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>)>,Concurrency::task<std::optional<winrt::WindowsUdk::UI::Input::Text::DictatedTextInputSession>>>(
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
0x1800edfac  mov     [rsp+arg_10], rbx
0x1800edfb1  mov     [rsp+arg_18], rsi
0x1800edfb6  push    rdi
0x1800edfb7  sub     rsp, 30h
0x1800edfbb  mov     rbx, r8
0x1800edfbe  mov     rdi, rdx
0x1800edfc1  mov     rsi, [rcx+28h]
0x1800edfc5  add     rsi, 160h
0x1800edfcc  mov     [rsp+38h+arg_0], rsi
0x1800edfd1  mov     rcx, rsi
0x1800edfd4  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1800edfda  nop
0x1800edfdb  mov     rax, [rbx]
0x1800edfde  mov     [rsp+38h+var_18], rax
0x1800edfe3  mov     rax, [rbx+8]
0x1800edfe7  mov     [rsp+38h+var_10], rax
0x1800edfec  mov     qword ptr [rbx], 0
0x1800edff3  mov     qword ptr [rbx+8], 0
0x1800edffb  lea     rax, [rsp+38h+var_18]
0x1800ee000  mov     [rsp+38h+arg_8], rax
0x1800ee005  mov     rcx, [rdi+38h]
0x1800ee009  test    rcx, rcx
0x1800ee00c  jnz     short loc_1800EE015
0x1800ee00e  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800ee014  int     3; Trap to Debugger
0x1800ee015  mov     rax, [rcx]
0x1800ee018  lea     rdx, [rsp+38h+var_18]
0x1800ee01d  mov     rax, [rax+10h]
0x1800ee021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee026  mov     bl, al
0x1800ee028  mov     rcx, [rsp+38h+var_10]; this
0x1800ee02d  test    rcx, rcx
0x1800ee030  jz      short loc_1800EE038
0x1800ee032  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ee037  nop
0x1800ee038  mov     rcx, rsi
0x1800ee03b  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1800ee041  nop
0x1800ee042  mov     al, bl
0x1800ee044  mov     rbx, [rsp+38h+arg_10]
0x1800ee049  mov     rsi, [rsp+38h+arg_18]
0x1800ee04e  add     rsp, 30h
0x1800ee052  pop     rdi
0x1800ee053  retn
```
