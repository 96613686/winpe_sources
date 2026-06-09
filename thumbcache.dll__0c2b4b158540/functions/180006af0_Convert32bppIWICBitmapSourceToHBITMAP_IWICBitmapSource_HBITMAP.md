# Convert32bppIWICBitmapSourceToHBITMAP(IWICBitmapSource *,HBITMAP__ * *)

- ea: `0x180006af0`
- end: `0x180006c34`
- name: `?Convert32bppIWICBitmapSourceToHBITMAP@@YAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, HBITMAP *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000701c`
- `0x180047358`

## callees

- `0x180006af0`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180006ba5`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180006ba5`
- `GDI32!DeleteObject` at `0x180006c2c`
- `GDI32!DeleteObject` at `0x180006c2c`

## pseudocode

```c
__int64 __fastcall Convert32bppIWICBitmapSourceToHBITMAP(struct IWICBitmapSource *a1, HBITMAP *a2)
{
  struct IWICBitmapSourceVtbl *lpVtbl; // rax
  int v5; // ebx
  HBITMAP v6; // rdi
  struct IWICBitmapSourceVtbl *v7; // rdx
  HRESULT (__stdcall *CopyPixels)(IWICBitmapSource *, const WICRect *, UINT, UINT, BYTE *); // rax
  void *ppvBits; // [rsp+30h] [rbp-19h] BYREF
  LONG v11; // [rsp+38h] [rbp-11h] BYREF
  int v12; // [rsp+3Ch] [rbp-Dh] BYREF
  __int64 v13; // [rsp+40h] [rbp-9h] BYREF
  LONG v14; // [rsp+48h] [rbp-1h]
  int v15; // [rsp+4Ch] [rbp+3h]
  BITMAPINFO pbmi; // [rsp+50h] [rbp+7h] BYREF

  *a2 = 0;
  lpVtbl = a1->lpVtbl;
  v11 = 0;
  v12 = 0;
  v5 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, LONG *, int *))lpVtbl->GetSize)(a1, &v11, &v12);
  if ( v5 >= 0 )
  {
    pbmi.bmiHeader.biSize = 40;
    pbmi.bmiHeader.biWidth = v11;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    pbmi.bmiHeader.biHeight = -v12;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    ppvBits = 0;
    v6 = CreateDIBSection(0, &pbmi, 0, &ppvBits, 0, 0);
    if ( v6 )
    {
      v7 = a1->lpVtbl;
      v15 = v12;
      CopyPixels = v7->CopyPixels;
      v14 = v11;
      v13 = 0;
      v5 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int64 *, _QWORD, _QWORD, void *))CopyPixels)(
             a1,
             &v13,
             (unsigned int)(4 * v11),
             (unsigned int)(4 * v11 * v12),
             ppvBits);
      if ( v5 < 0 )
        DeleteObject(v6);
      else
        *a2 = v6;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006af0  mov     [rsp-8+arg_10], rbx
0x180006af5  mov     [rsp-8+arg_18], rsi
0x180006afa  push    rbp
0x180006afb  push    rdi
0x180006afc  push    r14
0x180006afe  lea     rbp, [rsp-47h]
0x180006b03  sub     rsp, 90h
0x180006b0a  mov     rax, cs:__security_cookie
0x180006b11  xor     rax, rsp
0x180006b14  mov     [rbp+57h+var_20], rax
0x180006b18  mov     qword ptr [rdx], 0
0x180006b1f  lea     r8, [rbp+57h+var_64]
0x180006b23  mov     rax, [rcx]
0x180006b26  mov     rsi, rdx
0x180006b29  lea     rdx, [rbp+57h+var_68]
0x180006b2d  mov     [rbp+57h+var_68], 0
0x180006b34  mov     r14, rcx
0x180006b37  mov     [rbp+57h+var_64], 0
0x180006b3e  mov     rax, [rax+18h]
0x180006b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b47  mov     ebx, eax
0x180006b49  test    eax, eax
0x180006b4b  js      loc_180006BFC
0x180006b51  xor     eax, eax
0x180006b53  mov     [rsp+0A0h+offset], 0; offset
0x180006b5b  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x180006b5f  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180006b63  mov     eax, [rbp+57h+var_68]
0x180006b66  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180006b6a  xorps   xmm0, xmm0
0x180006b6d  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x180006b74  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x180006b78  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x180006b7b  xor     r8d, r8d; usage
0x180006b7e  mov     eax, [rbp+57h+var_64]
0x180006b81  xor     ecx, ecx; hdc
0x180006b83  neg     eax
0x180006b85  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180006b8d  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x180006b90  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180006b94  mov     [rbp+57h+ppvBits], 0
0x180006b9c  mov     [rsp+0A0h+hSection], 0; hSection
0x180006ba5  call    cs:__imp_CreateDIBSection
0x180006bab  mov     rdi, rax
0x180006bae  test    rax, rax
0x180006bb1  jz      short loc_180006C22
0x180006bb3  mov     r8d, [rbp+57h+var_68]
0x180006bb7  mov     rcx, r14
0x180006bba  mov     rdx, [r14]
0x180006bbd  mov     r9d, [rbp+57h+var_64]
0x180006bc1  mov     [rbp+57h+var_54], r9d
0x180006bc5  imul    r9d, r8d
0x180006bc9  mov     rax, [rdx+38h]
0x180006bcd  mov     rdx, [rbp+57h+ppvBits]
0x180006bd1  mov     [rsp+0A0h+hSection], rdx
0x180006bd6  lea     rdx, [rbp+57h+var_60]
0x180006bda  mov     [rbp+57h+var_58], r8d
0x180006bde  shl     r9d, 2
0x180006be2  shl     r8d, 2
0x180006be6  mov     [rbp+57h+var_60], 0
0x180006bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf3  mov     ebx, eax
0x180006bf5  test    eax, eax
0x180006bf7  js      short loc_180006C29
0x180006bf9  mov     [rsi], rdi
0x180006bfc  mov     eax, ebx
0x180006bfe  mov     rcx, [rbp+57h+var_20]
0x180006c02  xor     rcx, rsp; StackCookie
0x180006c05  call    __security_check_cookie
0x180006c0a  lea     r11, [rsp+0A0h+var_10]
0x180006c12  mov     rbx, [r11+30h]
0x180006c16  mov     rsi, [r11+38h]
0x180006c1a  mov     rsp, r11
0x180006c1d  pop     r14
0x180006c1f  pop     rdi
0x180006c20  pop     rbp
0x180006c21  retn
0x180006c22  mov     ebx, 8007000Eh
0x180006c27  jmp     short loc_180006BFC
0x180006c29  mov     rcx, rdi; ho
0x180006c2c  call    cs:__imp_DeleteObject
0x180006c32  jmp     short loc_180006BFC
```
