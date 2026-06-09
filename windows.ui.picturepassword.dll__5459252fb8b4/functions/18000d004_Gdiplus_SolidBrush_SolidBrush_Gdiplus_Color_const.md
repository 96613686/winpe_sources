# Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)

- ea: `0x18000d004`
- end: `0x18000d051`
- name: `??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z`
- size: `77`
- prototype: `Gdiplus::SolidBrush *__fastcall(Gdiplus::SolidBrush *this, const struct Gdiplus::Color *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e46c`
- `0x180012a94`

## import_xrefs

- `gdiplus!GdipCreateSolidFill` at `0x18000d036`
- `gdiplus!GdipCreateSolidFill` at `0x18000d036`

## pseudocode

```c
Gdiplus::SolidBrush *__fastcall Gdiplus::SolidBrush::SolidBrush(
        Gdiplus::SolidBrush *this,
        const struct Gdiplus::Color *a2)
{
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  *((_DWORD *)this + 4) = 6;
  *(_QWORD *)this = &Gdiplus::SolidBrush::`vftable';
  v4 = 0;
  *((_DWORD *)this + 4) = GdipCreateSolidFill(g_clrStroke, &v4);
  *((_QWORD *)this + 1) = v4;
  return this;
}

```

## disassembly

```asm
0x18000d004  mov     [rsp+arg_8], rdx
0x18000d009  push    rbx
0x18000d00a  sub     rsp, 20h
0x18000d00e  lea     rax, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18000d015  mov     dword ptr [rcx+10h], 6
0x18000d01c  mov     [rcx], rax
0x18000d01f  lea     rdx, [rsp+28h+arg_8]
0x18000d024  mov     rbx, rcx
0x18000d027  mov     [rsp+28h+arg_8], 0
0x18000d030  mov     ecx, cs:?g_clrStroke@@3VColor@Gdiplus@@A; Gdiplus::Color g_clrStroke
0x18000d036  call    cs:__imp_GdipCreateSolidFill
0x18000d03c  mov     [rbx+10h], eax
0x18000d03f  mov     rax, [rsp+28h+arg_8]
0x18000d044  mov     [rbx+8], rax
0x18000d048  mov     rax, rbx
0x18000d04b  add     rsp, 20h
0x18000d04f  pop     rbx
0x18000d050  retn
```
