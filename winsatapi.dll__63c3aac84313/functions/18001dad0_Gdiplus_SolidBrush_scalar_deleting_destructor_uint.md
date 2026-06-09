# Gdiplus::SolidBrush::`scalar deleting destructor'(uint)

- ea: `0x18001dad0`
- end: `0x18001db0f`
- name: `??_GSolidBrush@Gdiplus@@UEAAPEAXI@Z`
- size: `63`
- prototype: `Gdiplus::SolidBrush *__fastcall(Gdiplus::SolidBrush *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001dad0`

## import_xrefs

- `gdiplus!GdipFree` at `0x18001dafb`
- `gdiplus!GdipFree` at `0x18001dafb`
- `gdiplus!GdipDeleteBrush` at `0x18001daed`
- `gdiplus!GdipDeleteBrush` at `0x18001daed`

## pseudocode

```c
Gdiplus::SolidBrush *__fastcall Gdiplus::SolidBrush::`scalar deleting destructor'(Gdiplus::SolidBrush *this, char a2)
{
  *(_QWORD *)this = &Gdiplus::SolidBrush::`vftable';
  GdipDeleteBrush(*((_QWORD *)this + 1));
  if ( (a2 & 1) != 0 )
    GdipFree(this);
  return this;
}

```

## disassembly

```asm
0x18001dad0  mov     [rsp+arg_0], rbx
0x18001dad5  push    rdi
0x18001dad6  sub     rsp, 20h
0x18001dada  lea     rax, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18001dae1  mov     rdi, rcx
0x18001dae4  mov     [rcx], rax
0x18001dae7  mov     ebx, edx
0x18001dae9  mov     rcx, [rcx+8]
0x18001daed  call    cs:__imp_GdipDeleteBrush
0x18001daf3  test    bl, 1
0x18001daf6  jz      short loc_18001DB01
0x18001daf8  mov     rcx, rdi
0x18001dafb  call    cs:__imp_GdipFree
0x18001db01  mov     rbx, [rsp+28h+arg_0]
0x18001db06  mov     rax, rdi
0x18001db09  add     rsp, 20h
0x18001db0d  pop     rdi
0x18001db0e  retn
```
