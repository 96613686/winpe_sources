# _mi::MiSession::WriteErrorCallback_::_1_::catch$7

- ea: `0x18002c51a`
- end: `0x18002c554`
- name: `_mi::MiSession::WriteErrorCallback_::_1_::catch$7`
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
__int64 __fastcall mi::MiSession::WriteErrorCallback_::_1_::catch_7(__int64 a1, __int64 a2)
{
  bool v3; // dl
  MI_CancellationReason v4; // edx

  mi::MiAsyncOperation::MiOperationArgs::store_exception(*(mi::MiAsyncOperation::MiOperationArgs **)(a2 + 32));
  mi::MiAsyncOperation::MiOperationArgs::set_resultsCanceled(*(mi::MiAsyncOperation::MiOperationArgs **)(a2 + 32), v3);
  MI_Operation_Cancel(*(MI_Operation **)(a2 + 40), v4);
  return 0;
}

```

## disassembly

```asm
0x18002c51a  mov     [rsp+arg_8], rdx
0x18002c51f  push    rbp
0x18002c520  sub     rsp, 20h
0x18002c524  mov     rbp, rdx
0x18002c527  mov     rcx, [rbp+20h]; this
0x18002c52b  call    ?store_exception@MiOperationArgs@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::MiOperationArgs::store_exception(void)
0x18002c530  mov     rcx, [rbp+20h]; this
0x18002c534  call    ?set_resultsCanceled@MiOperationArgs@MiAsyncOperation@mi@@QEAAX_N@Z; mi::MiAsyncOperation::MiOperationArgs::set_resultsCanceled(bool)
0x18002c539  mov     rcx, [rbp+28h]; operation
0x18002c53d  call    MI_Operation_Cancel
0x18002c542  nop
0x18002c543  mov     rax, 0
0x18002c54d  add     rsp, 20h
0x18002c551  pop     rbp
0x18002c552  retn
```
