# OncRpcEndpointOpen

- ea: `0x140006d10`
- end: `0x140006d40`
- name: `OncRpcEndpointOpen`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005dc8`

## pseudocode

```c
__int64 __fastcall OncRpcEndpointOpen(__int128 *a1, __int64 a2, char a3, int a4, _QWORD *a5, __int64 a6, __int64 *a7)
{
  return OncRpcConnMgrEndpointOpen(a1, a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x140006d10  sub     rsp, 48h
0x140006d14  mov     rax, [rsp+48h+arg_30]
0x140006d1c  mov     [rsp+48h+var_18], rax
0x140006d21  mov     rax, [rsp+48h+arg_28]
0x140006d26  mov     [rsp+48h+var_20], rax
0x140006d2b  mov     rax, [rsp+48h+arg_20]
0x140006d30  mov     [rsp+48h+var_28], rax
0x140006d35  call    OncRpcConnMgrEndpointOpen
0x140006d3a  add     rsp, 48h
0x140006d3e  retn
```
