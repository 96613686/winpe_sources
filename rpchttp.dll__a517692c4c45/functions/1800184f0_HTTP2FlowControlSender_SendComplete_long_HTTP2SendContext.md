# HTTP2FlowControlSender::SendComplete(long,HTTP2SendContext *)

- ea: `0x1800184f0`
- end: `0x180018577`
- name: `?SendComplete@HTTP2FlowControlSender@@UEAAJJPEAVHTTP2SendContext@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(HTTP2FlowControlSender *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180016df8`
- `0x1800184f0`
- `0x180018980`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2FlowControlSender::SendComplete(
        HTTP2FlowControlSender *this,
        __int64 a2,
        struct HTTP2SendContext *a3)
{
  signed __int32 v4; // ebx
  unsigned int v5; // esi
  signed __int64 v6; // rax
  signed __int64 v7; // rbx
  unsigned int v8; // eax

  v4 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 28, 0xFFFFFFFF);
  v5 = HTTP2TransportChannel::SendComplete(this, a2, a3);
  if ( v4 == 1 )
  {
    v6 = *((_QWORD *)this + 13);
    if ( v6 )
    {
      v7 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 13, 0, v6);
      if ( v7 )
      {
        HTTP2Channel::RemoveReference(*((HTTP2Channel **)this + 3));
        v5 = (*(__int64 (__fastcall **)(_QWORD, signed __int64))(**((_QWORD **)this + 3) + 120LL))(
               *((_QWORD *)this + 3),
               v7);
        v8 = (*(__int64 (__fastcall **)(_QWORD, signed __int64))(**((_QWORD **)this + 3) + 8LL))(
               *((_QWORD *)this + 3),
               v7);
        if ( v8 )
          return v8;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800184f0  mov     [rsp+arg_0], rbx
0x1800184f5  mov     [rsp+arg_8], rsi
0x1800184fa  push    rdi
0x1800184fb  sub     rsp, 20h
0x1800184ff  mov     rdi, rcx
0x180018502  or      ebx, 0FFFFFFFFh
0x180018505  lock xadd [rcx+70h], ebx
0x18001850a  call    ?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)
0x18001850f  mov     esi, eax
0x180018511  cmp     ebx, 1
0x180018514  jnz     short loc_180018565
0x180018516  mov     rax, [rdi+68h]
0x18001851a  test    rax, rax
0x18001851d  jz      short loc_180018565
0x18001851f  xor     ecx, ecx
0x180018521  lock cmpxchg [rdi+68h], rcx
0x180018527  mov     rbx, rax
0x18001852a  test    rax, rax
0x18001852d  jz      short loc_180018565
0x18001852f  mov     rcx, [rdi+18h]; this
0x180018533  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x180018538  mov     rcx, [rdi+18h]
0x18001853c  mov     rdx, [rcx]
0x18001853f  mov     rax, [rdx+78h]
0x180018543  mov     rdx, rbx
0x180018546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001854b  mov     rcx, [rdi+18h]
0x18001854f  mov     esi, eax
0x180018551  mov     rdx, rbx
0x180018554  mov     rax, [rcx]
0x180018557  mov     rax, [rax+8]
0x18001855b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018560  test    eax, eax
0x180018562  cmovnz  esi, eax
0x180018565  mov     rbx, [rsp+28h+arg_0]
0x18001856a  mov     eax, esi
0x18001856c  mov     rsi, [rsp+28h+arg_8]
0x180018571  add     rsp, 20h
0x180018575  pop     rdi
0x180018576  retn
```
