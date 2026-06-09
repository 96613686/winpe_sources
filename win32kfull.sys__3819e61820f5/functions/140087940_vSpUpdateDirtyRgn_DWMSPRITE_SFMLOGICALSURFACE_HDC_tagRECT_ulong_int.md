# vSpUpdateDirtyRgn(DWMSPRITE *,SFMLOGICALSURFACE *,HDC__ *,tagRECT *,ulong *,int)

- ea: `0x140087940`
- end: `0x140087ea7`
- name: `?vSpUpdateDirtyRgn@@YAXPEAVDWMSPRITE@@PEAVSFMLOGICALSURFACE@@PEAUHDC__@@PEAUtagRECT@@PEAKH@Z`
- size: `1383`
- prototype: `void(struct DWMSPRITE *, struct SFMLOGICALSURFACE *, HDC, struct tagRECT *, unsigned int *, int)`
- caller_count: `6`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400865c0`
- `0x1400883f8`
- `0x140093034`
- `0x1401a46fc`
- `0x140213748`
- `0x14033595c`

## callees

- `0x140001158`
- `0x14005fab8`
- `0x1400620a8`
- `0x140063ee0`
- `0x140087940`
- `0x14008be9c`
- `0x1400f8e58`
- `0x1400fb65c`
- `0x140137bac`
- `0x14019db7c`
- `0x14019dd20`
- `0x14021d158`
- `0x14026a7c8`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140087de1`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140087de1`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140087d71`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140087d71`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140087a80`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140087b6e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140087d86`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140087a80`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140087b6e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140087d86`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140087ae2`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140087b8c`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140087be7`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140087cf1`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140087ae2`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140087b8c`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140087be7`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140087cf1`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008798d`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1400879ac`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140087d44`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008798d`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1400879ac`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140087d44`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140087afc`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140087ba6`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140087c06`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140087d0a`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140087afc`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140087ba6`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140087c06`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140087d0a`
- `win32kbase!EtwTraceLifetimeAccum` at `0x140087a1e`
- `win32kbase!EtwTraceLifetimeAccum` at `0x140087a1e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1400879e9`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140087a06`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140087b0f`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140087bca`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1400879e9`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140087a06`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140087b0f`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140087bca`
- `win32kbase!EtwTranslationUpdateOffset` at `0x140087c28`
- `win32kbase!EtwTranslationUpdateOffset` at `0x140087c28`
- `win32kbase!EtwTranslationUpdate` at `0x140087c4e`
- `win32kbase!EtwTranslationUpdate` at `0x140087c4e`
- `win32kbase!EtwDirtyRectUpdate` at `0x140087c9c`
- `win32kbase!EtwDirtyRectUpdate` at `0x140087c9c`

## pseudocode

