# CTextNormMultiResult::ComputeTopResults(long,CTnMultiResStringPackage *,CSPList<IParseTreeNode *,IParseTreeNode *> *)

- ea: `0x18000a614`
- end: `0x18000aa9e`
- name: `?ComputeTopResults@CTextNormMultiResult@@AEAAJJPEAVCTnMultiResStringPackage@@PEAV?$CSPList@PEAUIParseTreeNode@@PEAU1@@@@Z`
- size: `1162`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18000cd70`
- `0x18000cf10`
- `0x18000d040`

## callees

- `0x180002ecc`
- `0x180004f5c`
- `0x180008da8`
- `0x1800091b8`
- `0x18000959c`
- `0x1800098e0`
- `0x180009c04`
- `0x18000a614`
- `0x18000acb0`
- `0x18000af70`
- `0x18000bf40`
- `0x18000dc24`
- `0x18000de0c`
- `0x18000e0d8`
- `0x18000e118`
- `0x18000eda0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CTextNormMultiResult::ComputeTopResults(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r15
  __int64 result; // rax
  int FullTextAndParseTree; // ebx
  int v10; // r10d
  int v11; // r8d
  unsigned int v12; // r9d
  int v13; // eax
  unsigned int v14; // edx
  int v15; // ecx
  CTnMultiResCursor *v16; // r9
  __int64 v17; // r13
  _QWORD *i; // rcx
  _QWORD *v19; // rax
  struct CAgreementElement *v20; // r8
  _QWORD *v21; // rax
  const struct CAgreementElement *v22; // r15
  __int64 v23; // rdx
  _QWORD *v24; // rax
  int v25; // r8d
  CAgreementElement *v26; // rax
  CAgreementElement *v27; // rdi
  unsigned int v28; // edx
  __int64 v29; // rax
  __int64 **v30; // rdi
  __int64 *v31; // r15
  struct CTnMultiResCursor *Child; // rax
  _QWORD *v33; // rdi
  _QWORD *v34; // rdx
  __int64 v35; // r9
  __int64 v36; // rcx
  __int64 v37; // r9
  char v38; // [rsp+30h] [rbp-D0h]
  unsigned int v39; // [rsp+34h] [rbp-CCh]
  CTnMultiResCursor *v40; // [rsp+38h] [rbp-C8h]
  int v41; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+44h] [rbp-BCh] BYREF
  int v43; // [rsp+48h] [rbp-B8h] BYREF
  int v44; // [rsp+4Ch] [rbp-B4h]
  struct CAgreementElement *v45; // [rsp+50h] [rbp-B0h]
  _QWORD v46[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v47; // [rsp+68h] [rbp-98h]
  __int64 v48; // [rsp+70h] [rbp-90h]
  CSPPlex *v49; // [rsp+78h] [rbp-88h]
  int v50; // [rsp+80h] [rbp-80h]
  _QWORD *v51; // [rsp+88h] [rbp-78h]
  _QWORD v52[2]; // [rsp+90h] [rbp-70h] BYREF
  int v53; // [rsp+A0h] [rbp-60h]
  __int64 v54; // [rsp+A8h] [rbp-58h]
  CSPPlex *v55; // [rsp+B0h] [rbp-50h]
  int v56; // [rsp+B8h] [rbp-48h]
  _QWORD v57[3]; // [rsp+C0h] [rbp-40h] BYREF
  int v58; // [rsp+D8h] [rbp-28h]
  __int64 v59; // [rsp+E0h] [rbp-20h]
  __int64 v60; // [rsp+E8h] [rbp-18h]
  int v61; // [rsp+F0h] [rbp-10h]
  int v62; // [rsp+F8h] [rbp-8h]
  CAgreementElement *v63; // [rsp+100h] [rbp+0h]

  v4 = a4;
  result = CTextNormMultiResult::ProcessNetwork((CTextNormMultiResult *)a1);
  if ( (int)result < 0 )
    return result;
  v47 = 0;
  v48 = 0;
  v46[1] = 0;
  v46[0] = 0;
  v49 = 0;
  v50 = 10;
  v53 = 0;
  v54 = 0;
  v52[1] = 0;
  v52[0] = 0;
  v55 = 0;
  v56 = 10;
  v42 = 10 * a2;
  v41 = 10 * a2;
  v57[0] = &CSpClassFactory::`vftable';
  v58 = 0;
  v59 = 0;
  v57[2] = 0;
  v57[1] = 0;
  v60 = 0;
  v61 = 10;
  v62 = 0;
  if ( !a3 || *(_DWORD *)(a3 + 16) || !*(_QWORD *)(a1 + 96) || !*(_DWORD *)(a1 + 68) )
  {
    FullTextAndParseTree = -2147024809;
    goto LABEL_66;
  }
  if ( a2 )
  {
    FullTextAndParseTree = CSpClassFactory::CreateProduct<CTnMultiResCursor>((CSpClassFactory *)v57);
    if ( FullTextAndParseTree < 0 )
      goto LABEL_66;
    MEMORY[0x18] = *(_QWORD *)(a1 + 96);
    CTextNormMultiResult::PlaceCursorInQueue(MEMORY[0x18], 0, (unsigned int)v46, 10 * a2, (__int64)v52);
    v10 = 0;
    v11 = 0;
    v43 = 0;
    if ( *(_WORD *)(a1 + 64) == 1029
      || *(_WORD *)(a1 + 64) == 1051
      || (v12 = 1000, v44 = 1000, *(_WORD *)(a1 + 64) == 1058) )
    {
      v12 = 25000;
      v44 = 25000;
    }
    v13 = *(_DWORD *)(a3 + 16);
    if ( v13 >= a2 )
    {
LABEL_57:
      v15 = v13;
LABEL_58:
      if ( *(_DWORD *)(a1 + 80) != v10 && v15 >= 2 )
      {
        v33 = *(_QWORD **)a3;
        while ( v33 )
        {
          v34 = v33;
          v35 = v33[2];
          v33 = (_QWORD *)*v33;
          if ( *(_DWORD *)(v35 + 8) == *(_DWORD *)(a3 + 48) )
          {
            CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::RemoveAt(a3, v34);
            CSPList<CTnMultiResNode *,CTnMultiResNode *>::AddHead(v36, v37);
          }
        }
      }
      goto LABEL_66;
    }
    v14 = 0;
    v39 = 0;
    while ( 1 )
    {
      v15 = v13;
      if ( v11 >= 50 || v47 <= v10 || v14 >= v12 )
        goto LABEL_58;
      v16 = (CTnMultiResCursor *)CSPList<CTnMultiResNode *,CTnMultiResNode *>::RemoveHead(v46);
      v40 = v16;
      v17 = *((_QWORD *)v16 + 3);
      LOBYTE(i) = 1;
      v38 = 1;
      v19 = *(_QWORD **)(v17 + 128);
      if ( v19 )
      {
        while ( 2 )
        {
          if ( !(_BYTE)i )
            goto LABEL_50;
          if ( (*(_BYTE *)(v17 + 232) & 8) == 0 )
          {
            v51 = (_QWORD *)*v19;
            v20 = (struct CAgreementElement *)v19[2];
            v45 = v20;
            for ( i = (_QWORD *)*((_QWORD *)v16 + 4); ; i = (_QWORD *)i[4] )
            {
              if ( !i )
              {
LABEL_33:
                LOBYTE(i) = v38;
                goto LABEL_42;
              }
              v21 = (_QWORD *)i[6];
              if ( v21 )
                break;
LABEL_25:
              v23 = i[3];
              v24 = *(_QWORD **)(v23 + 128);
              if ( v24 )
              {
                v25 = *(_DWORD *)v20;
                while ( 1 )
                {
                  v22 = (const struct CAgreementElement *)v24[2];
                  if ( *(_DWORD *)v22 == v25 )
                    goto LABEL_34;
                  v24 = (_QWORD *)*v24;
                  if ( !v24 )
                  {
                    v20 = v45;
                    break;
                  }
                }
              }
              if ( (*(_BYTE *)(v23 + 232) & 8) != 0 )
                goto LABEL_33;
            }
            while ( 1 )
            {
              v22 = (const struct CAgreementElement *)v21[2];
              if ( *(_DWORD *)v22 == *(_DWORD *)v20 )
                break;
              v21 = (_QWORD *)*v21;
              if ( !v21 )
                goto LABEL_25;
            }
LABEL_34:
            v26 = (CAgreementElement *)operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
            v27 = v26;
            v63 = v26;
            if ( !v26 )
              goto LABEL_39;
            *(_DWORD *)v26 = -1;
            *((_WORD *)v26 + 2) = -1;
            *((_DWORD *)v26 + 6) = 0;
            *((_QWORD *)v26 + 4) = 0;
            *((_QWORD *)v26 + 2) = 0;
            *((_QWORD *)v26 + 1) = 0;
            *((_QWORD *)v26 + 5) = 0;
            *((_DWORD *)v26 + 12) = 10;
            FullTextAndParseTree = CAgreementElement::Intersection(v26, v45, v22);
            if ( FullTextAndParseTree < 0 )
              goto LABEL_66;
            if ( *((_DWORD *)v27 + 6) )
            {
              v29 = CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(
                      (char *)v40 + 48,
                      v27);
              v10 = 0;
              if ( !v29 )
                goto LABEL_39;
              LOBYTE(i) = v38;
            }
            else
            {
              CAgreementElement::`scalar deleting destructor'(v27, v28);
              v10 = 0;
              LOBYTE(i) = 0;
              v38 = 0;
            }
            v16 = v40;
