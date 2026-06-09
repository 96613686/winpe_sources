# UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x18001bbc4`
- end: `0x18001bfa8`
- name: `?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `996`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b280`
- `0x180035ce0`
- `0x1800433d0`
- `0x18004ee3c`
- `0x180066710`
- `0x180073de8`
- `0x180079790`
- `0x18007f868`
- `0x18008b42c`
- `0x18008bf00`
- `0x18008cbfc`
- `0x18008d960`
- `0x180095cb0`

## callees

- `0x18000716c`
- `0x1800072cc`
- `0x180007e10`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x180013730`
- `0x180016468`
- `0x18001bbc4`
- `0x18001fe24`
- `0x180027884`
- `0x18002be60`
- `0x180039950`
- `0x18003db78`
- `0x18003f0c0`
- `0x180046d74`
- `0x18004ac4c`
- `0x180050db0`
- `0x1800517cc`
- `0x1800654ec`
- `0x180075484`
- `0x18009633c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bece`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001bebf`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001bebf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001be44`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001be44`

## string_xrefs

- `0x18001bc2e`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18001bcec`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18001bdf6`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18001be60`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18001be97`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilGetTempFile(
        void **a1,
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
  int v14; // edx
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
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v34) )
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
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
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
                v24 = UtilVerifyFilePath((WCHAR *)lpFileName[0], FileW);
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
                      tlx::unique_any<tlx::file_handle_traits>::operator=(a1, (void **)dwShareMode);
                    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids);
                    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)dwShareMode);
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
              tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)dwShareMode);
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
0x18001bbc4  push    rbp
0x18001bbc6  push    rbx
0x18001bbc7  push    rsi
0x18001bbc8  push    rdi
0x18001bbc9  push    r12
0x18001bbcb  push    r13
0x18001bbcd  push    r14
0x18001bbcf  push    r15
0x18001bbd1  lea     rbp, [rsp-208h]
0x18001bbd9  sub     rsp, 308h
0x18001bbe0  mov     rax, cs:__security_cookie
0x18001bbe7  xor     rax, rsp
0x18001bbea  mov     [rbp+240h+var_50], rax
0x18001bbf1  mov     rsi, r9
0x18001bbf4  mov     r14, r8
0x18001bbf7  mov     rbx, rdx
0x18001bbfa  mov     r12, rcx
0x18001bbfd  mov     r13, [rbp+240h+lpSecurityAttributes]
0x18001bc04  mov     eax, [rbp+240h+arg_30]
0x18001bc0a  mov     [rsp+340h+dwShareMode], eax
0x18001bc0e  mov     r15d, [rbp+240h+arg_38]
0x18001bc15  xor     edi, edi
0x18001bc17  test    r9, r9
0x18001bc1a  jnz     short loc_18001BC3F
0x18001bc1c  lea     edx, [rdi+4Bh]; void *
0x18001bc1f  mov     ebx, 80070057h
0x18001bc24  mov     rcx, [rbp+248h]; this
0x18001bc2b  mov     r9d, ebx; char *
0x18001bc2e  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x18001bc35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc3a  jmp     loc_18001BF83
0x18001bc3f  xor     edx, edx; Val
0x18001bc41  mov     r8d, 208h; Size
0x18001bc47  lea     rcx, [rbp+240h+FileName]; void *
0x18001bc4b  call    memset_0
0x18001bc50  test    rbx, rbx
0x18001bc53  jnz     short loc_18001BC6F
0x18001bc55  lea     rcx, [rbp+240h+FileName]; lpFileName
0x18001bc59  call    ?UtilGetTempDirPath@@YAJPEA_WK@Z; UtilGetTempDirPath(wchar_t *,ulong)
0x18001bc5e  mov     ebx, eax
0x18001bc60  test    eax, eax
0x18001bc62  jns     short loc_18001BC6B
0x18001bc64  mov     edx, 50h ; 'P'
0x18001bc69  jmp     short loc_18001BC24
0x18001bc6b  lea     rbx, [rbp+240h+FileName]
0x18001bc6f  cmp     [rbx], di
0x18001bc72  jnz     short loc_18001BC7B
0x18001bc74  mov     edx, 59h ; 'Y'
0x18001bc79  jmp     short loc_18001BC1F
0x18001bc7b  lea     rcx, [rsp+340h+var_2D8]; void *
0x18001bc80  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001bc85  nop
0x18001bc86  mov     rdx, rbx
0x18001bc89  lea     rcx, [rsp+340h+var_2D8]
0x18001bc8e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18001bc93  test    al, al
0x18001bc95  jnz     short loc_18001BCA3
0x18001bc97  mov     ebx, 8007000Eh
0x18001bc9c  mov     edx, 5Eh ; '^'
0x18001bca1  jmp     short loc_18001BCE9
0x18001bca3  lea     rcx, [rsp+340h+var_2D8]
0x18001bca8  call    ?starts_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(wchar_t const *)
0x18001bcad  test    al, al
0x18001bcaf  jnz     short loc_18001BCD1
0x18001bcb1  mov     r9d, 4
0x18001bcb7  lea     rcx, [rsp+340h+var_2D8]
0x18001bcbc  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *,unsigned __int64)
0x18001bcc1  test    al, al
0x18001bcc3  jnz     short loc_18001BCD1
0x18001bcc5  mov     ebx, 8007000Eh
0x18001bcca  mov     edx, 64h ; 'd'
0x18001bccf  jmp     short loc_18001BCE9
0x18001bcd1  mov     rcx, [rsp+340h+var_2D8]; wchar_t *
0x18001bcd6  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x18001bcdb  test    al, al
0x18001bcdd  jnz     short loc_18001BD04
0x18001bcdf  mov     ebx, 80070057h
0x18001bce4  mov     edx, 6Ah ; 'j'; void *
0x18001bce9  mov     r9d, ebx; char *
0x18001bcec  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x18001bcf3  mov     rcx, [rbp+248h]; this
0x18001bcfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bcff  jmp     loc_18001BF79
0x18001bd04  test    r14, r14
0x18001bd07  jz      short loc_18001BD43
0x18001bd09  lea     rdi, WPP_GLOBAL_Control
0x18001bd10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd17  cmp     rcx, rdi
0x18001bd1a  jz      short loc_18001BD76
0x18001bd1c  test    byte ptr [rcx+1Ch], 4
0x18001bd20  jz      short loc_18001BD76
0x18001bd22  mov     edx, 0Ah
0x18001bd27  mov     qword ptr [rsp+340h+dwCreationDisposition], r14
0x18001bd2c  mov     r9, [rsp+340h+var_2D8]
0x18001bd31  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18001bd38  mov     rcx, [rcx+10h]
0x18001bd3c  call    WPP_SF_SS
0x18001bd41  jmp     short loc_18001BD76
0x18001bd43  lea     rdi, WPP_GLOBAL_Control
0x18001bd4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd51  cmp     rcx, rdi
0x18001bd54  jz      short loc_18001BD76
0x18001bd56  test    byte ptr [rcx+1Ch], 4
0x18001bd5a  jz      short loc_18001BD76
0x18001bd5c  mov     edx, 0Bh
0x18001bd61  mov     r9, [rsp+340h+var_2D8]
0x18001bd66  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18001bd6d  mov     rcx, [rcx+10h]
0x18001bd71  call    WPP_SF_S
0x18001bd76  lea     rcx, [rbp+240h+var_2B0]; wchar_t *
0x18001bd7a  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x18001bd7f  mov     ebx, eax
0x18001bd81  test    eax, eax
0x18001bd83  jns     short loc_18001BD92
0x18001bd85  mov     r9d, eax
0x18001bd88  mov     edx, 76h ; 'v'
0x18001bd8d  jmp     loc_18001BCEC
0x18001bd92  lea     rcx, [rsp+340h+lpFileName]; void *
0x18001bd97  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001bd9c  nop
0x18001bd9d  lea     r9, Src
0x18001bda4  test    r14, r14
0x18001bda7  cmovz   r14, r9
0x18001bdab  lea     rcx, [rsp+340h+var_2D8]
0x18001bdb0  call    ?ends_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(wchar_t)
0x18001bdb5  lea     rcx, SubBlock; "\\"
0x18001bdbc  test    al, al
0x18001bdbe  cmovz   r9, rcx
0x18001bdc2  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], r14
0x18001bdc7  lea     rax, [rbp+240h+var_2B0]
0x18001bdcb  mov     qword ptr [rsp+340h+dwCreationDisposition], rax; int
0x18001bdd0  mov     r8, [rsp+340h+var_2D8]
0x18001bdd5  lea     rdx, aLsLswerLsTmpLs; "%ls%lsWER.%ls.tmp%ls"
0x18001bddc  lea     rcx, [rsp+340h+lpFileName]
0x18001bde1  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18001bde6  mov     ebx, eax
0x18001bde8  test    eax, eax
0x18001bdea  jns     short loc_18001BE17
0x18001bdec  mov     rcx, [rbp+248h]; this
0x18001bdf3  mov     r9d, eax; char *
0x18001bdf6  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x18001bdfd  mov     edx, 7Fh; void *
0x18001be02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be07  nop
0x18001be08  lea     rcx, [rsp+340h+lpFileName]; void *
0x18001be0d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001be12  jmp     loc_18001BF79
0x18001be17  bts     r15d, 7
0x18001be1c  mov     [rsp+340h+hTemplateFile], 0; hTemplateFile
0x18001be25  mov     [rsp+340h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18001be2a  mov     [rsp+340h+dwCreationDisposition], 1; int
0x18001be32  mov     r9, r13; lpSecurityAttributes
0x18001be35  mov     r8d, [rsp+340h+dwShareMode]; dwShareMode
0x18001be3a  mov     edx, 0C0000000h; dwDesiredAccess
0x18001be3f  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x18001be44  call    cs:__imp_CreateFileW
0x18001be4a  mov     qword ptr [rsp+340h+dwShareMode], rax
0x18001be4f  lea     rcx, [rax+1]
0x18001be53  cmp     rcx, 1
0x18001be57  ja      short loc_18001BE7F
0x18001be59  mov     rcx, [rbp+248h]; this
0x18001be60  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x18001be67  mov     edx, 8Ah; void *
0x18001be6c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001be71  mov     ebx, eax
0x18001be73  lea     rcx, [rsp+340h+dwShareMode]
0x18001be78  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001be7d  jmp     short loc_18001BE08
0x18001be7f  mov     rdx, rax; void *
0x18001be82  mov     rcx, [rsp+340h+lpFileName]; wchar_t *
0x18001be87  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18001be8c  mov     ebx, eax
0x18001be8e  test    eax, eax
0x18001be90  jns     short loc_18001BEAF
0x18001be92  mov     edx, 8Eh; void *
0x18001be97  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\commo"...
0x18001be9e  mov     r9d, eax; char *
0x18001bea1  mov     rcx, [rbp+248h]; this
0x18001bea8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bead  jmp     short loc_18001BE73
0x18001beaf  mov     ebx, 104h
0x18001beb4  mov     r8d, ebx; cchBuffer
0x18001beb7  mov     rdx, rsi; lpszLongPath
0x18001beba  mov     rcx, [rsp+340h+lpFileName]; lpszShortPath
0x18001bebf  call    cs:__imp_GetLongPathNameW
0x18001bec5  dec     eax
0x18001bec7  cmp     eax, 102h
0x18001becc  jbe     short loc_18001BF25
0x18001bece  call    cs:__imp_GetLastError
0x18001bed4  mov     ecx, eax; unsigned int
0x18001bed6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001bedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bee2  cmp     rcx, rdi
0x18001bee5  jz      short loc_18001BF05
0x18001bee7  test    byte ptr [rcx+1Ch], 2
0x18001beeb  jz      short loc_18001BF05
0x18001beed  mov     edx, 0Ch
0x18001bef2  mov     r9d, eax
0x18001bef5  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18001befc  mov     rcx, [rcx+10h]
0x18001bf00  call    WPP_SF_d
0x18001bf05  mov     r8, [rsp+340h+lpFileName]; wchar_t *
0x18001bf0a  mov     rdx, rbx; unsigned __int64
0x18001bf0d  mov     rcx, rsi; wchar_t *
0x18001bf10  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001bf15  mov     ebx, eax
0x18001bf17  test    eax, eax
0x18001bf19  jns     short loc_18001BF25
0x18001bf1b  mov     edx, 9Ah
0x18001bf20  jmp     loc_18001BE97
0x18001bf25  test    r12, r12
0x18001bf28  jz      short loc_18001BF37
0x18001bf2a  lea     rdx, [rsp+340h+dwShareMode]
0x18001bf2f  mov     rcx, r12
0x18001bf32  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x18001bf37  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf3e  cmp     rcx, rdi
0x18001bf41  jz      short loc_18001BF62
0x18001bf43  test    byte ptr [rcx+1Ch], 4
0x18001bf47  jz      short loc_18001BF62
0x18001bf49  mov     edx, 0Dh
0x18001bf4e  mov     r9, rsi
0x18001bf51  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18001bf58  mov     rcx, [rcx+10h]
0x18001bf5c  call    WPP_SF_S
0x18001bf61  nop
0x18001bf62  lea     rcx, [rsp+340h+dwShareMode]
0x18001bf67  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001bf6c  nop
0x18001bf6d  lea     rcx, [rsp+340h+lpFileName]; void *
0x18001bf72  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001bf77  xor     ebx, ebx
0x18001bf79  lea     rcx, [rsp+340h+var_2D8]; void *
0x18001bf7e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001bf83  mov     eax, ebx
0x18001bf85  mov     rcx, [rbp+240h+var_50]
0x18001bf8c  xor     rcx, rsp; StackCookie
0x18001bf8f  call    __security_check_cookie
0x18001bf94  add     rsp, 308h
0x18001bf9b  pop     r15
0x18001bf9d  pop     r14
0x18001bf9f  pop     r13
0x18001bfa1  pop     r12
0x18001bfa3  pop     rdi
0x18001bfa4  pop     rsi
0x18001bfa5  pop     rbx
0x18001bfa6  pop     rbp
0x18001bfa7  retn
```
