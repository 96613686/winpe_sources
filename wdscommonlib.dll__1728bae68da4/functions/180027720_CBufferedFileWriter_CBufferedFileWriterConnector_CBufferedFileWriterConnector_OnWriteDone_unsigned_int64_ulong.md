# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::MergeAndWriteBuffer(ulong)

- ea: `0x180027720`
- end: `0x180027ab2`
- name: `?MergeAndWriteBuffer@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKK@Z`
- size: `914`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027c10`
- `0x1800280d0`

## callees

- `0x18000214c`
- `0x1800272cc`
- `0x180027440`
- `0x180027580`
- `0x180027720`
- `0x1800284e0`

## import_xrefs

- `msvcrt!qsort_s` at `0x1800277f3`
- `msvcrt!qsort_s` at `0x18002790c`
- `msvcrt!qsort_s` at `0x1800277f3`
- `msvcrt!qsort_s` at `0x18002790c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027a20`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027a34`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027a7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027a8e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027a20`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027a34`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027a7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027a8e`

## string_xrefs

- `0x18002786b`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x1800278d8`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x18002799a`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x1800279ca`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

## pseudocode

```c
__int64 __fastcall CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::MergeAndWriteBuffer(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r15
  _QWORD *v3; // rbx
  int v4; // edi
  int v5; // r14d
  int v6; // esi
  unsigned int v7; // r12d
  unsigned __int64 v9; // rax
  _QWORD *v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rax
  _QWORD *v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v18; // edi
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // esi
  int v22; // edi
  __m128i v23; // xmm1
  __int64 v24; // rdx
  __int64 v25; // rbx
  _QWORD *v26; // r12
  __int64 v27; // rsi
  _QWORD *v28; // rdi
  void *v29; // rcx
  _BYTE v30[24]; // [rsp+30h] [rbp-59h] BYREF
  int v31; // [rsp+48h] [rbp-41h]
  void *Base; // [rsp+50h] [rbp-39h] BYREF
  rsize_t NumOfElements; // [rsp+58h] [rbp-31h]
  __int64 v34; // [rsp+68h] [rbp-21h]
  _QWORD *v35; // [rsp+70h] [rbp-19h] BYREF
  __int128 v36; // [rsp+80h] [rbp-9h] BYREF
  __int64 v37; // [rsp+90h] [rbp+7h]
  int v40; // [rsp+100h] [rbp+77h]
  int v41; // [rsp+108h] [rbp+7Fh]

  LODWORD(v2) = 0;
  Base = 0;
  v3 = 0;
  NumOfElements = 0;
  v4 = 0;
  *(_QWORD *)v30 = 0;
  v5 = -1;
  *(_QWORD *)&v30[8] = 0xFFFFFFFF00000000uLL;
  v6 = -1;
  *(_DWORD *)&v30[16] = -1;
  v7 = 0;
  v40 = 0;
  if ( !*(_DWORD *)(a1 + 116) )
    return 0;
  v9 = 8LL * *(unsigned int *)(a1 + 116);
  if ( !is_mul_ok(*(unsigned int *)(a1 + 116), 8u) )
    v9 = -1;
  v10 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  if ( v10 )
  {
    v34 = a1 + 96;
    v11 = *(_QWORD *)(a1 + 96);
    if ( v11 )
    {
      do
      {
        v12 = v7++;
        v10[v12] = v11;
        v11 = *(_QWORD *)(v11 + 24);
      }
      while ( v11 );
      v40 = v7;
    }
    qsort_s(
      v10,
      v7,
      8u,
      CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::_DATA_BLOCK::CompareByOffset,
      0);
    if ( (int)v7 > 0 )
    {
      v13 = v10;
      do
      {
        if ( v5 == -1 )
        {
          v14 = *v13;
          v5 = 0;
          *(_QWORD *)&v30[12] = 0;
          v6 = 0;
          v4 = *(_DWORD *)(v14 + 8);
          *(_QWORD *)v30 = *(_QWORD *)v14;
        }
        else
        {
          if ( *(_QWORD *)*v13 == *(_QWORD *)v10[v6] + *(unsigned int *)(v10[v6] + 8LL) )
          {
            v4 += *(_DWORD *)(*v13 + 8LL);
          }
          else
          {
            v36 = *(_OWORD *)v30;
            v37 = *(_QWORD *)&v30[16];
            v2 = (unsigned int)CDynArray<CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::DATA_SEGMENT,CDeallocateNone>::AddItem(
                                 &Base,
                                 &v36);
            if ( (unsigned int)ElValidateWin32_14(
                                 v2,
                                 v15,
                                 "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
                                 799) )
              goto LABEL_40;
            v16 = *v13;
            v5 = (int)v3;
            *(_DWORD *)&v30[12] = (_DWORD)v3;
            v4 = *(_DWORD *)(v16 + 8);
            *(_QWORD *)v30 = *(_QWORD *)v16;
          }
          *(_DWORD *)&v30[16] = (_DWORD)v3;
          v6 = (int)v3;
        }
        LODWORD(v3) = (_DWORD)v3 + 1;
        *(_DWORD *)&v30[8] = v4;
        ++v13;
      }
      while ( (int)v3 < v40 );
      v7 = v40;
    }
    v36 = *(_OWORD *)v30;
    v37 = *(_QWORD *)&v30[16];
    CDynArray<CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::DATA_SEGMENT,CDeallocateNone>::AddItem(
      &Base,
      &v36);
    if ( (unsigned int)ElValidateWin32_14(
                         (unsigned int)v2,
                         v17,
                         "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
                         816) )
    {
LABEL_40:
      v3 = Base;
    }
    else
    {
      v18 = HIDWORD(NumOfElements);
      v3 = Base;
      qsort_s(
        Base,
        HIDWORD(NumOfElements),
        0x18u,
        CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::DATA_SEGMENT::CompareBySizeDesc,
        0);
      v20 = 0;
      v31 = 0;
      if ( v18 )
      {
        do
        {
          if ( a2 && *(_DWORD *)(a1 + 88) <= a2 )
            break;
          *(_QWORD *)v30 = 0;
          v21 = -1;
          v22 = -1;
          v41 = 0;
          LODWORD(v2) = 0;
          *(_QWORD *)&v30[8] = 0xFFFFFFFF00000000uLL;
          *(_DWORD *)&v30[16] = -1;
          if ( (unsigned int)v20 < HIDWORD(NumOfElements) )
          {
            v23 = *(__m128i *)&v3[3 * v20];
            *(_QWORD *)&v30[16] = v3[3 * v20 + 2];
            v22 = *(_DWORD *)&v30[16];
            *(__m128i *)v30 = v23;
            v21 = _mm_cvtsi128_si32(_mm_srli_si128(v23, 12));
            v41 = _mm_cvtsi128_si32(_mm_loadl_epi64((const __m128i *)&v3[3 * v20 + 1]));
          }
          else
          {
            LODWORD(v2) = 1413;
          }
          if ( (unsigned int)ElValidateWin32_14(
                               (unsigned int)v2,
                               v19,
                               "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
                               843) )
            break;
          v2 = (unsigned int)CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::IssueWrite(
                               a1,
                               (__int64)v30,
                               (__int64)v10,
                               v7);
          if ( (unsigned int)ElValidateWin32_14(
                               v2,
                               v24,
                               "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
                               848) )
            break;
          if ( v21 <= v22 )
          {
            v25 = v34;
            v26 = &v10[v21];
            v27 = (unsigned int)(v22 - v21 + 1);
            do
            {
              v35 = (_QWORD *)*v26;
              v28 = v35;
              CList<CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::_DATA_BLOCK,CNoLock>::DeleteAt(
                v25,
                &v35);
              if ( v28 )
              {
                v29 = (void *)v28[2];
                if ( v29 )
                {
                  operator delete(v29);
                  v28[2] = 0;
                }
                operator delete(v28);
              }
              ++v26;
              --v27;
            }
            while ( v27 );
            v3 = Base;
            v7 = v40;
          }
          *(_DWORD *)(a1 + 88) -= v41;
          v20 = (unsigned int)(v31 + 1);
          v31 = v20;
        }
        while ( (unsigned int)v20 < HIDWORD(NumOfElements) );
      }
    }
    operator delete(v10);
  }
  else
  {
    LODWORD(v2) = 8;
  }
  if ( v3 )
    operator delete(v3);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180027720  mov     [rsp-8+arg_8], edx
0x180027724  mov     [rsp-8+arg_0], rcx
0x180027729  push    rbp
0x18002772a  push    rbx
0x18002772b  push    rsi
0x18002772c  push    rdi
0x18002772d  push    r12
0x18002772f  push    r13
0x180027731  push    r14
0x180027733  push    r15
0x180027735  lea     rbp, [rsp-1Fh]
0x18002773a  sub     rsp, 0A8h
0x180027741  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027745  mov     rax, rcx
0x180027748  xor     ecx, ecx
0x18002774a  mov     dword ptr [rbp+57h+var_B0+0Ch], r8d
0x18002774e  mov     r15d, ecx
0x180027751  mov     [rbp+57h+Base], rcx
0x180027755  mov     ebx, ecx
0x180027757  mov     [rbp+57h+NumOfElements], rcx
0x18002775b  mov     edi, ecx
0x18002775d  mov     qword ptr [rbp+57h+var_B0], rcx
0x180027761  mov     r14d, r8d
0x180027764  mov     dword ptr [rbp+57h+var_B0+8], ecx
0x180027767  mov     esi, r8d
0x18002776a  mov     dword ptr [rbp+57h+var_A0], r8d
0x18002776e  mov     r12d, ecx
0x180027771  mov     [rbp+57h+arg_10], ecx
0x180027774  cmp     [rax+74h], ecx
0x180027777  jnz     short loc_180027780
0x180027779  xor     eax, eax
0x18002777b  jmp     loc_180027A9D
0x180027780  mov     ecx, [rax+74h]
0x180027783  mov     eax, 8
0x180027788  mul     rcx
0x18002778b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027792  cmovo   rax, r8
0x180027796  mov     rcx, rax; unsigned __int64
0x180027799  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002779e  mov     r13, rax
0x1800277a1  test    rax, rax
0x1800277a4  jnz     short loc_1800277AF
0x1800277a6  lea     r15d, [rax+8]
0x1800277aa  jmp     loc_180027A86
0x1800277af  mov     rax, [rbp+57h+arg_0]
0x1800277b3  add     rax, 60h ; '`'
0x1800277b7  mov     [rbp+57h+var_78], rax
0x1800277bb  mov     rcx, [rax]
0x1800277be  test    rcx, rcx
0x1800277c1  jz      short loc_1800277DB
0x1800277c3  mov     eax, r12d
0x1800277c6  inc     r12d
0x1800277c9  mov     [r13+rax*8+0], rcx
0x1800277ce  mov     rcx, [rcx+18h]
0x1800277d2  test    rcx, rcx
0x1800277d5  jnz     short loc_1800277C3
0x1800277d7  mov     [rbp+57h+arg_10], r12d
0x1800277db  and     [rsp+0E0h+var_C0], rbx
0x1800277e0  lea     r9, ?CompareByOffset@_DATA_BLOCK@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@SAHPEAXPEBX1@Z; CompareFunction
0x1800277e7  mov     edx, r12d; NumOfElements
0x1800277ea  mov     r8d, 8; SizeOfElements
0x1800277f0  mov     rcx, r13; Base
0x1800277f3  call    cs:__imp_qsort_s
0x1800277fa  nop     dword ptr [rax+rax+00h]
0x1800277ff  test    r12d, r12d
0x180027802  jle     loc_1800278B3
0x180027808  mov     r12, r13
0x18002780b  cmp     r14d, 0FFFFFFFFh
0x18002780f  jnz     short loc_18002782A
0x180027811  mov     rcx, [r12]
0x180027815  xor     r14d, r14d
0x180027818  mov     qword ptr [rbp+57h+var_B0+0Ch], r14
0x18002781c  xor     esi, esi
0x18002781e  mov     rax, [rcx]
0x180027821  mov     edi, [rcx+8]
0x180027824  mov     qword ptr [rbp+57h+var_B0], rax
0x180027828  jmp     short loc_18002789D
0x18002782a  mov     rdx, [r12]
0x18002782e  movsxd  rax, esi
0x180027831  mov     rcx, [r13+rax*8+0]
0x180027836  mov     eax, [rcx+8]
0x180027839  add     rax, [rcx]
0x18002783c  cmp     [rdx], rax
0x18002783f  jnz     short loc_180027846
0x180027841  add     edi, [rdx+8]
0x180027844  jmp     short loc_180027898
0x180027846  movups  xmm0, [rbp+57h+var_B0]
0x18002784a  lea     rdx, [rbp+57h+var_60]
0x18002784e  movsd   xmm1, [rbp+57h+var_A0]
0x180027853  lea     rcx, [rbp+57h+Base]
0x180027857  movaps  [rbp+57h+var_60], xmm0
0x18002785b  movsd   [rbp+57h+var_50], xmm1
0x180027860  call    ?AddItem@?$CDynArray@UDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@VCDeallocateNone@@@@QEAAKUDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@@Z; CDynArray<CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT,CDeallocateNone>::AddItem(CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT)
0x180027865  mov     r9d, 31Fh
0x18002786b  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180027872  mov     ecx, eax
0x180027874  mov     r15d, eax
0x180027877  call    ElValidateWin32_14
0x18002787c  test    eax, eax
0x18002787e  jnz     loc_180027A73
0x180027884  mov     rdx, [r12]
0x180027888  mov     r14d, ebx
0x18002788b  mov     dword ptr [rbp+57h+var_B0+0Ch], ebx
0x18002788e  mov     rcx, [rdx]
0x180027891  mov     edi, [rdx+8]
0x180027894  mov     qword ptr [rbp+57h+var_B0], rcx
0x180027898  mov     dword ptr [rbp+57h+var_A0], ebx
0x18002789b  mov     esi, ebx
0x18002789d  inc     ebx
0x18002789f  mov     dword ptr [rbp+57h+var_B0+8], edi
0x1800278a2  add     r12, 8
0x1800278a6  cmp     ebx, [rbp+57h+arg_10]
0x1800278a9  jl      loc_18002780B
0x1800278af  mov     r12d, [rbp+57h+arg_10]
0x1800278b3  movups  xmm0, [rbp+57h+var_B0]
0x1800278b7  lea     rdx, [rbp+57h+var_60]
0x1800278bb  movsd   xmm1, [rbp+57h+var_A0]
0x1800278c0  lea     rcx, [rbp+57h+Base]
0x1800278c4  movaps  [rbp+57h+var_60], xmm0
0x1800278c8  movsd   [rbp+57h+var_50], xmm1
0x1800278cd  call    ?AddItem@?$CDynArray@UDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@VCDeallocateNone@@@@QEAAKUDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@@Z; CDynArray<CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT,CDeallocateNone>::AddItem(CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT)
0x1800278d2  mov     r9d, 330h
0x1800278d8  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800278df  mov     ecx, r15d
0x1800278e2  call    ElValidateWin32_14
0x1800278e7  test    eax, eax
0x1800278e9  jnz     loc_180027A73
0x1800278ef  mov     edi, dword ptr [rbp+57h+NumOfElements+4]
0x1800278f2  lea     r9, ?CompareBySizeDesc@DATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@SAHPEAXPEBX1@Z; CompareFunction
0x1800278f9  mov     rbx, [rbp+57h+Base]
0x1800278fd  lea     r8d, [rax+18h]; SizeOfElements
0x180027901  and     [rsp+0E0h+var_C0], 0
0x180027907  mov     edx, edi; NumOfElements
0x180027909  mov     rcx, rbx; Base
0x18002790c  call    cs:__imp_qsort_s
0x180027913  nop     dword ptr [rax+rax+00h]
0x180027918  xor     eax, eax
0x18002791a  mov     [rbp+57h+var_98], eax
0x18002791d  test    edi, edi
0x18002791f  jz      loc_180027A77
0x180027925  mov     r14, [rbp+57h+arg_0]
0x180027929  mov     ecx, [rbp+57h+arg_8]
0x18002792c  test    ecx, ecx
0x18002792e  jz      short loc_18002793A
0x180027930  cmp     [r14+58h], ecx
0x180027934  jbe     loc_180027A77
0x18002793a  and     qword ptr [rbp+57h+var_B0], 0
0x18002793f  or      esi, 0FFFFFFFFh
0x180027942  xor     ecx, ecx
0x180027944  mov     dword ptr [rbp+57h+var_B0+0Ch], esi
0x180027947  or      edi, esi
0x180027949  mov     [rbp+57h+arg_18], ecx
0x18002794c  xor     r15d, r15d
0x18002794f  mov     dword ptr [rbp+57h+var_B0+8], ecx
0x180027952  mov     dword ptr [rbp+57h+var_A0], edi
0x180027955  cmp     eax, dword ptr [rbp+57h+NumOfElements+4]
0x180027958  jb      short loc_180027962
0x18002795a  mov     r15d, 585h
0x180027960  jmp     short loc_180027994
0x180027962  lea     rcx, [rax+rax*2]
0x180027966  movups  xmm2, xmmword ptr [rbx+rcx*8]
0x18002796a  movsd   xmm0, qword ptr [rbx+rcx*8+10h]
0x180027970  movdqa  xmm1, xmm2
0x180027974  movsd   [rbp+57h+var_A0], xmm0
0x180027979  mov     edi, dword ptr [rbp+57h+var_A0]
0x18002797c  movups  [rbp+57h+var_B0], xmm2
0x180027980  movq    xmm2, qword ptr [rbx+rcx*8+8]
0x180027986  psrldq  xmm1, 0Ch
0x18002798b  movd    esi, xmm1
0x18002798f  movd    [rbp+57h+arg_18], xmm2
0x180027994  mov     r9d, 34Bh
0x18002799a  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800279a1  mov     ecx, r15d
0x1800279a4  call    ElValidateWin32_14
0x1800279a9  test    eax, eax
0x1800279ab  jnz     loc_180027A77
0x1800279b1  mov     rcx, [rbp+57h+arg_0]
0x1800279b5  lea     rdx, [rbp+57h+var_B0]
0x1800279b9  mov     r9d, r12d
0x1800279bc  mov     r8, r13
0x1800279bf  call    ?IssueWrite@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKPEAUDATA_SEGMENT@1@PEAPEAU_DATA_BLOCK@1@K@Z; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::IssueWrite(CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT *,CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::_DATA_BLOCK * *,ulong)
0x1800279c4  mov     r9d, 350h
0x1800279ca  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800279d1  mov     ecx, eax
0x1800279d3  mov     r15d, eax
0x1800279d6  call    ElValidateWin32_14
0x1800279db  test    eax, eax
0x1800279dd  jnz     loc_180027A77
0x1800279e3  cmp     esi, edi
0x1800279e5  jg      short loc_180027A52
0x1800279e7  mov     rbx, [rbp+57h+var_78]
0x1800279eb  movsxd  rax, esi
0x1800279ee  lea     r12, ds:0[rax*8]
0x1800279f6  add     r12, r13
0x1800279f9  sub     edi, esi
0x1800279fb  lea     esi, [rdi+1]
0x1800279fe  mov     rdi, [r12]
0x180027a02  lea     rdx, [rbp+57h+var_70]
0x180027a06  mov     rcx, rbx
0x180027a09  mov     [rbp+57h+var_70], rdi
0x180027a0d  call    ?DeleteAt@?$CList@U_DATA_BLOCK@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@VCNoLock@@@@QEAAPEAU_DATA_BLOCK@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAPEAX@Z; CList<CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::_DATA_BLOCK,CNoLock>::DeleteAt(void * &)
0x180027a12  test    rdi, rdi
0x180027a15  jz      short loc_180027A40
0x180027a17  mov     rcx, [rdi+10h]
0x180027a1b  test    rcx, rcx
0x180027a1e  jz      short loc_180027A31
0x180027a20  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027a27  nop     dword ptr [rax+rax+00h]
0x180027a2c  and     qword ptr [rdi+10h], 0
0x180027a31  mov     rcx, rdi
0x180027a34  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027a3b  nop     dword ptr [rax+rax+00h]
0x180027a40  add     r12, 8
0x180027a44  sub     rsi, 1
0x180027a48  jnz     short loc_1800279FE
0x180027a4a  mov     rbx, [rbp+57h+Base]
0x180027a4e  mov     r12d, [rbp+57h+arg_10]
0x180027a52  mov     eax, [r14+58h]
0x180027a56  sub     eax, [rbp+57h+arg_18]
0x180027a59  mov     rcx, [rbp+57h+arg_0]
0x180027a5d  mov     [rcx+58h], eax
0x180027a60  mov     eax, [rbp+57h+var_98]
0x180027a63  inc     eax
0x180027a65  mov     [rbp+57h+var_98], eax
0x180027a68  cmp     eax, dword ptr [rbp+57h+NumOfElements+4]
0x180027a6b  jb      loc_180027929
0x180027a71  jmp     short loc_180027A77
0x180027a73  mov     rbx, [rbp+57h+Base]
0x180027a77  mov     rcx, r13
0x180027a7a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027a81  nop     dword ptr [rax+rax+00h]
0x180027a86  test    rbx, rbx
0x180027a89  jz      short loc_180027A9A
0x180027a8b  mov     rcx, rbx
0x180027a8e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027a95  nop     dword ptr [rax+rax+00h]
0x180027a9a  mov     eax, r15d
0x180027a9d  add     rsp, 0A8h
0x180027aa4  pop     r15
0x180027aa6  pop     r14
0x180027aa8  pop     r13
0x180027aaa  pop     r12
0x180027aac  pop     rdi
0x180027aad  pop     rsi
0x180027aae  pop     rbx
0x180027aaf  pop     rbp
0x180027ab0  retn
```
