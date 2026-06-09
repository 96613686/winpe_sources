# CRegistryLockedTransaction::`scalar deleting destructor'(uint)

- ea: `0x180007a5c`
- end: `0x180007a7c`
- name: `??_GCRegistryLockedTransaction@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(CRegistryLockedTransaction *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x180007a00`

## callees

- `0x18000d1ec`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007a6d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007a6d`

## pseudocode

```c
WCHAR *__fastcall CRegistryLockedTransaction::`scalar deleting destructor'(WCHAR *this)
{
  CRegistryLockedTransaction::~CRegistryLockedTransaction(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007a5c  push    rbx
0x180007a5e  sub     rsp, 20h
0x180007a62  mov     rbx, rcx
0x180007a65  call    ??1CRegistryLockedTransaction@@QEAA@XZ; CRegistryLockedTransaction::~CRegistryLockedTransaction(void)
0x180007a6a  mov     rcx, rbx
0x180007a6d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007a73  mov     rax, rbx
0x180007a76  add     rsp, 20h
0x180007a7a  pop     rbx
0x180007a7b  retn
```
