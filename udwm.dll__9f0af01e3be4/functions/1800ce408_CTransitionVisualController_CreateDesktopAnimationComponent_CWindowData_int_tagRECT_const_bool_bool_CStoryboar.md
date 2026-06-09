# CTransitionVisualController::CreateDesktopAnimationComponent(CWindowData *,int,tagRECT const &,bool,bool,CStoryboard *,CAnimationComponent * *)

- ea: `0x1800ce408`
- end: `0x1800cea7f`
- name: `?CreateDesktopAnimationComponent@CTransitionVisualController@@QEAAJPEAVCWindowData@@HAEBUtagRECT@@_N2PEAVCStoryboard@@PEAPEAVCAnimationComponent@@@Z`
- size: `1655`
- prototype: `__int64 __usercall@<rax>(CTransitionVisualController *__hidden this@<rcx>, struct CWindowData *@<rdx>, int@<r8d>, const struct tagRECT *@<r9>, bool, bool, struct CStoryboard *, struct CAnimationComponent **)`
- caller_count: `3`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x180068c60`
- `0x1800c48b0`
- `0x1800c5464`

## callees

- `0x180004108`
- `0x180005948`
- `0x1800079bc`
- `0x180008100`
- `0x18001ce00`
- `0x18001d6fc`
- `0x18001f43c`
- `0x18002f4f0`
- `0x180045f40`
- `0x180063e00`
- `0x180071758`
- `0x180076a64`
- `0x180080914`
- `0x18008093c`
- `0x1800814c8`
- `0x180083af0`
- `0x18008a1ac`
- `0x180091400`
- `0x180095130`
- `0x18009bf78`
- `0x18009c090`
- `0x18009c4e8`
- `0x18009e014`
- `0x1800b195c`
- `0x1800b19fc`
- `0x1800ce408`
- `0x1800cf99c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800ce7d6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800ce81d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800ce7d6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800ce81d`
- `USER32!IsRectEmpty` at `0x1800ce880`
- `USER32!IsRectEmpty` at `0x1800ce880`
- `USER32!GetDesktopID` at `0x1800ce4c1`
- `USER32!GetDesktopID` at `0x1800ce4c1`
- `USER32!EqualRect` at `0x1800ce6b9`
- `USER32!EqualRect` at `0x1800ce6db`
- `USER32!EqualRect` at `0x1800ce6b9`
- `USER32!EqualRect` at `0x1800ce6db`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTransitionVisualController::CreateDesktopAnimationComponent(
        CTransitionVisualController *this,
        struct CWindowData *a2,
        int a3,
        const struct tagRECT *a4,
        bool a5,
        bool a6,
        struct CStoryboard *a7,
        struct CAnimationComponent **a8)
{
  CBaseObject *v11; // r14
  struct CPerMonitorDesktopThumbnail *v12; // r12
  CAnimatedTransitionVisual *v13; // rdi
  unsigned int v14; // esi
  unsigned int v15; // ebx
  int v16; // eax
  unsigned __int64 v17; // rcx
  HWND ShellWindowForDesktop; // rbx
  void *v19; // rax
  __int64 v20; // rsi
  int DesktopThumbnail; // eax
  int v22; // eax
  int PerMonitorDesktopThumbnail; // eax
  int v24; // eax
  int v25; // eax
  int VisualBrush; // eax
  RECT v27; // xmm6
  int v28; // r9d
  bool v29; // sf
  int v30; // eax
  int v31; // ecx
  int v32; // edx
  int v33; // eax
  int v34; // r10d
  _DWORD *VisualBrushSourceRect; // rax
  int v36; // r9d
  int v37; // r10d
  int v38; // ecx
  int v39; // r14d
  int v40; // r13d
  int v41; // eax
  int v42; // edx
  int v43; // r14d
  int v44; // eax
  int v45; // edx
  int v46; // edx
  unsigned int v48; // [rsp+28h] [rbp-D1h]
  CAnimatedTransitionVisual *v49; // [rsp+58h] [rbp-A1h] BYREF
  int v50[2]; // [rsp+60h] [rbp-99h]
  struct CPerMonitorDesktopThumbnail *v51; // [rsp+68h] [rbp-91h] BYREF
  CBaseObject *v52; // [rsp+70h] [rbp-89h] BYREF
  unsigned __int64 v53; // [rsp+78h] [rbp-81h] BYREF
  RECT rc; // [rsp+88h] [rbp-71h] BYREF
  int v55; // [rsp+98h] [rbp-61h]
  struct CStoryboard *v56; // [rsp+A0h] [rbp-59h]
  struct CAnimationComponent **v57; // [rsp+A8h] [rbp-51h]
  const struct tagRECT *v58; // [rsp+B0h] [rbp-49h]
  __int128 v59; // [rsp+B8h] [rbp-41h] BYREF
  RECT rc2; // [rsp+C8h] [rbp-31h] BYREF

  v58 = a4;
  v50[0] = a3;
  v56 = a7;
  v57 = a8;
  v11 = 0;
  v52 = 0;
  v12 = 0;
  v51 = 0;
  v13 = 0;
  v49 = 0;
  v14 = *((_DWORD *)a2 + 186) & 0xFFF;
  v55 = (*(__int64 (__fastcall **)(struct CStoryboard *, _QWORD))(*(_QWORD *)a7 + 120LL))(a7, v14) & 0x10;
  v59 = 0;
  rc2 = *a4;
  if ( v55 )
    CTransitionVisualController::GetMonitorRectFromRectImpl(a4, &rc2);
  v53 = 0;
  if ( !(unsigned int)GetDesktopID(1, &v53) )
  {
    v48 = 1323;
LABEL_5:
    v15 = -2147467259;
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      -2147467259,
      v48,
      0);
    goto LABEL_77;
  }
  v16 = CTransitionVisualController::_SetDesktopId(this, v53);
  v15 = v16;
  if ( v16 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      v16,
      0x52Fu,
      0);
    goto LABEL_71;
  }
  ShellWindowForDesktop = CWindowList::GetShellWindowForDesktop(
                            *((CWindowList **)CDesktopManager::s_pDesktopManagerInstance + 53),
                            v53);
  if ( !ShellWindowForDesktop )
  {
    v48 = 1332;
    goto LABEL_5;
  }
  v19 = CAnimationComponent::operator new(v17);
  *(_QWORD *)&rc.left = v19;
  if ( !v19
    || (v20 = CAnimationComponent::CAnimationComponent(v19, ShellWindowForDesktop, v14, (unsigned int)v50[0], v56)) == 0 )
  {
    v15 = -2147024882;
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      -2147024882,
      0x538u,
      0);
    goto LABEL_71;
  }
  DesktopThumbnail = CDesktopThumbnail::GetDesktopThumbnail(&v52);
  v15 = DesktopThumbnail;
  if ( DesktopThumbnail < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      DesktopThumbnail,
      0x53Au,
      0);
LABEL_67:
    v11 = v52;
    goto LABEL_68;
  }
  v11 = v52;
  v22 = CDesktopThumbnailBase::SetDesktopId(v52, v53);
  v15 = v22;
  if ( v22 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      v22,
      0x53Bu,
      0);
    goto LABEL_68;
  }
  rc = rc2;
  PerMonitorDesktopThumbnail = CDesktopThumbnail::GetPerMonitorDesktopThumbnail(v11, &rc, &v51);
  v15 = PerMonitorDesktopThumbnail;
  if ( PerMonitorDesktopThumbnail < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      PerMonitorDesktopThumbnail,
      0x53Cu,
      0);
    v12 = v51;
    goto LABEL_68;
  }
  v24 = CAnimatedTransitionVisual::Create(&v49);
  v15 = v24;
  if ( v24 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      v24,
      0x53Eu,
      0);
    v12 = v51;
    goto LABEL_62;
  }
  if ( a5 )
    *(_BYTE *)(v20 + 67) = 1;
  v12 = v51;
  if ( !a6 || CDesktopThumbnail::IsDesktopThumbnailInSnapshot() )
  {
    VisualBrush = CDesktopThumbnailCVI::GetVisualBrush(v12, (struct CVisualBrush *)&v59);
    v15 = VisualBrush;
    if ( VisualBrush >= 0 )
    {
      v13 = v49;
      CAnimatedTransitionVisual::SetSharedVisualBrush(v49, (const struct CVisualBrush *)&v59);
      goto LABEL_23;
    }
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      VisualBrush,
      0x54Bu,
      0);
LABEL_62:
    v13 = v49;
    goto LABEL_68;
  }
  v13 = v49;
  v25 = CAnimatedTransitionVisual::SetVisual(v49, v11, 1, &rc2);
  v15 = v25;
  if ( v25 >= 0 )
  {
LABEL_23:
    CAnimatedTransitionVisual::SetTransitionStoryboardAndTarget(v13, *((_DWORD *)v56 + 18), v50[0]);
    *((_BYTE *)v13 + 908) = CStoryboard::IsRTL();
    CAnimationComponent::SetTransitionVisual((CAnimationComponent *)v20, v13);
    CAnimationComponent::SetDesktopThumbnailVisual((CAnimationComponent *)v20, v12);
    rc = 0;
    if ( (*((_DWORD *)a2 + 186) & 0x1000000) != 0 && EqualRect((const RECT *)((char *)a2 + 748), &rc2)
      || (*((_DWORD *)a2 + 186) & 0x800000) != 0 && EqualRect((const RECT *)((char *)a2 + 780), &rc2) )
    {
      v27 = rc2;
    }
    else
    {
      CTransitionVisualController::GetMonitorRectFromRectImpl(&rc2, &rc);
      v27 = rc;
    }
    *(RECT *)(v20 + 88) = v27;
    v49 = 0;
    if ( a6 )
    {
      v51 = 0;
      v28 = 0;
      if ( rc2.right - rc2.left >= 0 )
        v28 = rc2.right - rc2.left;
      v29 = rc2.bottom - rc2.top < 0;
      v30 = rc2.bottom - rc2.top;
    }
    else
    {
      rc = 0;
      CTransitionVisualController::GetMonitorRectFromRectImpl(&rc2, &rc);
      v31 = _mm_cvtsi128_si32((__m128i)v27);
      LODWORD(v51) = v31 - rc.left;
      v32 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v27, 4));
      HIDWORD(v51) = v32 - rc.top;
      v33 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v27, 8)) - v31;
      v28 = 0;
      if ( v33 >= 0 )
        v28 = v33;
      v30 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v27, 12)) - v32;
      v29 = v30 < 0;
    }
    v34 = 0;
    if ( !v29 )
      v34 = v30;
    v49 = (CAnimatedTransitionVisual *)__PAIR64__(v34, v28);
    VisualBrushSourceRect = (_DWORD *)CDesktopThumbnailCVI::GetVisualBrushSourceRect(v12);
    v38 = VisualBrushSourceRect[1];
    v50[0] = v38;
    v39 = VisualBrushSourceRect[3];
    v40 = VisualBrushSourceRect[2] - *VisualBrushSourceRect;
    v41 = 0;
    if ( v40 >= 0 )
      v41 = v40;
    if ( v36 > v41 )
    {
      v42 = 0;
      if ( v40 >= 0 )
        v42 = v40;
      v37 = MulDiv(v37, v42, v36);
      HIDWORD(v49) = v37;
      v36 = v40;
      if ( v40 < 0 )
        v36 = 0;
      LODWORD(v49) = v36;
      v38 = v50[0];
    }
    v43 = v39 - v38;
    v44 = 0;
    if ( v43 >= 0 )
      v44 = v43;
    if ( v37 > v44 )
    {
      v45 = 0;
      if ( v43 >= 0 )
        v45 = v43;
      LODWORD(v49) = MulDiv(v36, v45, v37);
      if ( v43 < 0 )
        v43 = 0;
      HIDWORD(v49) = v43;
    }
    *((_QWORD *)v13 + 110) = v51;
    *((_QWORD *)v13 + 111) = v49;
    if ( v55 )
    {
      CAnimatedTransitionVisual::SetBeginClip(v13, (const struct tagRECT *)((char *)a2 + 748));
      CAnimatedTransitionVisual::SetEndClip(v13, (const struct tagRECT *)((char *)a2 + 780));
      *((_BYTE *)v13 + 922) = 1;
    }
    if ( !IsRectEmpty((const RECT *)((char *)a2 + 812)) )
    {
      *(_OWORD *)(v20 + 104) = *(_OWORD *)((char *)a2 + 812);
      *(_DWORD *)(v20 + 68) = 2;
    }
    *v57 = (struct CAnimationComponent *)v20;
    CBaseObject::AddRef((CBaseObject *)v20);
    if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
      McTemplateU0pddddddd_EtwEventWriteTransfer(
        (_DWORD)v58,
        v46,
        *((_QWORD *)a2 + 5),
        *((_DWORD *)v56 + 18),
        *((_DWORD *)a2 + 186),
        1,
        v58->left,
        v58->top,
        v58->bottom,
        v58->right);
    goto LABEL_67;
  }
  MilInstrumentationCheckHR_MaybeFailFast(
    0x14u,
    &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
    2u,
    v25,
    0x547u,
    0);
LABEL_68:
  CBaseObject::Release((CBaseObject *)v20);
LABEL_71:
  if ( v11 )
    CBaseObject::Release(v11);
  if ( v12 )
    CBaseObject::Release(v12);
  if ( v13 )
    CBaseObject::Release((CAnimatedTransitionVisual *)((char *)v13 + 8));
LABEL_77:
  CVisualBrush::~CVisualBrush((CVisualBrush *)&v59);
  return v15;
}

```

