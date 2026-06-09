# LISTENER_CHANNEL_WORKITEM::~LISTENER_CHANNEL_WORKITEM(void)

- ea: `0x18000ac24`
- end: `0x18000ac61`
- name: `??1LISTENER_CHANNEL_WORKITEM@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(LISTENER_CHANNEL_WORKITEM *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ac90`
- `0x18000acd0`
- `0x18000ad10`

## callees

- `0x18000ac24`
- `0x18000ac68`
- `0x18000e010`

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
0x18000ac24  push    rbx
0x18000ac26  sub     rsp, 20h
0x18000ac2a  lea     rax, ??_7LISTENER_CHANNEL_WORKITEM@@6B@; const LISTENER_CHANNEL_WORKITEM::`vftable'
0x18000ac31  mov     rbx, rcx
0x18000ac34  mov     [rcx], rax
0x18000ac37  mov     rcx, [rcx+28h]
0x18000ac3b  test    rcx, rcx
0x18000ac3e  jz      short loc_18000AC54
0x18000ac40  mov     rax, [rcx]
0x18000ac43  mov     rax, [rax+8]
0x18000ac47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac4c  mov     qword ptr [rbx+28h], 0
0x18000ac54  mov     rcx, rbx; this
0x18000ac57  add     rsp, 20h
0x18000ac5b  pop     rbx
0x18000ac5c  jmp     ??1W3WP_HOST_WORKITEM@@UEAA@XZ; W3WP_HOST_WORKITEM::~W3WP_HOST_WORKITEM(void)
```
