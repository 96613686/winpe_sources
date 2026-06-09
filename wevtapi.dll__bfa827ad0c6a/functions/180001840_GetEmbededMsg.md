# GetEmbededMsg

- ea: `0x180001840`
- end: `0x180001d4f`
- name: `GetEmbededMsg`
- size: `1295`
- prototype: `__int64 __usercall@<rax>(BinXmlReader *this@<rcx>, LCID Locale@<edx>, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180007fb8`

## callees

- `0x180001840`
- `0x180003a68`
- `0x180007ae4`
- `0x18000a100`
- `0x18000a558`
- `0x18000bf5c`
- `0x18000bf84`
- `0x18000f2b0`
- `0x180023548`
- `0x180024a50`
- `0x180027fe0`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000196b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180001986`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000196b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180001986`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180001950`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180001950`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall GetEmbededMsg(BinXmlReader *this, LCID Locale, _BYTE *a3, int a4, _QWORD *a5)
{
  unsigned __int64 i; // rcx
  __int64 v10; // rax
  char v11; // di
  unsigned int v13; // ecx
  int v14; // edx
  __int64 v15; // rdx
  __int128 pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h]
  int v18; // [rsp+38h] [rbp-C8h]
  int v19; // [rsp+3Ch] [rbp-C4h]
  int v20; // [rsp+40h] [rbp-C0h]
  void **v21; // [rsp+48h] [rbp-B8h] BYREF
  void *v22; // [rsp+50h] [rbp-B0h]
  int v23; // [rsp+58h] [rbp-A8h]
  int v24; // [rsp+5Ch] [rbp-A4h]
  char v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v27; // [rsp+78h] [rbp-88h]
  _DWORD v28[25]; // [rsp+7Ch] [rbp-84h]
  __int64 v29; // [rsp+E0h] [rbp-20h]
  __int64 v30; // [rsp+F0h] [rbp-10h]
  int v31; // [rsp+FCh] [rbp-4h]
  WCHAR LCData[56]; // [rsp+100h] [rbp+0h] BYREF

  for ( i = 0; i < 9; ++i )
  {
    v10 = 2 * i;
    *(&v26 + v10) = 0;
    v28[2 * v10 - 1] = -1;
    v28[2 * v10] = 0;
  }
  v21 = &Buffer::`vftable';
  v23 = 0;
  v25 = 0;
  v22 = &v26;
  v24 = 144;
  BinXmlReader::Reset(this);
  BinXmlExtractor::Process((BinXmlExtractor *)qword_18004B680, this, &v21);
  *a3 = 0;
  v11 = 0;
  if ( v28[0] != 1 )
  {
    if ( v31 == 1 && a4 == 1 && v30 )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a5,
                               v30)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               a5,
                               0) )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, 14);
        }
        pExceptionObject = 0;
        v17 = 0;
        v18 = 14;
        v19 = -1;
        v20 = 498;
        throw (EvtException *)&pExceptionObject;
      }
      v11 = 1;
      *a3 = 1;
    }
    goto LABEL_5;
  }
  if ( v26 )
  {
    GetLocaleInfoW(Locale, 0x5Cu, LCData, 50);
    if ( v27 < 0x32 && (!(unsigned int)_o__wcsnicmp(LCData, v26, v27) || !(unsigned int)_o__wcsnicmp(L"zxx", v26, v27)) )
      *a3 = 1;
    v13 = 4;
    if ( (unsigned int)(a4 - 1) <= 4 )
    {
      switch ( a4 )
      {
        case 1:
          v13 = 1;
          break;
        case 2:
          v13 = 2;
          break;
        case 3:
          v13 = 3;
          break;
        default:
          if ( a4 != 4 )
          {
            switch ( a4 )
            {
              case 5:
                v13 = 7;
                break;
              case 6:
                v13 = 5;
                break;
              case 7:
                v13 = 6;
                break;
              default:
                Buffer::~Buffer((Buffer *)&v21);
                return 0;
            }
          }
          break;
      }
      v14 = v28[4 * v13];
      if ( v14 )
      {
        if ( v13 >= 7 )
        {
          if ( v14 == 1 && v29 )
          {
            if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                     a5,
                                     v29)
              || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                     a5,
                                     0) )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, 14);
              }
              pExceptionObject = 0;
              v17 = 0;
              v18 = 14;
              v19 = -1;
              v20 = 464;
              throw (EvtException *)&pExceptionObject;
            }
            if ( a5[1] != *a5
              && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                     a5,
                                     0) )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, 14);
              }
              pExceptionObject = 0;
              v17 = 0;
              v18 = 14;
              v19 = -1;
              v20 = 472;
              throw (EvtException *)&pExceptionObject;
            }
            goto LABEL_58;
          }
        }
        else if ( v14 == 1 )
        {
          v15 = *(&v26 + 2 * v13);
          if ( v15 )
          {
            if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                     a5,
                                     v15)
              || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                     a5,
                                     0) )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, 14);
              }
              pExceptionObject = 0;
              v17 = 0;
              v18 = 14;
              v19 = -1;
              v20 = 424;
              throw (EvtException *)&pExceptionObject;
            }
            if ( a4 == 1 )
              FromEscapedChars(a5);
            if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                     a5,
                                     0) )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, 14);
              }
              pExceptionObject = 0;
              v17 = 0;
              v18 = 14;
              v19 = -1;
              v20 = 434;
              throw (EvtException *)&pExceptionObject;
            }
LABEL_58:
            v11 = 1;
          }
        }
      }
    }
  }
LABEL_5:
  v21 = &Buffer::`vftable';
  if ( v25 )
    operator delete(v22);
  return v11;
}