LABEL_42:
            v19 = v51;
            if ( v51 )
              continue;
            if ( !(_BYTE)i )
            {
LABEL_50:
              CTextNormMultiResult::DecrementCursorListMaxSize(
                (_DWORD)i,
                (unsigned int)v46,
                (unsigned int)v52,
                (unsigned int)&v41,
                (__int64)&v42);
              v14 = ++v39;
              v10 = 0;
              goto LABEL_55;
            }
          }
          break;
        }
        v4 = a4;
      }
      if ( *(_DWORD *)(v17 + 88) == v10 )
      {
        CTextNormMultiResult::DecrementCursorListMaxSize(
          (_DWORD)i,
          (unsigned int)v46,
          (unsigned int)v52,
          (unsigned int)&v41,
          (__int64)&v42);
        FullTextAndParseTree = CTextNormMultiResult::GetFullTextAndParseTree(
                                 a1,
                                 (_DWORD)v40,
                                 (unsigned int)&v43,
                                 a3,
                                 v4);
        v10 = 0;
        if ( FullTextAndParseTree < 0 )
          goto LABEL_66;
        if ( (*(_BYTE *)(v17 + 232) & 4) != 0 )
          *(_DWORD *)(a1 + 80) = 1;
        v14 = 0;
        v39 = 0;
      }
      else
      {
        v30 = *(__int64 ***)(v17 + 72);
        if ( v30 )
        {
          while ( 1 )
          {
            v31 = *v30;
            Child = CTnMultiResCursor::CreateChild(v16, (struct CTnMultiResNode *)v30[2]);
            if ( !Child )
              break;
            v30 = (__int64 **)v31;
            CTextNormMultiResult::PlaceCursorInQueue(
              (unsigned int)v52,
              (_DWORD)Child,
              (unsigned int)v46,
              v41,
              (__int64)v52);
            v10 = 0;
            v16 = v40;
            if ( !v31 )
              goto LABEL_54;
          }
LABEL_39:
          FullTextAndParseTree = -2147024882;
          goto LABEL_66;
        }
LABEL_54:
        v14 = v39;
      }
