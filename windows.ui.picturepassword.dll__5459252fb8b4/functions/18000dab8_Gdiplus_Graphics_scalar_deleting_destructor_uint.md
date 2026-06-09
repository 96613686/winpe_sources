# Gdiplus::Graphics::`scalar deleting destructor'(uint)

- ea: `0x18000dab8`
- end: `0x18000dadc`
- name: `??_GGraphics@Gdiplus@@QEAAPEAXI@Z`
- size: `36`
- prototype: `Gdiplus::Graphics *__fastcall(Gdiplus::Graphics *this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180012338`
- `0x1800123dc`
- `0x180012a94`

## import_xrefs

- `gdiplus!GdipFree` at `0x18000dacd`
- `gdiplus!GdipFree` at `0x18000dacd`
- `gdiplus!GdipDeleteGraphics` at `0x18000dac4`
- `gdiplus!GdipDeleteGraphics` at `0x18000dac4`

## pseudocode

```c
Gdiplus::Graphics *__fastcall Gdiplus::Graphics::`scalar deleting destructor'(Gdiplus::Graphics *this)
{
  GdipDeleteGraphics(*(_QWORD *)this);
  GdipFree(this);
  return this;
}

```

## disassembly

```asm
0x18000dab8  push    rbx
0x18000daba  sub     rsp, 20h
0x18000dabe  mov     rbx, rcx
0x18000dac1  mov     rcx, [rcx]
0x18000dac4  call    cs:__imp_GdipDeleteGraphics
0x18000daca  mov     rcx, rbx
0x18000dacd  call    cs:__imp_GdipFree
0x18000dad3  mov     rax, rbx
0x18000dad6  add     rsp, 20h
0x18000dada  pop     rbx
0x18000dadb  retn
```
