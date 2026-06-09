# File::CreateNewVersion(utl::list<unsigned __int64,utl::allocator<unsigned __int64>> const &,unsigned __int64,unsigned __int64,bool,bool,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x1800b29b8`
- end: `0x1800b3037`
- name: `?CreateNewVersion@File@@AEAAXAEBV?$list@_KV?$allocator@_K@utl@@@utl@@_K1_N2AEAV?$unique_lock@Vshared_mutex@utl@@@3@@Z`
- size: `1663`
- prototype: `void __fastcall(File *this, _QWORD *, unsigned __int64, __int64, char, char, __int64)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, installer_update`

## callers

- `0x180040b48`
- `0x18007f4dc`

## callees

- `0x180009fa8`
- `0x18000a108`
- `0x18000a180`
- `0x180014bd0`
- `0x180017b60`
- `0x18002d204`
- `0x18003420c`
- `0x180048ffc`
- `0x18005ff90`
- `0x180064738`
- `0x18008a838`
- `0x18008d7a8`
- `0x180092008`
- `0x18009539c`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800b26bc`
- `0x1800b2780`
- `0x1800b29b8`
- `0x1800b3194`
- `0x1800b3998`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2fb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2fb4`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b2ed4`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b2ed4`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800b2ac8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800b2ac8`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800b2e10`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800b2e10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b2b7d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b2b7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall File::CreateNewVersion(
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
  unsigned __int64 v14; // rsi
  _QWORD *i; // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  unsigned int v20; // r15d
  unsigned int v21; // esi
  __int64 v22; // rax
  unsigned int v23; // esi
  DWORD v24; // edi
  DWORD v25; // edi
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
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
                           *v10,
                           (__int64)(v10[2] - *v10) >> 1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 14);
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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, LastError);
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
    v25 = GetLastError();
    if ( !v25 )
      v25 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v25);
    }
    pExceptionObject = 0;
    v28 = 0;
    v29 = v25;
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
    if ( !(unsigned __int8)AreAnyRestrictionsEnabled(1024) || (*((_BYTE *)this + 825) & 8) != 0 )
    {
      WriteFileView::UpdateBothCRCValues((WriteFileView *)v35);
    }
    else
    {
      *(_DWORD *)(v36[0] + 52LL) = 0;
      *(_DWORD *)(v36[0] + 124LL) = 0;
      *(_DWORD *)(v36[0] + 120LL) |= 4u;
    }
    v36[1] = (v14 << 16) + 4096;
    v20 = FileView::ActualWrite((FileView *)v36, FileW, 0, v37);
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v20);
      }
      *(_QWORD *)&pExceptionObject = &byte_1800EC961;
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
  LOBYTE(dwCreationDisposition) = *((_BYTE *)this + 825);
  v21 = File::WriteFileHeader(FileW, v38, 0, 0, dwCreationDisposition);
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v21);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v23);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v24);
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
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpPathName);
}

