# _mi::MiSession::WriteErrorCallback_::_1_::catch$7

- ea: `0x18002c023`
- end: `0x18002c05d`
- name: `_mi::MiSession::WriteErrorCallback_::_1_::catch$7`
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
0x18002c023  mov     [rsp+arg_8], rdx
0x18002c028  push    rbp
0x18002c029  sub     rsp, 20h
0x18002c02d  mov     rbp, rdx
0x18002c030  mov     rcx, [rbp+20h]; this
0x18002c034  call    ?store_exception@MiOperationArgs@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::MiOperationArgs::store_exception(void)
0x18002c039  mov     rcx, [rbp+20h]; this
0x18002c03d  call    ?set_resultsCanceled@MiOperationArgs@MiAsyncOperation@mi@@QEAAX_N@Z; mi::MiAsyncOperation::MiOperationArgs::set_resultsCanceled(bool)
0x18002c042  mov     rcx, [rbp+28h]; operation
0x18002c046  call    MI_Operation_Cancel
0x18002c04b  nop
0x18002c04c  mov     rax, 0
0x18002c056  add     rsp, 20h
0x18002c05a  pop     rbp
0x18002c05b  retn
```
