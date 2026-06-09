# ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)

- ea: `0x180013544`
- end: `0x180013564`
- name: `??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800153c8`
- `0x180015bc0`

## callees

- `0x1800135cc`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001354d`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001354d`

## pseudocode

```c
ALLOC_CACHE_HANDLER *__fastcall ALLOC_CACHE_HANDLER::`scalar deleting destructor'(ALLOC_CACHE_HANDLER *this)
{
  ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180013544  push    rbx
0x180013546  sub     rsp, 20h
0x18001354a  mov     rbx, rcx
0x18001354d  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180013553  mov     rcx, rbx; Block
0x180013556  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001355b  mov     rax, rbx
0x18001355e  add     rsp, 20h
0x180013562  pop     rbx
0x180013563  retn
```
