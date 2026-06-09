# vSpUpdateDirtyRgn(DWMSPRITE *,SFMLOGICALSURFACE *,HDC__ *,tagRECT *,ulong *,int)

- ea: `0x1400164f8`
- end: `0x140016a5f`
- name: `?vSpUpdateDirtyRgn@@YAXPEAVDWMSPRITE@@PEAVSFMLOGICALSURFACE@@PEAUHDC__@@PEAUtagRECT@@PEAKH@Z`
- size: `1383`
- prototype: `void __fastcall(struct DWMSPRITE *, struct SFMLOGICALSURFACE *, HDC, struct _RECTL *, unsigned int *, int)`
- caller_count: `6`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140015d84`
- `0x140017000`
- `0x1400a8ad8`
- `0x14011b49c`
- `0x14012273c`
- `0x140336d74`

## callees

- `0x140001158`
- `0x1400164f8`
- `0x1400697e4`
- `0x140069bc8`
- `0x140077348`
- `0x140079b44`
- `0x14008ac7c`
- `0x14009a3b8`
- `0x14011c694`
- `0x14019f638`
- `0x14019f7dc`
- `0x14021e768`
- `0x14026db38`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140016999`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140016999`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140016929`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140016929`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140016638`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140016726`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14001693e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140016638`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140016726`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14001693e`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14001669a`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140016744`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14001679f`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400168a9`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14001669a`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140016744`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14001679f`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400168a9`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140016545`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140016564`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1400168fc`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140016545`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140016564`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1400168fc`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400166b4`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14001675e`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400167be`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400168c2`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400166b4`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14001675e`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400167be`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400168c2`
- `win32kbase!EtwTraceLifetimeAccum` at `0x1400165d6`
- `win32kbase!EtwTraceLifetimeAccum` at `0x1400165d6`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1400165a1`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1400165be`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1400166c7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140016782`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1400165a1`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1400165be`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1400166c7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140016782`
- `win32kbase!EtwTranslationUpdateOffset` at `0x1400167e0`
- `win32kbase!EtwTranslationUpdateOffset` at `0x1400167e0`
- `win32kbase!EtwTranslationUpdate` at `0x140016806`
- `win32kbase!EtwTranslationUpdate` at `0x140016806`
- `win32kbase!EtwDirtyRectUpdate` at `0x140016854`
- `win32kbase!EtwDirtyRectUpdate` at `0x140016854`

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
  LONG v13; // ecx
  __int64 v14; // rcx
  struct REGION *v15; // rbx
  int v16; // eax
  int v17; // eax
  struct _RECTL v18; // xmm0
  int v19; // eax
  __int64 CurrentProcessWin32Process; // rax
  int v21; // ecx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  struct REGION *v25; // [rsp+40h] [rbp-99h] BYREF
  __int64 v26; // [rsp+48h] [rbp-91h] BYREF
  __int64 v27; // [rsp+50h] [rbp-89h] BYREF
  struct REGION *v28; // [rsp+58h] [rbp-81h] BYREF
  struct REGION *v29; // [rsp+60h] [rbp-79h] BYREF
  __int64 v30; // [rsp+68h] [rbp-71h] BYREF
  _QWORD v31[8]; // [rsp+70h] [rbp-69h] BYREF
  struct _RECTL v32; // [rsp+B0h] [rbp-29h] BYREF
  struct _RECTL v33; // [rsp+C0h] [rbp-19h] BYREF

  v6 = (struct REGION **)((char *)a2 + 128);
  v7 = (struct REGION *)*((_QWORD *)a2 + 16);
  v8 = 0;
  if ( !v7 )
  {
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v25);
    v7 = v25;
    *v6 = v25;
  }
  if ( *((_QWORD *)a2 + 10) )
  {
    LODWORD(v28) = 0;
  }
  else
  {
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v25);
    SFMLOGICALSURFACE::vDirtyRegionAccum(a2, v25);
    v7 = *v6;
    LODWORD(v28) = 1;
  }
  if ( !*((_QWORD *)a2 + 23) )
  {
    v25 = v7;
    RGNOBJ::vSet((RGNOBJ *)&v25);
    if ( *((_QWORD *)a2 + 10) )
    {
      *(_QWORD *)&v32.left = *((_QWORD *)a2 + 10);
      RGNOBJ::vSet((RGNOBJ *)&v32);
      EtwTraceLifetimeAccum(*(_QWORD *)a2, 1, *((_QWORD *)a2 + 10));
    }
  }
  v29 = *v6;
  RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v26);
  RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v27);
  RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v30);
  if ( v29 && v26 && v27 && v30 )
  {
    RGNOBJ::vSet((RGNOBJ *)&v26, a4);
    if ( (*((_DWORD *)a2 + 63) & 1) == 0 || !a3 )
      goto LABEL_58;
    DCOBJA::DCOBJA((DCOBJA *)v31, a3);
    if ( v31[0] )
    {
      if ( (*(_DWORD *)(v31[0] + 36LL) & 1) != 0 )
      {
        *(_QWORD *)&v32.left = XDCOBJ::prgnEffRao((XDCOBJ *)v31);
        if ( *(_QWORD *)&v32.left )
        {
          if ( RGNOBJ::bMerge((RGNOBJ *)&v27, (struct RGNOBJ *)&v32, (struct RGNOBJ *)&v26, 8u) )
          {
            RGNOBJ::vSwap((RGNOBJ *)&v27, (struct RGNOBJ *)&v26);
            v8 = 1;
          }
          else
          {
            RGNOBJ::vSet((RGNOBJ *)&v27);
          }
        }
      }
    }
    DCOBJA::~DCOBJA((DCOBJA *)v31);
    if ( !v8 )
    {
LABEL_58:
      if ( !a1 )
        goto LABEL_27;
      RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v25);
      v32.right = *((_DWORD *)a1 + 16) - *((_DWORD *)a1 + 14);
      v13 = *((_DWORD *)a1 + 17) - *((_DWORD *)a1 + 15);
      *(_QWORD *)&v32.left = 0;
      v32.bottom = v13;
      if ( v25 )
      {
        RGNOBJ::vSet((RGNOBJ *)&v25, &v32);
        if ( RGNOBJ::bMerge((RGNOBJ *)&v27, (struct RGNOBJ *)&v26, (struct RGNOBJ *)&v25, 8u) )
        {
          RGNOBJ::vSwap((RGNOBJ *)&v27, (struct RGNOBJ *)&v26);
          v8 = 1;
        }
      }
      RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v25);
      if ( !v8 )
