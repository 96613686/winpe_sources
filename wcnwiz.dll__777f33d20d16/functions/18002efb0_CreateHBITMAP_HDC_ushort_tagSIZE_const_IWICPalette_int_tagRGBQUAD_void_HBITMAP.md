# CreateHBITMAP(HDC__ *,ushort,tagSIZE const *,IWICPalette *,int,tagRGBQUAD,void * *,HBITMAP__ * *)

- ea: `0x18002efb0`
- end: `0x18002f12c`
- name: `?CreateHBITMAP@@YAJPEAUHDC__@@GPEBUtagSIZE@@PEAUIWICPalette@@HUtagRGBQUAD@@PEAPEAXPEAPEAUHBITMAP__@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(HDC, unsigned __int16, const struct tagSIZE *, struct IWICPalette *, int, struct tagRGBQUAD, void **ppvBits, HBITMAP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002f2e8`

## callees

- `0x180001820`
- `0x180002294`
- `0x18002efb0`
- `0x180031010`

## import_xrefs

- `USER32!GetDC` at `0x18002f0b4`
- `USER32!GetDC` at `0x18002f0b4`
- `USER32!ReleaseDC` at `0x18002f0ef`
- `USER32!ReleaseDC` at `0x18002f0ef`
- `GDI32!CreateDIBSection` at `0x18002f0e1`
- `GDI32!CreateDIBSection` at `0x18002f0e1`

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
0x18002efb0  mov     [rsp-8+arg_0], rbx
0x18002efb5  push    rbp
0x18002efb6  push    rsi
0x18002efb7  push    rdi
0x18002efb8  push    r14
0x18002efba  push    r15
0x18002efbc  lea     rbp, [rsp-380h]
0x18002efc4  sub     rsp, 480h
0x18002efcb  mov     rax, cs:__security_cookie
0x18002efd2  xor     rax, rsp
0x18002efd5  mov     [rbp+3A0h+var_30], rax
0x18002efdc  mov     r14, [rbp+3A0h+arg_38]
0x18002efe3  lea     rcx, [rsp+4A0h+pbmi.bmiHeader.biSizeImage]; void *
0x18002efe8  mov     r15, [rbp+3A0h+ppvBits]
0x18002efef  mov     rbx, r8
0x18002eff2  movzx   edi, dx
0x18002eff5  mov     r8d, 414h; Size
0x18002effb  xor     edx, edx; Val
0x18002effd  mov     rsi, r9
0x18002f000  mov     qword ptr [r14], 0
0x18002f007  call    memset_0
0x18002f00c  mov     eax, [rbx]
0x18002f00e  mov     [rsp+4A0h+pbmi.bmiHeader.biWidth], eax
0x18002f012  mov     eax, [rbx+4]
0x18002f015  mov     [rsp+4A0h+pbmi.bmiHeader.biHeight], eax
0x18002f019  mov     eax, 1
0x18002f01e  mov     [rsp+4A0h+pbmi.bmiHeader.biPlanes], ax
0x18002f023  mov     [rsp+4A0h+pbmi.bmiHeader.biSize], 28h ; '('
0x18002f02b  mov     [rsp+4A0h+pbmi.bmiHeader.biBitCount], di
0x18002f030  mov     [rsp+4A0h+pbmi.bmiHeader.biCompression], 0
0x18002f038  mov     [rsp+4A0h+var_470], 0
0x18002f040  test    rsi, rsi
0x18002f043  jz      short loc_18002F0AD
0x18002f045  mov     rax, [rsi]
0x18002f048  lea     rdx, [rsp+4A0h+var_470]
0x18002f04d  mov     rcx, rsi
0x18002f050  mov     rax, [rax+40h]
0x18002f054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f059  test    eax, eax
0x18002f05b  js      short loc_18002F0AD
0x18002f05d  mov     rax, [rsi]
0x18002f060  lea     r9, [rsp+4A0h+var_470]
0x18002f065  mov     edi, 100h
0x18002f06a  lea     r8, [rsp+4A0h+pbmi.bmiColors]
0x18002f06f  mov     edx, edi
0x18002f071  mov     rcx, rsi
0x18002f074  mov     rax, [rax+48h]
0x18002f078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f07d  mov     ebx, eax
0x18002f07f  test    eax, eax
0x18002f081  js      short loc_18002F0FD
0x18002f083  mov     edx, [rsp+4A0h+var_470]
0x18002f087  cmp     edx, edi
0x18002f089  ja      loc_18002F125
0x18002f08f  cmp     [rbp+3A0h+arg_20], 0
0x18002f096  jz      short loc_18002F0A5
0x18002f098  mov     eax, dword ptr [rbp+3A0h+arg_28.rgbBlue]
0x18002f09e  lea     ecx, [rdx-1]
0x18002f0a1  mov     dword ptr [rsp+rcx*4+4A0h+pbmi.bmiColors.rgbBlue], eax
0x18002f0a5  mov     [rsp+4A0h+pbmi.bmiHeader.biClrImportant], edx
0x18002f0a9  mov     [rsp+4A0h+pbmi.bmiHeader.biClrUsed], edx
0x18002f0ad  xor     ecx, ecx; hWnd
0x18002f0af  mov     ebx, 8007000Eh
0x18002f0b4  call    cs:__imp_GetDC
0x18002f0ba  mov     rdi, rax
0x18002f0bd  test    rax, rax
0x18002f0c0  jz      short loc_18002F0FD
0x18002f0c2  mov     [rsp+4A0h+offset], 0; offset
0x18002f0ca  lea     rdx, [rsp+4A0h+pbmi]; pbmi
0x18002f0cf  mov     r9, r15; ppvBits
0x18002f0d2  mov     [rsp+4A0h+hSection], 0; hSection
0x18002f0db  xor     r8d, r8d; usage
0x18002f0de  mov     rcx, rax; hdc
0x18002f0e1  call    cs:__imp_CreateDIBSection
0x18002f0e7  mov     rdx, rdi; hDC
0x18002f0ea  xor     ecx, ecx; hWnd
0x18002f0ec  mov     [r14], rax
0x18002f0ef  call    cs:__imp_ReleaseDC
0x18002f0f5  xor     eax, eax
0x18002f0f7  cmp     [r14], rax
0x18002f0fa  cmovnz  ebx, eax
0x18002f0fd  mov     eax, ebx
0x18002f0ff  mov     rcx, [rbp+3A0h+var_30]
0x18002f106  xor     rcx, rsp; StackCookie
0x18002f109  call    __security_check_cookie
0x18002f10e  mov     rbx, [rsp+4A0h+arg_0]
0x18002f116  add     rsp, 480h
0x18002f11d  pop     r15
0x18002f11f  pop     r14
0x18002f121  pop     rdi
0x18002f122  pop     rsi
0x18002f123  pop     rbp
0x18002f124  retn
0x18002f125  mov     ebx, 80070057h
0x18002f12a  jmp     short loc_18002F0FD
```
