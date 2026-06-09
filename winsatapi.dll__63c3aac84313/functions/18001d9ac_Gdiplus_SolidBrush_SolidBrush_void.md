# Gdiplus::SolidBrush::~SolidBrush(void)

- ea: `0x18001d9ac`
- end: `0x18001d9c1`
- name: `??1SolidBrush@Gdiplus@@UEAA@XZ`
- size: `21`
- prototype: `void __fastcall(Gdiplus::SolidBrush *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002f29e`
- `0x18002f2b0`
- `0x18002f2c2`

## import_xrefs

- `gdiplus!GdipDeleteBrush` at `0x18001d9ba`

## pseudocode

```c
void __fastcall Gdiplus::SolidBrush::~SolidBrush(Gdiplus::SolidBrush *this)
{
  *(_QWORD *)this = &Gdiplus::SolidBrush::`vftable';
  GdipDeleteBrush(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x18001d9ac  lea     rax, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18001d9b3  mov     [rcx], rax
0x18001d9b6  mov     rcx, [rcx+8]
0x18001d9ba  jmp     cs:__imp_GdipDeleteBrush
```
