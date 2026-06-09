# RPCSplWOW64DeletePort

- ea: `0x14000d8e0`
- end: `0x14000d918`
- name: `RPCSplWOW64DeletePort`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140006f98`

## pseudocode

```c
void __fastcall RPCSplWOW64DeletePort(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        _DWORD *a6)
{
  TLoad64BitDllsMgr::ExecuteMonitorOperation((__int64)a1, a1, a2, a3, a4, a5, 1, a6);
}

```

## disassembly

```asm
0x14000d8e0  sub     rsp, 48h
0x14000d8e4  mov     rax, [rsp+48h+arg_28]
0x14000d8e9  mov     [rsp+48h+var_10], rax
0x14000d8ee  mov     rax, [rsp+48h+arg_20]
0x14000d8f3  mov     [rsp+48h+var_18], 1
0x14000d8fb  mov     [rsp+48h+var_20], rax
0x14000d900  mov     [rsp+48h+var_28], r9
0x14000d905  mov     r9, r8
0x14000d908  mov     r8, rdx
0x14000d90b  mov     rdx, rcx
0x14000d90e  call    ?ExecuteMonitorOperation@TLoad64BitDllsMgr@@QEAAXPEAU_RPC_ASYNC_STATE@@_KPEBG22W4EPortOp@@PEAK@Z; TLoad64BitDllsMgr::ExecuteMonitorOperation(_RPC_ASYNC_STATE *,unsigned __int64,ushort const *,ushort const *,ushort const *,EPortOp,ulong *)
0x14000d913  add     rsp, 48h
0x14000d917  retn
```
