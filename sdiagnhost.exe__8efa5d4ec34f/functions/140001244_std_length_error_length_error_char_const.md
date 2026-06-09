# std::length_error::length_error(char const *)

- ea: `0x140001244`
- end: `0x140001273`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `std::length_error *__fastcall(std::length_error *this, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001340`
- `0x14000136c`

## callees

- `0x1400018d1`

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
0x140001244  mov     [rsp+arg_0], rcx
0x140001249  push    rbx
0x14000124a  sub     rsp, 20h
0x14000124e  mov     [rsp+28h+arg_0], rdx
0x140001253  mov     rbx, rcx
0x140001256  lea     rdx, [rsp+28h+arg_0]; char **
0x14000125b  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x140001260  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x140001267  mov     [rbx], rax
0x14000126a  mov     rax, rbx
0x14000126d  add     rsp, 20h
0x140001271  pop     rbx
0x140001272  retn
```
