# CReportStore::UpdateReportInStore(wchar_t const *,CReport *,int)

- ea: `0x18007a000`
- end: `0x18007a279`
- name: `?UpdateReportInStore@CReportStore@@UEAAJPEB_WPEAVCReport@@H@Z`
- size: `633`
- prototype: `int(CReportStore *__hidden this, const wchar_t *, struct CReport *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800793a0`

## callees

- `0x180007fd8`
- `0x180009684`
- `0x18000cf50`
- `0x18000db80`
- `0x18000e31c`
- `0x18001e658`
- `0x18002d8f4`
- `0x1800318c8`
- `0x18003fb94`
- `0x180040814`
- `0x180075fcc`
- `0x180076de4`
- `0x18007756c`
- `0x180079d7c`
- `0x18007a000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a1b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a1b8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007a1a8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007a1a8`

## string_xrefs

- `0x18007a050`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18007a0a4`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18007a10e`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18007a1e8`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18007a204`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18007a252`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CReportStore::UpdateReportInStore(CReportStore *this, wchar_t *a2, struct CReport *a3, int a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  int v11; // r8d
  CReport *v12; // rcx
  DWORD LastError; // ebx
  int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v17[2]; // [rsp+28h] [rbp-58h] BYREF
  char v18; // [rsp+38h] [rbp-48h]
  LPCWSTR lpExistingFileName[4]; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpNewFileName[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  int v22; // [rsp+A8h] [rbp+28h] BYREF
  CReport *v23; // [rsp+B0h] [rbp+30h] BYREF

  v23 = a3;
  if ( !a2 || !a3 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A1,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)0x80070057LL,
      v16);
    return v7;
  }
  v16 = 0;
  v6 = UtilVerifyAndLockDirectory(a2, (__int64)&v16);
  v7 = v6;
  if ( v6 >= 0 )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpExistingFileName);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpNewFileName);
    v22 = 0;
    if ( !(unsigned int)CReport::IsReportLocked(v23) )
    {
      v8 = CReport::TryReportLock(v23);
      v7 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5AE,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v8,
          v16);
LABEL_8:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpNewFileName);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
        goto LABEL_29;
      }
      v22 = 1;
    }
    v17[0] = &v22;
    v17[1] = &v23;
    v18 = 1;
    v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
           lpExistingFileName,
           L"%s\\%s",
           a2,
           L"Report.wer.tmp");
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
             lpNewFileName,
             L"%s\\%s",
             a2,
             L"Report.wer");
      v7 = v9;
      if ( v9 >= 0 )
      {
        v12 = v23;
        if ( a4 && !*((_DWORD *)v23 + 1637) )
        {
          v9 = CReport::SaveTemporaryAttachedFiles(v23, a2);
          v7 = v9;
          if ( v9 < 0 )
          {
            v10 = 1478;
            goto LABEL_12;
          }
          v12 = v23;
        }
        v9 = CReport::WriteReportToFile(v12, lpExistingFileName[0], v11, 0);
        v7 = v9;
        if ( v9 >= 0 )
        {
          if ( MoveFileExW(lpExistingFileName[0], lpNewFileName[0], 1u) )
            goto LABEL_28;
          LastError = GetLastError();
          *((_DWORD *)v23 + 1656) = 15;
          v14 = UtilDeleteFilePath(lpExistingFileName[0]);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5D1,
              (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
              (const char *)(unsigned int)v14,
              v16);
          if ( !LastError )
          {
LABEL_28:
            tlx::_UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___::__UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___(v17);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpNewFileName);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
            v7 = 0;
            goto LABEL_29;
          }
          v7 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x5D3,
                 (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
                 (const char *)LastError,
                 v16);
          goto LABEL_13;
        }
        v10 = 1482;
      }
      else
      {
        v10 = 1468;
      }
    }
    else
    {
      v10 = 1466;
    }
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)(unsigned int)v9,
      v16);
LABEL_13:
    tlx::_UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___::__UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___(v17);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5A6,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
    (const char *)(unsigned int)v6,
    v16);
LABEL_29:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v16);
  return v7;
}

```

## disassembly

