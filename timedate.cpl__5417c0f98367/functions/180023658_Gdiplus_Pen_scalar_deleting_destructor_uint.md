# Gdiplus::Pen::`scalar deleting destructor'(uint)

- ea: `0x180023658`
- end: `0x18002367c`
- name: `??_GPen@Gdiplus@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(Gdiplus::Pen *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180024010`

## import_xrefs

- `gdiplus!GdipDeletePen` at `0x180023664`
- `gdiplus!GdipDeletePen` at `0x180023664`
- `gdiplus!GdipFree` at `0x18002366d`
- `gdiplus!GdipFree` at `0x18002366d`

## pseudocode

```c
Gdiplus::Pen *__fastcall Gdiplus::Pen::`scalar deleting destructor'(Gdiplus::Pen *this)
{
  GdipDeletePen(*(_QWORD *)this);
  GdipFree(this);
  return this;
}

```

## disassembly

```asm
0x180023658  push    rbx
0x18002365a  sub     rsp, 20h
0x18002365e  mov     rbx, rcx
0x180023661  mov     rcx, [rcx]
0x180023664  call    cs:__imp_GdipDeletePen
0x18002366a  mov     rcx, rbx
0x18002366d  call    cs:__imp_GdipFree
0x180023673  mov     rax, rbx
0x180023676  add     rsp, 20h
0x18002367a  pop     rbx
0x18002367b  retn
```
