# std::bad_alloc::bad_alloc(void)

- ea: `0x180001fc4`
- end: `0x180001ff2`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002004`

## callees

- `0x1800020fa`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this)
{
  exception::exception(this, (const char *const *)&std::_bad_alloc_Message, 1);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001fc4  push    rbx
0x180001fc6  sub     rsp, 20h
0x180001fca  mov     r8d, 1; int
0x180001fd0  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char **
0x180001fd7  mov     rbx, rcx
0x180001fda  call    ??0exception@@QEAA@AEBQEBDH@Z_0; exception::exception(char const * const &,int)
0x180001fdf  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180001fe6  mov     [rbx], rax
0x180001fe9  mov     rax, rbx
0x180001fec  add     rsp, 20h
0x180001ff0  pop     rbx
0x180001ff1  retn
```
