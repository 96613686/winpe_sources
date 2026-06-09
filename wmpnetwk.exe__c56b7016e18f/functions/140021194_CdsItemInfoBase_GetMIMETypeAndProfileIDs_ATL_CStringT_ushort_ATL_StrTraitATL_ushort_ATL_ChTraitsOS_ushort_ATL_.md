# CdsItemInfoBase::GetMIMETypeAndProfileIDs(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x140021194`
- end: `0x1400215e7`
- name: `?GetMIMETypeAndProfileIDs@CdsItemInfoBase@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `1107`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14001fe78`
- `0x14002ba58`
- `0x140041c80`
- `0x14008dbdc`

## callees

- `0x140003750`
- `0x1400065e0`
- `0x14000b3f0`
- `0x14000c9cc`
- `0x140015230`
- `0x14001b620`
- `0x140021194`
- `0x1400215f0`
- `0x1400396dc`
- `0x14003e5f4`
- `0x140047798`
- `0x140059b38`
- `0x14005ea04`
- `0x140099f08`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1400214f5`
- `KERNEL32!CompareStringW` at `0x1400214f5`
- `OLEAUT32!__imp_VariantClear` at `0x140021381`
- `OLEAUT32!__imp_VariantClear` at `0x1400215c0`
- `OLEAUT32!__imp_VariantClear` at `0x140021381`
- `OLEAUT32!__imp_VariantClear` at `0x1400215c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CdsItemInfoBase::GetMIMETypeAndProfileIDs(__int64 *a1, __int64 *a2, __int64 *a3)
{
  PVOID *v6; // rcx
  __int64 v7; // rax
  int *v8; // rbx
  __int64 v9; // rsi
  ATL::CStringData *v10; // r14
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  PVOID *v14; // rcx
  int *v15; // rax
  __int64 v16; // rax
  char *v17; // rdi
  __int64 v18; // rdi
  __int64 v19; // rax
  _QWORD *v20; // rax
  char *v21; // rdi
  __int64 v22; // rdi
  __int64 v23; // rax
  PCNZWCH *v24; // rax
  int v25; // ebx
  __int64 v26; // rax
  _QWORD *v27; // rax
  __int64 v29; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+48h] [rbp-21h] BYREF
  VARIANTARG v31; // [rsp+50h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-1h] BYREF
  int *v33; // [rsp+E8h] [rbp+7Fh] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v31.vt = 19;
  v31.lVal = 3;
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_qD(v6[2], 48, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, &v31, 11);
  v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v8 = (int *)(v7 + 24);
  v33 = (int *)(v7 + 24);
  pvarg.vt = 19;
  pvarg.lVal = 11;
  v9 = *a1;
  if ( ((*(_DWORD *)(v7 + 12) - 257) | (1 - *(_DWORD *)(v7 + 16))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v33, 257);
    v8 = v33;
  }
  v10 = (ATL::CStringData *)(v8 - 6);
  if ( *(v8 - 3) < 257 )
    goto LABEL_57;
  *(v8 - 4) = 257;
  *((_WORD *)v8 + 257) = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, _QWORD, VARIANTARG *, int, int *))(v9 + 16))(
          a1,
          &v31,
          0,
          &pvarg,
          256,
          v8);
  if ( v12 >= 0 )
  {
    v13 = ATL::CSimpleStringT<unsigned short,0>::StringLength(v8);
    if ( v13 >= 0 && v13 <= *(v8 - 3) )
    {
      *(v8 - 4) = v13;
      *((_WORD *)v8 + v13) = 0;
      goto LABEL_17;
    }
LABEL_57:
    ATL::AtlThrowImpl(-2147024809);
  }
  if ( *(v8 - 3) < 0 )
    goto LABEL_57;
  *(v8 - 4) = 0;
  *(_WORD *)v8 = 0;
