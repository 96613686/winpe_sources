# UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x180008298`
- end: `0x18000868f`
- name: `?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `1015`
- prototype: ``
- caller_count: `13`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009074`
- `0x180037cb8`
- `0x180044a18`
- `0x180051270`
- `0x1800697d0`
- `0x180077234`
- `0x18007cd68`
- `0x180083350`
- `0x18008f2ec`
- `0x18008fe08`
- `0x180090b54`
- `0x180091940`
- `0x180099f40`

## callees

- `0x180007fd8`
- `0x180008298`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x18000e31c`
- `0x1800170b0`
- `0x180019ebc`
- `0x18001c368`
- `0x180020680`
- `0x180028760`
- `0x18002a758`
- `0x18002d75c`
- `0x18003bb8c`
- `0x18003fb94`
- `0x1800410bc`
- `0x180048b34`
- `0x18004cab0`
- `0x180053300`
- `0x180053d3c`
- `0x18006852c`
- `0x180078910`
- `0x18009a5dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ae`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180008599`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180008599`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008518`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008518`

## string_xrefs

- `0x180008302`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x1800083c0`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x1800084ca`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18000853a`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x180008571`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilGetTempFile(
        __int64 a1,
        WCHAR *a2,
        const size_t *a3,
        WCHAR *a4,
        __int64 a5,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD a7,
        int a8)
{
  __int64 v12; // rdx
  unsigned int TempDirPath; // ebx
  unsigned int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int64 v18; // r9
  int AsString; // eax
  const WCHAR *v20; // r9
  int v21; // eax
  HANDLE FileW; // rax
  const char *v23; // r9
  int v24; // eax
  __int64 v25; // rdx
  DWORD LastError; // eax
  unsigned int v27; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  DWORD dwShareMode[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v34[5]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t v35[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  dwShareMode[0] = a7;
  if ( a4 )
  {
    memset_0(FileName, 0, 0x208u);
    if ( !a2 )
    {
      TempDirPath = UtilGetTempDirPath(FileName, v14);
      if ( (TempDirPath & 0x80000000) != 0 )
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
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v34);
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v34, a2) )
    {
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(v34)
        || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(
                              v34,
                              v16,
                              v17,
                              4) )
      {
        if ( UtilPathIsDirectory(v34[0]) )
        {
          if ( a3 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                (unsigned int)WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
                v34[0],
                (__int64)a3);
          }
          else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, v34[0]);
          }
          AsString = UtilUuidCreateAsString(v35);
          TempDirPath = AsString;
          if ( AsString >= 0 )
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
            if ( !a3 )
              a3 = &Src;
            if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(v34) )
              v20 = L"\\";
            v21 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    lpFileName,
                    L"%ls%lsWER.%ls.tmp%ls",
                    v34[0],
                    v20,
                    v35,
                    a3);
            TempDirPath = v21;
            if ( v21 >= 0 )
            {
              FileW = CreateFileW(lpFileName[0], 0xC0000000, dwShareMode[0], lpSecurityAttributes, 1u, a8 | 0x80u, 0);
              *(_QWORD *)dwShareMode = FileW;
              if ( (unsigned __int64)FileW + 1 > 1 )
              {
                v24 = UtilVerifyFilePath(lpFileName[0], FileW);
                TempDirPath = v24;
                if ( v24 >= 0 )
                {
                  if ( GetLongPathNameW(lpFileName[0], a4, 0x104u) - 1 <= 0x102 )
                    goto LABEL_48;
                  LastError = GetLastError();
                  v27 = ERROR_HR_FROM_WIN32(LastError);
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      12,
                      WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
                      v27);
                  v24 = StringCchCopyW(a4, 0x104u, lpFileName[0]);
                  TempDirPath = v24;
                  if ( v24 >= 0 )
                  {
LABEL_48:
                    if ( a1 )
                      tlx::unique_any<tlx::file_handle_traits>::operator=(a1, dwShareMode);
                    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        13,
                        WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
                        a4);
                    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(dwShareMode);
                    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
                    TempDirPath = 0;
                    goto LABEL_54;
                  }
                  v25 = 154;
                }
                else
                {
                  v25 = 142;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v25,
                  (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
                  (const char *)(unsigned int)v24,
                  dwCreationDispositionb);
              }
              else
              {
                TempDirPath = wil::details::in1diag3::Return_GetLastError(
                                retaddr,
                                (void *)0x8A,
                                (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
                                v23);
              }
              tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(dwShareMode);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x7F,
                (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
                (const char *)(unsigned int)v21,
                dwCreationDispositiona);
            }
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
LABEL_54:
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v34);
            return TempDirPath;
          }
          v18 = (unsigned int)AsString;
          v15 = 118;
LABEL_19:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
            (const char *)v18,
            dwCreationDisposition);
          goto LABEL_54;
        }
        TempDirPath = -2147024809;
        v15 = 106;
      }
      else
      {
        TempDirPath = -2147024882;
        v15 = 100;
      }
    }
    else
    {
      TempDirPath = -2147024882;
      v15 = 94;
    }
    v18 = TempDirPath;
    goto LABEL_19;
  }
  v12 = 75;
LABEL_3:
  TempDirPath = -2147024809;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
    (const char *)TempDirPath,
    dwCreationDisposition);
  return TempDirPath;
}

```

