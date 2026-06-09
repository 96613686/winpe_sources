# std::bad_alloc::bad_alloc(void)

- ea: `0x1800010c4`
- end: `0x180001105`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `65`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001398`

## callees

- `0x180001fd9`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this)
{
  char *v3; // [rsp+40h] [rbp+8h] BYREF

  v3 = "bad allocation";
  exception::exception(this, (const char *const *)&v3, 1);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x1800010c4  push    rbx
0x1800010c6  sub     rsp, 30h
0x1800010ca  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800010d3  mov     rbx, rcx
0x1800010d6  lea     rax, aBadAllocation; "bad allocation"
0x1800010dd  mov     [rsp+38h+arg_0], rax
0x1800010e2  mov     r8d, 1; int
0x1800010e8  lea     rdx, [rsp+38h+arg_0]; char **
0x1800010ed  call    ??0exception@@QEAA@AEBQEBDH@Z_0; exception::exception(char const * const &,int)
0x1800010f2  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800010f9  mov     [rbx], rax
0x1800010fc  mov     rax, rbx
0x1800010ff  add     rsp, 30h
0x180001103  pop     rbx
0x180001104  retn
```
