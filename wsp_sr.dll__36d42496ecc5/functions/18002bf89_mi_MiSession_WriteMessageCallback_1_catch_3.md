# _mi::MiSession::WriteMessageCallback_::_1_::catch$3

- ea: `0x18002bf89`
- end: `0x18002bfc3`
- name: `_mi::MiSession::WriteMessageCallback_::_1_::catch$3`
- size: `58`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800258a0`
- `0x180028364`
- `0x1800283ac`

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
0x18002bf89  mov     [rsp+arg_8], rdx
0x18002bf8e  push    rbp
0x18002bf8f  sub     rsp, 20h
0x18002bf93  mov     rbp, rdx
0x18002bf96  mov     rcx, [rbp+28h]; this
0x18002bf9a  call    ?store_exception@MiOperationArgs@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::MiOperationArgs::store_exception(void)
0x18002bf9f  mov     rcx, [rbp+28h]; this
0x18002bfa3  call    ?set_resultsCanceled@MiOperationArgs@MiAsyncOperation@mi@@QEAAX_N@Z; mi::MiAsyncOperation::MiOperationArgs::set_resultsCanceled(bool)
0x18002bfa8  mov     rcx, [rbp+30h]; operation
0x18002bfac  call    MI_Operation_Cancel
0x18002bfb1  nop
0x18002bfb2  mov     rax, 0
0x18002bfbc  add     rsp, 20h
0x18002bfc0  pop     rbp
0x18002bfc1  retn
```
