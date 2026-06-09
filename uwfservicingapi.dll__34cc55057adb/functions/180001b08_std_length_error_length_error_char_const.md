# std::length_error::length_error(char const *)

- ea: `0x180001b08`
- end: `0x180001b37`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `std::length_error *__fastcall(std::length_error *this, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001db8`
- `0x180001de4`

## callees

- `0x18000249d`

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
0x180001b08  mov     [rsp+arg_0], rcx
0x180001b0d  push    rbx
0x180001b0e  sub     rsp, 20h
0x180001b12  mov     [rsp+28h+arg_0], rdx
0x180001b17  mov     rbx, rcx
0x180001b1a  lea     rdx, [rsp+28h+arg_0]; char **
0x180001b1f  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x180001b24  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x180001b2b  mov     [rbx], rax
0x180001b2e  mov     rax, rbx
0x180001b31  add     rsp, 20h
0x180001b35  pop     rbx
0x180001b36  retn
```
