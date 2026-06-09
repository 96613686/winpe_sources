# CMJPEGFormatPlugin::`scalar deleting destructor'(uint)

- ea: `0x14003c770`
- end: `0x14003c790`
- name: `??_GCMJPEGFormatPlugin@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CMJPEGFormatPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14000da90`
- `0x1400142d0`

## callees

- `0x14003af44`
- `0x14003c638`

## pseudocode

```c
CMJPEGFormatPlugin *__fastcall CMJPEGFormatPlugin::`scalar deleting destructor'(CMJPEGFormatPlugin *this)
{
  CMJPEGFormatPlugin::~CMJPEGFormatPlugin(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14003c770  push    rbx
0x14003c772  sub     rsp, 20h
0x14003c776  mov     rbx, rcx
0x14003c779  call    ??1CMJPEGFormatPlugin@@QEAA@XZ; CMJPEGFormatPlugin::~CMJPEGFormatPlugin(void)
0x14003c77e  mov     rcx, rbx; void *
0x14003c781  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003c786  mov     rax, rbx
0x14003c789  add     rsp, 20h
0x14003c78d  pop     rbx
0x14003c78e  retn
```
