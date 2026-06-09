# CGroupingStoryboard::_Create3DComponent(CWindowData *)

- ea: `0x18008dfc8`
- end: `0x18008e369`
- name: `?_Create3DComponent@CGroupingStoryboard@@IEAAJPEAVCWindowData@@@Z`
- size: `929`
- prototype: `__int64 __fastcall(CGroupingStoryboard *__hidden this, struct CWindowData *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800c69c0`
- `0x1800c74c0`

## callees

- `0x180008350`
- `0x18001ce00`
- `0x18001f43c`
- `0x180063e00`
- `0x180063ea0`
- `0x180068aa4`
- `0x180068af0`
- `0x18008dfc8`
- `0x18008e370`
- `0x18008e8f8`
- `0x180095130`
- `0x1800c5700`
- `0x1800c5fc4`
- `0x1800cedb0`
- `0x1800ea010`

## import_xrefs

- `USER32!OffsetRect` at `0x18008e143`
- `USER32!OffsetRect` at `0x18008e143`
- `USER32!IsRectEmpty` at `0x18008e108`
- `USER32!IsRectEmpty` at `0x18008e108`

## pseudocode

```c
_BOOL8 __fastcall CGroupingStoryboard::_Create3DComponent(CGroupingStoryboard *this, struct CWindowData *a2)
{
  int v4; // edx
  int v5; // r13d
  BOOL v6; // esi
  CBaseObject *v7; // r15
  CBaseObject *v8; // r14
  int v9; // eax
  int v10; // eax
  int v11; // edx
  int v12; // r8d
  struct tagRECT *p_rc; // rbx
  int v14; // eax
  int v15; // eax
  struct tagRECT v16; // xmm0
  int v17; // eax
  int v18; // eax
  CBaseObject *v19; // rbx
  struct tagRECT **v21; // [rsp+28h] [rbp-41h]
  CBaseObject *v22; // [rsp+50h] [rbp-19h] BYREF
  CBaseObject *v23; // [rsp+58h] [rbp-11h] BYREF
  CBaseObject *v24; // [rsp+60h] [rbp-9h] BYREF
  struct tagRECT rc; // [rsp+68h] [rbp-1h] BYREF
  struct tagRECT v26; // [rsp+78h] [rbp+Fh] BYREF

  v22 = 0;
  v4 = *((_DWORD *)a2 + 186);
  v23 = 0;
  v5 = v4 & 0xFFF;
  v24 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v26 = 0;
  if ( v5 != 1 && (v4 & 0xFFF) != 3 && (v4 & 0xFFF) != 4 )
  {
    if ( (v4 & 0xFFF) == 0x1E )
    {
      *(_QWORD *)&rc.left = 0;
      CStoryboard::_GetIdealRects(a2, 0, &v26, (struct tagRECT **)&rc, 0, v21);
      v9 = (*(__int64 (__fastcall **)(CGroupingStoryboard *, _QWORD))(*(_QWORD *)this + 112LL))(
             this,
             *((unsigned int *)a2 + 186));
      v10 = CStoryboard::_CreateAndAddAnimationComponentWithRect(
              this,
              a2,
              0,
              v9,
              *(struct tagRECT **)&rc.left,
              0,
              -1,
              &v22);
      v6 = v10;
      if ( v10 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v10, 0x87Au, 0);
        goto LABEL_35;
      }
    }
    goto LABEL_26;
  }
  if ( *((_DWORD *)a2 + 32) == 1 )
  {
    v4 |= 0x4000000u;
    *((_DWORD *)a2 + 186) = v4;
  }
  if ( (v4 & 0x10000000) == 0 || (int)CTransitionVisualController::GetClonableOwnedWindowCount(a2) <= 0 )
    LOBYTE(v6) = 1;
  if ( (*((_DWORD *)a2 + 186) & 0x1000000) != 0 && !IsRectEmpty((const RECT *)((char *)a2 + 748)) )
  {
    rc = 0;
    if ( v5 == 1 )
    {
      v11 = -*((_DWORD *)a2 + 191);
      v12 = -HIDWORD(*(_QWORD *)((char *)a2 + 764));
      rc = *(struct tagRECT *)((char *)a2 + 764);
      OffsetRect(&rc, v11, v12);
    }
    p_rc = &rc;
    if ( v5 != 1 )
      p_rc = 0;
    v14 = (*(__int64 (__fastcall **)(CGroupingStoryboard *, _QWORD))(*(_QWORD *)this + 112LL))(
            this,
            *((unsigned int *)a2 + 186));
    v15 = CStoryboard::_CreateAndAddAnimationComponentControlReuse(
            this,
            a2,
            0,
            v14,
            (struct tagRECT *)((char *)a2 + 748),
            p_rc,
            -1,
            v6,
            &v22);
    v6 = v15;
    if ( v15 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v15, 0x862u, 0);
      goto LABEL_35;
    }
    v16 = *(struct tagRECT *)((char *)a2 + 764);
    goto LABEL_25;
  }
  v17 = (*(__int64 (__fastcall **)(CGroupingStoryboard *, _QWORD))(*(_QWORD *)this + 112LL))(
          this,
          *((unsigned int *)a2 + 186));
  v18 = CStoryboard::_CreateAndAddAnimationComponentControlReuse(this, a2, 0, v17, 0, 0, -1, v6, &v22);
  v6 = v18;
  if ( v18 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v18, 0x867u, 0);
    goto LABEL_35;
  }
  if ( *((_DWORD *)a2 + 32) != 1 )
  {
    v16 = *(struct tagRECT *)((char *)v22 + 88);
LABEL_25:
    v26 = v16;
    goto LABEL_26;
  }
  CTransitionVisualController::GetMonitorRectFromRectImpl((const struct tagRECT *)a2 + 3, &v26);
LABEL_26:
  v19 = v22;
  *(_QWORD *)&rc.left = this;
  CAnimatedTransitionVisual::SetBeginRect(*((CAnimatedTransitionVisual **)v22 + 5), &v26);
  CAnimatedTransitionVisual::SetEndRect(*((CAnimatedTransitionVisual **)v19 + 5), &v26);
  CGroupingStoryboard::_Create3DComponent_::_44_::_lambda_1_::operator()(&rc, v19);
  if ( *((_DWORD *)v19 + 17) != 2 )
    *((_DWORD *)v19 + 17) = 1;
  if ( (*((_DWORD *)a2 + 186) & 0x18000) != 0 && CGroupingStoryboard::_IsPartOfGroup(this, a2) )
  {
    CGroupingStoryboard::_CreateGuttersForApp(this, a2, &v26, &v26, v5, &v23, &v24);
    v7 = v23;
    if ( v23 )
      CGroupingStoryboard::_Create3DComponent_::_44_::_lambda_1_::operator()(&rc, v23);
    v8 = v24;
    if ( v24 )
      CGroupingStoryboard::_Create3DComponent_::_44_::_lambda_1_::operator()(&rc, v24);
  }
LABEL_35:
  if ( v22 )
    CBaseObject::Release(v22);
  if ( v7 )
    CBaseObject::Release(v7);
  if ( v8 )
    CBaseObject::Release(v8);
  return v6;
}

```