```c
void __fastcall vSpUpdateDirtyRgn(
        struct DWMSPRITE *a1,
        struct SFMLOGICALSURFACE *a2,
        HDC a3,
        struct _RECTL *a4,
        unsigned int *a5,
        int a6)
{
  struct REGION **v6; // rsi
  struct REGION *v7; // rax
  int v8; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  LONG v17; // ecx
  __int64 v18; // rcx
  struct REGION *v19; // rbx
  int v20; // eax
  int v21; // eax
  struct _RECTL v22; // xmm0
  int v23; // eax
  __int64 CurrentProcessWin32Process; // rax
  __int64 v25; // r8
  int v26; // ecx
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  struct REGION *v30; // [rsp+40h] [rbp-99h] BYREF
  __int64 v31; // [rsp+48h] [rbp-91h] BYREF
  __int64 v32; // [rsp+50h] [rbp-89h] BYREF
  struct REGION *v33; // [rsp+58h] [rbp-81h] BYREF
  struct REGION *v34; // [rsp+60h] [rbp-79h] BYREF
  __int64 v35; // [rsp+68h] [rbp-71h] BYREF
  _QWORD v36[8]; // [rsp+70h] [rbp-69h] BYREF
  struct _RECTL v37; // [rsp+B0h] [rbp-29h] BYREF
  struct _RECTL v38; // [rsp+C0h] [rbp-19h] BYREF

  v6 = (struct REGION **)((char *)a2 + 128);
  v7 = (struct REGION *)*((_QWORD *)a2 + 16);
  v8 = 0;
  if ( !v7 )
  {
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v30);
    v7 = v30;
    *v6 = v30;
  }
  if ( *((_QWORD *)a2 + 10) )
  {
    LODWORD(v33) = 0;
  }
  else
  {
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v30);
    SFMLOGICALSURFACE::vDirtyRegionAccum(a2, v30);
    v7 = *v6;
    LODWORD(v33) = 1;
  }
  if ( !*((_QWORD *)a2 + 23) )
  {
    v30 = v7;
    RGNOBJ::vSet((RGNOBJ *)&v30);
    if ( *((_QWORD *)a2 + 10) )
    {
      *(_QWORD *)&v37.left = *((_QWORD *)a2 + 10);
      RGNOBJ::vSet((RGNOBJ *)&v37);
      EtwTraceLifetimeAccum(*(_QWORD *)a2, 1);
    }
  }
  v34 = *v6;
  RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v31);
  RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v32);
  RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v35);
  if ( v34 && v31 && v32 && v35 )
  {
    RGNOBJ::vSet((RGNOBJ *)&v31, a4);
    if ( (*((_DWORD *)a2 + 63) & 1) == 0 || !a3 )
      goto LABEL_58;
    DCOBJA::DCOBJA((DCOBJA *)v36, a3);
    if ( v36[0] )
    {
      if ( (*(_DWORD *)(v36[0] + 36LL) & 1) != 0 )
      {
        *(_QWORD *)&v37.left = XDCOBJ::prgnEffRao((XDCOBJ *)v36);
        if ( *(_QWORD *)&v37.left )
        {
          if ( RGNOBJ::bMerge((RGNOBJ *)&v32, (struct RGNOBJ *)&v37, (struct RGNOBJ *)&v31, 8u) )
          {
            RGNOBJ::vSwap((RGNOBJ *)&v32, (struct RGNOBJ *)&v31);
            v8 = 1;
          }
          else
          {
            RGNOBJ::vSet((RGNOBJ *)&v32);
          }
        }
      }
    }
    DCOBJA::~DCOBJA((DCOBJA *)v36);
    if ( !v8 )
    {
LABEL_58:
      if ( !a1 )
        goto LABEL_27;
      RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v30);
      v37.right = *((_DWORD *)a1 + 16) - *((_DWORD *)a1 + 14);
      v17 = *((_DWORD *)a1 + 17) - *((_DWORD *)a1 + 15);
      *(_QWORD *)&v37.left = 0;
      v37.bottom = v17;
      if ( v30 )
      {
        RGNOBJ::vSet((RGNOBJ *)&v30, &v37);
        if ( RGNOBJ::bMerge((RGNOBJ *)&v32, (struct RGNOBJ *)&v31, (struct RGNOBJ *)&v30, 8u) )
        {
          RGNOBJ::vSwap((RGNOBJ *)&v32, (struct RGNOBJ *)&v31);
          v8 = 1;
        }
      }
      RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v30);
      if ( !v8 )
LABEL_27:
        RGNOBJ::vSet((RGNOBJ *)&v31);
    }
    if ( RGNOBJ::bMerge((RGNOBJ *)&v32, (struct RGNOBJ *)&v34, (struct RGNOBJ *)&v31, 0xEu) )
    {
      RGNOBJ::vSwap((RGNOBJ *)&v32, (struct RGNOBJ *)&v34);
      v18 = *(_QWORD *)a2;
      if ( a6 )
      {
        EtwTranslationUpdateOffset(v18, *((_QWORD *)a2 + 19), HIDWORD(*((_QWORD *)a2 + 19)));
        EtwTranslationUpdate(
          *(_QWORD *)a2,
          (unsigned int)a4->left,
          (unsigned int)a4->top,
          (unsigned int)a4->right,
          a4->bottom);
        v19 = v34;
        v20 = METAREGION::vApplyMoveData(
                (METAREGION *)v6,
                (struct _RECTL *)a2 + 7,
                (struct _POINTL *)a2 + 13,
                *((struct REGION **)a2 + 12));
        *v6 = v19;
        if ( v20 )
          METAREGION::vCalculateNoMoveDirty((METAREGION *)v6);
      }
      else
      {
        EtwDirtyRectUpdate(v18, (unsigned int)a4->left, (unsigned int)a4->top, (unsigned int)a4->right, a4->bottom);
        METAREGION::vDirtyRegionWithRect((METAREGION *)v6, v34, (struct tagRECT *)a4);
      }
      v21 = *((_DWORD *)a2 + 63);
      if ( (v21 & 2) == 0 )
      {
        *((_DWORD *)a2 + 63) = v21 | 2;
        *a5 |= 1u;
      }
    }
    if ( *((_QWORD *)a2 + 10) )
    {
      v30 = (struct REGION *)*((_QWORD *)a2 + 10);
      if ( RGNOBJ::bMerge((RGNOBJ *)&v35, (struct RGNOBJ *)&v30, (struct RGNOBJ *)&v31, 0xEu) )
      {
        RGNOBJ::vSwap((RGNOBJ *)&v35, (struct RGNOBJ *)&v30);
        SFMLOGICALSURFACE::vDirtyRegionAccum(a2, v30);
      }
      if ( !(_DWORD)v33 && (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v30) == 2 )
      {
        v38 = 0;
        RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v33);
        if ( v33 )
        {
          v22 = *(struct _RECTL *)((char *)v30 + 52);
          *(_QWORD *)&v37.left = *((_QWORD *)a2 + 10);
          v38 = v22;
          RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v37);
          RGNOBJ::vSet((RGNOBJ *)&v33, &v38);
          SFMLOGICALSURFACE::vDirtyRegionAccum(a2, v33);
        }
      }
    }
  }
  v23 = *((_DWORD *)a2 + 63);
  if ( (v23 & 0x20) != 0 )
  {
    if ( (v23 & 4) != 0 )
      *a5 |= 2u;
    *((_DWORD *)a2 + 63) &= ~0x20u;
  }
  if ( a1 )
  {
    if ( (*((_DWORD *)a1 + 34) & 2) != 0 && (*a5 & 1) != 0 )
    {
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v14, v13, v15, v16);
      if ( CurrentProcessWin32Process )
      {
        if ( *(_QWORD *)CurrentProcessWin32Process )
        {
          v26 = *(_DWORD *)(CurrentProcessWin32Process + 276);
          if ( (v26 & 2) == 0 )
          {
            *(_DWORD *)(CurrentProcessWin32Process + 276) = v26 | 2;
            if ( (unsigned int)dword_14039AA20 > 5 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_14039AA20, 0x400000000000LL, v25) )
              {
                *(_QWORD *)&v37.left = 0x2000000;
                LODWORD(v33) = 1;
                LODWORD(v30) = 1;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                  v27,
                  (unsigned int)&dword_14036CE54,
                  v28,
                  v29,
                  (__int64)&v30,
                  (__int64)&v33,
                  (__int64)&v37);
              }
            }
          }
        }
      }
    }
  }
  RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v35);
  RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v32);
  RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v31);
}

```