LABEL_55:
      v13 = *(_DWORD *)(a3 + 16);
      if ( v13 >= a2 )
        goto LABEL_57;
      v11 = v43;
      v12 = v44;
      v4 = a4;
    }
  }
  FullTextAndParseTree = 1;
LABEL_66:
  CSpClassFactory::~CSpClassFactory((CSpClassFactory *)v57);
  if ( v55 )
    CSPPlex::FreeDataChain(v55);
  if ( v49 )
    CSPPlex::FreeDataChain(v49);
  return (unsigned int)FullTextAndParseTree;
}

```

## disassembly

```asm
0x18000a614  mov     [rsp-8+arg_18], r9
0x18000a619  push    rbp
0x18000a61a  push    rbx
0x18000a61b  push    rsi
0x18000a61c  push    rdi
0x18000a61d  push    r12
0x18000a61f  push    r13
0x18000a621  push    r14
0x18000a623  push    r15
0x18000a625  lea     rbp, [rsp-18h]
0x18000a62a  sub     rsp, 118h
0x18000a631  mov     r15, r9
0x18000a634  mov     rsi, r8
0x18000a637  mov     r12d, edx
0x18000a63a  mov     r14, rcx
0x18000a63d  call    ?ProcessNetwork@CTextNormMultiResult@@AEAAJXZ; CTextNormMultiResult::ProcessNetwork(void)
0x18000a642  xor     r10d, r10d
0x18000a645  test    eax, eax
0x18000a647  js      loc_18000AA8A
0x18000a64d  mov     [rsp+150h+var_E8], r10d
0x18000a652  mov     [rsp+150h+var_E0], r10
0x18000a657  mov     [rsp+150h+var_F0], r10
0x18000a65c  mov     [rsp+150h+var_F8], r10
0x18000a661  mov     [rsp+150h+var_D8], r10
0x18000a666  lea     ecx, [r10+0Ah]
0x18000a66a  mov     [rbp+50h+var_D0], ecx
0x18000a66d  mov     [rbp+50h+var_B0], r10d
0x18000a671  mov     [rbp+50h+var_A8], r10
0x18000a675  mov     [rbp+50h+var_B8], r10
0x18000a679  mov     [rbp+50h+var_C0], r10
0x18000a67d  mov     [rbp+50h+var_A0], r10
0x18000a681  mov     [rbp+50h+var_98], ecx
0x18000a684  lea     edi, [r12+r12*4]
0x18000a688  add     edi, edi
0x18000a68a  mov     [rsp+150h+var_10C], edi
0x18000a68e  mov     [rsp+150h+var_110], edi
0x18000a692  lea     rax, ??_7CSpClassFactory@@6B@; const CSpClassFactory::`vftable'
0x18000a699  mov     [rbp+50h+var_90], rax
0x18000a69d  mov     [rbp+50h+var_78], r10d
0x18000a6a1  mov     [rbp+50h+var_70], r10
0x18000a6a5  mov     [rbp+50h+var_80], r10
0x18000a6a9  mov     [rbp+50h+var_88], r10
0x18000a6ad  mov     [rbp+50h+var_68], r10
0x18000a6b1  mov     [rbp+50h+var_60], ecx
0x18000a6b4  mov     [rbp+50h+var_58], r10d
0x18000a6b8  mov     [rsp+150h+var_118], r10
0x18000a6bd  test    rsi, rsi
0x18000a6c0  jz      loc_18000AA5B
0x18000a6c6  cmp     [rsi+10h], r10d
0x18000a6ca  jnz     loc_18000AA5B
0x18000a6d0  cmp     [r14+60h], r10
0x18000a6d4  jz      loc_18000AA5B
0x18000a6da  cmp     [r14+44h], r10d
0x18000a6de  jz      loc_18000AA5B
0x18000a6e4  test    r12d, r12d
0x18000a6e7  jnz     short loc_18000A6F1
0x18000a6e9  lea     ebx, [rcx-9]
0x18000a6ec  jmp     loc_18000AA60
0x18000a6f1  lea     rdx, [rsp+150h+var_118]
0x18000a6f6  lea     rcx, [rbp+50h+var_90]; this
0x18000a6fa  call    ??$CreateProduct@VCTnMultiResCursor@@@CSpClassFactory@@QEAAJPEAPEAVCTnMultiResCursor@@@Z; CSpClassFactory::CreateProduct<CTnMultiResCursor>(CTnMultiResCursor * *)
0x18000a6ff  mov     ebx, eax
0x18000a701  test    eax, eax
0x18000a703  js      loc_18000AA60
0x18000a709  mov     rcx, [r14+60h]
0x18000a70d  mov     rdx, [rsp+150h+var_118]
0x18000a712  mov     [rdx+18h], rcx
0x18000a716  lea     rax, [rbp+50h+var_C0]
0x18000a71a  mov     [rsp+150h+var_130], rax
0x18000a71f  mov     r9d, edi
0x18000a722  lea     r8, [rsp+150h+var_F8]
0x18000a727  call    ?PlaceCursorInQueue@CTextNormMultiResult@@AEBAXPEAVCTnMultiResCursor@@AEAV?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@J1@Z; CTextNormMultiResult::PlaceCursorInQueue(CTnMultiResCursor *,CSPList<CTnMultiResCursor *,CTnMultiResCursor *> &,long,CSPList<CTnMultiResCursor *,CTnMultiResCursor *> &)
0x18000a72c  xor     r10d, r10d
0x18000a72f  mov     r8d, r10d
0x18000a732  mov     [rsp+150h+var_108], r10d
0x18000a737  mov     eax, 405h
0x18000a73c  cmp     [r14+40h], ax
0x18000a741  jz      short loc_18000A763
0x18000a743  mov     eax, 41Bh
0x18000a748  cmp     [r14+40h], ax
0x18000a74d  jz      short loc_18000A763
0x18000a74f  lea     r9d, [rax-33h]
0x18000a753  mov     [rsp+150h+var_104], r9d
0x18000a758  lea     eax, [r9+3Ah]
0x18000a75c  cmp     [r14+40h], ax
0x18000a761  jnz     short loc_18000A76E
0x18000a763  mov     r9d, 61A8h
0x18000a769  mov     [rsp+150h+var_104], r9d
0x18000a76e  mov     eax, [rsi+10h]
0x18000a771  cmp     eax, r12d
0x18000a774  jge     loc_18000AA1C
0x18000a77a  mov     edx, r10d
0x18000a77d  mov     [rsp+150h+var_11C], edx
0x18000a781  mov     ecx, eax
0x18000a783  cmp     r8d, 32h ; '2'
0x18000a787  jge     loc_18000AA1E
0x18000a78d  cmp     [rsp+150h+var_E8], r10d
0x18000a792  jle     loc_18000AA1E
0x18000a798  cmp     edx, r9d
0x18000a79b  jnb     loc_18000AA1E
0x18000a7a1  lea     rcx, [rsp+150h+var_F8]
0x18000a7a6  call    ?RemoveHead@?$CSPList@PEAVCTnMultiResNode@@PEAV1@@@QEAAPEAVCTnMultiResNode@@XZ; CSPList<CTnMultiResNode *,CTnMultiResNode *>::RemoveHead(void)
0x18000a7ab  mov     r9, rax
0x18000a7ae  mov     [rsp+150h+var_118], rax
0x18000a7b3  mov     r13, [rax+18h]
0x18000a7b7  mov     cl, 1
0x18000a7b9  mov     [rsp+150h+var_120], cl
0x18000a7bd  mov     rax, [r13+80h]
0x18000a7c4  test    rax, rax
0x18000a7c7  jz      loc_18000A91C
0x18000a7cd  test    cl, cl
0x18000a7cf  jz      loc_18000A985
0x18000a7d5  test    byte ptr [r13+0E8h], 8
0x18000a7dd  jnz     loc_18000A918
0x18000a7e3  mov     rcx, [rax]
0x18000a7e6  mov     [rbp+50h+var_C8], rcx
0x18000a7ea  mov     r8, [rax+10h]
0x18000a7ee  mov     [rsp+150h+var_100], r8
0x18000a7f3  mov     rcx, [r9+20h]
0x18000a7f7  jmp     short loc_18000A84C
0x18000a7f9  mov     rax, [rcx+30h]
0x18000a7fd  test    rax, rax
0x18000a800  jz      short loc_18000A816
0x18000a802  mov     edx, [r8]
0x18000a805  mov     r15, [rax+10h]
0x18000a809  cmp     [r15], edx
0x18000a80c  jz      short loc_18000A85A
0x18000a80e  mov     rax, [rax]
0x18000a811  test    rax, rax
0x18000a814  jnz     short loc_18000A805
0x18000a816  mov     rdx, [rcx+18h]
0x18000a81a  mov     rax, [rdx+80h]
0x18000a821  test    rax, rax
0x18000a824  jz      short loc_18000A83F
0x18000a826  mov     r8d, [r8]
0x18000a829  mov     r15, [rax+10h]
0x18000a82d  cmp     [r15], r8d
0x18000a830  jz      short loc_18000A85A
0x18000a832  mov     rax, [rax]
0x18000a835  test    rax, rax
0x18000a838  jnz     short loc_18000A829
0x18000a83a  mov     r8, [rsp+150h+var_100]
0x18000a83f  test    byte ptr [rdx+0E8h], 8
0x18000a846  jnz     short loc_18000A851
0x18000a848  mov     rcx, [rcx+20h]
0x18000a84c  test    rcx, rcx
0x18000a84f  jnz     short loc_18000A7F9
0x18000a851  mov     cl, [rsp+150h+var_120]
0x18000a855  jmp     loc_18000A907
0x18000a85a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a861  mov     ecx, 38h ; '8'; unsigned __int64
0x18000a866  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a86b  mov     rdi, rax
0x18000a86e  mov     [rbp+50h+var_50], rax
0x18000a872  xor     ecx, ecx
0x18000a874  test    rax, rax
0x18000a877  jz      short loc_18000A8F4
0x18000a879  mov     dword ptr [rax], 0FFFFFFFFh
0x18000a87f  mov     word ptr [rax+4], 0FFFFh
0x18000a885  mov     [rax+18h], ecx
0x18000a888  mov     [rax+20h], rcx
0x18000a88c  mov     [rax+10h], rcx
0x18000a890  mov     [rax+8], rcx
0x18000a894  mov     [rax+28h], rcx
0x18000a898  mov     dword ptr [rax+30h], 0Ah
0x18000a89f  test    rax, rax
0x18000a8a2  jz      short loc_18000A8F4
0x18000a8a4  mov     r8, r15; struct CAgreementElement *
0x18000a8a7  mov     rdx, [rsp+150h+var_100]; struct CAgreementElement *
0x18000a8ac  mov     rcx, rax; this
0x18000a8af  call    ?Intersection@CAgreementElement@@QEAAJAEBV1@0@Z; CAgreementElement::Intersection(CAgreementElement const &,CAgreementElement const &)
0x18000a8b4  mov     ebx, eax
0x18000a8b6  xor     r10d, r10d
0x18000a8b9  test    eax, eax
0x18000a8bb  js      loc_18000AA60
0x18000a8c1  cmp     [rdi+18h], r10d
0x18000a8c5  jnz     short loc_18000A8DB
0x18000a8c7  mov     rcx, rdi; this
0x18000a8ca  call    ??_GCAgreementElement@@QEAAPEAXI@Z; CAgreementElement::`scalar deleting destructor'(uint)
0x18000a8cf  xor     r10d, r10d
0x18000a8d2  mov     cl, r10b
0x18000a8d5  mov     [rsp+150h+var_120], cl
0x18000a8d9  jmp     short loc_18000A902
0x18000a8db  mov     rcx, [rsp+150h+var_118]
0x18000a8e0  add     rcx, 30h ; '0'
0x18000a8e4  mov     rdx, rdi
0x18000a8e7  call    ?AddTail@?$CSPList@PEAUSStrCost@CTnMultiResStringPackage@@PEAU12@@@QEAAPEAXPEAUSStrCost@CTnMultiResStringPackage@@@Z; CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(CTnMultiResStringPackage::SStrCost *)
0x18000a8ec  xor     r10d, r10d
0x18000a8ef  test    rax, rax
0x18000a8f2  jnz     short loc_18000A8FE
0x18000a8f4  mov     ebx, 8007000Eh
0x18000a8f9  jmp     loc_18000AA60
0x18000a8fe  mov     cl, [rsp+150h+var_120]
0x18000a902  mov     r9, [rsp+150h+var_118]
0x18000a907  mov     rax, [rbp+50h+var_C8]
0x18000a90b  test    rax, rax
0x18000a90e  jnz     loc_18000A7CD
0x18000a914  test    cl, cl
0x18000a916  jz      short loc_18000A985
0x18000a918  mov     r15, [rbp+50h+arg_18]
0x18000a91c  cmp     [r13+58h], r10d
0x18000a920  jnz     loc_18000A9B1
0x18000a926  lea     rax, [rsp+150h+var_10C]
0x18000a92b  mov     [rsp+150h+var_130], rax
0x18000a930  lea     r9, [rsp+150h+var_110]
0x18000a935  lea     r8, [rbp+50h+var_C0]
0x18000a939  lea     rdx, [rsp+150h+var_F8]
0x18000a93e  call    ?DecrementCursorListMaxSize@CTextNormMultiResult@@AEAAXAEAV?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@0AEAJ1@Z; CTextNormMultiResult::DecrementCursorListMaxSize(CSPList<CTnMultiResCursor *,CTnMultiResCursor *> &,CSPList<CTnMultiResCursor *,CTnMultiResCursor *> &,long &,long &)
0x18000a943  mov     [rsp+150h+var_130], r15
0x18000a948  mov     r9, rsi
0x18000a94b  lea     r8, [rsp+150h+var_108]
0x18000a950  mov     rdx, [rsp+150h+var_118]
0x18000a955  mov     rcx, r14
0x18000a958  call    ?GetFullTextAndParseTree@CTextNormMultiResult@@AEAAJPEAVCTnMultiResCursor@@AEAHPEAVCTnMultiResStringPackage@@PEAV?$CSPList@PEAUIParseTreeNode@@PEAU1@@@@Z; CTextNormMultiResult::GetFullTextAndParseTree(CTnMultiResCursor *,int &,CTnMultiResStringPackage *,CSPList<IParseTreeNode *,IParseTreeNode *> *)
0x18000a95d  mov     ebx, eax
0x18000a95f  xor     r10d, r10d
0x18000a962  test    eax, eax
0x18000a964  js      loc_18000AA60
0x18000a96a  test    byte ptr [r13+0E8h], 4
0x18000a972  jz      short loc_18000A97C
0x18000a974  mov     dword ptr [r14+50h], 1
0x18000a97c  mov     edx, r10d
0x18000a97f  mov     [rsp+150h+var_11C], edx
0x18000a983  jmp     short loc_18000AA01
0x18000a985  lea     rax, [rsp+150h+var_10C]
0x18000a98a  mov     [rsp+150h+var_130], rax
0x18000a98f  lea     r9, [rsp+150h+var_110]
0x18000a994  lea     r8, [rbp+50h+var_C0]
0x18000a998  lea     rdx, [rsp+150h+var_F8]
0x18000a99d  call    ?DecrementCursorListMaxSize@CTextNormMultiResult@@AEAAXAEAV?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@0AEAJ1@Z; CTextNormMultiResult::DecrementCursorListMaxSize(CSPList<CTnMultiResCursor *,CTnMultiResCursor *> &,CSPList<CTnMultiResCursor *,CTnMultiResCursor *> &,long &,long &)
0x18000a9a2  mov     edx, [rsp+150h+var_11C]
0x18000a9a6  inc     edx
0x18000a9a8  mov     [rsp+150h+var_11C], edx
0x18000a9ac  xor     r10d, r10d
0x18000a9af  jmp     short loc_18000AA01
0x18000a9b1  mov     rdi, [r13+48h]
0x18000a9b5  test    rdi, rdi
0x18000a9b8  jz      short loc_18000A9FD
0x18000a9ba  mov     r15, [rdi]
0x18000a9bd  mov     rdx, [rdi+10h]; struct CTnMultiResNode *
0x18000a9c1  mov     rcx, r9; this
0x18000a9c4  call    ?CreateChild@CTnMultiResCursor@@QEAAPEAV1@PEAVCTnMultiResNode@@@Z; CTnMultiResCursor::CreateChild(CTnMultiResNode *)
0x18000a9c9  test    rax, rax
0x18000a9cc  jz      loc_18000A8F4
0x18000a9d2  mov     rdi, r15
0x18000a9d5  lea     rcx, [rbp+50h+var_C0]
0x18000a9d9  mov     [rsp+150h+var_130], rcx
0x18000a9de  mov     r9d, [rsp+150h+var_110]
0x18000a9e3  lea     r8, [rsp+150h+var_F8]
0x18000a9e8  mov     rdx, rax
0x18000a9eb  call    ?PlaceCursorInQueue@CTextNormMultiResult@@AEBAXPEAVCTnMultiResCursor@@AEAV?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@J1@Z; CTextNormMultiResult::PlaceCursorInQueue(CTnMultiResCursor *,CSPList<CTnMultiResCursor *,CTnMultiResCursor *> &,long,CSPList<CTnMultiResCursor *,CTnMultiResCursor *> &)
0x18000a9f0  xor     r10d, r10d
0x18000a9f3  test    r15, r15
0x18000a9f6  mov     r9, [rsp+150h+var_118]
0x18000a9fb  jnz     short loc_18000A9BA
0x18000a9fd  mov     edx, [rsp+150h+var_11C]
0x18000aa01  mov     eax, [rsi+10h]
0x18000aa04  cmp     eax, r12d
0x18000aa07  jge     short loc_18000AA1C
0x18000aa09  mov     r8d, [rsp+150h+var_108]
0x18000aa0e  mov     r9d, [rsp+150h+var_104]
0x18000aa13  mov     r15, [rbp+50h+arg_18]
0x18000aa17  jmp     loc_18000A781
0x18000aa1c  mov     ecx, eax
0x18000aa1e  cmp     [r14+50h], r10d
0x18000aa22  jz      short loc_18000AA60
0x18000aa24  cmp     ecx, 2
0x18000aa27  jl      short loc_18000AA60
0x18000aa29  mov     rdi, [rsi]
0x18000aa2c  jmp     short loc_18000AA54
0x18000aa2e  mov     rdx, rdi
0x18000aa31  mov     r9, [rdi+10h]
0x18000aa35  mov     rdi, [rdi]
0x18000aa38  mov     eax, [rsi+30h]
0x18000aa3b  cmp     [r9+8], eax
0x18000aa3f  jnz     short loc_18000AA54
0x18000aa41  mov     rcx, rsi
0x18000aa44  call    ?RemoveAt@?$CSPList@PEAUSStrCost@CTnMultiResStringPackage@@PEAU12@@@QEAAXPEAX@Z; CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::RemoveAt(void *)
0x18000aa49  mov     rdx, r9
0x18000aa4c  call    ?AddHead@?$CSPList@PEAVCTnMultiResNode@@PEAV1@@@QEAAPEAXPEAVCTnMultiResNode@@@Z; CSPList<CTnMultiResNode *,CTnMultiResNode *>::AddHead(CTnMultiResNode *)
0x18000aa51  xor     r10d, r10d
0x18000aa54  test    rdi, rdi
0x18000aa57  jnz     short loc_18000AA2E
0x18000aa59  jmp     short loc_18000AA60
0x18000aa5b  mov     ebx, 80070057h
0x18000aa60  lea     rcx, [rbp+50h+var_90]; this
0x18000aa64  call    ??1CSpClassFactory@@UEAA@XZ; CSpClassFactory::~CSpClassFactory(void)
0x18000aa69  nop
0x18000aa6a  mov     rcx, [rbp+50h+var_A0]; this
0x18000aa6e  test    rcx, rcx
0x18000aa71  jz      short loc_18000AA79
0x18000aa73  call    ?FreeDataChain@CSPPlex@@QEAAXXZ; CSPPlex::FreeDataChain(void)
0x18000aa78  nop
0x18000aa79  mov     rcx, [rsp+150h+var_D8]; this
0x18000aa7e  test    rcx, rcx
0x18000aa81  jz      short loc_18000AA88
0x18000aa83  call    ?FreeDataChain@CSPPlex@@QEAAXXZ; CSPPlex::FreeDataChain(void)
0x18000aa88  mov     eax, ebx
0x18000aa8a  add     rsp, 118h
0x18000aa91  pop     r15
  ... truncated ...
```
