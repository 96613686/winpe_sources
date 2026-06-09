# CFrameFormatPlugin::`scalar deleting destructor'(uint)

- ea: `0x14003c720`
- end: `0x14003c740`
- name: `??_GCFrameFormatPlugin@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CFrameFormatPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14000da90`
- `0x14003e730`

## callees

- `0x14003af44`
- `0x14003c5d8`

## pseudocode

```c
CFrameFormatPlugin *__fastcall CFrameFormatPlugin::`scalar deleting destructor'(CFrameFormatPlugin *this)
{
  CFrameFormatPlugin::~CFrameFormatPlugin(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14003c720  push    rbx
0x14003c722  sub     rsp, 20h
0x14003c726  mov     rbx, rcx
0x14003c729  call    ??1CFrameFormatPlugin@@QEAA@XZ; CFrameFormatPlugin::~CFrameFormatPlugin(void)
0x14003c72e  mov     rcx, rbx; void *
0x14003c731  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003c736  mov     rax, rbx
0x14003c739  add     rsp, 20h
0x14003c73d  pop     rbx
0x14003c73e  retn
```
