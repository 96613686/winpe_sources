# _mi::MiSession::WriteMessageCallback_::_1_::catch$3

- ea: `0x18002c480`
- end: `0x18002c4ba`
- name: `_mi::MiSession::WriteMessageCallback_::_1_::catch$3`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180025bc0`
- `0x180028784`
- `0x1800287d8`

## pseudocode

```c
__int64 __fastcall mi::MiSession::WriteMessageCallback_::_1_::catch_3(__int64 a1, __int64 a2)
{
  bool v3; // dl
  MI_CancellationReason v4; // edx

  mi::MiAsyncOperation::MiOperationArgs::store_exception(*(mi::MiAsyncOperation::MiOperationArgs **)(a2 + 40));
  mi::MiAsyncOperation::MiOperationArgs::set_resultsCanceled(*(mi::MiAsyncOperation::MiOperationArgs **)(a2 + 40), v3);
  MI_Operation_Cancel(*(MI_Operation **)(a2 + 48), v4);
  return 0;
}

```

## disassembly

```asm
0x18002c480  mov     [rsp+arg_8], rdx
0x18002c485  push    rbp
0x18002c486  sub     rsp, 20h
0x18002c48a  mov     rbp, rdx
0x18002c48d  mov     rcx, [rbp+28h]; this
0x18002c491  call    ?store_exception@MiOperationArgs@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::MiOperationArgs::store_exception(void)
0x18002c496  mov     rcx, [rbp+28h]; this
0x18002c49a  call    ?set_resultsCanceled@MiOperationArgs@MiAsyncOperation@mi@@QEAAX_N@Z; mi::MiAsyncOperation::MiOperationArgs::set_resultsCanceled(bool)
0x18002c49f  mov     rcx, [rbp+30h]; operation
0x18002c4a3  call    MI_Operation_Cancel
0x18002c4a8  nop
0x18002c4a9  mov     rax, 0
0x18002c4b3  add     rsp, 20h
0x18002c4b7  pop     rbp
0x18002c4b8  retn
```
