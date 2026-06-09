# UtilFlushFiles(wchar_t const *,wchar_t const *)

- ea: `0x18000e318`
- end: `0x18000e629`
- name: `?UtilFlushFiles@@YAJPEB_W0@Z`
- size: `785`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180020e70`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x1800035e8`
- `0x180004a44`
- `0x180006aa8`
- `0x18000e318`
- `0x180011ef8`
- `0x180011f84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e573`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000e3e6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000e3e6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000e553`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000e553`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000e602`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000e602`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e4ac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e4ac`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000e4c2`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000e4c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4f7`

## pseudocode

```c
__int64 __fastcall UtilFlushFiles(const wchar_t *a1, const wchar_t *a2)
{
  int v3; // eax
  unsigned int v4; // edi
  __int64 FirstFileW; // rbx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  HANDLE FileW; // rax
  void *v11; // rdi
  LPCWSTR v12; // rdi
  signed int LastError; // eax
  signed int v14; // eax
  LPCWSTR v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v17[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v19[8]; // [rsp+70h] [rbp-90h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  lpFileName[0] = v19;
  v19[0] = 0;
  lpFileName[1] = v19;
  v17[0] = 0;
  v16[0] = v17;
  v16[1] = v17;
  v3 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         (__int64)lpFileName,
         L"%ls\\%ls",
         a1,
         L"*.*");
  v4 = v3;
  if ( v3 < 0 )
  {
    FirstFileW = -1;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 94;
      v8 = (unsigned int)v3;
LABEL_36:
      WPP_SF_d(v6[2], v7, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v8);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
  if ( FirstFileW != -1 )
  {
    do
    {
      if ( (FindFileData.cFileName[0] != 46
         || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]))
        && (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
               (__int64)v16,
               L"%ls\\%ls",
               a1,
               FindFileData.cFileName);
        if ( v9 >= 0 )
        {
          FileW = CreateFileW(v16[0], 0x40000000u, 3u, 0, 3u, 0, 0);
          v11 = FileW;
          if ( (unsigned __int64)FileW + 1 <= 1 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = v16[0];
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                98,
                (unsigned int)WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
                LastError,
                (__int64)v12);
            }
          }
          else
          {
            FlushFileBuffers(FileW);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v16[0]);
            CloseHandle(v11);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            (unsigned int)v9);
        }
      }
    }
    while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    goto LABEL_28;
  }
  if ( GetLastError() == 2 )
  {
LABEL_28:
    v4 = 0;
    goto LABEL_37;
  }
  v14 = GetLastError();
  v4 = v14;
  if ( v14 > 0 )
    v4 = (unsigned __int16)v14 | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    v4 = -2147467259;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 95;
    v8 = v4;
    goto LABEL_36;
  }
