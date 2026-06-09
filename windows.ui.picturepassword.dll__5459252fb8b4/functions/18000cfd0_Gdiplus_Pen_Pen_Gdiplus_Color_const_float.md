# Gdiplus::Pen::Pen(Gdiplus::Color const &,float)

- ea: `0x18000cfd0`
- end: `0x18000cffd`
- name: `??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z`
- size: `45`
- prototype: `Gdiplus::Pen *__fastcall(Gdiplus::Pen *this, const struct Gdiplus::Color *, float)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e46c`
- `0x18000e558`
- `0x1800123dc`
- `0x180012a94`

## import_xrefs

- `gdiplus!GdipCreatePen1` at `0x18000cfeb`
- `gdiplus!GdipCreatePen1` at `0x18000cfeb`

## pseudocode

```c
Gdiplus::Pen *__fastcall Gdiplus::Pen::Pen(Gdiplus::Pen *this, const struct Gdiplus::Color *a2, float a3)
{
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = GdipCreatePen1(*(unsigned int *)a2, a2, 0, this);
  return this;
}

```

## disassembly

```asm
0x18000cfd0  push    rbx
0x18000cfd2  sub     rsp, 20h
0x18000cfd6  mov     rbx, rcx
0x18000cfd9  mov     qword ptr [rcx], 0
0x18000cfe0  mov     r9, rcx
0x18000cfe3  xor     r8d, r8d
0x18000cfe6  mov     ecx, [rdx]
0x18000cfe8  movaps  xmm1, xmm2
0x18000cfeb  call    cs:__imp_GdipCreatePen1
0x18000cff1  mov     [rbx+8], eax
0x18000cff4  mov     rax, rbx
0x18000cff7  add     rsp, 20h
0x18000cffb  pop     rbx
0x18000cffc  retn
```
