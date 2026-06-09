# HTTP2Channel::SendComplete(long,HTTP2SendContext *)

- ea: `0x1800182f0`
- end: `0x180018330`
- name: `?SendComplete@HTTP2Channel@@UEAAJJPEAVHTTP2SendContext@@@Z`
- size: `64`
- prototype: `__int64 __fastcall(HTTP2Channel *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800187f0`

## callees

- `0x180005d18`
- `0x18000a44c`
- `0x1800182f0`

## pseudocode

```c
__int64 __fastcall HTTP2Channel::SendComplete(HTTP2Channel *this, unsigned int a2, struct HTTP2SendContext *a3)
{
  __int64 result; // rax

  result = HTTP2Channel::CheckSendCompleteForSync(this, a2, a3);
  if ( (_DWORD)result != -1073606615 )
    return HTTP2Channel::ForwardUpSendComplete(this, a2, a3);
  return result;
}

```

## disassembly

```asm
0x1800182f0  mov     [rsp+arg_0], rbx
0x1800182f5  mov     [rsp+arg_8], rsi
0x1800182fa  push    rdi
0x1800182fb  sub     rsp, 20h
0x1800182ff  mov     rbx, r8
0x180018302  mov     edi, edx
0x180018304  mov     rsi, rcx
0x180018307  call    ?CheckSendCompleteForSync@HTTP2Channel@@IEAAJJPEAVHTTP2SendContext@@@Z; HTTP2Channel::CheckSendCompleteForSync(long,HTTP2SendContext *)
0x18001830c  cmp     eax, 0C0021029h
0x180018311  jz      short loc_180018320
0x180018313  mov     r8, rbx; struct HTTP2SendContext *
0x180018316  mov     edx, edi; int
0x180018318  mov     rcx, rsi; this
0x18001831b  call    ?ForwardUpSendComplete@HTTP2Channel@@IEAAJJPEAVHTTP2SendContext@@@Z; HTTP2Channel::ForwardUpSendComplete(long,HTTP2SendContext *)
0x180018320  mov     rbx, [rsp+28h+arg_0]
0x180018325  mov     rsi, [rsp+28h+arg_8]
0x18001832a  add     rsp, 20h
0x18001832e  pop     rdi
0x18001832f  retn
```
