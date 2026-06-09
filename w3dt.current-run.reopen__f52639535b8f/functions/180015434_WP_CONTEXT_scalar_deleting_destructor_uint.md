# WP_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x180015434`
- end: `0x180015453`
- name: `??_GWP_CONTEXT@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(WP_CONTEXT *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180015660`
- `0x180015a40`

## callees

- `0x1800135cc`
- `0x180014740`

## pseudocode

```c
WP_CONTEXT *__fastcall WP_CONTEXT::`scalar deleting destructor'(WP_CONTEXT *this)
{
  WP_CONTEXT::~WP_CONTEXT(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180015434  push    rbx
0x180015436  sub     rsp, 20h
0x18001543a  mov     rbx, rcx
0x18001543d  call    ??1WP_CONTEXT@@QEAA@XZ; WP_CONTEXT::~WP_CONTEXT(void)
0x180015442  mov     rcx, rbx; Block
0x180015445  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001544a  mov     rax, rbx
0x18001544d  add     rsp, 20h
0x180015451  pop     rbx
0x180015452  retn
```
