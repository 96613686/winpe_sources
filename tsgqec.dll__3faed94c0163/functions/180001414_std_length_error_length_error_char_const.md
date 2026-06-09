# std::length_error::length_error(char const *)

- ea: `0x180001414`
- end: `0x180001443`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `__int64 __fastcall(std::length_error *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016b8`
- `0x1800016e4`

## callees

- `0x180002285`

## pseudocode

```c
std::length_error *__fastcall std::length_error::length_error(std::length_error *this, char *a2)
{
  char *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a2;
  exception::exception(this, (const char *const *)&v4);
  *(_QWORD *)this = &std::length_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001414  mov     [rsp+arg_0], rcx
0x180001419  push    rbx
0x18000141a  sub     rsp, 20h
0x18000141e  mov     [rsp+28h+arg_0], rdx
0x180001423  mov     rbx, rcx
0x180001426  lea     rdx, [rsp+28h+arg_0]; char **
0x18000142b  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x180001430  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x180001437  mov     [rbx], rax
0x18000143a  mov     rax, rbx
0x18000143d  add     rsp, 20h
0x180001441  pop     rbx
0x180001442  retn
```
