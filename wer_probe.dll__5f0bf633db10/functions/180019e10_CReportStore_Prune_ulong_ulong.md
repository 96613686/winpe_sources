# CReportStore::Prune(ulong,ulong)

- ea: `0x180019e10`
- end: `0x18001a2c6`
- name: `?Prune@CReportStore@@IEAAJKK@Z`
- size: `1206`
- prototype: `__int64 __fastcall(CReportStore *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x180009650`
- `0x1800441d0`
- `0x1800768e8`

## callees

- `0x180004754`
- `0x180007f7c`
- `0x18000bc10`
- `0x18000bc2c`
- `0x18000d048`
- `0x18000dad0`
- `0x18000e9ec`
- `0x180019e10`
- `0x18001a2cc`
- `0x18001a60c`
- `0x180021634`
- `0x180025c98`
- `0x18002b4c4`
- `0x18002ca14`
- `0x18002d9fc`
- `0x18002ffc4`
- `0x1800300a0`
- `0x18003db78`
- `0x18004057c`
- `0x180045bdc`
- `0x18004a474`
- `0x18004a66c`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ef1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ef1`

## string_xrefs

- `0x180019e9d`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a052`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a0e5`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a17d`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a1c7`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a202`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a236`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a24a`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a26b`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a27f`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a06b`: `Deleting report. Path: %ws`
- `0x18001a16b`: `Report is a UIF.  Not pruning. ReportId=%ws IntegratorReportId=%ws ReportPath=%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CReportStore::Prune(CReportStore *this, unsigned int a2, unsigned int a3)
{
  __int64 v3; // rdi
  unsigned int v4; // r13d
  unsigned int v6; // r15d
  const wchar_t *v7; // rdx
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  wil::details::in1diag3 *v12; // rcx
  int ReportCount; // eax
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // r12
  unsigned int v17; // esi
  CReport *v18; // r14
  int ReportKey; // eax
  int v20; // edi
  CReportKey *v21; // rsi
  int IsInvalid; // eax
  int v23; // r13d
  int ReportPath; // eax
  int SizeOnDisk; // eax
  CReport *v26; // rbx
  int v27; // eax
  __int64 v28; // r8
  int v29; // eax
  int v31; // [rsp+28h] [rbp-E0h]
  char *v32; // [rsp+30h] [rbp-D8h]
  char *v33; // [rsp+30h] [rbp-D8h]
  unsigned int v34[2]; // [rsp+48h] [rbp-C0h] BYREF
  CReport *v35; // [rsp+50h] [rbp-B8h] BYREF
  int v36[2]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *v37; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 v39; // [rsp+80h] [rbp-88h] BYREF
  struct CReportKey *v40; // [rsp+88h] [rbp-80h] BYREF
  char *v41[5]; // [rsp+90h] [rbp-78h] BYREF
  int v42; // [rsp+B8h] [rbp-50h] BYREF
  char v43[32]; // [rsp+C0h] [rbp-48h] BYREF
  char v44[24]; // [rsp+E0h] [rbp-28h] BYREF
  char v45[80]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]
  unsigned int v49; // [rsp+170h] [rbp+68h]

  v3 = a3;
  v4 = a2;
  v6 = 0;
  v42 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v43);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v44);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v45);
  v40 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v37);
  v35 = 0;
  v34[0] = 0;
  v39 = 0;
  LODWORD(v32) = v4;
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0x283,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
    (const char *)0x80000000LL,
    (int)"CReportStore::Prune: MaxReportCount=%d MaxSizeInMb=%d",
    v32);
  v7 = (const wchar_t *)*((_QWORD *)this + 2);
  if ( v7 == *((const wchar_t **)this + 3) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x288,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)0x8000FFFFLL,
      v31);
    if ( v37 != (wchar_t *)&v38 )
      HeapFree(g_hWerheap, 0, v37);
    goto LABEL_57;
  }
  v9 = CReportKeyEnumerator::Initialize((CReportKeyEnumerator *)&v42, v7, 0);
  v8 = v9;
  if ( v9 == -2147024893 )
  {
    v8 = -2147020590;
LABEL_7:
    v10 = v8;
    v11 = 662;
    goto LABEL_8;
  }
  if ( v9 < 0 )
    goto LABEL_7;
  ReportCount = CReportKeyEnumerator::GetReportCount((CReportKeyEnumerator *)&v42, v34);
  v8 = ReportCount;
  if ( ReportCount < 0 )
  {
    v10 = (unsigned int)ReportCount;
    v11 = 669;
    goto LABEL_8;
  }
  if ( !v34[0] )
  {
LABEL_56:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v37);
    v8 = 0;
    goto LABEL_57;
  }
  v14 = CReportKeyEnumerator::CalculateTotalSizeOnDisk((CReportKeyEnumerator *)&v42, (unsigned __int64 *)&v35);
  v8 = v14;
  if ( v14 < 0 )
  {
    v10 = (unsigned int)v14;
    v11 = 673;
    goto LABEL_8;
  }
  v15 = CReportKeyEnumerator::Sort((__int64)&v42);
  v8 = v15;
  if ( v15 >= 0 )
  {
    v16 = v3 << 20;
    if ( *((_DWORD *)this + 2) == 2 || (v36[1] = 1, !*((_DWORD *)this + 2)) )
      v36[1] = 2;
    v17 = v34[0];
    v49 = v34[0];
    v18 = v35;
    while ( 1 )
    {
      if ( v6 >= v34[0] )
        goto LABEL_56;
      v36[0] = 0;
      ReportKey = CReportKeyEnumerator::GetReportKey((CReportKeyEnumerator *)&v42, v6, &v40);
      v8 = ReportKey;
      if ( ReportKey < 0 )
      {
        v10 = (unsigned int)ReportKey;
        v11 = 705;
        goto LABEL_8;
      }
      if ( v16 && (unsigned __int64)v18 > v16 || (v20 = 0, v17 > v4) )
        v20 = 1;
      v21 = v40;
      IsInvalid = CReportKey::IsInvalid(v40, v36);
      v8 = IsInvalid;
      if ( IsInvalid < 0 )
      {
        v10 = (unsigned int)IsInvalid;
        v11 = 721;
        goto LABEL_8;
      }
      v23 = v36[0];
      if ( !v20 && !v36[0] )
        goto LABEL_43;
      ReportPath = CReportKey::GetReportPath((__int64)v21, (__int64)&v37);
      v8 = ReportPath;
      v12 = retaddr;
      if ( ReportPath < 0 )
      {
        v10 = (unsigned int)ReportPath;
        v11 = 731;
        goto LABEL_9;
      }
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x2DD,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
        (const char *)0x80000000LL,
        (int)"Deleting report. Path: %ws",
        (const char *)v37);
      SizeOnDisk = CReportKey::GetSizeOnDisk(v21, &v39);
      v8 = SizeOnDisk;
      if ( SizeOnDisk < 0 )
      {
        v10 = (unsigned int)SizeOnDisk;
        v11 = 737;
        goto LABEL_8;
      }
      if ( a2 && *((_DWORD *)this + 2) == 3 )
      {
        utl::make_unique<CReport,,0>(&v35);
        v26 = v35;
        if ( !v35 )
        {
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x2F3,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)0x80000000LL,
            (int)"Failed to allocate memory for report.",
            v33);
          goto LABEL_42;
        }
        v27 = CReport::ReadFromDirectory((__int64)v35, v37, v36[1]);
        if ( v27 >= 0 )
        {
          if ( (unsigned int)CReport::IsUIFReport(v26) )
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v41);
            CReport::GetUniqueIdentifier(v26, v41);
            UtilPathTail(v37);
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x302,
              (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
              (const char *)0x80000000LL,
              (int)"Report is a UIF.  Not pruning. ReportId=%ws IntegratorReportId=%ws ReportPath=%ws",
              v41[0]);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v41);
