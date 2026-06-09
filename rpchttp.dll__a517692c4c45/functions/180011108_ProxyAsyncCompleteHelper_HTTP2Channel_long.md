# ProxyAsyncCompleteHelper(HTTP2Channel *,long)

- ea: `0x180011108`
- end: `0x18001119d`
- name: `?ProxyAsyncCompleteHelper@@YAJPEAVHTTP2Channel@@J@Z`
- size: `149`
- prototype: `__int64 __fastcall(struct HTTP2Channel *this, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800053a0`
- `0x1800053b0`

## callees

- `0x180003f94`
- `0x180009aa4`
- `0x18000f3fc`
- `0x180011108`
- `0x180016df8`
- `0x18001ac60`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall ProxyAsyncCompleteHelper(struct HTTP2Channel *this, unsigned int a2)
{
  HTTP2VirtualConnection *v4; // rax
  HTTP2VirtualConnection *v5; // rsi
  int v6; // ebx

  if ( a2 && a2 != -1073606615 )
  {
    v4 = HTTP2Channel::LockParentPointer(this);
    v5 = v4;
    if ( v4 )
    {
      v6 = HTTP2VirtualConnection::AbortAndDestroy(v4, 1, *((_DWORD *)this + 17), a2);
      HTTP2Channel::UnlockParentPointer(this);
      if ( v6 )
      {
        HTTP2Channel::DrainUpcallsAndFreeParentInternal(this, 0);
        (*(void (__fastcall **)(HTTP2VirtualConnection *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 1);
      }
    }
    else
    {
      (*(void (__fastcall **)(struct HTTP2Channel *, _QWORD))(*(_QWORD *)this + 40LL))(this, a2);
    }
  }
  HTTP2Channel::RemoveReference(this);
  return 0;
}

```

## disassembly

```asm
0x180011108  mov     [rsp+arg_0], rbx
0x18001110d  mov     [rsp+arg_8], rsi
0x180011112  push    rdi
0x180011113  sub     rsp, 20h
0x180011117  mov     ebx, edx
0x180011119  mov     rdi, rcx
0x18001111c  test    edx, edx
0x18001111e  jz      short loc_180011183
0x180011120  cmp     edx, 0C0021029h
0x180011126  jz      short loc_180011183
0x180011128  call    ?LockParentPointer@HTTP2Channel@@QEAAPEAVHTTP2VirtualConnection@@XZ; HTTP2Channel::LockParentPointer(void)
0x18001112d  mov     rsi, rax
0x180011130  test    rax, rax
0x180011133  jnz     short loc_180011143
0x180011135  mov     rax, [rdi]
0x180011138  mov     edx, ebx
0x18001113a  mov     rcx, rdi
0x18001113d  mov     rax, [rax+28h]
0x180011141  jmp     short loc_18001117E
0x180011143  mov     r8d, [rdi+44h]; int
0x180011147  mov     r9d, ebx; int
0x18001114a  mov     edx, 1; int
0x18001114f  mov     rcx, rsi; this
0x180011152  call    ?AbortAndDestroy@HTTP2VirtualConnection@@QEAAHHHJ@Z; HTTP2VirtualConnection::AbortAndDestroy(int,int,long)
0x180011157  mov     rcx, rdi; this
0x18001115a  mov     ebx, eax
0x18001115c  call    ?UnlockParentPointer@HTTP2Channel@@QEAAXXZ; HTTP2Channel::UnlockParentPointer(void)
0x180011161  test    ebx, ebx
0x180011163  jz      short loc_180011183
0x180011165  xor     edx, edx; int
0x180011167  mov     rcx, rdi; this
0x18001116a  call    ?DrainUpcallsAndFreeParentInternal@HTTP2Channel@@IEAAXH@Z; HTTP2Channel::DrainUpcallsAndFreeParentInternal(int)
0x18001116f  mov     rax, [rsi]
0x180011172  mov     edx, 1
0x180011177  mov     rcx, rsi
0x18001117a  mov     rax, [rax+8]
0x18001117e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011183  mov     rcx, rdi; this
0x180011186  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x18001118b  mov     rbx, [rsp+28h+arg_0]
0x180011190  xor     eax, eax
0x180011192  mov     rsi, [rsp+28h+arg_8]
0x180011197  add     rsp, 20h
0x18001119b  pop     rdi
0x18001119c  retn
```
