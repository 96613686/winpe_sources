# CReport::~CReport(void)

- ea: `0x1800077d4`
- end: `0x180007c21`
- name: `??1CReport@@QEAA@XZ`
- size: `1101`
- prototype: `void __fastcall(CReport *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800077a4`

## callees

- `0x180005e08`
- `0x180005e34`
- `0x180005e78`
- `0x1800077d4`
- `0x180007e10`
- `0x180007e34`
- `0x18000d8f8`
- `0x18000da08`
- `0x18000dad0`
- `0x18001abd8`
- `0x180026498`
- `0x18002ffc4`
- `0x180037610`
- `0x180039dc8`
- `0x18003bf14`
- `0x1800426b4`
- `0x1800528b4`
- `0x180070f3c`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000799f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800079c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000799f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800079c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079d3`
- `api-ms-win-core-processsnapshot-l1-1-0!PssFreeSnapshot` at `0x1800079ab`
- `api-ms-win-core-processsnapshot-l1-1-0!PssFreeSnapshot` at `0x1800079ab`

## string_xrefs

- `0x180007843`: `onecore\windows\feedback\core\werdll\lib\report.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CReport::~CReport(CReport *this)
{
  const wchar_t *v2; // rcx
  int v3; // eax
  unsigned int v4; // esi
  struct CReportFile *v5; // rbx
  char v6; // dl
  __int64 v7; // rax
  __int64 v8; // rcx
  void (__fastcall *v9)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  __int64 v10; // rdx
  __int64 v11; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE v13; // rax
  HANDLE v14; // rcx
  int v15; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct CReportFile *v17; // [rsp+70h] [rbp+8h] BYREF

  if ( (*((_DWORD *)this + 1654) & 0x420) == 0 )
  {
    CReport::DeleteFilesToBeDeleted(this, 0);
    v2 = (const wchar_t *)*((_QWORD *)this + 5806);
    if ( v2 != *((const wchar_t **)this + 5807)
      && (*((_DWORD *)this + 11636) == 2 || (*((_DWORD *)this + 1654) & 0x100) != 0) )
    {
      v3 = UtilRecursiveRemoveDirectory(v2, 1, 0, 0);
      if ( v3 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBFF,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\report.cpp",
          (const char *)(unsigned int)v3,
          v15);
    }
  }
  v4 = 0;
  if ( (unsigned int)((__int64)(*((_QWORD *)this + 728) - *((_QWORD *)this + 727)) >> 3) )
  {
    while ( 1 )
    {
      v17 = 0;
      if ( (int)CReport::GetFileByIndex(this, v4, &v17) >= 0 )
        break;
LABEL_30:
      if ( ++v4 >= (unsigned int)((__int64)(*((_QWORD *)this + 728) - *((_QWORD *)this + 727)) >> 3) )
        goto LABEL_31;
    }
    v5 = v17;
    v6 = *((_BYTE *)v17 + 48);
    v7 = *((_QWORD *)v17 + 15);
    if ( v6 )
    {
      if ( *((_QWORD *)v17 + 14) != v7 )
        goto LABEL_23;
    }
    else if ( *((_QWORD *)v17 + 14) == v7 )
    {
      if ( *((_QWORD *)v17 + 7) )
      {
LABEL_16:
        v8 = *((_QWORD *)v17 + 14);
        if ( (v8 != *((_QWORD *)v17 + 15) || *((_QWORD *)v17 + 10) != *((_QWORD *)v17 + 11))
          && (v6 || v8 != *((_QWORD *)v17 + 15) || *((_QWORD *)v17 + 7))
          && (!*((_QWORD *)v17 + 9) || *((_QWORD *)v17 + 7)) )
        {
          goto LABEL_24;
        }
      }
LABEL_23:
      MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_24:
      v9 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)v5 + 7);
      if ( v9 && (*((_DWORD *)v5 + 1) & 0x10000000) == 0 && !*((_QWORD *)v5 + 9) )
      {
        v9(*((_QWORD *)v5 + 8), 0, 0, 0, 0, 0, 0);
        *((_DWORD *)v5 + 1) |= 0x10000000u;
      }
      v10 = *((_QWORD *)v5 + 9);
      *((_QWORD *)v5 + 9) = 0;
      if ( v10 )
        utl::default_delete<CReportCabStream>::operator()();
      goto LABEL_30;
    }
    if ( !*((_QWORD *)v17 + 7) && !*((_QWORD *)v17 + 9) )
      goto LABEL_16;
    goto LABEL_23;
  }
