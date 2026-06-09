# HSBSlider::CustomDrawChannel(tagNMCUSTOMDRAWINFO *)

- ea: `0x18000f10c`
- end: `0x18000f4e1`
- name: `?CustomDrawChannel@HSBSlider@@QEAAJPEAUtagNMCUSTOMDRAWINFO@@@Z`
- size: `981`
- prototype: `__int64 __fastcall(HSBSlider *__hidden this, struct tagNMCUSTOMDRAWINFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f580`

## callees

- `0x18000f10c`
- `0x18004fb5c`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x18000f1e5`
- `GDI32!CreateDIBSection` at `0x18000f1e5`
- `GDI32!SelectObject` at `0x18000f18e`
- `GDI32!SelectObject` at `0x18000f203`
- `GDI32!SelectObject` at `0x18000f18e`
- `GDI32!SelectObject` at `0x18000f203`
- `GDI32!BitBlt` at `0x18000f4a3`
- `GDI32!BitBlt` at `0x18000f4a3`
- `GDI32!DeleteObject` at `0x18000f19d`
- `GDI32!DeleteObject` at `0x18000f21e`
- `GDI32!DeleteObject` at `0x18000f19d`
- `GDI32!DeleteObject` at `0x18000f21e`

## pseudocode

```c
__int64 __fastcall HSBSlider::CustomDrawChannel(HSBSlider *this, struct tagNMCUSTOMDRAWINFO *a2)
{
  const BITMAPINFO *v2; // r12
  int *v3; // r14
  int v4; // edi
  int v7; // esi
  void *v8; // rdx
  void **v9; // r15
  HGDIOBJ v10; // rax
  HDC v11; // rcx
  HBITMAP DIBSection; // rax
  HBITMAP v13; // r12
  HGDIOBJ v14; // rax
  int v15; // eax
  unsigned int v16; // r15d
  int v17; // r14d
  __m128i si128; // xmm7
  CColorizationColor *v19; // rax
  int v20; // edx
  int v21; // r8d
  int v22; // eax
  CColorizationColor *v23; // rax
  int v24; // r8d
  double v25; // xmm3_8
  int v26; // ecx
  double v27; // xmm2_8
  double v28; // xmm1_8
  int i; // r9d
  int j; // edx
  int v31; // eax
  double v33; // [rsp+50h] [rbp-68h] BYREF
  __m128i v34; // [rsp+58h] [rbp-60h]
  char v35; // [rsp+C0h] [rbp+8h] BYREF

  v2 = (const BITMAPINFO *)((char *)this + 352);
  v3 = (int *)((char *)this + 360);
  v4 = ~a2->rc.left + a2->rc.right;
  if ( v4 < 1 )
    v4 = 1;
  v7 = a2->rc.bottom - a2->rc.top;
  if ( v7 < 1 )
    v7 = 1;
  if ( v4 != *((_DWORD *)this + 89) || v7 != *v3 )
  {
    v8 = (void *)*((_QWORD *)this + 52);
    v9 = (void **)((char *)this + 400);
    if ( v8 )
    {
      v10 = SelectObject(*((HDC *)this + 51), v8);
      DeleteObject(v10);
      *((_QWORD *)this + 52) = 0;
      *v9 = 0;
    }
    v11 = (HDC)*((_QWORD *)this + 51);
    *((_DWORD *)this + 89) = v4;
    *v3 = v7;
    DIBSection = CreateDIBSection(v11, v2, 0, v9, 0, 0);
    v13 = DIBSection;
    if ( DIBSection )
    {
      v14 = SelectObject(*((HDC *)this + 51), DIBSection);
      *((_QWORD *)this + 52) = v14;
      if ( !v14 )
      {
        DeleteObject(v13);
        *v9 = 0;
        *v3 = 0;
        *((_DWORD *)this + 89) = 0;
      }
    }
  }
  if ( *((_QWORD *)this + 50) )
  {
    v15 = *((_DWORD *)this + 106);
    v16 = 0;
    if ( v15 == -1 )
    {
      v17 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v34 = si128;
        v33 = (double)(360 * v17 / v4);
        v19 = CColorizationColor::CColorizationColor((CColorizationColor *)&v35, 0.0, (const struct CHSBColor *)&v33);
        v20 = 0;
        v21 = (unsigned __int8)(int)((double)(unsigned __int8)*(_DWORD *)v19 / 255.0 * 255.0)
            | ((unsigned __int8)(int)((double)(unsigned __int8)BYTE2(*(_DWORD *)v19) / 255.0 * 255.0) << 16)
            | ((unsigned __int8)(int)((double)(unsigned __int8)BYTE1(*(_DWORD *)v19) / 255.0 * 255.0) << 8);
        do
        {
          v22 = v20++;
          *(_DWORD *)(*((_QWORD *)this + 50) + 4LL * (v17 + v4 * v22)) = v21;
        }
        while ( v20 < v7 );
        ++v17;
      }
      while ( v17 < v4 );
    }
    else
    {
      v34 = _mm_load_si128((const __m128i *)&_xmm);
      v33 = (double)v15;
      v23 = CColorizationColor::CColorizationColor((CColorizationColor *)&v35, 0.0, (const struct CHSBColor *)&v33);
      v24 = 255;
      v25 = (double)(unsigned __int8)BYTE2(*(_DWORD *)v23) / 255.0;
      v26 = *((_DWORD *)this + 107);
      v27 = (double)(unsigned __int8)BYTE1(*(_DWORD *)v23) / 255.0;
      v28 = (double)(unsigned __int8)*(_DWORD *)v23 / 255.0;
      if ( v26 <= 255 )
      {
        v24 = *((_DWORD *)this + 107);
        if ( v26 < 0 )
          v24 = 0;
      }
      for ( i = 0; i < v4; ++i )
      {
        for ( j = 0; j < v7; ++j )
        {
          v31 = j;
          *(_DWORD *)(*((_QWORD *)this + 50) + 4LL * (i + v4 * v31)) = (unsigned __int8)(v24
                                                                                       + ((unsigned __int8)(int)(v28 * 255.0)
                                                                                        - v24)
                                                                                       * i
                                                                                       / v4)
                                                                     | ((unsigned __int8)(v24
                                                                                        + ((unsigned __int8)(int)(v25 * 255.0)
                                                                                         - v24)
                                                                                        * i
                                                                                        / v4) << 16)
                                                                     | ((unsigned __int8)(v24
                                                                                        + ((unsigned __int8)(int)(v27 * 255.0)
                                                                                         - v24)
                                                                                        * i
                                                                                        / v4) << 8);
        }
      }
    }
    BitBlt(a2->hdc, a2->rc.left, a2->rc.top, v4, v7, *((HDC *)this + 51), 0, 0, 0xCC0020u);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v16;
}

