# _CreateHBITMAP

- ea: `0x18006ca4c`
- end: `0x18006ccc2`
- name: `_CreateHBITMAP`
- size: `630`
- prototype: `__int64 __fastcall(Gdiplus::Image *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006bf6c`
- `0x18006bfe8`

## callees

- `0x18006bc28`
- `0x18006be28`
- `0x18006bf28`
- `0x18006c020`
- `0x18006c164`
- `0x18006ca4c`
- `0x18006d3c4`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `GDI32!DeleteObject` at `0x18006cbbc`
- `GDI32!DeleteObject` at `0x18006cbca`
- `GDI32!DeleteObject` at `0x18006cbbc`
- `GDI32!DeleteObject` at `0x18006cbca`
- `GDI32!CreateDIBSection` at `0x18006cb1b`
- `GDI32!CreateDIBSection` at `0x18006cb1b`
- `GDI32!CreateCompatibleDC` at `0x18006cae9`
- `GDI32!CreateCompatibleDC` at `0x18006cae9`
- `GDI32!DeleteDC` at `0x18006cbae`
- `GDI32!DeleteDC` at `0x18006cbae`
- `GDI32!CreateBrushIndirect` at `0x18006cb76`
- `GDI32!CreateBrushIndirect` at `0x18006cb76`
- `GDI32!PatBlt` at `0x18006cc40`
- `GDI32!PatBlt` at `0x18006cc40`
- `GDI32!SelectObject` at `0x18006cb36`
- `GDI32!SelectObject` at `0x18006cb94`
- `GDI32!SelectObject` at `0x18006cba5`
- `GDI32!SelectObject` at `0x18006cbff`
- `GDI32!SelectObject` at `0x18006cb36`
- `GDI32!SelectObject` at `0x18006cb94`
- `GDI32!SelectObject` at `0x18006cba5`
- `GDI32!SelectObject` at `0x18006cbff`
- `gdiplus!GdipAlloc` at `0x18006cc4b`
- `gdiplus!GdipAlloc` at `0x18006cc4b`

## pseudocode