```asm
0x18007a000  mov     [rsp-18h+arg_0], rbx
0x18007a005  mov     [rsp-18h+arg_10], r8
0x18007a00a  push    rbp
0x18007a00b  push    rsi
0x18007a00c  push    rdi
0x18007a00d  mov     rbp, rsp
0x18007a010  sub     rsp, 80h
0x18007a017  mov     esi, r9d
0x18007a01a  mov     rdi, rdx
0x18007a01d  test    rdx, rdx
0x18007a020  jz      loc_18007A246
0x18007a026  test    r8, r8
0x18007a029  jz      loc_18007A246
0x18007a02f  mov     [rbp+var_60], 0
0x18007a037  lea     rdx, [rbp+var_60]
0x18007a03b  mov     rcx, rdi; wchar_t *
0x18007a03e  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x18007a043  mov     ebx, eax
0x18007a045  test    eax, eax
0x18007a047  jns     short loc_18007A066
0x18007a049  mov     rcx, [rbp+18h]; this
0x18007a04d  mov     r9d, eax; char *
0x18007a050  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18007a057  mov     edx, 5A6h; void *
0x18007a05c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a061  jmp     loc_18007A23B
0x18007a066  lea     rcx, [rbp+lpExistingFileName]; void *
0x18007a06a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18007a06f  nop
0x18007a070  lea     rcx, [rbp+lpNewFileName]; void *
0x18007a074  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18007a079  nop
0x18007a07a  mov     [rbp+arg_8], 0
0x18007a081  mov     rcx, [rbp+arg_10]; this
0x18007a085  call    ?IsReportLocked@CReport@@QEAAHXZ; CReport::IsReportLocked(void)
0x18007a08a  test    eax, eax
0x18007a08c  jnz     short loc_18007A0D5
0x18007a08e  mov     rcx, [rbp+arg_10]; this
0x18007a092  call    ?TryReportLock@CReport@@QEAAJXZ; CReport::TryReportLock(void)
0x18007a097  mov     ebx, eax
0x18007a099  test    eax, eax
0x18007a09b  jns     short loc_18007A0CE
0x18007a09d  mov     rcx, [rbp+18h]; this
0x18007a0a1  mov     r9d, eax; char *
0x18007a0a4  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18007a0ab  mov     edx, 5AEh; void *
0x18007a0b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a0b5  nop
0x18007a0b6  lea     rcx, [rbp+lpNewFileName]; void *
0x18007a0ba  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007a0bf  nop
0x18007a0c0  lea     rcx, [rbp+lpExistingFileName]; void *
0x18007a0c4  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007a0c9  jmp     loc_18007A23B
0x18007a0ce  mov     [rbp+arg_8], 1
0x18007a0d5  lea     rax, [rbp+arg_8]
0x18007a0d9  mov     [rbp+var_58], rax
0x18007a0dd  lea     rax, [rbp+arg_10]
0x18007a0e1  mov     [rbp+var_50], rax
0x18007a0e5  mov     [rbp+var_48], 1
0x18007a0e9  lea     r9, aReportWerTmp; "Report.wer.tmp"
0x18007a0f0  mov     r8, rdi
0x18007a0f3  lea     rdx, aSS; "%s\\%s"
0x18007a0fa  lea     rcx, [rbp+lpExistingFileName]
0x18007a0fe  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007a103  mov     ebx, eax
0x18007a105  test    eax, eax
0x18007a107  jns     short loc_18007A12D
0x18007a109  mov     edx, 5BAh; void *
0x18007a10e  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18007a115  mov     r9d, eax; char *
0x18007a118  mov     rcx, [rbp+18h]; this
0x18007a11c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a121  nop
0x18007a122  lea     rcx, [rbp+var_58]
0x18007a126  call    tlx___UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf_______UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___
0x18007a12b  jmp     short loc_18007A0B6
0x18007a12d  lea     r9, aReportWer; "Report.wer"
0x18007a134  mov     r8, rdi
0x18007a137  lea     rdx, aSS; "%s\\%s"
0x18007a13e  lea     rcx, [rbp+lpNewFileName]
0x18007a142  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007a147  mov     ebx, eax
0x18007a149  test    eax, eax
0x18007a14b  jns     short loc_18007A154
0x18007a14d  mov     edx, 5BCh
0x18007a152  jmp     short loc_18007A10E
0x18007a154  mov     rcx, [rbp+arg_10]; this
0x18007a158  test    esi, esi
0x18007a15a  jz      short loc_18007A17E
0x18007a15c  cmp     dword ptr [rcx+1994h], 0
0x18007a163  jnz     short loc_18007A17E
0x18007a165  mov     rdx, rdi; wchar_t *
0x18007a168  call    ?SaveTemporaryAttachedFiles@CReport@@QEAAJPEB_W@Z; CReport::SaveTemporaryAttachedFiles(wchar_t const *)
0x18007a16d  mov     ebx, eax
0x18007a16f  test    eax, eax
0x18007a171  jns     short loc_18007A17A
0x18007a173  mov     edx, 5C6h
0x18007a178  jmp     short loc_18007A10E
0x18007a17a  mov     rcx, [rbp+arg_10]; this
0x18007a17e  xor     r9d, r9d; unsigned int
0x18007a181  mov     rdx, [rbp+lpExistingFileName]; wchar_t *
0x18007a185  call    ?WriteReportToFile@CReport@@QEAAJPEB_WHK@Z; CReport::WriteReportToFile(wchar_t const *,int,ulong)
0x18007a18a  mov     ebx, eax
0x18007a18c  test    eax, eax
0x18007a18e  jns     short loc_18007A19A
0x18007a190  mov     edx, 5CAh
0x18007a195  jmp     loc_18007A10E
0x18007a19a  mov     r8d, 1; dwFlags
0x18007a1a0  mov     rdx, [rbp+lpNewFileName]; lpNewFileName
0x18007a1a4  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x18007a1a8  call    cs:__imp_MoveFileExW
0x18007a1af  nop     dword ptr [rax+rax+00h]
0x18007a1b4  test    eax, eax
0x18007a1b6  jnz     short loc_18007A21C
0x18007a1b8  call    cs:__imp_GetLastError
0x18007a1bf  nop     dword ptr [rax+rax+00h]
0x18007a1c4  mov     ebx, eax
0x18007a1c6  mov     rcx, [rbp+arg_10]
0x18007a1ca  mov     dword ptr [rcx+19E0h], 0Fh
0x18007a1d4  mov     rcx, [rbp+lpExistingFileName]; wchar_t *
0x18007a1d8  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18007a1dd  mov     rcx, [rbp+18h]; this
0x18007a1e1  test    eax, eax
0x18007a1e3  jns     short loc_18007A1F9
0x18007a1e5  mov     r9d, eax; char *
0x18007a1e8  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18007a1ef  mov     edx, 5D1h; void *
0x18007a1f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007a1f9  test    ebx, ebx
0x18007a1fb  jz      short loc_18007A21C
0x18007a1fd  mov     rcx, [rbp+18h]; this
0x18007a201  mov     r9d, ebx; char *
0x18007a204  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18007a20b  mov     edx, 5D3h; void *
0x18007a210  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007a215  mov     ebx, eax
0x18007a217  jmp     loc_18007A122
0x18007a21c  lea     rcx, [rbp+var_58]
0x18007a220  call    tlx___UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf_______UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___
0x18007a225  nop
0x18007a226  lea     rcx, [rbp+lpNewFileName]; void *
0x18007a22a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007a22f  nop
0x18007a230  lea     rcx, [rbp+lpExistingFileName]; void *
0x18007a234  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007a239  xor     ebx, ebx
0x18007a23b  lea     rcx, [rbp+var_60]
0x18007a23f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18007a244  jmp     short loc_18007A263
0x18007a246  mov     rcx, [rbp+18h]; this
0x18007a24a  mov     ebx, 80070057h
0x18007a24f  mov     r9d, ebx; char *
0x18007a252  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18007a259  mov     edx, 5A1h; void *
0x18007a25e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a263  mov     eax, ebx
0x18007a265  mov     rbx, [rsp+80h+arg_0]
0x18007a26d  add     rsp, 80h
0x18007a274  pop     rdi
0x18007a275  pop     rsi
0x18007a276  pop     rbp
0x18007a277  retn
```