## disassembly

```asm
0x18008dfc8  mov     [rsp-8+arg_10], rbx
0x18008dfcd  push    rbp
0x18008dfce  push    rsi
0x18008dfcf  push    rdi
0x18008dfd0  push    r12
0x18008dfd2  push    r13
0x18008dfd4  push    r14
0x18008dfd6  push    r15
0x18008dfd8  lea     rbp, [rsp-27h]
0x18008dfdd  sub     rsp, 90h
0x18008dfe4  mov     rax, cs:__security_cookie
0x18008dfeb  xor     rax, rsp
0x18008dfee  mov     [rbp+57h+var_38], rax
0x18008dff2  xor     ebx, ebx
0x18008dff4  mov     r12, rcx
0x18008dff7  mov     rdi, rdx
0x18008dffa  mov     [rbp+57h+var_70], rbx
0x18008dffe  mov     edx, [rdx+2E8h]
0x18008e004  xorps   xmm0, xmm0
0x18008e007  mov     r13d, edx
0x18008e00a  mov     [rbp+57h+var_68], rbx
0x18008e00e  and     r13d, 0FFFh
0x18008e015  mov     [rbp+57h+var_60], rbx
0x18008e019  mov     ecx, r13d
0x18008e01c  mov     esi, ebx
0x18008e01e  mov     r15d, ebx
0x18008e021  mov     r14d, ebx
0x18008e024  movups  xmmword ptr [rbp+57h+var_48.left], xmm0
0x18008e028  sub     ecx, 1
0x18008e02b  jz      loc_18008E0C9
0x18008e031  sub     ecx, 2
0x18008e034  jz      loc_18008E0C9
0x18008e03a  sub     ecx, 1
0x18008e03d  jz      loc_18008E0C9
0x18008e043  cmp     ecx, 1Ah
0x18008e046  jnz     loc_18008E23F
0x18008e04c  lea     r9, [rbp+57h+rc]; struct tagRECT **
0x18008e050  mov     qword ptr [rbp+57h+rc.left], rbx
0x18008e054  lea     r8, [rbp+57h+var_48]; struct tagRECT *
0x18008e058  mov     [rsp+0C0h+var_A0], rbx; struct tagRECT *
0x18008e05d  xor     edx, edx; struct tagRECT *
0x18008e05f  mov     rcx, rdi; struct CWindowData *
0x18008e062  call    ?_GetIdealRects@CStoryboard@@KAXPEAVCWindowData@@PEBUtagRECT@@PEAU3@PEAPEAU3@23@Z; CStoryboard::_GetIdealRects(CWindowData *,tagRECT const *,tagRECT *,tagRECT * *,tagRECT *,tagRECT * *)
0x18008e067  mov     rax, [r12]
0x18008e06b  mov     rcx, r12
0x18008e06e  mov     edx, [rdi+2E8h]
0x18008e074  mov     rax, [rax+70h]
0x18008e078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e07d  mov     r9d, eax; int
0x18008e080  xor     r8d, r8d; bool
0x18008e083  lea     rax, [rbp+57h+var_70]
0x18008e087  mov     rdx, rdi; struct CWindowData *
0x18008e08a  mov     [rsp+0C0h+var_88], rax; struct CAnimationComponent **
0x18008e08f  mov     rcx, r12; this
0x18008e092  mov     rax, qword ptr [rbp+57h+rc.left]
0x18008e096  mov     [rsp+0C0h+var_90], 0FFFFFFFFh; int
0x18008e09e  mov     [rsp+0C0h+var_98], rbx; struct tagRECT *
0x18008e0a3  mov     [rsp+0C0h+var_A0], rax; struct tagRECT *
0x18008e0a8  call    ?_CreateAndAddAnimationComponentWithRect@CStoryboard@@IEAAJPEAVCWindowData@@_NHPEAUtagRECT@@2HPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddAnimationComponentWithRect(CWindowData *,bool,int,tagRECT *,tagRECT *,int,CAnimationComponent * *)
0x18008e0ad  mov     esi, eax
0x18008e0af  test    eax, eax
0x18008e0b1  jns     loc_18008E23F
0x18008e0b7  mov     [rsp+0C0h+var_98], rbx
0x18008e0bc  mov     dword ptr [rsp+0C0h+var_A0], 87Ah
0x18008e0c4  jmp     loc_18008E2FC
0x18008e0c9  cmp     dword ptr [rdi+80h], 1
0x18008e0d0  jnz     short loc_18008E0DC
0x18008e0d2  bts     edx, 1Ah
0x18008e0d6  mov     [rdi+2E8h], edx
0x18008e0dc  bt      edx, 1Ch
0x18008e0e0  jnb     short loc_18008E0EE
0x18008e0e2  mov     rcx, rdi; struct CWindowData *
0x18008e0e5  call    ?GetClonableOwnedWindowCount@CTransitionVisualController@@SAHPEAVCWindowData@@@Z; CTransitionVisualController::GetClonableOwnedWindowCount(CWindowData *)
0x18008e0ea  test    eax, eax
0x18008e0ec  jg      short loc_18008E0F1
0x18008e0ee  mov     sil, 1
0x18008e0f1  test    dword ptr [rdi+2E8h], 1000000h
0x18008e0fb  jz      loc_18008E1C9
0x18008e101  lea     rcx, [rdi+2ECh]; lprc
0x18008e108  call    cs:__imp_IsRectEmpty
0x18008e10e  test    eax, eax
0x18008e110  jnz     loc_18008E1C9
0x18008e116  xorps   xmm0, xmm0
0x18008e119  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18008e11d  cmp     r13d, 1
0x18008e121  jnz     short loc_18008E149
0x18008e123  movups  xmm0, xmmword ptr [rdi+2FCh]
0x18008e12a  lea     rcx, [rbp+57h+rc]; lprc
0x18008e12e  movq    rdx, xmm0
0x18008e133  mov     r8, rdx
0x18008e136  neg     edx; dx
0x18008e138  shr     r8, 20h
0x18008e13c  neg     r8d; dy
0x18008e13f  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18008e143  call    cs:__imp_OffsetRect
0x18008e149  mov     edx, [rdi+2E8h]
0x18008e14f  lea     rbx, [rbp+57h+rc]
0x18008e153  xor     eax, eax
0x18008e155  mov     rcx, r12
0x18008e158  cmp     r13d, 1
0x18008e15c  cmovnz  rbx, rax
0x18008e160  mov     rax, [r12]
0x18008e164  mov     rax, [rax+70h]
0x18008e168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e16d  mov     r9d, eax; int
0x18008e170  xor     r8d, r8d; bool
0x18008e173  lea     rax, [rbp+57h+var_70]
0x18008e177  mov     rdx, rdi; struct CWindowData *
0x18008e17a  mov     [rsp+0C0h+var_80], rax; struct CAnimationComponent **
0x18008e17f  mov     rcx, r12; this
0x18008e182  mov     byte ptr [rsp+0C0h+var_88], sil; bool
0x18008e187  lea     rax, [rdi+2ECh]
0x18008e18e  mov     [rsp+0C0h+var_90], 0FFFFFFFFh; int
0x18008e196  mov     [rsp+0C0h+var_98], rbx; struct tagRECT *
0x18008e19b  mov     [rsp+0C0h+var_A0], rax; struct tagRECT *
0x18008e1a0  call    ?_CreateAndAddAnimationComponentControlReuse@CStoryboard@@IEAAJPEAVCWindowData@@_NHPEAUtagRECT@@2H1PEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddAnimationComponentControlReuse(CWindowData *,bool,int,tagRECT *,tagRECT *,int,bool,CAnimationComponent * *)
0x18008e1a5  mov     esi, eax
0x18008e1a7  test    eax, eax
0x18008e1a9  js      short loc_18008E1B7
0x18008e1ab  movups  xmm0, xmmword ptr [rdi+2FCh]
0x18008e1b2  jmp     loc_18008E23A
0x18008e1b7  mov     [rsp+0C0h+var_98], r14
0x18008e1bc  mov     dword ptr [rsp+0C0h+var_A0], 862h
0x18008e1c4  jmp     loc_18008E2FC
0x18008e1c9  mov     rax, [r12]
0x18008e1cd  mov     rcx, r12
0x18008e1d0  mov     edx, [rdi+2E8h]
0x18008e1d6  mov     rax, [rax+70h]
0x18008e1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e1df  mov     r9d, eax; int
0x18008e1e2  xor     r8d, r8d; bool
0x18008e1e5  lea     rax, [rbp+57h+var_70]
0x18008e1e9  mov     rdx, rdi; struct CWindowData *
0x18008e1ec  mov     [rsp+0C0h+var_80], rax; struct CAnimationComponent **
0x18008e1f1  mov     rcx, r12; this
0x18008e1f4  mov     byte ptr [rsp+0C0h+var_88], sil; bool
0x18008e1f9  mov     [rsp+0C0h+var_90], 0FFFFFFFFh; int
0x18008e201  mov     [rsp+0C0h+var_98], rbx; struct tagRECT *
0x18008e206  mov     [rsp+0C0h+var_A0], rbx; struct tagRECT *
0x18008e20b  call    ?_CreateAndAddAnimationComponentControlReuse@CStoryboard@@IEAAJPEAVCWindowData@@_NHPEAUtagRECT@@2H1PEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddAnimationComponentControlReuse(CWindowData *,bool,int,tagRECT *,tagRECT *,int,bool,CAnimationComponent * *)
0x18008e210  mov     esi, eax
0x18008e212  test    eax, eax
0x18008e214  js      loc_18008E2EF
0x18008e21a  cmp     dword ptr [rdi+80h], 1
0x18008e221  jnz     short loc_18008E232
0x18008e223  lea     rcx, [rdi+30h]; struct tagRECT *
0x18008e227  lea     rdx, [rbp+57h+var_48]; struct tagRECT *
0x18008e22b  call    ?GetMonitorRectFromRectImpl@CTransitionVisualController@@KAXPEBUtagRECT@@PEAU2@@Z; CTransitionVisualController::GetMonitorRectFromRectImpl(tagRECT const *,tagRECT *)
0x18008e230  jmp     short loc_18008E23F
0x18008e232  mov     rax, [rbp+57h+var_70]
0x18008e236  movups  xmm0, xmmword ptr [rax+58h]
0x18008e23a  movdqu  xmmword ptr [rbp+57h+var_48.left], xmm0
0x18008e23f  mov     rbx, [rbp+57h+var_70]
0x18008e243  lea     rdx, [rbp+57h+var_48]; struct tagRECT *
0x18008e247  mov     qword ptr [rbp+57h+rc.left], r12
0x18008e24b  mov     rcx, [rbx+28h]; this
0x18008e24f  call    ?SetBeginRect@CAnimatedTransitionVisual@@QEAAXPEBUtagRECT@@@Z; CAnimatedTransitionVisual::SetBeginRect(tagRECT const *)
0x18008e254  mov     rcx, [rbx+28h]; this
0x18008e258  lea     rdx, [rbp+57h+var_48]; struct tagRECT *
0x18008e25c  call    ?SetEndRect@CAnimatedTransitionVisual@@QEAAXPEBUtagRECT@@@Z; CAnimatedTransitionVisual::SetEndRect(tagRECT const *)
0x18008e261  mov     rdx, rbx
0x18008e264  lea     rcx, [rbp+57h+rc]
0x18008e268  call    _CGroupingStoryboard___Create3DComponent____44____lambda_1___operator__
0x18008e26d  cmp     dword ptr [rbx+44h], 2
0x18008e271  jz      short loc_18008E27A
0x18008e273  mov     dword ptr [rbx+44h], 1
0x18008e27a  test    dword ptr [rdi+2E8h], 18000h
0x18008e284  jz      loc_18008E315
0x18008e28a  mov     rdx, rdi; struct CWindowData *
0x18008e28d  mov     rcx, r12; this
0x18008e290  call    ?_IsPartOfGroup@CGroupingStoryboard@@IEAA_NPEAVCWindowData@@@Z; CGroupingStoryboard::_IsPartOfGroup(CWindowData *)
0x18008e295  test    al, al
0x18008e297  jz      short loc_18008E315
0x18008e299  lea     rax, [rbp+57h+var_60]
0x18008e29d  mov     rdx, rdi
0x18008e2a0  mov     qword ptr [rsp+0C0h+var_90], rax
0x18008e2a5  lea     r9, [rbp+57h+var_48]
0x18008e2a9  lea     rax, [rbp+57h+var_68]
0x18008e2ad  mov     rcx, r12
0x18008e2b0  mov     [rsp+0C0h+var_98], rax
0x18008e2b5  lea     r8, [rbp+57h+var_48]
0x18008e2b9  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x18008e2be  call    ?_CreateGuttersForApp@CGroupingStoryboard@@IEAAJPEAVCWindowData@@PEBUtagRECT@@1W4DWMTRANSITION_TARGET@@PEAPEAVCAnimationComponent@@3@Z; CGroupingStoryboard::_CreateGuttersForApp(CWindowData *,tagRECT const *,tagRECT const *,DWMTRANSITION_TARGET,CAnimationComponent * *,CAnimationComponent * *)
0x18008e2c3  mov     r15, [rbp+57h+var_68]
0x18008e2c7  test    r15, r15
0x18008e2ca  jz      short loc_18008E2D8
0x18008e2cc  mov     rdx, r15
0x18008e2cf  lea     rcx, [rbp+57h+rc]
0x18008e2d3  call    _CGroupingStoryboard___Create3DComponent____44____lambda_1___operator__
0x18008e2d8  mov     r14, [rbp+57h+var_60]
0x18008e2dc  test    r14, r14
0x18008e2df  jz      short loc_18008E315
0x18008e2e1  mov     rdx, r14
0x18008e2e4  lea     rcx, [rbp+57h+rc]
0x18008e2e8  call    _CGroupingStoryboard___Create3DComponent____44____lambda_1___operator__
0x18008e2ed  jmp     short loc_18008E315
0x18008e2ef  mov     [rsp+0C0h+var_98], rbx; void *
0x18008e2f4  mov     dword ptr [rsp+0C0h+var_A0], 867h; unsigned int
0x18008e2fc  mov     r8d, 1; unsigned int
0x18008e302  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CStoryboard@@2QBJB; int *
0x18008e309  mov     r9d, eax; int
0x18008e30c  lea     ecx, [r8+13h]; unsigned int
0x18008e310  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18008e315  mov     rbx, [rbp+57h+var_70]
0x18008e319  test    rbx, rbx
0x18008e31c  jz      short loc_18008E326
0x18008e31e  mov     rcx, rbx; this
0x18008e321  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x18008e326  test    r15, r15
0x18008e329  jz      short loc_18008E333
0x18008e32b  mov     rcx, r15; this
0x18008e32e  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x18008e333  test    r14, r14
0x18008e336  jz      short loc_18008E340
0x18008e338  mov     rcx, r14; this
0x18008e33b  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x18008e340  mov     eax, esi
0x18008e342  mov     rcx, [rbp+57h+var_38]
0x18008e346  xor     rcx, rsp; StackCookie
0x18008e349  call    __security_check_cookie
0x18008e34e  mov     rbx, [rsp+0C0h+arg_10]
0x18008e356  add     rsp, 90h
0x18008e35d  pop     r15
0x18008e35f  pop     r14
0x18008e361  pop     r13
0x18008e363  pop     r12
0x18008e365  pop     rdi
0x18008e366  pop     rsi
0x18008e367  pop     rbp
0x18008e368  retn
```
