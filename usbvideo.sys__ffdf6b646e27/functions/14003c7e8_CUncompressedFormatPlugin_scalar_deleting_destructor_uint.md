# CUncompressedFormatPlugin::`scalar deleting destructor'(uint)

- ea: `0x14003c7e8`
- end: `0x14003c808`
- name: `??_GCUncompressedFormatPlugin@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CUncompressedFormatPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000da90`
- `0x1400400a0`

## callees

- `0x14003af44`
- `0x14003c6c8`

## pseudocode

```c
CUncompressedFormatPlugin *__fastcall CUncompressedFormatPlugin::`scalar deleting destructor'(
        CUncompressedFormatPlugin *this)
{
  CUncompressedFormatPlugin::~CUncompressedFormatPlugin(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14003c7e8  push    rbx
0x14003c7ea  sub     rsp, 20h
0x14003c7ee  mov     rbx, rcx
0x14003c7f1  call    ??1CUncompressedFormatPlugin@@QEAA@XZ; CUncompressedFormatPlugin::~CUncompressedFormatPlugin(void)
0x14003c7f6  mov     rcx, rbx; void *
0x14003c7f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003c7fe  mov     rax, rbx
0x14003c801  add     rsp, 20h
0x14003c805  pop     rbx
0x14003c806  retn
```
