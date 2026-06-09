# Gdiplus::Pen::Pen(Gdiplus::Color const &,float)

- ea: `0x1800235d4`
- end: `0x180023601`
- name: `??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z`
- size: `45`
- prototype: `__int64 __fastcall(Gdiplus::Pen *__hidden this, const struct Gdiplus::Color *, float)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180023f3c`

## import_xrefs

- `gdiplus!GdipCreatePen1` at `0x1800235ef`
- `gdiplus!GdipCreatePen1` at `0x1800235ef`

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
0x1800235d4  push    rbx
0x1800235d6  sub     rsp, 20h
0x1800235da  mov     rbx, rcx
0x1800235dd  mov     qword ptr [rcx], 0
0x1800235e4  mov     r9, rcx
0x1800235e7  xor     r8d, r8d
0x1800235ea  mov     ecx, [rdx]
0x1800235ec  movaps  xmm1, xmm2
0x1800235ef  call    cs:__imp_GdipCreatePen1
0x1800235f5  mov     [rbx+8], eax
0x1800235f8  mov     rax, rbx
0x1800235fb  add     rsp, 20h
0x1800235ff  pop     rbx
0x180023600  retn
```
