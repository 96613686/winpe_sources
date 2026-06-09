# CReport::~CReport(void)

- ea: `0x180007878`
- end: `0x180007ce3`
- name: `??1CReport@@QEAA@XZ`
- size: `1131`
- prototype: `void __fastcall(CReport *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007848`

## callees

- `0x1800062bc`
- `0x180006a24`
- `0x180006a58`
- `0x180006aa4`
- `0x180007514`
- `0x180007878`
- `0x180007fd8`
- `0x180008004`
- `0x18000d930`
- `0x18000db80`
- `0x180025848`
- `0x1800318c8`
- `0x1800396c0`
- `0x18003b9c0`
- `0x18003de9c`
- `0x18004373c`
- `0x180054e24`
- `0x180074268`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007a43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007a71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007a43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007a71`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007b42`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a89`
- `api-ms-win-core-processsnapshot-l1-1-0!PssFreeSnapshot` at `0x180007a55`
- `api-ms-win-core-processsnapshot-l1-1-0!PssFreeSnapshot` at `0x180007a55`

## string_xrefs

- `0x1800078e7`: `onecore\windows\feedback\core\werdll\lib\report.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CReport::~CReport(CReport *this)
{
  const wchar_t *v2; // rcx
  int v3; // eax
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  struct CReportFile *v8; // rbx
  __int64 v9; // rax
  void (__fastcall *v10)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  __int64 v11; // rdx
  __int64 v12; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE v14; // rax
  HANDLE v15; // rcx
  int v16; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct CReportFile *v18; // [rsp+70h] [rbp+8h] BYREF

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
          (void *)0xC1E,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\report.cpp",
          (const char *)(unsigned int)v3,
          v16);
    }
  }
  v4 = 0;
  if ( (unsigned int)((__int64)(*((_QWORD *)this + 728) - *((_QWORD *)this + 727)) >> 3) )
  {
    while ( 1 )
    {
      v18 = 0;
      if ( (int)CReport::GetFileByIndex(this, v4, &v18) >= 0 )
        break;
LABEL_30:
      if ( ++v4 >= (unsigned int)((__int64)(*((_QWORD *)this + 728) - *((_QWORD *)this + 727)) >> 3) )
        goto LABEL_31;
    }
    v8 = v18;
    LOBYTE(v5) = *((_BYTE *)v18 + 48);
    v9 = *((_QWORD *)v18 + 15);
    if ( (_BYTE)v5 )
    {
      if ( *((_QWORD *)v18 + 14) != v9 )
        goto LABEL_23;
    }
    else if ( *((_QWORD *)v18 + 14) == v9 )
    {
      if ( *((_QWORD *)v18 + 7) )
      {
LABEL_16:
        v6 = *((_QWORD *)v18 + 14);
        if ( (v6 != *((_QWORD *)v18 + 15) || *((_QWORD *)v18 + 10) != *((_QWORD *)v18 + 11))
          && ((_BYTE)v5 || v6 != *((_QWORD *)v18 + 15) || *((_QWORD *)v18 + 7))
          && (!*((_QWORD *)v18 + 9) || *((_QWORD *)v18 + 7)) )
        {
          goto LABEL_24;
        }
      }
LABEL_23:
      MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v7);
LABEL_24:
      v10 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)v8 + 7);
      if ( v10 && (*((_DWORD *)v8 + 1) & 0x10000000) == 0 && !*((_QWORD *)v8 + 9) )
      {
        v10(*((_QWORD *)v8 + 8), 0, 0, 0, 0, 0, 0);
        *((_DWORD *)v8 + 1) |= 0x10000000u;
      }
      v11 = *((_QWORD *)v8 + 9);
      *((_QWORD *)v8 + 9) = 0;
      if ( v11 )
        utl::default_delete<CReportCabStream>::operator()();
      goto LABEL_30;
    }
    if ( !*((_QWORD *)v18 + 7) && !*((_QWORD *)v18 + 9) )
      goto LABEL_16;
    goto LABEL_23;
  }
