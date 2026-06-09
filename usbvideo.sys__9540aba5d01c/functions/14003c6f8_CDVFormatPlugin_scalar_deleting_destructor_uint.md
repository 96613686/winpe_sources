# CDVFormatPlugin::`scalar deleting destructor'(uint)

- ea: `0x14003c6f8`
- end: `0x14003c718`
- name: `??_GCDVFormatPlugin@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CDVFormatPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14000da90`
- `0x14003d470`

## callees

- `0x14003af44`
- `0x14003c5a8`

## pseudocode

```c
CDVFormatPlugin *__fastcall CDVFormatPlugin::`scalar deleting destructor'(CDVFormatPlugin *this)
{
  CDVFormatPlugin::~CDVFormatPlugin(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14003c6f8  push    rbx
0x14003c6fa  sub     rsp, 20h
0x14003c6fe  mov     rbx, rcx
0x14003c701  call    ??1CDVFormatPlugin@@QEAA@XZ; CDVFormatPlugin::~CDVFormatPlugin(void)
0x14003c706  mov     rcx, rbx; void *
0x14003c709  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003c70e  mov     rax, rbx
0x14003c711  add     rsp, 20h
0x14003c715  pop     rbx
0x14003c716  retn
```