```

## disassembly

```asm
0x1800b29b8  push    rbp
0x1800b29ba  push    rbx
0x1800b29bb  push    rsi
0x1800b29bc  push    rdi
0x1800b29bd  push    r12
0x1800b29bf  push    r13
0x1800b29c1  push    r14
0x1800b29c3  push    r15
0x1800b29c5  lea     rbp, [rsp-438h]
0x1800b29cd  sub     rsp, 538h
0x1800b29d4  mov     rax, cs:__security_cookie
0x1800b29db  xor     rax, rsp
0x1800b29de  mov     [rbp+470h+var_50], rax
0x1800b29e5  mov     [rsp+570h+var_508], r9
0x1800b29ea  mov     r12, r8
0x1800b29ed  mov     r13, rdx
0x1800b29f0  mov     rdi, rcx
0x1800b29f3  mov     r15, [rbp+470h+arg_30]
0x1800b29fa  mov     [rsp+570h+var_4F8], r15
0x1800b29ff  lea     rcx, [rbp+470h+lpPathName]; void *
0x1800b2a03  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800b2a08  nop
0x1800b2a09  mov     rax, [rdi+2A8h]
0x1800b2a10  mov     [rsp+570h+var_500], rax
0x1800b2a15  lea     rdx, [rsp+570h+var_500]
0x1800b2a1a  lea     rcx, [rsp+570h+pExceptionObject]
0x1800b2a1f  call    ??$?0PEB_W_W@?$split_path@_W@tlx@@QEAA@AEBQEB_W@Z; tlx::split_path<wchar_t>::split_path<wchar_t>(wchar_t const * const &)
0x1800b2a24  mov     r8, [rax+10h]
0x1800b2a28  sub     r8, [rax]
0x1800b2a2b  sar     r8, 1
0x1800b2a2e  mov     rdx, [rax]
0x1800b2a31  lea     rcx, [rbp+470h+lpPathName]
0x1800b2a35  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800b2a3a  xor     r15d, r15d
0x1800b2a3d  test    al, al
0x1800b2a3f  jnz     short loc_1800B2AB3
0x1800b2a41  lea     rax, WPP_GLOBAL_Control
0x1800b2a48  lea     edi, [r15+0Eh]
0x1800b2a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2a53  cmp     rcx, rax
0x1800b2a56  jz      short loc_1800B2A7F
0x1800b2a58  test    dword ptr [rcx+1Ch], 8000h
0x1800b2a5f  jz      short loc_1800B2A7F
0x1800b2a61  lea     ebx, [rdi-0Ch]
0x1800b2a64  cmp     [rcx+19h], bl
0x1800b2a67  jb      short loc_1800B2A7F
0x1800b2a69  lea     edx, [rdi+49h]
0x1800b2a6c  mov     r9d, edi
0x1800b2a6f  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b2a76  mov     rcx, [rcx+10h]
0x1800b2a7a  call    WPP_SF_d
0x1800b2a7f  xorps   xmm0, xmm0
0x1800b2a82  movdqu  [rsp+570h+pExceptionObject], xmm0
0x1800b2a88  mov     [rsp+570h+var_520], r15
0x1800b2a8d  mov     [rsp+570h+var_518], edi
0x1800b2a91  mov     dword ptr [rsp+570h+var_514], 0FFFFFFFFh
0x1800b2a99  mov     dword ptr [rsp+570h+var_514+4], 8D1h
0x1800b2aa1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b2aa8  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x1800b2aad  call    _CxxThrowException_0
0x1800b2ab3  lea     r9, [rbp+470h+TempFileName]; lpTempFileName
0x1800b2aba  xor     r8d, r8d; uUnique
0x1800b2abd  lea     rdx, aEvt_0; "evt"
0x1800b2ac4  mov     rcx, [rbp+470h+lpPathName]; lpPathName
0x1800b2ac8  call    cs:__imp_GetTempFileNameW
0x1800b2ace  test    eax, eax
0x1800b2ad0  jnz     loc_1800B2B58
0x1800b2ad6  call    cs:__imp_GetLastError
0x1800b2adc  mov     edi, eax
0x1800b2ade  mov     eax, 507h
0x1800b2ae3  test    edi, edi
0x1800b2ae5  cmovz   edi, eax
0x1800b2ae8  lea     rax, WPP_GLOBAL_Control
0x1800b2aef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2af6  cmp     rcx, rax
0x1800b2af9  jz      short loc_1800B2B24
0x1800b2afb  test    dword ptr [rcx+1Ch], 8000h
0x1800b2b02  jz      short loc_1800B2B24
0x1800b2b04  mov     ebx, 2
0x1800b2b09  cmp     [rcx+19h], bl
0x1800b2b0c  jb      short loc_1800B2B24
0x1800b2b0e  lea     edx, [rbx+56h]
0x1800b2b11  mov     r9d, edi
0x1800b2b14  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b2b1b  mov     rcx, [rcx+10h]
0x1800b2b1f  call    WPP_SF_d
0x1800b2b24  xorps   xmm0, xmm0
0x1800b2b27  movdqu  [rsp+570h+pExceptionObject], xmm0
0x1800b2b2d  mov     [rsp+570h+var_520], r15
0x1800b2b32  mov     [rsp+570h+var_518], edi
0x1800b2b36  mov     dword ptr [rsp+570h+var_514], 0FFFFFFFFh
0x1800b2b3e  mov     dword ptr [rsp+570h+var_514+4], 8D7h
0x1800b2b46  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b2b4d  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x1800b2b52  call    _CxxThrowException_0
0x1800b2b58  mov     [rsp+570h+hTemplateFile], r15; hTemplateFile
0x1800b2b5d  mov     [rsp+570h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800b2b62  mov     [rsp+570h+dwCreationDisposition], 4; dwCreationDisposition
0x1800b2b6a  xor     r9d, r9d; lpSecurityAttributes
0x1800b2b6d  mov     edx, 0C0000000h; dwDesiredAccess
0x1800b2b72  lea     r8d, [r9+1]; dwShareMode
0x1800b2b76  lea     rcx, [rbp+470h+TempFileName]; lpFileName
0x1800b2b7d  call    cs:__imp_CreateFileW
0x1800b2b83  mov     r14, rax
0x1800b2b86  mov     [rsp+570h+var_500], rax
0x1800b2b8b  lea     rcx, [rax+1]
0x1800b2b8f  cmp     rcx, 1
0x1800b2b93  jbe     loc_1800B2FB4
0x1800b2b99  mov     rsi, r15
0x1800b2b9c  mov     r8b, 1; bool
0x1800b2b9f  lea     rcx, [rbp+470h+var_4D0]; this
0x1800b2ba3  call    ??0WriteFileView@@QEAA@K_N@Z; WriteFileView::WriteFileView(ulong,bool)
0x1800b2ba8  nop
0x1800b2ba9  mov     rbx, [r13+0]
0x1800b2bad  cmp     rbx, r13
0x1800b2bb0  jz      loc_1800B2CED
0x1800b2bb6  mov     r8, [rbx+10h]
0x1800b2bba  shl     r8, 10h
0x1800b2bbe  add     r8, 1000h; unsigned __int64
0x1800b2bc5  mov     rdx, [rdi+2A0h]; void *
0x1800b2bcc  lea     rcx, [rbp+470h+var_4C8]; this
0x1800b2bd0  call    ?ReadIn@FileView@@QEAAXPEAX_K@Z; FileView::ReadIn(void *,unsigned __int64)
0x1800b2bd5  cmp     [rbp+470h+arg_20], r15b
0x1800b2bdc  jz      short loc_1800B2C02
0x1800b2bde  mov     rcx, [rbp+470h+var_4C8]
0x1800b2be2  mov     rax, [rcx+10h]
0x1800b2be6  mov     rdx, [rcx+8]
0x1800b2bea  mov     [rcx+8], r12
0x1800b2bee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b2bf2  jz      short loc_1800B2C02
0x1800b2bf4  sub     rax, rdx
0x1800b2bf7  add     rax, r12
0x1800b2bfa  mov     [rcx+10h], rax
0x1800b2bfe  lea     r12, [rax+1]
0x1800b2c02  mov     ecx, 400h
0x1800b2c07  call    ?AreAnyRestrictionsEnabled@@YA_NW4FeatureRestrictions@@@Z; AreAnyRestrictionsEnabled(FeatureRestrictions)
0x1800b2c0c  test    al, al
0x1800b2c0e  jz      short loc_1800B2C33
0x1800b2c10  test    byte ptr [rdi+339h], 8
0x1800b2c17  jnz     short loc_1800B2C33
0x1800b2c19  mov     rax, [rbp+470h+var_4C8]
0x1800b2c1d  mov     [rax+34h], r15d
0x1800b2c21  mov     rax, [rbp+470h+var_4C8]
0x1800b2c25  mov     [rax+7Ch], r15d
0x1800b2c29  mov     rax, [rbp+470h+var_4C8]
0x1800b2c2d  or      dword ptr [rax+78h], 4
0x1800b2c31  jmp     short loc_1800B2C3C
0x1800b2c33  lea     rcx, [rbp+470h+var_4D0]; this
0x1800b2c37  call    ?UpdateBothCRCValues@WriteFileView@@QEAAXXZ; WriteFileView::UpdateBothCRCValues(void)
0x1800b2c3c  mov     rax, rsi
0x1800b2c3f  shl     rax, 10h
0x1800b2c43  add     rax, 1000h
0x1800b2c49  mov     [rbp+470h+var_4C0], rax
0x1800b2c4d  mov     r9d, [rbp+470h+var_4A8]; unsigned int
0x1800b2c51  xor     r8d, r8d; unsigned int
0x1800b2c54  mov     rdx, r14; void *
0x1800b2c57  lea     rcx, [rbp+470h+var_4C8]; this
0x1800b2c5b  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x1800b2c60  mov     r15d, eax
0x1800b2c63  test    eax, eax
0x1800b2c65  jnz     short loc_1800B2C75
0x1800b2c67  inc     rsi
0x1800b2c6a  mov     rbx, [rbx]
0x1800b2c6d  xor     r15d, r15d
0x1800b2c70  jmp     loc_1800B2BAD
0x1800b2c75  lea     rax, WPP_GLOBAL_Control
0x1800b2c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2c83  cmp     rcx, rax
0x1800b2c86  jz      short loc_1800B2CB1
0x1800b2c88  test    dword ptr [rcx+1Ch], 8000h
0x1800b2c8f  jz      short loc_1800B2CB1
0x1800b2c91  mov     ebx, 2
0x1800b2c96  cmp     [rcx+19h], bl
0x1800b2c99  jb      short loc_1800B2CB1
0x1800b2c9b  lea     edx, [rbx+58h]
0x1800b2c9e  mov     r9d, r15d
0x1800b2ca1  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b2ca8  mov     rcx, [rcx+10h]
0x1800b2cac  call    WPP_SF_d
0x1800b2cb1  lea     rax, byte_1800EC961
0x1800b2cb8  mov     qword ptr [rsp+570h+pExceptionObject], rax
0x1800b2cbd  xor     eax, eax
0x1800b2cbf  mov     qword ptr [rsp+570h+pExceptionObject+8], rax
0x1800b2cc4  mov     [rsp+570h+var_520], rax
0x1800b2cc9  mov     [rsp+570h+var_518], r15d
0x1800b2cce  mov     [rsp+570h+var_514], 0FFFFFFFFFFFFFFFFh
0x1800b2cd7  mov     [rsp+570h+var_50C], al
0x1800b2cdb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b2ce2  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x1800b2ce7  call    _CxxThrowException_0
0x1800b2ced  cmp     [rbp+470h+arg_28], r15b
0x1800b2cf4  jz      short loc_1800B2D0D
0x1800b2cf6  mov     r9b, [rdi+339h]
0x1800b2cfd  mov     r8, rsi; unsigned __int64
0x1800b2d00  mov     rdx, r12; unsigned __int64
0x1800b2d03  mov     rcx, r14; void *
0x1800b2d06  call    AddBlankChunk
0x1800b2d0b  jmp     short loc_1800B2D10
0x1800b2d0d  dec     rsi
0x1800b2d10  mov     ebx, 80h
0x1800b2d15  mov     r8d, ebx; Size
0x1800b2d18  xor     edx, edx; Val
0x1800b2d1a  lea     rcx, [rbp+470h+var_2E0]; void *
0x1800b2d21  call    memset_0
0x1800b2d26  mov     rax, qword ptr cs:aElffile; "ElfFile"
0x1800b2d2d  mov     [rbp+470h+var_2E0], rax
0x1800b2d34  mov     rax, [rsp+570h+var_508]
0x1800b2d39  mov     [rbp+470h+var_2C8], rax
0x1800b2d40  mov     [rbp+470h+var_2C0], ebx
0x1800b2d46  mov     [rbp+470h+var_2BC], 30002h
0x1800b2d50  mov     ebx, 2
0x1800b2d55  lea     rcx, [rsi+1]; unsigned __int64
0x1800b2d59  call    ?CalcFileSizeNeeded@@YA_K_K@Z; CalcFileSizeNeeded(unsigned __int64)
0x1800b2d5e  mov     [rbp+470h+var_2B8], rax
0x1800b2d65  mov     [rbp+470h+var_264], r15d
0x1800b2d6c  mov     [rbp+470h+var_2D0], rsi
0x1800b2d73  mov     al, [rdi+339h]
0x1800b2d79  mov     byte ptr [rsp+570h+dwCreationDisposition], al
0x1800b2d7d  xor     r9d, r9d
0x1800b2d80  xor     r8d, r8d
0x1800b2d83  lea     rdx, [rbp+470h+var_2E0]
0x1800b2d8a  mov     rcx, r14
0x1800b2d8d  call    ?WriteFileHeader@File@@CAKPEAXPEAUFileHeader@@_N2W4FileModeFlags@@@Z; File::WriteFileHeader(void *,FileHeader *,bool,bool,FileModeFlags)
0x1800b2d92  mov     esi, eax
0x1800b2d94  test    eax, eax
0x1800b2d96  jz      short loc_1800B2E0D
0x1800b2d98  lea     rax, WPP_GLOBAL_Control
0x1800b2d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2da6  cmp     rcx, rax
0x1800b2da9  jz      short loc_1800B2DCF
0x1800b2dab  test    dword ptr [rcx+1Ch], 8000h
0x1800b2db2  jz      short loc_1800B2DCF
0x1800b2db4  cmp     [rcx+19h], bl
0x1800b2db7  jb      short loc_1800B2DCF
0x1800b2db9  lea     edx, [rbx+59h]
0x1800b2dbc  mov     r9d, esi
0x1800b2dbf  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b2dc6  mov     rcx, [rcx+10h]
0x1800b2dca  call    WPP_SF_d
0x1800b2dcf  lea     rax, byte_1800EC961
0x1800b2dd6  mov     qword ptr [rsp+570h+pExceptionObject], rax
0x1800b2ddb  mov     qword ptr [rsp+570h+pExceptionObject+8], r15
0x1800b2de0  mov     [rsp+570h+var_520], 0
0x1800b2de9  mov     [rsp+570h+var_518], esi
0x1800b2ded  mov     [rsp+570h+var_514], 0FFFFFFFFFFFFFFFFh
0x1800b2df6  mov     [rsp+570h+var_50C], r15b
0x1800b2dfb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b2e02  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x1800b2e07  call    _CxxThrowException_0
0x1800b2e0d  mov     rcx, r14; hFile
0x1800b2e10  call    cs:__imp_FlushFileBuffers
0x1800b2e16  mov     rax, [rdi+2A0h]
0x1800b2e1d  mov     [rdi+2A0h], r15
0x1800b2e24  mov     [rsp+570h+var_508], rax
0x1800b2e29  lea     rcx, [rsp+570h+var_508]
0x1800b2e2e  call    CloseAndDelete
0x1800b2e33  mov     esi, eax
0x1800b2e35  test    eax, eax
0x1800b2e37  jz      short loc_1800B2EB0
0x1800b2e39  lea     rax, WPP_GLOBAL_Control
0x1800b2e40  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2e47  cmp     rcx, rax
0x1800b2e4a  jz      short loc_1800B2E72
0x1800b2e4c  test    dword ptr [rcx+1Ch], 8000h
0x1800b2e53  jz      short loc_1800B2E72
0x1800b2e55  cmp     [rcx+19h], bl
0x1800b2e58  jb      short loc_1800B2E72
0x1800b2e5a  mov     edx, 5Ch ; '\'
0x1800b2e5f  mov     r9d, esi
0x1800b2e62  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b2e69  mov     rcx, [rcx+10h]
0x1800b2e6d  call    WPP_SF_d
0x1800b2e72  lea     rax, byte_1800EC961
0x1800b2e79  mov     qword ptr [rsp+570h+pExceptionObject], rax
0x1800b2e7e  mov     qword ptr [rsp+570h+pExceptionObject+8], r15
0x1800b2e83  mov     [rsp+570h+var_520], 0
0x1800b2e8c  mov     [rsp+570h+var_518], esi
0x1800b2e90  mov     [rsp+570h+var_514], 0FFFFFFFFFFFFFFFFh
0x1800b2e99  mov     [rsp+570h+var_50C], r15b
0x1800b2e9e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b2ea5  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x1800b2eaa  call    _CxxThrowException_0
0x1800b2eb0  mov     [rdi+33Dh], r15b
0x1800b2eb7  xor     edx, edx
0x1800b2eb9  lea     rcx, [rsp+570h+var_500]
0x1800b2ebe  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800b2ec3  mov     r8d, ebx; dwFlags
0x1800b2ec6  mov     rdx, [rdi+2A8h]; lpNewFileName
0x1800b2ecd  lea     rcx, [rbp+470h+TempFileName]; lpExistingFileName
0x1800b2ed4  call    cs:__imp_MoveFileExW
0x1800b2eda  test    eax, eax
0x1800b2edc  jnz     loc_1800B2F65
0x1800b2ee2  call    cs:__imp_GetLastError
0x1800b2ee8  mov     edi, eax
0x1800b2eea  mov     eax, 507h
0x1800b2eef  test    edi, edi
0x1800b2ef1  cmovz   edi, eax
0x1800b2ef4  lea     rax, WPP_GLOBAL_Control
0x1800b2efb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2f02  cmp     rcx, rax
  ... truncated ...
```