LABEL_37:
  if ( v16[0] != v17 )
    operator delete((void *)v16[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName[0] != v19 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  return v4;
}

```

## disassembly

```asm
0x18000e318  push    rbp
0x18000e31a  push    rbx
0x18000e31b  push    rsi
0x18000e31c  push    rdi
0x18000e31d  push    r14
0x18000e31f  push    r15
0x18000e321  lea     rbp, [rsp-1E8h]
0x18000e329  sub     rsp, 2E8h
0x18000e330  mov     rax, cs:__security_cookie
0x18000e337  xor     rax, rsp
0x18000e33a  mov     [rbp+210h+var_40], rax
0x18000e341  mov     r14, rcx
0x18000e344  xor     edx, edx; Val
0x18000e346  lea     rcx, [rbp+210h+FindFileData]; void *
0x18000e34a  mov     r8d, 250h; Size
0x18000e350  call    memset_0
0x18000e355  lea     rax, [rsp+310h+var_2A0]
0x18000e35a  xor     r15d, r15d
0x18000e35d  mov     [rsp+310h+lpFileName], rax
0x18000e362  lea     r9, asc_18003CA30; "*.*"
0x18000e369  lea     rax, [rsp+310h+var_2A0]
0x18000e36e  mov     [rsp+310h+var_2A0], r15w
0x18000e374  mov     [rsp+310h+var_2A8], rax
0x18000e379  lea     rdx, aLsLs; "%ls\\%ls"
0x18000e380  lea     rax, [rsp+310h+var_2C0]
0x18000e385  mov     [rsp+310h+var_2C0], r15w
0x18000e38b  mov     [rsp+310h+var_2D0], rax
0x18000e390  lea     rcx, [rsp+310h+lpFileName]
0x18000e395  lea     rax, [rsp+310h+var_2C0]
0x18000e39a  mov     r8, r14
0x18000e39d  mov     [rsp+310h+var_2C8], rax
0x18000e3a2  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000e3a7  mov     edi, eax
0x18000e3a9  test    eax, eax
0x18000e3ab  jns     short loc_18000E3DD
0x18000e3ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3b8  lea     rsi, WPP_GLOBAL_Control
0x18000e3bf  cmp     rcx, rsi
0x18000e3c2  jz      loc_18000E5C3
0x18000e3c8  test    byte ptr [rcx+1Ch], 1
0x18000e3cc  jz      loc_18000E5C3
0x18000e3d2  lea     edx, [rbx+5Fh]
0x18000e3d5  mov     r9d, eax
0x18000e3d8  jmp     loc_18000E5B3
0x18000e3dd  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x18000e3e2  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18000e3e6  call    cs:__imp_FindFirstFileW
0x18000e3ec  mov     rbx, rax
0x18000e3ef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e3f3  jz      loc_18000E563
0x18000e3f9  lea     rsi, WPP_GLOBAL_Control
0x18000e400  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x18000e405  movzx   eax, [rbp+210h+FindFileData.cFileName+2]
0x18000e409  jnz     short loc_18000E42C
0x18000e40b  test    ax, ax
0x18000e40e  jz      loc_18000E54C
0x18000e414  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x18000e419  jnz     short loc_18000E42C
0x18000e41b  cmp     ax, 2Eh ; '.'
0x18000e41f  jnz     short loc_18000E42C
0x18000e421  cmp     [rbp+210h+FindFileData.cFileName+4], r15w
0x18000e426  jz      loc_18000E54C
0x18000e42c  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x18000e430  jnz     loc_18000E54C
0x18000e436  lea     r9, [rbp+210h+FindFileData.cFileName]
0x18000e43a  mov     r8, r14
0x18000e43d  lea     rdx, aLsLs; "%ls\\%ls"
0x18000e444  lea     rcx, [rsp+310h+var_2D0]
0x18000e449  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000e44e  test    eax, eax
0x18000e450  jns     short loc_18000E489
0x18000e452  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e459  cmp     rcx, rsi
0x18000e45c  jz      loc_18000E54C
0x18000e462  test    byte ptr [rcx+1Ch], 2
0x18000e466  jz      loc_18000E54C
0x18000e46c  mov     rcx, [rcx+10h]
0x18000e470  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000e477  mov     edx, 60h ; '`'
0x18000e47c  mov     r9d, eax
0x18000e47f  call    WPP_SF_d
0x18000e484  jmp     loc_18000E54C
0x18000e489  mov     rcx, [rsp+310h+var_2D0]; lpFileName
0x18000e48e  xor     r9d, r9d; lpSecurityAttributes
0x18000e491  mov     [rsp+310h+hTemplateFile], r15; hTemplateFile
0x18000e496  mov     edx, 40000000h; dwDesiredAccess
0x18000e49b  mov     [rsp+310h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18000e4a0  mov     [rsp+310h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e4a8  lea     r8d, [r9+3]; dwShareMode
0x18000e4ac  call    cs:__imp_CreateFileW
0x18000e4b2  mov     rdi, rax
0x18000e4b5  lea     rcx, [rax+1]
0x18000e4b9  cmp     rcx, 1
0x18000e4bd  jbe     short loc_18000E4FF
0x18000e4bf  mov     rcx, rax; hFile
0x18000e4c2  call    cs:__imp_FlushFileBuffers
0x18000e4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4cf  cmp     rcx, rsi
0x18000e4d2  jz      short loc_18000E4F4
0x18000e4d4  test    byte ptr [rcx+1Ch], 8
0x18000e4d8  jz      short loc_18000E4F4
0x18000e4da  mov     r9, [rsp+310h+var_2D0]
0x18000e4df  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000e4e6  mov     rcx, [rcx+10h]
0x18000e4ea  mov     edx, 61h ; 'a'
0x18000e4ef  call    WPP_SF_S
0x18000e4f4  mov     rcx, rdi; hObject
0x18000e4f7  call    cs:__imp_CloseHandle
0x18000e4fd  jmp     short loc_18000E54C
0x18000e4ff  mov     rax, cs:WPP_GLOBAL_Control
0x18000e506  cmp     rax, rsi
0x18000e509  jz      short loc_18000E54C
0x18000e50b  test    byte ptr [rax+1Ch], 2
0x18000e50f  jz      short loc_18000E54C
0x18000e511  mov     rdi, [rsp+310h+var_2D0]
0x18000e516  call    cs:__imp_GetLastError
0x18000e51c  test    eax, eax
0x18000e51e  jle     short loc_18000E528
0x18000e520  movzx   eax, ax
0x18000e523  or      eax, 80070000h
0x18000e528  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e52f  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000e536  mov     edx, 62h ; 'b'
0x18000e53b  mov     qword ptr [rsp+310h+dwCreationDisposition], rdi
0x18000e540  mov     r9d, eax
0x18000e543  mov     rcx, [rcx+10h]
0x18000e547  call    WPP_SF_DS
0x18000e54c  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18000e550  mov     rcx, rbx; hFindFile
0x18000e553  call    cs:__imp_FindNextFileW
0x18000e559  test    eax, eax
0x18000e55b  jnz     loc_18000E400
0x18000e561  jmp     short loc_18000E56E
0x18000e563  call    cs:__imp_GetLastError
0x18000e569  cmp     eax, 2
0x18000e56c  jnz     short loc_18000E573
0x18000e56e  mov     edi, r15d
0x18000e571  jmp     short loc_18000E5C3
0x18000e573  call    cs:__imp_GetLastError
0x18000e579  mov     edi, eax
0x18000e57b  test    eax, eax
0x18000e57d  jle     short loc_18000E588
0x18000e57f  movzx   edi, ax
0x18000e582  or      edi, 80070000h
0x18000e588  test    edi, edi
0x18000e58a  mov     eax, 80004005h
0x18000e58f  cmovns  edi, eax
0x18000e592  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e599  lea     rsi, WPP_GLOBAL_Control
0x18000e5a0  cmp     rcx, rsi
0x18000e5a3  jz      short loc_18000E5C3
0x18000e5a5  test    byte ptr [rcx+1Ch], 1
0x18000e5a9  jz      short loc_18000E5C3
0x18000e5ab  mov     edx, 5Fh ; '_'
0x18000e5b0  mov     r9d, edi
0x18000e5b3  mov     rcx, [rcx+10h]
0x18000e5b7  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000e5be  call    WPP_SF_d
0x18000e5c3  mov     rcx, [rsp+310h+var_2D0]; void *
0x18000e5c8  lea     rax, [rsp+310h+var_2C0]
0x18000e5cd  cmp     rcx, rax
0x18000e5d0  jz      short loc_18000E5DE
0x18000e5d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e5d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e5de  mov     rcx, [rsp+310h+lpFileName]; void *
0x18000e5e3  lea     rax, [rsp+310h+var_2A0]
0x18000e5e8  cmp     rcx, rax
0x18000e5eb  jz      short loc_18000E5F9
0x18000e5ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e5f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e5f9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e5fd  jz      short loc_18000E608
0x18000e5ff  mov     rcx, rbx; hFindFile
0x18000e602  call    cs:__imp_FindClose
0x18000e608  mov     eax, edi
0x18000e60a  mov     rcx, [rbp+210h+var_40]
0x18000e611  xor     rcx, rsp; StackCookie
0x18000e614  call    __security_check_cookie
0x18000e619  add     rsp, 2E8h
0x18000e620  pop     r15
0x18000e622  pop     r14
0x18000e624  pop     rdi
0x18000e625  pop     rsi
0x18000e626  pop     rbx
0x18000e627  pop     rbp
0x18000e628  retn
```
