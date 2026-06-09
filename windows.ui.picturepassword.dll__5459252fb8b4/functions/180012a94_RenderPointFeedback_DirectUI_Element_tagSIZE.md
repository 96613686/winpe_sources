# _RenderPointFeedback(DirectUI::Element *,tagSIZE *)

- ea: `0x180012a94`
- end: `0x180012b9a`
- name: `?_RenderPointFeedback@@YAJPEAVElement@DirectUI@@PEAUtagSIZE@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180010d70`

## callees

- `0x1800092b8`
- `0x18000cc68`
- `0x18000cfd0`
- `0x18000d004`
- `0x18000dab8`
- `0x18000e814`
- `0x18000e8a0`
- `0x180011220`
- `0x180012a94`
- `0x180012bd0`

## import_xrefs

- `gdiplus!GdipFillEllipseI` at `0x180012b0e`
- `gdiplus!GdipFillEllipseI` at `0x180012b0e`
- `gdiplus!GdipDeleteBrush` at `0x180012b7e`
- `gdiplus!GdipDeleteBrush` at `0x180012b7e`
- `gdiplus!GdipDeletePen` at `0x180012b73`
- `gdiplus!GdipDeletePen` at `0x180012b73`
- `gdiplus!GdipDisposeImage` at `0x180012b89`
- `gdiplus!GdipDisposeImage` at `0x180012b89`

## pseudocode

```c
__int64 __fastcall _RenderPointFeedback(struct DirectUI::Element *a1, struct tagSIZE *a2)
{
  Gdiplus::Graphics *v4; // rbx
  int Error; // edi
  const struct Gdiplus::Color *v6; // rdx
  int v7; // eax
  _QWORD v9[2]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v10[8]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+48h] [rbp-50h]
  _BYTE v12[8]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v13; // [rsp+60h] [rbp-38h]

  *a2 = 0;
  Gdiplus::Bitmap::Bitmap((Gdiplus::Bitmap *)v10, 0x21u, 0x21u);
  v4 = Gdiplus::Graphics::FromImage((struct Image *)v10);
  if ( v4 )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  if ( Error >= 0 )
  {
    Gdiplus::Graphics::SetSmoothingMode(v4);
    Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v12, v6);
    v7 = GdipFillEllipseI(*(_QWORD *)v4, v13, 0, 0, 32, 32);
    if ( v7 )
      *((_DWORD *)v4 + 2) = v7;
    Gdiplus::Pen::Pen((Gdiplus::Pen *)v9, (const struct Gdiplus::Color *)&g_clrEdge, 1.0);
    Gdiplus::Graphics::DrawEllipse(v4, v9, 0, 0, 32, 32);
    Error = _SetFeedBackDUIElement(a1, (struct Gdiplus::Bitmap *)v10, a2);
    if ( v4 )
      Gdiplus::Graphics::`scalar deleting destructor'(v4);
    GdipDeletePen(v9[0]);
    GdipDeleteBrush(v13);
  }
  GdipDisposeImage(v11);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180012a94  push    rbx
0x180012a96  push    rbp
0x180012a97  push    rsi
0x180012a98  push    rdi
0x180012a99  sub     rsp, 78h
0x180012a9d  mov     rsi, rdx
0x180012aa0  mov     qword ptr [rdx], 0
0x180012aa7  mov     edx, 21h ; '!'; int
0x180012aac  mov     rbp, rcx
0x180012aaf  mov     r8d, edx; int
0x180012ab2  lea     rcx, [rsp+98h+var_58]; this
0x180012ab7  call    ??0Bitmap@Gdiplus@@QEAA@HHH@Z; Gdiplus::Bitmap::Bitmap(int,int,int)
0x180012abc  lea     rcx, [rsp+98h+var_58]; struct Image *
0x180012ac1  call    ?FromImage@Graphics@Gdiplus@@SAPEAV12@PEAVImage@2@@Z; Gdiplus::Graphics::FromImage(Gdiplus::Image *)
0x180012ac6  mov     rbx, rax
0x180012ac9  test    rax, rax
0x180012acc  jnz     short loc_180012AD7
0x180012ace  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180012ad3  mov     edi, eax
0x180012ad5  jmp     short loc_180012AD9
0x180012ad7  xor     edi, edi
0x180012ad9  test    edi, edi
0x180012adb  js      loc_180012B84
0x180012ae1  mov     rcx, rbx
0x180012ae4  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x180012ae9  lea     rcx, [rsp+98h+var_40]; this
0x180012aee  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x180012af3  mov     rdx, [rsp+98h+var_38]
0x180012af8  mov     edi, 20h ; ' '
0x180012afd  mov     rcx, [rbx]
0x180012b00  xor     r9d, r9d
0x180012b03  mov     [rsp+98h+var_70], edi
0x180012b07  xor     r8d, r8d
0x180012b0a  mov     [rsp+98h+var_78], edi
0x180012b0e  call    cs:__imp_GdipFillEllipseI
0x180012b14  test    eax, eax
0x180012b16  jz      short loc_180012B1B
0x180012b18  mov     [rbx+8], eax
0x180012b1b  movss   xmm2, cs:__real@3f800000; float
0x180012b23  lea     rdx, ?g_clrEdge@@3VColor@Gdiplus@@A; struct Gdiplus::Color *
0x180012b2a  lea     rcx, [rsp+98h+var_68]; this
0x180012b2f  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x180012b34  xor     r9d, r9d
0x180012b37  mov     [rsp+98h+var_70], edi
0x180012b3b  xor     r8d, r8d
0x180012b3e  mov     [rsp+98h+var_78], edi
0x180012b42  lea     rdx, [rsp+98h+var_68]
0x180012b47  mov     rcx, rbx
0x180012b4a  call    ?DrawEllipse@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@HHHH@Z; Gdiplus::Graphics::DrawEllipse(Gdiplus::Pen const *,int,int,int,int)
0x180012b4f  mov     r8, rsi; struct tagSIZE *
0x180012b52  lea     rdx, [rsp+98h+var_58]; struct Gdiplus::Bitmap *
0x180012b57  mov     rcx, rbp; struct DirectUI::Element *
0x180012b5a  call    ?_SetFeedBackDUIElement@@YAJPEAVElement@DirectUI@@PEAVBitmap@Gdiplus@@PEAUtagSIZE@@@Z; _SetFeedBackDUIElement(DirectUI::Element *,Gdiplus::Bitmap *,tagSIZE *)
0x180012b5f  mov     edi, eax
0x180012b61  test    rbx, rbx
0x180012b64  jz      short loc_180012B6E
0x180012b66  mov     rcx, rbx; this
0x180012b69  call    ??_GGraphics@Gdiplus@@QEAAPEAXI@Z; Gdiplus::Graphics::`scalar deleting destructor'(uint)
0x180012b6e  mov     rcx, [rsp+98h+var_68]
0x180012b73  call    cs:__imp_GdipDeletePen
0x180012b79  mov     rcx, [rsp+98h+var_38]
0x180012b7e  call    cs:__imp_GdipDeleteBrush
0x180012b84  mov     rcx, [rsp+98h+var_50]
0x180012b89  call    cs:__imp_GdipDisposeImage
0x180012b8f  mov     eax, edi
0x180012b91  add     rsp, 78h
0x180012b95  pop     rdi
0x180012b96  pop     rsi
0x180012b97  pop     rbp
0x180012b98  pop     rbx
0x180012b99  retn
```