```

## disassembly

```asm
0x180001840  push    rbp
0x180001842  push    rbx
0x180001843  push    rsi
0x180001844  push    rdi
0x180001845  push    r12
0x180001847  push    r14
0x180001849  push    r15
0x18000184b  lea     rbp, [rsp-80h]
0x180001850  sub     rsp, 180h
0x180001857  mov     rax, cs:__security_cookie
0x18000185e  xor     rax, rsp
0x180001861  mov     [rbp+0B0h+var_40], rax
0x180001865  mov     r14d, r9d
0x180001868  mov     rsi, r8
0x18000186b  mov     r15d, edx
0x18000186e  mov     rdi, rcx
0x180001871  mov     rbx, [rbp+0B0h+arg_20]
0x180001878  xor     r12d, r12d
0x18000187b  mov     ecx, r12d
0x18000187e  mov     rax, rcx
0x180001881  add     rax, rax
0x180001884  mov     [rsp+rax*8+1B0h+var_140], r12
0x180001889  mov     [rsp+rax*8+1B0h+var_138], 0FFFFFFFFh
0x180001891  mov     [rsp+rax*8+1B0h+var_134], r12d
0x180001896  inc     rcx
0x180001899  cmp     rcx, 9
0x18000189d  jb      short loc_18000187E
0x18000189f  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x1800018a6  mov     [rsp+1B0h+var_168], rax
0x1800018ab  mov     [rsp+1B0h+var_158], r12d
0x1800018b0  mov     [rsp+1B0h+var_150], r12b
0x1800018b5  lea     rax, [rsp+1B0h+var_140]
0x1800018ba  mov     [rsp+1B0h+var_160], rax
0x1800018bf  mov     [rsp+1B0h+var_154], 90h
0x1800018c7  mov     rcx, rdi; this
0x1800018ca  call    ?Reset@BinXmlReader@@QEAAXXZ; BinXmlReader::Reset(void)
0x1800018cf  lea     r8, [rsp+1B0h+var_168]; void *
0x1800018d4  mov     rdx, rdi; struct BinXmlReader *
0x1800018d7  lea     rcx, qword_18004B680; this
0x1800018de  call    ?Process@BinXmlExtractor@@QEAAXAEAVBinXmlReader@@PEAX@Z; BinXmlExtractor::Process(BinXmlReader &,void *)
0x1800018e3  mov     [rsi], r12b
0x1800018e6  mov     dil, r12b
0x1800018e9  cmp     [rsp+1B0h+var_134], 1
0x1800018ee  jz      short loc_180001938
0x1800018f0  cmp     [rbp+0B0h+var_B4], 1
0x1800018f4  jz      loc_180001CA2
0x1800018fa  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x180001901  mov     [rsp+1B0h+var_168], rax
0x180001906  cmp     [rsp+1B0h+var_150], r12b
0x18000190b  jz      short loc_180001917
0x18000190d  mov     rcx, [rsp+1B0h+var_160]; void *
0x180001912  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001917  mov     al, dil
0x18000191a  mov     rcx, [rbp+0B0h+var_40]
0x18000191e  xor     rcx, rsp; StackCookie
0x180001921  call    __security_check_cookie
0x180001926  add     rsp, 180h
0x18000192d  pop     r15
0x18000192f  pop     r14
0x180001931  pop     r12
0x180001933  pop     rdi
0x180001934  pop     rsi
0x180001935  pop     rbx
0x180001936  pop     rbp
0x180001937  retn
0x180001938  cmp     [rsp+1B0h+var_140], r12
0x18000193d  jz      short loc_1800018FA
0x18000193f  mov     r9d, 32h ; '2'; cchData
0x180001945  lea     r8, [rbp+0B0h+LCData]; lpLCData
0x180001949  lea     edx, [r9+2Ah]; LCType
0x18000194d  mov     ecx, r15d; Locale
0x180001950  call    cs:__imp_GetLocaleInfoW
0x180001956  cmp     [rsp+1B0h+var_138], 32h ; '2'
0x18000195b  jnb     short loc_180001993
0x18000195d  mov     r8d, [rsp+1B0h+var_138]
0x180001962  mov     rdx, [rsp+1B0h+var_140]
0x180001967  lea     rcx, [rbp+0B0h+LCData]
0x18000196b  call    cs:__imp__o__wcsnicmp
0x180001971  test    eax, eax
0x180001973  jz      short loc_180001990
0x180001975  mov     r8d, [rsp+1B0h+var_138]
0x18000197a  mov     rdx, [rsp+1B0h+var_140]
0x18000197f  lea     rcx, aZxx; "zxx"
0x180001986  call    cs:__imp__o__wcsnicmp
0x18000198c  test    eax, eax
0x18000198e  jnz     short loc_180001993
0x180001990  mov     byte ptr [rsi], 1
0x180001993  lea     eax, [r14-1]
0x180001997  mov     ecx, 4
0x18000199c  cmp     eax, ecx
0x18000199e  ja      loc_1800018FA
0x1800019a4  mov     eax, r14d
0x1800019a7  sub     eax, 1
0x1800019aa  jz      short loc_1800019FE
0x1800019ac  sub     eax, 1
0x1800019af  jz      short loc_1800019F7
0x1800019b1  sub     eax, 1
0x1800019b4  jz      short loc_1800019F0
0x1800019b6  sub     eax, 1
0x1800019b9  jz      short loc_180001A03
0x1800019bb  sub     eax, 1
0x1800019be  jz      short loc_1800019E9
0x1800019c0  sub     eax, 1
0x1800019c3  jz      short loc_1800019E2
0x1800019c5  cmp     eax, 1
0x1800019c8  jz      short loc_1800019DB
0x1800019ca  lea     rcx, [rsp+1B0h+var_168]; this
0x1800019cf  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800019d4  xor     al, al
0x1800019d6  jmp     loc_18000191A
0x1800019db  mov     ecx, 6
0x1800019e0  jmp     short loc_180001A03
0x1800019e2  mov     ecx, 5
0x1800019e7  jmp     short loc_180001A03
0x1800019e9  mov     ecx, 7
0x1800019ee  jmp     short loc_180001A03
0x1800019f0  mov     ecx, 3
0x1800019f5  jmp     short loc_180001A03
0x1800019f7  mov     ecx, 2
0x1800019fc  jmp     short loc_180001A03
0x1800019fe  mov     ecx, 1
0x180001a03  mov     eax, ecx
0x180001a05  add     rax, rax
0x180001a08  mov     edx, [rsp+rax*8+1B0h+var_134]
0x180001a0c  test    edx, edx
0x180001a0e  jz      loc_1800018FA
0x180001a14  cmp     ecx, 7
0x180001a17  jnb     loc_180001B5D
0x180001a1d  cmp     edx, 1
0x180001a20  jnz     loc_1800018FA
0x180001a26  mov     rdx, [rsp+rax*8+1B0h+var_140]
0x180001a2b  test    rdx, rdx
0x180001a2e  jz      loc_1800018FA
0x180001a34  mov     r8d, [rsp+rax*8+1B0h+var_138]
0x180001a39  mov     rcx, rbx
0x180001a3c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180001a41  test    al, al
0x180001a43  jz      loc_180001AEC
0x180001a49  xor     edx, edx
0x180001a4b  mov     rcx, rbx
0x180001a4e  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180001a53  test    al, al
0x180001a55  jz      loc_180001AEC
0x180001a5b  cmp     r14d, 1
0x180001a5f  jnz     short loc_180001A69
0x180001a61  mov     rcx, rbx
0x180001a64  call    FromEscapedChars
0x180001a69  xor     edx, edx
0x180001a6b  mov     rcx, rbx
0x180001a6e  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180001a73  test    al, al
0x180001a75  jnz     loc_180001C29
0x180001a7b  lea     rax, WPP_GLOBAL_Control
0x180001a82  mov     ebx, 0Eh
0x180001a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a8e  cmp     rcx, rax
0x180001a91  jz      short loc_180001AB8
0x180001a93  test    dword ptr [rcx+1Ch], 40000h
0x180001a9a  jz      short loc_180001AB8
0x180001a9c  cmp     byte ptr [rcx+19h], 2
0x180001aa0  jb      short loc_180001AB8
0x180001aa2  lea     edx, [rbx+2]
0x180001aa5  mov     r9d, ebx
0x180001aa8  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x180001aaf  mov     rcx, [rcx+10h]
0x180001ab3  call    WPP_SF_D
0x180001ab8  xorps   xmm0, xmm0
0x180001abb  movdqu  [rsp+1B0h+pExceptionObject], xmm0
0x180001ac1  mov     [rsp+1B0h+var_180], r12
0x180001ac6  mov     [rsp+1B0h+var_178], ebx
0x180001aca  mov     [rsp+1B0h+var_174], 0FFFFFFFFh
0x180001ad2  mov     [rsp+1B0h+var_170], 1B2h
0x180001ada  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180001ae1  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180001ae6  call    _CxxThrowException_0
0x180001aec  lea     rax, WPP_GLOBAL_Control
0x180001af3  mov     ebx, 0Eh
0x180001af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180001aff  cmp     rcx, rax
0x180001b02  jz      short loc_180001B29
0x180001b04  test    dword ptr [rcx+1Ch], 40000h
0x180001b0b  jz      short loc_180001B29
0x180001b0d  cmp     byte ptr [rcx+19h], 2
0x180001b11  jb      short loc_180001B29
0x180001b13  lea     edx, [rbx+1]
0x180001b16  mov     r9d, ebx
0x180001b19  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x180001b20  mov     rcx, [rcx+10h]
0x180001b24  call    WPP_SF_D
0x180001b29  xorps   xmm0, xmm0
0x180001b2c  movdqu  [rsp+1B0h+pExceptionObject], xmm0
0x180001b32  mov     [rsp+1B0h+var_180], r12
0x180001b37  mov     [rsp+1B0h+var_178], ebx
0x180001b3b  mov     [rsp+1B0h+var_174], 0FFFFFFFFh
0x180001b43  mov     [rsp+1B0h+var_170], 1A8h
0x180001b4b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180001b52  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180001b57  call    _CxxThrowException_0
0x180001b5d  jnz     loc_1800018FA
0x180001b63  cmp     edx, 1
0x180001b66  jnz     loc_1800018FA
0x180001b6c  mov     rdx, [rsp+rax*8+1B0h+var_140]
0x180001b71  test    rdx, rdx
0x180001b74  jz      loc_1800018FA
0x180001b7a  mov     r8d, [rsp+rax*8+1B0h+var_138]
0x180001b7f  mov     rcx, rbx
0x180001b82  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180001b87  test    al, al
0x180001b89  jz      loc_180001C31
0x180001b8f  xor     edx, edx
0x180001b91  mov     rcx, rbx
0x180001b94  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180001b99  test    al, al
0x180001b9b  jz      loc_180001C31
0x180001ba1  mov     rax, [rbx+8]
0x180001ba5  cmp     rax, [rbx]
0x180001ba8  jz      short loc_180001C29
0x180001baa  xor     edx, edx
0x180001bac  mov     rcx, rbx
0x180001baf  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180001bb4  test    al, al
0x180001bb6  jnz     short loc_180001C29
0x180001bb8  lea     rax, WPP_GLOBAL_Control
0x180001bbf  mov     ebx, 0Eh
0x180001bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bcb  cmp     rcx, rax
0x180001bce  jz      short loc_180001BF5
0x180001bd0  test    dword ptr [rcx+1Ch], 40000h
0x180001bd7  jz      short loc_180001BF5
0x180001bd9  cmp     byte ptr [rcx+19h], 2
0x180001bdd  jb      short loc_180001BF5
0x180001bdf  lea     edx, [rbx+5]
0x180001be2  mov     r9d, ebx
0x180001be5  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x180001bec  mov     rcx, [rcx+10h]
0x180001bf0  call    WPP_SF_D
0x180001bf5  xorps   xmm0, xmm0
0x180001bf8  movdqu  [rsp+1B0h+pExceptionObject], xmm0
0x180001bfe  mov     [rsp+1B0h+var_180], r12
0x180001c03  mov     [rsp+1B0h+var_178], ebx
0x180001c07  mov     [rsp+1B0h+var_174], 0FFFFFFFFh
0x180001c0f  mov     [rsp+1B0h+var_170], 1D8h
0x180001c17  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180001c1e  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180001c23  call    _CxxThrowException_0
0x180001c29  mov     dil, 1
0x180001c2c  jmp     loc_1800018FA
0x180001c31  lea     rax, WPP_GLOBAL_Control
0x180001c38  mov     ebx, 0Eh
0x180001c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c44  cmp     rcx, rax
0x180001c47  jz      short loc_180001C6E
0x180001c49  test    dword ptr [rcx+1Ch], 40000h
0x180001c50  jz      short loc_180001C6E
0x180001c52  cmp     byte ptr [rcx+19h], 2
0x180001c56  jb      short loc_180001C6E
0x180001c58  lea     edx, [rbx+4]
0x180001c5b  mov     r9d, ebx
0x180001c5e  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x180001c65  mov     rcx, [rcx+10h]
0x180001c69  call    WPP_SF_D
0x180001c6e  xorps   xmm0, xmm0
0x180001c71  movdqu  [rsp+1B0h+pExceptionObject], xmm0
0x180001c77  mov     [rsp+1B0h+var_180], r12
0x180001c7c  mov     [rsp+1B0h+var_178], ebx
0x180001c80  mov     [rsp+1B0h+var_174], 0FFFFFFFFh
0x180001c88  mov     [rsp+1B0h+var_170], 1D0h
0x180001c90  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180001c97  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180001c9c  call    _CxxThrowException_0
0x180001ca2  cmp     r14d, 1
0x180001ca6  jnz     loc_1800018FA
0x180001cac  mov     rdx, [rbp+0B0h+var_C0]
0x180001cb0  test    rdx, rdx
0x180001cb3  jz      loc_1800018FA
0x180001cb9  mov     rcx, rbx
0x180001cbc  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180001cc1  test    al, al
0x180001cc3  jz      short loc_180001CDE
0x180001cc5  xor     edx, edx
0x180001cc7  mov     rcx, rbx
0x180001cca  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180001ccf  test    al, al
0x180001cd1  jz      short loc_180001CDE
0x180001cd3  mov     dil, r14b
0x180001cd6  mov     [rsi], r14b
0x180001cd9  jmp     loc_1800018FA
0x180001cde  lea     rax, WPP_GLOBAL_Control
0x180001ce5  mov     ebx, 0Eh
0x180001cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cf1  cmp     rcx, rax
0x180001cf4  jz      short loc_180001D1B
0x180001cf6  test    dword ptr [rcx+1Ch], 40000h
0x180001cfd  jz      short loc_180001D1B
0x180001cff  cmp     byte ptr [rcx+19h], 2
0x180001d03  jb      short loc_180001D1B
0x180001d05  lea     edx, [rbx+6]
0x180001d08  mov     r9d, ebx
0x180001d0b  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x180001d12  mov     rcx, [rcx+10h]
  ... truncated ...
```
