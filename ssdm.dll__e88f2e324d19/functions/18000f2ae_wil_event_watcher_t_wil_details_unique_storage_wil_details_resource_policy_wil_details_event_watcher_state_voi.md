# _wil::event_watcher_t_wil::details::unique_storage_wil::details::resource_policy_wil::details::event_watcher_state___void_(__cdecl_)(wil::details::event_watcher_state__)_&wil::details::delete_event_watcher_state_wistd::integral_constant_unsigned___int64_2__wil::details::event_watcher_state___wil::details::event_watcher_state___0_std::nullptr_t____wil::err_exception_policy_::create_take_hevent_ownership_::_1_::dtor$1

- ea: `0x18000f2ae`
- end: `0x18000f2cd`
- name: `_wil::event_watcher_t_wil::details::unique_storage_wil::details::resource_policy_wil::details::event_watcher_state___void_(__cdecl_)(wil::details::event_watcher_state__)_&wil::details::delete_event_watcher_state_wistd::integral_constant_unsigned___int64_2__wil::details::event_watcher_state___wil::details::event_watcher_state___0_std::nullptr_t____wil::err_exception_policy_::create_take_hevent_ownership_::_1_::dtor$1`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x180002d6c`

## pseudocode

```c
void __fastcall wil::event_watcher_t_wil::details::unique_storage_wil::details::resource_policy_wil::details::event_watcher_state___void____cdecl___wil::details::event_watcher_state_____wil::details::delete_event_watcher_state_wistd::integral_constant_unsigned___int64_2__wil::details::event_watcher_state___wil::details::event_watcher_state___0_std::nullptr_t____wil::err_exception_policy_::create_take_hevent_ownership_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 32), (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x18000f2ae  push    rbp
0x18000f2b0  sub     rsp, 20h
0x18000f2b4  mov     rbp, rdx
0x18000f2b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f2be  mov     rcx, [rbp+20h]; void *
0x18000f2c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f2c7  add     rsp, 20h
0x18000f2cb  pop     rbp
0x18000f2cc  retn
```
