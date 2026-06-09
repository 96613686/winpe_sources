# CTSCryptUtils::UrlEncodedStringToBinaryW(ushort const *,uchar * *,ulong *)

- ea: `0x180015050`
- end: `0x18001547f`
- name: `?UrlEncodedStringToBinaryW@CTSCryptUtils@@SAJPEBGPEAPEAEPEAK@Z`
- size: `1071`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011310`

## callees

- `0x1800011c8`
- `0x180006734`
- `0x180007a64`
- `0x18000e2e8`
- `0x180014ae8`
- `0x180014b34`
- `0x180014fec`
- `0x180015050`
- `0x180015488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153b2`
- `CRYPT32!CryptStringToBinaryW` at `0x1800152b8`
- `CRYPT32!CryptStringToBinaryW` at `0x1800153a4`
- `CRYPT32!CryptStringToBinaryW` at `0x1800152b8`
- `CRYPT32!CryptStringToBinaryW` at `0x1800153a4`

## string_xrefs

- `0x1800152ff`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1800153e7`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`

## pseudocode

```c
__int64 __fastcall CTSCryptUtils::UrlEncodedStringToBinaryW(
        const unsigned __int16 *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  int ActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  signed int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned __int64 v12; // r14
  unsigned __int16 *v13; // rax
  WCHAR *v14; // rsi
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned __int64 i; // rax
  signed int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  unsigned __int8 *v22; // rdi
  signed int LastError; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  DWORD v27; // eax
  int v29; // [rsp+50h] [rbp-20h] BYREF
  int v30; // [rsp+54h] [rbp-1Ch] BYREF
  const char *v31; // [rsp+58h] [rbp-18h] BYREF
  const char *v32; // [rsp+60h] [rbp-10h] BYREF
  const char *v33; // [rsp+68h] [rbp-8h] BYREF
  DWORD pcbBinary; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int64 v35; // [rsp+B8h] [rbp+48h] BYREF

  pcbBinary = 0;
  v35 = 0;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2);
    v7 = 151;
    v8 = "pszIn";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_7bbe3e938a5e3b4d176d7f01d750665e_Traceguids,
      ActivityIdPrefix,
      (__int64)v8);
    return (unsigned int)-2147024809;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 0);
    v7 = 152;
    v8 = "ppOut";
    goto LABEL_6;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2);
    v7 = 153;
    v8 = "pcbOut";
    goto LABEL_6;
  }
  *a2 = 0;
  *a3 = 0;
  v9 = StringCchLengthW(a1, (unsigned __int64)a2, &v35);
  if ( v9 >= 0 )
  {
    v12 = v35 + 2;
    v13 = (unsigned __int16 *)operator new(saturated_mul(v35 + 2, 2u));
    v14 = v13;
    if ( v13 )
    {
      v9 = StringCchCopyW(v13, v12, a1);
      if ( v9 >= 0 )
      {
        for ( i = 0; i < v12; ++i )
        {
          if ( v14[i] == 45 )
          {
            v14[i] = 43;
          }
          else if ( v14[i] == 95 )
          {
            v14[i] = 47;
          }
        }
        if ( CryptStringToBinaryW(v14, 0, 1u, 0, &pcbBinary, 0, 0) )
        {
          v22 = (unsigned __int8 *)operator new(pcbBinary);
          if ( v22 )
          {
            if ( CryptStringToBinaryW(v14, 0, 1u, v22, &pcbBinary, 0, 0) )
            {
              v27 = pcbBinary;
              v9 = 0;
              *a2 = v22;
              *a3 = v27;
            }
            else
            {
              LastError = GetLastError();
              v9 = LastError;
              if ( LastError > 0 )
                v9 = (unsigned __int16)LastError | 0x80070000;
              if ( (unsigned int)dword_18001F000 > 2 )
              {
                LODWORD(v35) = v9;
                v33 = "UrlEncodedStringToBinaryW";
                v30 = 2407;
                v32 = "onecore\\termsrv\\rdpplatform\\common\\cryptutil\\base\\tscryptutils.cpp";
                v31 = "CryptStringToBinary failed: 0x%X";
                v29 = -2147467259;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v24,
                  (unsigned int)word_18001AD22,
                  v25,
                  v26,
                  (__int64)&v31,
                  (__int64)&v29,
                  (__int64)&v32,
                  (__int64)&v30,
                  (__int64)&v33,
                  (__int64)&v35);
              }
              operator delete(v22);
            }
          }
          else
          {
            v9 = -2147024882;
          }
        }
        else
        {
          v18 = GetLastError();
          v9 = v18;
          if ( v18 > 0 )
            v9 = (unsigned __int16)v18 | 0x80070000;
          if ( (unsigned int)dword_18001F000 > 2 )
          {
            LODWORD(v35) = v9;
            v31 = "UrlEncodedStringToBinaryW";
            v29 = 2380;
            v32 = "onecore\\termsrv\\rdpplatform\\common\\cryptutil\\base\\tscryptutils.cpp";
            v33 = "CryptStringToBinary failed: 0x%X";
            v30 = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v19,
              (unsigned int)byte_18001ACD9,
              v20,
              v21,
              (__int64)&v33,
              (__int64)&v30,
              (__int64)&v32,
              (__int64)&v29,
              (__int64)&v31,
              (__int64)&v35);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v15);
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, WPP_7bbe3e938a5e3b4d176d7f01d750665e_Traceguids, v16, v9);
      }
      operator delete(v14);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v10);
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, WPP_7bbe3e938a5e3b4d176d7f01d750665e_Traceguids, v11, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015050  mov     [rsp-28h+arg_8], rbx
0x180015055  mov     [rsp-28h+arg_10], rsi
0x18001505a  push    rbp
0x18001505b  push    rdi
0x18001505c  push    r12
0x18001505e  push    r14
0x180015060  push    r15
0x180015062  mov     rbp, rsp
0x180015065  sub     rsp, 70h
0x180015069  mov     r15, r8
0x18001506c  mov     [rbp+arg_0], 0
0x180015073  mov     r12, rdx
0x180015076  mov     [rbp+arg_18], 0
0x18001507e  mov     rdi, rcx
0x180015081  test    rcx, rcx
0x180015084  jnz     short loc_1800150DF
0x180015086  mov     rcx, cs:WPP_GLOBAL_Control
0x18001508d  lea     rax, WPP_GLOBAL_Control
0x180015094  cmp     rcx, rax
0x180015097  jz      short loc_1800150D5
0x180015099  test    byte ptr [rcx+1Ch], 8
0x18001509d  jz      short loc_1800150D5
0x18001509f  cmp     byte ptr [rcx+19h], 2
0x1800150a3  jb      short loc_1800150D5
0x1800150a5  call    RdpX_GetActivityIdPrefix
0x1800150aa  mov     edx, 97h
0x1800150af  lea     rcx, aPszin; "pszIn"
0x1800150b6  mov     [rsp+70h+pcbBinary], rcx
0x1800150bb  lea     r8, WPP_7bbe3e938a5e3b4d176d7f01d750665e_Traceguids
0x1800150c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150c9  mov     r9d, eax
0x1800150cc  mov     rcx, [rcx+10h]
0x1800150d0  call    WPP_SF_Ds
0x1800150d5  mov     ebx, 80070057h
0x1800150da  jmp     loc_180015464
0x1800150df  test    r12, r12
0x1800150e2  jnz     short loc_180015116
0x1800150e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150eb  lea     rax, WPP_GLOBAL_Control
0x1800150f2  cmp     rcx, rax
0x1800150f5  jz      short loc_1800150D5
0x1800150f7  test    byte ptr [rcx+1Ch], 8
0x1800150fb  jz      short loc_1800150D5
0x1800150fd  cmp     byte ptr [rcx+19h], 2
0x180015101  jb      short loc_1800150D5
0x180015103  call    RdpX_GetActivityIdPrefix
0x180015108  mov     edx, 98h
0x18001510d  lea     rcx, aPpout; "ppOut"
0x180015114  jmp     short loc_1800150B6
0x180015116  test    r15, r15
0x180015119  jnz     short loc_180015150
0x18001511b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015122  lea     rax, WPP_GLOBAL_Control
0x180015129  cmp     rcx, rax
0x18001512c  jz      short loc_1800150D5
0x18001512e  test    byte ptr [rcx+1Ch], 8
0x180015132  jz      short loc_1800150D5
0x180015134  cmp     byte ptr [rcx+19h], 2
0x180015138  jb      short loc_1800150D5
0x18001513a  call    RdpX_GetActivityIdPrefix
0x18001513f  mov     edx, 99h; unsigned __int64
0x180015144  lea     rcx, aPcbout; "pcbOut"
0x18001514b  jmp     loc_1800150B6
0x180015150  mov     qword ptr [rdx], 0
0x180015157  mov     dword ptr [r8], 0
0x18001515e  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x180015162  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180015167  mov     ebx, eax
0x180015169  test    eax, eax
0x18001516b  jns     short loc_1800151C5
0x18001516d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015174  lea     rax, WPP_GLOBAL_Control
0x18001517b  cmp     rcx, rax
0x18001517e  jz      loc_180015464
0x180015184  test    byte ptr [rcx+1Ch], 8
0x180015188  jz      loc_180015464
0x18001518e  cmp     byte ptr [rcx+19h], 2
0x180015192  jb      loc_180015464
0x180015198  call    RdpX_GetActivityIdPrefix
0x18001519d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151a4  lea     r8, WPP_7bbe3e938a5e3b4d176d7f01d750665e_Traceguids
0x1800151ab  mov     edx, 9Ah
0x1800151b0  mov     dword ptr [rsp+70h+pcbBinary], ebx
0x1800151b4  mov     r9d, eax
0x1800151b7  mov     rcx, [rcx+10h]
0x1800151bb  call    WPP_SF_DD
0x1800151c0  jmp     loc_180015464
0x1800151c5  mov     r14, [rbp+arg_18]
0x1800151c9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800151d0  add     r14, 2
0x1800151d4  mov     eax, 2
0x1800151d9  mul     r14
0x1800151dc  cmovb   rax, rcx
0x1800151e0  mov     rcx, rax; Size
0x1800151e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800151e8  mov     rsi, rax
0x1800151eb  test    rax, rax
0x1800151ee  jnz     short loc_1800151FA
0x1800151f0  mov     ebx, 8007000Eh
0x1800151f5  jmp     loc_180015464
0x1800151fa  mov     r8, rdi; unsigned __int16 *
0x1800151fd  mov     rdx, r14; unsigned __int64
0x180015200  mov     rcx, rsi; unsigned __int16 *
0x180015203  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015208  mov     ebx, eax
0x18001520a  test    eax, eax
0x18001520c  jns     short loc_180015266
0x18001520e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015215  lea     rax, WPP_GLOBAL_Control
0x18001521c  cmp     rcx, rax
0x18001521f  jz      loc_18001545C
0x180015225  test    byte ptr [rcx+1Ch], 8
0x180015229  jz      loc_18001545C
0x18001522f  cmp     byte ptr [rcx+19h], 2
0x180015233  jb      loc_18001545C
0x180015239  call    RdpX_GetActivityIdPrefix
0x18001523e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015245  lea     r8, WPP_7bbe3e938a5e3b4d176d7f01d750665e_Traceguids
0x18001524c  mov     edx, 9Bh
0x180015251  mov     dword ptr [rsp+70h+pcbBinary], ebx
0x180015255  mov     r9d, eax
0x180015258  mov     rcx, [rcx+10h]
0x18001525c  call    WPP_SF_DD
0x180015261  jmp     loc_18001545C
0x180015266  xor     eax, eax
0x180015268  test    r14, r14
0x18001526b  jz      short loc_180015291
0x18001526d  cmp     word ptr [rsi+rax*2], 2Dh ; '-'
0x180015272  jnz     short loc_18001527C
0x180015274  mov     word ptr [rsi+rax*2], 2Bh ; '+'
0x18001527a  jmp     short loc_180015289
0x18001527c  cmp     word ptr [rsi+rax*2], 5Fh ; '_'
0x180015281  jnz     short loc_180015289
0x180015283  mov     word ptr [rsi+rax*2], 2Fh ; '/'
0x180015289  inc     rax
0x18001528c  cmp     rax, r14
0x18001528f  jb      short loc_18001526D
0x180015291  xor     r9d, r9d; pbBinary
0x180015294  mov     [rsp+70h+pdwFlags], 0; pdwFlags
0x18001529d  lea     rax, [rbp+arg_0]
0x1800152a1  mov     [rsp+70h+pdwSkip], 0; pdwSkip
0x1800152aa  xor     edx, edx; cchString
0x1800152ac  mov     [rsp+70h+pcbBinary], rax; pcbBinary
0x1800152b1  mov     rcx, rsi; pszString
0x1800152b4  lea     r8d, [r9+1]; dwFlags
0x1800152b8  call    cs:__imp_CryptStringToBinaryW
0x1800152be  test    eax, eax
0x1800152c0  jnz     loc_180015363
0x1800152c6  call    cs:__imp_GetLastError
0x1800152cc  mov     ebx, eax
0x1800152ce  test    eax, eax
0x1800152d0  jle     short loc_1800152DB
0x1800152d2  movzx   ebx, ax
0x1800152d5  or      ebx, 80070000h
0x1800152db  mov     eax, cs:dword_18001F000
0x1800152e1  cmp     eax, 2
0x1800152e4  jbe     loc_18001545C
0x1800152ea  lea     rax, aUrlencodedstri; "UrlEncodedStringToBinaryW"
0x1800152f1  mov     dword ptr [rbp+arg_18], ebx
0x1800152f4  mov     [rbp+var_18], rax
0x1800152f8  lea     rdx, byte_18001ACD9
0x1800152ff  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180015306  mov     [rbp+var_20], 94Ch
0x18001530d  mov     [rbp+var_10], rax
0x180015311  lea     rax, aCryptstringtob; "CryptStringToBinary failed: 0x%X"
0x180015318  mov     [rbp+var_8], rax
0x18001531c  lea     rax, [rbp+arg_18]
0x180015320  mov     [rsp+70h+var_28], rax
0x180015325  lea     rax, [rbp+var_18]
0x180015329  mov     [rsp+70h+var_30], rax
0x18001532e  lea     rax, [rbp+var_20]
0x180015332  mov     [rsp+70h+var_38], rax
0x180015337  lea     rax, [rbp+var_10]
0x18001533b  mov     [rsp+70h+pdwFlags], rax
0x180015340  lea     rax, [rbp+var_1C]
0x180015344  mov     [rsp+70h+pdwSkip], rax
0x180015349  lea     rax, [rbp+var_8]
0x18001534d  mov     [rsp+70h+pcbBinary], rax
0x180015352  mov     [rbp+var_1C], 80004005h
0x180015359  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001535e  jmp     loc_18001545C
0x180015363  mov     ecx, [rbp+arg_0]; Size
0x180015366  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001536b  mov     rdi, rax
0x18001536e  test    rax, rax
0x180015371  jnz     short loc_18001537D
0x180015373  mov     ebx, 8007000Eh
0x180015378  jmp     loc_18001545C
0x18001537d  xor     edx, edx; cchString
0x18001537f  mov     [rsp+70h+pdwFlags], 0; pdwFlags
0x180015388  lea     rax, [rbp+arg_0]
0x18001538c  mov     [rsp+70h+pdwSkip], 0; pdwSkip
0x180015395  mov     r9, rdi; pbBinary
0x180015398  mov     [rsp+70h+pcbBinary], rax; pcbBinary
0x18001539d  mov     rcx, rsi; pszString
0x1800153a0  lea     r8d, [rdx+1]; dwFlags
0x1800153a4  call    cs:__imp_CryptStringToBinaryW
0x1800153aa  test    eax, eax
0x1800153ac  jnz     loc_180015450
0x1800153b2  call    cs:__imp_GetLastError
0x1800153b8  mov     ebx, eax
0x1800153ba  test    eax, eax
0x1800153bc  jle     short loc_1800153C7
0x1800153be  movzx   ebx, ax
0x1800153c1  or      ebx, 80070000h
0x1800153c7  mov     eax, cs:dword_18001F000
0x1800153cd  cmp     eax, 2
0x1800153d0  jbe     short loc_180015446
0x1800153d2  lea     rax, aUrlencodedstri; "UrlEncodedStringToBinaryW"
0x1800153d9  mov     dword ptr [rbp+arg_18], ebx
0x1800153dc  mov     [rbp+var_8], rax
0x1800153e0  lea     rdx, word_18001AD22
0x1800153e7  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800153ee  mov     [rbp+var_1C], 967h
0x1800153f5  mov     [rbp+var_10], rax
0x1800153f9  lea     rax, aCryptstringtob; "CryptStringToBinary failed: 0x%X"
0x180015400  mov     [rbp+var_18], rax
0x180015404  lea     rax, [rbp+arg_18]
0x180015408  mov     [rsp+70h+var_28], rax
0x18001540d  lea     rax, [rbp+var_8]
0x180015411  mov     [rsp+70h+var_30], rax
0x180015416  lea     rax, [rbp+var_1C]
0x18001541a  mov     [rsp+70h+var_38], rax
0x18001541f  lea     rax, [rbp+var_10]
0x180015423  mov     [rsp+70h+pdwFlags], rax
0x180015428  lea     rax, [rbp+var_20]
0x18001542c  mov     [rsp+70h+pdwSkip], rax
0x180015431  lea     rax, [rbp+var_18]
0x180015435  mov     [rsp+70h+pcbBinary], rax
0x18001543a  mov     [rbp+var_20], 80004005h
0x180015441  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180015446  mov     rcx, rdi; Block
0x180015449  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001544e  jmp     short loc_18001545C
0x180015450  mov     eax, [rbp+arg_0]
0x180015453  xor     ebx, ebx
0x180015455  mov     [r12], rdi
0x180015459  mov     [r15], eax
0x18001545c  mov     rcx, rsi; Block
0x18001545f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015464  lea     r11, [rsp+70h+var_s0]
0x180015469  mov     eax, ebx
0x18001546b  mov     rbx, [r11+38h]
0x18001546f  mov     rsi, [r11+40h]
0x180015473  mov     rsp, r11
0x180015476  pop     r15
0x180015478  pop     r14
0x18001547a  pop     r12
0x18001547c  pop     rdi
0x18001547d  pop     rbp
0x18001547e  retn
```
