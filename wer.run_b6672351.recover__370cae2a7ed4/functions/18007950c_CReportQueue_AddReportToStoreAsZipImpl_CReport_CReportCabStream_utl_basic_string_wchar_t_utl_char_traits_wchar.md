# CReportQueue::AddReportToStoreAsZipImpl(CReport *,CReportCabStream *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18007950c`
- end: `0x1800799fb`
- name: `?AddReportToStoreAsZipImpl@CReportQueue@@AEAAJPEAVCReport@@PEAVCReportCabStream@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1263`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x180047220`

## callees

- `0x1800062bc`
- `0x180007f74`
- `0x180007fa0`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x18000e31c`
- `0x180025560`
- `0x18003be90`
- `0x18003fb94`
- `0x180040814`
- `0x1800479ac`
- `0x18004dfbc`
- `0x180051144`
- `0x1800768f8`
- `0x18007756c`
- `0x1800794b8`
- `0x18007950c`
- `0x180079cf0`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798b8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800798d8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800798d8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800797e8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800797e8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800798a8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800798a8`

## string_xrefs

- `0x180079549`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800795c9`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180079607`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180079699`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180079708`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800797be`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x18007985b`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180079901`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CReportQueue::AddReportToStoreAsZipImpl(__int64 a1, CReport *a2, _DWORD *a3, __int64 a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // esi
  int UniqueIdentifier; // eax
  int v13; // eax
  const wchar_t *v14; // rax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  unsigned __int64 v20; // r9
  int v21; // r8d
  int v22; // eax
  int v23; // r8d
  __int64 v24; // rdx
  DWORD LastError; // ebx
  unsigned int v26; // r8d
  const char *v27; // r9
  int v29; // [rsp+28h] [rbp-E0h]
  int v30; // [rsp+28h] [rbp-E0h]
  unsigned int v31; // [rsp+28h] [rbp-E0h]
  wchar_t *v32[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v33[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-A0h]
  wchar_t *v35[4]; // [rsp+70h] [rbp-98h] BYREF
  LPCWSTR v36[4]; // [rsp+90h] [rbp-78h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+B0h] [rbp-58h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+D0h] [rbp-38h] BYREF
  wchar_t *v39[5]; // [rsp+F0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+38h]
  CReport *v41; // [rsp+150h] [rbp+48h] BYREF

  v41 = a2;
  if ( a2 )
  {
    if ( !a3 )
    {
      v7 = 350;
      goto LABEL_3;
    }
    *((_DWORD *)a2 + 1656) = 9;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v39);
    v32[0] = 0;
    if ( (unsigned int)CReport::GetStorePath(v41, (const wchar_t **)v32) != -2147467259 && v32[0] && *v32[0] )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v39,
                               v32[0]) )
      {
        v8 = -2147024882;
        v9 = 2147942414LL;
        v10 = 368;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
          (const char *)v9,
          v29);
LABEL_57:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v39);
        return v8;
      }
      v11 = 1;
    }
    else
    {
      v11 = 0;
      v13 = CReportStore::ReserveReportDirInStore(a1, v41, v39);
      v8 = v13;
      if ( v13 < 0 )
      {
        v9 = (unsigned int)v13;
        v10 = 364;
        goto LABEL_11;
      }
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36);
    UniqueIdentifier = CReport::GetUniqueIdentifier(v41, v36);
    v8 = UniqueIdentifier;
    if ( UniqueIdentifier < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)UniqueIdentifier,
        v29);
LABEL_15:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v36);
      goto LABEL_57;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
    v14 = L"zip";
    if ( !a3[4] )
      v14 = L"cab";
    v15 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v35,
            L"%s\\%s.%s",
            v39[0],
            v36[0],
            v14);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)v15,
        v30);
