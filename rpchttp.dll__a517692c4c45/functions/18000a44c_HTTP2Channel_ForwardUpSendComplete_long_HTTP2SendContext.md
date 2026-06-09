# HTTP2Channel::ForwardUpSendComplete(long,HTTP2SendContext *)

- ea: `0x18000a44c`
- end: `0x18000a4e5`
- name: `?ForwardUpSendComplete@HTTP2Channel@@IEAAJJPEAVHTTP2SendContext@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(HTTP2Channel *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800182f0`
- `0x180018340`

## callees

- `0x18000a44c`
- `0x18000aafc`
- `0x18000f060`
- `0x18000f3fc`
- `0x18001ac60`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2Channel::ForwardUpSendComplete(
        HTTP2Channel *this,
        unsigned int a2,
        struct HTTP2SendContext *a3)
{
  struct HTTP2VirtualConnection *v6; // rax

  v6 = HTTP2Channel::LockParentPointer(this);
  if ( v6 )
  {
    a2 = (*(__int64 (__fastcall **)(struct HTTP2VirtualConnection *, _QWORD, struct HTTP2SendContext *, _QWORD))(*(_QWORD *)v6 + 32LL))(
           v6,
           a2,
           a3,
           *((unsigned int *)this + 17));
    HTTP2Channel::UnlockParentPointer(this);
  }
  else
  {
    if ( a2 )
    {
      (*(void (__fastcall **)(HTTP2Channel *, _QWORD))(*(_QWORD *)this + 40LL))(this, a2);
    }
    else
    {
      a2 = -1073606615;
      if ( *((_DWORD *)a3 + 22) != 1 )
        a2 = 0;
    }
    if ( *((_DWORD *)a3 + 22) == 1 || (unsigned int)HTTP2Channel::IsProxyChannel(this) )
    {
      FreeSendContextAndPossiblyData(a3);
      return 3221360681LL;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18000a44c  mov     [rsp+arg_0], rbx
0x18000a451  mov     [rsp+arg_8], rsi
0x18000a456  push    rdi
0x18000a457  sub     rsp, 30h
0x18000a45b  mov     rdi, r8
0x18000a45e  mov     ebx, edx
0x18000a460  mov     rsi, rcx
0x18000a463  call    ?LockParentPointer@HTTP2Channel@@QEAAPEAVHTTP2VirtualConnection@@XZ; HTTP2Channel::LockParentPointer(void)
0x18000a468  mov     rcx, rax
0x18000a46b  test    rax, rax
0x18000a46e  jnz     short loc_18000A4B4
0x18000a470  test    ebx, ebx
0x18000a472  jnz     short loc_18000A482
0x18000a474  cmp     dword ptr [rdi+58h], 1
0x18000a478  mov     ebx, 0C0021029h
0x18000a47d  cmovnz  ebx, eax
0x18000a480  jmp     short loc_18000A493
0x18000a482  mov     rax, [rsi]
0x18000a485  mov     edx, ebx
0x18000a487  mov     rcx, rsi
0x18000a48a  mov     rax, [rax+28h]
0x18000a48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a493  cmp     dword ptr [rdi+58h], 1
0x18000a497  jz      short loc_18000A4A5
0x18000a499  mov     rcx, rsi; this
0x18000a49c  call    ?IsProxyChannel@HTTP2Channel@@QEAAHXZ; HTTP2Channel::IsProxyChannel(void)
0x18000a4a1  test    eax, eax
0x18000a4a3  jz      short loc_18000A4D3
0x18000a4a5  mov     rcx, rdi; struct HTTP2SendContext *
0x18000a4a8  call    ?FreeSendContextAndPossiblyData@@YAXPEAVHTTP2SendContext@@@Z; FreeSendContextAndPossiblyData(HTTP2SendContext *)
0x18000a4ad  mov     eax, 0C0021029h
0x18000a4b2  jmp     short loc_18000A4D5
0x18000a4b4  mov     rax, [rax]
0x18000a4b7  mov     r8, rdi
0x18000a4ba  mov     r9d, [rsi+44h]
0x18000a4be  mov     edx, ebx
0x18000a4c0  mov     rax, [rax+20h]
0x18000a4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c9  mov     rcx, rsi; this
0x18000a4cc  mov     ebx, eax
0x18000a4ce  call    ?UnlockParentPointer@HTTP2Channel@@QEAAXXZ; HTTP2Channel::UnlockParentPointer(void)
0x18000a4d3  mov     eax, ebx
0x18000a4d5  mov     rbx, [rsp+38h+arg_0]
0x18000a4da  mov     rsi, [rsp+38h+arg_8]
0x18000a4df  add     rsp, 30h
0x18000a4e3  pop     rdi
0x18000a4e4  retn
```
