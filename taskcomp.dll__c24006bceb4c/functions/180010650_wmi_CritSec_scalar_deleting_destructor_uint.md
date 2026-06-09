# wmi::CritSec::`scalar deleting destructor'(uint)

- ea: `0x180010650`
- end: `0x180010670`
- name: `??_GCritSec@wmi@@QEAAPEAXI@Z`
- size: `32`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180013738`
- `0x18001ae60`

## callees

- `0x1800074c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010659`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010659`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall wmi::CritSec::`scalar deleting destructor'(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180010650  push    rbx
0x180010652  sub     rsp, 20h
0x180010656  mov     rbx, rcx
0x180010659  call    cs:__imp_DeleteCriticalSection
0x18001065f  mov     rcx, rbx; Block
0x180010662  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010667  mov     rax, rbx
0x18001066a  add     rsp, 20h
0x18001066e  pop     rbx
0x18001066f  retn
```