## disassembly

```asm
0x1800ce408  mov     rax, rsp
0x1800ce40b  push    rbp
0x1800ce40c  push    rbx
0x1800ce40d  push    rsi
0x1800ce40e  push    rdi
0x1800ce40f  push    r12
0x1800ce411  push    r13
0x1800ce413  push    r14
0x1800ce415  push    r15
0x1800ce417  lea     rbp, [rax-47h]
0x1800ce41b  sub     rsp, 0F8h
0x1800ce422  movaps  xmmword ptr [rax-58h], xmm6
0x1800ce426  mov     rax, cs:__security_cookie
0x1800ce42d  xor     rax, rsp
0x1800ce430  mov     [rbp+3Fh+var_60], rax
0x1800ce434  mov     rbx, r9
0x1800ce437  mov     [rbp+3Fh+var_88], rbx
0x1800ce43b  mov     [rsp+130h+var_D8], r8d
0x1800ce440  mov     r15, rdx
0x1800ce443  mov     r13, rcx
0x1800ce446  mov     rcx, [rbp+3Fh+arg_30]
0x1800ce44a  mov     [rbp+3Fh+var_98], rcx
0x1800ce44e  mov     rax, [rbp+3Fh+arg_38]
0x1800ce455  mov     [rbp+3Fh+var_90], rax
0x1800ce459  xor     r14d, r14d
0x1800ce45c  mov     [rsp+130h+var_C8], r14
0x1800ce461  xor     r12d, r12d
0x1800ce464  mov     [rsp+130h+var_D0], r12
0x1800ce469  xor     edi, edi
0x1800ce46b  mov     [rsp+130h+var_E0], rdi
0x1800ce470  mov     esi, [rdx+2E8h]
0x1800ce476  and     esi, 0FFFh
0x1800ce47c  mov     rax, [rcx]
0x1800ce47f  mov     edx, esi
0x1800ce481  mov     rax, [rax+78h]
0x1800ce485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce48a  and     eax, 10h
0x1800ce48d  mov     [rbp+3Fh+var_A0], eax
0x1800ce490  xorps   xmm0, xmm0
0x1800ce493  movdqu  [rbp+3Fh+var_80], xmm0
0x1800ce498  movups  xmm0, xmmword ptr [rbx]
0x1800ce49b  movdqu  xmmword ptr [rbp+3Fh+rc2.left], xmm0
0x1800ce4a0  jz      short loc_1800CE4AE
0x1800ce4a2  lea     rdx, [rbp+3Fh+rc2]; struct tagRECT *
0x1800ce4a6  mov     rcx, rbx; struct tagRECT *
0x1800ce4a9  call    ?GetMonitorRectFromRectImpl@CTransitionVisualController@@KAXPEBUtagRECT@@PEAU2@@Z; CTransitionVisualController::GetMonitorRectFromRectImpl(tagRECT const *,tagRECT *)
0x1800ce4ae  mov     [rsp+130h+var_C0], 0
0x1800ce4b7  lea     rdx, [rsp+130h+var_C0]
0x1800ce4bc  mov     ecx, 1
0x1800ce4c1  call    cs:__imp_GetDesktopID
0x1800ce4c7  test    eax, eax
0x1800ce4c9  jnz     short loc_1800CE500
0x1800ce4cb  mov     [rsp+130h+var_108], 0; void *
0x1800ce4d4  mov     [rsp+130h+var_110], 52Bh; unsigned int
0x1800ce4dc  mov     r9d, 80004005h; int
0x1800ce4e2  mov     ebx, r9d
0x1800ce4e5  mov     r8d, 2; unsigned int
0x1800ce4eb  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CTransitionVisualController@@2QBJB; int *
0x1800ce4f2  lea     ecx, [r8+12h]; unsigned int
0x1800ce4f6  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800ce4fb  jmp     loc_1800CEA4C
0x1800ce500  mov     rdx, [rsp+130h+var_C0]; unsigned __int64
0x1800ce505  mov     rcx, r13; this
0x1800ce508  call    ?_SetDesktopId@CTransitionVisualController@@IEAAJ_K@Z; CTransitionVisualController::_SetDesktopId(unsigned __int64)
0x1800ce50d  mov     ebx, eax
0x1800ce50f  xor     r13d, r13d
0x1800ce512  test    eax, eax
0x1800ce514  js      loc_1800CE9FD
0x1800ce51a  mov     rdx, [rsp+130h+var_C0]; unsigned __int64
0x1800ce51f  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800ce526  mov     rcx, [rcx+1A8h]; this
0x1800ce52d  call    ?GetShellWindowForDesktop@CWindowList@@QEAAPEAUHWND__@@_K@Z; CWindowList::GetShellWindowForDesktop(unsigned __int64)
0x1800ce532  mov     rbx, rax
0x1800ce535  test    rax, rax
0x1800ce538  jnz     short loc_1800CE549
0x1800ce53a  mov     [rsp+130h+var_108], r13
0x1800ce53f  mov     [rsp+130h+var_110], 534h
0x1800ce547  jmp     short loc_1800CE4DC
0x1800ce549  call    ??2CAnimationComponent@@SAPEAX_K@Z; CAnimationComponent::operator new(unsigned __int64)
0x1800ce54e  mov     qword ptr [rbp+3Fh+rc.left], rax
0x1800ce552  test    rax, rax
0x1800ce555  jz      loc_1800CE9E6
0x1800ce55b  mov     rcx, [rbp+3Fh+var_98]
0x1800ce55f  mov     qword ptr [rsp+130h+var_110], rcx
0x1800ce564  mov     r9d, [rsp+130h+var_D8]
0x1800ce569  mov     r8d, esi
0x1800ce56c  mov     rdx, rbx
0x1800ce56f  mov     rcx, rax
0x1800ce572  call    ??0CAnimationComponent@@QEAA@PEAUHWND__@@W4DWMTRANSITION_TARGET@@HPEAVCStoryboard@@@Z; CAnimationComponent::CAnimationComponent(HWND__ *,DWMTRANSITION_TARGET,int,CStoryboard *)
0x1800ce577  mov     rsi, rax
0x1800ce57a  test    rax, rax
0x1800ce57d  jz      loc_1800CE9E6
0x1800ce583  lea     rcx, [rsp+130h+var_C8]; struct CDesktopThumbnail **
0x1800ce588  call    ?GetDesktopThumbnail@CDesktopThumbnail@@SAJPEAPEAV1@@Z; CDesktopThumbnail::GetDesktopThumbnail(CDesktopThumbnail * *)
0x1800ce58d  mov     ebx, eax
0x1800ce58f  test    eax, eax
0x1800ce591  js      loc_1800CE9B1
0x1800ce597  mov     rdx, [rsp+130h+var_C0]; unsigned __int64
0x1800ce59c  mov     r14, [rsp+130h+var_C8]
0x1800ce5a1  mov     rcx, r14; this
0x1800ce5a4  call    ?SetDesktopId@CDesktopThumbnailBase@@QEAAJ_K@Z; CDesktopThumbnailBase::SetDesktopId(unsigned __int64)
0x1800ce5a9  mov     ebx, eax
0x1800ce5ab  test    eax, eax
0x1800ce5ad  js      loc_1800CE989
0x1800ce5b3  movaps  xmm0, xmmword ptr [rbp+3Fh+rc2.left]
0x1800ce5b7  movdqa  xmmword ptr [rbp+3Fh+rc.left], xmm0
0x1800ce5bc  lea     r8, [rsp+130h+var_D0]; struct CPerMonitorDesktopThumbnail **
0x1800ce5c1  lea     rdx, [rbp+3Fh+rc]; lprc
0x1800ce5c5  mov     rcx, r14; this
0x1800ce5c8  call    ?GetPerMonitorDesktopThumbnail@CDesktopThumbnail@@QEAAJUtagRECT@@PEAPEAVCPerMonitorDesktopThumbnail@@@Z; CDesktopThumbnail::GetPerMonitorDesktopThumbnail(tagRECT,CPerMonitorDesktopThumbnail * *)
0x1800ce5cd  mov     ebx, eax
0x1800ce5cf  test    eax, eax
0x1800ce5d1  js      loc_1800CE95C
0x1800ce5d7  lea     rcx, [rsp+130h+var_E0]; struct CAnimatedTransitionVisual **
0x1800ce5dc  call    ?Create@CAnimatedTransitionVisual@@SAJPEAPEAV1@@Z; CAnimatedTransitionVisual::Create(CAnimatedTransitionVisual * *)
0x1800ce5e1  mov     ebx, eax
0x1800ce5e3  test    eax, eax
0x1800ce5e5  js      loc_1800CE927
0x1800ce5eb  cmp     [rbp+3Fh+arg_20], r13b
0x1800ce5ef  jz      short loc_1800CE5F5
0x1800ce5f1  mov     byte ptr [rsi+43h], 1
0x1800ce5f5  mov     r12, [rsp+130h+var_D0]
0x1800ce5fa  mov     r13b, [rbp+3Fh+arg_28]
0x1800ce5fe  test    r13b, r13b
0x1800ce601  jz      short loc_1800CE63E
0x1800ce603  call    ?IsDesktopThumbnailInSnapshot@CDesktopThumbnail@@SA_NXZ; CDesktopThumbnail::IsDesktopThumbnailInSnapshot(void)
0x1800ce608  test    al, al
0x1800ce60a  jnz     short loc_1800CE63E
0x1800ce60c  lea     r9, [rbp+3Fh+rc2]; struct tagRECT *
0x1800ce610  mov     r8b, 1; bool
0x1800ce613  mov     rdx, r14; struct CVisual *
0x1800ce616  mov     rdi, [rsp+130h+var_E0]
0x1800ce61b  mov     rcx, rdi; this
0x1800ce61e  call    ?SetVisual@CAnimatedTransitionVisual@@QEAAJPEAVCVisual@@_NPEBUtagRECT@@@Z; CAnimatedTransitionVisual::SetVisual(CVisual *,bool,tagRECT const *)
0x1800ce623  mov     ebx, eax
0x1800ce625  test    eax, eax
0x1800ce627  jns     short loc_1800CE665
0x1800ce629  xor     r13d, r13d
0x1800ce62c  mov     [rsp+130h+var_108], r13
0x1800ce631  mov     [rsp+130h+var_110], 547h
0x1800ce639  jmp     loc_1800CE996
0x1800ce63e  lea     rdx, [rbp+3Fh+var_80]; struct CVisualBrush *
0x1800ce642  mov     rcx, r12; this
0x1800ce645  call    ?GetVisualBrush@CDesktopThumbnailCVI@@QEAAJPEAVCVisualBrush@@@Z; CDesktopThumbnailCVI::GetVisualBrush(CVisualBrush *)
0x1800ce64a  mov     ebx, eax
0x1800ce64c  test    eax, eax
0x1800ce64e  js      loc_1800CE8FE
0x1800ce654  lea     rdx, [rbp+3Fh+var_80]; struct CVisualBrush *
0x1800ce658  mov     rdi, [rsp+130h+var_E0]
0x1800ce65d  mov     rcx, rdi; this
0x1800ce660  call    ?SetSharedVisualBrush@CAnimatedTransitionVisual@@QEAAXAEBVCVisualBrush@@@Z; CAnimatedTransitionVisual::SetSharedVisualBrush(CVisualBrush const &)
0x1800ce665  mov     r8d, [rsp+130h+var_D8]; int
0x1800ce66a  mov     rax, [rbp+3Fh+var_98]
0x1800ce66e  mov     edx, [rax+48h]; int
0x1800ce671  mov     rcx, rdi; this
0x1800ce674  call    ?SetTransitionStoryboardAndTarget@CAnimatedTransitionVisual@@QEAAXHH@Z; CAnimatedTransitionVisual::SetTransitionStoryboardAndTarget(int,int)
0x1800ce679  call    ?IsRTL@CStoryboard@@SA_NXZ; CStoryboard::IsRTL(void)
0x1800ce67e  mov     [rdi+38Ch], al
0x1800ce684  mov     rdx, rdi; struct CAnimatedTransitionVisual *
0x1800ce687  mov     rcx, rsi; this
0x1800ce68a  call    ?SetTransitionVisual@CAnimationComponent@@QEAAXPEAVCAnimatedTransitionVisual@@@Z; CAnimationComponent::SetTransitionVisual(CAnimatedTransitionVisual *)
0x1800ce68f  mov     rdx, r12; struct CPerMonitorDesktopThumbnail *
0x1800ce692  mov     rcx, rsi; this
0x1800ce695  call    ?SetDesktopThumbnailVisual@CAnimationComponent@@QEAAXPEAVCPerMonitorDesktopThumbnail@@@Z; CAnimationComponent::SetDesktopThumbnailVisual(CPerMonitorDesktopThumbnail *)
0x1800ce69a  xorps   xmm0, xmm0
0x1800ce69d  movups  xmmword ptr [rbp+3Fh+rc.left], xmm0
0x1800ce6a1  test    dword ptr [r15+2E8h], 1000000h
0x1800ce6ac  jz      short loc_1800CE6C3
0x1800ce6ae  lea     rcx, [r15+2ECh]; lprc1
0x1800ce6b5  lea     rdx, [rbp+3Fh+rc2]; lprc2
0x1800ce6b9  call    cs:__imp_EqualRect
0x1800ce6bf  test    eax, eax
0x1800ce6c1  jnz     short loc_1800CE6E5
0x1800ce6c3  test    dword ptr [r15+2E8h], 800000h
0x1800ce6ce  jz      short loc_1800CE6EB
0x1800ce6d0  lea     rcx, [r15+30Ch]; lprc1
0x1800ce6d7  lea     rdx, [rbp+3Fh+rc2]; lprc2
0x1800ce6db  call    cs:__imp_EqualRect
0x1800ce6e1  test    eax, eax
0x1800ce6e3  jz      short loc_1800CE6EB
0x1800ce6e5  movaps  xmm6, xmmword ptr [rbp+3Fh+rc2.left]
0x1800ce6e9  jmp     short loc_1800CE6FC
0x1800ce6eb  lea     rdx, [rbp+3Fh+rc]; struct tagRECT *
0x1800ce6ef  lea     rcx, [rbp+3Fh+rc2]; struct tagRECT *
0x1800ce6f3  call    ?GetMonitorRectFromRectImpl@CTransitionVisualController@@KAXPEBUtagRECT@@PEAU2@@Z; CTransitionVisualController::GetMonitorRectFromRectImpl(tagRECT const *,tagRECT *)
0x1800ce6f8  movaps  xmm6, xmmword ptr [rbp+3Fh+rc.left]
0x1800ce6fc  movdqu  xmmword ptr [rsi+58h], xmm6
0x1800ce701  mov     [rsp+130h+var_E0], 0
0x1800ce70a  test    r13b, r13b
0x1800ce70d  jz      short loc_1800CE730
0x1800ce70f  mov     [rsp+130h+var_D0], 0
0x1800ce718  mov     eax, [rbp+3Fh+rc2.right]
0x1800ce71b  sub     eax, [rbp+3Fh+rc2.left]
0x1800ce71e  mov     r9d, 0
0x1800ce724  cmovns  r9d, eax
0x1800ce728  mov     eax, [rbp+3Fh+rc2.bottom]
0x1800ce72b  sub     eax, [rbp+3Fh+rc2.top]
0x1800ce72e  jmp     short loc_1800CE78B
0x1800ce730  xorps   xmm0, xmm0
0x1800ce733  movups  xmmword ptr [rbp+3Fh+rc.left], xmm0
0x1800ce737  lea     rdx, [rbp+3Fh+rc]; struct tagRECT *
0x1800ce73b  lea     rcx, [rbp+3Fh+rc2]; struct tagRECT *
0x1800ce73f  call    ?GetMonitorRectFromRectImpl@CTransitionVisualController@@KAXPEBUtagRECT@@PEAU2@@Z; CTransitionVisualController::GetMonitorRectFromRectImpl(tagRECT const *,tagRECT *)
0x1800ce744  movd    ecx, xmm6
0x1800ce748  mov     eax, ecx
0x1800ce74a  sub     eax, [rbp+3Fh+rc.left]
0x1800ce74d  mov     dword ptr [rsp+130h+var_D0], eax
0x1800ce751  movdqa  xmm0, xmm6
0x1800ce755  psrldq  xmm0, 4
0x1800ce75a  movd    edx, xmm0
0x1800ce75e  mov     eax, edx
0x1800ce760  sub     eax, [rbp+3Fh+rc.top]
0x1800ce763  mov     dword ptr [rsp+130h+var_D0+4], eax
0x1800ce767  movdqa  xmm0, xmm6
0x1800ce76b  psrldq  xmm0, 8
0x1800ce770  movd    eax, xmm0
0x1800ce774  sub     eax, ecx
0x1800ce776  mov     r9d, 0
0x1800ce77c  cmovns  r9d, eax
0x1800ce780  psrldq  xmm6, 0Ch
0x1800ce785  movd    eax, xmm6
0x1800ce789  sub     eax, edx
0x1800ce78b  mov     r10d, 0
0x1800ce791  cmovns  r10d, eax
0x1800ce795  mov     dword ptr [rsp+130h+var_E0+4], r10d
0x1800ce79a  mov     dword ptr [rsp+130h+var_E0], r9d
0x1800ce79f  mov     rcx, r12
0x1800ce7a2  call    ?GetVisualBrushSourceRect@CDesktopThumbnailCVI@@QEAAAEBV?$TMilRect_@HUtagRECT@@UMil3DRectL@@UD2D_POINTANDSIZE_L@@U_CMilRectL_@RectUniqueness@@@@XZ; CDesktopThumbnailCVI::GetVisualBrushSourceRect(void)
0x1800ce7a7  mov     ecx, [rax+4]
0x1800ce7aa  mov     [rsp+130h+var_D8], ecx
0x1800ce7ae  mov     r14d, [rax+0Ch]
0x1800ce7b2  mov     r13d, [rax+8]
0x1800ce7b6  sub     r13d, [rax]
0x1800ce7b9  mov     eax, 0
0x1800ce7be  cmovns  eax, r13d
0x1800ce7c2  cmp     r9d, eax
0x1800ce7c5  jle     short loc_1800CE7F8
0x1800ce7c7  xor     edx, edx
0x1800ce7c9  test    r13d, r13d
0x1800ce7cc  cmovns  edx, r13d; nNumerator
0x1800ce7d0  mov     r8d, r9d; nDenominator
0x1800ce7d3  mov     ecx, r10d; nNumber
0x1800ce7d6  call    cs:__imp_MulDiv
0x1800ce7dc  mov     r10d, eax
0x1800ce7df  mov     dword ptr [rsp+130h+var_E0+4], eax
0x1800ce7e3  mov     r9d, r13d
0x1800ce7e6  xor     eax, eax
0x1800ce7e8  test    r13d, r13d
0x1800ce7eb  cmovs   r9d, eax
0x1800ce7ef  mov     dword ptr [rsp+130h+var_E0], r9d
0x1800ce7f4  mov     ecx, [rsp+130h+var_D8]
0x1800ce7f8  sub     r14d, ecx
0x1800ce7fb  mov     r13d, 0
0x1800ce801  mov     eax, r13d
0x1800ce804  cmovns  eax, r14d
0x1800ce808  cmp     r10d, eax
0x1800ce80b  jle     short loc_1800CE833
0x1800ce80d  mov     edx, r13d
0x1800ce810  test    r14d, r14d
0x1800ce813  cmovns  edx, r14d; nNumerator
0x1800ce817  mov     r8d, r10d; nDenominator
0x1800ce81a  mov     ecx, r9d; nNumber
0x1800ce81d  call    cs:__imp_MulDiv
0x1800ce823  mov     dword ptr [rsp+130h+var_E0], eax
0x1800ce827  test    r14d, r14d
0x1800ce82a  cmovs   r14d, r13d
0x1800ce82e  mov     dword ptr [rsp+130h+var_E0+4], r14d
0x1800ce833  mov     rax, [rsp+130h+var_D0]
0x1800ce838  mov     [rdi+370h], rax
0x1800ce83f  mov     rax, [rsp+130h+var_E0]
0x1800ce844  mov     [rdi+378h], rax
0x1800ce84b  cmp     [rbp+3Fh+var_A0], r13d
0x1800ce84f  jz      short loc_1800CE876
0x1800ce851  lea     rdx, [r15+2ECh]; struct tagRECT *
0x1800ce858  mov     rcx, rdi; this
0x1800ce85b  call    ?SetBeginClip@CAnimatedTransitionVisual@@QEAAXPEBUtagRECT@@@Z; CAnimatedTransitionVisual::SetBeginClip(tagRECT const *)
0x1800ce860  lea     rdx, [r15+30Ch]; struct tagRECT *
0x1800ce867  mov     rcx, rdi; this
0x1800ce86a  call    ?SetEndClip@CAnimatedTransitionVisual@@QEAAXPEBUtagRECT@@@Z; CAnimatedTransitionVisual::SetEndClip(tagRECT const *)
0x1800ce86f  mov     byte ptr [rdi+39Ah], 1
0x1800ce876  lea     r14, [r15+32Ch]
0x1800ce87d  mov     rcx, r14; lprc
0x1800ce880  call    cs:__imp_IsRectEmpty
0x1800ce886  test    eax, eax
0x1800ce888  jnz     short loc_1800CE89A
0x1800ce88a  movups  xmm0, xmmword ptr [r14]
0x1800ce88e  movdqu  xmmword ptr [rsi+68h], xmm0
0x1800ce893  mov     dword ptr [rsi+44h], 2
0x1800ce89a  mov     rax, [rbp+3Fh+var_90]
0x1800ce89e  mov     [rax], rsi
0x1800ce8a1  mov     rcx, rsi; this
0x1800ce8a4  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x1800ce8a9  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x1800ce8b0  jz      loc_1800CE9D7
0x1800ce8b6  mov     rcx, [rbp+3Fh+var_88]
0x1800ce8ba  mov     eax, [rcx+8]
0x1800ce8bd  mov     dword ptr [rsp+130h+var_E8], eax
0x1800ce8c1  mov     eax, [rcx+0Ch]
0x1800ce8c4  mov     [rsp+130h+var_F0], eax
0x1800ce8c8  mov     eax, [rcx+4]
  ... truncated ...
```
