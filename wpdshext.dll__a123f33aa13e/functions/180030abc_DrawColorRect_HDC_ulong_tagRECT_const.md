# _DrawColorRect(HDC__ *,ulong,tagRECT const *)

- ea: `0x180030abc`
- end: `0x180030b94`
- name: `?_DrawColorRect@@YAXPEAUHDC__@@KPEBUtagRECT@@@Z`
- size: `216`
- prototype: `void __fastcall(HDC, unsigned int, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180069430`

## callees

- `0x18002ea3c`
- `0x180030abc`
- `0x180030b9c`
- `0x180068644`

## import_xrefs

- `gdiplus!GdipFillRectangleI` at `0x180030b5a`
- `gdiplus!GdipFillRectangleI` at `0x180030b5a`
- `gdiplus!GdipDeleteBrush` at `0x180030b7e`
- `gdiplus!GdipDeleteBrush` at `0x180030b7e`
- `gdiplus!GdipDeleteGraphics` at `0x180030b6a`
- `gdiplus!GdipDeleteGraphics` at `0x180030b6a`
- `gdiplus!GdipAlloc` at `0x180030ae5`
- `gdiplus!GdipAlloc` at `0x180030ae5`
- `gdiplus!GdipFree` at `0x180030b73`
- `gdiplus!GdipFree` at `0x180030b73`

## pseudocode

```c
void __fastcall _DrawColorRect(HDC a1, int a2, const struct tagRECT *a3)
{
  Gdiplus::Graphics *v6; // rax
  _QWORD *v7; // rbx
  int v8; // eax
  _BYTE v9[8]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h]
  unsigned int v11; // [rsp+78h] [rbp+20h] BYREF

  if ( (int)StartGdiPlus() >= 0 )
  {
    v6 = (Gdiplus::Graphics *)GdipAlloc(16);
    v7 = v6 ? (_QWORD *)Gdiplus::Graphics::Graphics(v6, a1) : 0LL;
    if ( v7 )
    {
      v11 = BYTE2(a2) | a2 & 0xFF00 | ((a2 | 0xFFFFFF00) << 16);
      Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v9, (const struct Gdiplus::Color *)&v11);
      v8 = GdipFillRectangleI(*v7, v10, (unsigned int)a3->left);
      if ( v8 )
        *((_DWORD *)v7 + 2) = v8;
      GdipDeleteGraphics(*v7);
      GdipFree(v7);
      GdipDeleteBrush(v10);
    }
  }
}

```

## disassembly

```asm
0x180030abc  mov     [rsp+arg_0], rbx
0x180030ac1  mov     [rsp+arg_8], rsi
0x180030ac6  push    rdi
0x180030ac7  sub     rsp, 50h
0x180030acb  mov     rsi, r8
0x180030ace  mov     edi, edx
0x180030ad0  mov     rbx, rcx
0x180030ad3  call    ?StartGdiPlus@@YAJXZ; StartGdiPlus(void)
0x180030ad8  test    eax, eax
0x180030ada  js      loc_180030B84
0x180030ae0  mov     ecx, 10h
0x180030ae5  call    cs:__imp_GdipAlloc
0x180030aeb  test    rax, rax
0x180030aee  jz      short loc_180030B00
0x180030af0  mov     rdx, rbx; HDC
0x180030af3  mov     rcx, rax; this
0x180030af6  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x180030afb  mov     rbx, rax
0x180030afe  jmp     short loc_180030B02
0x180030b00  xor     ebx, ebx
0x180030b02  test    rbx, rbx
0x180030b05  jz      short loc_180030B84
0x180030b07  movzx   ecx, dil
0x180030b0b  mov     edx, 0FFFFFF00h
0x180030b10  or      ecx, edx
0x180030b12  movzx   eax, di
0x180030b15  shl     ecx, 10h
0x180030b18  and     eax, edx
0x180030b1a  or      ecx, eax
0x180030b1c  shr     edi, 10h
0x180030b1f  movzx   eax, dil
0x180030b23  lea     rdx, [rsp+58h+arg_18]; struct Gdiplus::Color *
0x180030b28  or      ecx, eax
0x180030b2a  mov     [rsp+58h+arg_18], ecx
0x180030b2e  lea     rcx, [rsp+58h+var_28]; this
0x180030b33  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x180030b38  mov     ecx, [rsi+0Ch]
0x180030b3b  mov     r9d, [rsi+4]
0x180030b3f  sub     ecx, r9d
0x180030b42  mov     eax, [rsi+8]
0x180030b45  sub     eax, [rsi]
0x180030b47  mov     r8d, [rsi]
0x180030b4a  mov     rdx, [rsp+58h+var_20]
0x180030b4f  mov     [rsp+58h+var_30], ecx
0x180030b53  mov     rcx, [rbx]
0x180030b56  mov     [rsp+58h+var_38], eax
0x180030b5a  call    cs:__imp_GdipFillRectangleI
0x180030b60  test    eax, eax
0x180030b62  jz      short loc_180030B67
0x180030b64  mov     [rbx+8], eax
0x180030b67  mov     rcx, [rbx]
0x180030b6a  call    cs:__imp_GdipDeleteGraphics
0x180030b70  mov     rcx, rbx
0x180030b73  call    cs:__imp_GdipFree
0x180030b79  mov     rcx, [rsp+58h+var_20]
0x180030b7e  call    cs:__imp_GdipDeleteBrush
0x180030b84  mov     rbx, [rsp+58h+arg_0]
0x180030b89  mov     rsi, [rsp+58h+arg_8]
0x180030b8e  add     rsp, 50h
0x180030b92  pop     rdi
0x180030b93  retn
```
