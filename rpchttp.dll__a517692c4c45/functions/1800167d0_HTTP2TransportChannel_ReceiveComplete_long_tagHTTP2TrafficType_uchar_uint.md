# HTTP2TransportChannel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)

- ea: `0x1800167d0`
- end: `0x1800167f3`
- name: `?ReceiveComplete@HTTP2TransportChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008b30`
- `0x180011fb0`
- `0x180013200`
- `0x180015790`
- `0x180015850`

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2TransportChannel::ReceiveComplete(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 32LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x1800167d0  sub     rsp, 38h
0x1800167d4  mov     rcx, [rcx+10h]
0x1800167d8  mov     r10d, [rsp+38h+arg_20]
0x1800167dd  mov     [rsp+38h+var_18], r10d
0x1800167e2  mov     rax, [rcx]
0x1800167e5  mov     rax, [rax+20h]
0x1800167e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167ee  add     rsp, 38h
0x1800167f2  retn
```
