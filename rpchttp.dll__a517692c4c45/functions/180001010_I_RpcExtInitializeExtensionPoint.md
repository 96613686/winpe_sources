# I_RpcExtInitializeExtensionPoint

- ea: `0x180001010`
- end: `0x1800010a1`
- name: `I_RpcExtInitializeExtensionPoint`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001010`

## pseudocode

```c
__int64 __fastcall I_RpcExtInitializeExtensionPoint(int a1, _QWORD *a2)
{
  if ( a1 != 2 )
    return 87;
  *a2 = I_RpcGetRpcProxy;
  a2[1] = HTTP2ProcessComplexTSend;
  a2[2] = HTTP2ProcessComplexTReceive;
  a2[3] = HttpSendIdentifyResponse;
  a2[4] = CompareHttpTransportCredentials;
  a2[5] = ConvertToUnicodeHttpTransportCredentials;
  a2[6] = DuplicateHttpTransportCredentials;
  a2[7] = FreeHttpTransportCredentials;
  a2[8] = WS_HTTP2_INITIAL_CONNECTION__new;
  a2[9] = WS_HTTP2_CONNECTION__Initialize;
  a2[10] = HTTP2TestHook;
  a2[11] = &qword_180026010;
  return 0;
}

```

## disassembly

```asm
0x180001010  cmp     ecx, 2
0x180001013  jz      short loc_18000101B
0x180001015  mov     eax, 57h ; 'W'
0x18000101a  retn
0x18000101b  lea     rax, ?I_RpcGetRpcProxy@@YAJPEAGPEAPEAG@Z; I_RpcGetRpcProxy(ushort *,ushort * *)
0x180001022  mov     [rdx], rax
0x180001025  lea     rax, ?HTTP2ProcessComplexTSend@@YAJPEAXJPEAPEAE@Z; HTTP2ProcessComplexTSend(void *,long,uchar * *)
0x18000102c  mov     [rdx+8], rax
0x180001030  lea     rax, ?HTTP2ProcessComplexTReceive@@YAJPEAPEAXJKPEAPEAEPEAI@Z; HTTP2ProcessComplexTReceive(void * *,long,ulong,uchar * *,uint *)
0x180001037  mov     [rdx+10h], rax
0x18000103b  lea     rax, ?HttpSendIdentifyResponse@@YAJPEAX@Z; HttpSendIdentifyResponse(void *)
0x180001042  mov     [rdx+18h], rax
0x180001046  lea     rax, ?CompareHttpTransportCredentials@@YAHPEBU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@0@Z; CompareHttpTransportCredentials(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W const *,_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W const *)
0x18000104d  mov     [rdx+20h], rax
0x180001051  lea     rax, ?ConvertToUnicodeHttpTransportCredentials@@YAPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@PEBU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_A@@@Z; ConvertToUnicodeHttpTransportCredentials(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_A const *)
0x180001058  mov     [rdx+28h], rax
0x18000105c  lea     rax, ?DuplicateHttpTransportCredentials@@YAPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@PEBU1@@Z; DuplicateHttpTransportCredentials(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W const *)
0x180001063  mov     [rdx+30h], rax
0x180001067  lea     rax, ?FreeHttpTransportCredentials@@YAXPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@@Z; FreeHttpTransportCredentials(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *)
0x18000106e  mov     [rdx+38h], rax
0x180001072  lea     rax, ?WS_HTTP2_INITIAL_CONNECTION__new@@YAPEAVWS_CONNECTION@@PEAV1@@Z; WS_HTTP2_INITIAL_CONNECTION__new(WS_CONNECTION *)
0x180001079  mov     [rdx+40h], rax
0x18000107d  lea     rax, ?WS_HTTP2_CONNECTION__Initialize@@YAXPEAVWS_HTTP2_CONNECTION@@@Z; WS_HTTP2_CONNECTION__Initialize(WS_HTTP2_CONNECTION *)
0x180001084  mov     [rdx+48h], rax
0x180001088  lea     rax, ?HTTP2TestHook@@YAJW4tagSystemFunction001Commands@@PEAX1@Z; HTTP2TestHook(tagSystemFunction001Commands,void *,void *)
0x18000108f  mov     [rdx+50h], rax
0x180001093  lea     rax, qword_180026010
0x18000109a  mov     [rdx+58h], rax
0x18000109e  xor     eax, eax
0x1800010a0  retn
```