LABEL_27:
        RGNOBJ::vSet((RGNOBJ *)&v26);
    }
    if ( RGNOBJ::bMerge((RGNOBJ *)&v27, (struct RGNOBJ *)&v29, (struct RGNOBJ *)&v26, 0xEu) )
    {
      RGNOBJ::vSwap((RGNOBJ *)&v27, (struct RGNOBJ *)&v29);
      v14 = *(_QWORD *)a2;
      if ( a6 )
      {
        EtwTranslationUpdateOffset(v14, *((_QWORD *)a2 + 19), HIDWORD(*((_QWORD *)a2 + 19)));
        EtwTranslationUpdate(
          *(_QWORD *)a2,
          (unsigned int)a4->left,
          (unsigned int)a4->top,
          (unsigned int)a4->right,
          a4->bottom);
        v15 = v29;
        v16 = METAREGION::vApplyMoveData(
                (METAREGION *)v6,
                (struct _RECTL *)a2 + 7,
                (struct _POINTL *)a2 + 13,
                *((struct REGION **)a2 + 12));
        *v6 = v15;
        if ( v16 )
          METAREGION::vCalculateNoMoveDirty((METAREGION *)v6);
      }
      else
      {
        EtwDirtyRectUpdate(v14, (unsigned int)a4->left, (unsigned int)a4->top, (unsigned int)a4->right, a4->bottom);
        METAREGION::vDirtyRegionWithRect((METAREGION *)v6, v29, (struct tagRECT *)a4);
      }
      v17 = *((_DWORD *)a2 + 63);
      if ( (v17 & 2) == 0 )
      {
        *((_DWORD *)a2 + 63) = v17 | 2;
        *a5 |= 1u;
      }
    }
    if ( *((_QWORD *)a2 + 10) )
    {
      v25 = (struct REGION *)*((_QWORD *)a2 + 10);
      if ( RGNOBJ::bMerge((RGNOBJ *)&v30, (struct RGNOBJ *)&v25, (struct RGNOBJ *)&v26, 0xEu) )
      {
        RGNOBJ::vSwap((RGNOBJ *)&v30, (struct RGNOBJ *)&v25);
        SFMLOGICALSURFACE::vDirtyRegionAccum(a2, v25);
      }
      if ( !(_DWORD)v28 && (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v25) == 2 )
      {
        v33 = 0;
        RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v28);
        if ( v28 )
        {
          v18 = *(struct _RECTL *)((char *)v25 + 52);
          *(_QWORD *)&v32.left = *((_QWORD *)a2 + 10);
          v33 = v18;
          RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v32);
          RGNOBJ::vSet((RGNOBJ *)&v28, &v33);
          SFMLOGICALSURFACE::vDirtyRegionAccum(a2, v28);
        }
      }
    }
  }
  v19 = *((_DWORD *)a2 + 63);
  if ( (v19 & 0x20) != 0 )
  {
    if ( (v19 & 4) != 0 )
      *a5 |= 2u;
    *((_DWORD *)a2 + 63) &= ~0x20u;
  }
  if ( a1 )
  {
    if ( (*((_DWORD *)a1 + 34) & 2) != 0 && (*a5 & 1) != 0 )
    {
      CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
      if ( CurrentProcessWin32Process )
      {
        if ( *(_QWORD *)CurrentProcessWin32Process )
        {
          v21 = *(_DWORD *)(CurrentProcessWin32Process + 276);
          if ( (v21 & 2) == 0 )
          {
            *(_DWORD *)(CurrentProcessWin32Process + 276) = v21 | 2;
            if ( (unsigned int)dword_14039BA20 > 5 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_14039BA20, 0x400000000000LL) )
              {
                *(_QWORD *)&v32.left = 0x2000000;
                LODWORD(v28) = 1;
                LODWORD(v25) = 1;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                  v22,
                  (__int64)&dword_14036DDD4,
                  v23,
                  v24,
                  (__int64)&v25,
                  (__int64)&v28,
                  (__int64)&v32);
              }
            }
          }
        }
      }
    }
  }
  RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v30);
  RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v27);
  RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v26);
}

