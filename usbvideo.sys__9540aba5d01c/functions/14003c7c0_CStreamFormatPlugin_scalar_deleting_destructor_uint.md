# CStreamFormatPlugin::`scalar deleting destructor'(uint)

- ea: `0x14003c7c0`
- end: `0x14003c7e0`
- name: `??_GCStreamFormatPlugin@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CStreamFormatPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14000da90`
- `0x14003db10`

## callees

- `0x14003af44`
- `0x14003c698`

## pseudocode

```c
CStreamFormatPlugin *__fastcall CStreamFormatPlugin::`scalar deleting destructor'(CStreamFormatPlugin *this)
{
  CStreamFormatPlugin::~CStreamFormatPlugin(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14003c7c0  push    rbx
0x14003c7c2  sub     rsp, 20h
0x14003c7c6  mov     rbx, rcx
0x14003c7c9  call    ??1CStreamFormatPlugin@@QEAA@XZ; CStreamFormatPlugin::~CStreamFormatPlugin(void)
0x14003c7ce  mov     rcx, rbx; void *
0x14003c7d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003c7d6  mov     rax, rbx
0x14003c7d9  add     rsp, 20h
0x14003c7dd  pop     rbx
0x14003c7de  retn
```
