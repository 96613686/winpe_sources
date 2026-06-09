# sub_18058ECDC

- ea: `0x18058ecdc`
- end: `0x18058f381`
- name: `sub_18058ECDC`
- size: `1701`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: ``

## callers

- `0x18058e740`
- `0x180592b90`

## callees

- `0x180159890`
- `0x18015a728`
- `0x1801c11c0`
- `0x18040acd8`
- `0x18040b75c`
- `0x180478188`
- `0x180478884`
- `0x18047a048`
- `0x18047abf4`
- `0x18047c0f8`
- `0x18047cf30`
- `0x18047d240`
- `0x18047d270`
- `0x180491e7c`
- `0x18058d7bc`
- `0x18058e0a4`
- `0x18058ecdc`
- `0x18058f9e0`
- `0x180591204`
- `0x1805913c8`
- `0x1805916ac`
- `0x18074be40`

## import_xrefs

- `gdiplus!GdipDeleteGraphics` at `0x18058f33c`
- `gdiplus!GdipDeleteGraphics` at `0x18058f33c`
- `gdiplus!GdipDeleteBrush` at `0x18058f250`
- `gdiplus!GdipDeleteBrush` at `0x18058f250`
- `gdiplus!GdipDeletePen` at `0x18058f2f8`
- `gdiplus!GdipDeletePen` at `0x18058f31b`
- `gdiplus!GdipDeletePen` at `0x18058f2f8`
- `gdiplus!GdipDeletePen` at `0x18058f31b`
- `gdiplus!GdipDeleteMatrix` at `0x18058f060`
- `gdiplus!GdipDeleteMatrix` at `0x18058f32b`
- `gdiplus!GdipDeleteMatrix` at `0x18058f060`
- `gdiplus!GdipDeleteMatrix` at `0x18058f32b`
- `gdiplus!GdipCreateImageAttributes` at `0x18058efa2`
- `gdiplus!GdipCreateImageAttributes` at `0x18058efa2`
- `gdiplus!GdipDisposeImageAttributes` at `0x18058f30b`
- `gdiplus!GdipDisposeImageAttributes` at `0x18058f30b`
- `USER32!CopyRect` at `0x18058ee3d`
- `USER32!CopyRect` at `0x18058ee3d`
- `USER32!OffsetRect` at `0x18058ee98`
- `USER32!OffsetRect` at `0x18058eeaf`
- `USER32!OffsetRect` at `0x18058eec6`
- `USER32!OffsetRect` at `0x18058ee98`
- `USER32!OffsetRect` at `0x18058eeaf`
- `USER32!OffsetRect` at `0x18058eec6`
- `USER32!IsRectEmpty` at `0x18058ee6a`
- `USER32!IsRectEmpty` at `0x18058ee6a`

## pseudocode

