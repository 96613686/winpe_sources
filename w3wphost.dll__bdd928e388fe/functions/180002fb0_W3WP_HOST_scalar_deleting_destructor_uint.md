# W3WP_HOST::`scalar deleting destructor'(uint)

- ea: `0x180002fb0`
- end: `0x180002fcf`
- name: `??_GW3WP_HOST@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(W3WP_HOST *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003340`
- `0x180004750`
- `0x180004a40`
- `0x1800064b0`

## callees

- `0x180001fa8`
- `0x180002c20`

## pseudocode

```c
W3WP_HOST *__fastcall W3WP_HOST::`scalar deleting destructor'(W3WP_HOST *this)
{
  W3WP_HOST::~W3WP_HOST(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002fb0  push    rbx
0x180002fb2  sub     rsp, 20h
0x180002fb6  mov     rbx, rcx
0x180002fb9  call    ??1W3WP_HOST@@QEAA@XZ; W3WP_HOST::~W3WP_HOST(void)
0x180002fbe  mov     rcx, rbx; Block
0x180002fc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002fc6  mov     rax, rbx
0x180002fc9  add     rsp, 20h
0x180002fcd  pop     rbx
0x180002fce  retn
```
