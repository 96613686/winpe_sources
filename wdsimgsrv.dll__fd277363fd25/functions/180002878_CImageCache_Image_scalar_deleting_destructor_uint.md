# CImageCache::Image::`scalar deleting destructor'(uint)

- ea: `0x180002878`
- end: `0x18000289f`
- name: `??_GImage@CImageCache@@QEAAPEAXI@Z`
- size: `39`
- prototype: `void *__fastcall(CImageCache::Image *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800028a8`
- `0x1800081d0`
- `0x180008494`
- `0x18000891c`

## callees

- `0x1800027fc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002889`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002889`

## pseudocode

```c
CImageCache::Image *__fastcall CImageCache::Image::`scalar deleting destructor'(CImageCache::Image *this)
{
  CImageCache::Image::~Image(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002878  push    rbx
0x18000287a  sub     rsp, 20h
0x18000287e  mov     rbx, rcx
0x180002881  call    ??1Image@CImageCache@@QEAA@XZ; CImageCache::Image::~Image(void)
0x180002886  mov     rcx, rbx
0x180002889  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002890  nop     dword ptr [rax+rax+00h]
0x180002895  mov     rax, rbx
0x180002898  add     rsp, 20h
0x18000289c  pop     rbx
0x18000289d  retn
```
