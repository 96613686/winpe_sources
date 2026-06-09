# Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)

- ea: `0x18001d804`
- end: `0x18001d84c`
- name: `??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z`
- size: `72`
- prototype: `Gdiplus::SolidBrush *__fastcall(Gdiplus::SolidBrush *this, const struct Gdiplus::Color *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800119a4`

## import_xrefs

- `gdiplus!GdipCreateSolidFill` at `0x18001d831`
- `gdiplus!GdipCreateSolidFill` at `0x18001d831`

## pseudocode

```c
Gdiplus::SolidBrush *__fastcall Gdiplus::SolidBrush::SolidBrush(
        Gdiplus::SolidBrush *this,
        const struct Gdiplus::Color *a2)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  *((_DWORD *)this + 4) = 6;
  v4 = 0;
  *(_QWORD *)this = &Gdiplus::SolidBrush::`vftable';
  *((_DWORD *)this + 4) = GdipCreateSolidFill(*(unsigned int *)a2, &v4);
  *((_QWORD *)this + 1) = v4;
  return this;
}

```

## disassembly

```asm
0x18001d804  push    rbx
0x18001d806  sub     rsp, 20h
0x18001d80a  mov     rbx, rcx
0x18001d80d  mov     dword ptr [rcx+10h], 6
0x18001d814  mov     rax, rdx
0x18001d817  mov     [rsp+28h+arg_0], 0
0x18001d820  lea     rcx, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18001d827  lea     rdx, [rsp+28h+arg_0]
0x18001d82c  mov     [rbx], rcx
0x18001d82f  mov     ecx, [rax]
0x18001d831  call    cs:__imp_GdipCreateSolidFill
0x18001d837  mov     [rbx+10h], eax
0x18001d83a  mov     rax, [rsp+28h+arg_0]
0x18001d83f  mov     [rbx+8], rax
0x18001d843  mov     rax, rbx
0x18001d846  add     rsp, 20h
0x18001d84a  pop     rbx
0x18001d84b  retn
```
