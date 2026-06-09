# Gdiplus::Effect::~Effect(void)

- ea: `0x18000d3d0`
- end: `0x18000d3fd`
- name: `??1Effect@Gdiplus@@UEAA@XZ`
- size: `45`
- prototype: `void __fastcall(Gdiplus::Effect *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000da80`
- `0x180012bd0`

## import_xrefs

- `gdiplus!GdipFree` at `0x18000d3e7`
- `gdiplus!GdipFree` at `0x18000d3e7`
- `gdiplus!GdipDeleteEffect` at `0x18000d3f6`

## pseudocode

```c
void __fastcall Gdiplus::Effect::~Effect(Gdiplus::Effect *this)
{
  *(_QWORD *)this = &Gdiplus::ColorMatrixEffect::`vftable';
  GdipFree(*((_QWORD *)this + 3));
  GdipDeleteEffect(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x18000d3d0  push    rbx
0x18000d3d2  sub     rsp, 20h
0x18000d3d6  lea     rax, ??_7ColorMatrixEffect@Gdiplus@@6B@; const Gdiplus::ColorMatrixEffect::`vftable'
0x18000d3dd  mov     rbx, rcx
0x18000d3e0  mov     [rcx], rax
0x18000d3e3  mov     rcx, [rcx+18h]
0x18000d3e7  call    cs:__imp_GdipFree
0x18000d3ed  mov     rcx, [rbx+8]
0x18000d3f1  add     rsp, 20h
0x18000d3f5  pop     rbx
0x18000d3f6  jmp     cs:__imp_GdipDeleteEffect
```
