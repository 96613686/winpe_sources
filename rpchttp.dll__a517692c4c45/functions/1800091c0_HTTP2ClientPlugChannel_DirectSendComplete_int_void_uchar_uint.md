# HTTP2ClientPlugChannel::DirectSendComplete(int *,void * *,uchar * *,uint *)

- ea: `0x1800091c0`
- end: `0x1800091e3`
- name: `?DirectSendComplete@HTTP2ClientPlugChannel@@UEAAJPEAHPEAPEAXPEAPEAEPEAI@Z`
- size: `35`
- prototype: `__int64 __fastcall(HTTP2ClientPlugChannel *__hidden this, int *, void **, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800094a0`

## pseudocode

```c
__int64 __fastcall HTTP2ClientPlugChannel::DirectSendComplete(
        HTTP2ClientPlugChannel *this,
        int *a2,
        void **a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int *v5; // rax
  int v7; // [rsp+48h] [rbp+10h] BYREF

  v5 = a5;
  *a2 = 1;
  return HTTP2PlugChannel::DirectSendComplete(this, &v7, a3, a4, v5);
}

```

## disassembly

```asm
0x1800091c0  sub     rsp, 38h
0x1800091c4  mov     rax, [rsp+38h+arg_20]
0x1800091c9  mov     dword ptr [rdx], 1
0x1800091cf  lea     rdx, [rsp+38h+arg_8]; int *
0x1800091d4  mov     [rsp+38h+var_18], rax; unsigned int *
0x1800091d9  call    ?DirectSendComplete@HTTP2PlugChannel@@UEAAJPEAHPEAPEAXPEAPEAEPEAI@Z; HTTP2PlugChannel::DirectSendComplete(int *,void * *,uchar * *,uint *)
0x1800091de  add     rsp, 38h
0x1800091e2  retn
```
