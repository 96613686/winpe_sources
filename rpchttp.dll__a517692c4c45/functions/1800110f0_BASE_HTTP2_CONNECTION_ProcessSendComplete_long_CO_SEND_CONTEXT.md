# BASE_HTTP2_CONNECTION::ProcessSendComplete(long,CO_SEND_CONTEXT *)

- ea: `0x1800110f0`
- end: `0x180011100`
- name: `?ProcessSendComplete@BASE_HTTP2_CONNECTION@@UEAAJJPEAUCO_SEND_CONTEXT@@@Z`
- size: `16`
- prototype: `__int64 __fastcall(BASE_HTTP2_CONNECTION *__hidden this, int, struct CO_SEND_CONTEXT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall BASE_HTTP2_CONNECTION::ProcessSendComplete(
        BASE_HTTP2_CONNECTION *this,
        __int64 a2,
        struct CO_SEND_CONTEXT *a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, __int64, struct CO_SEND_CONTEXT *))(**((_QWORD **)this + 1) + 24LL))(
           *((_QWORD *)this + 1),
           a2,
           a3);
}

```

## disassembly

```asm
0x1800110f0  mov     rcx, [rcx+8]
0x1800110f4  mov     rax, [rcx]
0x1800110f7  mov     rax, [rax+18h]
0x1800110fb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