LABEL_17:
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v12 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dDDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v11, v12, v31.cVal, pvarg.cVal, (__int64)v8);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 && *((_BYTE *)v14 + 25) >= 5u )
      WPP_SF_S(v14[2], 50, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, v8);
  }
  VariantClear(&pvarg);
  if ( *(v8 - 4) > 0 )
  {
    v15 = v8;
    if ( v8 )
    {
      while ( *(_WORD *)v15 )
      {
        if ( *(_WORD *)v15 == 58 )
        {
          if ( v15 )
          {
            v16 = ((char *)v15 - (char *)v8) >> 1;
            if ( (_DWORD)v16 != -1 )
            {
              if ( (int)v16 + 1 >= 0 && (int)v16 + 1 < *(v8 - 4) )
              {
                v17 = (char *)v8 + 2 * (int)v16 + 2;
                if ( v17 )
                {
                  while ( *(_WORD *)v17 )
                  {
                    if ( *(_WORD *)v17 == 58 )
                    {
                      if ( !v17 )
                        break;
                      v18 = (v17 - (char *)v8) >> 1;
                      goto LABEL_41;
                    }
                    v17 += 2;
                  }
                }
              }
              LODWORD(v18) = -1;
LABEL_41:
              if ( (_DWORD)v18 != -1 )
              {
                v19 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
                        &v33,
                        &v30,
                        (unsigned int)(v18 + 1));
                v20 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
                                  v19,
                                  &v29,
                                  L":");
                ATL::CSimpleStringT<unsigned short,0>::operator=(a2, v20);
                ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
                ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
                if ( (int)v18 + 1 >= 0 && (int)v18 + 1 < *(v8 - 4) )
                {
                  v21 = (char *)v8 + 2 * (int)v18 + 2;
                  if ( v21 )
                  {
                    while ( *(_WORD *)v21 )
                    {
                      if ( *(_WORD *)v21 == 58 )
                      {
                        if ( v21 )
                        {
                          v22 = (v21 - (char *)v8) >> 1;
                          if ( (_DWORD)v22 != -1 )
                          {
                            v23 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
                                    &v33,
                                    &v29,
                                    (unsigned int)(v22 + 1));
                            v24 = (PCNZWCH *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                                               v23,
                                               &v30,
                                               12);
                            v25 = CompareStringW(0x7Fu, 0, L"DLNA.ORG_PN=", 12, *v24, -1);
                            ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
                            ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
                            if ( v25 == 2 )
                            {
                              v26 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
                                      &v33,
                                      &v29,
                                      (unsigned int)(v22 + 13));
                              v27 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
                                                v26,
                                                &v30,
                                                L";");
                              ATL::CSimpleStringT<unsigned short,0>::operator=(a3, v27);
                              ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
                              ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
                            }
                          }
                        }
                        goto LABEL_52;
                      }
                      v21 += 2;
                    }
                  }
                }
              }
            }
          }
          break;
        }
        v15 = (int *)((char *)v15 + 2);
      }
    }
  }
LABEL_52:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 2), *a2, *a3);
  }
  ATL::CStringData::Release(v10);
  VariantClear(&v31);
  return 0;
}

