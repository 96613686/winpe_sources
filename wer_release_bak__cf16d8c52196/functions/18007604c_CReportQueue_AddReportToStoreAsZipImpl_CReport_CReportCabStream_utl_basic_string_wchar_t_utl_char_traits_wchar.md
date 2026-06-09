# CReportQueue::AddReportToStoreAsZipImpl(CReport *,CReportCabStream *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18007604c`
- end: `0x180076522`
- name: `?AddReportToStoreAsZipImpl@CReportQueue@@AEAAJPEAVCReport@@PEAVCReportCabStream@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1238`
- prototype: `__int64 __fastcall(__int64, CReport *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x180045458`

## callees

- `0x180007db4`
- `0x180007de0`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x18000ea64`
- `0x18001abd8`
- `0x180039f70`
- `0x18003db78`
- `0x18003e864`
- `0x180045bdc`
- `0x18004bc2c`
- `0x18004ed14`
- `0x180073514`
- `0x180074114`
- `0x180076000`
- `0x18007604c`
- `0x180076800`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800763ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800763ec`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180076406`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180076406`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180076328`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180076328`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800763e2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800763e2`

## string_xrefs

- `0x180076089`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076109`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076147`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800761d9`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076248`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800762fe`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076395`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076429`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`

## pseudocode

```c
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
    UniqueIdentifier = CReport::GetUniqueIdentifier(v41, (__int64)v36);
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
0x18007604c  mov     rax, rsp
0x18007604f  mov     [rax+8], rbx
0x180076053  mov     [rax+18h], rsi
0x180076057  mov     [rax+10h], rdx
0x18007605b  push    rbp
0x18007605c  push    rdi
0x18007605d  push    r12
0x18007605f  push    r14
0x180076061  push    r15
0x180076063  lea     rbp, [rax-38h]
0x180076067  sub     rsp, 110h
0x18007606e  mov     r14, r9
0x180076071  mov     rdi, r8
0x180076074  mov     r15, rcx
0x180076077  xor     r12d, r12d
0x18007607a  test    rdx, rdx
0x18007607d  jnz     short loc_1800760A1
0x18007607f  mov     edx, 15Dh; void *
0x180076084  mov     ebx, 80070057h
0x180076089  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076090  mov     r9d, ebx; char *
0x180076093  mov     rcx, [rbp+38h]; this
0x180076097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007609c  jmp     loc_180076504
0x1800760a1  test    rdi, rdi
0x1800760a4  jnz     short loc_1800760AD
0x1800760a6  mov     edx, 15Eh
0x1800760ab  jmp     short loc_180076084
0x1800760ad  mov     dword ptr [rdx+19E0h], 9
0x1800760b7  lea     rcx, [rbp+30h+var_48]; void *
0x1800760bb  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800760c0  nop
0x1800760c1  mov     [rsp+130h+var_F0], r12
0x1800760c6  lea     rdx, [rsp+130h+var_F0]; wchar_t **
0x1800760cb  mov     rcx, [rbp+30h+arg_8]; this
0x1800760cf  call    ?GetStorePath@CReport@@QEAAJPEAPEB_W@Z; CReport::GetStorePath(wchar_t const * *)
0x1800760d4  cmp     eax, 80004005h
0x1800760d9  jz      loc_180076167
0x1800760df  mov     rdx, [rsp+130h+var_F0]
0x1800760e4  test    rdx, rdx
0x1800760e7  jz      short loc_180076167
0x1800760e9  cmp     [rdx], r12w
0x1800760ed  jz      short loc_180076167
0x1800760ef  lea     rcx, [rbp+30h+var_48]
0x1800760f3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800760f8  test    al, al
0x1800760fa  jnz     short loc_18007611E
0x1800760fc  mov     ebx, 8007000Eh
0x180076101  mov     r9d, ebx; char *
0x180076104  mov     edx, 170h; void *
0x180076109  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076110  mov     rcx, [rbp+38h]; this
0x180076114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076119  jmp     loc_1800764FB
0x18007611e  mov     esi, 1
0x180076123  lea     rcx, [rbp+30h+var_A8]; void *
0x180076127  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18007612c  nop
0x18007612d  lea     rdx, [rbp+30h+var_A8]
0x180076131  mov     rcx, [rbp+30h+arg_8]
0x180076135  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18007613a  mov     ebx, eax
0x18007613c  test    eax, eax
0x18007613e  jns     short loc_18007618D
0x180076140  mov     rcx, [rbp+38h]; this
0x180076144  mov     r9d, eax; char *
0x180076147  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007614e  mov     edx, 17Dh; void *
0x180076153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076158  nop
0x180076159  lea     rcx, [rbp+30h+var_A8]; void *
0x18007615d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076162  jmp     loc_1800764FB
0x180076167  mov     esi, r12d
0x18007616a  lea     r8, [rbp+30h+var_48]
0x18007616e  mov     rdx, [rbp+30h+arg_8]
0x180076172  mov     rcx, r15
0x180076175  call    ?ReserveReportDirInStore@CReportStore@@QEAAJPEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::ReserveReportDirInStore(CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18007617a  mov     ebx, eax
0x18007617c  test    eax, eax
0x18007617e  jns     short loc_180076123
0x180076180  mov     r9d, eax
0x180076183  mov     edx, 16Ch
0x180076188  jmp     loc_180076109
0x18007618d  lea     rcx, [rsp+130h+var_C8]; void *
0x180076192  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076197  nop
0x180076198  lea     rcx, aCab_1; "cab"
0x18007619f  lea     rax, aZip_0; "zip"
0x1800761a6  cmp     [rdi+10h], r12d
0x1800761aa  cmovz   rax, rcx
0x1800761ae  mov     [rsp+130h+var_110], rax; int
0x1800761b3  mov     r9, [rbp+30h+var_A8]
0x1800761b7  mov     r8, [rbp+30h+var_48]
0x1800761bb  lea     rdx, aSSS_0; "%s\\%s.%s"
0x1800761c2  lea     rcx, [rsp+130h+var_C8]
0x1800761c7  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800761cc  mov     ebx, eax
0x1800761ce  test    eax, eax
0x1800761d0  jns     short loc_1800761FA
0x1800761d2  mov     rcx, [rbp+38h]; this
0x1800761d6  mov     r9d, eax; char *
0x1800761d9  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800761e0  mov     edx, 184h; void *
0x1800761e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800761ea  nop
0x1800761eb  lea     rcx, [rsp+130h+var_C8]; void *
0x1800761f0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800761f5  jmp     loc_180076159
0x1800761fa  lea     rax, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x180076201  mov     [rsp+130h+var_F0], rax
0x180076206  mov     [rsp+130h+var_E8], r12
0x18007620b  mov     [rsp+130h+var_F8], r12; void *
0x180076210  mov     [rsp+130h+var_100], 80h; unsigned int
0x180076218  mov     [rsp+130h+var_108], 1; unsigned int
0x180076220  mov     [rsp+130h+var_110], r12; int
0x180076225  xor     r9d, r9d; unsigned int
0x180076228  mov     r8d, 40000000h; unsigned int
0x18007622e  mov     rdx, [rsp+130h+var_C8]; wchar_t *
0x180076233  lea     rcx, [rsp+130h+var_F0]; this
0x180076238  call    ?OpenFile@CFileByteStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CFileByteStream::OpenFile(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18007623d  mov     ebx, eax
0x18007623f  test    eax, eax
0x180076241  jns     short loc_180076268
0x180076243  mov     edx, 192h; void *
0x180076248  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007624f  mov     r9d, eax; char *
0x180076252  mov     rcx, [rbp+38h]; this
0x180076256  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007625b  nop
0x18007625c  lea     rcx, [rsp+130h+var_F0]; this
0x180076261  call    ??1CFileByteStream@@UEAA@XZ; CFileByteStream::~CFileByteStream(void)
0x180076266  jmp     short loc_1800761EB
0x180076268  mov     rax, [rdi]
0x18007626b  xor     r8d, r8d
0x18007626e  lea     rdx, [rsp+130h+var_F0]
0x180076273  mov     rcx, rdi
0x180076276  mov     rax, [rax+18h]
0x18007627a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007627f  mov     ebx, eax
0x180076281  test    eax, eax
0x180076283  jns     short loc_18007628C
0x180076285  mov     edx, 194h
0x18007628a  jmp     short loc_180076248
0x18007628c  lea     rcx, [rsp+130h+var_F0]; this
0x180076291  call    ?Close@CFileByteStream@@UEAAXXZ; CFileByteStream::Close(void)
0x180076296  nop
0x180076297  lea     rcx, [rsp+130h+var_F0]; this
0x18007629c  call    ??1CFileByteStream@@UEAA@XZ; CFileByteStream::~CFileByteStream(void)
0x1800762a1  lea     rax, [rsp+130h+var_C8]
0x1800762a6  mov     [rsp+130h+var_E0], rax
0x1800762ab  lea     rax, [rbp+30h+arg_8]
0x1800762af  mov     qword ptr [rsp+130h+var_D8], rax
0x1800762b4  mov     byte ptr [rsp+130h+var_D0], 1
0x1800762b9  mov     rax, [rbp+30h+arg_8]
0x1800762bd  mov     dword ptr [rax+1994h], 1
0x1800762c7  lea     rcx, [rbp+30h+lpFileName]; void *
0x1800762cb  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800762d0  nop
0x1800762d1  lea     r9, aReportWer; "Report.wer"
0x1800762d8  mov     r8, [rbp+30h+var_48]
0x1800762dc  lea     rdx, aSS; "%s\\%s"
0x1800762e3  lea     rcx, [rbp+30h+lpFileName]
0x1800762e7  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800762ec  mov     ebx, eax
0x1800762ee  test    eax, eax
0x1800762f0  jns     short loc_180076324
0x1800762f2  mov     edx, 1A5h; void *
0x1800762f7  mov     r9d, eax; char *
0x1800762fa  mov     rcx, [rbp+38h]; this
0x1800762fe  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076305  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007630a  nop
0x18007630b  lea     rcx, [rbp+30h+lpFileName]; void *
0x18007630f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076314  nop
0x180076315  lea     rcx, [rsp+130h+var_E0]
0x18007631a  call    tlx___UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf_______UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___
0x18007631f  jmp     loc_1800761EB
0x180076324  mov     rcx, [rbp+30h+lpFileName]; lpFileName
0x180076328  call    cs:__imp_GetFileAttributesW
0x18007632e  cmp     eax, 0FFFFFFFFh
0x180076331  jnz     short loc_180076365
0x180076333  xor     r9d, r9d; unsigned int
0x180076336  mov     rdx, [rbp+30h+lpFileName]; wchar_t *
0x18007633a  mov     rcx, [rbp+30h+arg_8]; this
0x18007633e  call    ?WriteReportToFile@CReport@@QEAAJPEB_WHK@Z; CReport::WriteReportToFile(wchar_t const *,int,ulong)
0x180076343  mov     ebx, eax
0x180076345  test    eax, eax
0x180076347  jns     loc_180076458
0x18007634d  mov     rax, [rbp+30h+arg_8]
0x180076351  mov     dword ptr [rax+19E0h], 0Fh
0x18007635b  mov     r9d, ebx
0x18007635e  mov     edx, 1B2h
0x180076363  jmp     short loc_1800762FA
0x180076365  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x180076369  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18007636e  nop
0x18007636f  lea     r9, aReportWerTmp; "Report.wer.tmp"
0x180076376  mov     r8, [rbp+30h+var_48]
0x18007637a  lea     rdx, aSS; "%s\\%s"
0x180076381  lea     rcx, [rbp+30h+lpExistingFileName]
0x180076385  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007638a  mov     ebx, eax
0x18007638c  test    eax, eax
0x18007638e  jns     short loc_1800763B7
0x180076390  mov     edx, 1B8h; void *
0x180076395  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007639c  mov     r9d, eax; char *
0x18007639f  mov     rcx, [rbp+38h]; this
0x1800763a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800763a8  nop
0x1800763a9  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x1800763ad  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800763b2  jmp     loc_18007630B
0x1800763b7  xor     r9d, r9d; unsigned int
0x1800763ba  mov     rdx, [rbp+30h+lpExistingFileName]; wchar_t *
0x1800763be  mov     rcx, [rbp+30h+arg_8]; this
0x1800763c2  call    ?WriteReportToFile@CReport@@QEAAJPEB_WHK@Z; CReport::WriteReportToFile(wchar_t const *,int,ulong)
0x1800763c7  mov     ebx, eax
0x1800763c9  test    eax, eax
0x1800763cb  jns     short loc_1800763D4
0x1800763cd  mov     edx, 1BAh
0x1800763d2  jmp     short loc_180076395
0x1800763d4  mov     r8d, 1; dwFlags
0x1800763da  mov     rdx, [rbp+30h+lpFileName]; lpNewFileName
0x1800763de  mov     rcx, [rbp+30h+lpExistingFileName]; lpExistingFileName
0x1800763e2  call    cs:__imp_MoveFileExW
0x1800763e8  test    eax, eax
0x1800763ea  jnz     short loc_18007644F
0x1800763ec  call    cs:__imp_GetLastError
0x1800763f2  mov     ebx, eax
0x1800763f4  mov     rcx, [rbp+30h+arg_8]
0x1800763f8  mov     dword ptr [rcx+19E0h], 0Fh
0x180076402  mov     rcx, [rbp+30h+lpExistingFileName]; lpFileName
0x180076406  call    cs:__imp_DeleteFileW
0x18007640c  mov     rcx, [rbp+38h]; this
0x180076410  test    eax, eax
0x180076412  jnz     short loc_18007641E
0x180076414  mov     edx, 1C1h; void *
0x180076419  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18007641e  test    ebx, ebx
0x180076420  jz      short loc_180076441
0x180076422  mov     rcx, [rbp+38h]; this
0x180076426  mov     r9d, ebx; char *
0x180076429  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076430  mov     edx, 1C3h; void *
0x180076435  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007643a  mov     ebx, eax
0x18007643c  jmp     loc_1800763A9
0x180076441  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x180076445  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007644a  jmp     loc_1800764CF
0x18007644f  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x180076453  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076458  mov     byte ptr [rsp+130h+var_D0], r12b
0x18007645d  test    esi, esi
0x18007645f  jz      short loc_180076494
0x180076461  mov     r9, [rbp+30h+lpFileName]; wchar_t *
0x180076465  mov     r8, [rsp+130h+var_C8]; wchar_t *
0x18007646a  xor     edx, edx; int
0x18007646c  mov     rcx, [rbp+30h+var_48]; wchar_t *
0x180076470  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x180076475  mov     ebx, eax
0x180076477  test    eax, eax
0x180076479  jz      short loc_180076494
0x18007647b  cmp     eax, 80070091h
0x180076480  jz      short loc_180076494
0x180076482  test    eax, eax
0x180076484  jns     loc_18007630B
0x18007648a  mov     edx, 1D3h
0x18007648f  jmp     loc_1800762F7
0x180076494  mov     ecx, [r15+8]
0x180076498  mov     rax, [rbp+30h+arg_8]
0x18007649c  mov     [rax+0B5D0h], ecx
0x1800764a2  mov     rdx, [rbp+30h+var_48]; wchar_t *
0x1800764a6  mov     rcx, [rbp+30h+arg_8]; this
0x1800764aa  call    ?SetStorePath@CReport@@QEAAJPEB_W@Z; CReport::SetStorePath(wchar_t const *)
0x1800764af  mov     rax, [rbp+30h+arg_8]
0x1800764b3  mov     dword ptr [rax+19E0h], 0Eh
0x1800764bd  test    r14, r14
0x1800764c0  jz      short loc_1800764CF
0x1800764c2  lea     rdx, [rbp+30h+var_48]
0x1800764c6  mov     rcx, r14
0x1800764c9  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1800764ce  nop
0x1800764cf  lea     rcx, [rbp+30h+lpFileName]; void *
0x1800764d3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800764d8  nop
0x1800764d9  lea     rcx, [rsp+130h+var_E0]
0x1800764de  call    tlx___UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf_______UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___
0x1800764e3  nop
0x1800764e4  lea     rcx, [rsp+130h+var_C8]; void *
0x1800764e9  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800764ee  nop
0x1800764ef  lea     rcx, [rbp+30h+var_A8]; void *
0x1800764f3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800764f8  mov     ebx, r12d
0x1800764fb  lea     rcx, [rbp+30h+var_48]; void *
0x1800764ff  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
  ... truncated ...
```
