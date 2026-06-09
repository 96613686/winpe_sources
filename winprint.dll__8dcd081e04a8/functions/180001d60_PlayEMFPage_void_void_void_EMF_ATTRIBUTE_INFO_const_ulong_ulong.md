# PlayEMFPage(void *,void *,void *,_EMF_ATTRIBUTE_INFO * const,ulong,ulong)

- ea: `0x180001d60`
- end: `0x180001fb7`
- name: `?PlayEMFPage@@YAHPEAX00QEAU_EMF_ATTRIBUTE_INFO@@KK@Z`
- size: `599`
- prototype: `__int64 __usercall@<rax>(HANDLE SpoolFileHandle@<rcx>, HDC hdc@<rdx>, void *@<r8>, struct _EMF_ATTRIBUTE_INFO *const@<r9>, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180006bcc`
- `0x180006e10`
- `0x180007210`

## callees

- `0x180001d60`
- `0x180001fc0`
- `0x180004c80`

## import_xrefs

- `GDI32!GdiPlayPageEMF` at `0x180001f77`
- `GDI32!GdiPlayPageEMF` at `0x180001f77`
- `GDI32!ModifyWorldTransform` at `0x180001e9b`
- `GDI32!ModifyWorldTransform` at `0x180001f2e`
- `GDI32!ModifyWorldTransform` at `0x180001f4c`
- `GDI32!ModifyWorldTransform` at `0x180001e9b`
- `GDI32!ModifyWorldTransform` at `0x180001f2e`
- `GDI32!ModifyWorldTransform` at `0x180001f4c`
- `GDI32!SetWorldTransform` at `0x180001e72`
- `GDI32!SetWorldTransform` at `0x180001f13`
- `GDI32!SetWorldTransform` at `0x180001e72`
- `GDI32!SetWorldTransform` at `0x180001f13`

## pseudocode

```c
__int64 __fastcall PlayEMFPage(
        HANDLE SpoolFileHandle,
        HDC hdc,
        void *a3,
        struct _EMF_ATTRIBUTE_INFO *const a4,
        unsigned int a5,
        __int16 a6)
{
  int v6; // r12d
  unsigned int v7; // esi
  int v11; // edx
  int v12; // ebx
  RECT *prectClip; // r14
  BOOL v14; // eax
  unsigned int v15; // ecx
  __m128i v17; // xmm0
  __m128i v18; // xmm1
  RECT *p_prectDocument; // r8
  int v20; // [rsp+30h] [rbp-89h] BYREF
  HANDLE hemf; // [rsp+38h] [rbp-81h]
  RECT prectDocument; // [rsp+40h] [rbp-79h] BYREF
  __int128 v23; // [rsp+50h] [rbp-69h] BYREF
  XFORM v24; // [rsp+60h] [rbp-59h] BYREF
  XFORM xf; // [rsp+78h] [rbp-41h] BYREF
  RECT prectBorder; // [rsp+90h] [rbp-29h] BYREF
  XFORM v27; // [rsp+A0h] [rbp-19h] BYREF

  v6 = *((_DWORD *)a4 + 8);
  v7 = 0;
  hemf = a3;
  v20 = 0;
  prectDocument = 0;
  v23 = 0;
  prectBorder = (RECT)_mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(_QWORD *)&v24.eDx = 0;
  *(__m128i *)&v27.eM11 = _mm_load_si128((const __m128i *)&_xmm);
  *(_QWORD *)&v27.eDx = 0;
  *(__m128i *)&v24.eM11 = _mm_load_si128((const __m128i *)&_xmm);
  *(_QWORD *)&xf.eDx = 0;
  *(_OWORD *)&xf.eM11 = *(_OWORD *)&v24.eM11;
  if ( (unsigned int)GetPageCoordinatesForNUp(hdc, a4, &prectDocument, &prectBorder, a5, &v20) )
  {
    v11 = 0;
    if ( a6 < 0 )
      v12 = v20 == 0;
    else
      v12 = v20;
    if ( (a6 & 2) != 0 )
    {
      v27.eM12 = 1.0;
      v27.eM21 = -1.0;
    }
    if ( v12 )
    {
      *(_QWORD *)&v23 = 0;
      HIDWORD(v23) = prectDocument.right - prectDocument.left;
      DWORD2(v23) = prectDocument.bottom - prectDocument.top;
      if ( (a6 & 2) != 0 )
      {
        v17 = _mm_cvtsi32_si128(prectDocument.right);
        v18 = _mm_cvtsi32_si128(prectDocument.top);
      }
      else
      {
        v17 = _mm_cvtsi32_si128(prectDocument.left);
        v18 = _mm_cvtsi32_si128(prectDocument.bottom);
      }
      LODWORD(v24.eDy) = _mm_cvtepi32_ps(v18).m128_u32[0];
      LODWORD(v24.eDx) = _mm_cvtepi32_ps(v17).m128_u32[0];
      if ( !SetWorldTransform(hdc, &v27) || !ModifyWorldTransform(hdc, &v24, 3u) )
        goto LABEL_10;
      v11 = 1;
    }
    prectClip = &prectDocument;
    if ( v6 == 1 )
    {
      prectClip = 0;
      xf.eM11 = *((FLOAT *)a4 + 22);
      xf.eM22 = xf.eM11;
      if ( v11 )
      {
        if ( !ModifyWorldTransform(hdc, &xf, 3u) )
          goto LABEL_10;
      }
      else if ( !SetWorldTransform(hdc, &xf) )
      {
        goto LABEL_10;
      }
    }
    p_prectDocument = (RECT *)&v23;
    if ( !v12 )
      p_prectDocument = &prectDocument;
    GdiPlayPageEMF(SpoolFileHandle, hemf, p_prectDocument, &prectBorder, prectClip);
    v7 = 1;
  }
LABEL_10:
  v14 = ModifyWorldTransform(hdc, 0, 1u);
  v15 = 0;
  if ( v14 )
    return v7;
  return v15;
}

```

