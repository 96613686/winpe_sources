# ScopedCS::`scalar deleting destructor'(uint)

- ea: `0x180033df4`
- end: `0x180033e21`
- name: `??_GScopedCS@@QEAAPEAXI@Z`
- size: `45`
- prototype: `void *__fastcall(ScopedCS *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001d0c8`
- `0x180033c5c`

## callees

- `0x180021ccc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033dfd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033dfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _RTL_CRITICAL_SECTION *__fastcall ScopedCS::`scalar deleting destructor'(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
  operator delete(this, 0x28u);
  return this;
}

```

## disassembly

```asm
0x180033df4  push    rbx
0x180033df6  sub     rsp, 20h
0x180033dfa  mov     rbx, rcx
0x180033dfd  call    cs:__imp_DeleteCriticalSection
0x180033e04  nop     dword ptr [rax+rax+00h]
0x180033e09  nop
0x180033e0a  mov     edx, 28h ; '('; unsigned __int64
0x180033e0f  mov     rcx, rbx; void *
0x180033e12  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180033e17  mov     rax, rbx
0x180033e1a  add     rsp, 20h
0x180033e1e  pop     rbx
0x180033e1f  retn
```
