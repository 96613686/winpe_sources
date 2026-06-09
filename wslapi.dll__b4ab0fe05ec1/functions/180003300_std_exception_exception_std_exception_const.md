# std::exception::exception(std::exception const &)

- ea: `0x180003300`
- end: `0x180003332`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `50`
- prototype: `std::exception *__fastcall(std::exception *this, const struct std::exception *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031f8`
- `0x180009d64`
- `0x180009d8c`
- `0x18000a60c`

## callees

- `0x1800029c6`

## pseudocode

```c
std::exception *__fastcall std::exception::exception(std::exception *this, const struct std::exception *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  o___std_exception_copy_0((char *)a2 + 8);
  return this;
}

```

## disassembly

```asm
0x180003300  push    rbx
0x180003302  sub     rsp, 20h
0x180003306  mov     rbx, rcx
0x180003309  mov     rax, rdx
0x18000330c  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180003313  xorps   xmm0, xmm0
0x180003316  mov     [rbx], rcx
0x180003319  lea     rdx, [rbx+8]
0x18000331d  lea     rcx, [rax+8]
0x180003321  movups  xmmword ptr [rdx], xmm0
0x180003324  call    _o___std_exception_copy_0
0x180003329  mov     rax, rbx
0x18000332c  add     rsp, 20h
0x180003330  pop     rbx
0x180003331  retn
```
