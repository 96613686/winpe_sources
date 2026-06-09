# DrawArrow(Gdiplus::Graphics *,TRI_POINTS &)

- ea: `0x18000e46c`
- end: `0x18000e552`
- name: `?DrawArrow@@YAXPEAVGraphics@Gdiplus@@AEAUTRI_POINTS@@@Z`
- size: `230`
- prototype: `void __fastcall(struct Gdiplus::Graphics *, struct TRI_POINTS *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e558`
- `0x1800123dc`

## callees

- `0x180002610`
- `0x18000cfd0`
- `0x18000d004`
- `0x18000e46c`

## import_xrefs

- `gdiplus!GdipDeleteBrush` at `0x18000e52b`
- `gdiplus!GdipDeleteBrush` at `0x18000e52b`
- `gdiplus!GdipDrawPolygonI` at `0x18000e510`
- `gdiplus!GdipDrawPolygonI` at `0x18000e510`
- `gdiplus!GdipFillPolygonI` at `0x18000e4f2`
- `gdiplus!GdipFillPolygonI` at `0x18000e4f2`
- `gdiplus!GdipDeletePen` at `0x18000e521`
- `gdiplus!GdipDeletePen` at `0x18000e521`

## pseudocode

```c
void __fastcall DrawArrow(struct Gdiplus::Graphics *a1, struct TRI_POINTS *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  int v6; // eax
  __int64 v7; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v8[8]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+48h] [rbp-38h]
  _DWORD v10[6]; // [rsp+58h] [rbp-28h] BYREF

  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v8, a2);
  Gdiplus::Pen::Pen((Gdiplus::Pen *)&v7, (const struct Gdiplus::Color *)&g_clrEdge, 1.0);
  v4 = *(_QWORD *)a1;
  v10[0] = *(_DWORD *)a2;
  v10[1] = *((_DWORD *)a2 + 1);
  v10[2] = *((_DWORD *)a2 + 2);
  v10[3] = *((_DWORD *)a2 + 3);
  v10[4] = *((_DWORD *)a2 + 4);
  v10[5] = *((_DWORD *)a2 + 5);
  v5 = GdipFillPolygonI(v4, v9, v10, 3, 0);
  if ( v5 )
    *((_DWORD *)a1 + 2) = v5;
  v6 = GdipDrawPolygonI(*(_QWORD *)a1, v7, v10, 3);
  if ( v6 )
    *((_DWORD *)a1 + 2) = v6;
  GdipDeletePen(v7);
  GdipDeleteBrush(v9);
}

```

## disassembly

```asm
0x18000e46c  mov     [rsp-8+arg_8], rbx
0x18000e471  mov     [rsp-8+arg_10], rdi
0x18000e476  push    rbp
0x18000e477  mov     rbp, rsp
0x18000e47a  sub     rsp, 80h
0x18000e481  mov     rax, cs:__security_cookie
0x18000e488  xor     rax, rsp
0x18000e48b  mov     [rbp+var_10], rax
0x18000e48f  mov     rdi, rcx
0x18000e492  mov     rbx, rdx
0x18000e495  lea     rcx, [rbp+var_40]; this
0x18000e499  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x18000e49e  movss   xmm2, cs:__real@3f800000; float
0x18000e4a6  lea     rdx, ?g_clrEdge@@3VColor@Gdiplus@@A; struct Gdiplus::Color *
0x18000e4ad  lea     rcx, [rbp+var_50]; this
0x18000e4b1  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x18000e4b6  mov     eax, [rbx]
0x18000e4b8  lea     r8, [rbp+var_28]
0x18000e4bc  mov     rdx, [rbp+var_38]
0x18000e4c0  mov     r9d, 3
0x18000e4c6  mov     rcx, [rdi]
0x18000e4c9  mov     [rbp+var_28], eax
0x18000e4cc  mov     eax, [rbx+4]
0x18000e4cf  mov     [rbp+var_24], eax
0x18000e4d2  mov     eax, [rbx+8]
0x18000e4d5  mov     [rbp+var_20], eax
0x18000e4d8  mov     eax, [rbx+0Ch]
0x18000e4db  mov     [rbp+var_1C], eax
0x18000e4de  mov     eax, [rbx+10h]
0x18000e4e1  mov     [rbp+var_18], eax
0x18000e4e4  mov     eax, [rbx+14h]
0x18000e4e7  mov     [rbp+var_14], eax
0x18000e4ea  mov     [rsp+80h+var_60], 0
0x18000e4f2  call    cs:__imp_GdipFillPolygonI
0x18000e4f8  test    eax, eax
0x18000e4fa  jz      short loc_18000E4FF
0x18000e4fc  mov     [rdi+8], eax
0x18000e4ff  mov     rdx, [rbp+var_50]
0x18000e503  lea     r8, [rbp+var_28]
0x18000e507  mov     rcx, [rdi]
0x18000e50a  mov     r9d, 3
0x18000e510  call    cs:__imp_GdipDrawPolygonI
0x18000e516  test    eax, eax
0x18000e518  jz      short loc_18000E51D
0x18000e51a  mov     [rdi+8], eax
0x18000e51d  mov     rcx, [rbp+var_50]
0x18000e521  call    cs:__imp_GdipDeletePen
0x18000e527  mov     rcx, [rbp+var_38]
0x18000e52b  call    cs:__imp_GdipDeleteBrush
0x18000e531  mov     rcx, [rbp+var_10]
0x18000e535  xor     rcx, rsp; StackCookie
0x18000e538  call    __security_check_cookie
0x18000e53d  lea     r11, [rsp+80h+var_s0]
0x18000e545  mov     rbx, [r11+18h]
0x18000e549  mov     rdi, [r11+20h]
0x18000e54d  mov     rsp, r11
0x18000e550  pop     rbp
0x18000e551  retn
```
