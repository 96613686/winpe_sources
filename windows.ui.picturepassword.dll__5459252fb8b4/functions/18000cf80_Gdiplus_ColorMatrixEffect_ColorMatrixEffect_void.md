# Gdiplus::ColorMatrixEffect::ColorMatrixEffect(void)

- ea: `0x18000cf80`
- end: `0x18000cfc7`
- name: `??0ColorMatrixEffect@Gdiplus@@QEAA@XZ`
- size: `71`
- prototype: `Gdiplus::ColorMatrixEffect *__fastcall(Gdiplus::ColorMatrixEffect *this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180012bd0`

## import_xrefs

- `gdiplus!GdipCreateEffect` at `0x18000cfb8`
- `gdiplus!GdipCreateEffect` at `0x18000cfb8`

## pseudocode

```c
Gdiplus::ColorMatrixEffect *__fastcall Gdiplus::ColorMatrixEffect::ColorMatrixEffect(Gdiplus::ColorMatrixEffect *this)
{
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF

  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &Gdiplus::ColorMatrixEffect::`vftable';
  v3 = xmmword_180023358;
  GdipCreateEffect(&v3);
  return this;
}

```

## disassembly

```asm
0x18000cf80  push    rbx
0x18000cf82  sub     rsp, 30h
0x18000cf86  movups  xmm0, cs:xmmword_180023358
0x18000cf8d  xor     eax, eax
0x18000cf8f  lea     rdx, [rcx+8]
0x18000cf93  mov     [rcx+10h], eax
0x18000cf96  mov     rbx, rcx
0x18000cf99  mov     [rcx+18h], rax
0x18000cf9d  mov     [rcx+20h], eax
0x18000cfa0  mov     [rdx], rax
0x18000cfa3  lea     rax, ??_7ColorMatrixEffect@Gdiplus@@6B@; const Gdiplus::ColorMatrixEffect::`vftable'
0x18000cfaa  mov     [rcx], rax
0x18000cfad  lea     rcx, [rsp+38h+var_18]
0x18000cfb2  movdqu  [rsp+38h+var_18], xmm0
0x18000cfb8  call    cs:__imp_GdipCreateEffect
0x18000cfbe  mov     rax, rbx
0x18000cfc1  add     rsp, 30h
0x18000cfc5  pop     rbx
0x18000cfc6  retn
```
