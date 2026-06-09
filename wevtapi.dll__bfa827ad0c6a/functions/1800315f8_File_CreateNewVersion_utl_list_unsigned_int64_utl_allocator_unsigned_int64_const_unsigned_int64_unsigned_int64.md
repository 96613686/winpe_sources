# File::CreateNewVersion(utl::list<unsigned __int64,utl::allocator<unsigned __int64>> const &,unsigned __int64,unsigned __int64,bool,bool,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x1800315f8`
- end: `0x180031c35`
- name: `?CreateNewVersion@File@@AEAAXAEBV?$list@_KV?$allocator@_K@utl@@@utl@@_K1_N2AEAV?$unique_lock@Vshared_mutex@utl@@@3@@Z`
- size: `1597`
- prototype: `__int64 __usercall@<rax>(File *this@<rcx>, char, char, __int64)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, installer_update`

## callers

- `0x180031f14`
- `0x18003459c`

## callees

- `0x18000a724`
- `0x18000bf84`
- `0x18000c404`
- `0x18001585c`
- `0x180022340`
- `0x1800225a8`
- `0x1800227b4`
- `0x180022d84`
- `0x180023548`
- `0x180024a50`
- `0x180025514`
- `0x1800314f0`
- `0x180031594`
- `0x1800315f8`
- `0x180033078`
- `0x180034fd8`
- `0x180034ffc`
- `0x180035170`
- `0x180035338`
- `0x180035894`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bb2`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180031a0e`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180031a0e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031708`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031708`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800317bd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800317bd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180031ad2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180031ad2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall File::CreateNewVersion(
        File *this,
        _QWORD *a2,
        unsigned __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        __int64 a7)
{
  _QWORD *v10; // rax
  DWORD LastError; // edi
  unsigned int v12; // edx
  HANDLE FileW; // r14
  unsigned __int64 v14; // rdi
  _QWORD *i; // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  unsigned int v20; // r15d
  unsigned int v21; // edi
  __int64 v22; // rax
  unsigned int v23; // edi
  DWORD v24; // edi
  DWORD v26; // edi
  __int128 pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  int v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+5Ch] [rbp-A4h]
  char v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpPathName[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v35[8]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v36[4]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v37; // [rsp+C8h] [rbp-38h]
  _QWORD v38[4]; // [rsp+290h] [rbp+190h] BYREF
  int v39; // [rsp+2B0h] [rbp+1B0h]
  int v40; // [rsp+2B4h] [rbp+1B4h]
  unsigned __int64 v41; // [rsp+2B8h] [rbp+1B8h]
  int v42; // [rsp+30Ch] [rbp+20Ch]
  WCHAR TempFileName[264]; // [rsp+310h] [rbp+210h] BYREF

  v32 = a4;
  v33[1] = a7;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpPathName);
  v33[0] = *((_QWORD *)this + 85);
  v10 = (_QWORD *)tlx::split_path<wchar_t>::split_path<wchar_t>(&pExceptionObject, v33);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           lpPathName,
                           *v10) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 14);
    }
    pExceptionObject = 0;
    v28 = 0;
    v29 = 14;
    v30 = 0x8D1FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !GetTempFileNameW(lpPathName[0], L"evt", 0, TempFileName) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v28 = 0;
    v29 = LastError;
    v30 = 0x8D7FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  FileW = CreateFileW(TempFileName, 0xC0000000, 1u, 0, 4u, 0, 0);
  v33[0] = FileW;
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    v26 = GetLastError();
    if ( !v26 )
      v26 = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v26);
    }
    pExceptionObject = 0;
    v28 = 0;
    v29 = v26;
    v30 = 0x8E4FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v14 = 0;
  WriteFileView::WriteFileView((WriteFileView *)v35, v12, 1);
  for ( i = (_QWORD *)*a2; i != a2; i = (_QWORD *)*i )
  {
    FileView::ReadIn((FileView *)v36, *((void **)this + 84), (i[2] << 16) + 4096LL);
    if ( a5 )
    {
      v16 = v36[0];
      v17 = *(_QWORD *)(v36[0] + 16LL);
      v18 = *(_QWORD *)(v36[0] + 8LL);
      *(_QWORD *)(v36[0] + 8LL) = a3;
      if ( v17 != -1 )
      {
        v19 = a3 + v17 - v18;
        *(_QWORD *)(v16 + 16) = v19;
        a3 = v19 + 1;
      }
    }
    WriteFileView::UpdateBothCRCValues((WriteFileView *)v35);
    v36[1] = (v14 << 16) + 4096;
    v20 = FileView::ActualWrite((FileView *)v36, FileW, 0, v37);
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v20);
      }
      *(_QWORD *)&pExceptionObject = &word_18004024A;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v28 = 0;
      v29 = v20;
      v30 = -1;
      v31 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    ++v14;
  }
  if ( a6 )
    AddBlankChunk(FileW, a3, v14);
  else
    --v14;
  memset_0(v38, 0, 0x80u);
  strcpy((char *)v38, "ElfFile");
  v38[3] = v32;
  v39 = 128;
  v40 = 196610;
  v41 = CalcFileSizeNeeded(v14 + 1);
  v42 = 0;
  v38[2] = v14;
  v21 = File::WriteFileHeader(FileW, v38, 0, 0);
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v21);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v28 = 0;
    v29 = v21;
    v30 = -1;
    v31 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  FlushFileBuffers(FileW);
  v22 = *((_QWORD *)this + 84);
  *((_QWORD *)this + 84) = 0;
  v32 = v22;
  v23 = CloseAndDelete(&v32);
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v23);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v28 = 0;
    v29 = v23;
    v30 = -1;
    v31 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  *((_BYTE *)this + 829) = 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(v33, 0);
  if ( !MoveFileExW(TempFileName, *((LPCWSTR *)this + 85), 2u) )
  {
    v24 = GetLastError();
    if ( !v24 )
      v24 = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v24);
    }
    pExceptionObject = 0;
    v28 = 0;
    v29 = v24;
    v30 = 0x92FFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  File::OpenFile(this);
  FileView::~FileView((FileView *)v36);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(v33);
  return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(lpPathName);
}