```

## disassembly

```asm
0x18000f10c  mov     rax, rsp
0x18000f10f  mov     [rax+10h], rbx
0x18000f113  mov     [rax+18h], rbp
0x18000f117  push    rsi
0x18000f118  push    rdi
0x18000f119  push    r12
0x18000f11b  push    r14
0x18000f11d  push    r15
0x18000f11f  sub     rsp, 90h
0x18000f126  mov     r8d, [rdx+28h]
0x18000f12a  lea     r12, [rcx+160h]
0x18000f131  mov     edi, [rdx+30h]
0x18000f134  lea     r14, [rcx+168h]
0x18000f13b  mov     esi, [rdx+34h]
0x18000f13e  not     r8d
0x18000f141  add     edi, r8d
0x18000f144  movaps  xmmword ptr [rax-38h], xmm6
0x18000f148  movaps  xmmword ptr [rax-48h], xmm7
0x18000f14c  mov     rbp, rdx
0x18000f14f  mov     eax, 1
0x18000f154  mov     rbx, rcx
0x18000f157  cmp     edi, eax
0x18000f159  cmovl   edi, eax
0x18000f15c  sub     esi, [rdx+2Ch]
0x18000f15f  cmp     esi, eax
0x18000f161  cmovl   esi, eax
0x18000f164  cmp     edi, [r12+4]
0x18000f169  jnz     short loc_18000F174
0x18000f16b  cmp     esi, [r14]
0x18000f16e  jz      loc_18000F242
0x18000f174  mov     rdx, [rcx+1A0h]; h
0x18000f17b  lea     r15, [rcx+190h]
0x18000f182  test    rdx, rdx
0x18000f185  jz      short loc_18000F1BB
0x18000f187  mov     rcx, [rcx+198h]; hdc
0x18000f18e  call    cs:__imp_SelectObject
0x18000f195  nop     dword ptr [rax+rax+00h]
0x18000f19a  mov     rcx, rax; ho
0x18000f19d  call    cs:__imp_DeleteObject
0x18000f1a4  nop     dword ptr [rax+rax+00h]
0x18000f1a9  mov     qword ptr [rbx+1A0h], 0
0x18000f1b4  mov     qword ptr [r15], 0
0x18000f1bb  mov     rcx, [rbx+198h]; hdc
0x18000f1c2  mov     r9, r15; ppvBits
0x18000f1c5  mov     [rsp+0B8h+offset], 0; offset
0x18000f1cd  xor     r8d, r8d; usage
0x18000f1d0  mov     rdx, r12; pbmi
0x18000f1d3  mov     [rsp+0B8h+hSection], 0; hSection
0x18000f1dc  mov     [rbx+164h], edi
0x18000f1e2  mov     [r14], esi
0x18000f1e5  call    cs:__imp_CreateDIBSection
0x18000f1ec  nop     dword ptr [rax+rax+00h]
0x18000f1f1  mov     r12, rax
0x18000f1f4  test    rax, rax
0x18000f1f7  jz      short loc_18000F242
0x18000f1f9  mov     rcx, [rbx+198h]; hdc
0x18000f200  mov     rdx, rax; h
0x18000f203  call    cs:__imp_SelectObject
0x18000f20a  nop     dword ptr [rax+rax+00h]
0x18000f20f  mov     [rbx+1A0h], rax
0x18000f216  test    rax, rax
0x18000f219  jnz     short loc_18000F242
0x18000f21b  mov     rcx, r12; ho
0x18000f21e  call    cs:__imp_DeleteObject
0x18000f225  nop     dword ptr [rax+rax+00h]
0x18000f22a  mov     qword ptr [r15], 0
0x18000f231  mov     dword ptr [r14], 0
0x18000f238  mov     dword ptr [rbx+164h], 0
0x18000f242  cmp     qword ptr [rbx+190h], 0
0x18000f24a  jz      loc_18000F4B1
0x18000f250  mov     eax, [rbx+1A8h]
0x18000f256  xor     r15d, r15d
0x18000f259  cmp     eax, 0FFFFFFFFh
0x18000f25c  jnz     loc_18000F34A
0x18000f262  xor     r14d, r14d
0x18000f265  test    edi, edi
0x18000f267  jz      loc_18000F473
0x18000f26d  movdqa  xmm7, cs:__xmm@3ff00000000000003ff0000000000000
0x18000f275  movsd   xmm6, cs:__real@406fe00000000000
0x18000f27d  imul    eax, r14d, 168h
0x18000f284  lea     r8, [rsp+0B8h+var_68]; struct CHSBColor *
0x18000f289  xorps   xmm1, xmm1; double
0x18000f28c  lea     rcx, [rsp+0B8h+arg_0]; this
0x18000f294  movups  [rsp+0B8h+var_60], xmm7
0x18000f299  cdq
0x18000f29a  idiv    edi
0x18000f29c  movd    xmm0, eax
0x18000f2a0  cvtdq2pd xmm0, xmm0
0x18000f2a4  movsd   [rsp+0B8h+var_68], xmm0
0x18000f2aa  call    ??0CColorizationColor@@QEAA@NAEBVCHSBColor@@@Z; CColorizationColor::CColorizationColor(double,CHSBColor const &)
0x18000f2af  xorps   xmm0, xmm0
0x18000f2b2  mov     edx, [rax]
0x18000f2b4  mov     eax, edx
0x18000f2b6  shr     eax, 8
0x18000f2b9  movzx   eax, al
0x18000f2bc  cvtsi2sd xmm0, rax
0x18000f2c1  divsd   xmm0, xmm6
0x18000f2c5  mulsd   xmm0, xmm6
0x18000f2c9  cvttsd2si eax, xmm0
0x18000f2cd  xorps   xmm0, xmm0
0x18000f2d0  movzx   r8d, al
0x18000f2d4  mov     eax, edx
0x18000f2d6  shr     eax, 10h
0x18000f2d9  movzx   eax, al
0x18000f2dc  shl     r8d, 8
0x18000f2e0  cvtsi2sd xmm0, rax
0x18000f2e5  divsd   xmm0, xmm6
0x18000f2e9  mulsd   xmm0, xmm6
0x18000f2ed  cvttsd2si eax, xmm0
0x18000f2f1  xorps   xmm0, xmm0
0x18000f2f4  movzx   ecx, al
0x18000f2f7  movzx   eax, dl
0x18000f2fa  xor     edx, edx
0x18000f2fc  shl     ecx, 10h
0x18000f2ff  or      r8d, ecx
0x18000f302  cvtsi2sd xmm0, rax
0x18000f307  divsd   xmm0, xmm6
0x18000f30b  mulsd   xmm0, xmm6
0x18000f30f  cvttsd2si eax, xmm0
0x18000f313  movzx   ecx, al
0x18000f316  or      r8d, ecx
0x18000f319  test    esi, esi
0x18000f31b  jz      short loc_18000F339
0x18000f31d  mov     eax, edx
0x18000f31f  inc     edx
0x18000f321  imul    eax, edi
0x18000f324  add     eax, r14d
0x18000f327  movsxd  rcx, eax
0x18000f32a  mov     rax, [rbx+190h]
0x18000f331  mov     [rax+rcx*4], r8d
0x18000f335  cmp     edx, esi
0x18000f337  jl      short loc_18000F31D
0x18000f339  inc     r14d
0x18000f33c  cmp     r14d, edi
0x18000f33f  jl      loc_18000F27D
0x18000f345  jmp     loc_18000F473
0x18000f34a  movdqa  xmm1, cs:__xmm@3ff00000000000003ff0000000000000
0x18000f352  lea     r8, [rsp+0B8h+var_68]; struct CHSBColor *
0x18000f357  movd    xmm0, eax
0x18000f35b  lea     rcx, [rsp+0B8h+arg_0]; this
0x18000f363  cvtdq2pd xmm0, xmm0
0x18000f367  movups  [rsp+0B8h+var_60], xmm1
0x18000f36c  xorps   xmm1, xmm1; double
0x18000f36f  movsd   [rsp+0B8h+var_68], xmm0
0x18000f375  call    ??0CColorizationColor@@QEAA@NAEBVCHSBColor@@@Z; CColorizationColor::CColorizationColor(double,CHSBColor const &)
0x18000f37a  movsd   xmm0, cs:__real@406fe00000000000
0x18000f382  xorps   xmm3, xmm3
0x18000f385  xorps   xmm2, xmm2
0x18000f388  xorps   xmm1, xmm1
0x18000f38b  mov     r8d, 0FFh
0x18000f391  mov     ecx, [rax]
0x18000f393  mov     eax, ecx
0x18000f395  shr     eax, 10h
0x18000f398  movzx   eax, al
0x18000f39b  cvtsi2sd xmm3, rax
0x18000f3a0  mov     eax, ecx
0x18000f3a2  shr     eax, 8
0x18000f3a5  movzx   eax, al
0x18000f3a8  divsd   xmm3, xmm0
0x18000f3ac  cvtsi2sd xmm2, rax
0x18000f3b1  movzx   eax, cl
0x18000f3b4  mov     ecx, [rbx+1ACh]
0x18000f3ba  cvtsi2sd xmm1, rax
0x18000f3bf  divsd   xmm2, xmm0
0x18000f3c3  divsd   xmm1, xmm0
0x18000f3c7  cmp     ecx, r8d
0x18000f3ca  jg      short loc_18000F3D7
0x18000f3cc  xor     eax, eax
0x18000f3ce  mov     r8d, ecx
0x18000f3d1  test    ecx, ecx
0x18000f3d3  cmovs   r8d, eax
0x18000f3d7  mulsd   xmm1, xmm0
0x18000f3db  xor     r9d, r9d
0x18000f3de  mulsd   xmm2, xmm0
0x18000f3e2  mulsd   xmm3, xmm0
0x18000f3e6  cvttsd2si eax, xmm1
0x18000f3ea  movzx   r11d, al
0x18000f3ee  cvttsd2si eax, xmm2
0x18000f3f2  sub     r11d, r8d
0x18000f3f5  movzx   r14d, al
0x18000f3f9  cvttsd2si eax, xmm3
0x18000f3fd  sub     r14d, r8d
0x18000f400  movzx   r12d, al
0x18000f404  sub     r12d, r8d
0x18000f407  test    edi, edi
0x18000f409  jz      short loc_18000F473
0x18000f40b  mov     eax, r9d
0x18000f40e  imul    eax, r14d
0x18000f412  cdq
0x18000f413  idiv    edi
0x18000f415  add     al, r8b
0x18000f418  movzx   r10d, al
0x18000f41c  mov     eax, r9d
0x18000f41f  imul    eax, r12d
0x18000f423  shl     r10d, 8
0x18000f427  cdq
0x18000f428  idiv    edi
0x18000f42a  add     al, r8b
0x18000f42d  movzx   ecx, al
0x18000f430  mov     eax, r9d
0x18000f433  imul    eax, r11d
0x18000f437  shl     ecx, 10h
0x18000f43a  or      r10d, ecx
0x18000f43d  cdq
0x18000f43e  idiv    edi
0x18000f440  xor     edx, edx
0x18000f442  add     al, r8b
0x18000f445  movzx   ecx, al
0x18000f448  or      r10d, ecx
0x18000f44b  test    esi, esi
0x18000f44d  jz      short loc_18000F46B
0x18000f44f  mov     eax, edx
0x18000f451  inc     edx
0x18000f453  imul    eax, edi
0x18000f456  add     eax, r9d
0x18000f459  movsxd  rcx, eax
0x18000f45c  mov     rax, [rbx+190h]
0x18000f463  mov     [rax+rcx*4], r10d
0x18000f467  cmp     edx, esi
0x18000f469  jl      short loc_18000F44F
0x18000f46b  inc     r9d
0x18000f46e  cmp     r9d, edi
0x18000f471  jl      short loc_18000F40B
0x18000f473  mov     rax, [rbx+198h]
0x18000f47a  mov     r9d, edi; cx
0x18000f47d  mov     r8d, [rbp+2Ch]; y
0x18000f481  mov     edx, [rbp+28h]; x
0x18000f484  mov     rcx, [rbp+20h]; hdc
0x18000f488  mov     [rsp+0B8h+rop], 0CC0020h; rop
0x18000f490  mov     [rsp+0B8h+y1], r15d; y1
0x18000f495  mov     [rsp+0B8h+x1], r15d; x1
0x18000f49a  mov     qword ptr [rsp+0B8h+offset], rax; hdcSrc
0x18000f49f  mov     dword ptr [rsp+0B8h+hSection], esi; cy
0x18000f4a3  call    cs:__imp_BitBlt
0x18000f4aa  nop     dword ptr [rax+rax+00h]
0x18000f4af  jmp     short loc_18000F4B7
0x18000f4b1  mov     r15d, 8007000Eh
0x18000f4b7  movaps  xmm7, [rsp+0B8h+var_48]
0x18000f4bc  lea     r11, [rsp+0B8h+var_28]
0x18000f4c4  mov     rbx, [r11+38h]
0x18000f4c8  mov     eax, r15d
0x18000f4cb  mov     rbp, [r11+40h]
0x18000f4cf  movaps  xmm6, xmmword ptr [r11-10h]
0x18000f4d4  mov     rsp, r11
0x18000f4d7  pop     r15
0x18000f4d9  pop     r14
0x18000f4db  pop     r12
0x18000f4dd  pop     rdi
0x18000f4de  pop     rsi
0x18000f4df  retn
```