LABEL_42:
            utl::unique_ptr<CReport,utl::default_delete<CReport>>::~unique_ptr<CReport,utl::default_delete<CReport>>(&v35);
LABEL_43:
            v17 = v49;
            goto LABEL_44;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2F7,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
            (const char *)(unsigned int)v27,
            v31);
        }
        utl::unique_ptr<CReport,utl::default_delete<CReport>>::~unique_ptr<CReport,utl::default_delete<CReport>>(&v35);
      }
      if ( v23 )
        v28 = 6;
      else
        v28 = (unsigned int)(a2 != 0) + 1;
      v29 = CReportStore::DeleteReportFromStore(this, v37, v28, 0);
      if ( v29 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x316,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v29,
          v31);
        goto LABEL_43;
      }
      if ( v39 > (unsigned __int64)v18 )
      {
        v8 = -2147418113;
        v10 = 2147549183LL;
        v11 = 801;
        goto LABEL_8;
      }
      v18 = (CReport *)((char *)v18 - v39);
      v17 = --v49;
LABEL_44:
      ++v6;
      v4 = a2;
    }
  }
  v10 = (unsigned int)v15;
  v11 = 678;
LABEL_8:
  v12 = retaddr;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    v12,
    (void *)v11,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
    (const char *)v10,
    v31);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v37);