```

## disassembly

```asm
0x140021194  push    rbp
0x140021196  push    rbx
0x140021197  push    rsi
0x140021198  push    rdi
0x140021199  push    r12
0x14002119b  push    r13
0x14002119d  push    r14
0x14002119f  push    r15
0x1400211a1  lea     rbp, [rsp-1Fh]
0x1400211a6  sub     rsp, 88h
0x1400211ad  mov     r15, r8
0x1400211b0  mov     r12, rdx
0x1400211b3  mov     rdi, rcx
0x1400211b6  lea     rbx, WPP_GLOBAL_Control
0x1400211bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211c4  cmp     rcx, rbx
0x1400211c7  jz      short loc_1400211EB
0x1400211c9  test    byte ptr [rcx+1Ch], 2
0x1400211cd  jz      short loc_1400211EB
0x1400211cf  mov     edx, 40h ; '@'
0x1400211d4  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x1400211db  mov     rcx, [rcx+10h]
0x1400211df  call    WPP_SF_
0x1400211e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211eb  mov     esi, 13h
0x1400211f0  mov     word ptr [rbp+57h+var_70], si
0x1400211f4  mov     dword ptr [rbp+57h+var_70+8], 3
0x1400211fb  lea     r14d, [rsi-8]
0x1400211ff  cmp     rcx, rbx
0x140021202  jz      short loc_14002122D
0x140021204  test    byte ptr [rcx+1Ch], 2
0x140021208  jz      short loc_14002122D
0x14002120a  cmp     byte ptr [rcx+19h], 5
0x14002120e  jb      short loc_14002122D
0x140021210  lea     edx, [rsi+1Dh]
0x140021213  mov     dword ptr [rsp+0C0h+lpString2], r14d
0x140021218  lea     r9, [rbp+57h+var_70]
0x14002121c  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x140021223  mov     rcx, [rcx+10h]
0x140021227  call    WPP_SF_qD
0x14002122c  nop
0x14002122d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140021234  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002123b  mov     rax, [rax+18h]
0x14002123f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021244  lea     rbx, [rax+18h]
0x140021248  mov     [rbp+57h+arg_18], rbx
0x14002124c  mov     word ptr [rbp+57h+pvarg], si
0x140021250  mov     dword ptr [rbp+57h+pvarg+8], r14d
0x140021254  mov     rsi, [rdi]
0x140021257  mov     ecx, 1
0x14002125c  sub     ecx, [rbx-8]
0x14002125f  mov     eax, [rbx-0Ch]
0x140021262  mov     r13d, 101h
0x140021268  sub     eax, r13d
0x14002126b  or      ecx, eax
0x14002126d  jge     short loc_14002127F
0x14002126f  mov     edx, r13d
0x140021272  lea     rcx, [rbp+57h+arg_18]
0x140021276  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14002127b  mov     rbx, [rbp+57h+arg_18]
0x14002127f  lea     r14, [rbx-18h]
0x140021283  cmp     [r14+0Ch], r13d
0x140021287  jl      loc_1400215DC
0x14002128d  mov     [rbx-10h], r13d
0x140021291  xor     r13d, r13d
0x140021294  mov     [rbx+202h], r13w
0x14002129c  mov     qword ptr [rsp+0C0h+cchCount2], rbx
0x1400212a1  mov     dword ptr [rsp+0C0h+lpString2], 100h
0x1400212a9  lea     r9, [rbp+57h+pvarg]
0x1400212ad  xor     r8d, r8d
0x1400212b0  lea     rdx, [rbp+57h+var_70]
0x1400212b4  mov     rcx, rdi
0x1400212b7  mov     rax, [rsi+10h]
0x1400212bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400212c0  mov     r9d, eax
0x1400212c3  test    eax, eax
0x1400212c5  js      short loc_1400212ED
0x1400212c7  mov     rcx, rbx
0x1400212ca  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x1400212cf  test    eax, eax
0x1400212d1  js      loc_1400215DC
0x1400212d7  cmp     eax, [rbx-0Ch]
0x1400212da  jg      loc_1400215DC
0x1400212e0  mov     [rbx-10h], eax
0x1400212e3  movsxd  rcx, eax
0x1400212e6  mov     [rbx+rcx*2], r13w
0x1400212eb  jmp     short loc_1400212FF
0x1400212ed  cmp     [rbx-0Ch], r13d
0x1400212f1  jl      loc_1400215DC
0x1400212f7  mov     [rbx-10h], r13d
0x1400212fb  mov     [rbx], r13w
0x1400212ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140021306  lea     rdi, WPP_GLOBAL_Control
0x14002130d  cmp     rcx, rdi
0x140021310  jz      short loc_14002137D
0x140021312  test    byte ptr [rcx+1Ch], 20h
0x140021316  jz      short loc_140021354
0x140021318  mov     edx, r9d
0x14002131b  sar     edx, 1Fh
0x14002131e  and     edx, 0FFFFFFFDh
0x140021321  add     edx, 5
0x140021324  movzx   eax, byte ptr [rcx+19h]
0x140021328  cmp     eax, edx
0x14002132a  jb      short loc_140021354
0x14002132c  mov     edx, 31h ; '1'
0x140021331  mov     [rsp+0C0h+var_90], rbx
0x140021336  mov     eax, dword ptr [rbp+57h+pvarg+8]
0x140021339  mov     [rsp+0C0h+cchCount2], eax
0x14002133d  mov     eax, dword ptr [rbp+57h+var_70+8]
0x140021340  mov     dword ptr [rsp+0C0h+lpString2], eax
0x140021344  mov     rcx, [rcx+10h]
0x140021348  call    WPP_SF_dDDS
0x14002134d  mov     rcx, cs:WPP_GLOBAL_Control
0x140021354  cmp     rcx, rdi
0x140021357  jz      short loc_14002137D
0x140021359  test    byte ptr [rcx+1Ch], 2
0x14002135d  jz      short loc_14002137D
0x14002135f  cmp     byte ptr [rcx+19h], 5
0x140021363  jb      short loc_14002137D
0x140021365  mov     edx, 32h ; '2'
0x14002136a  mov     r9, rbx
0x14002136d  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x140021374  mov     rcx, [rcx+10h]
0x140021378  call    WPP_SF_S
0x14002137d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140021381  call    cs:__imp_VariantClear
0x140021387  cmp     [rbx-10h], r13d
0x14002138b  jle     loc_14002156A
0x140021391  mov     rax, rbx
0x140021394  test    rbx, rbx
0x140021397  jz      loc_14002156A
0x14002139d  cmp     [rax], r13w
0x1400213a1  jz      loc_14002156A
0x1400213a7  cmp     word ptr [rax], 3Ah ; ':'
0x1400213ab  jz      short loc_1400213B3
0x1400213ad  add     rax, 2
0x1400213b1  jmp     short loc_14002139D
0x1400213b3  test    rax, rax
0x1400213b6  jz      loc_14002156A
0x1400213bc  sub     rax, rbx
0x1400213bf  sar     rax, 1
0x1400213c2  or      edx, 0FFFFFFFFh
0x1400213c5  cmp     eax, edx
0x1400213c7  jz      loc_14002156A
0x1400213cd  lea     ecx, [rax+1]
0x1400213d0  test    ecx, ecx
0x1400213d2  js      short loc_140021407
0x1400213d4  cmp     ecx, [rbx-10h]
0x1400213d7  jge     short loc_140021407
0x1400213d9  movsxd  rdi, eax
0x1400213dc  inc     rdi
0x1400213df  lea     rdi, [rbx+rdi*2]
0x1400213e3  test    rdi, rdi
0x1400213e6  jz      short loc_140021407
0x1400213e8  cmp     [rdi], r13w
0x1400213ec  jz      short loc_140021407
0x1400213ee  cmp     word ptr [rdi], 3Ah ; ':'
0x1400213f2  jz      short loc_1400213FA
0x1400213f4  add     rdi, 2
0x1400213f8  jmp     short loc_1400213E8
0x1400213fa  test    rdi, rdi
0x1400213fd  jz      short loc_140021407
0x1400213ff  sub     rdi, rbx
0x140021402  sar     rdi, 1
0x140021405  jmp     short loc_140021409
0x140021407  mov     edi, edx
0x140021409  cmp     edi, edx
0x14002140b  jz      loc_14002156A
0x140021411  lea     esi, [rdi+1]
0x140021414  mov     r8d, esi
0x140021417  lea     rdx, [rbp+57h+var_78]
0x14002141b  lea     rcx, [rbp+57h+arg_18]
0x14002141f  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Mid(int)
0x140021424  lea     r8, asc_1400A3454; ":"
0x14002142b  lea     rdx, [rbp+57h+var_80]
0x14002142f  mov     rcx, rax
0x140021432  call    ?SpanExcluding@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::SpanExcluding(ushort const *)
0x140021437  mov     rdx, rax
0x14002143a  mov     rcx, r12
0x14002143d  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140021442  nop
0x140021443  mov     rcx, [rbp+57h+var_80]
0x140021447  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14002144b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140021450  nop
0x140021451  mov     rcx, [rbp+57h+var_78]
0x140021455  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140021459  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14002145e  nop
0x14002145f  test    esi, esi
0x140021461  js      loc_14002156A
0x140021467  cmp     esi, [rbx-10h]
0x14002146a  jge     loc_14002156A
0x140021470  movsxd  rdi, edi
0x140021473  inc     rdi
0x140021476  lea     rdi, [rbx+rdi*2]
0x14002147a  test    rdi, rdi
0x14002147d  jz      loc_14002156A
0x140021483  cmp     [rdi], r13w
0x140021487  jz      loc_14002156A
0x14002148d  cmp     word ptr [rdi], 3Ah ; ':'
0x140021491  jz      short loc_140021499
0x140021493  add     rdi, 2
0x140021497  jmp     short loc_140021483
0x140021499  test    rdi, rdi
0x14002149c  jz      loc_14002156A
0x1400214a2  sub     rdi, rbx
0x1400214a5  sar     rdi, 1
0x1400214a8  cmp     edi, 0FFFFFFFFh
0x1400214ab  jz      loc_14002156A
0x1400214b1  lea     r8d, [rdi+1]
0x1400214b5  lea     rdx, [rbp+57h+var_80]
0x1400214b9  lea     rcx, [rbp+57h+arg_18]
0x1400214bd  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Mid(int)
0x1400214c2  mov     ebx, 0Ch
0x1400214c7  mov     r8d, ebx
0x1400214ca  lea     rdx, [rbp+57h+var_78]
0x1400214ce  mov     rcx, rax
0x1400214d1  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x1400214d6  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400214de  mov     rax, [rax]
0x1400214e1  mov     [rsp+0C0h+lpString2], rax; lpString2
0x1400214e6  mov     r9d, ebx; cchCount1
0x1400214e9  lea     r8, Buf2; "DLNA.ORG_PN="
0x1400214f0  xor     edx, edx; dwCmpFlags
0x1400214f2  lea     ecx, [rbx+73h]; Locale
0x1400214f5  call    cs:__imp_CompareStringW
0x1400214fb  mov     ebx, eax
0x1400214fd  mov     rcx, [rbp+57h+var_78]
0x140021501  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140021505  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14002150a  nop
0x14002150b  mov     rcx, [rbp+57h+var_80]
0x14002150f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140021513  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140021518  nop
0x140021519  cmp     ebx, 2
0x14002151c  jnz     short loc_14002156A
0x14002151e  lea     r8d, [rdi+0Dh]
0x140021522  lea     rdx, [rbp+57h+var_80]
0x140021526  lea     rcx, [rbp+57h+arg_18]
0x14002152a  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Mid(int)
0x14002152f  lea     r8, asc_1400A3EB0; ";"
0x140021536  lea     rdx, [rbp+57h+var_78]
0x14002153a  mov     rcx, rax
0x14002153d  call    ?SpanExcluding@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::SpanExcluding(ushort const *)
0x140021542  mov     rdx, rax
0x140021545  mov     rcx, r15
0x140021548  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002154d  nop
0x14002154e  mov     rcx, [rbp+57h+var_78]
0x140021552  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140021556  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14002155b  nop
0x14002155c  mov     rcx, [rbp+57h+var_80]
0x140021560  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140021564  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140021569  nop
0x14002156a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021571  lea     rax, WPP_GLOBAL_Control
0x140021578  cmp     rcx, rax
0x14002157b  jz      short loc_1400215B3
0x14002157d  test    byte ptr [rcx+1Ch], 2
0x140021581  jz      short loc_1400215B3
0x140021583  cmp     byte ptr [rcx+19h], 5
0x140021587  jb      short loc_1400215B3
0x140021589  mov     edx, 41h ; 'A'
0x14002158e  mov     rax, [r15]
0x140021591  mov     qword ptr [rsp+0C0h+cchCount2], rax; __int64
0x140021596  mov     rax, [r12]
0x14002159a  mov     [rsp+0C0h+lpString2], rax; __int64
0x14002159f  xor     r9d, r9d
0x1400215a2  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x1400215a9  mov     rcx, [rcx+10h]; LoggerHandle
0x1400215ad  call    WPP_SF_dSS
0x1400215b2  nop
0x1400215b3  mov     rcx, r14; this
0x1400215b6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400215bb  nop
0x1400215bc  lea     rcx, [rbp+57h+var_70]; pvarg
0x1400215c0  call    cs:__imp_VariantClear
0x1400215c6  xor     eax, eax
0x1400215c8  add     rsp, 88h
0x1400215cf  pop     r15
0x1400215d1  pop     r14
0x1400215d3  pop     r13
0x1400215d5  pop     r12
0x1400215d7  pop     rdi
0x1400215d8  pop     rsi
0x1400215d9  pop     rbx
0x1400215da  pop     rbp
0x1400215db  retn
0x1400215dc  mov     ecx, 80070057h; int
0x1400215e1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
