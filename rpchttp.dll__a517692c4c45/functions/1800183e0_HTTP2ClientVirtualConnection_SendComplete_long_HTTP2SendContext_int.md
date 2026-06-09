# HTTP2ClientVirtualConnection::SendComplete(long,HTTP2SendContext *,int)

- ea: `0x1800183e0`
- end: `0x1800184e9`
- name: `?SendComplete@HTTP2ClientVirtualConnection@@UEAAJJPEAVHTTP2SendContext@@H@Z`
- size: `265`
- prototype: `__int64 __fastcall(HTTP2ClientVirtualConnection *__hidden this, int, struct HTTP2SendContext *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003ffc`
- `0x18000aafc`
- `0x1800183e0`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180018415`
- `RPCRT4!I_RpcLogEvent` at `0x18001844c`
- `RPCRT4!I_RpcLogEvent` at `0x1800184d9`
- `RPCRT4!I_RpcLogEvent` at `0x180018415`
- `RPCRT4!I_RpcLogEvent` at `0x18001844c`
- `RPCRT4!I_RpcLogEvent` at `0x1800184d9`

## pseudocode

```c
__int64 __fastcall HTTP2ClientVirtualConnection::SendComplete(
        HTTP2ClientVirtualConnection *this,
        __int64 a2,
        struct HTTP2SendContext *a3,
        int a4)
{
  HTTP2ClientVirtualConnection *v5; // r8
  unsigned int v7; // esi
  int *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx

  v5 = this;
  v7 = a2;
  v8 = (int *)this;
  LOBYTE(this) = 50;
  LOBYTE(a2) = 111;
  I_RpcLogEvent(this, a2, v5, 17104907, (_DWORD)a3, 0, 0);
  if ( v7 )
  {
    if ( a4 != v8[v8[48] + 38] && a4 != v8[v8[68] + 58] )
    {
      if ( *((_DWORD *)a3 + 22) == 1 )
      {
        FreeSendContextAndPossiblyData(a3);
        HTTP2ClientVirtualConnection::AbortChannels((HTTP2ClientVirtualConnection *)v8, v7);
        v7 = -1073606615;
        goto LABEL_4;
      }
LABEL_3:
      v7 = 0;
LABEL_4:
      LOBYTE(v9) = 111;
      LOBYTE(v10) = 50;
      I_RpcLogEvent(v10, v9, v8, 327691, (_DWORD)a3, 0, 0);
      return v7;
    }
    HTTP2ClientVirtualConnection::AbortChannels((HTTP2ClientVirtualConnection *)v8, v7);
    if ( *((_DWORD *)a3 + 22) != 1 )
      goto LABEL_4;
  }
  else if ( *((_DWORD *)a3 + 22) != 1 )
  {
    goto LABEL_3;
  }
  FreeSendContextAndPossiblyData(a3);
  LOBYTE(v12) = 111;
  LOBYTE(v13) = 50;
  I_RpcLogEvent(v13, v12, v8, 327691, (_DWORD)a3, 0, 0);
  return 3221360681LL;
}

```

## disassembly

```asm
0x1800183e0  push    rbx
0x1800183e2  push    rbp
0x1800183e3  push    rsi
0x1800183e4  push    rdi
0x1800183e5  sub     rsp, 48h
0x1800183e9  mov     rdi, r8
0x1800183ec  mov     [rsp+68h+var_38], 0
0x1800183f4  mov     r8, rcx
0x1800183f7  mov     [rsp+68h+var_40], 0
0x1800183ff  mov     ebp, r9d
0x180018402  mov     [rsp+68h+var_48], edi
0x180018406  mov     esi, edx
0x180018408  mov     rbx, rcx
0x18001840b  mov     cl, 32h ; '2'
0x18001840d  mov     r9d, 105000Bh
0x180018413  mov     dl, 6Fh ; 'o'
0x180018415  call    cs:__imp_I_RpcLogEvent
0x18001841b  test    esi, esi
0x18001841d  jnz     short loc_18001845D
0x18001841f  cmp     dword ptr [rdi+58h], 1
0x180018423  jz      loc_1800184B0
0x180018429  xor     esi, esi
0x18001842b  mov     [rsp+68h+var_38], 0
0x180018433  mov     r9d, 5000Bh
0x180018439  mov     [rsp+68h+var_40], 0
0x180018441  mov     r8, rbx
0x180018444  mov     dl, 6Fh ; 'o'
0x180018446  mov     [rsp+68h+var_48], edi
0x18001844a  mov     cl, 32h ; '2'
0x18001844c  call    cs:__imp_I_RpcLogEvent
0x180018452  mov     eax, esi
0x180018454  add     rsp, 48h
0x180018458  pop     rdi
0x180018459  pop     rsi
0x18001845a  pop     rbp
0x18001845b  pop     rbx
0x18001845c  retn
0x18001845d  movsxd  rax, dword ptr [rbx+0C0h]
0x180018464  cmp     ebp, [rbx+rax*4+98h]
0x18001846b  jz      short loc_18001849C
0x18001846d  movsxd  rax, dword ptr [rbx+110h]
0x180018474  cmp     ebp, [rbx+rax*4+0E8h]
0x18001847b  jz      short loc_18001849C
0x18001847d  cmp     dword ptr [rdi+58h], 1
0x180018481  jnz     short loc_180018429
0x180018483  mov     rcx, rdi; struct HTTP2SendContext *
0x180018486  call    ?FreeSendContextAndPossiblyData@@YAXPEAVHTTP2SendContext@@@Z; FreeSendContextAndPossiblyData(HTTP2SendContext *)
0x18001848b  mov     edx, esi; int
0x18001848d  mov     rcx, rbx; this
0x180018490  call    ?AbortChannels@HTTP2ClientVirtualConnection@@QEAAXJ@Z; HTTP2ClientVirtualConnection::AbortChannels(long)
0x180018495  mov     esi, 0C0021029h
0x18001849a  jmp     short loc_18001842B
0x18001849c  mov     edx, esi; int
0x18001849e  mov     rcx, rbx; this
0x1800184a1  call    ?AbortChannels@HTTP2ClientVirtualConnection@@QEAAXJ@Z; HTTP2ClientVirtualConnection::AbortChannels(long)
0x1800184a6  cmp     dword ptr [rdi+58h], 1
0x1800184aa  jnz     loc_18001842B
0x1800184b0  mov     rcx, rdi; struct HTTP2SendContext *
0x1800184b3  call    ?FreeSendContextAndPossiblyData@@YAXPEAVHTTP2SendContext@@@Z; FreeSendContextAndPossiblyData(HTTP2SendContext *)
0x1800184b8  mov     [rsp+68h+var_38], 0
0x1800184c0  mov     r9d, 5000Bh
0x1800184c6  mov     [rsp+68h+var_40], 0
0x1800184ce  mov     r8, rbx
0x1800184d1  mov     dl, 6Fh ; 'o'
0x1800184d3  mov     [rsp+68h+var_48], edi
0x1800184d7  mov     cl, 32h ; '2'
0x1800184d9  call    cs:__imp_I_RpcLogEvent
0x1800184df  mov     eax, 0C0021029h
0x1800184e4  jmp     loc_180018454
```
