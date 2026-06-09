# CSlideIn::_WindowEnumCallback(CWindowData *,CStoryboard::EnumWindowFlags,long *)

- ea: `0x1800c8570`
- end: `0x1800c8ae8`
- name: `?_WindowEnumCallback@CSlideIn@@EEAA_NPEAVCWindowData@@W4EnumWindowFlags@CStoryboard@@PEAJ@Z`
- size: `1400`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x180019e20`
- `0x180019e64`
- `0x18001ce00`
- `0x18001f43c`
- `0x18002d0a4`
- `0x18002e6a0`
- `0x18002e6e0`
- `0x180045c80`
- `0x180063e00`
- `0x180072e90`
- `0x180073e20`
- `0x180075f08`
- `0x180095130`
- `0x18009c024`
- `0x1800c3d30`
- `0x1800c6418`
- `0x1800c6610`
- `0x1800c8570`
- `0x1800ea010`

## import_xrefs

- `USER32!OffsetRect` at `0x1800c88f6`
- `USER32!OffsetRect` at `0x1800c88f6`
- `USER32!IsRectEmpty` at `0x1800c8724`
- `USER32!IsRectEmpty` at `0x1800c8a16`
- `USER32!IsRectEmpty` at `0x1800c8724`
- `USER32!IsRectEmpty` at `0x1800c8a16`
- `USER32!IntersectRect` at `0x1800c8712`
- `USER32!IntersectRect` at `0x1800c8a08`
- `USER32!IntersectRect` at `0x1800c8712`
- `USER32!IntersectRect` at `0x1800c8a08`

## pseudocode

```c
char __fastcall CSlideIn::_WindowEnumCallback(CStoryboard *a1, __int64 a2, char a3, int *a4)
{
  int v4; // ebx
  int v8; // esi
  unsigned __int64 v9; // rcx
  int v10; // eax
  CBaseObject *v11; // rsi
  double v12; // xmm7_8
  LONG *TaggedWindow; // rax
  unsigned int v14; // r9d
  LONG bottom; // edi
  int v16; // edx
  int v17; // ecx
  __m128i v18; // xmm0
  CWindowPropertyTracker *WPT; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // ecx
  int v25; // ecx
  CWindowPropertyTracker *v26; // rax
  CStoryboard *v27; // rcx
  int v28; // eax
  struct tagRECT v29; // xmm0
  CWindowPropertyTracker *v30; // rax
  CStoryboard *v31; // rcx
  CWindowPropertyTracker *v32; // rax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // ecx
  double v37; // xmm0_8
  struct tagSIZE *v38; // r8
  struct tagPOINT *v39; // rdx
  CBaseObject *v41; // [rsp+38h] [rbp-69h] BYREF
  struct tagPOINT v42; // [rsp+40h] [rbp-61h] BYREF
  struct tagSIZE v43; // [rsp+48h] [rbp-59h] BYREF
  struct tagRECT v44; // [rsp+50h] [rbp-51h] BYREF
  struct tagRECT rcDst; // [rsp+60h] [rbp-41h] BYREF
  RECT rcSrc2; // [rsp+70h] [rbp-31h] BYREF
  RECT rcSrc1; // [rsp+80h] [rbp-21h] BYREF
  RECT v48; // [rsp+90h] [rbp-11h] BYREF

  v4 = 0;
  v41 = 0;
  if ( (a3 & 1) == 0 )
    goto LABEL_72;
  v44 = 0;
  CTransitionVisualController::GetMonitorRectFromRectImpl((const struct tagRECT *)(a2 + 48), &v44);
  v8 = *(_DWORD *)(a2 + 744);
  v9 = v8 & 0xFFF;
  if ( (unsigned int)v9 <= 0x2B )
  {
    if ( (_DWORD)v9 == 43 )
    {
      v22 = (*(__int64 (__fastcall **)(CStoryboard *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, (unsigned int)v8);
      v23 = CStoryboard::_CreateAndAddNullComponentWithWindow(a1, (struct CWindowData *)a2, v22, &v41);
      v4 = v23;
      if ( v23 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v23, 0x2E3u, 0);
      goto LABEL_70;
    }
    if ( (v8 & 0xFFF) == 0 )
    {
      if ( v8 < 0 )
      {
        v21 = CSlide::_SlideWindow(a1, (struct CWindowData *)a2, 1.0, 0);
        v4 = v21;
        if ( v21 < 0 )
          MilInstrumentationCheckHR_MaybeFailFast(
            0x14u,
            &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v21,
            0x2DDu,
            0);
      }
      goto LABEL_72;
    }
    if ( (_DWORD)v9 == 8 )
    {
      WPT = CStoryboard::_GetWPT((CStoryboard *)v9);
      if ( !CWindowPropertyTracker::IsWindowTrackedAndCloakChanged(WPT, *(HWND *)(a2 + 40), 0) )
        goto LABEL_72;
      *(_DWORD *)(a2 + 744) |= 0x200000u;
      v20 = CSlide::_SlideWindowVertically(a1, (struct CWindowData *)a2, &v44, 1, &v41);
      v4 = v20;
      if ( v20 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v20, 0x28Cu, 0);
      else
        *(_BYTE *)(*((_QWORD *)v41 + 5) + 912LL) = 1;
      goto LABEL_70;
    }
    if ( (_DWORD)v9 != 11 )
    {
      if ( (_DWORD)v9 != 24 && (_DWORD)v9 != 42 )
        goto LABEL_72;
      goto LABEL_38;
    }
    v8 |= 0x200000u;
    *(_DWORD *)(a2 + 744) = v8;
LABEL_11:
    v10 = CSlide::_SlideWindow(a1, (struct CWindowData *)a2, 1.0, &v41);
    v4 = v10;
    if ( v10 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v10, 0x29Au, 0);
    }
    else
    {
      *(_DWORD *)(a2 + 744) = v8;
      if ( (v8 & 0xFFF) == 0x3C )
      {
        v11 = v41;
        *(_BYTE *)(*((_QWORD *)v41 + 5) + 912LL) = 1;
        v48 = 0;
        rcSrc1 = 0;
        if ( (int)CAnimatedTransitionVisual::GetBeginRect(*((CAnimatedTransitionVisual **)v11 + 5), &v48) >= 0
          && (int)CAnimatedTransitionVisual::GetEndRect(*((CAnimatedTransitionVisual **)v11 + 5), &rcSrc1) >= 0 )
        {
          v12 = 0.0;
          v43 = 0;
          *(double *)&v42 = 0.0;
          rcDst = 0;
          rcSrc2 = 0;
          TaggedWindow = (LONG *)CStoryboard::GetTaggedWindow();
          bottom = v44.bottom;
          if ( TaggedWindow )
          {
            v16 = 0;
            rcSrc2.left = TaggedWindow[12];
            if ( TaggedWindow[15] - TaggedWindow[13] >= 0 )
              v16 = TaggedWindow[15] - TaggedWindow[13];
            rcSrc2.top = v44.bottom - v16;
            rcSrc2.right = TaggedWindow[14];
            rcSrc2.bottom = v44.bottom;
          }
          if ( v48.bottom <= rcSrc1.bottom )
          {
            if ( v48.bottom < rcSrc1.bottom )
            {
              if ( IntersectRect(&rcDst, &v48, &rcSrc2) && !IsRectEmpty(&rcDst) )
              {
                v36 = 0;
                if ( rcDst.bottom - rcDst.top >= 0 )
                  v36 = rcDst.bottom - rcDst.top;
                v12 = (double)-v36;
                *(double *)&v42 = v12;
              }
              v18 = _mm_cvtsi32_si128(bottom - rcSrc1.bottom);
              goto LABEL_60;
            }
          }
          else
          {
            v12 = (double)(v44.bottom - v48.bottom);
            *(double *)&v42 = v12;
            if ( IntersectRect(&rcDst, &rcSrc1, &rcSrc2) && !IsRectEmpty(&rcDst) )
            {
              v17 = 0;
              if ( rcDst.bottom - rcDst.top >= 0 )
                v17 = rcDst.bottom - rcDst.top;
              v18 = _mm_cvtsi32_si128(-v17);
LABEL_60:
              *(_QWORD *)&v37 = *(_OWORD *)&_mm_cvtepi32_pd(v18);
              v43 = *(struct tagSIZE *)&v37;
LABEL_62:
              if ( v37 == 0.0 )
                v38 = 0;
              else
                v38 = &v43;
              if ( v12 == 0.0 )
                v39 = 0;
              else
                v39 = &v42;
              CAnimatedTransitionVisual::SetChopPosition(
                *((CAnimatedTransitionVisual **)v11 + 5),
                (const double *)v39,
                (const double *)v38,
                v14);
              goto LABEL_70;
            }
          }
          v37 = 0.0;
          goto LABEL_62;
        }
      }
    }
LABEL_70:
    if ( v41 )
      CBaseObject::Release(v41);
    goto LABEL_72;
  }
  v24 = v9 - 60;
  if ( !v24 )
    goto LABEL_11;
  v25 = v24 - 9;
  if ( !v25 )
  {
    v35 = CSlide::_SlideWindowVertically(a1, (struct CWindowData *)a2, &v44, 1, &v41);
    v4 = v35;
    if ( v35 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v35, 0x282u, 0);
    goto LABEL_70;
  }
  v9 = (unsigned int)(v25 - 1);
  if ( !(_DWORD)v9 )
  {
    v34 = CSlide::_SlideWindow(a1, (struct CWindowData *)a2, 1.0, &v41);
    v4 = v34;
    if ( v34 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v34, 0x27Eu, 0);
    goto LABEL_70;
  }
  if ( (_DWORD)v9 != 17 )
    goto LABEL_72;
LABEL_38:
  v26 = CStoryboard::_GetWPT((CStoryboard *)v9);
  if ( CWindowPropertyTracker::IsWindowTrackedAndCloakChanged(v26, *(HWND *)(a2 + 40), 0)
    || ((v28 = *(_DWORD *)(a2 + 744) & 0xFFF, v28 == 42) || v28 == 87)
    && CTransitionVisualController::HasVisibleStyle(*(HWND *)(a2 + 40)) )
  {
    v29 = *(struct tagRECT *)(a2 + 48);
    *(double *)&v42 = 0.0;
    v43 = 0;
    rcDst = v29;
    v30 = CStoryboard::_GetWPT(v27);
    if ( (int)CWindowPropertyTracker::GetWindowEndPosition(v30, *(HWND *)(a2 + 40), &v42) >= 0 )
      OffsetRect(&rcDst, v42.x - rcDst.left, v42.y - rcDst.top);
    v32 = CStoryboard::_GetWPT(v31);
    if ( (int)CWindowPropertyTracker::GetWindowEndSize(v32, *(HWND *)(a2 + 40), &v43) >= 0 )
    {
      rcDst.right = rcDst.left + v43.cx;
      rcDst.bottom = v43.cy + rcDst.top;
    }
    CTransitionVisualController::GetMonitorRectFromRectImpl(&rcDst, &v44);
    v33 = CSlide::_SlideWindowHorizontally(a1, (struct CWindowData *)a2, &v44, 1, &rcDst, &v41);
    v4 = v33;
    if ( v33 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v33, 0x278u, 0);
    else
      *(_BYTE *)(*((_QWORD *)v41 + 5) + 912LL) = 1;
    goto LABEL_70;
  }
LABEL_72:
  *a4 = v4;
  return 1;
}

```

## disassembly

```asm
0x1800c8570  mov     rax, rsp
0x1800c8573  push    rbp
0x1800c8574  push    rbx
0x1800c8575  push    rsi
0x1800c8576  push    rdi
0x1800c8577  push    r12
0x1800c8579  push    r14
0x1800c857b  push    r15
0x1800c857d  lea     rbp, [rax-5Fh]
0x1800c8581  sub     rsp, 0C0h
0x1800c8588  movaps  xmmword ptr [rax-48h], xmm6
0x1800c858c  movaps  xmmword ptr [rax-58h], xmm7
0x1800c8590  mov     rax, cs:__security_cookie
0x1800c8597  xor     rax, rsp
0x1800c859a  mov     [rbp+57h+var_58], rax
0x1800c859e  xor     ebx, ebx
0x1800c85a0  mov     r12, r9
0x1800c85a3  mov     [rbp+57h+var_C0], rbx
0x1800c85a7  mov     rdi, rdx
0x1800c85aa  mov     r14, rcx
0x1800c85ad  test    r8b, 1
0x1800c85b1  jz      loc_1800C8AB6
0x1800c85b7  xorps   xmm0, xmm0
0x1800c85ba  lea     rdx, [rbp+57h+var_A8]; struct tagRECT *
0x1800c85be  lea     rcx, [rdi+30h]; struct tagRECT *
0x1800c85c2  movups  xmmword ptr [rbp+57h+var_A8.left], xmm0
0x1800c85c6  call    ?GetMonitorRectFromRectImpl@CTransitionVisualController@@KAXPEBUtagRECT@@PEAU2@@Z; CTransitionVisualController::GetMonitorRectFromRectImpl(tagRECT const *,tagRECT *)
0x1800c85cb  mov     esi, [rdi+2E8h]
0x1800c85d1  mov     ecx, esi
0x1800c85d3  and     ecx, 0FFFh; this
0x1800c85d9  cmp     ecx, 2Bh ; '+'
0x1800c85dc  ja      loc_1800C8854
0x1800c85e2  jz      loc_1800C8811
0x1800c85e8  test    ecx, ecx
0x1800c85ea  jz      loc_1800C87BA
0x1800c85f0  cmp     ecx, 8
0x1800c85f3  jz      loc_1800C874B
0x1800c85f9  cmp     ecx, 0Bh
0x1800c85fc  jz      short loc_1800C8615
0x1800c85fe  cmp     ecx, 18h
0x1800c8601  jz      loc_1800C8878
0x1800c8607  cmp     ecx, 2Ah ; '*'
0x1800c860a  jz      loc_1800C8878
0x1800c8610  jmp     loc_1800C8AB6
0x1800c8615  bts     esi, 15h
0x1800c8619  mov     [rdi+2E8h], esi
0x1800c861f  movss   xmm2, cs:__real@3f800000; float
0x1800c8627  lea     r9, [rbp+57h+var_C0]; struct CAnimationComponent **
0x1800c862b  mov     rdx, rdi; struct CWindowData *
0x1800c862e  mov     rcx, r14; this
0x1800c8631  call    ?_SlideWindow@CSlide@@IEAAJPEAVCWindowData@@MPEAPEAVCAnimationComponent@@@Z; CSlide::_SlideWindow(CWindowData *,float,CAnimationComponent * *)
0x1800c8636  mov     ebx, eax
0x1800c8638  test    eax, eax
0x1800c863a  js      loc_1800C8A7E
0x1800c8640  mov     [rdi+2E8h], esi
0x1800c8646  and     esi, 0FFFh
0x1800c864c  cmp     esi, 3Ch ; '<'
0x1800c864f  jnz     loc_1800C8AA8
0x1800c8655  mov     rsi, [rbp+57h+var_C0]
0x1800c8659  lea     rdx, [rbp+57h+var_68]; struct tagRECT *
0x1800c865d  xorps   xmm0, xmm0
0x1800c8660  xorps   xmm1, xmm1
0x1800c8663  mov     rax, [rsi+28h]
0x1800c8667  mov     byte ptr [rax+390h], 1
0x1800c866e  movups  xmmword ptr [rbp+57h+var_68.left], xmm0
0x1800c8672  movups  xmmword ptr [rbp+57h+rcSrc1.left], xmm1
0x1800c8676  mov     rcx, [rsi+28h]; this
0x1800c867a  call    ?GetBeginRect@CAnimatedTransitionVisual@@UEAAJPEAUtagRECT@@@Z; CAnimatedTransitionVisual::GetBeginRect(tagRECT *)
0x1800c867f  test    eax, eax
0x1800c8681  js      loc_1800C8AA8
0x1800c8687  mov     rcx, [rsi+28h]; this
0x1800c868b  lea     rdx, [rbp+57h+rcSrc1]; struct tagRECT *
0x1800c868f  call    ?GetEndRect@CAnimatedTransitionVisual@@UEAAJPEAUtagRECT@@@Z; CAnimatedTransitionVisual::GetEndRect(tagRECT *)
0x1800c8694  test    eax, eax
0x1800c8696  js      loc_1800C8AA8
0x1800c869c  xorps   xmm6, xmm6
0x1800c869f  xorps   xmm7, xmm7
0x1800c86a2  xorps   xmm0, xmm0
0x1800c86a5  movsd   qword ptr [rbp+57h+var_B0.cx], xmm6
0x1800c86aa  xorps   xmm1, xmm1
0x1800c86ad  movsd   qword ptr [rbp+57h+var_B8.x], xmm7
0x1800c86b2  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x1800c86b6  movups  xmmword ptr [rbp+57h+rcSrc2.left], xmm1
0x1800c86ba  call    ?GetTaggedWindow@CStoryboard@@SAPEAVCWindowData@@W4DWMTRANSITION_TARGET@@@Z; CStoryboard::GetTaggedWindow(DWMTRANSITION_TARGET)
0x1800c86bf  mov     edi, [rbp+57h+var_A8.bottom]
0x1800c86c2  test    rax, rax
0x1800c86c5  jz      short loc_1800C86EB
0x1800c86c7  mov     ecx, [rax+30h]
0x1800c86ca  mov     edx, 0
0x1800c86cf  mov     [rbp+57h+rcSrc2.left], ecx
0x1800c86d2  mov     ecx, [rax+3Ch]
0x1800c86d5  sub     ecx, [rax+34h]
0x1800c86d8  cmovns  edx, ecx
0x1800c86db  mov     ecx, edi
0x1800c86dd  sub     ecx, edx
0x1800c86df  mov     [rbp+57h+rcSrc2.top], ecx
0x1800c86e2  mov     eax, [rax+38h]
0x1800c86e5  mov     [rbp+57h+rcSrc2.right], eax
0x1800c86e8  mov     [rbp+57h+rcSrc2.bottom], edi
0x1800c86eb  mov     eax, [rbp+57h+var_68.bottom]
0x1800c86ee  cmp     eax, [rbp+57h+rcSrc1.bottom]
0x1800c86f1  jle     loc_1800C89FA
0x1800c86f7  sub     edi, eax
0x1800c86f9  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x1800c86fd  lea     rdx, [rbp+57h+rcSrc1]; lprcSrc1
0x1800c8701  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1800c8705  movd    xmm7, edi
0x1800c8709  cvtdq2pd xmm7, xmm7
0x1800c870d  movsd   qword ptr [rbp+57h+var_B8.x], xmm7
0x1800c8712  call    cs:__imp_IntersectRect
0x1800c8718  test    eax, eax
0x1800c871a  jz      loc_1800C8A4F
0x1800c8720  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800c8724  call    cs:__imp_IsRectEmpty
0x1800c872a  test    eax, eax
0x1800c872c  jnz     loc_1800C8A4F
0x1800c8732  mov     eax, [rbp+57h+rcDst.bottom]
0x1800c8735  mov     ecx, 0
0x1800c873a  sub     eax, [rbp+57h+rcDst.top]
0x1800c873d  cmovns  ecx, eax
0x1800c8740  neg     ecx
0x1800c8742  movd    xmm0, ecx
0x1800c8746  jmp     loc_1800C8A44
0x1800c874b  call    ?_GetWPT@CStoryboard@@IEAAPEAVCWindowPropertyTracker@@XZ; CStoryboard::_GetWPT(void)
0x1800c8750  mov     rdx, [rdi+28h]; HWND
0x1800c8754  mov     rcx, rax; this
0x1800c8757  xor     r8d, r8d; bool
0x1800c875a  call    ?IsWindowTrackedAndCloakChanged@CWindowPropertyTracker@@QEAA_NPEAUHWND__@@_N@Z; CWindowPropertyTracker::IsWindowTrackedAndCloakChanged(HWND__ *,bool)
0x1800c875f  test    al, al
0x1800c8761  jz      loc_1800C8AB6
0x1800c8767  bts     dword ptr [rdi+2E8h], 15h
0x1800c876f  lea     rax, [rbp+57h+var_C0]
0x1800c8773  mov     r9b, 1; bool
0x1800c8776  mov     [rsp+0F0h+var_D0], rax; struct CAnimationComponent **
0x1800c877b  lea     r8, [rbp+57h+var_A8]; struct tagRECT *
0x1800c877f  mov     rdx, rdi; struct CWindowData *
0x1800c8782  mov     rcx, r14; this
0x1800c8785  call    ?_SlideWindowVertically@CSlide@@IEAAJPEAVCWindowData@@AEBUtagRECT@@_NPEAPEAVCAnimationComponent@@@Z; CSlide::_SlideWindowVertically(CWindowData *,tagRECT const &,bool,CAnimationComponent * *)
0x1800c878a  mov     ebx, eax
0x1800c878c  test    eax, eax
0x1800c878e  js      short loc_1800C87A4
0x1800c8790  mov     rcx, [rbp+57h+var_C0]
0x1800c8794  mov     rdx, [rcx+28h]
0x1800c8798  mov     byte ptr [rdx+390h], 1
0x1800c879f  jmp     loc_1800C8AA8
0x1800c87a4  mov     [rsp+0F0h+var_C8], 0
0x1800c87ad  mov     dword ptr [rsp+0F0h+var_D0], 28Ch
0x1800c87b5  jmp     loc_1800C8A8F
0x1800c87ba  test    esi, esi
0x1800c87bc  jns     loc_1800C8AB6
0x1800c87c2  movss   xmm2, cs:__real@3f800000; float
0x1800c87ca  xor     r9d, r9d; struct CAnimationComponent **
0x1800c87cd  mov     rdx, rdi; struct CWindowData *
0x1800c87d0  mov     rcx, r14; this
0x1800c87d3  call    ?_SlideWindow@CSlide@@IEAAJPEAVCWindowData@@MPEAPEAVCAnimationComponent@@@Z; CSlide::_SlideWindow(CWindowData *,float,CAnimationComponent * *)
0x1800c87d8  mov     ebx, eax
0x1800c87da  test    eax, eax
0x1800c87dc  jns     loc_1800C8AB6
0x1800c87e2  mov     r8d, 1; unsigned int
0x1800c87e8  mov     [rsp+0F0h+var_C8], 0; void *
0x1800c87f1  mov     r9d, eax; int
0x1800c87f4  mov     dword ptr [rsp+0F0h+var_D0], 2DDh; unsigned int
0x1800c87fc  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CStoryboard@@2QBJB; int *
0x1800c8803  lea     ecx, [r8+13h]; unsigned int
0x1800c8807  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800c880c  jmp     loc_1800C8AB6
0x1800c8811  mov     rax, [r14]
0x1800c8814  mov     edx, esi
0x1800c8816  mov     rcx, r14
0x1800c8819  mov     rax, [rax+70h]
0x1800c881d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8822  mov     r8d, eax; int
0x1800c8825  lea     r9, [rbp+57h+var_C0]; struct CAnimationComponent **
0x1800c8829  mov     rdx, rdi; struct CWindowData *
0x1800c882c  mov     rcx, r14; this
0x1800c882f  call    ?_CreateAndAddNullComponentWithWindow@CStoryboard@@IEAAJPEAVCWindowData@@HPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddNullComponentWithWindow(CWindowData *,int,CAnimationComponent * *)
0x1800c8834  mov     ebx, eax
0x1800c8836  test    eax, eax
0x1800c8838  jns     loc_1800C8AA8
0x1800c883e  mov     [rsp+0F0h+var_C8], 0
0x1800c8847  mov     dword ptr [rsp+0F0h+var_D0], 2E3h
0x1800c884f  jmp     loc_1800C8A8F
0x1800c8854  sub     ecx, 3Ch ; '<'
0x1800c8857  jz      loc_1800C861F
0x1800c885d  sub     ecx, 9
0x1800c8860  jz      loc_1800C89BF
0x1800c8866  sub     ecx, 1; this
0x1800c8869  jz      loc_1800C8988
0x1800c886f  cmp     ecx, 11h
0x1800c8872  jnz     loc_1800C8AB6
0x1800c8878  call    ?_GetWPT@CStoryboard@@IEAAPEAVCWindowPropertyTracker@@XZ; CStoryboard::_GetWPT(void)
0x1800c887d  mov     rdx, [rdi+28h]; HWND
0x1800c8881  mov     rcx, rax; this
0x1800c8884  xor     r8d, r8d; bool
0x1800c8887  call    ?IsWindowTrackedAndCloakChanged@CWindowPropertyTracker@@QEAA_NPEAUHWND__@@_N@Z; CWindowPropertyTracker::IsWindowTrackedAndCloakChanged(HWND__ *,bool)
0x1800c888c  test    al, al
0x1800c888e  jnz     short loc_1800C88BA
0x1800c8890  mov     eax, [rdi+2E8h]
0x1800c8896  and     eax, 0FFFh
0x1800c889b  cmp     eax, 2Ah ; '*'
0x1800c889e  jz      short loc_1800C88A9
0x1800c88a0  cmp     eax, 57h ; 'W'
0x1800c88a3  jnz     loc_1800C8AB6
0x1800c88a9  mov     rcx, [rdi+28h]; HWND
0x1800c88ad  call    ?HasVisibleStyle@CTransitionVisualController@@SA_NPEAUHWND__@@@Z; CTransitionVisualController::HasVisibleStyle(HWND__ *)
0x1800c88b2  test    al, al
0x1800c88b4  jz      loc_1800C8AB6
0x1800c88ba  movups  xmm0, xmmword ptr [rdi+30h]
0x1800c88be  mov     qword ptr [rbp+57h+var_B8.x], rbx
0x1800c88c2  mov     qword ptr [rbp+57h+var_B0.cx], rbx
0x1800c88c6  movdqu  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x1800c88cb  call    ?_GetWPT@CStoryboard@@IEAAPEAVCWindowPropertyTracker@@XZ; CStoryboard::_GetWPT(void)
0x1800c88d0  mov     rdx, [rdi+28h]; HWND
0x1800c88d4  lea     r8, [rbp+57h+var_B8]; struct tagPOINT *
0x1800c88d8  mov     rcx, rax; this
0x1800c88db  call    ?GetWindowEndPosition@CWindowPropertyTracker@@QEAAJPEAUHWND__@@PEAUtagPOINT@@@Z; CWindowPropertyTracker::GetWindowEndPosition(HWND__ *,tagPOINT *)
0x1800c88e0  test    eax, eax
0x1800c88e2  js      short loc_1800C88FC
0x1800c88e4  mov     r8d, [rbp+57h+var_B8.y]
0x1800c88e8  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800c88ec  mov     edx, [rbp+57h+var_B8.x]
0x1800c88ef  sub     r8d, [rbp+57h+rcDst.top]; dy
0x1800c88f3  sub     edx, [rbp+57h+rcDst.left]; dx
0x1800c88f6  call    cs:__imp_OffsetRect
0x1800c88fc  call    ?_GetWPT@CStoryboard@@IEAAPEAVCWindowPropertyTracker@@XZ; CStoryboard::_GetWPT(void)
0x1800c8901  mov     rdx, [rdi+28h]; HWND
0x1800c8905  lea     r8, [rbp+57h+var_B0]; struct tagSIZE *
0x1800c8909  mov     rcx, rax; this
0x1800c890c  call    ?GetWindowEndSize@CWindowPropertyTracker@@QEAAJPEAUHWND__@@PEAUtagSIZE@@@Z; CWindowPropertyTracker::GetWindowEndSize(HWND__ *,tagSIZE *)
0x1800c8911  test    eax, eax
0x1800c8913  js      short loc_1800C8927
0x1800c8915  mov     ecx, [rbp+57h+var_B0.cx]
0x1800c8918  add     ecx, [rbp+57h+rcDst.left]
0x1800c891b  mov     [rbp+57h+rcDst.right], ecx
0x1800c891e  mov     ecx, [rbp+57h+rcDst.top]
0x1800c8921  add     ecx, [rbp+57h+var_B0.cy]
0x1800c8924  mov     [rbp+57h+rcDst.bottom], ecx
0x1800c8927  lea     rdx, [rbp+57h+var_A8]; struct tagRECT *
0x1800c892b  lea     rcx, [rbp+57h+rcDst]; struct tagRECT *
0x1800c892f  call    ?GetMonitorRectFromRectImpl@CTransitionVisualController@@KAXPEBUtagRECT@@PEAU2@@Z; CTransitionVisualController::GetMonitorRectFromRectImpl(tagRECT const *,tagRECT *)
0x1800c8934  lea     rax, [rbp+57h+var_C0]
0x1800c8938  mov     r9b, 1; bool
0x1800c893b  mov     [rsp+0F0h+var_C8], rax; struct CAnimationComponent **
0x1800c8940  lea     r8, [rbp+57h+var_A8]; struct tagRECT *
0x1800c8944  lea     rax, [rbp+57h+rcDst]
0x1800c8948  mov     rdx, rdi; struct CWindowData *
0x1800c894b  mov     rcx, r14; this
0x1800c894e  mov     [rsp+0F0h+var_D0], rax; struct tagRECT *
0x1800c8953  call    ?_SlideWindowHorizontally@CSlide@@IEAAJPEAVCWindowData@@AEBUtagRECT@@_NPEBU3@PEAPEAVCAnimationComponent@@@Z; CSlide::_SlideWindowHorizontally(CWindowData *,tagRECT const &,bool,tagRECT const *,CAnimationComponent * *)
0x1800c8958  mov     ebx, eax
0x1800c895a  test    eax, eax
0x1800c895c  js      short loc_1800C8972
0x1800c895e  mov     rax, [rbp+57h+var_C0]
0x1800c8962  mov     rcx, [rax+28h]
0x1800c8966  mov     byte ptr [rcx+390h], 1
0x1800c896d  jmp     loc_1800C8AA8
0x1800c8972  mov     [rsp+0F0h+var_C8], 0
0x1800c897b  mov     dword ptr [rsp+0F0h+var_D0], 278h
0x1800c8983  jmp     loc_1800C8A8F
0x1800c8988  movss   xmm2, cs:__real@3f800000; float
0x1800c8990  lea     r9, [rbp+57h+var_C0]; struct CAnimationComponent **
0x1800c8994  mov     rdx, rdi; struct CWindowData *
0x1800c8997  mov     rcx, r14; this
0x1800c899a  call    ?_SlideWindow@CSlide@@IEAAJPEAVCWindowData@@MPEAPEAVCAnimationComponent@@@Z; CSlide::_SlideWindow(CWindowData *,float,CAnimationComponent * *)
0x1800c899f  mov     ebx, eax
0x1800c89a1  test    eax, eax
0x1800c89a3  jns     loc_1800C8AA8
0x1800c89a9  mov     [rsp+0F0h+var_C8], 0
0x1800c89b2  mov     dword ptr [rsp+0F0h+var_D0], 27Eh
0x1800c89ba  jmp     loc_1800C8A8F
0x1800c89bf  lea     rax, [rbp+57h+var_C0]
0x1800c89c3  mov     r9b, 1; bool
0x1800c89c6  lea     r8, [rbp+57h+var_A8]; struct tagRECT *
0x1800c89ca  mov     [rsp+0F0h+var_D0], rax; struct CAnimationComponent **
0x1800c89cf  mov     rdx, rdi; struct CWindowData *
0x1800c89d2  mov     rcx, r14; this
0x1800c89d5  call    ?_SlideWindowVertically@CSlide@@IEAAJPEAVCWindowData@@AEBUtagRECT@@_NPEAPEAVCAnimationComponent@@@Z; CSlide::_SlideWindowVertically(CWindowData *,tagRECT const &,bool,CAnimationComponent * *)
0x1800c89da  mov     ebx, eax
0x1800c89dc  test    eax, eax
0x1800c89de  jns     loc_1800C8AA8
0x1800c89e4  mov     [rsp+0F0h+var_C8], 0
0x1800c89ed  mov     dword ptr [rsp+0F0h+var_D0], 282h
0x1800c89f5  jmp     loc_1800C8A8F
0x1800c89fa  jge     short loc_1800C8A4F
0x1800c89fc  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x1800c8a00  lea     rdx, [rbp+57h+var_68]; lprcSrc1
0x1800c8a04  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1800c8a08  call    cs:__imp_IntersectRect
0x1800c8a0e  test    eax, eax
0x1800c8a10  jz      short loc_1800C8A3D
0x1800c8a12  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800c8a16  call    cs:__imp_IsRectEmpty
0x1800c8a1c  test    eax, eax
0x1800c8a1e  jnz     short loc_1800C8A3D
0x1800c8a20  mov     eax, [rbp+57h+rcDst.bottom]
0x1800c8a23  mov     ecx, 0
0x1800c8a28  sub     eax, [rbp+57h+rcDst.top]
0x1800c8a2b  cmovns  ecx, eax
0x1800c8a2e  neg     ecx
0x1800c8a30  movd    xmm7, ecx
  ... truncated ...
```
