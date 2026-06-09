# LogonScreenHelper::CreateDuiBitmapFromGDIPlusBitmap(Gdiplus::Bitmap *,uint,uint,tagRECT,uchar,bool)

- ea: `0x180017bc0`
- end: `0x180017c99`
- name: `?CreateDuiBitmapFromGDIPlusBitmap@LogonScreenHelper@@QEAAPEAVValue@DirectUI@@PEAVBitmap@Gdiplus@@IIUtagRECT@@E_N@Z`
- size: `217`
- prototype: `struct DirectUI::Value *__fastcall(LogonScreenHelper *__hidden this, struct Gdiplus::Bitmap *, unsigned int, unsigned int, struct tagRECT *, unsigned __int8, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180016f48`
- `0x18001716c`

## callees

- `0x180017844`
- `0x180017bc0`
- `0x180018c00`
- `0x18001d010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180017c52`
- `GDI32!DeleteObject` at `0x180017c52`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180017c18`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180017c18`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x180017c3f`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x180017c3f`

## pseudocode

```c
struct DirectUI::Value *__fastcall LogonScreenHelper::CreateDuiBitmapFromGDIPlusBitmap(
        LogonScreenHelper *this,
        struct Gdiplus::Bitmap *a2,
        unsigned int a3,
        unsigned int a4,
        struct tagRECT *a5)
{
  struct DirectUI::Value *Graphic; // rsi
  struct Gdiplus::Bitmap *v7; // rbx
  LogonScreenHelper *v8; // rcx
  struct Gdiplus::Bitmap *v9; // rax
  struct Gdiplus::Bitmap *v10; // rdi
  __int64 v11; // rcx
  int v12; // eax
  struct tagRECT v14; // [rsp+30h] [rbp-38h] BYREF
  HGDIOBJ ho; // [rsp+70h] [rbp+8h] BYREF

  ho = this;
  Graphic = 0;
  v7 = LogonScreenHelper::ResizeGDIplusBitmap(this, a2, a3, a4);
  v14 = *a5;
  v9 = LogonScreenHelper::ClipGDIplusBitmap(v8, v7, &v14);
  v10 = v9;
  if ( v9 )
  {
    v11 = *((_QWORD *)v9 + 1);
    ho = 0;
    v12 = GdipCreateHBITMAPFromBitmap(v11, &ho, 4278190080LL);
    if ( v12 )
    {
      *((_DWORD *)v10 + 4) = v12;
    }
    else
    {
      Graphic = DirectUI::Value::CreateGraphic((HBITMAP)ho, 0, 0xFFFFFFFF, 0, 0, 0);
      if ( !Graphic )
        DeleteObject(ho);
    }
    if ( v10 != v7 )
      (**(void (__fastcall ***)(struct Gdiplus::Bitmap *, __int64))v10)(v10, 1);
    if ( v7 != a2 && v7 )
      (**(void (__fastcall ***)(struct Gdiplus::Bitmap *, __int64))v7)(v7, 1);
  }
  return Graphic;
}

```

## disassembly

```asm
0x180017bc0  mov     [rsp+ho], rcx
0x180017bc5  push    rbx
0x180017bc6  push    rbp
0x180017bc7  push    rsi
0x180017bc8  push    rdi
0x180017bc9  sub     rsp, 48h
0x180017bcd  mov     rbp, rdx
0x180017bd0  xor     esi, esi
0x180017bd2  call    ?ResizeGDIplusBitmap@LogonScreenHelper@@QEAAPEAVBitmap@Gdiplus@@PEAV23@II@Z; LogonScreenHelper::ResizeGDIplusBitmap(Gdiplus::Bitmap *,uint,uint)
0x180017bd7  mov     rbx, rax
0x180017bda  lea     r8, [rsp+68h+var_38]; struct tagRECT
0x180017bdf  mov     rax, [rsp+68h+arg_20]
0x180017be7  mov     rdx, rbx; struct Gdiplus::Bitmap *
0x180017bea  movaps  xmm0, xmmword ptr [rax]
0x180017bed  movdqa  xmmword ptr [rsp+68h+var_38.left], xmm0
0x180017bf3  call    ?ClipGDIplusBitmap@LogonScreenHelper@@QEAAPEAVBitmap@Gdiplus@@PEAV23@UtagRECT@@@Z; LogonScreenHelper::ClipGDIplusBitmap(Gdiplus::Bitmap *,tagRECT)
0x180017bf8  mov     rdi, rax
0x180017bfb  test    rax, rax
0x180017bfe  jz      loc_180017C8D
0x180017c04  mov     rcx, [rax+8]
0x180017c08  lea     rdx, [rsp+68h+ho]
0x180017c0d  mov     r8d, 0FF000000h
0x180017c13  mov     [rsp+68h+ho], rsi
0x180017c18  call    cs:__imp_GdipCreateHBITMAPFromBitmap
0x180017c1e  test    eax, eax
0x180017c20  jz      short loc_180017C27
0x180017c22  mov     [rdi+10h], eax
0x180017c25  jmp     short loc_180017C58
0x180017c27  mov     rcx, [rsp+68h+ho]
0x180017c2c  xor     r9d, r9d
0x180017c2f  mov     [rsp+68h+var_40], sil
0x180017c34  or      r8d, 0FFFFFFFFh
0x180017c38  xor     edx, edx
0x180017c3a  mov     [rsp+68h+var_48], sil
0x180017c3f  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x180017c45  mov     rsi, rax
0x180017c48  test    rax, rax
0x180017c4b  jnz     short loc_180017C58
0x180017c4d  mov     rcx, [rsp+68h+ho]; ho
0x180017c52  call    cs:__imp_DeleteObject
0x180017c58  cmp     rdi, rbx
0x180017c5b  jz      short loc_180017C70
0x180017c5d  mov     rcx, [rdi]
0x180017c60  mov     edx, 1
0x180017c65  mov     rax, [rcx]
0x180017c68  mov     rcx, rdi
0x180017c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c70  cmp     rbx, rbp
0x180017c73  jz      short loc_180017C8D
0x180017c75  test    rbx, rbx
0x180017c78  jz      short loc_180017C8D
0x180017c7a  mov     rax, [rbx]
0x180017c7d  mov     edx, 1
0x180017c82  mov     rcx, rbx
0x180017c85  mov     rax, [rax]
0x180017c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c8d  mov     rax, rsi
0x180017c90  add     rsp, 48h
0x180017c94  pop     rdi
0x180017c95  pop     rsi
0x180017c96  pop     rbp
0x180017c97  pop     rbx
0x180017c98  retn
```