```

## disassembly

```asm
0x1400164f8  push    rbp
0x1400164fa  push    rbx
0x1400164fb  push    rsi
0x1400164fc  push    rdi
0x1400164fd  push    r12
0x1400164ff  push    r13
0x140016501  push    r14
0x140016503  push    r15
0x140016505  lea     rbp, [rsp-0Fh]
0x14001650a  sub     rsp, 0E8h
0x140016511  mov     rax, cs:__security_cookie
0x140016518  xor     rax, rsp
0x14001651b  mov     [rbp+47h+var_50], rax
0x14001651f  mov     r15, [rbp+47h+arg_20]
0x140016523  lea     rsi, [rdx+80h]
0x14001652a  mov     rax, [rsi]
0x14001652d  xor     ebx, ebx
0x14001652f  mov     r12, r9
0x140016532  mov     r13, r8
0x140016535  mov     rdi, rdx
0x140016538  mov     r14, rcx
0x14001653b  test    rax, rax
0x14001653e  jnz     short loc_140016559
0x140016540  lea     rcx, [rsp+120h+var_E0]
0x140016545  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14001654c  nop     dword ptr [rax+rax+00h]
0x140016551  mov     rax, [rsp+120h+var_E0]
0x140016556  mov     [rsi], rax
0x140016559  cmp     [rdi+50h], rbx
0x14001655d  jnz     short loc_14001658A
0x14001655f  lea     rcx, [rsp+120h+var_E0]
0x140016564  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14001656b  nop     dword ptr [rax+rax+00h]
0x140016570  mov     rdx, [rsp+120h+var_E0]; struct REGION *
0x140016575  mov     rcx, rdi; this
0x140016578  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x14001657d  mov     rax, [rsi]
0x140016580  mov     dword ptr [rsp+120h+var_C8], 1
0x140016588  jmp     short loc_14001658E
0x14001658a  mov     dword ptr [rsp+120h+var_C8], ebx
0x14001658e  cmp     [rdi+0B8h], rbx
0x140016595  jnz     short loc_1400165E2
0x140016597  lea     rcx, [rsp+120h+var_E0]
0x14001659c  mov     [rsp+120h+var_E0], rax
0x1400165a1  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x1400165a8  nop     dword ptr [rax+rax+00h]
0x1400165ad  mov     rax, [rdi+50h]
0x1400165b1  test    rax, rax
0x1400165b4  jz      short loc_1400165E2
0x1400165b6  lea     rcx, [rbp+47h+var_70]
0x1400165ba  mov     [rbp+47h+var_70], rax
0x1400165be  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x1400165c5  nop     dword ptr [rax+rax+00h]
0x1400165ca  mov     r8, [rdi+50h]
0x1400165ce  mov     edx, 1
0x1400165d3  mov     rcx, [rdi]
0x1400165d6  call    cs:__imp_EtwTraceLifetimeAccum
0x1400165dd  nop     dword ptr [rax+rax+00h]
0x1400165e2  mov     rax, [rsi]
0x1400165e5  lea     rcx, [rsp+120h+var_D8]; this
0x1400165ea  mov     [rbp+47h+var_C0], rax
0x1400165ee  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x1400165f3  lea     rcx, [rsp+120h+var_D0]; this
0x1400165f8  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x1400165fd  lea     rcx, [rbp+47h+var_B8]; this
0x140016601  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x140016606  cmp     [rbp+47h+var_C0], rbx
0x14001660a  jz      loc_140016957
0x140016610  cmp     [rsp+120h+var_D8], rbx
0x140016615  jz      loc_140016957
0x14001661b  cmp     [rsp+120h+var_D0], rbx
0x140016620  jz      loc_140016957
0x140016626  cmp     [rbp+47h+var_B8], rbx
0x14001662a  jz      loc_140016957
0x140016630  mov     rdx, r12
0x140016633  lea     rcx, [rsp+120h+var_D8]
0x140016638  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14001663f  nop     dword ptr [rax+rax+00h]
0x140016644  mov     eax, [rdi+0FCh]
0x14001664a  test    al, 1
0x14001664c  jz      loc_1400166E4
0x140016652  test    r13, r13
0x140016655  jz      loc_1400166E4
0x14001665b  mov     rdx, r13; HDC
0x14001665e  lea     rcx, [rbp+47h+var_B0]; this
0x140016662  call    ??0DCOBJA@@QEAA@PEAUHDC__@@@Z; DCOBJA::DCOBJA(HDC__ *)
0x140016667  mov     rax, [rbp+47h+var_B0]
0x14001666b  test    rax, rax
0x14001666e  jz      short loc_1400166D3
0x140016670  mov     eax, [rax+24h]
0x140016673  test    al, 1
0x140016675  jz      short loc_1400166D3
0x140016677  lea     rcx, [rbp+47h+var_B0]; this
0x14001667b  call    ?prgnEffRao@XDCOBJ@@QEAAPEAVREGION@@XZ; XDCOBJ::prgnEffRao(void)
0x140016680  mov     [rbp+47h+var_70], rax
0x140016684  test    rax, rax
0x140016687  jz      short loc_1400166D3
0x140016689  mov     r9b, 8
0x14001668c  lea     r8, [rsp+120h+var_D8]
0x140016691  lea     rdx, [rbp+47h+var_70]
0x140016695  lea     rcx, [rsp+120h+var_D0]
0x14001669a  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1400166a1  nop     dword ptr [rax+rax+00h]
0x1400166a6  lea     rcx, [rsp+120h+var_D0]
0x1400166ab  test    eax, eax
0x1400166ad  jz      short loc_1400166C7
0x1400166af  lea     rdx, [rsp+120h+var_D8]
0x1400166b4  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x1400166bb  nop     dword ptr [rax+rax+00h]
0x1400166c0  mov     ebx, 1
0x1400166c5  jmp     short loc_1400166D3
0x1400166c7  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x1400166ce  nop     dword ptr [rax+rax+00h]
0x1400166d3  lea     rcx, [rbp+47h+var_B0]; this
0x1400166d7  call    ??1DCOBJA@@QEAA@XZ; DCOBJA::~DCOBJA(void)
0x1400166dc  test    ebx, ebx
0x1400166de  jnz     loc_14001678E
0x1400166e4  test    r14, r14
0x1400166e7  jz      loc_14001677D
0x1400166ed  lea     rcx, [rsp+120h+var_E0]; this
0x1400166f2  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x1400166f7  mov     ecx, [r14+40h]
0x1400166fb  sub     ecx, [r14+38h]
0x1400166ff  mov     [rbp+47h+var_68], ecx
0x140016702  mov     ecx, [r14+44h]
0x140016706  sub     ecx, [r14+3Ch]
0x14001670a  cmp     [rsp+120h+var_E0], 0
0x140016710  mov     [rbp+47h+var_70], 0
0x140016718  mov     [rbp+47h+var_64], ecx
0x14001671b  jz      short loc_14001676F
0x14001671d  lea     rdx, [rbp+47h+var_70]
0x140016721  lea     rcx, [rsp+120h+var_E0]
0x140016726  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14001672d  nop     dword ptr [rax+rax+00h]
0x140016732  mov     r9b, 8
0x140016735  lea     r8, [rsp+120h+var_E0]
0x14001673a  lea     rdx, [rsp+120h+var_D8]
0x14001673f  lea     rcx, [rsp+120h+var_D0]
0x140016744  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x14001674b  nop     dword ptr [rax+rax+00h]
0x140016750  test    eax, eax
0x140016752  jz      short loc_14001676F
0x140016754  lea     rdx, [rsp+120h+var_D8]
0x140016759  lea     rcx, [rsp+120h+var_D0]
0x14001675e  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x140016765  nop     dword ptr [rax+rax+00h]
0x14001676a  mov     ebx, 1
0x14001676f  lea     rcx, [rsp+120h+var_E0]; this
0x140016774  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x140016779  test    ebx, ebx
0x14001677b  jnz     short loc_14001678E
0x14001677d  lea     rcx, [rsp+120h+var_D8]
0x140016782  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x140016789  nop     dword ptr [rax+rax+00h]
0x14001678e  mov     r9b, 0Eh
0x140016791  lea     r8, [rsp+120h+var_D8]
0x140016796  lea     rdx, [rbp+47h+var_C0]
0x14001679a  lea     rcx, [rsp+120h+var_D0]
0x14001679f  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1400167a6  nop     dword ptr [rax+rax+00h]
0x1400167ab  xor     ebx, ebx
0x1400167ad  test    eax, eax
0x1400167af  jz      loc_140016886
0x1400167b5  lea     rdx, [rbp+47h+var_C0]
0x1400167b9  lea     rcx, [rsp+120h+var_D0]
0x1400167be  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x1400167c5  nop     dword ptr [rax+rax+00h]
0x1400167ca  mov     rcx, [rdi]
0x1400167cd  cmp     [rbp+47h+arg_28], ebx
0x1400167d0  jz      short loc_14001683D
0x1400167d2  mov     rdx, [rdi+98h]
0x1400167d9  mov     r8, rdx
0x1400167dc  shr     r8, 20h
0x1400167e0  call    cs:__imp_EtwTranslationUpdateOffset
0x1400167e7  nop     dword ptr [rax+rax+00h]
0x1400167ec  mov     eax, [r12+0Ch]
0x1400167f1  mov     r9d, [r12+8]
0x1400167f6  mov     r8d, [r12+4]
0x1400167fb  mov     edx, [r12]
0x1400167ff  mov     rcx, [rdi]
0x140016802  mov     dword ptr [rsp+120h+var_100], eax
0x140016806  call    cs:__imp_EtwTranslationUpdate
0x14001680d  nop     dword ptr [rax+rax+00h]
0x140016812  mov     r9, [rdi+60h]; struct REGION *
0x140016816  lea     r8, [rdi+68h]; struct _POINTL *
0x14001681a  mov     rbx, [rbp+47h+var_C0]
0x14001681e  lea     rdx, [rdi+70h]; struct _RECTL *
0x140016822  mov     rcx, rsi; this
0x140016825  call    ?vApplyMoveData@METAREGION@@AEAAHPEAU_RECTL@@PEAU_POINTL@@PEAVREGION@@@Z; METAREGION::vApplyMoveData(_RECTL *,_POINTL *,REGION *)
0x14001682a  mov     [rsi], rbx
0x14001682d  xor     ebx, ebx
0x14001682f  test    eax, eax
0x140016831  jz      short loc_14001686F
0x140016833  mov     rcx, rsi; this
0x140016836  call    ?vCalculateNoMoveDirty@METAREGION@@AEAAXXZ; METAREGION::vCalculateNoMoveDirty(void)
0x14001683b  jmp     short loc_14001686F
0x14001683d  mov     eax, [r12+0Ch]
0x140016842  mov     r9d, [r12+8]
0x140016847  mov     r8d, [r12+4]
0x14001684c  mov     edx, [r12]
0x140016850  mov     dword ptr [rsp+120h+var_100], eax
0x140016854  call    cs:__imp_EtwDirtyRectUpdate
0x14001685b  nop     dword ptr [rax+rax+00h]
0x140016860  mov     rdx, [rbp+47h+var_C0]; struct REGION *
0x140016864  mov     r8, r12; struct tagRECT *
0x140016867  mov     rcx, rsi; this
0x14001686a  call    ?vDirtyRegionWithRect@METAREGION@@QEAAXPEAVREGION@@PEAUtagRECT@@@Z; METAREGION::vDirtyRegionWithRect(REGION *,tagRECT *)
0x14001686f  mov     eax, [rdi+0FCh]
0x140016875  test    al, 2
0x140016877  jnz     short loc_140016886
0x140016879  or      eax, 2
0x14001687c  mov     [rdi+0FCh], eax
0x140016882  or      dword ptr [r15], 1
0x140016886  mov     rax, [rdi+50h]
0x14001688a  test    rax, rax
0x14001688d  jz      loc_140016957
0x140016893  mov     r9b, 0Eh
0x140016896  mov     [rsp+120h+var_E0], rax
0x14001689b  lea     r8, [rsp+120h+var_D8]
0x1400168a0  lea     rdx, [rsp+120h+var_E0]
0x1400168a5  lea     rcx, [rbp+47h+var_B8]
0x1400168a9  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1400168b0  nop     dword ptr [rax+rax+00h]
0x1400168b5  test    eax, eax
0x1400168b7  jz      short loc_1400168DB
0x1400168b9  lea     rdx, [rsp+120h+var_E0]
0x1400168be  lea     rcx, [rbp+47h+var_B8]
0x1400168c2  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x1400168c9  nop     dword ptr [rax+rax+00h]
0x1400168ce  mov     rdx, [rsp+120h+var_E0]; struct REGION *
0x1400168d3  mov     rcx, rdi; this
0x1400168d6  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x1400168db  cmp     dword ptr [rsp+120h+var_C8], ebx
0x1400168df  jnz     short loc_140016957
0x1400168e1  lea     rcx, [rsp+120h+var_E0]; this
0x1400168e6  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x1400168eb  cmp     eax, 2
0x1400168ee  jnz     short loc_140016957
0x1400168f0  xorps   xmm0, xmm0
0x1400168f3  lea     rcx, [rsp+120h+var_C8]
0x1400168f8  movups  [rbp+47h+var_60], xmm0
0x1400168fc  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x140016903  nop     dword ptr [rax+rax+00h]
0x140016908  cmp     [rsp+120h+var_C8], rbx
0x14001690d  jz      short loc_140016957
0x14001690f  mov     rax, [rsp+120h+var_E0]
0x140016914  lea     rcx, [rbp+47h+var_70]
0x140016918  movups  xmm0, xmmword ptr [rax+34h]
0x14001691c  mov     rax, [rdi+50h]
0x140016920  mov     [rbp+47h+var_70], rax
0x140016924  movdqu  [rbp+47h+var_60], xmm0
0x140016929  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140016930  nop     dword ptr [rax+rax+00h]
0x140016935  lea     rdx, [rbp+47h+var_60]
0x140016939  lea     rcx, [rsp+120h+var_C8]
0x14001693e  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x140016945  nop     dword ptr [rax+rax+00h]
0x14001694a  mov     rdx, [rsp+120h+var_C8]; struct REGION *
0x14001694f  mov     rcx, rdi; this
0x140016952  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x140016957  mov     eax, [rdi+0FCh]
0x14001695d  test    al, 20h
0x14001695f  jz      short loc_140016970
0x140016961  test    al, 4
0x140016963  jz      short loc_140016969
0x140016965  or      dword ptr [r15], 2
0x140016969  and     dword ptr [rdi+0FCh], 0FFFFFFDFh
0x140016970  test    r14, r14
0x140016973  jz      loc_140016A21
0x140016979  mov     eax, [r14+88h]
0x140016980  test    al, 2
0x140016982  jz      loc_140016A21
0x140016988  mov     eax, [r15]
0x14001698b  mov     edi, 1
0x140016990  test    dil, al
0x140016993  jz      loc_140016A21
0x140016999  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400169a0  nop     dword ptr [rax+rax+00h]
0x1400169a5  test    rax, rax
0x1400169a8  jz      short loc_140016A21
0x1400169aa  cmp     [rax], rbx
0x1400169ad  jz      short loc_140016A21
0x1400169af  mov     ecx, [rax+114h]
0x1400169b5  test    cl, 2
0x1400169b8  jnz     short loc_140016A21
0x1400169ba  or      ecx, 2
0x1400169bd  mov     [rax+114h], ecx
0x1400169c3  mov     eax, cs:dword_14039BA20
0x1400169c9  cmp     eax, 5
0x1400169cc  jbe     short loc_140016A21
0x1400169ce  mov     rdx, 400000000000h
0x1400169d8  lea     rcx, dword_14039BA20
0x1400169df  call    _tlgKeywordOn
0x1400169e4  test    al, al
0x1400169e6  jz      short loc_140016A21
0x1400169e8  lea     rax, [rbp+47h+var_70]
0x1400169ec  mov     [rbp+47h+var_70], 2000000h
0x1400169f4  mov     [rsp+120h+var_F0], rax
0x1400169f9  lea     rdx, dword_14036DDD4
0x140016a00  lea     rax, [rsp+120h+var_C8]
  ... truncated ...
```
