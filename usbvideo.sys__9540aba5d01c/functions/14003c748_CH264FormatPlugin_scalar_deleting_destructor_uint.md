# CH264FormatPlugin::`scalar deleting destructor'(uint)

- ea: `0x14003c748`
- end: `0x14003c768`
- name: `??_GCH264FormatPlugin@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CH264FormatPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14000da90`
- `0x14003f550`

## callees

- `0x14003af44`
- `0x14003c608`

## pseudocode

```c
CH264FormatPlugin *__fastcall CH264FormatPlugin::`scalar deleting destructor'(CH264FormatPlugin *this)
{
  CH264FormatPlugin::~CH264FormatPlugin(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14003c748  push    rbx
0x14003c74a  sub     rsp, 20h
0x14003c74e  mov     rbx, rcx
0x14003c751  call    ??1CH264FormatPlugin@@QEAA@XZ; CH264FormatPlugin::~CH264FormatPlugin(void)
0x14003c756  mov     rcx, rbx; void *
0x14003c759  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003c75e  mov     rax, rbx
0x14003c761  add     rsp, 20h
0x14003c765  pop     rbx
0x14003c766  retn
```
