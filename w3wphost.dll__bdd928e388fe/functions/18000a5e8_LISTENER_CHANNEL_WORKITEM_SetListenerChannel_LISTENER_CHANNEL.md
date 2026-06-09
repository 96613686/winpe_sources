# LISTENER_CHANNEL_WORKITEM::SetListenerChannel(LISTENER_CHANNEL *)

- ea: `0x18000a5e8`
- end: `0x18000a62f`
- name: `?SetListenerChannel@LISTENER_CHANNEL_WORKITEM@@QEAAXPEAVLISTENER_CHANNEL@@@Z`
- size: `71`
- prototype: `void __fastcall(LISTENER_CHANNEL_WORKITEM *__hidden this, struct LISTENER_CHANNEL *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180009ef0`
- `0x18000a7b0`
- `0x18000a8e0`

## callees

- `0x18000a5e8`
- `0x18000d010`

## pseudocode

```c
void __fastcall LISTENER_CHANNEL_WORKITEM::SetListenerChannel(
        LISTENER_CHANNEL_WORKITEM *this,
        struct LISTENER_CHANNEL *a2)
{
  __int64 v4; // rcx

  if ( a2 )
    (**(void (__fastcall ***)(struct LISTENER_CHANNEL *))a2)(a2);
  v4 = *((_QWORD *)this + 5);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  *((_QWORD *)this + 5) = a2;
}

```

## disassembly

```asm
0x18000a5e8  mov     [rsp+arg_0], rbx
0x18000a5ed  push    rdi
0x18000a5ee  sub     rsp, 20h
0x18000a5f2  mov     rbx, rdx
0x18000a5f5  mov     rdi, rcx
0x18000a5f8  test    rdx, rdx
0x18000a5fb  jz      short loc_18000A60B
0x18000a5fd  mov     rax, [rdx]
0x18000a600  mov     rcx, rdx
0x18000a603  mov     rax, [rax]
0x18000a606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a60b  mov     rcx, [rdi+28h]
0x18000a60f  test    rcx, rcx
0x18000a612  jz      short loc_18000A620
0x18000a614  mov     rax, [rcx]
0x18000a617  mov     rax, [rax+8]
0x18000a61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a620  mov     [rdi+28h], rbx
0x18000a624  mov     rbx, [rsp+28h+arg_0]
0x18000a629  add     rsp, 20h
0x18000a62d  pop     rdi
0x18000a62e  retn
```