```c
__int64 __fastcall sub_18058ECDC(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5, int a6, int a7)
{
  int v10; // esi
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // edx
  bool v17; // r12
  bool v18; // cl
  __int64 v19; // rdx
  float v20; // xmm6_4
  __int64 *v21; // rsi
  char v22; // r15
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // eax
  int v26; // ebx
  int v27; // eax
  int v28; // eax
  int v29; // ebx
  int v30; // eax
  void (__fastcall ***v31)(_QWORD, __int64); // rdi
  int v32; // eax
  int v33; // ebx
  int v34; // eax
  unsigned int v35; // ebx
  void (__fastcall ***v37)(_QWORD, __int64); // [rsp+68h] [rbp-A0h] BYREF
  int v38; // [rsp+70h] [rbp-98h]
  int v39; // [rsp+74h] [rbp-94h]
  int v40[4]; // [rsp+78h] [rbp-90h] BYREF
  float v41[2]; // [rsp+88h] [rbp-80h] BYREF
  int v42; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v43[3]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-58h] BYREF
  int v45; // [rsp+B8h] [rbp-50h]
  _QWORD v46[2]; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v47[2]; // [rsp+D0h] [rbp-38h] BYREF
  RECT rcSrc; // [rsp+E0h] [rbp-28h] BYREF
  struct tagRECT rcDst; // [rsp+F0h] [rbp-18h] BYREF
  RECT rc; // [rsp+100h] [rbp-8h] BYREF
  struct tagRECT v51; // [rsp+110h] [rbp+8h] BYREF
  struct tagRECT lprc; // [rsp+120h] [rbp+18h] BYREF
  _OWORD v53[4]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v54; // [rsp+178h] [rbp+70h]
  float v55; // [rsp+180h] [rbp+78h]
  int v56; // [rsp+184h] [rbp+7Ch]
  __int128 v57; // [rsp+188h] [rbp+80h]
  int v58; // [rsp+198h] [rbp+90h]

  if ( !a5 )
    return (unsigned int)-2147418113;
  v10 = 6;
  if ( a7 <= 6 )
    v10 = a7;
  if ( v10 > 0 && *(_DWORD *)(a3 + 8) && *(_DWORD *)(a3 + 12) )
  {
    *(_QWORD *)v40 = 0;
    v40[2] = (int)o_sqrt();
    v40[3] = (int)o_sqrt();
    lprc = 0;
    sub_1801C11C0(a5);
    v12 = v11;
    v13 = sub_18040B75C(a5);
    sub_1805913C8(a2, (int)v40, v13, v12, &lprc);
    v14 = *(_DWORD *)(a3 + 12);
    v15 = 0;
    v16 = 0;
    if ( lprc.right - lprc.left >= 0 )
      v15 = lprc.right - lprc.left;
    rcDst = 0;
    if ( lprc.bottom - lprc.top >= 0 )
      v16 = lprc.bottom - lprc.top;
    rcSrc.left = (unsigned int)(*(_DWORD *)(a3 + 8) - v15) >> 1;
    rcSrc.right = v15 + rcSrc.left;
    rcSrc.top = (unsigned int)(v14 - v16) >> 1;
    rcSrc.bottom = rcSrc.top + v16;
    rc = 0;
    v51 = 0;
    CopyRect(&rcDst, &rcSrc);
    sub_180591204(a2, &rc);
    v17 = 0;
    v18 = !IsRectEmpty(&rc);
    if ( v10 == 1 )
      v17 = v18;
    if ( v17 )
    {
      OffsetRect(&rcDst, rcSrc.left, rcSrc.top);
      OffsetRect(&v51, rcSrc.left, rcSrc.top);
      OffsetRect(&rc, rcSrc.left, rcSrc.top);
    }
    v19 = *(_QWORD *)(a4 + 8);
    LODWORD(v37) = *(_DWORD *)(a3 + 12);
    v41[0] = *(float *)(a3 + 8);
    v20 = fminf((float)((float)(a6 - v10 + 6) / 6.0) + 0.30000001, 1.0);
    sub_18040ACD8(v40, v19);
    sub_18047A048(v47);
    v42 = (unsigned __int8)(int)(float)(v20 * 255.0) << 24;
    sub_18058D7BC(v46, &v42);
    v53[1] = _mm_load_si128((const __m128i *)&xmmword_18087C5C0);
    v53[2] = 0;
    v57 = 0;
    v55 = v20;
    v53[0] = _mm_load_si128((const __m128i *)&xmmword_18087C580);
    v53[3] = v53[0];
    v54 = 0;
    v56 = 0;
    v58 = 1065353216;
    v44 = 0;
    v45 = GdipCreateImageAttributes(&v44);
    if ( a6 == v10 - 1 )
    {
      v21 = 0;
      v22 = 1;
    }
    else
    {
      v22 = 0;
      sub_18047A048(v43);
      v41[0] = (float)SLODWORD(v41[0]) * 0.5;
      v41[1] = (float)(int)v37 * 0.5;
      sub_18047C0F8(v43, v23, v41);
      sub_18047D270(v40, v43);
      sub_18047D240(v40, 4);
      sub_180491E7C(&v44, v53, v24, 0);
      v21 = &v44;
      GdipDeleteMatrix(v43[0]);
    }
    sub_18047CF30(v40, 2);
    if ( v17 )
    {
      LODWORD(v37) = -16777216;
      sub_180478188(v43, &v37);
      sub_180478884((unsigned int)v40, (unsigned int)v43, v51.left, v51.top, v51.right - v51.left, v51.bottom - v51.top);
      v37 = *(void (__fastcall ****)(_QWORD, __int64))&rcDst.left;
      v38 = rcDst.right - rcDst.left;
      v39 = rcDst.bottom - rcDst.top;
      sub_1801C11C0(a5);
      v29 = v28;
      v30 = sub_18040B75C(a5);
      sub_18047ABF4((unsigned int)v40, a5, (unsigned int)&v37, 0, 0, v30, v29);
      v37 = 0;
      v31 = 0;
      if ( (a2 & 0x8000) != 0 )
      {
        sub_1805916AC(L"sprockets_256.png", &v37);
        v31 = v37;
      }
      if ( (a2 & 0x20000) != 0 )
      {
        sub_1805916AC(L"jewelcase.png", &v37);
        v31 = v37;
      }
      if ( v31 )
      {
        v37 = *(void (__fastcall ****)(_QWORD, __int64))&rc.left;
        v38 = rc.right - rc.left;
        v39 = rc.bottom - rc.top;
        sub_1801C11C0(v31);
        v33 = v32;
        v34 = sub_18040B75C(v31);
        sub_18047ABF4((unsigned int)v40, (_DWORD)v31, (unsigned int)&v37, 0, 0, v34, v33);
        (**v31)(v31, 1);
      }
      GdipDeleteBrush(v43[1]);
    }
    else
    {
      if ( v22 )
        sub_18058F9E0(a2, v40, &rcSrc, v21);
      v37 = *(void (__fastcall ****)(_QWORD, __int64))&rcSrc.left;
      v38 = rcSrc.right - rcSrc.left;
      v39 = rcSrc.bottom - rcSrc.top;
      sub_1801C11C0(a5);
      v26 = v25;
      v27 = sub_18040B75C(a5);
      sub_18047ABF4((unsigned int)v40, a5, (unsigned int)&v37, 0, 0, v27, v26);
    }
    if ( v22 )
    {
      if ( !v17 && (a2 & 0x10000) != 0 )
      {
        LODWORD(v37) = 2130706432;
        sub_18058D7BC(v43, &v37);
        sub_18058E0A4(
          (unsigned int)v40,
          (unsigned int)v43,
          rcSrc.left,
          rcSrc.top,
          rcSrc.right - rcSrc.left,
          rcSrc.bottom - rcSrc.top);
        GdipDeletePen(v43[0]);
      }
    }
    else
    {
      if ( !v17 )
        sub_18058E0A4(
          (unsigned int)v40,
          (unsigned int)v46,
          rcSrc.left,
          rcSrc.top,
          rcSrc.right - rcSrc.left,
          rcSrc.bottom - rcSrc.top);
      sub_18047D270(v40, v47);
    }
    v35 = 0;
    GdipDisposeImageAttributes(v44);
    GdipDeletePen(v46[0]);
    GdipDeleteMatrix(v47[0]);
    GdipDeleteGraphics(*(_QWORD *)v40);
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v35;
}

```