LABEL_31:
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46560, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 52056, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46616, 0);
  v12 = *((_QWORD *)this + 1139);
  if ( v12 )
  {
    CurrentProcess = GetCurrentProcess();
    PssFreeSnapshot(CurrentProcess, v12);
    *((_QWORD *)this + 1139) = 0;
  }
  if ( *((_QWORD *)this + 830) )
  {
    v14 = GetCurrentProcess();
    v15 = (HANDLE)*((_QWORD *)this + 830);
    if ( v15 != v14 )
    {
      CloseHandle(v15);
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
0x180007878  mov     [rsp+arg_8], rbx
0x18000787d  mov     [rsp+arg_10], rbp
0x180007882  push    rsi
0x180007883  push    rdi
0x180007884  push    r12
0x180007886  push    r14
0x180007888  push    r15
0x18000788a  sub     rsp, 40h
0x18000788e  mov     rdi, rcx
0x180007891  xor     r12d, r12d
0x180007894  test    dword ptr [rcx+19D8h], 420h
0x18000789e  jnz     short loc_1800078F8
0x1800078a0  xor     edx, edx; int
0x1800078a2  call    ?DeleteFilesToBeDeleted@CReport@@QEAAJH@Z; CReport::DeleteFilesToBeDeleted(int)
0x1800078a7  mov     rcx, [rdi+0B570h]; wchar_t *
0x1800078ae  cmp     rcx, [rdi+0B578h]
0x1800078b5  jz      short loc_1800078F8
0x1800078b7  cmp     dword ptr [rdi+0B5D0h], 2
0x1800078be  jz      short loc_1800078CC
0x1800078c0  test    dword ptr [rdi+19D8h], 100h
0x1800078ca  jz      short loc_1800078F8
0x1800078cc  xor     r9d, r9d; wchar_t *
0x1800078cf  xor     r8d, r8d; wchar_t *
0x1800078d2  lea     edx, [r9+1]; int
0x1800078d6  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x1800078db  mov     rcx, [rsp+68h]; this
0x1800078e0  test    eax, eax
0x1800078e2  jns     short loc_1800078F8
0x1800078e4  mov     r9d, eax; char *
0x1800078e7  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werdl"...
0x1800078ee  mov     edx, 0C1Eh; void *
0x1800078f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800078f8  mov     esi, r12d
0x1800078fb  lea     rbp, [rdi+16B8h]
0x180007902  mov     rax, [rdi+16C0h]
0x180007909  sub     rax, [rbp+0]
0x18000790d  sar     rax, 3
0x180007911  test    eax, eax
0x180007913  jz      loc_180007A04
0x180007919  mov     r14d, 10000000h
0x18000791f  mov     [rsp+68h+arg_0], r12
0x180007924  lea     r8, [rsp+68h+arg_0]; struct CReportFile **
0x180007929  mov     edx, esi; unsigned int
0x18000792b  mov     rcx, rdi; this
0x18000792e  call    ?GetFileByIndex@CReport@@QEAAJKPEAPEAVCReportFile@@@Z; CReport::GetFileByIndex(ulong,CReportFile * *)
0x180007933  test    eax, eax
0x180007935  js      loc_1800079EB
0x18000793b  mov     rbx, [rsp+68h+arg_0]
0x180007940  mov     dl, [rbx+30h]
0x180007943  mov     rax, [rbx+78h]
0x180007947  test    dl, dl
0x180007949  jz      short loc_18000795F
0x18000794b  cmp     [rbx+70h], rax
0x18000794f  jnz     short loc_18000799B
0x180007951  cmp     [rbx+38h], r12
0x180007955  jnz     short loc_18000799B
0x180007957  cmp     [rbx+48h], r12
0x18000795b  jnz     short loc_18000799B
0x18000795d  jmp     short loc_18000796B
0x18000795f  cmp     [rbx+70h], rax
0x180007963  jnz     short loc_180007951
0x180007965  cmp     [rbx+38h], r12
0x180007969  jz      short loc_18000799B
0x18000796b  mov     rcx, [rbx+70h]
0x18000796f  cmp     rcx, [rbx+78h]
0x180007973  jnz     short loc_18000797F
0x180007975  mov     rax, [rbx+58h]
0x180007979  cmp     [rbx+50h], rax
0x18000797d  jz      short loc_18000799B
0x18000797f  test    dl, dl
0x180007981  jnz     short loc_18000798F
0x180007983  cmp     rcx, [rbx+78h]
0x180007987  jnz     short loc_18000798F
0x180007989  cmp     [rbx+38h], r12
0x18000798d  jz      short loc_18000799B
0x18000798f  cmp     [rbx+48h], r12
0x180007993  jz      short loc_1800079A0
0x180007995  cmp     [rbx+38h], r12
0x180007999  jnz     short loc_1800079A0
0x18000799b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800079a0  mov     rax, [rbx+38h]
0x1800079a4  test    rax, rax
0x1800079a7  jz      short loc_1800079D9
0x1800079a9  test    [rbx+4], r14d
0x1800079ad  jnz     short loc_1800079D9
0x1800079af  cmp     [rbx+48h], r12
0x1800079b3  jnz     short loc_1800079D9
0x1800079b5  mov     [rsp+68h+var_38], r12
0x1800079ba  mov     [rsp+68h+var_40], r12
0x1800079bf  mov     [rsp+68h+var_48], r12
0x1800079c4  xor     r9d, r9d
0x1800079c7  xor     r8d, r8d
0x1800079ca  xor     edx, edx
0x1800079cc  mov     rcx, [rbx+40h]
0x1800079d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d5  or      [rbx+4], r14d
0x1800079d9  mov     rdx, [rbx+48h]
0x1800079dd  mov     [rbx+48h], r12
0x1800079e1  test    rdx, rdx
0x1800079e4  jz      short loc_1800079EB
0x1800079e6  call    ??R?$default_delete@VCReportCabStream@@@utl@@QEBAXPEAVCReportCabStream@@@Z; utl::default_delete<CReportCabStream>::operator()(CReportCabStream *)
0x1800079eb  inc     esi
0x1800079ed  mov     rax, [rdi+16C0h]
0x1800079f4  sub     rax, [rbp+0]
0x1800079f8  sar     rax, 3
0x1800079fc  cmp     esi, eax
0x1800079fe  jb      loc_18000791F
0x180007a04  lea     rsi, [rdi+0B5E0h]
0x180007a0b  xor     edx, edx
0x180007a0d  mov     rcx, rsi
0x180007a10  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180007a15  lea     r14, [rdi+0CB58h]
0x180007a1c  xor     edx, edx
0x180007a1e  mov     rcx, r14
0x180007a21  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180007a26  lea     r15, [rdi+0B618h]
0x180007a2d  xor     edx, edx
0x180007a2f  mov     rcx, r15
0x180007a32  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180007a37  mov     rbx, [rdi+2398h]
0x180007a3e  test    rbx, rbx
0x180007a41  jz      short loc_180007A68
0x180007a43  call    cs:__imp_GetCurrentProcess
0x180007a4a  nop     dword ptr [rax+rax+00h]
0x180007a4f  mov     rdx, rbx
0x180007a52  mov     rcx, rax
0x180007a55  call    cs:__imp_PssFreeSnapshot
0x180007a5c  nop     dword ptr [rax+rax+00h]
0x180007a61  mov     [rdi+2398h], r12
0x180007a68  cmp     [rdi+19F0h], r12
0x180007a6f  jz      short loc_180007A9C
0x180007a71  call    cs:__imp_GetCurrentProcess
0x180007a78  nop     dword ptr [rax+rax+00h]
0x180007a7d  mov     rcx, [rdi+19F0h]; hObject
0x180007a84  cmp     rcx, rax
0x180007a87  jz      short loc_180007A9C
0x180007a89  call    cs:__imp_CloseHandle
0x180007a90  nop     dword ptr [rax+rax+00h]
0x180007a95  mov     [rdi+19F0h], r12
0x180007a9c  lea     rbx, [rdi+0B5D8h]
0x180007aa3  xor     edx, edx
0x180007aa5  mov     rcx, rbx
0x180007aa8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180007aad  mov     rcx, r14
0x180007ab0  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180007ab5  lea     rcx, [rdi+0CB38h]
0x180007abc  call    ?_Uninit@?$vector@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@V?$allocator@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(void)
0x180007ac1  lea     rcx, [rdi+0CB10h]; void *
0x180007ac8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007acd  lea     rcx, [rdi+0CAF0h]; void *
0x180007ad4  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007ad9  lea     rcx, [rdi+0CAD0h]; void *
0x180007ae0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007ae5  lea     rcx, [rdi+0CA98h]; void *
0x180007aec  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007af1  lea     rcx, [rdi+0CA78h]; void *
0x180007af8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007afd  nop
0x180007afe  lea     rcx, [rdi+0B660h]; void *
0x180007b05  lea     r9, ??1CRegSetting@@QEAA@XZ; void (*)(void *)
0x180007b0c  mov     edx, 68h ; 'h'; unsigned __int64
0x180007b11  lea     r8d, [rdx-37h]; unsigned __int64
0x180007b15  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007b1a  nop
0x180007b1b  lea     rcx, [rdi+0B640h]
0x180007b22  call    ?_Uninit@?$vector@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@V?$allocator@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(void)
0x180007b27  lea     rcx, [rdi+0B628h]
0x180007b2e  call    ?_Uninit@?$vector@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@V?$allocator@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::allocator<utl::_TreeConstIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>::_Uninit(void)
0x180007b33  mov     rcx, r15
0x180007b36  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180007b3b  lea     rcx, [rdi+0B5F0h]; lpCriticalSection
0x180007b42  call    cs:__imp_DeleteCriticalSection
0x180007b49  nop     dword ptr [rax+rax+00h]
0x180007b4e  mov     rcx, rsi
0x180007b51  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180007b56  mov     rcx, rbx
0x180007b59  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180007b5e  lea     rcx, [rdi+0B5B0h]; void *
0x180007b65  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007b6a  lea     rcx, [rdi+0B590h]; void *
0x180007b71  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007b76  lea     rcx, [rdi+0B570h]; void *
0x180007b7d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007b82  lea     rcx, [rdi+0B550h]; void *
0x180007b89  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007b8e  lea     rcx, [rdi+40D0h]; void *
0x180007b95  lea     r9, ??1CProcessDump@@QEAA@XZ; void (*)(void *)
0x180007b9c  mov     edx, 748h; unsigned __int64
0x180007ba1  mov     r8d, 10h; unsigned __int64
0x180007ba7  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007bac  lea     rcx, [rdi+3988h]; this
0x180007bb3  call    ??1CProcessDump@@QEAA@XZ; CProcessDump::~CProcessDump(void)
0x180007bb8  lea     rcx, [rdi+3240h]; this
0x180007bbf  call    ??1CProcessDump@@QEAA@XZ; CProcessDump::~CProcessDump(void)
0x180007bc4  lea     rcx, [rdi+2AF8h]; this
0x180007bcb  call    ??1CProcessDump@@QEAA@XZ; CProcessDump::~CProcessDump(void)
0x180007bd0  lea     rcx, [rdi+23B0h]; this
0x180007bd7  call    ??1CProcessDump@@QEAA@XZ; CProcessDump::~CProcessDump(void)
0x180007bdc  lea     rcx, [rdi+19A8h]; void *
0x180007be3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007be8  lea     rcx, [rdi+1790h]; this
0x180007bef  call    ??1OsInformation@@QEAA@XZ; OsInformation::~OsInformation(void)
0x180007bf4  lea     rcx, [rdi+1750h]; this
0x180007bfb  call    ??1CIniParser@@QEAA@XZ; CIniParser::~CIniParser(void)
0x180007c00  lea     rcx, [rdi+1718h]; void *
0x180007c07  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007c0c  lea     rcx, [rdi+16F8h]; void *
0x180007c13  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007c18  lea     rcx, [rdi+16D8h]
0x180007c1f  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x180007c24  mov     rcx, rbp
0x180007c27  call    ?_Uninit@?$vector@V?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>,utl::allocator<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>>>::_Uninit(void)
0x180007c2c  lea     rcx, [rdi+1680h]; this
0x180007c33  call    ??1CIniParser@@QEAA@XZ; CIniParser::~CIniParser(void)
0x180007c38  lea     rcx, [rdi+1400h]; void *
0x180007c3f  lea     rbp, ??1TOKEN_VALUE@CTpNonUniqueArgumentSet@@QEAA@XZ; CTpNonUniqueArgumentSet::TOKEN_VALUE::~TOKEN_VALUE(void)
0x180007c46  mov     r9, rbp; void (*)(void *)
0x180007c49  mov     esi, 0Ah
0x180007c4e  mov     r8d, esi; unsigned __int64
0x180007c51  lea     ebx, [rsi+36h]
0x180007c54  mov     edx, ebx; unsigned __int64
0x180007c56  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007c5b  lea     rcx, [rdi+13E0h]; void *
0x180007c62  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007c67  lea     rcx, [rdi+13C0h]; void *
0x180007c6e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007c73  lea     rcx, [rdi+640h]; void *
0x180007c7a  mov     r9, rbp; void (*)(void *)
0x180007c7d  lea     r8d, [rsi+2Ch]; unsigned __int64
0x180007c81  mov     edx, ebx; unsigned __int64
0x180007c83  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007c88  lea     rcx, [rdi+3C0h]; void *
0x180007c8f  mov     r9, rbp; void (*)(void *)
0x180007c92  mov     r8d, esi; unsigned __int64
0x180007c95  mov     edx, ebx; unsigned __int64
0x180007c97  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007c9c  lea     rcx, [rdi+260h]; void *
0x180007ca3  lea     r9, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; void (*)(void *)
0x180007caa  lea     edx, [rsi+16h]; unsigned __int64
0x180007cad  lea     r8d, [rsi+1]; unsigned __int64
0x180007cb1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007cb6  lea     rcx, [rdi+230h]; void *
0x180007cbd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180007cc2  lea     rcx, [rdi+8]; this
0x180007cc6  lea     r11, [rsp+68h+var_28]
0x180007ccb  mov     rbx, [r11+38h]
0x180007ccf  mov     rbp, [r11+40h]
0x180007cd3  mov     rsp, r11
0x180007cd6  pop     r15
0x180007cd8  pop     r14
0x180007cda  pop     r12
0x180007cdc  pop     rdi
0x180007cdd  pop     rsi
0x180007cde  jmp     ??1CResponse@@QEAA@XZ; CResponse::~CResponse(void)
```