## disassembly

```asm
0x180008298  push    rbp
0x18000829a  push    rbx
0x18000829b  push    rsi
0x18000829c  push    rdi
0x18000829d  push    r12
0x18000829f  push    r13
0x1800082a1  push    r14
0x1800082a3  push    r15
0x1800082a5  lea     rbp, [rsp-208h]
0x1800082ad  sub     rsp, 308h
0x1800082b4  mov     rax, cs:__security_cookie
0x1800082bb  xor     rax, rsp
0x1800082be  mov     [rbp+240h+var_50], rax
0x1800082c5  mov     rsi, r9
0x1800082c8  mov     r14, r8
0x1800082cb  mov     rbx, rdx
0x1800082ce  mov     r12, rcx
0x1800082d1  mov     r13, [rbp+240h+lpSecurityAttributes]
0x1800082d8  mov     eax, [rbp+240h+arg_30]
0x1800082de  mov     [rsp+340h+dwShareMode], eax
0x1800082e2  mov     r15d, [rbp+240h+arg_38]
0x1800082e9  xor     edi, edi
0x1800082eb  test    r9, r9
0x1800082ee  jnz     short loc_180008313
0x1800082f0  lea     edx, [rdi+4Bh]; void *
0x1800082f3  mov     ebx, 80070057h
0x1800082f8  mov     rcx, [rbp+248h]; this
0x1800082ff  mov     r9d, ebx; char *
0x180008302  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x180008309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000830e  jmp     loc_180008669
0x180008313  xor     edx, edx; Val
0x180008315  mov     r8d, 208h; Size
0x18000831b  lea     rcx, [rbp+240h+FileName]; void *
0x18000831f  call    memset_0
0x180008324  test    rbx, rbx
0x180008327  jnz     short loc_180008343
0x180008329  lea     rcx, [rbp+240h+FileName]; lpFileName
0x18000832d  call    ?UtilGetTempDirPath@@YAJPEA_WK@Z; UtilGetTempDirPath(wchar_t *,ulong)
0x180008332  mov     ebx, eax
0x180008334  test    eax, eax
0x180008336  jns     short loc_18000833F
0x180008338  mov     edx, 50h ; 'P'
0x18000833d  jmp     short loc_1800082F8
0x18000833f  lea     rbx, [rbp+240h+FileName]
0x180008343  cmp     [rbx], di
0x180008346  jnz     short loc_18000834F
0x180008348  mov     edx, 59h ; 'Y'
0x18000834d  jmp     short loc_1800082F3
0x18000834f  lea     rcx, [rsp+340h+var_2D8]; void *
0x180008354  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180008359  nop
0x18000835a  mov     rdx, rbx
0x18000835d  lea     rcx, [rsp+340h+var_2D8]
0x180008362  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180008367  test    al, al
0x180008369  jnz     short loc_180008377
0x18000836b  mov     ebx, 8007000Eh
0x180008370  mov     edx, 5Eh ; '^'
0x180008375  jmp     short loc_1800083BD
0x180008377  lea     rcx, [rsp+340h+var_2D8]
0x18000837c  call    ?starts_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(wchar_t const *)
0x180008381  test    al, al
0x180008383  jnz     short loc_1800083A5
0x180008385  mov     r9d, 4
0x18000838b  lea     rcx, [rsp+340h+var_2D8]
0x180008390  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *,unsigned __int64)
0x180008395  test    al, al
0x180008397  jnz     short loc_1800083A5
0x180008399  mov     ebx, 8007000Eh
0x18000839e  mov     edx, 64h ; 'd'
0x1800083a3  jmp     short loc_1800083BD
0x1800083a5  mov     rcx, [rsp+340h+var_2D8]; wchar_t *
0x1800083aa  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x1800083af  test    al, al
0x1800083b1  jnz     short loc_1800083D8
0x1800083b3  mov     ebx, 80070057h
0x1800083b8  mov     edx, 6Ah ; 'j'; void *
0x1800083bd  mov     r9d, ebx; char *
0x1800083c0  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x1800083c7  mov     rcx, [rbp+248h]; this
0x1800083ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083d3  jmp     loc_18000865F
0x1800083d8  test    r14, r14
0x1800083db  jz      short loc_180008417
0x1800083dd  lea     rdi, WPP_GLOBAL_Control
0x1800083e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083eb  cmp     rcx, rdi
0x1800083ee  jz      short loc_18000844A
0x1800083f0  test    byte ptr [rcx+1Ch], 4
0x1800083f4  jz      short loc_18000844A
0x1800083f6  mov     edx, 0Ah
0x1800083fb  mov     qword ptr [rsp+340h+dwCreationDisposition], r14
0x180008400  mov     r9, [rsp+340h+var_2D8]
0x180008405  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000840c  mov     rcx, [rcx+10h]
0x180008410  call    WPP_SF_SS
0x180008415  jmp     short loc_18000844A
0x180008417  lea     rdi, WPP_GLOBAL_Control
0x18000841e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008425  cmp     rcx, rdi
0x180008428  jz      short loc_18000844A
0x18000842a  test    byte ptr [rcx+1Ch], 4
0x18000842e  jz      short loc_18000844A
0x180008430  mov     edx, 0Bh
0x180008435  mov     r9, [rsp+340h+var_2D8]
0x18000843a  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x180008441  mov     rcx, [rcx+10h]
0x180008445  call    WPP_SF_S
0x18000844a  lea     rcx, [rbp+240h+var_2B0]; wchar_t *
0x18000844e  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x180008453  mov     ebx, eax
0x180008455  test    eax, eax
0x180008457  jns     short loc_180008466
0x180008459  mov     r9d, eax
0x18000845c  mov     edx, 76h ; 'v'
0x180008461  jmp     loc_1800083C0
0x180008466  lea     rcx, [rsp+340h+lpFileName]; void *
0x18000846b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180008470  nop
0x180008471  lea     r9, Src
0x180008478  test    r14, r14
0x18000847b  cmovz   r14, r9
0x18000847f  lea     rcx, [rsp+340h+var_2D8]
0x180008484  call    ?ends_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(wchar_t)
0x180008489  lea     rcx, SubBlock; "\\"
0x180008490  test    al, al
0x180008492  cmovz   r9, rcx
0x180008496  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], r14
0x18000849b  lea     rax, [rbp+240h+var_2B0]
0x18000849f  mov     qword ptr [rsp+340h+dwCreationDisposition], rax; int
0x1800084a4  mov     r8, [rsp+340h+var_2D8]
0x1800084a9  lea     rdx, aLsLswerLsTmpLs; "%ls%lsWER.%ls.tmp%ls"
0x1800084b0  lea     rcx, [rsp+340h+lpFileName]
0x1800084b5  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800084ba  mov     ebx, eax
0x1800084bc  test    eax, eax
0x1800084be  jns     short loc_1800084EB
0x1800084c0  mov     rcx, [rbp+248h]; this
0x1800084c7  mov     r9d, eax; char *
0x1800084ca  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x1800084d1  mov     edx, 7Fh; void *
0x1800084d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084db  nop
0x1800084dc  lea     rcx, [rsp+340h+lpFileName]; void *
0x1800084e1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800084e6  jmp     loc_18000865F
0x1800084eb  bts     r15d, 7
0x1800084f0  mov     [rsp+340h+hTemplateFile], 0; hTemplateFile
0x1800084f9  mov     [rsp+340h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800084fe  mov     [rsp+340h+dwCreationDisposition], 1; int
0x180008506  mov     r9, r13; lpSecurityAttributes
0x180008509  mov     r8d, [rsp+340h+dwShareMode]; dwShareMode
0x18000850e  mov     edx, 0C0000000h; dwDesiredAccess
0x180008513  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x180008518  call    cs:__imp_CreateFileW
0x18000851f  nop     dword ptr [rax+rax+00h]
0x180008524  mov     qword ptr [rsp+340h+dwShareMode], rax
0x180008529  lea     rcx, [rax+1]
0x18000852d  cmp     rcx, 1
0x180008531  ja      short loc_180008559
0x180008533  mov     rcx, [rbp+248h]; this
0x18000853a  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x180008541  mov     edx, 8Ah; void *
0x180008546  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000854b  mov     ebx, eax
0x18000854d  lea     rcx, [rsp+340h+dwShareMode]
0x180008552  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180008557  jmp     short loc_1800084DC
0x180008559  mov     rdx, rax; void *
0x18000855c  mov     rcx, [rsp+340h+lpFileName]; wchar_t *
0x180008561  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x180008566  mov     ebx, eax
0x180008568  test    eax, eax
0x18000856a  jns     short loc_180008589
0x18000856c  mov     edx, 8Eh; void *
0x180008571  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x180008578  mov     r9d, eax; char *
0x18000857b  mov     rcx, [rbp+248h]; this
0x180008582  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008587  jmp     short loc_18000854D
0x180008589  mov     ebx, 104h
0x18000858e  mov     r8d, ebx; cchBuffer
0x180008591  mov     rdx, rsi; lpszLongPath
0x180008594  mov     rcx, [rsp+340h+lpFileName]; lpszShortPath
0x180008599  call    cs:__imp_GetLongPathNameW
0x1800085a0  nop     dword ptr [rax+rax+00h]
0x1800085a5  dec     eax
0x1800085a7  cmp     eax, 102h
0x1800085ac  jbe     short loc_18000860B
0x1800085ae  call    cs:__imp_GetLastError
0x1800085b5  nop     dword ptr [rax+rax+00h]
0x1800085ba  mov     ecx, eax; unsigned int
0x1800085bc  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800085c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085c8  cmp     rcx, rdi
0x1800085cb  jz      short loc_1800085EB
0x1800085cd  test    byte ptr [rcx+1Ch], 2
0x1800085d1  jz      short loc_1800085EB
0x1800085d3  mov     edx, 0Ch
0x1800085d8  mov     r9d, eax
0x1800085db  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x1800085e2  mov     rcx, [rcx+10h]
0x1800085e6  call    WPP_SF_d
0x1800085eb  mov     r8, [rsp+340h+lpFileName]; wchar_t *
0x1800085f0  mov     rdx, rbx; unsigned __int64
0x1800085f3  mov     rcx, rsi; wchar_t *
0x1800085f6  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800085fb  mov     ebx, eax
0x1800085fd  test    eax, eax
0x1800085ff  jns     short loc_18000860B
0x180008601  mov     edx, 9Ah
0x180008606  jmp     loc_180008571
0x18000860b  test    r12, r12
0x18000860e  jz      short loc_18000861D
0x180008610  lea     rdx, [rsp+340h+dwShareMode]
0x180008615  mov     rcx, r12
0x180008618  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x18000861d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008624  cmp     rcx, rdi
0x180008627  jz      short loc_180008648
0x180008629  test    byte ptr [rcx+1Ch], 4
0x18000862d  jz      short loc_180008648
0x18000862f  mov     edx, 0Dh
0x180008634  mov     r9, rsi
0x180008637  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18000863e  mov     rcx, [rcx+10h]
0x180008642  call    WPP_SF_S
0x180008647  nop
0x180008648  lea     rcx, [rsp+340h+dwShareMode]
0x18000864d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180008652  nop
0x180008653  lea     rcx, [rsp+340h+lpFileName]; void *
0x180008658  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18000865d  xor     ebx, ebx
0x18000865f  lea     rcx, [rsp+340h+var_2D8]; void *
0x180008664  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180008669  mov     eax, ebx
0x18000866b  mov     rcx, [rbp+240h+var_50]
0x180008672  xor     rcx, rsp; StackCookie
0x180008675  call    __security_check_cookie
0x18000867a  add     rsp, 308h
0x180008681  pop     r15
0x180008683  pop     r14
0x180008685  pop     r13
0x180008687  pop     r12
0x180008689  pop     rdi
0x18000868a  pop     rsi
0x18000868b  pop     rbx
0x18000868c  pop     rbp
0x18000868d  retn
```
