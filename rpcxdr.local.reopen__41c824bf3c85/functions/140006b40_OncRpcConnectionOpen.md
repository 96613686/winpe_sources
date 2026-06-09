# OncRpcConnectionOpen

- ea: `0x140006b40`
- end: `0x140006b63`
- name: `OncRpcConnectionOpen`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140007394`

## pseudocode

```c
__int64 __fastcall OncRpcConnectionOpen(_WORD *a1, char a2, __int64 a3, __int64 a4, __int64 a5, __int64 *a6)
{
  return OncRpcConnMgrConnectionOpen(a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x140006b40  sub     rsp, 38h
0x140006b44  mov     rax, [rsp+38h+arg_28]
0x140006b49  mov     [rsp+38h+var_10], rax
0x140006b4e  mov     rax, [rsp+38h+arg_20]
0x140006b53  mov     [rsp+38h+var_18], rax
0x140006b58  call    OncRpcConnMgrConnectionOpen
0x140006b5d  add     rsp, 38h
0x140006b61  retn
```
