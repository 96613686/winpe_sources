# CUnbufferedWriter::`scalar deleting destructor'(uint)

- ea: `0x180007f74`
- end: `0x180007f98`
- name: `??_GCUnbufferedWriter@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(CUnbufferedWriter *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007bd8`
- `0x180009630`
- `0x180009820`

## callees

- `0x180001194`
- `0x18000c914`

## pseudocode

```c
HANDLE *__fastcall CUnbufferedWriter::`scalar deleting destructor'(HANDLE *this)
{
  CUnbufferedWriter::~CUnbufferedWriter(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007f74  push    rbx
0x180007f76  sub     rsp, 20h
0x180007f7a  mov     rbx, rcx
0x180007f7d  call    ??1CUnbufferedWriter@@QEAA@XZ; CUnbufferedWriter::~CUnbufferedWriter(void)
0x180007f82  mov     edx, 58h ; 'X'; unsigned __int64
0x180007f87  mov     rcx, rbx; void *
0x180007f8a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007f8f  mov     rax, rbx
0x180007f92  add     rsp, 20h
0x180007f96  pop     rbx
0x180007f97  retn
```
