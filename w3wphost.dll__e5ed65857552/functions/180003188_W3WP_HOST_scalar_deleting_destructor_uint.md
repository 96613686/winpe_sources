# W3WP_HOST::`scalar deleting destructor'(uint)

- ea: `0x180003188`
- end: `0x1800031a8`
- name: `??_GW3WP_HOST@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(W3WP_HOST *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003540`
- `0x180004b20`
- `0x180004e50`
- `0x180006b00`

## callees

- `0x1800020d0`
- `0x180002dbc`

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
0x180003188  push    rbx
0x18000318a  sub     rsp, 20h
0x18000318e  mov     rbx, rcx
0x180003191  call    ??1W3WP_HOST@@QEAA@XZ; W3WP_HOST::~W3WP_HOST(void)
0x180003196  mov     rcx, rbx; Block
0x180003199  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000319e  mov     rax, rbx
0x1800031a1  add     rsp, 20h
0x1800031a5  pop     rbx
0x1800031a6  retn
```