LABEL_31:
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46560, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 52056, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46616, 0);
  v11 = *((_QWORD *)this + 1139);
  if ( v11 )
  {
    CurrentProcess = GetCurrentProcess();
    PssFreeSnapshot(CurrentProcess, v11);
    *((_QWORD *)this + 1139) = 0;
  }
  if ( *((_QWORD *)this + 830) )
  {
    v13 = GetCurrentProcess();
    v14 = (HANDLE)*((_QWORD *)this + 830);
    if ( v14 != v13 )
    {
      CloseHandle(v14);
      *((_QWORD *)this + 830) = 0;
    }
  }
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46552, 0);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 52056);
  utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit((char *)this + 52024);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 51984);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 51952);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 51920);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 51864);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 51832);
  `eh vector destructor iterator'((char *)this + 46688, 0x68u, 0x31u, (void (*)(void *))CRegSetting::~CRegSetting);
  utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit((char *)this + 46656);
  utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit((char *)this + 46632);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 46616);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 46576));
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 46560);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 46552);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 46512);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 46480);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 46448);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 46416);
  `eh vector destructor iterator'((char *)this + 16592, 0x748u, 0x10u, (void (*)(void *))CProcessDump::~CProcessDump);
  CProcessDump::~CProcessDump((CReport *)((char *)this + 14728));
  CProcessDump::~CProcessDump((CReport *)((char *)this + 12864));
  CProcessDump::~CProcessDump((CReport *)((char *)this + 11000));
  CProcessDump::~CProcessDump((CReport *)((char *)this + 9136));
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 6568);
  OsInformation::~OsInformation((CReport *)((char *)this + 6032));
  CIniParser::~CIniParser((CReport *)((char *)this + 5968));
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 5912);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 5880);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit((char *)this + 5848);
  utl::vector<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>,utl::allocator<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>>>::_Uninit((char *)this + 5816);
  CIniParser::~CIniParser((CReport *)((char *)this + 5760));
  `eh vector destructor iterator'(
    (char *)this + 5120,
    0x40u,
    0xAu,
    (void (*)(void *))CTpNonUniqueArgumentSet::TOKEN_VALUE::~TOKEN_VALUE);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 5088);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 5056);
  `eh vector destructor iterator'(
    (char *)this + 1600,
    0x40u,
    0x36u,
    (void (*)(void *))CTpNonUniqueArgumentSet::TOKEN_VALUE::~TOKEN_VALUE);
  `eh vector destructor iterator'(
    (char *)this + 960,
    0x40u,
    0xAu,
    (void (*)(void *))CTpNonUniqueArgumentSet::TOKEN_VALUE::~TOKEN_VALUE);
  `eh vector destructor iterator'(
    (char *)this + 608,
    0x20u,
    0xBu,
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 560);
  CResponse::~CResponse((CReport *)((char *)this + 8));
}