LABEL_57:
  CReportKeyEnumerator::~CReportKeyEnumerator((CReportKeyEnumerator *)&v42);
  return v8;
}

```

## disassembly

```asm
0x180019e10  mov     rax, rsp
0x180019e13  mov     [rax+18h], rbx
0x180019e17  mov     [rax+10h], edx
0x180019e1a  mov     [rax+8], rcx
0x180019e1e  push    rbp
0x180019e1f  push    rsi
0x180019e20  push    rdi
0x180019e21  push    r12
0x180019e23  push    r13
0x180019e25  push    r14
0x180019e27  push    r15
0x180019e29  lea     rbp, [rax-48h]
0x180019e2d  sub     rsp, 110h
0x180019e34  mov     edi, r8d
0x180019e37  mov     r13d, edx
0x180019e3a  mov     rsi, rcx
0x180019e3d  xor     r15d, r15d
0x180019e40  mov     [rbp+40h+var_90], r15d
0x180019e44  lea     rcx, [rbp+40h+var_88]; void *
0x180019e48  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180019e4d  lea     rcx, [rbp+40h+var_68]
0x180019e51  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x180019e56  lea     rcx, [rbp+40h+var_50]; void *
0x180019e5a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180019e5f  nop
0x180019e60  mov     [rbp+40h+var_C0], r15
0x180019e64  lea     rcx, [rsp+140h+var_E8]; void *
0x180019e69  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180019e6e  nop
0x180019e6f  mov     [rsp+140h+var_F8], r15
0x180019e74  mov     [rsp+140h+var_100], r15d
0x180019e79  mov     [rsp+140h+var_C8], r15
0x180019e7e  mov     rcx, [rbp+48h]; this
0x180019e82  mov     dword ptr [rsp+140h+var_110], edi
0x180019e86  mov     dword ptr [rsp+140h+var_118], r13d; char *
0x180019e8b  lea     rax, aCreportstorePr; "CReportStore::Prune: MaxReportCount=%d "...
0x180019e92  mov     qword ptr [rsp+140h+var_120], rax; int
0x180019e97  mov     r9d, 80000000h; char *
0x180019e9d  lea     r14, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180019ea4  mov     r8, r14; unsigned int
0x180019ea7  mov     edx, 283h; void *
0x180019eac  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180019eb1  mov     rdx, [rsi+10h]; wchar_t *
0x180019eb5  cmp     rdx, [rsi+18h]
0x180019eb9  jnz     short loc_180019EFC
0x180019ebb  mov     rcx, [rbp+48h]; this
0x180019ebf  mov     ebx, 8000FFFFh
0x180019ec4  mov     r9d, ebx; char *
0x180019ec7  mov     r8, r14; unsigned int
0x180019eca  mov     edx, 288h; void *
0x180019ecf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ed4  nop
0x180019ed5  lea     rax, [rsp+68h]
0x180019eda  mov     r8, [rsp+140h+var_E8]; lpMem
0x180019edf  cmp     r8, rax
0x180019ee2  jz      loc_18001A2A0
0x180019ee8  xor     edx, edx; dwFlags
0x180019eea  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180019ef1  call    cs:__imp_HeapFree
0x180019ef7  jmp     loc_18001A2A0
0x180019efc  xor     r8d, r8d; wchar_t *
0x180019eff  lea     rcx, [rbp+40h+var_90]; this
0x180019f03  call    ?Initialize@CReportKeyEnumerator@@QEAAJPEB_W0@Z; CReportKeyEnumerator::Initialize(wchar_t const *,wchar_t const *)
0x180019f08  mov     ebx, eax
0x180019f0a  cmp     eax, 80070003h
0x180019f0f  jnz     short loc_180019F18
0x180019f11  mov     ebx, 800710D2h
0x180019f16  jmp     short loc_180019F1C
0x180019f18  test    eax, eax
0x180019f1a  jns     short loc_180019F40
0x180019f1c  mov     r9d, ebx; char *
0x180019f1f  mov     edx, 296h; void *
0x180019f24  mov     r8, r14; unsigned int
0x180019f27  mov     rcx, [rbp+48h]; this
0x180019f2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f30  nop
0x180019f31  lea     rcx, [rsp+140h+var_E8]; void *
0x180019f36  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180019f3b  jmp     loc_18001A2A0
0x180019f40  lea     rdx, [rsp+140h+var_100]; unsigned int *
0x180019f45  lea     rcx, [rbp+40h+var_90]; this
0x180019f49  call    ?GetReportCount@CReportKeyEnumerator@@QEAAJPEAK@Z; CReportKeyEnumerator::GetReportCount(ulong *)
0x180019f4e  mov     ebx, eax
0x180019f50  test    eax, eax
0x180019f52  jns     short loc_180019F5E
0x180019f54  mov     r9d, eax
0x180019f57  mov     edx, 29Dh
0x180019f5c  jmp     short loc_180019F24
0x180019f5e  cmp     [rsp+140h+var_100], r15d
0x180019f63  jz      loc_18001A293
0x180019f69  lea     rdx, [rsp+140h+var_F8]; unsigned __int64 *
0x180019f6e  lea     rcx, [rbp+40h+var_90]; this
0x180019f72  call    ?CalculateTotalSizeOnDisk@CReportKeyEnumerator@@QEAAJPEA_K@Z; CReportKeyEnumerator::CalculateTotalSizeOnDisk(unsigned __int64 *)
0x180019f77  mov     ebx, eax
0x180019f79  test    eax, eax
0x180019f7b  jns     short loc_180019F87
0x180019f7d  mov     r9d, eax
0x180019f80  mov     edx, 2A1h
0x180019f85  jmp     short loc_180019F24
0x180019f87  lea     rcx, [rbp+40h+var_90]
0x180019f8b  call    ?Sort@CReportKeyEnumerator@@QEAAJW4_REPORT_KEY_SORT@@@Z; CReportKeyEnumerator::Sort(_REPORT_KEY_SORT)
0x180019f90  mov     ebx, eax
0x180019f92  test    eax, eax
0x180019f94  jns     short loc_180019FA0
0x180019f96  mov     r9d, eax
0x180019f99  mov     edx, 2A6h
0x180019f9e  jmp     short loc_180019F24
0x180019fa0  mov     r12, rdi
0x180019fa3  shl     r12, 14h
0x180019fa7  cmp     dword ptr [rsi+8], 2
0x180019fab  jz      short loc_180019FBB
0x180019fad  mov     [rsp+140h+var_F0+4], 1
0x180019fb5  cmp     [rsi+8], r15d
0x180019fb9  jnz     short loc_180019FC3
0x180019fbb  mov     [rsp+140h+var_F0+4], 2
0x180019fc3  mov     esi, [rsp+140h+var_100]
0x180019fc7  mov     [rbp+40h+arg_18], esi
0x180019fca  mov     r14, [rsp+140h+var_F8]
0x180019fcf  cmp     r15d, [rsp+140h+var_100]
0x180019fd4  jnb     loc_18001A290
0x180019fda  mov     [rsp+140h+var_F0], 0
0x180019fe2  lea     r8, [rbp+40h+var_C0]; struct CReportKey **
0x180019fe6  mov     edx, r15d; unsigned int
0x180019fe9  lea     rcx, [rbp+40h+var_90]; this
0x180019fed  call    ?GetReportKey@CReportKeyEnumerator@@QEAAJKPEAPEAVCReportKey@@@Z; CReportKeyEnumerator::GetReportKey(ulong,CReportKey * *)
0x180019ff2  mov     ebx, eax
0x180019ff4  test    eax, eax
0x180019ff6  js      loc_18001A27C
0x180019ffc  test    r12, r12
0x180019fff  jz      short loc_18001A006
0x18001a001  cmp     r14, r12
0x18001a004  ja      short loc_18001A00D
0x18001a006  xor     edi, edi
0x18001a008  cmp     esi, r13d
0x18001a00b  jbe     short loc_18001A012
0x18001a00d  mov     edi, 1
0x18001a012  lea     rdx, [rsp+140h+var_F0]; int *
0x18001a017  mov     rsi, [rbp+40h+var_C0]
0x18001a01b  mov     rcx, rsi; this
0x18001a01e  call    ?IsInvalid@CReportKey@@QEAAJAEAH@Z; CReportKey::IsInvalid(int &)
0x18001a023  mov     ebx, eax
0x18001a025  test    eax, eax
0x18001a027  js      loc_18001A268
0x18001a02d  mov     r13d, [rsp+140h+var_F0]
0x18001a032  test    edi, edi
0x18001a034  jnz     short loc_18001A03F
0x18001a036  test    r13d, r13d
0x18001a039  jz      loc_18001A1A2
0x18001a03f  lea     rdx, [rsp+140h+var_E8]
0x18001a044  mov     rcx, rsi
0x18001a047  call    ?GetReportPath@CReportKey@@QEBAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportKey::GetReportPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001a04c  mov     ebx, eax
0x18001a04e  mov     rcx, [rbp+48h]; this
0x18001a052  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001a059  test    eax, eax
0x18001a05b  js      loc_18001A25B
0x18001a061  mov     rax, [rsp+140h+var_E8]
0x18001a066  mov     [rsp+140h+var_118], rax; char *
0x18001a06b  lea     rax, aDeletingReport; "Deleting report. Path: %ws"
0x18001a072  mov     qword ptr [rsp+140h+var_120], rax; int
0x18001a077  mov     r9d, 80000000h; char *
0x18001a07d  mov     edx, 2DDh; void *
0x18001a082  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a087  lea     rdx, [rsp+140h+var_C8]; unsigned __int64 *
0x18001a08c  mov     rcx, rsi; this
0x18001a08f  call    ?GetSizeOnDisk@CReportKey@@QEBAJPEA_K@Z; CReportKey::GetSizeOnDisk(unsigned __int64 *)
0x18001a094  mov     ebx, eax
0x18001a096  test    eax, eax
0x18001a098  js      loc_18001A247
0x18001a09e  mov     edi, [rbp+40h+arg_8]
0x18001a0a1  mov     rsi, [rbp+40h+arg_0]
0x18001a0a5  test    edi, edi
0x18001a0a7  jz      short loc_18001A101
0x18001a0a9  cmp     dword ptr [rsi+8], 3
0x18001a0ad  jnz     short loc_18001A101
0x18001a0af  lea     rcx, [rsp+140h+var_F8]
0x18001a0b4  call    ??$make_unique@VCReport@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCReport@@U?$default_delete@VCReport@@@utl@@@0@XZ; utl::make_unique<CReport,,0>(void)
0x18001a0b9  nop
0x18001a0ba  mov     rbx, [rsp+140h+var_F8]
0x18001a0bf  test    rbx, rbx
0x18001a0c2  jz      loc_18001A1B1
0x18001a0c8  mov     r8d, [rsp+140h+var_F0+4]
0x18001a0cd  mov     rdx, [rsp+140h+var_E8]
0x18001a0d2  mov     rcx, rbx
0x18001a0d5  call    ?ReadFromDirectory@CReport@@QEAAJPEB_WW4REPORT_SOURCE_TYPE@@@Z; CReport::ReadFromDirectory(wchar_t const *,REPORT_SOURCE_TYPE)
0x18001a0da  mov     rcx, [rbp+48h]; this
0x18001a0de  test    eax, eax
0x18001a0e0  jns     short loc_18001A115
0x18001a0e2  mov     r9d, eax; char *
0x18001a0e5  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001a0ec  mov     edx, 2F7h; void *
0x18001a0f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a0f6  nop
0x18001a0f7  lea     rcx, [rsp+140h+var_F8]
0x18001a0fc  call    ??1?$unique_ptr@VCReport@@U?$default_delete@VCReport@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReport,utl::default_delete<CReport>>::~unique_ptr<CReport,utl::default_delete<CReport>>(void)
0x18001a101  test    r13d, r13d
0x18001a104  jz      loc_18001A1DA
0x18001a10a  mov     r8d, 6
0x18001a110  jmp     loc_18001A1E7
0x18001a115  mov     rcx, rbx; this
0x18001a118  call    ?IsUIFReport@CReport@@QEBAHXZ; CReport::IsUIFReport(void)
0x18001a11d  test    eax, eax
0x18001a11f  jz      short loc_18001A0F7
0x18001a121  lea     rcx, [rbp+40h+var_B8]; void *
0x18001a125  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001a12a  lea     rdx, [rbp+40h+var_B8]
0x18001a12e  mov     rcx, rbx
0x18001a131  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001a136  mov     r8, [rbx+1718h]
0x18001a13d  xor     eax, eax
0x18001a13f  cmp     r8, [rbx+1720h]
0x18001a146  cmovz   r8, rax
0x18001a14a  mov     rcx, [rsp+140h+var_E8]; wchar_t *
0x18001a14f  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18001a154  mov     rcx, [rbp+48h]; this
0x18001a158  mov     qword ptr [rsp+140h+var_108], rax
0x18001a15d  mov     [rsp+140h+var_110], r8
0x18001a162  mov     rax, [rbp+40h+var_B8]
0x18001a166  mov     [rsp+140h+var_118], rax; char *
0x18001a16b  lea     rax, aReportIsAUifNo; "Report is a UIF.  Not pruning. ReportId"...
0x18001a172  mov     qword ptr [rsp+140h+var_120], rax; int
0x18001a177  mov     r9d, 80000000h; char *
0x18001a17d  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001a184  mov     edx, 302h; void *
0x18001a189  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a18e  lea     rcx, [rbp+40h+var_B8]; void *
0x18001a192  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001a197  nop
0x18001a198  lea     rcx, [rsp+140h+var_F8]
0x18001a19d  call    ??1?$unique_ptr@VCReport@@U?$default_delete@VCReport@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReport,utl::default_delete<CReport>>::~unique_ptr<CReport,utl::default_delete<CReport>>(void)
0x18001a1a2  mov     esi, [rbp+40h+arg_18]
0x18001a1a5  inc     r15d
0x18001a1a8  mov     r13d, [rbp+40h+arg_8]
0x18001a1ac  jmp     loc_180019FCF
0x18001a1b1  mov     rcx, [rbp+48h]; this
0x18001a1b5  lea     rax, aFailedToAlloca; "Failed to allocate memory for report."
0x18001a1bc  mov     qword ptr [rsp+140h+var_120], rax; int
0x18001a1c1  mov     r9d, 80000000h; char *
0x18001a1c7  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001a1ce  mov     edx, 2F3h; void *
0x18001a1d3  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a1d8  jmp     short loc_18001A198
0x18001a1da  mov     eax, edi
0x18001a1dc  neg     eax
0x18001a1de  sbb     r8d, r8d
0x18001a1e1  neg     r8d
0x18001a1e4  inc     r8d
0x18001a1e7  xor     r9d, r9d
0x18001a1ea  mov     rdx, [rsp+140h+var_E8]
0x18001a1ef  mov     rcx, rsi
0x18001a1f2  call    ?DeleteReportFromStore@CReportStore@@QEAAJPEB_WW4REPORT_DELETE_REASON@@PEAVCReport@@@Z; CReportStore::DeleteReportFromStore(wchar_t const *,REPORT_DELETE_REASON,CReport *)
0x18001a1f7  mov     rcx, [rbp+48h]; this
0x18001a1fb  test    eax, eax
0x18001a1fd  jns     short loc_18001A215
0x18001a1ff  mov     r9d, eax; char *
0x18001a202  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001a209  mov     edx, 316h; void *
0x18001a20e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a213  jmp     short loc_18001A1A2
0x18001a215  cmp     [rsp+140h+var_C8], r14
0x18001a21a  ja      short loc_18001A22E
0x18001a21c  sub     r14, [rsp+140h+var_C8]
0x18001a221  mov     esi, [rbp+40h+arg_18]
0x18001a224  dec     esi
0x18001a226  mov     [rbp+40h+arg_18], esi
0x18001a229  jmp     loc_18001A1A5
0x18001a22e  mov     ebx, 8000FFFFh
0x18001a233  mov     r9d, ebx
0x18001a236  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001a23d  mov     edx, 321h
0x18001a242  jmp     loc_180019F27
0x18001a247  mov     r9d, eax
0x18001a24a  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001a251  mov     edx, 2E1h
0x18001a256  jmp     loc_180019F27
0x18001a25b  mov     r9d, eax
0x18001a25e  mov     edx, 2DBh
0x18001a263  jmp     loc_180019F2B
0x18001a268  mov     r9d, eax
0x18001a26b  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001a272  mov     edx, 2D1h
0x18001a277  jmp     loc_180019F27
0x18001a27c  mov     r9d, eax
0x18001a27f  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18001a286  mov     edx, 2C1h
0x18001a28b  jmp     loc_180019F27
0x18001a290  xor     r15d, r15d
0x18001a293  lea     rcx, [rsp+140h+var_E8]; void *
0x18001a298  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001a29d  mov     ebx, r15d
0x18001a2a0  lea     rcx, [rbp+40h+var_90]; this
0x18001a2a4  call    ??1CReportKeyEnumerator@@QEAA@XZ; CReportKeyEnumerator::~CReportKeyEnumerator(void)
0x18001a2a9  mov     eax, ebx
0x18001a2ab  mov     rbx, [rsp+140h+arg_10]
0x18001a2b3  add     rsp, 110h
0x18001a2ba  pop     r15
0x18001a2bc  pop     r14
0x18001a2be  pop     r13
0x18001a2c0  pop     r12
0x18001a2c2  pop     rdi
  ... truncated ...
```
