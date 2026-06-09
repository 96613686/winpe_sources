# Gdiplus::Font::~Font(void)

- ea: `0x18001d938`
- end: `0x18001d942`
- name: `??1Font@Gdiplus@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(Gdiplus::Font *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002f28c`

## import_xrefs

- `gdiplus!GdipDeleteFont` at `0x18001d93b`

## pseudocode

```c
void __fastcall Gdiplus::Font::~Font(Gdiplus::Font *this)
{
  GdipDeleteFont(*(_QWORD *)this);
}

```

## disassembly

```asm
0x18001d938  mov     rcx, [rcx]
0x18001d93b  jmp     cs:__imp_GdipDeleteFont
```
