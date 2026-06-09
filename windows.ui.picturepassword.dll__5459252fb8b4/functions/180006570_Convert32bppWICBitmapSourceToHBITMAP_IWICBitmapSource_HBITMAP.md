# Convert32bppWICBitmapSourceToHBITMAP(IWICBitmapSource *,HBITMAP__ * *)

- ea: `0x180006570`
- end: `0x1800066b4`
- name: `?Convert32bppWICBitmapSourceToHBITMAP@@YAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, HBITMAP *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006880`

## callees

- `0x180002610`
- `0x180006570`
- `0x18001f010`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180006625`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180006625`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180006688`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180006688`

## pseudocode

```c
__int64 __fastcall Convert32bppWICBitmapSourceToHBITMAP(struct IWICBitmapSource *a1, HBITMAP *a2)
{
  struct IWICBitmapSourceVtbl *lpVtbl; // rax
  int v5; // ebx
  HBITMAP v6; // rdi
  struct IWICBitmapSourceVtbl *v7; // rax
  HRESULT (__stdcall *CopyPixels)(IWICBitmapSource *, const WICRect *, UINT, UINT, BYTE *); // rax
  LONG v10; // [rsp+30h] [rbp-19h] BYREF
  int v11; // [rsp+34h] [rbp-15h] BYREF
  void *ppvBits; // [rsp+38h] [rbp-11h] BYREF
  __int64 v13; // [rsp+40h] [rbp-9h] BYREF
  LONG v14; // [rsp+48h] [rbp-1h]
  int v15; // [rsp+4Ch] [rbp+3h]
  BITMAPINFO pbmi; // [rsp+50h] [rbp+7h] BYREF

  *a2 = 0;
  lpVtbl = a1->lpVtbl;
  v10 = 0;
  v11 = 0;
  v5 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, LONG *, int *))lpVtbl->GetSize)(a1, &v10, &v11);
  if ( v5 >= 0 )
  {
    pbmi.bmiHeader.biSize = 40;
    pbmi.bmiHeader.biWidth = v10;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    pbmi.bmiHeader.biHeight = -v11;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    ppvBits = 0;
    v6 = CreateDIBSection(0, &pbmi, 0, &ppvBits, 0, 0);
    if ( v6 )
    {
      v7 = a1->lpVtbl;
      v15 = v11;
      v14 = v10;
      CopyPixels = v7->CopyPixels;
      v13 = 0;
      v5 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int64 *, _QWORD, _QWORD, void *))CopyPixels)(
             a1,
             &v13,
             (unsigned int)(4 * v10),
             (unsigned int)(4 * v10 * v11),
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
0x180006570  mov     [rsp-8+arg_10], rbx
0x180006575  mov     [rsp-8+arg_18], rsi
0x18000657a  push    rbp
0x18000657b  push    rdi
0x18000657c  push    r14
0x18000657e  lea     rbp, [rsp-47h]
0x180006583  sub     rsp, 90h
0x18000658a  mov     rax, cs:__security_cookie
0x180006591  xor     rax, rsp
0x180006594  mov     [rbp+57h+var_20], rax
0x180006598  mov     qword ptr [rdx], 0
0x18000659f  lea     r8, [rbp+57h+var_6C]
0x1800065a3  mov     rax, [rcx]
0x1800065a6  mov     rsi, rdx
0x1800065a9  lea     rdx, [rbp+57h+var_70]
0x1800065ad  mov     [rbp+57h+var_70], 0
0x1800065b4  mov     r14, rcx
0x1800065b7  mov     [rbp+57h+var_6C], 0
0x1800065be  mov     rax, [rax+18h]
0x1800065c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065c7  mov     ebx, eax
0x1800065c9  test    eax, eax
0x1800065cb  js      loc_18000668E
0x1800065d1  xor     eax, eax
0x1800065d3  mov     [rsp+0A0h+offset], 0; offset
0x1800065db  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x1800065df  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x1800065e3  mov     eax, [rbp+57h+var_70]
0x1800065e6  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1800065ea  xorps   xmm0, xmm0
0x1800065ed  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800065f4  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x1800065f8  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1800065fb  xor     r8d, r8d; usage
0x1800065fe  mov     eax, [rbp+57h+var_6C]
0x180006601  xor     ecx, ecx; hdc
0x180006603  neg     eax
0x180006605  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18000660d  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x180006610  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180006614  mov     [rbp+57h+ppvBits], 0
0x18000661c  mov     [rsp+0A0h+hSection], 0; hSection
0x180006625  call    cs:__imp_CreateDIBSection
0x18000662b  mov     rdi, rax
0x18000662e  test    rax, rax
0x180006631  jnz     short loc_18000663A
0x180006633  mov     ebx, 8007000Eh
0x180006638  jmp     short loc_18000668E
0x18000663a  mov     r8d, [rbp+57h+var_70]
0x18000663e  mov     rcx, r14
0x180006641  mov     r9d, [rbp+57h+var_6C]
0x180006645  mov     rdx, [rbp+57h+ppvBits]
0x180006649  mov     rax, [r14]
0x18000664c  mov     [rbp+57h+var_54], r9d
0x180006650  imul    r9d, r8d
0x180006654  mov     [rbp+57h+var_58], r8d
0x180006658  mov     rax, [rax+38h]
0x18000665c  mov     [rsp+0A0h+hSection], rdx
0x180006661  lea     rdx, [rbp+57h+var_60]
0x180006665  shl     r8d, 2
0x180006669  shl     r9d, 2
0x18000666d  mov     [rbp+57h+var_60], 0
0x180006675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000667a  mov     ebx, eax
0x18000667c  test    eax, eax
0x18000667e  js      short loc_180006685
0x180006680  mov     [rsi], rdi
0x180006683  jmp     short loc_18000668E
0x180006685  mov     rcx, rdi; ho
0x180006688  call    cs:__imp_DeleteObject
0x18000668e  mov     eax, ebx
0x180006690  mov     rcx, [rbp+57h+var_20]
0x180006694  xor     rcx, rsp; StackCookie
0x180006697  call    __security_check_cookie
0x18000669c  lea     r11, [rsp+0A0h+var_10]
0x1800066a4  mov     rbx, [r11+30h]
0x1800066a8  mov     rsi, [r11+38h]
0x1800066ac  mov     rsp, r11
0x1800066af  pop     r14
0x1800066b1  pop     rdi
0x1800066b2  pop     rbp
0x1800066b3  retn
```