```c
__int64 __fastcall CreateHBITMAP(Gdiplus::Image *this, int a2, HBITMAP *a3)
{
  HDC CompatibleDC; // rax
  HDC v6; // r14
  int v7; // ebx
  HBRUSH v8; // rsi
  HBITMAP v9; // rax
  HBITMAP v10; // rdi
  HBRUSH v11; // rax
  HGDIOBJ v12; // r15
  int Height; // ebx
  int Width; // eax
  Gdiplus::Graphics *v16; // rax
  Gdiplus::Graphics *v17; // r12
  unsigned int v18; // ebx
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // edx
  void *ppvBits; // [rsp+30h] [rbp-99h] BYREF
  HBITMAP *v23; // [rsp+38h] [rbp-91h]
  HGDIOBJ h; // [rsp+40h] [rbp-89h]
  LOGBRUSH plbrush; // [rsp+48h] [rbp-81h] BYREF
  BITMAPINFO pbmi; // [rsp+60h] [rbp-69h] BYREF
  int v27; // [rsp+8Ch] [rbp-3Dh]
  int v28; // [rsp+90h] [rbp-39h]
  int v29; // [rsp+94h] [rbp-35h]

  v23 = a3;
  memset_0(&pbmi.bmiHeader.biWidth, 0, 0x78u);
  ppvBits = 0;
  pbmi.bmiHeader.biSize = 124;
  plbrush = 0;
  pbmi.bmiHeader.biWidth = Gdiplus::Image::GetWidth(this);
  pbmi.bmiHeader.biHeight = Gdiplus::Image::GetHeight(this);
  *(_DWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  pbmi.bmiHeader.biCompression = 3;
  v29 = -16777216;
  pbmi.bmiColors[0] = (RGBQUAD)16711680;
  v27 = 65280;
  v28 = 255;
  CompatibleDC = CreateCompatibleDC(0);
  v6 = CompatibleDC;
  if ( !CompatibleDC )
    return (unsigned int)-2147024882;
  v8 = 0;
  v9 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
  v10 = v9;
  if ( v9 )
  {
    h = SelectObject(v6, v9);
    if ( !h )
    {
      v7 = -2147418113;
      goto LABEL_12;
    }
    plbrush.lbStyle = 0;
    BYTE2(plbrush.lbColor) = a2;
    LOBYTE(plbrush.lbColor) = BYTE2(a2);
    BYTE1(plbrush.lbColor) = BYTE1(a2);
    v11 = CreateBrushIndirect(&plbrush);
    v8 = v11;
    if ( v11 )
    {
      v12 = SelectObject(v6, v11);
      if ( !v12 )
      {
        v7 = -2147418113;
LABEL_10:
        SelectObject(v6, h);
        if ( v12 )
          SelectObject(v6, v12);
        goto LABEL_12;
      }
      Height = Gdiplus::Image::GetHeight(this);
      Width = Gdiplus::Image::GetWidth(this);
      PatBlt(v6, 0, 0, Width, Height, 0xF00021u);
      v16 = (Gdiplus::Graphics *)GdipAlloc(16);
      if ( v16 )
      {
        v17 = (Gdiplus::Graphics *)Gdiplus::Graphics::Graphics(v16, v6);
        if ( v17 )
        {
          v18 = Gdiplus::Image::GetHeight(this);
          v19 = Gdiplus::Image::GetWidth(this);
          v20 = Gdiplus::Graphics::DrawImage(v17, this, 0, 0, v19, v18, ppvBits);
          v7 = ResultFromGdiplusStatus(v20);
          if ( v7 >= 0 )
          {
            *v23 = v10;
            v10 = 0;
            v7 = 0;
          }
          Gdiplus::Graphics::`scalar deleting destructor'(v17, v21);
          goto LABEL_10;
        }
      }
    }
    else
    {
      v12 = 0;
    }
    v7 = -2147024882;
    goto LABEL_10;
  }
  v7 = -2147024882;
