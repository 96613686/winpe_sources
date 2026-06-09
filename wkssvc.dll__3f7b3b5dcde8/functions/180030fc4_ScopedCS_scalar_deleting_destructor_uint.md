# ScopedCS::`scalar deleting destructor'(uint)

- ea: `0x180030fc4`
- end: `0x180030fea`
- name: `??_GScopedCS@@QEAAPEAXI@Z`
- size: `38`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001bb48`
- `0x180030e40`

## callees

- `0x18002051c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030fcd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030fcd`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ScopedCS::`scalar deleting destructor'(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180030fc4  push    rbx
0x180030fc6  sub     rsp, 20h
0x180030fca  mov     rbx, rcx
0x180030fcd  call    cs:__imp_DeleteCriticalSection
0x180030fd3  nop
0x180030fd4  mov     edx, 28h ; '('; unsigned __int64
0x180030fd9  mov     rcx, rbx; void *
0x180030fdc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180030fe1  mov     rax, rbx
0x180030fe4  add     rsp, 20h
0x180030fe8  pop     rbx
0x180030fe9  retn
```
