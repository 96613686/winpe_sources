# UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x180012e94`
- end: `0x1800133d5`
- name: `?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `1345`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800139c0`
- `0x180018e90`
- `0x180019004`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x1800035e8`
- `0x180004a44`
- `0x180006aa8`
- `0x18000caf0`
- `0x18000cb10`
- `0x18000cf08`
- `0x1800106f4`
- `0x180011648`
- `0x180011ef8`
- `0x180012b4c`
- `0x180012e94`
- `0x180013494`
- `0x180013580`
- `0x180013678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013277`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013023`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013023`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180013268`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180013268`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800131a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800131a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800132f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800132f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013332`

## string_xrefs

- `0x180012efe`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x180012fe5`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x180013148`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x1800131c9`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x1800131fc`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x180013381`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilGetTempFile(
        void **a1,
        WCHAR *a2,
        __int64 a3,
        wchar_t *a4,
        __int64 a5,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD a7,
        int a8)
{
  __int64 v12; // rdx
  int TempDirPath; // ebx
  unsigned int v14; // edx
  unsigned __int64 v15; // r8
  __int64 v16; // rdx
  const WCHAR *v17; // rcx
  __int64 v18; // r9
  LPCWSTR v19; // rdx
  const wchar_t *v20; // r8
  DWORD FileAttributesW; // eax
  __int64 v23; // rdx
  int v24; // eax
  HANDLE FileW; // rax
  int v26; // r8d
  const char *v27; // r9
  void *v28; // rbx
  void *v29; // rsi
  int v30; // edi
  __int64 v31; // rdx
  signed int LastError; // eax
  void *v33; // rcx
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v35; // [rsp+48h] [rbp-B8h]
  _WORD v36[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszShortPath[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v38[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwShareMode[4]; // [rsp+80h] [rbp-80h]
  wchar_t v40[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  dwShareMode[0] = a7;
  if ( !a4 )
  {
    v12 = 75;
LABEL_3:
    TempDirPath = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)TempDirPath);
    return (unsigned int)TempDirPath;
  }
  memset_0(FileName, 0, 0x208u);
  if ( !a2 )
  {
    TempDirPath = UtilGetTempDirPath(FileName, v14);
    if ( TempDirPath < 0 )
    {
      v12 = 80;
      goto LABEL_4;
    }
    a2 = FileName;
  }
  if ( !*a2 )
  {
    v12 = 89;
    goto LABEL_3;
  }
  lpFileName = v36;
  v35 = v36;
  v36[0] = 0;
  v15 = -1;
  do
    ++v15;
  while ( a2[v15] );
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          (__int64)&lpFileName,
          a2,
          v15) )
  {
    v16 = 94;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)0x8007000ELL);
    if ( lpFileName != v36 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v17 = lpFileName;
  if ( (unsigned __int64)(v35 - lpFileName) >= 4 )
  {
    v18 = 4;
    v19 = lpFileName;
    v20 = L"\\\\?\\";
    while ( *v20 == *v19 )
    {
      ++v20;
      ++v19;
      if ( !--v18 )
        goto LABEL_26;
    }
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(&lpFileName) )
  {
    v16 = 100;
    goto LABEL_22;
  }
  v17 = lpFileName;
LABEL_26:
  FileAttributesW = GetFileAttributesW(v17);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    TempDirPath = -2147024809;
    v23 = 106;
    goto LABEL_74;
  }
  if ( a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
        (_DWORD)lpFileName,
        a3);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, lpFileName);
  }
  TempDirPath = UtilUuidCreateAsString(v40);
  if ( TempDirPath < 0 )
  {
    v23 = 118;
LABEL_74:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)TempDirPath);
LABEL_75:
    if ( lpFileName != v36 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)TempDirPath;
  }
  lpszShortPath[0] = v38;
  lpszShortPath[1] = v38;
  v38[0] = 0;
  v24 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          (__int64)lpszShortPath,
          L"%ls%lsWER.%ls.tmp%ls");
  TempDirPath = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)v24);
    goto LABEL_39;
  }
  FileW = CreateFileW(lpszShortPath[0], 0xC0000000, dwShareMode[0], lpSecurityAttributes, 1u, a8 | 0x80u, 0);
  v28 = FileW;
  v29 = FileW;
  *(_QWORD *)dwShareMode = FileW;
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    TempDirPath = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x8A,
                    (int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
                    v27);
LABEL_39:
    if ( lpszShortPath[0] != v38 )
      operator delete((void *)lpszShortPath[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_75;
  }
  v30 = UtilVerifyFilePath((wchar_t *)lpszShortPath[0], FileW, v26, (int)v27);
  if ( v30 < 0 )
  {
    v31 = 142;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)v30);
    CloseHandle(v28);
    if ( lpszShortPath[0] != v38 )
      operator delete((void *)lpszShortPath[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpFileName != v36 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v30;
  }
  if ( GetLongPathNameW(lpszShortPath[0], a4, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
        (unsigned int)LastError);
    v30 = StringCchCopyW(a4, 0x104u, lpszShortPath[0]);
    if ( v30 < 0 )
    {
      v31 = 154;
      goto LABEL_45;
    }
  }
  if ( a1 )
  {
    v29 = 0;
    v33 = *a1;
    *a1 = v28;
    if ( (unsigned __int64)v33 + 1 > 1 )
      CloseHandle(v33);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, a4);
  if ( (unsigned __int64)v29 + 1 > 1 )
    CloseHandle(v29);
  if ( lpszShortPath[0] != v38 )
    operator delete((void *)lpszShortPath[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v36 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180012e94  push    rbp
0x180012e96  push    rbx
0x180012e97  push    rsi
0x180012e98  push    rdi
0x180012e99  push    r12
0x180012e9b  push    r13
0x180012e9d  push    r14
0x180012e9f  push    r15
0x180012ea1  lea     rbp, [rsp-208h]
0x180012ea9  sub     rsp, 308h
0x180012eb0  mov     rax, cs:__security_cookie
0x180012eb7  xor     rax, rsp
0x180012eba  mov     [rbp+240h+var_50], rax
0x180012ec1  mov     r12, r9
0x180012ec4  mov     rdi, r8
0x180012ec7  mov     rbx, rdx
0x180012eca  mov     r15, rcx
0x180012ecd  mov     r13, [rbp+240h+lpSecurityAttributes]
0x180012ed4  mov     eax, [rbp+240h+arg_30]
0x180012eda  mov     [rbp+240h+dwShareMode], eax
0x180012edd  mov     esi, [rbp+240h+arg_38]
0x180012ee3  xor     r14d, r14d
0x180012ee6  test    r9, r9
0x180012ee9  jnz     short loc_180012F0F
0x180012eeb  lea     edx, [r9+4Bh]; void *
0x180012eef  mov     ebx, 80070057h
0x180012ef4  mov     rcx, [rbp+248h]; this
0x180012efb  mov     r9d, ebx; char *
0x180012efe  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x180012f05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f0a  jmp     loc_1800133B0
0x180012f0f  xor     edx, edx; Val
0x180012f11  mov     r8d, 208h; Size
0x180012f17  lea     rcx, [rbp+240h+FileName]; void *
0x180012f1b  call    memset_0
0x180012f20  test    rbx, rbx
0x180012f23  jnz     short loc_180012F3F
0x180012f25  lea     rcx, [rbp+240h+FileName]; lpFileName
0x180012f29  call    ?UtilGetTempDirPath@@YAJPEA_WK@Z; UtilGetTempDirPath(wchar_t *,ulong)
0x180012f2e  mov     ebx, eax
0x180012f30  test    eax, eax
0x180012f32  jns     short loc_180012F3B
0x180012f34  mov     edx, 50h ; 'P'
0x180012f39  jmp     short loc_180012EF4
0x180012f3b  lea     rbx, [rbp+240h+FileName]
0x180012f3f  cmp     [rbx], r14w
0x180012f43  jnz     short loc_180012F4C
0x180012f45  mov     edx, 59h ; 'Y'
0x180012f4a  jmp     short loc_180012EEF
0x180012f4c  lea     rax, [rsp+340h+var_2F0]
0x180012f51  mov     [rsp+340h+lpFileName], rax
0x180012f56  lea     rax, [rsp+340h+var_2F0]
0x180012f5b  mov     [rsp+340h+var_2F8], rax
0x180012f60  mov     [rsp+340h+var_2F0], r14w
0x180012f66  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012f6a  inc     r8
0x180012f6d  cmp     [rbx+r8*2], r14w
0x180012f72  jnz     short loc_180012F6A
0x180012f74  mov     rdx, rbx
0x180012f77  lea     rcx, [rsp+340h+lpFileName]
0x180012f7c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180012f81  test    al, al
0x180012f83  jnz     short loc_180012F8C
0x180012f85  mov     edx, 5Eh ; '^'
0x180012f8a  jmp     short loc_180012FDF
0x180012f8c  mov     rax, [rsp+340h+var_2F8]
0x180012f91  mov     rcx, [rsp+340h+lpFileName]
0x180012f96  sub     rax, rcx
0x180012f99  sar     rax, 1
0x180012f9c  mov     ebx, 4
0x180012fa1  cmp     rax, rbx
0x180012fa4  jb      short loc_180012FCC
0x180012fa6  mov     r9d, ebx
0x180012fa9  mov     rdx, rcx
0x180012fac  lea     r8, asc_18003B710; "\\\\?\\"
0x180012fb3  movzx   eax, word ptr [rdx]
0x180012fb6  cmp     [r8], ax
0x180012fba  jnz     short loc_180012FCC
0x180012fbc  add     r8, 2
0x180012fc0  add     rdx, 2
0x180012fc4  sub     r9, 1
0x180012fc8  jnz     short loc_180012FB3
0x180012fca  jmp     short loc_180013023
0x180012fcc  lea     rcx, [rsp+340h+lpFileName]
0x180012fd1  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *)
0x180012fd6  test    al, al
0x180012fd8  jnz     short loc_18001301E
0x180012fda  mov     edx, 64h ; 'd'; void *
0x180012fdf  mov     r9d, 8007000Eh; char *
0x180012fe5  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x180012fec  mov     rcx, [rbp+248h]; this
0x180012ff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ff8  nop
0x180012ff9  lea     rax, [rsp+340h+var_2F0]
0x180012ffe  mov     rcx, [rsp+340h+lpFileName]; void *
0x180013003  cmp     rcx, rax
0x180013006  jz      short loc_180013014
0x180013008  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001300f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013014  mov     eax, 8007000Eh
0x180013019  jmp     loc_1800133B2
0x18001301e  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x180013023  call    cs:__imp_GetFileAttributesW
0x180013029  cmp     eax, 0FFFFFFFFh
0x18001302c  jz      loc_180013374
0x180013032  test    al, 10h
0x180013034  jz      loc_180013374
0x18001303a  test    rdi, rdi
0x18001303d  jz      short loc_180013078
0x18001303f  lea     r14, WPP_GLOBAL_Control
0x180013046  mov     rcx, cs:WPP_GLOBAL_Control
0x18001304d  cmp     rcx, r14
0x180013050  jz      short loc_1800130AA
0x180013052  test    [rcx+1Ch], bl
0x180013055  jz      short loc_1800130AA
0x180013057  mov     edx, 0Ah
0x18001305c  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x180013061  mov     r9, [rsp+340h+lpFileName]
0x180013066  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18001306d  mov     rcx, [rcx+10h]
0x180013071  call    WPP_SF_SS
0x180013076  jmp     short loc_1800130AA
0x180013078  lea     r14, WPP_GLOBAL_Control
0x18001307f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013086  cmp     rcx, r14
0x180013089  jz      short loc_1800130AA
0x18001308b  test    [rcx+1Ch], bl
0x18001308e  jz      short loc_1800130AA
0x180013090  mov     edx, 0Bh
0x180013095  mov     r9, [rsp+340h+lpFileName]
0x18001309a  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800130a1  mov     rcx, [rcx+10h]
0x1800130a5  call    WPP_SF_S
0x1800130aa  lea     rcx, [rbp+240h+var_2B0]; wchar_t *
0x1800130ae  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x1800130b3  mov     ebx, eax
0x1800130b5  test    eax, eax
0x1800130b7  jns     short loc_1800130C3
0x1800130b9  mov     edx, 76h ; 'v'
0x1800130be  jmp     loc_18001337E
0x1800130c3  lea     rax, [rsp+340h+var_2D0]
0x1800130c8  mov     [rsp+340h+lpszShortPath], rax
0x1800130cd  lea     rax, [rsp+340h+var_2D0]
0x1800130d2  mov     [rsp+340h+var_2D8], rax
0x1800130d7  xor     eax, eax
0x1800130d9  mov     [rsp+340h+var_2D0], ax
0x1800130de  lea     r9, dword_180039414
0x1800130e5  test    rdi, rdi
0x1800130e8  cmovz   rdi, r9
0x1800130ec  mov     r8, [rsp+340h+lpFileName]
0x1800130f1  mov     rax, [rsp+340h+var_2F8]
0x1800130f6  cmp     r8, rax
0x1800130f9  jz      short loc_18001310A
0x1800130fb  mov     ecx, 5Ch ; '\'
0x180013100  cmp     cx, [rax-2]
0x180013104  jnz     short loc_18001310A
0x180013106  mov     al, 1
0x180013108  jmp     short loc_18001310C
0x18001310a  xor     al, al
0x18001310c  lea     rcx, SubBlock; "\\"
0x180013113  test    al, al
0x180013115  cmovz   r9, rcx
0x180013119  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], rdi
0x18001311e  lea     rax, [rbp+240h+var_2B0]
0x180013122  mov     qword ptr [rsp+340h+dwCreationDisposition], rax; int
0x180013127  lea     rdx, aLsLswerLsTmpLs; "%ls%lsWER.%ls.tmp%ls"
0x18001312e  lea     rcx, [rsp+340h+lpszShortPath]
0x180013133  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180013138  mov     ebx, eax
0x18001313a  test    eax, eax
0x18001313c  jns     short loc_18001317E
0x18001313e  mov     rcx, [rbp+248h]; this
0x180013145  mov     r9d, eax; char *
0x180013148  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x18001314f  mov     edx, 7Fh; void *
0x180013154  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013159  nop
0x18001315a  lea     rax, [rsp+340h+var_2D0]
0x18001315f  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x180013164  cmp     rcx, rax
0x180013167  jz      loc_180013395
0x18001316d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013174  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013179  jmp     loc_180013395
0x18001317e  bts     esi, 7
0x180013182  mov     [rsp+340h+hTemplateFile], 0; hTemplateFile
0x18001318b  mov     [rsp+340h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18001318f  mov     [rsp+340h+dwCreationDisposition], 1; int
0x180013197  mov     r9, r13; lpSecurityAttributes
0x18001319a  mov     r8d, [rbp+240h+dwShareMode]; dwShareMode
0x18001319e  mov     edx, 0C0000000h; dwDesiredAccess
0x1800131a3  mov     rcx, [rsp+340h+lpszShortPath]; lpFileName
0x1800131a8  call    cs:__imp_CreateFileW
0x1800131ae  mov     rbx, rax
0x1800131b1  mov     rsi, rax
0x1800131b4  mov     qword ptr [rbp+240h+dwShareMode], rax
0x1800131b8  lea     rcx, [rax+1]
0x1800131bc  cmp     rcx, 1
0x1800131c0  ja      short loc_1800131E1
0x1800131c2  mov     rcx, [rbp+248h]; this
0x1800131c9  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x1800131d0  mov     edx, 8Ah; void *
0x1800131d5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800131da  mov     ebx, eax
0x1800131dc  jmp     loc_18001315A
0x1800131e1  mov     rdx, rbx; void *
0x1800131e4  mov     rcx, [rsp+340h+lpszShortPath]; wchar_t *
0x1800131e9  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x1800131ee  mov     edi, eax
0x1800131f0  test    eax, eax
0x1800131f2  jns     short loc_180013258
0x1800131f4  mov     edx, 8Eh; void *
0x1800131f9  mov     r9d, edi; char *
0x1800131fc  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x180013203  mov     rcx, [rbp+248h]; this
0x18001320a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001320f  nop
0x180013210  mov     rcx, rbx; hObject
0x180013213  call    cs:__imp_CloseHandle
0x180013219  nop
0x18001321a  lea     rax, [rsp+340h+var_2D0]
0x18001321f  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x180013224  cmp     rcx, rax
0x180013227  jz      short loc_180013236
0x180013229  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013230  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013235  nop
0x180013236  lea     rax, [rsp+340h+var_2F0]
0x18001323b  mov     rcx, [rsp+340h+lpFileName]; void *
0x180013240  cmp     rcx, rax
0x180013243  jz      short loc_180013251
0x180013245  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001324c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013251  mov     eax, edi
0x180013253  jmp     loc_1800133B2
0x180013258  mov     edi, 104h
0x18001325d  mov     r8d, edi; cchBuffer
0x180013260  mov     rdx, r12; lpszLongPath
0x180013263  mov     rcx, [rsp+340h+lpszShortPath]; lpszShortPath
0x180013268  call    cs:__imp_GetLongPathNameW
0x18001326e  dec     eax
0x180013270  cmp     eax, 102h
0x180013275  jbe     short loc_1800132DD
0x180013277  call    cs:__imp_GetLastError
0x18001327d  test    eax, eax
0x18001327f  jle     short loc_180013289
0x180013281  movzx   eax, ax
0x180013284  or      eax, 80070000h
0x180013289  mov     ecx, 80004005h
0x18001328e  test    eax, eax
0x180013290  cmovns  eax, ecx
0x180013293  mov     rcx, cs:WPP_GLOBAL_Control
0x18001329a  cmp     rcx, r14
0x18001329d  jz      short loc_1800132BD
0x18001329f  test    byte ptr [rcx+1Ch], 2
0x1800132a3  jz      short loc_1800132BD
0x1800132a5  mov     edx, 0Ch
0x1800132aa  mov     r9d, eax
0x1800132ad  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800132b4  mov     rcx, [rcx+10h]
0x1800132b8  call    WPP_SF_d
0x1800132bd  mov     r8, [rsp+340h+lpszShortPath]; wchar_t *
0x1800132c2  mov     rdx, rdi; unsigned __int64
0x1800132c5  mov     rcx, r12; wchar_t *
0x1800132c8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800132cd  mov     edi, eax
0x1800132cf  test    eax, eax
0x1800132d1  jns     short loc_1800132DD
0x1800132d3  mov     edx, 9Ah
0x1800132d8  jmp     loc_1800131F9
0x1800132dd  test    r15, r15
0x1800132e0  jz      short loc_1800132FA
0x1800132e2  xor     esi, esi
0x1800132e4  mov     rcx, [r15]; hObject
0x1800132e7  mov     [r15], rbx
0x1800132ea  lea     rax, [rcx+1]
0x1800132ee  cmp     rax, 1
0x1800132f2  jbe     short loc_1800132FA
0x1800132f4  call    cs:__imp_CloseHandle
0x1800132fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180013301  cmp     rcx, r14
0x180013304  jz      short loc_180013325
0x180013306  test    byte ptr [rcx+1Ch], 4
0x18001330a  jz      short loc_180013325
0x18001330c  mov     edx, 0Dh
0x180013311  mov     r9, r12
0x180013314  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18001331b  mov     rcx, [rcx+10h]
0x18001331f  call    WPP_SF_S
0x180013324  nop
0x180013325  lea     rax, [rsi+1]
0x180013329  cmp     rax, 1
0x18001332d  jbe     short loc_180013339
0x18001332f  mov     rcx, rsi; hObject
0x180013332  call    cs:__imp_CloseHandle
0x180013338  nop
0x180013339  lea     rax, [rsp+340h+var_2D0]
0x18001333e  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x180013343  cmp     rcx, rax
0x180013346  jz      short loc_180013355
  ... truncated ...
```