## disassembly

```asm
0x140087940  push    rbp
0x140087942  push    rbx
0x140087943  push    rsi
0x140087944  push    rdi
0x140087945  push    r12
0x140087947  push    r13
0x140087949  push    r14
0x14008794b  push    r15
0x14008794d  lea     rbp, [rsp-0Fh]
0x140087952  sub     rsp, 0E8h
0x140087959  mov     rax, cs:__security_cookie
0x140087960  xor     rax, rsp
0x140087963  mov     [rbp+47h+var_50], rax
0x140087967  mov     r15, [rbp+47h+arg_20]
0x14008796b  lea     rsi, [rdx+80h]
0x140087972  mov     rax, [rsi]
0x140087975  xor     ebx, ebx
0x140087977  mov     r12, r9
0x14008797a  mov     r13, r8
0x14008797d  mov     rdi, rdx
0x140087980  mov     r14, rcx
0x140087983  test    rax, rax
0x140087986  jnz     short loc_1400879A1
0x140087988  lea     rcx, [rsp+120h+var_E0]
0x14008798d  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x140087994  nop     dword ptr [rax+rax+00h]
0x140087999  mov     rax, [rsp+120h+var_E0]
0x14008799e  mov     [rsi], rax
0x1400879a1  cmp     [rdi+50h], rbx
0x1400879a5  jnz     short loc_1400879D2
0x1400879a7  lea     rcx, [rsp+120h+var_E0]
0x1400879ac  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1400879b3  nop     dword ptr [rax+rax+00h]
0x1400879b8  mov     rdx, [rsp+120h+var_E0]; struct REGION *
0x1400879bd  mov     rcx, rdi; this
0x1400879c0  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x1400879c5  mov     rax, [rsi]
0x1400879c8  mov     dword ptr [rsp+120h+var_C8], 1
0x1400879d0  jmp     short loc_1400879D6
0x1400879d2  mov     dword ptr [rsp+120h+var_C8], ebx
0x1400879d6  cmp     [rdi+0B8h], rbx
0x1400879dd  jnz     short loc_140087A2A
0x1400879df  lea     rcx, [rsp+120h+var_E0]
0x1400879e4  mov     [rsp+120h+var_E0], rax
0x1400879e9  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x1400879f0  nop     dword ptr [rax+rax+00h]
0x1400879f5  mov     rax, [rdi+50h]
0x1400879f9  test    rax, rax
0x1400879fc  jz      short loc_140087A2A
0x1400879fe  lea     rcx, [rbp+47h+var_70]
0x140087a02  mov     [rbp+47h+var_70], rax
0x140087a06  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x140087a0d  nop     dword ptr [rax+rax+00h]
0x140087a12  mov     r8, [rdi+50h]
0x140087a16  mov     edx, 1
0x140087a1b  mov     rcx, [rdi]
0x140087a1e  call    cs:__imp_EtwTraceLifetimeAccum
0x140087a25  nop     dword ptr [rax+rax+00h]
0x140087a2a  mov     rax, [rsi]
0x140087a2d  lea     rcx, [rsp+120h+var_D8]; this
0x140087a32  mov     [rbp+47h+var_C0], rax
0x140087a36  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x140087a3b  lea     rcx, [rsp+120h+var_D0]; this
0x140087a40  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x140087a45  lea     rcx, [rbp+47h+var_B8]; this
0x140087a49  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x140087a4e  cmp     [rbp+47h+var_C0], rbx
0x140087a52  jz      loc_140087D9F
0x140087a58  cmp     [rsp+120h+var_D8], rbx
0x140087a5d  jz      loc_140087D9F
0x140087a63  cmp     [rsp+120h+var_D0], rbx
0x140087a68  jz      loc_140087D9F
0x140087a6e  cmp     [rbp+47h+var_B8], rbx
0x140087a72  jz      loc_140087D9F
0x140087a78  mov     rdx, r12
0x140087a7b  lea     rcx, [rsp+120h+var_D8]
0x140087a80  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x140087a87  nop     dword ptr [rax+rax+00h]
0x140087a8c  mov     eax, [rdi+0FCh]
0x140087a92  test    al, 1
0x140087a94  jz      loc_140087B2C
0x140087a9a  test    r13, r13
0x140087a9d  jz      loc_140087B2C
0x140087aa3  mov     rdx, r13; HDC
0x140087aa6  lea     rcx, [rbp+47h+var_B0]; this
0x140087aaa  call    ??0DCOBJA@@QEAA@PEAUHDC__@@@Z; DCOBJA::DCOBJA(HDC__ *)
0x140087aaf  mov     rax, [rbp+47h+var_B0]
0x140087ab3  test    rax, rax
0x140087ab6  jz      short loc_140087B1B
0x140087ab8  mov     eax, [rax+24h]
0x140087abb  test    al, 1
0x140087abd  jz      short loc_140087B1B
0x140087abf  lea     rcx, [rbp+47h+var_B0]; this
0x140087ac3  call    ?prgnEffRao@XDCOBJ@@QEAAPEAVREGION@@XZ; XDCOBJ::prgnEffRao(void)
0x140087ac8  mov     [rbp+47h+var_70], rax
0x140087acc  test    rax, rax
0x140087acf  jz      short loc_140087B1B
0x140087ad1  mov     r9b, 8
0x140087ad4  lea     r8, [rsp+120h+var_D8]
0x140087ad9  lea     rdx, [rbp+47h+var_70]
0x140087add  lea     rcx, [rsp+120h+var_D0]
0x140087ae2  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x140087ae9  nop     dword ptr [rax+rax+00h]
0x140087aee  lea     rcx, [rsp+120h+var_D0]
0x140087af3  test    eax, eax
0x140087af5  jz      short loc_140087B0F
0x140087af7  lea     rdx, [rsp+120h+var_D8]
0x140087afc  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x140087b03  nop     dword ptr [rax+rax+00h]
0x140087b08  mov     ebx, 1
0x140087b0d  jmp     short loc_140087B1B
0x140087b0f  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x140087b16  nop     dword ptr [rax+rax+00h]
0x140087b1b  lea     rcx, [rbp+47h+var_B0]; this
0x140087b1f  call    ??1DCOBJA@@QEAA@XZ; DCOBJA::~DCOBJA(void)
0x140087b24  test    ebx, ebx
0x140087b26  jnz     loc_140087BD6
0x140087b2c  test    r14, r14
0x140087b2f  jz      loc_140087BC5
0x140087b35  lea     rcx, [rsp+120h+var_E0]; this
0x140087b3a  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x140087b3f  mov     ecx, [r14+40h]
0x140087b43  sub     ecx, [r14+38h]
0x140087b47  mov     [rbp+47h+var_68], ecx
0x140087b4a  mov     ecx, [r14+44h]
0x140087b4e  sub     ecx, [r14+3Ch]
0x140087b52  cmp     [rsp+120h+var_E0], 0
0x140087b58  mov     [rbp+47h+var_70], 0
0x140087b60  mov     [rbp+47h+var_64], ecx
0x140087b63  jz      short loc_140087BB7
0x140087b65  lea     rdx, [rbp+47h+var_70]
0x140087b69  lea     rcx, [rsp+120h+var_E0]
0x140087b6e  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x140087b75  nop     dword ptr [rax+rax+00h]
0x140087b7a  mov     r9b, 8
0x140087b7d  lea     r8, [rsp+120h+var_E0]
0x140087b82  lea     rdx, [rsp+120h+var_D8]
0x140087b87  lea     rcx, [rsp+120h+var_D0]
0x140087b8c  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x140087b93  nop     dword ptr [rax+rax+00h]
0x140087b98  test    eax, eax
0x140087b9a  jz      short loc_140087BB7
0x140087b9c  lea     rdx, [rsp+120h+var_D8]
0x140087ba1  lea     rcx, [rsp+120h+var_D0]
0x140087ba6  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x140087bad  nop     dword ptr [rax+rax+00h]
0x140087bb2  mov     ebx, 1
0x140087bb7  lea     rcx, [rsp+120h+var_E0]; this
0x140087bbc  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x140087bc1  test    ebx, ebx
0x140087bc3  jnz     short loc_140087BD6
0x140087bc5  lea     rcx, [rsp+120h+var_D8]
0x140087bca  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x140087bd1  nop     dword ptr [rax+rax+00h]
0x140087bd6  mov     r9b, 0Eh
0x140087bd9  lea     r8, [rsp+120h+var_D8]
0x140087bde  lea     rdx, [rbp+47h+var_C0]
0x140087be2  lea     rcx, [rsp+120h+var_D0]
0x140087be7  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x140087bee  nop     dword ptr [rax+rax+00h]
0x140087bf3  xor     ebx, ebx
0x140087bf5  test    eax, eax
0x140087bf7  jz      loc_140087CCE
0x140087bfd  lea     rdx, [rbp+47h+var_C0]
0x140087c01  lea     rcx, [rsp+120h+var_D0]
0x140087c06  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x140087c0d  nop     dword ptr [rax+rax+00h]
0x140087c12  mov     rcx, [rdi]
0x140087c15  cmp     [rbp+47h+arg_28], ebx
0x140087c18  jz      short loc_140087C85
0x140087c1a  mov     rdx, [rdi+98h]
0x140087c21  mov     r8, rdx
0x140087c24  shr     r8, 20h
0x140087c28  call    cs:__imp_EtwTranslationUpdateOffset
0x140087c2f  nop     dword ptr [rax+rax+00h]
0x140087c34  mov     eax, [r12+0Ch]
0x140087c39  mov     r9d, [r12+8]
0x140087c3e  mov     r8d, [r12+4]
0x140087c43  mov     edx, [r12]
0x140087c47  mov     rcx, [rdi]
0x140087c4a  mov     dword ptr [rsp+120h+var_100], eax
0x140087c4e  call    cs:__imp_EtwTranslationUpdate
0x140087c55  nop     dword ptr [rax+rax+00h]
0x140087c5a  mov     r9, [rdi+60h]; struct REGION *
0x140087c5e  lea     r8, [rdi+68h]; struct _POINTL *
0x140087c62  mov     rbx, [rbp+47h+var_C0]
0x140087c66  lea     rdx, [rdi+70h]; struct _RECTL *
0x140087c6a  mov     rcx, rsi; this
0x140087c6d  call    ?vApplyMoveData@METAREGION@@AEAAHPEAU_RECTL@@PEAU_POINTL@@PEAVREGION@@@Z; METAREGION::vApplyMoveData(_RECTL *,_POINTL *,REGION *)
0x140087c72  mov     [rsi], rbx
0x140087c75  xor     ebx, ebx
0x140087c77  test    eax, eax
0x140087c79  jz      short loc_140087CB7
0x140087c7b  mov     rcx, rsi; this
0x140087c7e  call    ?vCalculateNoMoveDirty@METAREGION@@AEAAXXZ; METAREGION::vCalculateNoMoveDirty(void)
0x140087c83  jmp     short loc_140087CB7
0x140087c85  mov     eax, [r12+0Ch]
0x140087c8a  mov     r9d, [r12+8]
0x140087c8f  mov     r8d, [r12+4]
0x140087c94  mov     edx, [r12]
0x140087c98  mov     dword ptr [rsp+120h+var_100], eax
0x140087c9c  call    cs:__imp_EtwDirtyRectUpdate
0x140087ca3  nop     dword ptr [rax+rax+00h]
0x140087ca8  mov     rdx, [rbp+47h+var_C0]; struct REGION *
0x140087cac  mov     r8, r12; struct tagRECT *
0x140087caf  mov     rcx, rsi; this
0x140087cb2  call    ?vDirtyRegionWithRect@METAREGION@@QEAAXPEAVREGION@@PEAUtagRECT@@@Z; METAREGION::vDirtyRegionWithRect(REGION *,tagRECT *)
0x140087cb7  mov     eax, [rdi+0FCh]
0x140087cbd  test    al, 2
0x140087cbf  jnz     short loc_140087CCE
0x140087cc1  or      eax, 2
0x140087cc4  mov     [rdi+0FCh], eax
0x140087cca  or      dword ptr [r15], 1
0x140087cce  mov     rax, [rdi+50h]
0x140087cd2  test    rax, rax
0x140087cd5  jz      loc_140087D9F
0x140087cdb  mov     r9b, 0Eh
0x140087cde  mov     [rsp+120h+var_E0], rax
0x140087ce3  lea     r8, [rsp+120h+var_D8]
0x140087ce8  lea     rdx, [rsp+120h+var_E0]
0x140087ced  lea     rcx, [rbp+47h+var_B8]
0x140087cf1  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x140087cf8  nop     dword ptr [rax+rax+00h]
0x140087cfd  test    eax, eax
0x140087cff  jz      short loc_140087D23
0x140087d01  lea     rdx, [rsp+120h+var_E0]
0x140087d06  lea     rcx, [rbp+47h+var_B8]
0x140087d0a  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x140087d11  nop     dword ptr [rax+rax+00h]
0x140087d16  mov     rdx, [rsp+120h+var_E0]; struct REGION *
0x140087d1b  mov     rcx, rdi; this
0x140087d1e  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x140087d23  cmp     dword ptr [rsp+120h+var_C8], ebx
0x140087d27  jnz     short loc_140087D9F
0x140087d29  lea     rcx, [rsp+120h+var_E0]; this
0x140087d2e  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x140087d33  cmp     eax, 2
0x140087d36  jnz     short loc_140087D9F
0x140087d38  xorps   xmm0, xmm0
0x140087d3b  lea     rcx, [rsp+120h+var_C8]
0x140087d40  movups  [rbp+47h+var_60], xmm0
0x140087d44  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x140087d4b  nop     dword ptr [rax+rax+00h]
0x140087d50  cmp     [rsp+120h+var_C8], rbx
0x140087d55  jz      short loc_140087D9F
0x140087d57  mov     rax, [rsp+120h+var_E0]
0x140087d5c  lea     rcx, [rbp+47h+var_70]
0x140087d60  movups  xmm0, xmmword ptr [rax+34h]
0x140087d64  mov     rax, [rdi+50h]
0x140087d68  mov     [rbp+47h+var_70], rax
0x140087d6c  movdqu  [rbp+47h+var_60], xmm0
0x140087d71  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140087d78  nop     dword ptr [rax+rax+00h]
0x140087d7d  lea     rdx, [rbp+47h+var_60]
0x140087d81  lea     rcx, [rsp+120h+var_C8]
0x140087d86  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x140087d8d  nop     dword ptr [rax+rax+00h]
0x140087d92  mov     rdx, [rsp+120h+var_C8]; struct REGION *
0x140087d97  mov     rcx, rdi; this
0x140087d9a  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x140087d9f  mov     eax, [rdi+0FCh]
0x140087da5  test    al, 20h
0x140087da7  jz      short loc_140087DB8
0x140087da9  test    al, 4
0x140087dab  jz      short loc_140087DB1
0x140087dad  or      dword ptr [r15], 2
0x140087db1  and     dword ptr [rdi+0FCh], 0FFFFFFDFh
0x140087db8  test    r14, r14
0x140087dbb  jz      loc_140087E69
0x140087dc1  mov     eax, [r14+88h]
0x140087dc8  test    al, 2
0x140087dca  jz      loc_140087E69
0x140087dd0  mov     eax, [r15]
0x140087dd3  mov     edi, 1
0x140087dd8  test    dil, al
0x140087ddb  jz      loc_140087E69
0x140087de1  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140087de8  nop     dword ptr [rax+rax+00h]
0x140087ded  test    rax, rax
0x140087df0  jz      short loc_140087E69
0x140087df2  cmp     [rax], rbx
0x140087df5  jz      short loc_140087E69
0x140087df7  mov     ecx, [rax+114h]
0x140087dfd  test    cl, 2
0x140087e00  jnz     short loc_140087E69
0x140087e02  or      ecx, 2
0x140087e05  mov     [rax+114h], ecx
0x140087e0b  mov     eax, cs:dword_14039AA20
0x140087e11  cmp     eax, 5
0x140087e14  jbe     short loc_140087E69
0x140087e16  mov     rdx, 400000000000h
0x140087e20  lea     rcx, dword_14039AA20
0x140087e27  call    _tlgKeywordOn
0x140087e2c  test    al, al
0x140087e2e  jz      short loc_140087E69
0x140087e30  lea     rax, [rbp+47h+var_70]
0x140087e34  mov     [rbp+47h+var_70], 2000000h
0x140087e3c  mov     [rsp+120h+var_F0], rax
0x140087e41  lea     rdx, dword_14036CE54
0x140087e48  lea     rax, [rsp+120h+var_C8]
  ... truncated ...
```