## disassembly

```asm
0x18058ecdc  mov     rax, rsp
0x18058ecdf  mov     [rax+8], rbx
0x18058ece3  push    rbp
0x18058ece4  push    rsi
0x18058ece5  push    rdi
0x18058ece6  push    r12
0x18058ece8  push    r13
0x18058ecea  push    r14
0x18058ecec  push    r15
0x18058ecee  lea     rbp, [rax-0F8h]
0x18058ecf5  sub     rsp, 1C0h
0x18058ecfc  movaps  xmmword ptr [rax-48h], xmm6
0x18058ed00  mov     rax, cs:__security_cookie
0x18058ed07  xor     rax, rsp
0x18058ed0a  mov     [rbp+0F0h+var_50], rax
0x18058ed11  mov     rdi, [rbp+0F0h+arg_20]
0x18058ed18  mov     r13, r9
0x18058ed1b  mov     r15, r8
0x18058ed1e  mov     r14d, edx
0x18058ed21  test    rdi, rdi
0x18058ed24  jz      loc_18058F34A
0x18058ed2a  mov     esi, 6
0x18058ed2f  cmp     [rbp+0F0h+arg_30], esi
0x18058ed35  cmovle  esi, [rbp+0F0h+arg_30]
0x18058ed3c  test    esi, esi
0x18058ed3e  jle     loc_18058F34A
0x18058ed44  mov     eax, [r8+8]
0x18058ed48  test    eax, eax
0x18058ed4a  jz      loc_18058F34A
0x18058ed50  mov     ebx, [r8+0Ch]
0x18058ed54  test    ebx, ebx
0x18058ed56  jz      loc_18058F34A
0x18058ed5c  xorps   xmm0, xmm0
0x18058ed5f  imul    eax, eax
0x18058ed62  mov     qword ptr [rsp+1F0h+var_180], 0
0x18058ed6b  cvtsi2ss xmm0, rax
0x18058ed70  mulss   xmm0, cs:dword_18087BD80
0x18058ed78  cvtps2pd xmm0, xmm0
0x18058ed7b  call    _o_sqrt
0x18058ed80  cvttsd2si eax, xmm0
0x18058ed84  xorps   xmm0, xmm0
0x18058ed87  imul    ebx, ebx
0x18058ed8a  mov     [rsp+1F0h+var_178], eax
0x18058ed8e  mov     eax, ebx
0x18058ed90  cvtsi2ss xmm0, rax
0x18058ed95  mulss   xmm0, cs:dword_18087BD80
0x18058ed9d  cvtps2pd xmm0, xmm0
0x18058eda0  call    _o_sqrt
0x18058eda5  cvttsd2si eax, xmm0
0x18058eda9  mov     rcx, rdi
0x18058edac  xorps   xmm1, xmm1
0x18058edaf  mov     [rsp+1F0h+var_174], eax
0x18058edb3  movups  xmmword ptr [rbp+0F0h+var_D8.left], xmm1
0x18058edb7  call    sub_1801C11C0
0x18058edbc  mov     rcx, rdi
0x18058edbf  mov     ebx, eax
0x18058edc1  call    sub_18040B75C
0x18058edc6  lea     rcx, [rbp+0F0h+var_D8]
0x18058edca  mov     r9d, ebx; int
0x18058edcd  mov     [rsp+1F0h+lprc], rcx; lprc
0x18058edd2  lea     rdx, [rsp+1F0h+var_180]; int
0x18058edd7  mov     ecx, r14d; int
0x18058edda  mov     r8d, eax; int
0x18058eddd  call    sub_1805913C8
0x18058ede2  mov     ecx, [r15+0Ch]
0x18058ede6  xorps   xmm0, xmm0
0x18058ede9  mov     eax, [rbp+0F0h+var_D8.right]
0x18058edec  mov     r8d, 0
0x18058edf2  sub     eax, [rbp+0F0h+var_D8.left]
0x18058edf5  mov     edx, 0
0x18058edfa  xorps   xmm1, xmm1
0x18058edfd  cmovns  r8d, eax
0x18058ee01  mov     eax, [rbp+0F0h+var_D8.bottom]
0x18058ee04  sub     eax, [rbp+0F0h+var_D8.top]
0x18058ee07  movups  xmmword ptr [rbp+0F0h+rcDst.left], xmm0
0x18058ee0b  cmovns  edx, eax
0x18058ee0e  mov     eax, [r15+8]
0x18058ee12  sub     eax, r8d
0x18058ee15  sub     ecx, edx
0x18058ee17  shr     eax, 1
0x18058ee19  shr     ecx, 1
0x18058ee1b  mov     [rbp+0F0h+rcSrc.left], eax
0x18058ee1e  add     eax, r8d
0x18058ee21  mov     [rbp+0F0h+rcSrc.right], eax
0x18058ee24  mov     [rbp+0F0h+rcSrc.top], ecx
0x18058ee27  lea     eax, [rcx+rdx]
0x18058ee2a  lea     rdx, [rbp+0F0h+rcSrc]; lprcSrc
0x18058ee2e  mov     [rbp+0F0h+rcSrc.bottom], eax
0x18058ee31  lea     rcx, [rbp+0F0h+rcDst]; lprcDst
0x18058ee35  movups  xmmword ptr [rbp+0F0h+rc.left], xmm1
0x18058ee39  movups  xmmword ptr [rbp+0F0h+var_E8.left], xmm0
0x18058ee3d  call    cs:CopyRect
0x18058ee44  nop     dword ptr [rax+rax+00h]
0x18058ee49  lea     rax, [rbp+0F0h+rc]
0x18058ee4d  mov     ecx, r14d; int
0x18058ee50  lea     r9, [rbp+0F0h+var_E8]
0x18058ee54  mov     [rsp+1F0h+lprc], rax; LPRECT
0x18058ee59  lea     r8, [rbp+0F0h+rcDst]
0x18058ee5d  lea     rdx, [rbp+0F0h+rcSrc]
0x18058ee61  call    sub_180591204
0x18058ee66  lea     rcx, [rbp+0F0h+rc]; lprc
0x18058ee6a  call    cs:IsRectEmpty
0x18058ee71  nop     dword ptr [rax+rax+00h]
0x18058ee76  test    eax, eax
0x18058ee78  setz    al
0x18058ee7b  xor     r12d, r12d
0x18058ee7e  cmp     esi, 1
0x18058ee81  movzx   ecx, al
0x18058ee84  cmovz   r12d, ecx
0x18058ee88  test    r12b, r12b
0x18058ee8b  jz      short loc_18058EED2
0x18058ee8d  mov     r8d, [rbp+0F0h+rcSrc.top]; dy
0x18058ee91  lea     rcx, [rbp+0F0h+rcDst]; lprc
0x18058ee95  mov     edx, [rbp+0F0h+rcSrc.left]; dx
0x18058ee98  call    cs:OffsetRect
0x18058ee9f  nop     dword ptr [rax+rax+00h]
0x18058eea4  mov     r8d, [rbp+0F0h+rcSrc.top]; dy
0x18058eea8  lea     rcx, [rbp+0F0h+var_E8]; lprc
0x18058eeac  mov     edx, [rbp+0F0h+rcSrc.left]; dx
0x18058eeaf  call    cs:OffsetRect
0x18058eeb6  nop     dword ptr [rax+rax+00h]
0x18058eebb  mov     r8d, [rbp+0F0h+rcSrc.top]; dy
0x18058eebf  lea     rcx, [rbp+0F0h+rc]; lprc
0x18058eec3  mov     edx, [rbp+0F0h+rcSrc.left]; dx
0x18058eec6  call    cs:OffsetRect
0x18058eecd  nop     dword ptr [rax+rax+00h]
0x18058eed2  mov     eax, [r15+0Ch]
0x18058eed6  lea     rcx, [rsp+1F0h+var_180]
0x18058eedb  mov     ebx, [rbp+0F0h+arg_28]
0x18058eee1  mov     rdx, [r13+8]
0x18058eee5  sub     ebx, esi
0x18058eee7  add     ebx, 6
0x18058eeea  mov     [rsp+1F0h+var_190], eax
0x18058eeee  mov     eax, [r15+8]
0x18058eef2  mov     [rbp+0F0h+var_170], eax
0x18058eef5  movd    xmm6, ebx
0x18058eef9  cvtdq2ps xmm6, xmm6
0x18058eefc  divss   xmm6, cs:dword_18087C04C
0x18058ef04  addss   xmm6, cs:dword_18087BD64
0x18058ef0c  minss   xmm6, cs:dword_180803798
0x18058ef14  call    sub_18040ACD8
0x18058ef19  lea     rcx, [rbp+0F0h+var_128]
0x18058ef1d  call    sub_18047A048
0x18058ef22  movss   xmm2, cs:dword_180803798
0x18058ef2a  lea     rdx, [rbp+0F0h+var_168]
0x18058ef2e  movaps  xmm0, xmm6
0x18058ef31  mulss   xmm0, cs:dword_18087C0FC
0x18058ef39  cvttss2si eax, xmm0
0x18058ef3d  movzx   ecx, al
0x18058ef40  shl     ecx, 18h
0x18058ef43  mov     [rbp+0F0h+var_168], ecx
0x18058ef46  lea     rcx, [rbp+0F0h+var_138]
0x18058ef4a  call    sub_18058D7BC
0x18058ef4f  movdqa  xmm0, cs:xmmword_18087C5C0
0x18058ef57  lea     rcx, [rbp+0F0h+var_148]
0x18058ef5b  movdqa  xmm1, cs:xmmword_18087C580
0x18058ef63  xor     r13d, r13d
0x18058ef66  movaps  [rbp+0F0h+var_B0], xmm0
0x18058ef6a  xorps   xmm0, xmm0
0x18058ef6d  movaps  [rbp+0F0h+var_A0], xmm0
0x18058ef71  movaps  [rbp+0F0h+var_70], xmm0
0x18058ef78  movss   [rbp+0F0h+var_78], xmm6
0x18058ef7d  movaps  [rbp+0F0h+var_C0], xmm1
0x18058ef81  movaps  [rbp+0F0h+var_90], xmm1
0x18058ef85  mov     [rbp+0F0h+var_80], 0
0x18058ef8d  mov     [rbp+0F0h+var_74], 0
0x18058ef94  mov     [rbp+0F0h+var_60], 3F800000h
0x18058ef9e  mov     [rbp+0F0h+var_148], r13
0x18058efa2  call    cs:GdipCreateImageAttributes
0x18058efa9  nop     dword ptr [rax+rax+00h]
0x18058efae  mov     [rbp+0F0h+var_140], eax
0x18058efb1  lea     eax, [rsi-1]
0x18058efb4  cmp     [rbp+0F0h+arg_28], eax
0x18058efba  jnz     short loc_18058EFC7
0x18058efbc  mov     esi, r13d
0x18058efbf  mov     r15b, 1
0x18058efc2  jmp     loc_18058F06C
0x18058efc7  lea     rcx, [rbp+0F0h+var_160]
0x18058efcb  mov     r15b, r13b
0x18058efce  call    sub_18047A048
0x18058efd3  mov     eax, [rbp+0F0h+var_170]
0x18058efd6  lea     r8, [rbp+0F0h+var_170]
0x18058efda  xorps   xmm1, xmm1
0x18058efdd  lea     rcx, [rbp+0F0h+var_160]
0x18058efe1  xorps   xmm0, xmm0
0x18058efe4  cvtsi2ss xmm0, rax
0x18058efe9  mov     eax, [rsp+1F0h+var_190]
0x18058efed  cvtsi2ss xmm1, rax
0x18058eff2  lea     eax, [rbx+1]
0x18058eff5  mulss   xmm0, cs:dword_18087BD80
0x18058effd  mulss   xmm1, cs:dword_18087BD80
0x18058f005  movss   [rbp+0F0h+var_170], xmm0
0x18058f00a  movss   [rbp+0F0h+var_16C], xmm1
0x18058f00f  movd    xmm1, eax
0x18058f013  cvtdq2ps xmm1, xmm1
0x18058f016  mulss   xmm1, cs:dword_18087C0D0
0x18058f01e  subss   xmm1, cs:dword_18087C0EC
0x18058f026  call    sub_18047C0F8
0x18058f02b  lea     rdx, [rbp+0F0h+var_160]
0x18058f02f  lea     rcx, [rsp+1F0h+var_180]
0x18058f034  call    sub_18047D270
0x18058f039  mov     edx, 4
0x18058f03e  lea     rcx, [rsp+1F0h+var_180]
0x18058f043  call    sub_18047D240
0x18058f048  xor     r9d, r9d
0x18058f04b  lea     rdx, [rbp+0F0h+var_C0]
0x18058f04f  lea     rcx, [rbp+0F0h+var_148]
0x18058f053  call    sub_180491E7C
0x18058f058  mov     rcx, [rbp+0F0h+var_160]
0x18058f05c  lea     rsi, [rbp+0F0h+var_148]
0x18058f060  call    cs:GdipDeleteMatrix
0x18058f067  nop     dword ptr [rax+rax+00h]
0x18058f06c  mov     edx, 2
0x18058f071  lea     rcx, [rsp+1F0h+var_180]
0x18058f076  call    sub_18047CF30
0x18058f07b  test    r12b, r12b
0x18058f07e  jnz     short loc_18058F0FA
0x18058f080  test    r15b, r15b
0x18058f083  jz      short loc_18058F099
0x18058f085  mov     r9, rsi
0x18058f088  lea     r8, [rbp+0F0h+rcSrc]
0x18058f08c  lea     rdx, [rsp+1F0h+var_180]
0x18058f091  mov     ecx, r14d
0x18058f094  call    sub_18058F9E0
0x18058f099  mov     ecx, [rbp+0F0h+rcSrc.left]
0x18058f09c  mov     r8d, [rbp+0F0h+rcSrc.top]
0x18058f0a0  mov     eax, [rbp+0F0h+rcSrc.right]
0x18058f0a3  sub     eax, ecx
0x18058f0a5  mov     [rsp+1F0h+var_190], ecx
0x18058f0a9  mov     dword ptr [rsp+1F0h+var_188], eax
0x18058f0ad  mov     rcx, rdi
0x18058f0b0  mov     eax, [rbp+0F0h+rcSrc.bottom]
0x18058f0b3  sub     eax, r8d
0x18058f0b6  mov     [rsp+1F0h+var_18C], r8d
0x18058f0bb  mov     dword ptr [rsp+1F0h+var_188+4], eax
0x18058f0bf  call    sub_1801C11C0
0x18058f0c4  mov     rcx, rdi
0x18058f0c7  mov     ebx, eax
0x18058f0c9  call    sub_18040B75C
0x18058f0ce  mov     [rsp+1F0h+var_1B0], rsi
0x18058f0d3  lea     r8, [rsp+1F0h+var_190]
0x18058f0d8  mov     [rsp+1F0h+var_1C0], ebx
0x18058f0dc  lea     rcx, [rsp+1F0h+var_180]
0x18058f0e1  mov     [rsp+1F0h+var_1C8], eax
0x18058f0e5  xor     r9d, r9d
0x18058f0e8  mov     rdx, rdi
0x18058f0eb  mov     dword ptr [rsp+1F0h+lprc], r13d
0x18058f0f0  call    sub_18047ABF4
0x18058f0f5  jmp     loc_18058F25C
0x18058f0fa  lea     rdx, [rsp+1F0h+var_190]
0x18058f0ff  mov     [rsp+1F0h+var_190], 0FF000000h
0x18058f107  lea     rcx, [rbp+0F0h+var_160]
0x18058f10b  call    sub_180478188
0x18058f110  mov     ecx, [rbp+0F0h+var_E8.bottom]
0x18058f113  lea     rdx, [rbp+0F0h+var_160]
0x18058f117  mov     r9d, [rbp+0F0h+var_E8.top]
0x18058f11b  sub     ecx, r9d
0x18058f11e  mov     eax, [rbp+0F0h+var_E8.right]
0x18058f121  mov     r8d, [rbp+0F0h+var_E8.left]
0x18058f125  sub     eax, r8d
0x18058f128  mov     [rsp+1F0h+var_1C8], ecx
0x18058f12c  lea     rcx, [rsp+1F0h+var_180]
0x18058f131  mov     dword ptr [rsp+1F0h+lprc], eax
0x18058f135  call    sub_180478884
0x18058f13a  mov     ecx, [rbp+0F0h+rcDst.left]
0x18058f13d  mov     edx, [rbp+0F0h+rcDst.top]
0x18058f140  mov     eax, [rbp+0F0h+rcDst.right]
0x18058f143  sub     eax, ecx
0x18058f145  mov     [rsp+1F0h+var_190], ecx
0x18058f149  mov     dword ptr [rsp+1F0h+var_188], eax
0x18058f14d  mov     rcx, rdi
0x18058f150  mov     eax, [rbp+0F0h+rcDst.bottom]
0x18058f153  sub     eax, edx
0x18058f155  mov     [rsp+1F0h+var_18C], edx
0x18058f159  mov     dword ptr [rsp+1F0h+var_188+4], eax
0x18058f15d  call    sub_1801C11C0
0x18058f162  mov     rcx, rdi
0x18058f165  mov     ebx, eax
0x18058f167  call    sub_18040B75C
0x18058f16c  mov     [rsp+1F0h+var_1B0], rsi
0x18058f171  lea     r8, [rsp+1F0h+var_190]
0x18058f176  mov     [rsp+1F0h+var_1C0], ebx
0x18058f17a  lea     rcx, [rsp+1F0h+var_180]
0x18058f17f  mov     [rsp+1F0h+var_1C8], eax
0x18058f183  xor     r9d, r9d
0x18058f186  mov     rdx, rdi
0x18058f189  mov     dword ptr [rsp+1F0h+lprc], r13d
0x18058f18e  call    sub_18047ABF4
0x18058f193  mov     qword ptr [rsp+1F0h+var_190], r13
0x18058f198  mov     rdi, r13
0x18058f19b  bt      r14d, 0Fh
0x18058f1a0  jnb     short loc_18058F1B8
0x18058f1a2  lea     rdx, [rsp+1F0h+var_190]
0x18058f1a7  lea     rcx, aSprockets256Pn; "sprockets_256.png"
0x18058f1ae  call    sub_1805916AC
0x18058f1b3  mov     rdi, qword ptr [rsp+1F0h+var_190]
0x18058f1b8  bt      r14d, 11h
0x18058f1bd  jnb     short loc_18058F1D5
0x18058f1bf  lea     rdx, [rsp+1F0h+var_190]
0x18058f1c4  lea     rcx, aJewelcasePng; "jewelcase.png"
  ... truncated ...
```
