# LISTENER_CHANNEL_WORKITEM::~LISTENER_CHANNEL_WORKITEM(void)

- ea: `0x18000a004`
- end: `0x18000a041`
- name: `??1LISTENER_CHANNEL_WORKITEM@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(LISTENER_CHANNEL_WORKITEM *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a070`
- `0x18000a0b0`
- `0x18000a0f0`

## callees

- `0x18000a004`
- `0x18000a048`
- `0x18000d010`

## pseudocode

```c
void __fastcall LISTENER_CHANNEL_WORKITEM::~LISTENER_CHANNEL_WORKITEM(LISTENER_CHANNEL_WORKITEM *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &LISTENER_CHANNEL_WORKITEM::`vftable';
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 5) = 0;
  }
  W3WP_HOST_WORKITEM::~W3WP_HOST_WORKITEM(this);
}

```

## disassembly

```asm
0x18000a004  push    rbx
0x18000a006  sub     rsp, 20h
0x18000a00a  lea     rax, ??_7LISTENER_CHANNEL_WORKITEM@@6B@; const LISTENER_CHANNEL_WORKITEM::`vftable'
0x18000a011  mov     rbx, rcx
0x18000a014  mov     [rcx], rax
0x18000a017  mov     rcx, [rcx+28h]
0x18000a01b  test    rcx, rcx
0x18000a01e  jz      short loc_18000A034
0x18000a020  mov     rax, [rcx]
0x18000a023  mov     rax, [rax+8]
0x18000a027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a02c  mov     qword ptr [rbx+28h], 0
0x18000a034  mov     rcx, rbx; this
0x18000a037  add     rsp, 20h
0x18000a03b  pop     rbx
0x18000a03c  jmp     ??1W3WP_HOST_WORKITEM@@UEAA@XZ; W3WP_HOST_WORKITEM::~W3WP_HOST_WORKITEM(void)
```
