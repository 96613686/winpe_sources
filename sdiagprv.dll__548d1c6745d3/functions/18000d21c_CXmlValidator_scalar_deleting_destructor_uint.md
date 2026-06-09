# CXmlValidator::`scalar deleting destructor'(uint)

- ea: `0x18000d21c`
- end: `0x18000d23b`
- name: `??_GCXmlValidator@@QEAAPEAXI@Z`
- size: `31`
- prototype: `CXmlValidator *__fastcall(CXmlValidator *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000d748`
- `0x180016858`

## callees

- `0x1800010b4`
- `0x1800166b4`

## pseudocode

```c
CXmlValidator *__fastcall CXmlValidator::`scalar deleting destructor'(CXmlValidator *this)
{
  CXmlValidator::~CXmlValidator(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000d21c  push    rbx
0x18000d21e  sub     rsp, 20h
0x18000d222  mov     rbx, rcx
0x18000d225  call    ??1CXmlValidator@@QEAA@XZ; CXmlValidator::~CXmlValidator(void)
0x18000d22a  mov     rcx, rbx; Block
0x18000d22d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d232  mov     rax, rbx
0x18000d235  add     rsp, 20h
0x18000d239  pop     rbx
0x18000d23a  retn
```
