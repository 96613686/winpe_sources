# HTTP2IISTransportChannel::ReceiveCompleteInternal(long,tagHTTP2TrafficType,int,uchar * *,uint *)

- ea: `0x1800168a0`
- end: `0x1800168bc`
- name: `?ReceiveCompleteInternal@HTTP2IISTransportChannel@@MEAAJJW4tagHTTP2TrafficType@@HPEAPEAEPEAI@Z`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180013630`
- `0x1800168a0`

## pseudocode

```c
__int64 __fastcall HTTP2IISTransportChannel::ReceiveCompleteInternal(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        _QWORD *a5,
        unsigned int *a6)
{
  if ( a4 )
    --*(_DWORD *)(a1 + 88);
  return HTTP2FragmentReceiver::ReceiveComplete((__int64 *)a1, a2, a3, a5, a6);
}

```

## disassembly

```asm
0x1800168a0  test    r9d, r9d
0x1800168a3  jz      short loc_1800168A8
0x1800168a5  dec     dword ptr [rcx+58h]
0x1800168a8  mov     rax, [rsp+arg_28]
0x1800168ad  mov     r9, [rsp+arg_20]
0x1800168b2  mov     [rsp+arg_20], rax
0x1800168b7  jmp     ?ReceiveComplete@HTTP2FragmentReceiver@@UEAAJJW4tagHTTP2TrafficType@@PEAPEAEPEAI@Z; HTTP2FragmentReceiver::ReceiveComplete(long,tagHTTP2TrafficType,uchar * *,uint *)
```
