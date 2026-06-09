# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,ulong)

- ea: `0x180007a20`
- end: `0x180007aa0`
- name: `?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z`
- size: `128`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800071d4`
- `0x1800071e4`
- `0x180007a20`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180007a42`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180007a42`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007a74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007a74`

## pseudocode

```c
void __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        const char *WaitResult)
{
  __int64 v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (*((_BYTE *)Context + 136) & 1) == 0 && !ResetEvent(*((HANDLE *)Context + 15)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, (unsigned int)Wait, WaitResult);
  v6 = *((_QWORD *)Context + 14);
  if ( !v6 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
  (*(void (__fastcall **)(__int64, PVOID, PTP_WAIT, const char *))(*(_QWORD *)v6 + 32LL))(v6, Context, Wait, WaitResult);
  if ( (*((_BYTE *)Context + 136) & 2) == 0 )
    SetThreadpoolWait(Wait, *((HANDLE *)Context + 15), 0);
}

```

## disassembly

```asm
0x180007a20  mov     [rsp+arg_0], rbx
0x180007a25  mov     [rsp+arg_8], rsi
0x180007a2a  push    rdi
0x180007a2b  sub     rsp, 20h
0x180007a2f  test    byte ptr [rdx+88h], 1
0x180007a36  mov     rsi, r8
0x180007a39  mov     rdi, rdx
0x180007a3c  jnz     short loc_180007A4C
0x180007a3e  mov     rcx, [rdx+78h]; hEvent
0x180007a42  call    cs:__imp_ResetEvent
0x180007a48  test    eax, eax
0x180007a4a  jz      short loc_180007A90
0x180007a4c  mov     rcx, [rdi+70h]; this
0x180007a50  test    rcx, rcx
0x180007a53  jz      short loc_180007A8A
0x180007a55  mov     rax, [rcx]
0x180007a58  mov     rax, [rax+20h]
0x180007a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a61  test    byte ptr [rdi+88h], 2
0x180007a68  jnz     short loc_180007A7A
0x180007a6a  mov     rdx, [rdi+78h]; h
0x180007a6e  xor     r8d, r8d; pftTimeout
0x180007a71  mov     rcx, rsi; pwa
0x180007a74  call    cs:__imp_SetThreadpoolWait
0x180007a7a  mov     rbx, [rsp+28h+arg_0]
0x180007a7f  mov     rsi, [rsp+28h+arg_8]
0x180007a84  add     rsp, 20h
0x180007a88  pop     rdi
0x180007a89  retn
0x180007a8a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007a90  mov     rcx, [rsp+28h]; this
0x180007a95  mov     edx, 0A06h; void *
0x180007a9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
