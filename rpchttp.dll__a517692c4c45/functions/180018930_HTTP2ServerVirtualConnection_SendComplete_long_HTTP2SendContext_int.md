# HTTP2ServerVirtualConnection::SendComplete(long,HTTP2SendContext *,int)

- ea: `0x180018930`
- end: `0x180018970`
- name: `?SendComplete@HTTP2ServerVirtualConnection@@UEAAJJPEAVHTTP2SendContext@@H@Z`
- size: `64`
- prototype: `__int64 __fastcall(HTTP2ServerVirtualConnection *__hidden this, int, struct HTTP2SendContext *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004058`
- `0x18000aafc`
- `0x180018930`

## pseudocode

```c
__int64 __fastcall HTTP2ServerVirtualConnection::SendComplete(
        HTTP2ServerVirtualConnection *this,
        unsigned int a2,
        struct HTTP2SendContext *a3)
{
  if ( *((_DWORD *)a3 + 22) != 1 )
    return a2;
  FreeSendContextAndPossiblyData(a3);
  if ( a2 )
    HTTP2VirtualConnection::AbortChannels(this, a2);
  return 3221360681LL;
}

```

## disassembly

```asm
0x180018930  mov     [rsp+arg_0], rbx
0x180018935  push    rdi
0x180018936  sub     rsp, 20h
0x18001893a  cmp     dword ptr [r8+58h], 1
0x18001893f  mov     ebx, edx
0x180018941  mov     rdi, rcx
0x180018944  jnz     short loc_180018963
0x180018946  mov     rcx, r8; struct HTTP2SendContext *
0x180018949  call    ?FreeSendContextAndPossiblyData@@YAXPEAVHTTP2SendContext@@@Z; FreeSendContextAndPossiblyData(HTTP2SendContext *)
0x18001894e  test    ebx, ebx
0x180018950  jz      short loc_18001895C
0x180018952  mov     edx, ebx; int
0x180018954  mov     rcx, rdi; this
0x180018957  call    ?AbortChannels@HTTP2VirtualConnection@@QEAAXJ@Z; HTTP2VirtualConnection::AbortChannels(long)
0x18001895c  mov     eax, 0C0021029h
0x180018961  jmp     short loc_180018965
0x180018963  mov     eax, ebx
0x180018965  mov     rbx, [rsp+28h+arg_0]
0x18001896a  add     rsp, 20h
0x18001896e  pop     rdi
0x18001896f  retn
```
