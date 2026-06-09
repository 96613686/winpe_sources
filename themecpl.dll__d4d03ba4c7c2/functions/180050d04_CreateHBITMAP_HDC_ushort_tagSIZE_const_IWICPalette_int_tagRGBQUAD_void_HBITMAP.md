# CreateHBITMAP(HDC__ *,ushort,tagSIZE const *,IWICPalette *,int,tagRGBQUAD,void * *,HBITMAP__ * *)

- ea: `0x180050d04`
- end: `0x180050e97`
- name: `?CreateHBITMAP@@YAJPEAUHDC__@@GPEBUtagSIZE@@PEAUIWICPalette@@HUtagRGBQUAD@@PEAPEAXPEAPEAUHBITMAP__@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(HDC, unsigned __int16, const struct tagSIZE *, struct IWICPalette *, int, struct tagRGBQUAD, void **ppvBits, HBITMAP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180051058`

## callees

- `0x180002280`
- `0x180002f34`
- `0x180050d04`
- `0x180057010`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x180050e3f`
- `GDI32!CreateDIBSection` at `0x180050e3f`
- `USER32!GetDC` at `0x180050e0c`
- `USER32!GetDC` at `0x180050e0c`
- `USER32!ReleaseDC` at `0x180050e53`
- `USER32!ReleaseDC` at `0x180050e53`

## pseudocode

```c
__int64 __fastcall CreateHBITMAP(
        HDC a1,
        WORD a2,
        const struct tagSIZE *a3,
        struct IWICPalette *a4,
        int a5,
        struct tagRGBQUAD a6,
        void **ppvBits,
        HBITMAP *a8)
{
  int v11; // ebx
  DWORD v12; // edx
  HDC DC; // rax
  HDC v14; // rdi
  _DWORD v16[4]; // [rsp+30h] [rbp-D0h] BYREF
  BITMAPINFO pbmi; // [rsp+40h] [rbp-C0h] BYREF

  *a8 = 0;
  memset_0(&pbmi.bmiHeader.biSizeImage, 0, 0x414u);
  *(struct tagSIZE *)&pbmi.bmiHeader.biWidth = *a3;
  pbmi.bmiHeader.biPlanes = 1;
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biBitCount = a2;
  pbmi.bmiHeader.biCompression = 0;
  v16[0] = 0;
  if ( a4 && ((int (__fastcall *)(struct IWICPalette *, _DWORD *))a4->lpVtbl->GetColorCount)(a4, v16) >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(struct IWICPalette *, __int64, RGBQUAD *, _DWORD *))a4->lpVtbl->GetColors)(
            a4,
            256,
            pbmi.bmiColors,
            v16);
    if ( v11 < 0 )
      return (unsigned int)v11;
    v12 = v16[0];
    if ( v16[0] > 0x100u )
      return (unsigned int)-2147024809;
    if ( a5 )
      pbmi.bmiColors[v16[0] - 1] = a6;
    pbmi.bmiHeader.biClrImportant = v12;
    pbmi.bmiHeader.biClrUsed = v12;
  }
  v11 = -2147024882;
  DC = GetDC(0);
  v14 = DC;
  if ( DC )
  {
    *a8 = CreateDIBSection(DC, &pbmi, 0, ppvBits, 0, 0);
    ReleaseDC(0, v14);
    if ( *a8 )
      return 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180050d04  mov     [rsp-8+arg_0], rbx
0x180050d09  push    rbp
0x180050d0a  push    rsi
0x180050d0b  push    rdi
0x180050d0c  push    r14
0x180050d0e  push    r15
0x180050d10  lea     rbp, [rsp-380h]
0x180050d18  sub     rsp, 480h
0x180050d1f  mov     rax, cs:__security_cookie
0x180050d26  xor     rax, rsp
0x180050d29  mov     [rbp+3A0h+var_30], rax
0x180050d30  mov     r14, [rbp+3A0h+arg_38]
0x180050d37  lea     rcx, [rsp+4A0h+pbmi.bmiHeader.biSizeImage]; void *
0x180050d3c  mov     r15, [rbp+3A0h+ppvBits]
0x180050d43  mov     rbx, r8
0x180050d46  movzx   edi, dx
0x180050d49  mov     r8d, 414h; Size
0x180050d4f  xor     edx, edx; Val
0x180050d51  mov     rsi, r9
0x180050d54  mov     qword ptr [r14], 0
0x180050d5b  call    memset_0
0x180050d60  mov     eax, [rbx]
0x180050d62  mov     [rsp+4A0h+pbmi.bmiHeader.biWidth], eax
0x180050d66  mov     eax, [rbx+4]
0x180050d69  mov     [rsp+4A0h+pbmi.bmiHeader.biHeight], eax
0x180050d6d  mov     eax, 1
0x180050d72  mov     [rsp+4A0h+pbmi.bmiHeader.biPlanes], ax
0x180050d77  mov     [rsp+4A0h+pbmi.bmiHeader.biSize], 28h ; '('
0x180050d7f  mov     [rsp+4A0h+pbmi.bmiHeader.biBitCount], di
0x180050d84  mov     [rsp+4A0h+pbmi.bmiHeader.biCompression], 0
0x180050d8c  mov     [rsp+4A0h+var_470], 0
0x180050d94  test    rsi, rsi
0x180050d97  jz      short loc_180050E05
0x180050d99  mov     rax, [rsi]
0x180050d9c  lea     rdx, [rsp+4A0h+var_470]
0x180050da1  mov     rcx, rsi
0x180050da4  mov     rax, [rax+40h]
0x180050da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dad  test    eax, eax
0x180050daf  js      short loc_180050E05
0x180050db1  mov     rax, [rsi]
0x180050db4  lea     r9, [rsp+4A0h+var_470]
0x180050db9  mov     edi, 100h
0x180050dbe  lea     r8, [rsp+4A0h+pbmi.bmiColors]
0x180050dc3  mov     edx, edi
0x180050dc5  mov     rcx, rsi
0x180050dc8  mov     rax, [rax+48h]
0x180050dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dd1  mov     ebx, eax
0x180050dd3  test    eax, eax
0x180050dd5  js      loc_180050E67
0x180050ddb  mov     edx, [rsp+4A0h+var_470]
0x180050ddf  cmp     edx, edi
0x180050de1  ja      loc_180050E90
0x180050de7  cmp     [rbp+3A0h+arg_20], 0
0x180050dee  jz      short loc_180050DFD
0x180050df0  mov     eax, dword ptr [rbp+3A0h+arg_28.rgbBlue]
0x180050df6  lea     ecx, [rdx-1]
0x180050df9  mov     dword ptr [rsp+rcx*4+4A0h+pbmi.bmiColors.rgbBlue], eax
0x180050dfd  mov     [rsp+4A0h+pbmi.bmiHeader.biClrImportant], edx
0x180050e01  mov     [rsp+4A0h+pbmi.bmiHeader.biClrUsed], edx
0x180050e05  xor     ecx, ecx; hWnd
0x180050e07  mov     ebx, 8007000Eh
0x180050e0c  call    cs:__imp_GetDC
0x180050e13  nop     dword ptr [rax+rax+00h]
0x180050e18  mov     rdi, rax
0x180050e1b  test    rax, rax
0x180050e1e  jz      short loc_180050E67
0x180050e20  mov     [rsp+4A0h+offset], 0; offset
0x180050e28  lea     rdx, [rsp+4A0h+pbmi]; pbmi
0x180050e2d  mov     r9, r15; ppvBits
0x180050e30  mov     [rsp+4A0h+hSection], 0; hSection
0x180050e39  xor     r8d, r8d; usage
0x180050e3c  mov     rcx, rax; hdc
0x180050e3f  call    cs:__imp_CreateDIBSection
0x180050e46  nop     dword ptr [rax+rax+00h]
0x180050e4b  mov     rdx, rdi; hDC
0x180050e4e  xor     ecx, ecx; hWnd
0x180050e50  mov     [r14], rax
0x180050e53  call    cs:__imp_ReleaseDC
0x180050e5a  nop     dword ptr [rax+rax+00h]
0x180050e5f  xor     eax, eax
0x180050e61  cmp     [r14], rax
0x180050e64  cmovnz  ebx, eax
0x180050e67  mov     eax, ebx
0x180050e69  mov     rcx, [rbp+3A0h+var_30]
0x180050e70  xor     rcx, rsp; StackCookie
0x180050e73  call    __security_check_cookie
0x180050e78  mov     rbx, [rsp+4A0h+arg_0]
0x180050e80  add     rsp, 480h
0x180050e87  pop     r15
0x180050e89  pop     r14
0x180050e8b  pop     rdi
0x180050e8c  pop     rsi
0x180050e8d  pop     rbp
0x180050e8e  retn
0x180050e90  mov     ebx, 80070057h
0x180050e95  jmp     short loc_180050E67
```
