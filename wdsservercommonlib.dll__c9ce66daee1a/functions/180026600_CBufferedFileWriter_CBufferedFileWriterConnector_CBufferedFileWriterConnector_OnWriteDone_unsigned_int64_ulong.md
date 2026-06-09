# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::MergeAndWriteBuffer(ulong)

- ea: `0x180026600`
- end: `0x180026976`
- name: `?MergeAndWriteBuffer@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKK@Z`
- size: `886`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026ad0`
- `0x180026f90`

## callees

- `0x18000179c`
- `0x1800261ac`
- `0x180026310`
- `0x180026450`
- `0x180026600`
- `0x180027390`
- `0x18002e468`

## import_xrefs

- `msvcrt!qsort_s` at `0x1800266d3`
- `msvcrt!qsort_s` at `0x1800267ec`
- `msvcrt!qsort_s` at `0x1800266d3`
- `msvcrt!qsort_s` at `0x1800267ec`

## string_xrefs

- `0x18002674b`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x1800267b8`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x18002687a`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x1800268aa`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

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
0x180026600  mov     [rsp-8+arg_8], edx
0x180026604  mov     [rsp-8+arg_0], rcx
0x180026609  push    rbp
0x18002660a  push    rbx
0x18002660b  push    rsi
0x18002660c  push    rdi
0x18002660d  push    r12
0x18002660f  push    r13
0x180026611  push    r14
0x180026613  push    r15
0x180026615  lea     rbp, [rsp-1Fh]
0x18002661a  sub     rsp, 0A8h
0x180026621  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026625  mov     rax, rcx
0x180026628  xor     ecx, ecx
0x18002662a  mov     dword ptr [rbp+57h+var_B0+0Ch], r8d
0x18002662e  mov     r15d, ecx
0x180026631  mov     [rbp+57h+Base], rcx
0x180026635  mov     ebx, ecx
0x180026637  mov     [rbp+57h+NumOfElements], rcx
0x18002663b  mov     edi, ecx
0x18002663d  mov     qword ptr [rbp+57h+var_B0], rcx
0x180026641  mov     r14d, r8d
0x180026644  mov     dword ptr [rbp+57h+var_B0+8], ecx
0x180026647  mov     esi, r8d
0x18002664a  mov     dword ptr [rbp+57h+var_A0], r8d
0x18002664e  mov     r12d, ecx
0x180026651  mov     [rbp+57h+arg_10], ecx
0x180026654  cmp     [rax+74h], ecx
0x180026657  jnz     short loc_180026660
0x180026659  xor     eax, eax
0x18002665b  jmp     loc_180026961
0x180026660  mov     ecx, [rax+74h]
0x180026663  mov     eax, 8
0x180026668  mul     rcx
0x18002666b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026672  cmovo   rax, r8
0x180026676  mov     rcx, rax; unsigned __int64
0x180026679  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002667e  mov     r13, rax
0x180026681  test    rax, rax
0x180026684  jnz     short loc_18002668F
0x180026686  lea     r15d, [rax+8]
0x18002668a  jmp     loc_180026951
0x18002668f  mov     rax, [rbp+57h+arg_0]
0x180026693  add     rax, 60h ; '`'
0x180026697  mov     [rbp+57h+var_78], rax
0x18002669b  mov     rcx, [rax]
0x18002669e  test    rcx, rcx
0x1800266a1  jz      short loc_1800266BB
0x1800266a3  mov     eax, r12d
0x1800266a6  inc     r12d
0x1800266a9  mov     [r13+rax*8+0], rcx
0x1800266ae  mov     rcx, [rcx+18h]
0x1800266b2  test    rcx, rcx
0x1800266b5  jnz     short loc_1800266A3
0x1800266b7  mov     [rbp+57h+arg_10], r12d
0x1800266bb  and     [rsp+0E0h+var_C0], rbx
0x1800266c0  lea     r9, ?CompareByOffset@_DATA_BLOCK@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@SAHPEAXPEBX1@Z; CompareFunction
0x1800266c7  mov     edx, r12d; NumOfElements
0x1800266ca  mov     r8d, 8; SizeOfElements
0x1800266d0  mov     rcx, r13; Base
0x1800266d3  call    cs:__imp_qsort_s
0x1800266da  nop     dword ptr [rax+rax+00h]
0x1800266df  test    r12d, r12d
0x1800266e2  jle     loc_180026793
0x1800266e8  mov     r12, r13
0x1800266eb  cmp     r14d, 0FFFFFFFFh
0x1800266ef  jnz     short loc_18002670A
0x1800266f1  mov     rcx, [r12]
0x1800266f5  xor     r14d, r14d
0x1800266f8  mov     qword ptr [rbp+57h+var_B0+0Ch], r14
0x1800266fc  xor     esi, esi
0x1800266fe  mov     rax, [rcx]
0x180026701  mov     edi, [rcx+8]
0x180026704  mov     qword ptr [rbp+57h+var_B0], rax
0x180026708  jmp     short loc_18002677D
0x18002670a  mov     rdx, [r12]
0x18002670e  movsxd  rax, esi
0x180026711  mov     rcx, [r13+rax*8+0]
0x180026716  mov     eax, [rcx+8]
0x180026719  add     rax, [rcx]
0x18002671c  cmp     [rdx], rax
0x18002671f  jnz     short loc_180026726
0x180026721  add     edi, [rdx+8]
0x180026724  jmp     short loc_180026778
0x180026726  movups  xmm0, [rbp+57h+var_B0]
0x18002672a  lea     rdx, [rbp+57h+var_60]
0x18002672e  movsd   xmm1, [rbp+57h+var_A0]
0x180026733  lea     rcx, [rbp+57h+Base]
0x180026737  movaps  [rbp+57h+var_60], xmm0
0x18002673b  movsd   [rbp+57h+var_50], xmm1
0x180026740  call    ?AddItem@?$CDynArray@UDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@VCDeallocateNone@@@@QEAAKUDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@@Z; CDynArray<CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT,CDeallocateNone>::AddItem(CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT)
0x180026745  mov     r9d, 31Fh
0x18002674b  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180026752  mov     ecx, eax
0x180026754  mov     r15d, eax
0x180026757  call    ElValidateWin32_14
0x18002675c  test    eax, eax
0x18002675e  jnz     loc_180026945
0x180026764  mov     rdx, [r12]
0x180026768  mov     r14d, ebx
0x18002676b  mov     dword ptr [rbp+57h+var_B0+0Ch], ebx
0x18002676e  mov     rcx, [rdx]
0x180026771  mov     edi, [rdx+8]
0x180026774  mov     qword ptr [rbp+57h+var_B0], rcx
0x180026778  mov     dword ptr [rbp+57h+var_A0], ebx
0x18002677b  mov     esi, ebx
0x18002677d  inc     ebx
0x18002677f  mov     dword ptr [rbp+57h+var_B0+8], edi
0x180026782  add     r12, 8
0x180026786  cmp     ebx, [rbp+57h+arg_10]
0x180026789  jl      loc_1800266EB
0x18002678f  mov     r12d, [rbp+57h+arg_10]
0x180026793  movups  xmm0, [rbp+57h+var_B0]
0x180026797  lea     rdx, [rbp+57h+var_60]
0x18002679b  movsd   xmm1, [rbp+57h+var_A0]
0x1800267a0  lea     rcx, [rbp+57h+Base]
0x1800267a4  movaps  [rbp+57h+var_60], xmm0
0x1800267a8  movsd   [rbp+57h+var_50], xmm1
0x1800267ad  call    ?AddItem@?$CDynArray@UDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@VCDeallocateNone@@@@QEAAKUDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@@Z; CDynArray<CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT,CDeallocateNone>::AddItem(CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT)
0x1800267b2  mov     r9d, 330h
0x1800267b8  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800267bf  mov     ecx, r15d
0x1800267c2  call    ElValidateWin32_14
0x1800267c7  test    eax, eax
0x1800267c9  jnz     loc_180026945
0x1800267cf  mov     edi, dword ptr [rbp+57h+NumOfElements+4]
0x1800267d2  lea     r9, ?CompareBySizeDesc@DATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@SAHPEAXPEBX1@Z; CompareFunction
0x1800267d9  mov     rbx, [rbp+57h+Base]
0x1800267dd  lea     r8d, [rax+18h]; SizeOfElements
0x1800267e1  and     [rsp+0E0h+var_C0], 0
0x1800267e7  mov     edx, edi; NumOfElements
0x1800267e9  mov     rcx, rbx; Base
0x1800267ec  call    cs:__imp_qsort_s
0x1800267f3  nop     dword ptr [rax+rax+00h]
0x1800267f8  xor     eax, eax
0x1800267fa  mov     [rbp+57h+var_98], eax
0x1800267fd  test    edi, edi
0x1800267ff  jz      loc_180026949
0x180026805  mov     r14, [rbp+57h+arg_0]
0x180026809  mov     ecx, [rbp+57h+arg_8]
0x18002680c  test    ecx, ecx
0x18002680e  jz      short loc_18002681A
0x180026810  cmp     [r14+58h], ecx
0x180026814  jbe     loc_180026949
0x18002681a  and     qword ptr [rbp+57h+var_B0], 0
0x18002681f  or      esi, 0FFFFFFFFh
0x180026822  xor     ecx, ecx
0x180026824  mov     dword ptr [rbp+57h+var_B0+0Ch], esi
0x180026827  or      edi, esi
0x180026829  mov     [rbp+57h+arg_18], ecx
0x18002682c  xor     r15d, r15d
0x18002682f  mov     dword ptr [rbp+57h+var_B0+8], ecx
0x180026832  mov     dword ptr [rbp+57h+var_A0], edi
0x180026835  cmp     eax, dword ptr [rbp+57h+NumOfElements+4]
0x180026838  jb      short loc_180026842
0x18002683a  mov     r15d, 585h
0x180026840  jmp     short loc_180026874
0x180026842  lea     rcx, [rax+rax*2]
0x180026846  movups  xmm2, xmmword ptr [rbx+rcx*8]
0x18002684a  movsd   xmm0, qword ptr [rbx+rcx*8+10h]
0x180026850  movdqa  xmm1, xmm2
0x180026854  movsd   [rbp+57h+var_A0], xmm0
0x180026859  mov     edi, dword ptr [rbp+57h+var_A0]
0x18002685c  movups  [rbp+57h+var_B0], xmm2
0x180026860  movq    xmm2, qword ptr [rbx+rcx*8+8]
0x180026866  psrldq  xmm1, 0Ch
0x18002686b  movd    esi, xmm1
0x18002686f  movd    [rbp+57h+arg_18], xmm2
0x180026874  mov     r9d, 34Bh
0x18002687a  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180026881  mov     ecx, r15d
0x180026884  call    ElValidateWin32_14
0x180026889  test    eax, eax
0x18002688b  jnz     loc_180026949
0x180026891  mov     rcx, [rbp+57h+arg_0]
0x180026895  lea     rdx, [rbp+57h+var_B0]
0x180026899  mov     r9d, r12d
0x18002689c  mov     r8, r13
0x18002689f  call    ?IssueWrite@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKPEAUDATA_SEGMENT@1@PEAPEAU_DATA_BLOCK@1@K@Z; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::IssueWrite(CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT *,CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::_DATA_BLOCK * *,ulong)
0x1800268a4  mov     r9d, 350h
0x1800268aa  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800268b1  mov     ecx, eax
0x1800268b3  mov     r15d, eax
0x1800268b6  call    ElValidateWin32_14
0x1800268bb  test    eax, eax
0x1800268bd  jnz     loc_180026949
0x1800268c3  cmp     esi, edi
0x1800268c5  jg      short loc_180026924
0x1800268c7  mov     rbx, [rbp+57h+var_78]
0x1800268cb  movsxd  rax, esi
0x1800268ce  lea     r12, ds:0[rax*8]
0x1800268d6  add     r12, r13
0x1800268d9  sub     edi, esi
0x1800268db  lea     esi, [rdi+1]
0x1800268de  mov     rdi, [r12]
0x1800268e2  lea     rdx, [rbp+57h+var_70]
0x1800268e6  mov     rcx, rbx
0x1800268e9  mov     [rbp+57h+var_70], rdi
0x1800268ed  call    ?DeleteAt@?$CList@U_DATA_BLOCK@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@VCNoLock@@@@QEAAPEAU_DATA_BLOCK@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAPEAX@Z; CList<CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::_DATA_BLOCK,CNoLock>::DeleteAt(void * &)
0x1800268f2  test    rdi, rdi
0x1800268f5  jz      short loc_180026912
0x1800268f7  mov     rcx, [rdi+10h]; lpMem
0x1800268fb  test    rcx, rcx
0x1800268fe  jz      short loc_18002690A
0x180026900  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026905  and     qword ptr [rdi+10h], 0
0x18002690a  mov     rcx, rdi; lpMem
0x18002690d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026912  add     r12, 8
0x180026916  sub     rsi, 1
0x18002691a  jnz     short loc_1800268DE
0x18002691c  mov     rbx, [rbp+57h+Base]
0x180026920  mov     r12d, [rbp+57h+arg_10]
0x180026924  mov     eax, [r14+58h]
0x180026928  sub     eax, [rbp+57h+arg_18]
0x18002692b  mov     rcx, [rbp+57h+arg_0]
0x18002692f  mov     [rcx+58h], eax
0x180026932  mov     eax, [rbp+57h+var_98]
0x180026935  inc     eax
0x180026937  mov     [rbp+57h+var_98], eax
0x18002693a  cmp     eax, dword ptr [rbp+57h+NumOfElements+4]
0x18002693d  jb      loc_180026809
0x180026943  jmp     short loc_180026949
0x180026945  mov     rbx, [rbp+57h+Base]
0x180026949  mov     rcx, r13; lpMem
0x18002694c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026951  test    rbx, rbx
0x180026954  jz      short loc_18002695E
0x180026956  mov     rcx, rbx; lpMem
0x180026959  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002695e  mov     eax, r15d
0x180026961  add     rsp, 0A8h
0x180026968  pop     r15
0x18002696a  pop     r14
0x18002696c  pop     r13
0x18002696e  pop     r12
0x180026970  pop     rdi
0x180026971  pop     rsi
0x180026972  pop     rbx
0x180026973  pop     rbp
0x180026974  retn
```
