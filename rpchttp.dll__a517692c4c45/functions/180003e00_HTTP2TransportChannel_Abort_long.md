# HTTP2TransportChannel::Abort(long)

- ea: `0x180003e00`
- end: `0x180003e10`
- name: `?Abort@HTTP2TransportChannel@@UEAAXJ@Z`
- size: `16`
- prototype: `void __fastcall(HTTP2TransportChannel *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x180003960`
- `0x180003a20`
- `0x180003b90`
- `0x180003bd0`
- `0x180003c40`

## callees

- `0x180025010`

## pseudocode

```c
void __fastcall HTTP2TransportChannel::Abort(HTTP2TransportChannel *this)
{
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 40LL))(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x180003e00  mov     rcx, [rcx+8]
0x180003e04  mov     rax, [rcx]
0x180003e07  mov     rax, [rax+28h]
0x180003e0b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