```

## disassembly

```asm
0x1800315f8  push    rbp
0x1800315fa  push    rbx
0x1800315fb  push    rsi
0x1800315fc  push    rdi
0x1800315fd  push    r12
0x1800315ff  push    r13
0x180031601  push    r14
0x180031603  push    r15
0x180031605  lea     rbp, [rsp-438h]
0x18003160d  sub     rsp, 538h
0x180031614  mov     rax, cs:__security_cookie
0x18003161b  xor     rax, rsp
0x18003161e  mov     [rbp+470h+var_50], rax
0x180031625  mov     [rsp+570h+var_508], r9
0x18003162a  mov     r12, r8
0x18003162d  mov     r13, rdx
0x180031630  mov     rsi, rcx
0x180031633  mov     r15, [rbp+470h+arg_30]
0x18003163a  mov     [rsp+570h+var_4F8], r15
0x18003163f  lea     rcx, [rbp+470h+lpPathName]
0x180031643  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180031648  nop
0x180031649  mov     rax, [rsi+2A8h]
0x180031650  mov     [rsp+570h+var_500], rax
0x180031655  lea     rdx, [rsp+570h+var_500]
0x18003165a  lea     rcx, [rsp+570h+pExceptionObject]
0x18003165f  call    ??$?0PEB_W_W@?$split_path@_W@tlx@@QEAA@AEBQEB_W@Z; tlx::split_path<wchar_t>::split_path<wchar_t>(wchar_t const * const &)
0x180031664  mov     r8, [rax+10h]
0x180031668  sub     r8, [rax]
0x18003166b  sar     r8, 1
0x18003166e  mov     rdx, [rax]
0x180031671  lea     rcx, [rbp+470h+lpPathName]
0x180031675  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18003167a  xor     r15d, r15d
0x18003167d  test    al, al
0x18003167f  jnz     short loc_1800316F3
0x180031681  lea     rax, WPP_GLOBAL_Control
0x180031688  lea     edi, [r15+0Eh]
0x18003168c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031693  cmp     rcx, rax
0x180031696  jz      short loc_1800316BF
0x180031698  test    dword ptr [rcx+1Ch], 8000h
0x18003169f  jz      short loc_1800316BF
0x1800316a1  lea     ebx, [rdi-0Ch]
0x1800316a4  cmp     [rcx+19h], bl
0x1800316a7  jb      short loc_1800316BF
0x1800316a9  lea     edx, [rdi+49h]
0x1800316ac  mov     r9d, edi
0x1800316af  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800316b6  mov     rcx, [rcx+10h]
0x1800316ba  call    WPP_SF_D
0x1800316bf  xorps   xmm0, xmm0
0x1800316c2  movdqu  [rsp+570h+pExceptionObject], xmm0
0x1800316c8  mov     [rsp+570h+var_520], r15
0x1800316cd  mov     [rsp+570h+var_518], edi
0x1800316d1  mov     dword ptr [rsp+570h+var_514], 0FFFFFFFFh
0x1800316d9  mov     dword ptr [rsp+570h+var_514+4], 8D1h
0x1800316e1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800316e8  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x1800316ed  call    _CxxThrowException_0
0x1800316f3  lea     r9, [rbp+470h+TempFileName]; lpTempFileName
0x1800316fa  xor     r8d, r8d; uUnique
0x1800316fd  lea     rdx, PrefixString; "evt"
0x180031704  mov     rcx, [rbp+470h+lpPathName]; lpPathName
0x180031708  call    cs:__imp_GetTempFileNameW
0x18003170e  test    eax, eax
0x180031710  jnz     loc_180031798
0x180031716  call    cs:__imp_GetLastError
0x18003171c  mov     edi, eax
0x18003171e  mov     eax, 507h
0x180031723  test    edi, edi
0x180031725  cmovz   edi, eax
0x180031728  lea     rax, WPP_GLOBAL_Control
0x18003172f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031736  cmp     rcx, rax
0x180031739  jz      short loc_180031764
0x18003173b  test    dword ptr [rcx+1Ch], 8000h
0x180031742  jz      short loc_180031764
0x180031744  mov     ebx, 2
0x180031749  cmp     [rcx+19h], bl
0x18003174c  jb      short loc_180031764
0x18003174e  lea     edx, [rbx+56h]
0x180031751  mov     r9d, edi
0x180031754  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18003175b  mov     rcx, [rcx+10h]
0x18003175f  call    WPP_SF_D
0x180031764  xorps   xmm0, xmm0
0x180031767  movdqu  [rsp+570h+pExceptionObject], xmm0
0x18003176d  mov     [rsp+570h+var_520], r15
0x180031772  mov     [rsp+570h+var_518], edi
0x180031776  mov     dword ptr [rsp+570h+var_514], 0FFFFFFFFh
0x18003177e  mov     dword ptr [rsp+570h+var_514+4], 8D7h
0x180031786  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003178d  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x180031792  call    _CxxThrowException_0
0x180031798  mov     [rsp+570h+hTemplateFile], r15; hTemplateFile
0x18003179d  mov     [rsp+570h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800317a2  mov     [rsp+570h+dwCreationDisposition], 4; dwCreationDisposition
0x1800317aa  xor     r9d, r9d; lpSecurityAttributes
0x1800317ad  mov     edx, 0C0000000h; dwDesiredAccess
0x1800317b2  lea     r8d, [r9+1]; dwShareMode
0x1800317b6  lea     rcx, [rbp+470h+TempFileName]; lpFileName
0x1800317bd  call    cs:__imp_CreateFileW
0x1800317c3  mov     r14, rax
0x1800317c6  mov     [rsp+570h+var_500], rax
0x1800317cb  lea     rcx, [rax+1]
0x1800317cf  cmp     rcx, 1
0x1800317d3  jbe     loc_180031BB2
0x1800317d9  mov     rdi, r15
0x1800317dc  mov     r8b, 1; bool
0x1800317df  lea     rcx, [rbp+470h+var_4D0]; this
0x1800317e3  call    ??0WriteFileView@@QEAA@K_N@Z; WriteFileView::WriteFileView(ulong,bool)
0x1800317e8  nop
0x1800317e9  mov     rbx, [r13+0]
0x1800317ed  cmp     rbx, r13
0x1800317f0  jz      loc_1800318FC
0x1800317f6  mov     r8, [rbx+10h]
0x1800317fa  shl     r8, 10h
0x1800317fe  add     r8, 1000h; unsigned __int64
0x180031805  mov     rdx, [rsi+2A0h]; void *
0x18003180c  lea     rcx, [rbp+470h+var_4C8]; this
0x180031810  call    ?ReadIn@FileView@@QEAAXPEAX_K@Z; FileView::ReadIn(void *,unsigned __int64)
0x180031815  cmp     [rbp+470h+arg_20], r15b
0x18003181c  jz      short loc_180031842
0x18003181e  mov     rcx, [rbp+470h+var_4C8]
0x180031822  mov     rax, [rcx+10h]
0x180031826  mov     rdx, [rcx+8]
0x18003182a  mov     [rcx+8], r12
0x18003182e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031832  jz      short loc_180031842
0x180031834  sub     rax, rdx
0x180031837  add     rax, r12
0x18003183a  mov     [rcx+10h], rax
0x18003183e  lea     r12, [rax+1]
0x180031842  lea     rcx, [rbp+470h+var_4D0]; this
0x180031846  call    ?UpdateBothCRCValues@WriteFileView@@QEAAXXZ; WriteFileView::UpdateBothCRCValues(void)
0x18003184b  mov     rax, rdi
0x18003184e  shl     rax, 10h
0x180031852  add     rax, 1000h
0x180031858  mov     [rbp+470h+var_4C0], rax
0x18003185c  mov     r9d, [rbp+470h+var_4A8]; unsigned int
0x180031860  xor     r8d, r8d; unsigned int
0x180031863  mov     rdx, r14; void *
0x180031866  lea     rcx, [rbp+470h+var_4C8]; this
0x18003186a  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x18003186f  mov     r15d, eax
0x180031872  test    eax, eax
0x180031874  jnz     short loc_180031884
0x180031876  inc     rdi
0x180031879  mov     rbx, [rbx]
0x18003187c  xor     r15d, r15d
0x18003187f  jmp     loc_1800317ED
0x180031884  lea     rax, WPP_GLOBAL_Control
0x18003188b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031892  cmp     rcx, rax
0x180031895  jz      short loc_1800318C0
0x180031897  test    dword ptr [rcx+1Ch], 8000h
0x18003189e  jz      short loc_1800318C0
0x1800318a0  mov     ebx, 2
0x1800318a5  cmp     [rcx+19h], bl
0x1800318a8  jb      short loc_1800318C0
0x1800318aa  lea     edx, [rbx+58h]
0x1800318ad  mov     r9d, r15d
0x1800318b0  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800318b7  mov     rcx, [rcx+10h]
0x1800318bb  call    WPP_SF_D
0x1800318c0  lea     rax, word_18004024A
0x1800318c7  mov     qword ptr [rsp+570h+pExceptionObject], rax
0x1800318cc  xor     eax, eax
0x1800318ce  mov     qword ptr [rsp+570h+pExceptionObject+8], rax
0x1800318d3  mov     [rsp+570h+var_520], rax
0x1800318d8  mov     [rsp+570h+var_518], r15d
0x1800318dd  mov     [rsp+570h+var_514], 0FFFFFFFFFFFFFFFFh
0x1800318e6  mov     [rsp+570h+var_50C], al
0x1800318ea  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800318f1  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x1800318f6  call    _CxxThrowException_0
0x1800318fc  cmp     [rbp+470h+arg_28], r15b
0x180031903  jz      short loc_180031915
0x180031905  mov     r8, rdi; unsigned __int64
0x180031908  mov     rdx, r12; unsigned __int64
0x18003190b  mov     rcx, r14; void *
0x18003190e  call    AddBlankChunk
0x180031913  jmp     short loc_180031918
0x180031915  dec     rdi
0x180031918  mov     ebx, 80h
0x18003191d  mov     r8d, ebx; Size
0x180031920  xor     edx, edx; Val
0x180031922  lea     rcx, [rbp+470h+var_2E0]; void *
0x180031929  call    memset_0
0x18003192e  mov     rax, qword ptr cs:aElffile; "ElfFile"
0x180031935  mov     [rbp+470h+var_2E0], rax
0x18003193c  mov     rax, [rsp+570h+var_508]
0x180031941  mov     [rbp+470h+var_2C8], rax
0x180031948  mov     [rbp+470h+var_2C0], ebx
0x18003194e  mov     [rbp+470h+var_2BC], 30002h
0x180031958  mov     ebx, 2
0x18003195d  lea     rcx, [rdi+1]; unsigned __int64
0x180031961  call    ?CalcFileSizeNeeded@@YA_K_K@Z; CalcFileSizeNeeded(unsigned __int64)
0x180031966  mov     [rbp+470h+var_2B8], rax
0x18003196d  mov     [rbp+470h+var_264], r15d
0x180031974  mov     [rbp+470h+var_2D0], rdi
0x18003197b  xor     r9d, r9d
0x18003197e  xor     r8d, r8d
0x180031981  lea     rdx, [rbp+470h+var_2E0]
0x180031988  mov     rcx, r14
0x18003198b  call    ?WriteFileHeader@File@@CAKPEAXPEAUFileHeader@@_N2W4FileModeFlags@@@Z; File::WriteFileHeader(void *,FileHeader *,bool,bool,FileModeFlags)
0x180031990  mov     edi, eax
0x180031992  test    eax, eax
0x180031994  jz      short loc_180031A0B
0x180031996  lea     rax, WPP_GLOBAL_Control
0x18003199d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319a4  cmp     rcx, rax
0x1800319a7  jz      short loc_1800319CD
0x1800319a9  test    dword ptr [rcx+1Ch], 8000h
0x1800319b0  jz      short loc_1800319CD
0x1800319b2  cmp     [rcx+19h], bl
0x1800319b5  jb      short loc_1800319CD
0x1800319b7  lea     edx, [rbx+59h]
0x1800319ba  mov     r9d, edi
0x1800319bd  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800319c4  mov     rcx, [rcx+10h]
0x1800319c8  call    WPP_SF_D
0x1800319cd  lea     rax, word_18004024A
0x1800319d4  mov     qword ptr [rsp+570h+pExceptionObject], rax
0x1800319d9  mov     qword ptr [rsp+570h+pExceptionObject+8], r15
0x1800319de  mov     [rsp+570h+var_520], 0
0x1800319e7  mov     [rsp+570h+var_518], edi
0x1800319eb  mov     [rsp+570h+var_514], 0FFFFFFFFFFFFFFFFh
0x1800319f4  mov     [rsp+570h+var_50C], r15b
0x1800319f9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180031a00  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x180031a05  call    _CxxThrowException_0
0x180031a0b  mov     rcx, r14; hFile
0x180031a0e  call    cs:__imp_FlushFileBuffers
0x180031a14  mov     rax, [rsi+2A0h]
0x180031a1b  mov     [rsi+2A0h], r15
0x180031a22  mov     [rsp+570h+var_508], rax
0x180031a27  lea     rcx, [rsp+570h+var_508]
0x180031a2c  call    CloseAndDelete
0x180031a31  mov     edi, eax
0x180031a33  test    eax, eax
0x180031a35  jz      short loc_180031AAE
0x180031a37  lea     rax, WPP_GLOBAL_Control
0x180031a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a45  cmp     rcx, rax
0x180031a48  jz      short loc_180031A70
0x180031a4a  test    dword ptr [rcx+1Ch], 8000h
0x180031a51  jz      short loc_180031A70
0x180031a53  cmp     [rcx+19h], bl
0x180031a56  jb      short loc_180031A70
0x180031a58  mov     edx, 5Ch ; '\'
0x180031a5d  mov     r9d, edi
0x180031a60  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180031a67  mov     rcx, [rcx+10h]
0x180031a6b  call    WPP_SF_D
0x180031a70  lea     rax, word_18004024A
0x180031a77  mov     qword ptr [rsp+570h+pExceptionObject], rax
0x180031a7c  mov     qword ptr [rsp+570h+pExceptionObject+8], r15
0x180031a81  mov     [rsp+570h+var_520], 0
0x180031a8a  mov     [rsp+570h+var_518], edi
0x180031a8e  mov     [rsp+570h+var_514], 0FFFFFFFFFFFFFFFFh
0x180031a97  mov     [rsp+570h+var_50C], r15b
0x180031a9c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180031aa3  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x180031aa8  call    _CxxThrowException_0
0x180031aae  mov     [rsi+33Dh], r15b
0x180031ab5  xor     edx, edx
0x180031ab7  lea     rcx, [rsp+570h+var_500]
0x180031abc  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180031ac1  mov     r8d, ebx; dwFlags
0x180031ac4  mov     rdx, [rsi+2A8h]; lpNewFileName
0x180031acb  lea     rcx, [rbp+470h+TempFileName]; lpExistingFileName
0x180031ad2  call    cs:__imp_MoveFileExW
0x180031ad8  test    eax, eax
0x180031ada  jnz     loc_180031B63
0x180031ae0  call    cs:__imp_GetLastError
0x180031ae6  mov     edi, eax
0x180031ae8  mov     eax, 507h
0x180031aed  test    edi, edi
0x180031aef  cmovz   edi, eax
0x180031af2  lea     rax, WPP_GLOBAL_Control
0x180031af9  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b00  cmp     rcx, rax
0x180031b03  jz      short loc_180031B2B
0x180031b05  test    dword ptr [rcx+1Ch], 8000h
0x180031b0c  jz      short loc_180031B2B
0x180031b0e  cmp     [rcx+19h], bl
0x180031b11  jb      short loc_180031B2B
0x180031b13  mov     edx, 5Dh ; ']'
0x180031b18  mov     r9d, edi
0x180031b1b  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180031b22  mov     rcx, [rcx+10h]
0x180031b26  call    WPP_SF_D
0x180031b2b  xorps   xmm0, xmm0
0x180031b2e  movdqu  [rsp+570h+pExceptionObject], xmm0
0x180031b34  mov     [rsp+570h+var_520], 0
0x180031b3d  mov     [rsp+570h+var_518], edi
0x180031b41  mov     dword ptr [rsp+570h+var_514], 0FFFFFFFFh
0x180031b49  mov     dword ptr [rsp+570h+var_514+4], 92Fh
  ... truncated ...
```
