# CReportStore::Prune(ulong,ulong)

- ea: `0x1800053e0`
- end: `0x18000589d`
- name: `?Prune@CReportStore@@IEAAJKK@Z`
- size: `1213`
- prototype: `__int64 __fastcall(CReportStore *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x18000a8e0`
- `0x1800460f0`
- `0x180079dd8`

## callees

- `0x180004808`
- `0x1800053e0`
- `0x1800058a4`
- `0x180005be8`
- `0x180005c04`
- `0x180005cd4`
- `0x180008164`
- `0x18000cf50`
- `0x18000db80`
- `0x18000e798`
- `0x18002219c`
- `0x180025ce4`
- `0x18002ce6c`
- `0x18002e204`
- `0x18002f4b4`
- `0x1800318c8`
- `0x1800319d8`
- `0x18003fb94`
- `0x1800424e8`
- `0x1800479ac`
- `0x18004c7b8`
- `0x18004c9ec`
- `0x180075690`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054c1`

## string_xrefs

- `0x18000546d`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180005628`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x1800056bb`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180005753`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18000579d`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x1800057d8`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18000580c`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180005820`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180005841`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180005855`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180005641`: `Deleting report. Path: %ws`
- `0x180005741`: `Report is a UIF.  Not pruning. ReportId=%ws IntegratorReportId=%ws ReportPath=%ws`

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
  v15 = CReportKeyEnumerator::Sort(&v42);
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
      ReportPath = CReportKey::GetReportPath(v21, &v37);
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
        v27 = CReport::ReadFromDirectory(v35, v37, (unsigned int)v36[1]);
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
0x1800053e0  mov     rax, rsp
0x1800053e3  mov     [rax+18h], rbx
0x1800053e7  mov     [rax+10h], edx
0x1800053ea  mov     [rax+8], rcx
0x1800053ee  push    rbp
0x1800053ef  push    rsi
0x1800053f0  push    rdi
0x1800053f1  push    r12
0x1800053f3  push    r13
0x1800053f5  push    r14
0x1800053f7  push    r15
0x1800053f9  lea     rbp, [rax-48h]
0x1800053fd  sub     rsp, 110h
0x180005404  mov     edi, r8d
0x180005407  mov     r13d, edx
0x18000540a  mov     rsi, rcx
0x18000540d  xor     r15d, r15d
0x180005410  mov     [rbp+40h+var_90], r15d
0x180005414  lea     rcx, [rbp+40h+var_88]; void *
0x180005418  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000541d  lea     rcx, [rbp+40h+var_68]
0x180005421  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x180005426  lea     rcx, [rbp+40h+var_50]; void *
0x18000542a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000542f  nop
0x180005430  mov     [rbp+40h+var_C0], r15
0x180005434  lea     rcx, [rsp+140h+var_E8]; void *
0x180005439  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000543e  nop
0x18000543f  mov     [rsp+140h+var_F8], r15
0x180005444  mov     [rsp+140h+var_100], r15d
0x180005449  mov     [rsp+140h+var_C8], r15
0x18000544e  mov     rcx, [rbp+48h]; this
0x180005452  mov     dword ptr [rsp+140h+var_110], edi
0x180005456  mov     dword ptr [rsp+140h+var_118], r13d; char *
0x18000545b  lea     rax, aCreportstorePr; "CReportStore::Prune: MaxReportCount=%d "...
0x180005462  mov     qword ptr [rsp+140h+var_120], rax; int
0x180005467  mov     r9d, 80000000h; char *
0x18000546d  lea     r14, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180005474  mov     r8, r14; unsigned int
0x180005477  mov     edx, 283h; void *
0x18000547c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180005481  mov     rdx, [rsi+10h]; wchar_t *
0x180005485  cmp     rdx, [rsi+18h]
0x180005489  jnz     short loc_1800054D2
0x18000548b  mov     rcx, [rbp+48h]; this
0x18000548f  mov     ebx, 8000FFFFh
0x180005494  mov     r9d, ebx; char *
0x180005497  mov     r8, r14; unsigned int
0x18000549a  mov     edx, 288h; void *
0x18000549f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800054a4  nop
0x1800054a5  lea     rax, [rsp+68h]
0x1800054aa  mov     r8, [rsp+140h+var_E8]; lpMem
0x1800054af  cmp     r8, rax
0x1800054b2  jz      loc_180005876
0x1800054b8  xor     edx, edx; dwFlags
0x1800054ba  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800054c1  call    cs:__imp_HeapFree
0x1800054c8  nop     dword ptr [rax+rax+00h]
0x1800054cd  jmp     loc_180005876
0x1800054d2  xor     r8d, r8d; wchar_t *
0x1800054d5  lea     rcx, [rbp+40h+var_90]; this
0x1800054d9  call    ?Initialize@CReportKeyEnumerator@@QEAAJPEB_W0@Z; CReportKeyEnumerator::Initialize(wchar_t const *,wchar_t const *)
0x1800054de  mov     ebx, eax
0x1800054e0  cmp     eax, 80070003h
0x1800054e5  jnz     short loc_1800054EE
0x1800054e7  mov     ebx, 800710D2h
0x1800054ec  jmp     short loc_1800054F2
0x1800054ee  test    eax, eax
0x1800054f0  jns     short loc_180005516
0x1800054f2  mov     r9d, ebx; char *
0x1800054f5  mov     edx, 296h; void *
0x1800054fa  mov     r8, r14; unsigned int
0x1800054fd  mov     rcx, [rbp+48h]; this
0x180005501  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005506  nop
0x180005507  lea     rcx, [rsp+140h+var_E8]; void *
0x18000550c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180005511  jmp     loc_180005876
0x180005516  lea     rdx, [rsp+140h+var_100]; unsigned int *
0x18000551b  lea     rcx, [rbp+40h+var_90]; this
0x18000551f  call    ?GetReportCount@CReportKeyEnumerator@@QEAAJPEAK@Z; CReportKeyEnumerator::GetReportCount(ulong *)
0x180005524  mov     ebx, eax
0x180005526  test    eax, eax
0x180005528  jns     short loc_180005534
0x18000552a  mov     r9d, eax
0x18000552d  mov     edx, 29Dh
0x180005532  jmp     short loc_1800054FA
0x180005534  cmp     [rsp+140h+var_100], r15d
0x180005539  jz      loc_180005869
0x18000553f  lea     rdx, [rsp+140h+var_F8]; unsigned __int64 *
0x180005544  lea     rcx, [rbp+40h+var_90]; this
0x180005548  call    ?CalculateTotalSizeOnDisk@CReportKeyEnumerator@@QEAAJPEA_K@Z; CReportKeyEnumerator::CalculateTotalSizeOnDisk(unsigned __int64 *)
0x18000554d  mov     ebx, eax
0x18000554f  test    eax, eax
0x180005551  jns     short loc_18000555D
0x180005553  mov     r9d, eax
0x180005556  mov     edx, 2A1h
0x18000555b  jmp     short loc_1800054FA
0x18000555d  lea     rcx, [rbp+40h+var_90]
0x180005561  call    ?Sort@CReportKeyEnumerator@@QEAAJW4_REPORT_KEY_SORT@@@Z; CReportKeyEnumerator::Sort(_REPORT_KEY_SORT)
0x180005566  mov     ebx, eax
0x180005568  test    eax, eax
0x18000556a  jns     short loc_180005576
0x18000556c  mov     r9d, eax
0x18000556f  mov     edx, 2A6h
0x180005574  jmp     short loc_1800054FA
0x180005576  mov     r12, rdi
0x180005579  shl     r12, 14h
0x18000557d  cmp     dword ptr [rsi+8], 2
0x180005581  jz      short loc_180005591
0x180005583  mov     [rsp+140h+var_F0+4], 1
0x18000558b  cmp     [rsi+8], r15d
0x18000558f  jnz     short loc_180005599
0x180005591  mov     [rsp+140h+var_F0+4], 2
0x180005599  mov     esi, [rsp+140h+var_100]
0x18000559d  mov     [rbp+40h+arg_18], esi
0x1800055a0  mov     r14, [rsp+140h+var_F8]
0x1800055a5  cmp     r15d, [rsp+140h+var_100]
0x1800055aa  jnb     loc_180005866
0x1800055b0  mov     [rsp+140h+var_F0], 0
0x1800055b8  lea     r8, [rbp+40h+var_C0]; struct CReportKey **
0x1800055bc  mov     edx, r15d; unsigned int
0x1800055bf  lea     rcx, [rbp+40h+var_90]; this
0x1800055c3  call    ?GetReportKey@CReportKeyEnumerator@@QEAAJKPEAPEAVCReportKey@@@Z; CReportKeyEnumerator::GetReportKey(ulong,CReportKey * *)
0x1800055c8  mov     ebx, eax
0x1800055ca  test    eax, eax
0x1800055cc  js      loc_180005852
0x1800055d2  test    r12, r12
0x1800055d5  jz      short loc_1800055DC
0x1800055d7  cmp     r14, r12
0x1800055da  ja      short loc_1800055E3
0x1800055dc  xor     edi, edi
0x1800055de  cmp     esi, r13d
0x1800055e1  jbe     short loc_1800055E8
0x1800055e3  mov     edi, 1
0x1800055e8  lea     rdx, [rsp+140h+var_F0]; int *
0x1800055ed  mov     rsi, [rbp+40h+var_C0]
0x1800055f1  mov     rcx, rsi; this
0x1800055f4  call    ?IsInvalid@CReportKey@@QEAAJAEAH@Z; CReportKey::IsInvalid(int &)
0x1800055f9  mov     ebx, eax
0x1800055fb  test    eax, eax
0x1800055fd  js      loc_18000583E
0x180005603  mov     r13d, [rsp+140h+var_F0]
0x180005608  test    edi, edi
0x18000560a  jnz     short loc_180005615
0x18000560c  test    r13d, r13d
0x18000560f  jz      loc_180005778
0x180005615  lea     rdx, [rsp+140h+var_E8]
0x18000561a  mov     rcx, rsi
0x18000561d  call    ?GetReportPath@CReportKey@@QEBAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportKey::GetReportPath(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180005622  mov     ebx, eax
0x180005624  mov     rcx, [rbp+48h]; this
0x180005628  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18000562f  test    eax, eax
0x180005631  js      loc_180005831
0x180005637  mov     rax, [rsp+140h+var_E8]
0x18000563c  mov     [rsp+140h+var_118], rax; char *
0x180005641  lea     rax, aDeletingReport; "Deleting report. Path: %ws"
0x180005648  mov     qword ptr [rsp+140h+var_120], rax; int
0x18000564d  mov     r9d, 80000000h; char *
0x180005653  mov     edx, 2DDh; void *
0x180005658  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000565d  lea     rdx, [rsp+140h+var_C8]; unsigned __int64 *
0x180005662  mov     rcx, rsi; this
0x180005665  call    ?GetSizeOnDisk@CReportKey@@QEBAJPEA_K@Z; CReportKey::GetSizeOnDisk(unsigned __int64 *)
0x18000566a  mov     ebx, eax
0x18000566c  test    eax, eax
0x18000566e  js      loc_18000581D
0x180005674  mov     edi, [rbp+40h+arg_8]
0x180005677  mov     rsi, [rbp+40h+arg_0]
0x18000567b  test    edi, edi
0x18000567d  jz      short loc_1800056D7
0x18000567f  cmp     dword ptr [rsi+8], 3
0x180005683  jnz     short loc_1800056D7
0x180005685  lea     rcx, [rsp+140h+var_F8]
0x18000568a  call    ??$make_unique@VCReport@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCReport@@U?$default_delete@VCReport@@@utl@@@0@XZ; utl::make_unique<CReport,,0>(void)
0x18000568f  nop
0x180005690  mov     rbx, [rsp+140h+var_F8]
0x180005695  test    rbx, rbx
0x180005698  jz      loc_180005787
0x18000569e  mov     r8d, [rsp+140h+var_F0+4]
0x1800056a3  mov     rdx, [rsp+140h+var_E8]
0x1800056a8  mov     rcx, rbx
0x1800056ab  call    ?ReadFromDirectory@CReport@@QEAAJPEB_WW4REPORT_SOURCE_TYPE@@@Z; CReport::ReadFromDirectory(wchar_t const *,REPORT_SOURCE_TYPE)
0x1800056b0  mov     rcx, [rbp+48h]; this
0x1800056b4  test    eax, eax
0x1800056b6  jns     short loc_1800056EB
0x1800056b8  mov     r9d, eax; char *
0x1800056bb  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x1800056c2  mov     edx, 2F7h; void *
0x1800056c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800056cc  nop
0x1800056cd  lea     rcx, [rsp+140h+var_F8]
0x1800056d2  call    ??1?$unique_ptr@VCReport@@U?$default_delete@VCReport@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReport,utl::default_delete<CReport>>::~unique_ptr<CReport,utl::default_delete<CReport>>(void)
0x1800056d7  test    r13d, r13d
0x1800056da  jz      loc_1800057B0
0x1800056e0  mov     r8d, 6
0x1800056e6  jmp     loc_1800057BD
0x1800056eb  mov     rcx, rbx; this
0x1800056ee  call    ?IsUIFReport@CReport@@QEBAHXZ; CReport::IsUIFReport(void)
0x1800056f3  test    eax, eax
0x1800056f5  jz      short loc_1800056CD
0x1800056f7  lea     rcx, [rbp+40h+var_B8]; void *
0x1800056fb  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180005700  lea     rdx, [rbp+40h+var_B8]
0x180005704  mov     rcx, rbx
0x180005707  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000570c  mov     r8, [rbx+1718h]
0x180005713  xor     eax, eax
0x180005715  cmp     r8, [rbx+1720h]
0x18000571c  cmovz   r8, rax
0x180005720  mov     rcx, [rsp+140h+var_E8]; wchar_t *
0x180005725  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18000572a  mov     rcx, [rbp+48h]; this
0x18000572e  mov     qword ptr [rsp+140h+var_108], rax
0x180005733  mov     [rsp+140h+var_110], r8
0x180005738  mov     rax, [rbp+40h+var_B8]
0x18000573c  mov     [rsp+140h+var_118], rax; char *
0x180005741  lea     rax, aReportIsAUifNo; "Report is a UIF.  Not pruning. ReportId"...
0x180005748  mov     qword ptr [rsp+140h+var_120], rax; int
0x18000574d  mov     r9d, 80000000h; char *
0x180005753  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18000575a  mov     edx, 302h; void *
0x18000575f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180005764  lea     rcx, [rbp+40h+var_B8]; void *
0x180005768  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18000576d  nop
0x18000576e  lea     rcx, [rsp+140h+var_F8]
0x180005773  call    ??1?$unique_ptr@VCReport@@U?$default_delete@VCReport@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReport,utl::default_delete<CReport>>::~unique_ptr<CReport,utl::default_delete<CReport>>(void)
0x180005778  mov     esi, [rbp+40h+arg_18]
0x18000577b  inc     r15d
0x18000577e  mov     r13d, [rbp+40h+arg_8]
0x180005782  jmp     loc_1800055A5
0x180005787  mov     rcx, [rbp+48h]; this
0x18000578b  lea     rax, aFailedToAlloca; "Failed to allocate memory for report."
0x180005792  mov     qword ptr [rsp+140h+var_120], rax; int
0x180005797  mov     r9d, 80000000h; char *
0x18000579d  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x1800057a4  mov     edx, 2F3h; void *
0x1800057a9  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800057ae  jmp     short loc_18000576E
0x1800057b0  mov     eax, edi
0x1800057b2  neg     eax
0x1800057b4  sbb     r8d, r8d
0x1800057b7  neg     r8d
0x1800057ba  inc     r8d
0x1800057bd  xor     r9d, r9d
0x1800057c0  mov     rdx, [rsp+140h+var_E8]
0x1800057c5  mov     rcx, rsi
0x1800057c8  call    ?DeleteReportFromStore@CReportStore@@QEAAJPEB_WW4REPORT_DELETE_REASON@@PEAVCReport@@@Z; CReportStore::DeleteReportFromStore(wchar_t const *,REPORT_DELETE_REASON,CReport *)
0x1800057cd  mov     rcx, [rbp+48h]; this
0x1800057d1  test    eax, eax
0x1800057d3  jns     short loc_1800057EB
0x1800057d5  mov     r9d, eax; char *
0x1800057d8  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x1800057df  mov     edx, 316h; void *
0x1800057e4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800057e9  jmp     short loc_180005778
0x1800057eb  cmp     [rsp+140h+var_C8], r14
0x1800057f0  ja      short loc_180005804
0x1800057f2  sub     r14, [rsp+140h+var_C8]
0x1800057f7  mov     esi, [rbp+40h+arg_18]
0x1800057fa  dec     esi
0x1800057fc  mov     [rbp+40h+arg_18], esi
0x1800057ff  jmp     loc_18000577B
0x180005804  mov     ebx, 8000FFFFh
0x180005809  mov     r9d, ebx
0x18000580c  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180005813  mov     edx, 321h
0x180005818  jmp     loc_1800054FD
0x18000581d  mov     r9d, eax
0x180005820  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180005827  mov     edx, 2E1h
0x18000582c  jmp     loc_1800054FD
0x180005831  mov     r9d, eax
0x180005834  mov     edx, 2DBh
0x180005839  jmp     loc_180005501
0x18000583e  mov     r9d, eax
0x180005841  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180005848  mov     edx, 2D1h
0x18000584d  jmp     loc_1800054FD
0x180005852  mov     r9d, eax
0x180005855  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18000585c  mov     edx, 2C1h
0x180005861  jmp     loc_1800054FD
0x180005866  xor     r15d, r15d
0x180005869  lea     rcx, [rsp+140h+var_E8]; void *
0x18000586e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180005873  mov     ebx, r15d
0x180005876  lea     rcx, [rbp+40h+var_90]; this
0x18000587a  call    ??1CReportKeyEnumerator@@QEAA@XZ; CReportKeyEnumerator::~CReportKeyEnumerator(void)
0x18000587f  mov     eax, ebx
0x180005881  mov     rbx, [rsp+140h+arg_10]
0x180005889  add     rsp, 110h
0x180005890  pop     r15
0x180005892  pop     r14
0x180005894  pop     r13
0x180005896  pop     r12
  ... truncated ...
```
