# CMPEG2TSFormatPlugin::`scalar deleting destructor'(uint)

- ea: `0x14003c798`
- end: `0x14003c7b8`
- name: `??_GCMPEG2TSFormatPlugin@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CMPEG2TSFormatPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14000da90`
- `0x14003ec80`

## callees

- `0x14003af44`
- `0x14003c668`

## pseudocode

```c
CMPEG2TSFormatPlugin *__fastcall CMPEG2TSFormatPlugin::`scalar deleting destructor'(CMPEG2TSFormatPlugin *this)
{
  CMPEG2TSFormatPlugin::~CMPEG2TSFormatPlugin(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14003c798  push    rbx
0x14003c79a  sub     rsp, 20h
0x14003c79e  mov     rbx, rcx
0x14003c7a1  call    ??1CMPEG2TSFormatPlugin@@QEAA@XZ; CMPEG2TSFormatPlugin::~CMPEG2TSFormatPlugin(void)
0x14003c7a6  mov     rcx, rbx; void *
0x14003c7a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003c7ae  mov     rax, rbx
0x14003c7b1  add     rsp, 20h
0x14003c7b5  pop     rbx
0x14003c7b6  retn
```