LABEL_12:
  DeleteDC(v6);
  if ( v10 )
    DeleteObject(v10);
  if ( v8 )
    DeleteObject(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006ca4c  mov     [rsp-8+arg_8], rbx
0x18006ca51  push    rbp
0x18006ca52  push    rsi
0x18006ca53  push    rdi
0x18006ca54  push    r12
0x18006ca56  push    r13
0x18006ca58  push    r14
0x18006ca5a  push    r15
0x18006ca5c  lea     rbp, [rsp-27h]
0x18006ca61  sub     rsp, 0F0h
0x18006ca68  mov     rax, cs:__security_cookie
0x18006ca6f  xor     rax, rsp
0x18006ca72  mov     [rbp+57h+var_40], rax
0x18006ca76  mov     ebx, edx
0x18006ca78  mov     [rsp+120h+var_E8], r8
0x18006ca7d  xor     edx, edx; Val
0x18006ca7f  mov     r13, rcx
0x18006ca82  lea     rcx, [rbp+57h+pbmi.bmiHeader.biWidth]; void *
0x18006ca86  lea     r8d, [rdx+78h]; Size
0x18006ca8a  call    memset_0
0x18006ca8f  xorps   xmm0, xmm0
0x18006ca92  mov     [rsp+120h+ppvBits], 0
0x18006ca9b  mov     rcx, r13; this
0x18006ca9e  mov     [rbp+57h+pbmi.bmiHeader.biSize], 7Ch ; '|'
0x18006caa5  movups  xmmword ptr [rsp+120h+plbrush.lbStyle], xmm0
0x18006caaa  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x18006caaf  mov     rcx, r13; this
0x18006cab2  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x18006cab5  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x18006caba  xor     ecx, ecx; hdc
0x18006cabc  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18006cabf  mov     dword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18006cac6  mov     [rbp+57h+pbmi.bmiHeader.biCompression], 3
0x18006cacd  mov     [rbp+57h+var_8C], 0FF000000h
0x18006cad4  mov     dword ptr [rbp+57h+pbmi.bmiColors.rgbBlue], 0FF0000h
0x18006cadb  mov     [rbp+57h+var_94], 0FF00h
0x18006cae2  mov     [rbp+57h+var_90], 0FFh
0x18006cae9  call    cs:__imp_CreateCompatibleDC
0x18006caef  mov     r14, rax
0x18006caf2  test    rax, rax
0x18006caf5  jnz     short loc_18006CB01
0x18006caf7  mov     ebx, 8007000Eh
0x18006cafc  jmp     loc_18006CBD0
0x18006cb01  xor     esi, esi
0x18006cb03  lea     r9, [rsp+120h+ppvBits]; ppvBits
0x18006cb08  mov     [rsp+120h+offset], esi; offset
0x18006cb0c  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18006cb10  xor     r8d, r8d; usage
0x18006cb13  mov     [rsp+120h+hSection], rsi; hSection
0x18006cb18  mov     rcx, r14; hdc
0x18006cb1b  call    cs:__imp_CreateDIBSection
0x18006cb21  mov     rdi, rax
0x18006cb24  test    rax, rax
0x18006cb27  jnz     short loc_18006CB30
0x18006cb29  mov     ebx, 8007000Eh
0x18006cb2e  jmp     short loc_18006CBAB
0x18006cb30  mov     rdx, rdi; h
0x18006cb33  mov     rcx, r14; hdc
0x18006cb36  call    cs:__imp_SelectObject
0x18006cb3c  mov     [rsp+120h+h], rax
0x18006cb41  test    rax, rax
0x18006cb44  jnz     short loc_18006CB4D
0x18006cb46  mov     ebx, 8000FFFFh
0x18006cb4b  jmp     short loc_18006CBAB
0x18006cb4d  mov     eax, ebx
0x18006cb4f  mov     [rsp+120h+plbrush.lbStyle], esi
0x18006cb53  shr     eax, 8
0x18006cb56  movzx   edx, al
0x18006cb59  mov     eax, ebx
0x18006cb5b  shr     eax, 10h
0x18006cb5e  movzx   ecx, al
0x18006cb61  shl     edx, 8
0x18006cb64  or      edx, ecx
0x18006cb66  movzx   eax, bl
0x18006cb69  shl     eax, 10h
0x18006cb6c  lea     rcx, [rsp+120h+plbrush]; plbrush
0x18006cb71  or      edx, eax
0x18006cb73  mov     [rbp+57h+plbrush.lbColor], edx
0x18006cb76  call    cs:__imp_CreateBrushIndirect
0x18006cb7c  mov     rsi, rax
0x18006cb7f  test    rax, rax
0x18006cb82  jnz     short loc_18006CBF9
0x18006cb84  xor     r15d, r15d
0x18006cb87  mov     ebx, 8007000Eh
0x18006cb8c  mov     rdx, [rsp+120h+h]; h
0x18006cb91  mov     rcx, r14; hdc
0x18006cb94  call    cs:__imp_SelectObject
0x18006cb9a  test    r15, r15
0x18006cb9d  jz      short loc_18006CBAB
0x18006cb9f  mov     rdx, r15; h
0x18006cba2  mov     rcx, r14; hdc
0x18006cba5  call    cs:__imp_SelectObject
0x18006cbab  mov     rcx, r14; hdc
0x18006cbae  call    cs:__imp_DeleteDC
0x18006cbb4  test    rdi, rdi
0x18006cbb7  jz      short loc_18006CBC2
0x18006cbb9  mov     rcx, rdi; ho
0x18006cbbc  call    cs:__imp_DeleteObject
0x18006cbc2  test    rsi, rsi
0x18006cbc5  jz      short loc_18006CBD0
0x18006cbc7  mov     rcx, rsi; ho
0x18006cbca  call    cs:__imp_DeleteObject
0x18006cbd0  mov     eax, ebx
0x18006cbd2  mov     rcx, [rbp+57h+var_40]
0x18006cbd6  xor     rcx, rsp; StackCookie
0x18006cbd9  call    __security_check_cookie
0x18006cbde  mov     rbx, [rsp+120h+arg_8]
0x18006cbe6  add     rsp, 0F0h
0x18006cbed  pop     r15
0x18006cbef  pop     r14
0x18006cbf1  pop     r13
0x18006cbf3  pop     r12
0x18006cbf5  pop     rdi
0x18006cbf6  pop     rsi
0x18006cbf7  pop     rbp
0x18006cbf8  retn
0x18006cbf9  mov     rdx, rax; h
0x18006cbfc  mov     rcx, r14; hdc
0x18006cbff  call    cs:__imp_SelectObject
0x18006cc05  mov     r15, rax
0x18006cc08  test    rax, rax
0x18006cc0b  jnz     short loc_18006CC17
0x18006cc0d  mov     ebx, 8000FFFFh
0x18006cc12  jmp     loc_18006CB8C
0x18006cc17  mov     rcx, r13; this
0x18006cc1a  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x18006cc1f  mov     rcx, r13; this
0x18006cc22  mov     ebx, eax
0x18006cc24  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x18006cc29  mov     r9d, eax; w
0x18006cc2c  mov     [rsp+120h+offset], 0F00021h; rop
0x18006cc34  xor     r8d, r8d; y
0x18006cc37  mov     dword ptr [rsp+120h+hSection], ebx; h
0x18006cc3b  xor     edx, edx; x
0x18006cc3d  mov     rcx, r14; hdc
0x18006cc40  call    cs:__imp_PatBlt
0x18006cc46  mov     ecx, 10h
0x18006cc4b  call    cs:__imp_GdipAlloc
0x18006cc51  test    rax, rax
0x18006cc54  jz      loc_18006CB87
0x18006cc5a  mov     rdx, r14; HDC
0x18006cc5d  mov     rcx, rax; this
0x18006cc60  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x18006cc65  mov     r12, rax
0x18006cc68  test    rax, rax
0x18006cc6b  jz      loc_18006CB87
0x18006cc71  mov     rcx, r13; this
0x18006cc74  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x18006cc79  mov     rcx, r13; this
0x18006cc7c  mov     ebx, eax
0x18006cc7e  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x18006cc83  xor     r9d, r9d
0x18006cc86  mov     [rsp+120h+offset], ebx
0x18006cc8a  xor     r8d, r8d
0x18006cc8d  mov     dword ptr [rsp+120h+hSection], eax
0x18006cc91  mov     rdx, r13
0x18006cc94  mov     rcx, r12
0x18006cc97  call    ?DrawImage@Graphics@Gdiplus@@QEAA?AW4Status@2@PEAVImage@2@HHHH@Z; Gdiplus::Graphics::DrawImage(Gdiplus::Image *,int,int,int,int)
0x18006cc9c  mov     ecx, eax
0x18006cc9e  call    _ResultFromGdiplusStatus
0x18006cca3  mov     ebx, eax
0x18006cca5  test    eax, eax
0x18006cca7  js      short loc_18006CCB5
0x18006cca9  mov     rax, [rsp+120h+var_E8]
0x18006ccae  mov     [rax], rdi
0x18006ccb1  xor     edi, edi
0x18006ccb3  xor     ebx, ebx
0x18006ccb5  mov     rcx, r12; this
0x18006ccb8  call    ??_GGraphics@Gdiplus@@QEAAPEAXI@Z; Gdiplus::Graphics::`scalar deleting destructor'(uint)
0x18006ccbd  jmp     loc_18006CB8C
```