```

## disassembly

```asm
0x1800077d4  mov     [rsp+arg_8], rbx
0x1800077d9  mov     [rsp+arg_10], rbp
0x1800077de  push    rsi
0x1800077df  push    rdi
0x1800077e0  push    r12
0x1800077e2  push    r14
0x1800077e4  push    r15
0x1800077e6  sub     rsp, 40h
0x1800077ea  mov     rdi, rcx
0x1800077ed  xor     r12d, r12d
0x1800077f0  test    dword ptr [rcx+19D8h], 420h
0x1800077fa  jnz     short loc_180007854
0x1800077fc  xor     edx, edx; int
0x1800077fe  call    ?DeleteFilesToBeDeleted@CReport@@QEAAJH@Z; CReport::DeleteFilesToBeDeleted(int)
0x180007803  mov     rcx, [rdi+0B570h]; wchar_t *
0x18000780a  cmp     rcx, [rdi+0B578h]
0x180007811  jz      short loc_180007854
0x180007813  cmp     dword ptr [rdi+0B5D0h], 2
0x18000781a  jz      short loc_180007828
0x18000781c  test    dword ptr [rdi+19D8h], 100h
0x180007826  jz      short loc_180007854
0x180007828  xor     r9d, r9d; wchar_t *
0x18000782b  xor     r8d, r8d; wchar_t *
0x18000782e  lea     edx, [r9+1]; int
0x180007832  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x180007837  mov     rcx, [rsp+68h]; this
0x18000783c  test    eax, eax
0x18000783e  jns     short loc_180007854
0x180007840  mov     r9d, eax; char *
0x180007843  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werdl"...
0x18000784a  mov     edx, 0BFFh; void *
0x18000784f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007854  mov     esi, r12d
0x180007857  lea     rbp, [rdi+16B8h]
0x18000785e  mov     rax, [rdi+16C0h]
0x180007865  sub     rax, [rbp+0]
0x180007869  sar     rax, 3
0x18000786d  test    eax, eax
0x18000786f  jz      loc_180007960
0x180007875  mov     r14d, 10000000h
0x18000787b  mov     [rsp+68h+arg_0], r12
0x180007880  lea     r8, [rsp+68h+arg_0]; struct CReportFile **
0x180007885  mov     edx, esi; unsigned int
0x180007887  mov     rcx, rdi; this
0x18000788a  call    ?GetFileByIndex@CReport@@QEAAJKPEAPEAVCReportFile@@@Z; CReport::GetFileByIndex(ulong,CReportFile * *)
0x18000788f  test    eax, eax
0x180007891  js      loc_180007947
0x180007897  mov     rbx, [rsp+68h+arg_0]
0x18000789c  mov     dl, [rbx+30h]
0x18000789f  mov     rax, [rbx+78h]
0x1800078a3  test    dl, dl
0x1800078a5  jz      short loc_1800078BB
0x1800078a7  cmp     [rbx+70h], rax
0x1800078ab  jnz     short loc_1800078F7
0x1800078ad  cmp     [rbx+38h], r12
0x1800078b1  jnz     short loc_1800078F7
0x1800078b3  cmp     [rbx+48h], r12
0x1800078b7  jnz     short loc_1800078F7
0x1800078b9  jmp     short loc_1800078C7
0x1800078bb  cmp     [rbx+70h], rax
0x1800078bf  jnz     short loc_1800078AD
0x1800078c1  cmp     [rbx+38h], r12
0x1800078c5  jz      short loc_1800078F7
0x1800078c7  mov     rcx, [rbx+70h]
0x1800078cb  cmp     rcx, [rbx+78h]
0x1800078cf  jnz     short loc_1800078DB
0x1800078d1  mov     rax, [rbx+58h]
0x1800078d5  cmp     [rbx+50h], rax
0x1800078d9  jz      short loc_1800078F7
0x1800078db  test    dl, dl
0x1800078dd  jnz     short loc_1800078EB
0x1800078df  cmp     rcx, [rbx+78h]
0x1800078e3  jnz     short loc_1800078EB
0x1800078e5  cmp     [rbx+38h], r12
0x1800078e9  jz      short loc_1800078F7
0x1800078eb  cmp     [rbx+48h], r12
0x1800078ef  jz      short loc_1800078FC
0x1800078f1  cmp     [rbx+38h], r12
0x1800078f5  jnz     short loc_1800078FC
0x1800078f7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800078fc  mov     rax, [rbx+38h]
0x180007900  test    rax, rax
0x180007903  jz      short loc_180007935
0x180007905  test    [rbx+4], r14d
0x180007909  jnz     short loc_180007935
0x18000790b  cmp     [rbx+48h], r12
0x18000790f  jnz     short loc_180007935
0x180007911  mov     [rsp+68h+var_38], r12
0x180007916  mov     [rsp+68h+var_40], r12
0x18000791b  mov     [rsp+68h+var_48], r12
0x180007920  xor     r9d, r9d
0x180007923  xor     r8d, r8d
0x180007926  xor     edx, edx
0x180007928  mov     rcx, [rbx+40h]
0x18000792c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007931  or      [rbx+4], r14d
0x180007935  mov     rdx, [rbx+48h]
0x180007939  mov     [rbx+48h], r12
0x18000793d  test    rdx, rdx
0x180007940  jz      short loc_180007947
0x180007942  call    ??R?$default_delete@VCReportCabStream@@@utl@@QEBAXPEAVCReportCabStream@@@Z; utl::default_delete<CReportCabStream>::operator()(CReportCabStream *)
0x180007947  inc     esi
0x180007949  mov     rax, [rdi+16C0h]
0x180007950  sub     rax, [rbp+0]
0x180007954  sar     rax, 3
0x180007958  cmp     esi, eax
0x18000795a  jb      loc_18000787B
0x180007960  lea     rsi, [rdi+0B5E0h]
0x180007967  xor     edx, edx
0x180007969  mov     rcx, rsi
0x18000796c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180007971  lea     r14, [rdi+0CB58h]
0x180007978  xor     edx, edx
0x18000797a  mov     rcx, r14
0x18000797d  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180007982  lea     r15, [rdi+0B618h]
0x180007989  xor     edx, edx
0x18000798b  mov     rcx, r15
0x18000798e  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180007993  mov     rbx, [rdi+2398h]
0x18000799a  test    rbx, rbx
0x18000799d  jz      short loc_1800079B8
0x18000799f  call    cs:__imp_GetCurrentProcess
0x1800079a5  mov     rdx, rbx
0x1800079a8  mov     rcx, rax
0x1800079ab  call    cs:__imp_PssFreeSnapshot
0x1800079b1  mov     [rdi+2398h], r12
0x1800079b8  cmp     [rdi+19F0h], r12
0x1800079bf  jz      short loc_1800079E0
0x1800079c1  call    cs:__imp_GetCurrentProcess
0x1800079c7  mov     rcx, [rdi+19F0h]; hObject
0x1800079ce  cmp     rcx, rax
0x1800079d1  jz      short loc_1800079E0
0x1800079d3  call    cs:__imp_CloseHandle
0x1800079d9  mov     [rdi+19F0h], r12
0x1800079e0  lea     rbx, [rdi+0B5D8h]
0x1800079e7  xor     edx, edx
0x1800079e9  mov     rcx, rbx
0x1800079ec  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800079f1  mov     rcx, r14
0x1800079f4  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800079f9  lea     rcx, [rdi+0CB38h]
0x180007a00  call    ?_Uninit@?$vector@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@V?$allocator@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(void)
0x180007a05  lea     rcx, [rdi+0CB10h]; void *
0x180007a0c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007a11  lea     rcx, [rdi+0CAF0h]; void *
0x180007a18  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007a1d  lea     rcx, [rdi+0CAD0h]; void *
0x180007a24  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007a29  lea     rcx, [rdi+0CA98h]; void *
0x180007a30  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007a35  lea     rcx, [rdi+0CA78h]; void *
0x180007a3c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007a41  nop
0x180007a42  lea     rcx, [rdi+0B660h]; void *
0x180007a49  lea     r9, ??1CRegSetting@@QEAA@XZ; void (*)(void *)
0x180007a50  mov     edx, 68h ; 'h'; unsigned __int64
0x180007a55  lea     r8d, [rdx-37h]; unsigned __int64
0x180007a59  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007a5e  nop
0x180007a5f  lea     rcx, [rdi+0B640h]
0x180007a66  call    ?_Uninit@?$vector@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@V?$allocator@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(void)
0x180007a6b  lea     rcx, [rdi+0B628h]
0x180007a72  call    ?_Uninit@?$vector@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@V?$allocator@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(void)
0x180007a77  mov     rcx, r15
0x180007a7a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180007a7f  lea     rcx, [rdi+0B5F0h]; lpCriticalSection
0x180007a86  call    cs:__imp_DeleteCriticalSection
0x180007a8c  mov     rcx, rsi
0x180007a8f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180007a94  mov     rcx, rbx
0x180007a97  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180007a9c  lea     rcx, [rdi+0B5B0h]; void *
0x180007aa3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007aa8  lea     rcx, [rdi+0B590h]; void *
0x180007aaf  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007ab4  lea     rcx, [rdi+0B570h]; void *
0x180007abb  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007ac0  lea     rcx, [rdi+0B550h]; void *
0x180007ac7  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007acc  lea     rcx, [rdi+40D0h]; void *
0x180007ad3  lea     r9, ??1CProcessDump@@QEAA@XZ; void (*)(void *)
0x180007ada  mov     edx, 748h; unsigned __int64
0x180007adf  mov     r8d, 10h; unsigned __int64
0x180007ae5  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007aea  lea     rcx, [rdi+3988h]; this
0x180007af1  call    ??1CProcessDump@@QEAA@XZ; CProcessDump::~CProcessDump(void)
0x180007af6  lea     rcx, [rdi+3240h]; this
0x180007afd  call    ??1CProcessDump@@QEAA@XZ; CProcessDump::~CProcessDump(void)
0x180007b02  lea     rcx, [rdi+2AF8h]; this
0x180007b09  call    ??1CProcessDump@@QEAA@XZ; CProcessDump::~CProcessDump(void)
0x180007b0e  lea     rcx, [rdi+23B0h]; this
0x180007b15  call    ??1CProcessDump@@QEAA@XZ; CProcessDump::~CProcessDump(void)
0x180007b1a  lea     rcx, [rdi+19A8h]; void *
0x180007b21  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007b26  lea     rcx, [rdi+1790h]; this
0x180007b2d  call    ??1OsInformation@@QEAA@XZ; OsInformation::~OsInformation(void)
0x180007b32  lea     rcx, [rdi+1750h]; this
0x180007b39  call    ??1CIniParser@@QEAA@XZ; CIniParser::~CIniParser(void)
0x180007b3e  lea     rcx, [rdi+1718h]; void *
0x180007b45  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007b4a  lea     rcx, [rdi+16F8h]; void *
0x180007b51  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007b56  lea     rcx, [rdi+16D8h]
0x180007b5d  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x180007b62  mov     rcx, rbp
0x180007b65  call    ?_Uninit@?$vector@V?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>,utl::allocator<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>>>::_Uninit(void)
0x180007b6a  lea     rcx, [rdi+1680h]; this
0x180007b71  call    ??1CIniParser@@QEAA@XZ; CIniParser::~CIniParser(void)
0x180007b76  lea     rcx, [rdi+1400h]; void *
0x180007b7d  lea     rbp, ??1TOKEN_VALUE@CTpNonUniqueArgumentSet@@QEAA@XZ; CTpNonUniqueArgumentSet::TOKEN_VALUE::~TOKEN_VALUE(void)
0x180007b84  mov     r9, rbp; void (*)(void *)
0x180007b87  mov     esi, 0Ah
0x180007b8c  mov     r8d, esi; unsigned __int64
0x180007b8f  lea     ebx, [rsi+36h]
0x180007b92  mov     edx, ebx; unsigned __int64
0x180007b94  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007b99  lea     rcx, [rdi+13E0h]; void *
0x180007ba0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007ba5  lea     rcx, [rdi+13C0h]; void *
0x180007bac  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007bb1  lea     rcx, [rdi+640h]; void *
0x180007bb8  mov     r9, rbp; void (*)(void *)
0x180007bbb  lea     r8d, [rsi+2Ch]; unsigned __int64
0x180007bbf  mov     edx, ebx; unsigned __int64
0x180007bc1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007bc6  lea     rcx, [rdi+3C0h]; void *
0x180007bcd  mov     r9, rbp; void (*)(void *)
0x180007bd0  mov     r8d, esi; unsigned __int64
0x180007bd3  mov     edx, ebx; unsigned __int64
0x180007bd5  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007bda  lea     rcx, [rdi+260h]; void *
0x180007be1  lea     r9, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; void (*)(void *)
0x180007be8  lea     edx, [rsi+16h]; unsigned __int64
0x180007beb  lea     r8d, [rsi+1]; unsigned __int64
0x180007bef  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007bf4  lea     rcx, [rdi+230h]; void *
0x180007bfb  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007c00  lea     rcx, [rdi+8]; this
0x180007c04  lea     r11, [rsp+68h+var_28]
0x180007c09  mov     rbx, [r11+38h]
0x180007c0d  mov     rbp, [r11+40h]
0x180007c11  mov     rsp, r11
0x180007c14  pop     r15
0x180007c16  pop     r14
0x180007c18  pop     r12
0x180007c1a  pop     rdi
0x180007c1b  pop     rsi
0x180007c1c  jmp     ??1CResponse@@QEAA@XZ; CResponse::~CResponse(void)
```