LABEL_22:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
      goto LABEL_15;
    }
    v32[0] = (wchar_t *)&CFileByteStream::`vftable';
    v32[1] = 0;
    v16 = CFileByteStream::OpenFile((CFileByteStream *)v32, v35[0], 0x40000000u, 0, 0, 1u, 0x80u, 0);
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 402;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)v16,
        v31);
      CFileByteStream::~CFileByteStream((CFileByteStream *)v32);
      goto LABEL_22;
    }
    v16 = (*(__int64 (__fastcall **)(_DWORD *, wchar_t **, _QWORD))(*(_QWORD *)a3 + 24LL))(a3, v32, 0);
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 404;
      goto LABEL_25;
    }
    CFileByteStream::Close((CFileByteStream *)v32);
    CFileByteStream::~CFileByteStream((CFileByteStream *)v32);
    v33[0] = v35;
    v33[1] = &v41;
    LOBYTE(v34) = 1;
    *((_DWORD *)v41 + 1637) = 1;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
    v18 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            lpFileName,
            L"%s\\%s",
            v39[0],
            L"Report.wer");
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 421;
LABEL_30:
      v20 = (unsigned int)v18;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)v20,
        v31);
LABEL_32:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
      tlx::_UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___::__UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___(v33);
      goto LABEL_22;
    }
    if ( GetFileAttributesW(lpFileName[0]) == -1 )
    {
      v8 = CReport::WriteReportToFile(v41, lpFileName[0], v21, 0);
      if ( (v8 & 0x80000000) != 0 )
      {
        *((_DWORD *)v41 + 1656) = 15;
        v20 = v8;
        v19 = 434;
        goto LABEL_31;
      }
      goto LABEL_49;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpExistingFileName);
    v22 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            lpExistingFileName,
            L"%s\\%s",
            v39[0],
            L"Report.wer.tmp");
    v8 = v22;
    if ( v22 >= 0 )
    {
      v22 = CReport::WriteReportToFile(v41, lpExistingFileName[0], v23, 0);
      v8 = v22;
      if ( v22 >= 0 )
      {
        if ( MoveFileExW(lpExistingFileName[0], lpFileName[0], 1u) )
        {
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
LABEL_49:
          LOBYTE(v34) = 0;
          if ( v11 )
          {
            v18 = UtilRecursiveRemoveDirectory(v39[0], 0, v35[0], lpFileName[0], v31);
            v8 = v18;
            if ( v18 )
            {
              if ( v18 != -2147024751 )
              {
                if ( v18 >= 0 )
                  goto LABEL_32;
                v19 = 467;
                goto LABEL_30;
              }
            }
          }
          *((_DWORD *)v41 + 11636) = *(_DWORD *)(a1 + 8);
          CReport::SetStorePath(v41, v39[0]);
          *((_DWORD *)v41 + 1656) = 14;
          if ( a4 )
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a4, v39);
LABEL_56:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
          tlx::_UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___::__UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___(v33);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v36);
          v8 = 0;
          goto LABEL_57;
        }
        LastError = GetLastError();
        *((_DWORD *)v41 + 1656) = 15;
        if ( !DeleteFileW(lpExistingFileName[0]) )
          wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x1C1, v26, v27);
        if ( !LastError )
        {
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
          goto LABEL_56;
        }
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1C3,
               (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
               (const char *)LastError,
               v31);
LABEL_39:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
        goto LABEL_32;
      }
      v24 = 442;
    }
    else
    {
      v24 = 440;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
      (const char *)(unsigned int)v22,
      v31);
    goto LABEL_39;
  }
  v7 = 349;
LABEL_3:
  v8 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
    (const char *)0x80070057LL,
    v29);
  return v8;
}

```

## disassembly

