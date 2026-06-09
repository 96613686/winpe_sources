# HTTP2Channel::ForwardUpReceiveComplete(long,uchar *,uint)

- ea: `0x18000a3b4`
- end: `0x18000a444`
- name: `?ForwardUpReceiveComplete@HTTP2Channel@@IEAAJJPEAEI@Z`
- size: `144`
- prototype: `__int64 __fastcall(HTTP2Channel *__hidden this, int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012050`

## callees

- `0x18000a3b4`
- `0x18000f3fc`
- `0x18001ac60`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2Channel::ForwardUpReceiveComplete(
        HTTP2Channel *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  struct HTTP2VirtualConnection *v8; // rax
  unsigned int v10; // edi

  v8 = HTTP2Channel::LockParentPointer(this);
  if ( v8 )
  {
    v10 = (*(__int64 (__fastcall **)(struct HTTP2VirtualConnection *, _QWORD, unsigned __int8 *, _QWORD, _DWORD))(*(_QWORD *)v8 + 40LL))(
            v8,
            a2,
            a3,
            a4,
            *((_DWORD *)this + 17));
    HTTP2Channel::UnlockParentPointer(this);
    if ( v10 == -1073606611 )
    {
      (*(void (__fastcall **)(HTTP2Channel *, __int64))(*(_QWORD *)this + 40LL))(this, 3221360658LL);
      return (unsigned int)-1073606615;
    }
    return v10;
  }
  else
  {
    (*(void (__fastcall **)(HTTP2Channel *, __int64))(*(_QWORD *)this + 40LL))(this, 3221360658LL);
    return 3221360681LL;
  }
}

```

## disassembly

```asm
0x18000a3b4  push    rbx
0x18000a3b6  push    rbp
0x18000a3b7  push    rsi
0x18000a3b8  push    rdi
0x18000a3b9  sub     rsp, 38h
0x18000a3bd  mov     edi, r9d
0x18000a3c0  mov     rsi, r8
0x18000a3c3  mov     ebp, edx
0x18000a3c5  mov     rbx, rcx
0x18000a3c8  call    ?LockParentPointer@HTTP2Channel@@QEAAPEAVHTTP2VirtualConnection@@XZ; HTTP2Channel::LockParentPointer(void)
0x18000a3cd  mov     r10, rax
0x18000a3d0  test    rax, rax
0x18000a3d3  jnz     short loc_18000A3F0
0x18000a3d5  mov     rax, [rbx]
0x18000a3d8  mov     edx, 0C0021012h
0x18000a3dd  mov     rcx, rbx
0x18000a3e0  mov     rax, [rax+28h]
0x18000a3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3e9  mov     eax, 0C0021029h
0x18000a3ee  jmp     short loc_18000A43B
0x18000a3f0  mov     ecx, [rbx+44h]
0x18000a3f3  mov     r9d, edi
0x18000a3f6  mov     rax, [rax]
0x18000a3f9  mov     r8, rsi
0x18000a3fc  mov     [rsp+58h+var_38], ecx
0x18000a400  mov     edx, ebp
0x18000a402  mov     rcx, r10
0x18000a405  mov     rax, [rax+28h]
0x18000a409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a40e  mov     rcx, rbx; this
0x18000a411  mov     edi, eax
0x18000a413  call    ?UnlockParentPointer@HTTP2Channel@@QEAAXXZ; HTTP2Channel::UnlockParentPointer(void)
0x18000a418  cmp     edi, 0C002102Dh
0x18000a41e  jnz     short loc_18000A439
0x18000a420  mov     rax, [rbx]
0x18000a423  mov     edx, 0C0021012h
0x18000a428  mov     rcx, rbx
0x18000a42b  mov     rax, [rax+28h]
0x18000a42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a434  mov     edi, 0C0021029h
0x18000a439  mov     eax, edi
0x18000a43b  add     rsp, 38h
0x18000a43f  pop     rdi
0x18000a440  pop     rsi
0x18000a441  pop     rbp
0x18000a442  pop     rbx
0x18000a443  retn
```