## disassembly

```asm
0x180001d60  push    rbp
0x180001d62  push    rsi
0x180001d63  push    rdi
0x180001d64  push    r12
0x180001d66  push    r13
0x180001d68  push    r15
0x180001d6a  lea     rbp, [rsp-1Fh]
0x180001d6f  sub     rsp, 0D8h
0x180001d76  mov     rax, cs:__security_cookie
0x180001d7d  xor     rax, rsp
0x180001d80  mov     [rbp+47h+var_48], rax
0x180001d84  movdqa  xmm2, cs:__xmm@3f80000000000000000000003f800000
0x180001d8c  lea     rax, [rsp+100h+var_D0]
0x180001d91  mov     r12d, [r9+20h]
0x180001d95  xor     esi, esi
0x180001d97  xorps   xmm0, xmm0
0x180001d9a  mov     [rsp+100h+var_D8], rax; int *
0x180001d9f  mov     eax, [rbp+47h+arg_20]
0x180001da2  xorps   xmm1, xmm1
0x180001da5  mov     r15, r9
0x180001da8  mov     [rsp+100h+hemf], r8
0x180001dad  mov     rdi, rdx
0x180001db0  mov     [rsp+100h+var_D0], esi
0x180001db4  movups  xmmword ptr [rbp+47h+prectDocument.left], xmm0
0x180001db8  lea     r9, [rbp+47h+prectBorder]; struct tagRECT *
0x180001dbc  mov     r13, rcx
0x180001dbf  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180001dc7  lea     r8, [rbp+47h+prectDocument]; struct tagRECT *
0x180001dcb  movups  [rbp+47h+var_B0], xmm1
0x180001dcf  mov     rdx, r15; struct _EMF_ATTRIBUTE_INFO *
0x180001dd2  mov     rcx, rdi; hdc
0x180001dd5  movdqa  xmm1, cs:__xmm@000000003f800000bf80000000000000
0x180001ddd  movdqu  xmmword ptr [rbp+47h+prectBorder.left], xmm0
0x180001de2  mov     qword ptr [rbp+47h+var_A0.eDx], rsi
0x180001de6  movups  xmmword ptr [rbp+47h+var_60.eM11], xmm1
0x180001dea  mov     qword ptr [rbp+47h+var_60.eDx], rsi
0x180001dee  movups  xmmword ptr [rbp+47h+var_A0.eM11], xmm2
0x180001df2  mov     qword ptr [rbp+47h+xf.eDx], rsi
0x180001df6  movups  xmmword ptr [rbp+47h+xf.eM11], xmm2
0x180001dfa  mov     dword ptr [rsp+100h+prectClip], eax; unsigned int
0x180001dfe  call    ?GetPageCoordinatesForNUp@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@PEAUtagRECT@@2IPEAH@Z; GetPageCoordinatesForNUp(void *,_EMF_ATTRIBUTE_INFO *,tagRECT *,tagRECT *,uint,int *)
0x180001e03  test    eax, eax
0x180001e05  jz      loc_180001E90
0x180001e0b  mov     ecx, [rbp+47h+arg_28]
0x180001e0e  xor     edx, edx
0x180001e10  mov     [rsp+100h+var_30], rbx
0x180001e18  bt      ecx, 0Fh
0x180001e1c  jb      loc_180001F96
0x180001e22  mov     ebx, [rsp+100h+var_D0]
0x180001e26  and     ecx, 2
0x180001e29  jnz     loc_180001FA4
0x180001e2f  test    ebx, ebx
0x180001e31  jnz     loc_180001EC7
0x180001e37  xor     eax, eax
0x180001e39  mov     [rsp+100h+var_38], r14
0x180001e41  cmp     r12d, 1
0x180001e45  lea     r14, [rbp+47h+prectDocument]
0x180001e49  cmovz   r14, rax
0x180001e4d  jnz     loc_180001F5A
0x180001e53  movss   xmm0, dword ptr [r15+58h]
0x180001e59  test    edx, edx
0x180001e5b  movss   [rbp+47h+xf.eM11], xmm0
0x180001e60  lea     rdx, [rbp+47h+xf]; lpxf
0x180001e64  movss   [rbp+47h+xf.eM22], xmm0
0x180001e69  mov     rcx, rdi; hdc
0x180001e6c  jnz     loc_180001F46
0x180001e72  call    cs:__imp_SetWorldTransform
0x180001e78  test    eax, eax
0x180001e7a  jnz     loc_180001F5A
0x180001e80  mov     r14, [rsp+100h+var_38]
0x180001e88  mov     rbx, [rsp+100h+var_30]
0x180001e90  xor     edx, edx; lpxf
0x180001e92  mov     r8d, 1; mode
0x180001e98  mov     rcx, rdi; hdc
0x180001e9b  call    cs:__imp_ModifyWorldTransform
0x180001ea1  xor     ecx, ecx
0x180001ea3  test    eax, eax
0x180001ea5  cmovnz  ecx, esi
0x180001ea8  mov     eax, ecx
0x180001eaa  mov     rcx, [rbp+47h+var_48]
0x180001eae  xor     rcx, rsp; StackCookie
0x180001eb1  call    __security_check_cookie
0x180001eb6  add     rsp, 0D8h
0x180001ebd  pop     r15
0x180001ebf  pop     r13
0x180001ec1  pop     r12
0x180001ec3  pop     rdi
0x180001ec4  pop     rsi
0x180001ec5  pop     rbp
0x180001ec6  retn
0x180001ec7  mov     r8d, [rbp+47h+prectDocument.left]
0x180001ecb  mov     r9d, [rbp+47h+prectDocument.bottom]
0x180001ecf  mov     r10d, [rbp+47h+prectDocument.top]
0x180001ed3  mov     qword ptr [rbp+47h+var_B0], rdx
0x180001ed7  mov     edx, [rbp+47h+prectDocument.right]
0x180001eda  mov     eax, edx
0x180001edc  sub     eax, r8d
0x180001edf  mov     dword ptr [rbp+47h+var_B0+0Ch], eax
0x180001ee2  mov     eax, r9d
0x180001ee5  sub     eax, r10d
0x180001ee8  mov     dword ptr [rbp+47h+var_B0+8], eax
0x180001eeb  test    ecx, ecx
0x180001eed  jz      loc_180001F87
0x180001ef3  movd    xmm0, edx
0x180001ef7  movd    xmm1, r10d
0x180001efc  cvtdq2ps xmm1, xmm1
0x180001eff  lea     rdx, [rbp+47h+var_60]; lpxf
0x180001f03  mov     rcx, rdi; hdc
0x180001f06  cvtdq2ps xmm0, xmm0
0x180001f09  movss   [rbp+47h+var_A0.eDy], xmm1
0x180001f0e  movss   [rbp+47h+var_A0.eDx], xmm0
0x180001f13  call    cs:__imp_SetWorldTransform
0x180001f19  test    eax, eax
0x180001f1b  jz      loc_180001E88
0x180001f21  mov     r8d, 3; mode
0x180001f27  lea     rdx, [rbp+47h+var_A0]; lpxf
0x180001f2b  mov     rcx, rdi; hdc
0x180001f2e  call    cs:__imp_ModifyWorldTransform
0x180001f34  test    eax, eax
0x180001f36  jz      loc_180001E88
0x180001f3c  mov     edx, 1
0x180001f41  jmp     loc_180001E37
0x180001f46  mov     r8d, 3; mode
0x180001f4c  call    cs:__imp_ModifyWorldTransform
0x180001f52  test    eax, eax
0x180001f54  jz      loc_180001E80
0x180001f5a  mov     rdx, [rsp+100h+hemf]; hemf
0x180001f5f  lea     r9, [rbp+47h+prectBorder]; prectBorder
0x180001f63  mov     [rsp+100h+prectClip], r14; prectClip
0x180001f68  mov     rcx, r13; SpoolFileHandle
0x180001f6b  lea     r8, [rbp+47h+var_B0]
0x180001f6f  test    ebx, ebx
0x180001f71  jnz     short loc_180001F77
0x180001f73  lea     r8, [rbp+47h+prectDocument]; prectDocument
0x180001f77  call    cs:__imp_GdiPlayPageEMF
0x180001f7d  mov     esi, 1
0x180001f82  jmp     loc_180001E80
0x180001f87  movd    xmm0, r8d
0x180001f8c  movd    xmm1, r9d
0x180001f91  jmp     loc_180001EFC
0x180001f96  xor     ebx, ebx
0x180001f98  cmp     [rsp+100h+var_D0], edx
0x180001f9c  setz    bl
0x180001f9f  jmp     loc_180001E26
0x180001fa4  mov     [rbp+47h+var_60.eM12], 3F800000h
0x180001fab  mov     [rbp+47h+var_60.eM21], 0BF800000h
0x180001fb2  jmp     loc_180001E2F
```