```asm
0x18007950c  mov     rax, rsp
0x18007950f  mov     [rax+8], rbx
0x180079513  mov     [rax+18h], rsi
0x180079517  mov     [rax+10h], rdx
0x18007951b  push    rbp
0x18007951c  push    rdi
0x18007951d  push    r12
0x18007951f  push    r14
0x180079521  push    r15
0x180079523  lea     rbp, [rax-38h]
0x180079527  sub     rsp, 110h
0x18007952e  mov     r14, r9
0x180079531  mov     rdi, r8
0x180079534  mov     r15, rcx
0x180079537  xor     r12d, r12d
0x18007953a  test    rdx, rdx
0x18007953d  jnz     short loc_180079561
0x18007953f  mov     edx, 15Dh; void *
0x180079544  mov     ebx, 80070057h
0x180079549  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180079550  mov     r9d, ebx; char *
0x180079553  mov     rcx, [rbp+38h]; this
0x180079557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007955c  jmp     loc_1800799DC
0x180079561  test    rdi, rdi
0x180079564  jnz     short loc_18007956D
0x180079566  mov     edx, 15Eh
0x18007956b  jmp     short loc_180079544
0x18007956d  mov     dword ptr [rdx+19E0h], 9
0x180079577  lea     rcx, [rbp+30h+var_48]; void *
0x18007957b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180079580  nop
0x180079581  mov     [rsp+130h+var_F0], r12
0x180079586  lea     rdx, [rsp+130h+var_F0]; wchar_t **
0x18007958b  mov     rcx, [rbp+30h+arg_8]; this
0x18007958f  call    ?GetStorePath@CReport@@QEAAJPEAPEB_W@Z; CReport::GetStorePath(wchar_t const * *)
0x180079594  cmp     eax, 80004005h
0x180079599  jz      loc_180079627
0x18007959f  mov     rdx, [rsp+130h+var_F0]
0x1800795a4  test    rdx, rdx
0x1800795a7  jz      short loc_180079627
0x1800795a9  cmp     [rdx], r12w
0x1800795ad  jz      short loc_180079627
0x1800795af  lea     rcx, [rbp+30h+var_48]
0x1800795b3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800795b8  test    al, al
0x1800795ba  jnz     short loc_1800795DE
0x1800795bc  mov     ebx, 8007000Eh
0x1800795c1  mov     r9d, ebx; char *
0x1800795c4  mov     edx, 170h; void *
0x1800795c9  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800795d0  mov     rcx, [rbp+38h]; this
0x1800795d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800795d9  jmp     loc_1800799D3
0x1800795de  mov     esi, 1
0x1800795e3  lea     rcx, [rbp+30h+var_A8]; void *
0x1800795e7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800795ec  nop
0x1800795ed  lea     rdx, [rbp+30h+var_A8]
0x1800795f1  mov     rcx, [rbp+30h+arg_8]
0x1800795f5  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800795fa  mov     ebx, eax
0x1800795fc  test    eax, eax
0x1800795fe  jns     short loc_18007964D
0x180079600  mov     rcx, [rbp+38h]; this
0x180079604  mov     r9d, eax; char *
0x180079607  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007960e  mov     edx, 17Dh; void *
0x180079613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079618  nop
0x180079619  lea     rcx, [rbp+30h+var_A8]; void *
0x18007961d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180079622  jmp     loc_1800799D3
0x180079627  mov     esi, r12d
0x18007962a  lea     r8, [rbp+30h+var_48]
0x18007962e  mov     rdx, [rbp+30h+arg_8]
0x180079632  mov     rcx, r15
0x180079635  call    ?ReserveReportDirInStore@CReportStore@@QEAAJPEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::ReserveReportDirInStore(CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18007963a  mov     ebx, eax
0x18007963c  test    eax, eax
0x18007963e  jns     short loc_1800795E3
0x180079640  mov     r9d, eax
0x180079643  mov     edx, 16Ch
0x180079648  jmp     loc_1800795C9
0x18007964d  lea     rcx, [rsp+130h+var_C8]; void *
0x180079652  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180079657  nop
0x180079658  lea     rcx, aCab_1; "cab"
0x18007965f  lea     rax, aZip_0; "zip"
0x180079666  cmp     [rdi+10h], r12d
0x18007966a  cmovz   rax, rcx
0x18007966e  mov     [rsp+130h+var_110], rax; int
0x180079673  mov     r9, [rbp+30h+var_A8]
0x180079677  mov     r8, [rbp+30h+var_48]
0x18007967b  lea     rdx, aSSS_0; "%s\\%s.%s"
0x180079682  lea     rcx, [rsp+130h+var_C8]
0x180079687  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007968c  mov     ebx, eax
0x18007968e  test    eax, eax
0x180079690  jns     short loc_1800796BA
0x180079692  mov     rcx, [rbp+38h]; this
0x180079696  mov     r9d, eax; char *
0x180079699  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800796a0  mov     edx, 184h; void *
0x1800796a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800796aa  nop
0x1800796ab  lea     rcx, [rsp+130h+var_C8]; void *
0x1800796b0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800796b5  jmp     loc_180079619
0x1800796ba  lea     rax, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x1800796c1  mov     [rsp+130h+var_F0], rax
0x1800796c6  mov     [rsp+130h+var_E8], r12
0x1800796cb  mov     [rsp+130h+var_F8], r12; void *
0x1800796d0  mov     [rsp+130h+var_100], 80h; unsigned int
0x1800796d8  mov     [rsp+130h+var_108], 1; unsigned int
0x1800796e0  mov     [rsp+130h+var_110], r12; int
0x1800796e5  xor     r9d, r9d; unsigned int
0x1800796e8  mov     r8d, 40000000h; unsigned int
0x1800796ee  mov     rdx, [rsp+130h+var_C8]; wchar_t *
0x1800796f3  lea     rcx, [rsp+130h+var_F0]; this
0x1800796f8  call    ?OpenFile@CFileByteStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CFileByteStream::OpenFile(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x1800796fd  mov     ebx, eax
0x1800796ff  test    eax, eax
0x180079701  jns     short loc_180079728
0x180079703  mov     edx, 192h; void *
0x180079708  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007970f  mov     r9d, eax; char *
0x180079712  mov     rcx, [rbp+38h]; this
0x180079716  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007971b  nop
0x18007971c  lea     rcx, [rsp+130h+var_F0]; this
0x180079721  call    ??1CFileByteStream@@UEAA@XZ; CFileByteStream::~CFileByteStream(void)
0x180079726  jmp     short loc_1800796AB
0x180079728  mov     rax, [rdi]
0x18007972b  xor     r8d, r8d
0x18007972e  lea     rdx, [rsp+130h+var_F0]
0x180079733  mov     rcx, rdi
0x180079736  mov     rax, [rax+18h]
0x18007973a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007973f  mov     ebx, eax
0x180079741  test    eax, eax
0x180079743  jns     short loc_18007974C
0x180079745  mov     edx, 194h
0x18007974a  jmp     short loc_180079708
0x18007974c  lea     rcx, [rsp+130h+var_F0]; this
0x180079751  call    ?Close@CFileByteStream@@UEAAXXZ; CFileByteStream::Close(void)
0x180079756  nop
0x180079757  lea     rcx, [rsp+130h+var_F0]; this
0x18007975c  call    ??1CFileByteStream@@UEAA@XZ; CFileByteStream::~CFileByteStream(void)
0x180079761  lea     rax, [rsp+130h+var_C8]
0x180079766  mov     [rsp+130h+var_E0], rax
0x18007976b  lea     rax, [rbp+30h+arg_8]
0x18007976f  mov     qword ptr [rsp+130h+var_D8], rax
0x180079774  mov     byte ptr [rsp+130h+var_D0], 1
0x180079779  mov     rax, [rbp+30h+arg_8]
0x18007977d  mov     dword ptr [rax+1994h], 1
0x180079787  lea     rcx, [rbp+30h+lpFileName]; void *
0x18007978b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180079790  nop
0x180079791  lea     r9, aReportWer; "Report.wer"
0x180079798  mov     r8, [rbp+30h+var_48]
0x18007979c  lea     rdx, aSS; "%s\\%s"
0x1800797a3  lea     rcx, [rbp+30h+lpFileName]
0x1800797a7  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800797ac  mov     ebx, eax
0x1800797ae  test    eax, eax
0x1800797b0  jns     short loc_1800797E4
0x1800797b2  mov     edx, 1A5h; void *
0x1800797b7  mov     r9d, eax; char *
0x1800797ba  mov     rcx, [rbp+38h]; this
0x1800797be  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800797c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800797ca  nop
0x1800797cb  lea     rcx, [rbp+30h+lpFileName]; void *
0x1800797cf  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800797d4  nop
0x1800797d5  lea     rcx, [rsp+130h+var_E0]
0x1800797da  call    tlx___UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf_______UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___
0x1800797df  jmp     loc_1800796AB
0x1800797e4  mov     rcx, [rbp+30h+lpFileName]; lpFileName
0x1800797e8  call    cs:__imp_GetFileAttributesW
0x1800797ef  nop     dword ptr [rax+rax+00h]
0x1800797f4  cmp     eax, 0FFFFFFFFh
0x1800797f7  jnz     short loc_18007982B
0x1800797f9  xor     r9d, r9d; unsigned int
0x1800797fc  mov     rdx, [rbp+30h+lpFileName]; wchar_t *
0x180079800  mov     rcx, [rbp+30h+arg_8]; this
0x180079804  call    ?WriteReportToFile@CReport@@QEAAJPEB_WHK@Z; CReport::WriteReportToFile(wchar_t const *,int,ulong)
0x180079809  mov     ebx, eax
0x18007980b  test    eax, eax
0x18007980d  jns     loc_180079930
0x180079813  mov     rax, [rbp+30h+arg_8]
0x180079817  mov     dword ptr [rax+19E0h], 0Fh
0x180079821  mov     r9d, ebx
0x180079824  mov     edx, 1B2h
0x180079829  jmp     short loc_1800797BA
0x18007982b  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x18007982f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180079834  nop
0x180079835  lea     r9, aReportWerTmp; "Report.wer.tmp"
0x18007983c  mov     r8, [rbp+30h+var_48]
0x180079840  lea     rdx, aSS; "%s\\%s"
0x180079847  lea     rcx, [rbp+30h+lpExistingFileName]
0x18007984b  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180079850  mov     ebx, eax
0x180079852  test    eax, eax
0x180079854  jns     short loc_18007987D
0x180079856  mov     edx, 1B8h; void *
0x18007985b  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180079862  mov     r9d, eax; char *
0x180079865  mov     rcx, [rbp+38h]; this
0x180079869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007986e  nop
0x18007986f  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x180079873  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180079878  jmp     loc_1800797CB
0x18007987d  xor     r9d, r9d; unsigned int
0x180079880  mov     rdx, [rbp+30h+lpExistingFileName]; wchar_t *
0x180079884  mov     rcx, [rbp+30h+arg_8]; this
0x180079888  call    ?WriteReportToFile@CReport@@QEAAJPEB_WHK@Z; CReport::WriteReportToFile(wchar_t const *,int,ulong)
0x18007988d  mov     ebx, eax
0x18007988f  test    eax, eax
0x180079891  jns     short loc_18007989A
0x180079893  mov     edx, 1BAh
0x180079898  jmp     short loc_18007985B
0x18007989a  mov     r8d, 1; dwFlags
0x1800798a0  mov     rdx, [rbp+30h+lpFileName]; lpNewFileName
0x1800798a4  mov     rcx, [rbp+30h+lpExistingFileName]; lpExistingFileName
0x1800798a8  call    cs:__imp_MoveFileExW
0x1800798af  nop     dword ptr [rax+rax+00h]
0x1800798b4  test    eax, eax
0x1800798b6  jnz     short loc_180079927
0x1800798b8  call    cs:__imp_GetLastError
0x1800798bf  nop     dword ptr [rax+rax+00h]
0x1800798c4  mov     ebx, eax
0x1800798c6  mov     rcx, [rbp+30h+arg_8]
0x1800798ca  mov     dword ptr [rcx+19E0h], 0Fh
0x1800798d4  mov     rcx, [rbp+30h+lpExistingFileName]; lpFileName
0x1800798d8  call    cs:__imp_DeleteFileW
0x1800798df  nop     dword ptr [rax+rax+00h]
0x1800798e4  mov     rcx, [rbp+38h]; this
0x1800798e8  test    eax, eax
0x1800798ea  jnz     short loc_1800798F6
0x1800798ec  mov     edx, 1C1h; void *
0x1800798f1  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800798f6  test    ebx, ebx
0x1800798f8  jz      short loc_180079919
0x1800798fa  mov     rcx, [rbp+38h]; this
0x1800798fe  mov     r9d, ebx; char *
0x180079901  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180079908  mov     edx, 1C3h; void *
0x18007990d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180079912  mov     ebx, eax
0x180079914  jmp     loc_18007986F
0x180079919  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x18007991d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180079922  jmp     loc_1800799A7
0x180079927  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x18007992b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180079930  mov     byte ptr [rsp+130h+var_D0], r12b
0x180079935  test    esi, esi
0x180079937  jz      short loc_18007996C
0x180079939  mov     r9, [rbp+30h+lpFileName]; wchar_t *
0x18007993d  mov     r8, [rsp+130h+var_C8]; wchar_t *
0x180079942  xor     edx, edx; int
0x180079944  mov     rcx, [rbp+30h+var_48]; wchar_t *
0x180079948  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x18007994d  mov     ebx, eax
0x18007994f  test    eax, eax
0x180079951  jz      short loc_18007996C
0x180079953  cmp     eax, 80070091h
0x180079958  jz      short loc_18007996C
0x18007995a  test    eax, eax
0x18007995c  jns     loc_1800797CB
0x180079962  mov     edx, 1D3h
0x180079967  jmp     loc_1800797B7
0x18007996c  mov     ecx, [r15+8]
0x180079970  mov     rax, [rbp+30h+arg_8]
0x180079974  mov     [rax+0B5D0h], ecx
0x18007997a  mov     rdx, [rbp+30h+var_48]; wchar_t *
0x18007997e  mov     rcx, [rbp+30h+arg_8]; this
0x180079982  call    ?SetStorePath@CReport@@QEAAJPEB_W@Z; CReport::SetStorePath(wchar_t const *)
0x180079987  mov     rax, [rbp+30h+arg_8]
0x18007998b  mov     dword ptr [rax+19E0h], 0Eh
0x180079995  test    r14, r14
0x180079998  jz      short loc_1800799A7
0x18007999a  lea     rdx, [rbp+30h+var_48]
0x18007999e  mov     rcx, r14
0x1800799a1  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1800799a6  nop
0x1800799a7  lea     rcx, [rbp+30h+lpFileName]; void *
0x1800799ab  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800799b0  nop
0x1800799b1  lea     rcx, [rsp+130h+var_E0]
0x1800799b6  call    tlx___UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf_______UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___
0x1800799bb  nop
0x1800799bc  lea     rcx, [rsp+130h+var_C8]; void *
0x1800799c1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800799c6  nop
0x1800799c7  lea     rcx, [rbp+30h+var_A8]; void *
  ... truncated ...
```
