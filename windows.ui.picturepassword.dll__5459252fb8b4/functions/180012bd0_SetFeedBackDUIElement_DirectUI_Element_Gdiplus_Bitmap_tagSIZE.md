# _SetFeedBackDUIElement(DirectUI::Element *,Gdiplus::Bitmap *,tagSIZE *)

- ea: `0x180012bd0`
- end: `0x180012d73`
- name: `?_SetFeedBackDUIElement@@YAJPEAVElement@DirectUI@@PEAVBitmap@Gdiplus@@PEAUtagSIZE@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, struct Gdiplus::Bitmap *, struct tagSIZE *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180012338`
- `0x1800123dc`
- `0x180012a94`

## callees

- `0x180002610`
- `0x180002f94`
- `0x1800092b8`
- `0x18000cf80`
- `0x18000d3d0`
- `0x18000db20`
- `0x180010d04`
- `0x180012bd0`

## import_xrefs

- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x180012cac`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x180012cac`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180012cf4`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180012cf4`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180012ce1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180012cd9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180012cd9`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180012c6e`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180012c6e`
- `gdiplus!GdipGetImageHeight` at `0x180012d31`
- `gdiplus!GdipGetImageHeight` at `0x180012d31`
- `gdiplus!GdipSetEffectParameters` at `0x180012c44`
- `gdiplus!GdipSetEffectParameters` at `0x180012c44`
- `gdiplus!GdipGetImageWidth` at `0x180012d0d`
- `gdiplus!GdipGetImageWidth` at `0x180012d0d`

## pseudocode

```c
__int64 __fastcall _SetFeedBackDUIElement(struct DirectUI::Element *a1, struct Gdiplus::Bitmap *a2, struct tagSIZE *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  HBITMAP v8; // rcx
  int Error; // edi
  struct DirectUI::Value *Graphic; // rax
  struct DirectUI::Value *v11; // rdi
  int v12; // eax
  __int64 v13; // rcx
  int ImageWidth; // eax
  __int64 v15; // rcx
  int ImageHeight; // eax
  LONG v18; // [rsp+30h] [rbp-89h] BYREF
  HGDIOBJ ho; // [rsp+38h] [rbp-81h] BYREF
  struct DirectUI::Value *v20; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v21[8]; // [rsp+48h] [rbp-71h] BYREF
  __int64 v22; // [rsp+50h] [rbp-69h]
  _DWORD v23[28]; // [rsp+70h] [rbp-49h] BYREF

  memset_0(v23, 0, 0x64u);
  v23[24] = 1065353216;
  v23[12] = 1065353216;
  v23[6] = 1065353216;
  v23[0] = 1065353216;
  v23[18] = 1056997505;
  Gdiplus::ColorMatrixEffect::ColorMatrixEffect((Gdiplus::ColorMatrixEffect *)v21);
  GdipSetEffectParameters(v22, v23, 100);
  Gdiplus::Bitmap::ApplyEffect(a2, v21);
  v6 = *((_QWORD *)a2 + 1);
  ho = 0;
  v7 = GdipCreateHBITMAPFromBitmap(v6, &ho, 4278190080LL);
  if ( v7 )
    *((_DWORD *)a2 + 4) = v7;
  v8 = (HBITMAP)ho;
  if ( !ho )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_14;
    v8 = (HBITMAP)ho;
  }
  Graphic = DirectUI::Value::CreateGraphic(v8, 2u, 0xFFFFFFFF, 0, 0, 1);
  v20 = 0;
  v11 = Graphic;
  CValuePtr::Release((CValuePtr *)&v20);
  v20 = v11;
  if ( v11 )
  {
    v12 = DirectUI::Element::SetValue(
            a1,
            (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
            1,
            v11);
    v13 = *((_QWORD *)a2 + 1);
    Error = v12;
    v18 = 0;
    ImageWidth = GdipGetImageWidth(v13, &v18);
    if ( ImageWidth )
      *((_DWORD *)a2 + 4) = ImageWidth;
    a3->cx = v18;
    v15 = *((_QWORD *)a2 + 1);
    v18 = 0;
    ImageHeight = GdipGetImageHeight(v15, &v18);
    if ( ImageHeight )
      *((_DWORD *)a2 + 4) = ImageHeight;
    a3->cy = v18;
  }
  else
  {
    Error = -2147024882;
    DeleteObject(ho);
  }
  CValuePtr::Release((CValuePtr *)&v20);
LABEL_14:
  Gdiplus::Effect::~Effect((Gdiplus::Effect *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180012bd0  push    rbp
0x180012bd2  push    rbx
0x180012bd3  push    rsi
0x180012bd4  push    rdi
0x180012bd5  push    r14
0x180012bd7  lea     rbp, [rsp-37h]
0x180012bdc  sub     rsp, 0F0h
0x180012be3  mov     rax, cs:__security_cookie
0x180012bea  xor     rax, rsp
0x180012bed  mov     [rbp+57h+var_30], rax
0x180012bf1  mov     rsi, r8
0x180012bf4  mov     rbx, rdx
0x180012bf7  mov     r14, rcx
0x180012bfa  mov     edi, 64h ; 'd'
0x180012bff  mov     r8d, edi; Size
0x180012c02  lea     rcx, [rbp+57h+var_A0]; void *
0x180012c06  xor     edx, edx; Val
0x180012c08  call    memset_0
0x180012c0d  lea     rcx, [rbp+57h+var_C8]; this
0x180012c11  mov     [rbp+57h+var_40], 3F800000h
0x180012c18  mov     [rbp+57h+var_70], 3F800000h
0x180012c1f  mov     [rbp+57h+var_88], 3F800000h
0x180012c26  mov     [rbp+57h+var_A0], 3F800000h
0x180012c2d  mov     [rbp+57h+var_58], 3F008081h
0x180012c34  call    ??0ColorMatrixEffect@Gdiplus@@QEAA@XZ; Gdiplus::ColorMatrixEffect::ColorMatrixEffect(void)
0x180012c39  mov     rcx, [rbp+57h+var_C0]
0x180012c3d  lea     rdx, [rbp+57h+var_A0]
0x180012c41  mov     r8d, edi
0x180012c44  call    cs:__imp_GdipSetEffectParameters
0x180012c4a  lea     rdx, [rbp+57h+var_C8]
0x180012c4e  mov     rcx, rbx
0x180012c51  call    ?ApplyEffect@Bitmap@Gdiplus@@QEAA?AW4Status@2@PEAVEffect@2@PEAUtagRECT@@@Z; Gdiplus::Bitmap::ApplyEffect(Gdiplus::Effect *,tagRECT *)
0x180012c56  mov     rcx, [rbx+8]
0x180012c5a  lea     rdx, [rsp+110h+ho]
0x180012c5f  mov     r8d, 0FF000000h
0x180012c65  mov     [rsp+110h+ho], 0
0x180012c6e  call    cs:__imp_GdipCreateHBITMAPFromBitmap
0x180012c74  test    eax, eax
0x180012c76  jz      short loc_180012C7B
0x180012c78  mov     [rbx+10h], eax
0x180012c7b  mov     rcx, [rsp+110h+ho]
0x180012c80  test    rcx, rcx
0x180012c83  jnz     short loc_180012C99
0x180012c85  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180012c8a  mov     edi, eax
0x180012c8c  test    eax, eax
0x180012c8e  js      loc_180012D4E
0x180012c94  mov     rcx, [rsp+110h+ho]
0x180012c99  mov     [rsp+110h+var_E8], 1
0x180012c9e  xor     r9d, r9d
0x180012ca1  or      r8d, 0FFFFFFFFh
0x180012ca5  mov     [rsp+110h+var_F0], 0
0x180012caa  mov     dl, 2
0x180012cac  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x180012cb2  lea     rcx, [rbp+57h+var_D0]; this
0x180012cb6  mov     [rbp+57h+var_D0], 0
0x180012cbe  mov     rdi, rax
0x180012cc1  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180012cc6  mov     [rbp+57h+var_D0], rdi
0x180012cca  test    rdi, rdi
0x180012ccd  jnz     short loc_180012CE1
0x180012ccf  mov     rcx, [rsp+110h+ho]; ho
0x180012cd4  mov     edi, 8007000Eh
0x180012cd9  call    cs:__imp_DeleteObject
0x180012cdf  jmp     short loc_180012D45
0x180012ce1  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180012ce8  mov     r9, rdi
0x180012ceb  mov     r8d, 1
0x180012cf1  mov     rcx, r14
0x180012cf4  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180012cfa  mov     rcx, [rbx+8]
0x180012cfe  lea     rdx, [rsp+110h+var_E0]
0x180012d03  mov     edi, eax
0x180012d05  mov     [rsp+110h+var_E0], 0
0x180012d0d  call    cs:__imp_GdipGetImageWidth
0x180012d13  test    eax, eax
0x180012d15  jz      short loc_180012D1A
0x180012d17  mov     [rbx+10h], eax
0x180012d1a  mov     ecx, [rsp+110h+var_E0]
0x180012d1e  lea     rdx, [rsp+110h+var_E0]
0x180012d23  mov     [rsi], ecx
0x180012d25  mov     rcx, [rbx+8]
0x180012d29  mov     [rsp+110h+var_E0], 0
0x180012d31  call    cs:__imp_GdipGetImageHeight
0x180012d37  test    eax, eax
0x180012d39  jz      short loc_180012D3E
0x180012d3b  mov     [rbx+10h], eax
0x180012d3e  mov     eax, [rsp+110h+var_E0]
0x180012d42  mov     [rsi+4], eax
0x180012d45  lea     rcx, [rbp+57h+var_D0]; this
0x180012d49  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180012d4e  lea     rcx, [rbp+57h+var_C8]; this
0x180012d52  call    ??1Effect@Gdiplus@@UEAA@XZ; Gdiplus::Effect::~Effect(void)
0x180012d57  mov     eax, edi
0x180012d59  mov     rcx, [rbp+57h+var_30]
0x180012d5d  xor     rcx, rsp; StackCookie
0x180012d60  call    __security_check_cookie
0x180012d65  add     rsp, 0F0h
0x180012d6c  pop     r14
0x180012d6e  pop     rdi
0x180012d6f  pop     rsi
0x180012d70  pop     rbx
0x180012d71  pop     rbp
0x180012d72  retn
```
