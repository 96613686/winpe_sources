# std::bad_alloc::bad_alloc(std::bad_alloc const &)

- ea: `0x180001fa0`
- end: `0x180001fc1`
- name: `??0bad_alloc@std@@QEAA@AEBV01@@Z`
- size: `33`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this, const struct std::bad_alloc *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002004`
- `0x1800020d0`

## callees

- `0x180002100`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this, const struct std::bad_alloc *a2)
{
  exception::exception(this, a2);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001fa0  push    rbx
0x180001fa2  sub     rsp, 20h
0x180001fa6  mov     rbx, rcx
0x180001fa9  call    ??0exception@@QEAA@AEBV0@@Z_0; exception::exception(exception const &)
0x180001fae  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180001fb5  mov     [rbx], rax
0x180001fb8  mov     rax, rbx
0x180001fbb  add     rsp, 20h
0x180001fbf  pop     rbx
0x180001fc0  retn
```
