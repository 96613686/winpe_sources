# LISTENER_CHANNEL_WORKITEM::SetListenerChannel(LISTENER_CHANNEL *)

- ea: `0x18000b2fc`
- end: `0x18000b344`
- name: `?SetListenerChannel@LISTENER_CHANNEL_WORKITEM@@QEAAXPEAVLISTENER_CHANNEL@@@Z`
- size: `72`
- prototype: `void __fastcall(LISTENER_CHANNEL_WORKITEM *__hidden this, struct LISTENER_CHANNEL *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aaf0`
- `0x18000b4ec`
- `0x18000b630`

## callees

- `0x18000b2fc`
- `0x18000e010`

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
0x18000b2fc  mov     [rsp+arg_0], rbx
0x18000b301  push    rdi
0x18000b302  sub     rsp, 20h
0x18000b306  mov     rbx, rdx
0x18000b309  mov     rdi, rcx
0x18000b30c  test    rdx, rdx
0x18000b30f  jz      short loc_18000B31F
0x18000b311  mov     rax, [rdx]
0x18000b314  mov     rcx, rdx
0x18000b317  mov     rax, [rax]
0x18000b31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b31f  mov     rcx, [rdi+28h]
0x18000b323  test    rcx, rcx
0x18000b326  jz      short loc_18000B334
0x18000b328  mov     rax, [rcx]
0x18000b32b  mov     rax, [rax+8]
0x18000b32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b334  mov     [rdi+28h], rbx
0x18000b338  mov     rbx, [rsp+28h+arg_0]
0x18000b33d  add     rsp, 20h
0x18000b341  pop     rdi
0x18000b342  retn
```
