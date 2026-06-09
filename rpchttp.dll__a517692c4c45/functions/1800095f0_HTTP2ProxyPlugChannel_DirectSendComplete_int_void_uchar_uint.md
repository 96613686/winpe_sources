# HTTP2ProxyPlugChannel::DirectSendComplete(int *,void * *,uchar * *,uint *)

- ea: `0x1800095f0`
- end: `0x180009618`
- name: `?DirectSendComplete@HTTP2ProxyPlugChannel@@UEAAJPEAHPEAPEAXPEAPEAEPEAI@Z`
- size: `40`
- prototype: `__int64 __fastcall(HTTP2ProxyPlugChannel *__hidden this, int *, void **, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800094a0`

## pseudocode

```c
__int64 __fastcall HTTP2ProxyPlugChannel::DirectSendComplete(
        HTTP2ProxyPlugChannel *this,
        int *a2,
        void **a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int *v5; // rax
  int v7; // [rsp+48h] [rbp+10h] BYREF

  v5 = a5;
  *a2 = 0;
  HTTP2PlugChannel::DirectSendComplete(this, &v7, a3, a4, v5);
  return 3221360681LL;
}

```

## disassembly

```asm
0x1800095f0  sub     rsp, 38h
0x1800095f4  mov     rax, [rsp+38h+arg_20]
0x1800095f9  mov     dword ptr [rdx], 0
0x1800095ff  lea     rdx, [rsp+38h+arg_8]; int *
0x180009604  mov     [rsp+38h+var_18], rax; unsigned int *
0x180009609  call    ?DirectSendComplete@HTTP2PlugChannel@@UEAAJPEAHPEAPEAXPEAPEAEPEAI@Z; HTTP2PlugChannel::DirectSendComplete(int *,void * *,uchar * *,uint *)
0x18000960e  mov     eax, 0C0021029h
0x180009613  add     rsp, 38h
0x180009617  retn
```
