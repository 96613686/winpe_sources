# QueryLogCommand::Init(void)

- ea: `0x14001c6b0`
- end: `0x14001cfc3`
- name: `?Init@QueryLogCommand@@UEAAXXZ`
- size: `2323`
- prototype: `void __fastcall(QueryLogCommand *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x14000cabc`
- `0x14000d8c4`
- `0x14000ebbc`
- `0x14000f940`
- `0x14000fa70`
- `0x140010450`
- `0x140011a38`
- `0x140011bbc`
- `0x1400163cc`
- `0x1400165a4`
- `0x14001c6b0`
- `0x14001d38c`
- `0x140021b00`
- `0x140022cec`
- `0x14002445c`
- `0x1400247c8`
- `0x140024b00`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x14001cefa`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x14001cefa`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14001cf91`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14001cf91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001cf0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001cf0e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001cf9d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001cf9d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001c7ff`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001c7ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall QueryLogCommand::Init(CommandArguments **this)
{
  HRESULT v2; // eax
  unsigned int v3; // edi
  wchar_t **v4; // rdi
  __int64 Argument; // rax
  int OptionInteger; // eax
  _QWORD *v7; // rsi
  int v8; // eax
  __int64 v9; // r9
  __int64 v10; // r9
  __int64 v11; // r9
  int Option; // eax
  wchar_t *v13; // rcx
  __int64 OptionString; // rax
  wchar_t *p_pExceptionObject; // rcx
  const WCHAR *v16; // rax
  const wchar_t *Src; // rdi
  LCID v18; // eax
  DWORD LastError; // ebx
  char *v20; // [rsp+20h] [rbp-E0h]
  char *v21; // [rsp+20h] [rbp-E0h]
  char *v22; // [rsp+20h] [rbp-E0h]
  char *v23; // [rsp+20h] [rbp-E0h]
  char *v24; // [rsp+20h] [rbp-E0h]
  char v25[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  char v29; // [rsp+71h] [rbp-8Fh]
  __int128 pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v31; // [rsp+98h] [rbp-68h]
  _QWORD v32[22]; // [rsp+B0h] [rbp-50h] BYREF

  v32[0] = L"logfile";
  v32[1] = L"lf";
  v32[2] = L"structuredquery";
  v32[3] = L"sq";
  v32[4] = L"batchsize";
  v32[5] = L"bs";
  v32[6] = L"query";
  v32[7] = L"q";
  v32[8] = L"bookmark";
  v32[9] = L"bm";
  v32[10] = L"savebookmark";
  v32[11] = L"sbm";
  v32[12] = L"reversdirection";
  v32[13] = L"rd";
  v32[14] = L"count";
  v32[15] = L"c";
  v32[16] = L"locale";
  v32[17] = L"l";
  v32[18] = L"format";
  v32[19] = L"f";
  v32[20] = L"element";
  v32[21] = L"e";
  CommandArguments::ValidateArgumentCount(this[1], 2u);
  *(_QWORD *)&pExceptionObject = v32;
  *((_QWORD *)&pExceptionObject + 1) = 22;
  CommandArguments::ValidateOptions(this[1], &pExceptionObject);
  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids,
        (unsigned int)v2);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, v3, 0, 0, v20, 52, 3u, 0);
    throw (EvtException *)&pExceptionObject;
  }
  v29 = 1;
  v4 = (wchar_t **)(this + 5);
  Argument = CommandArguments::GetArgument(this[1], 1);
  std::wstring::operator=(this + 5, Argument);
  *(_QWORD *)&pExceptionObject = L"bs";
  *((_QWORD *)&pExceptionObject + 1) = 2;
  *(_QWORD *)&v26 = L"batchsize";
  *((_QWORD *)&v26 + 1) = 9;
  OptionInteger = CommandArguments::GetOptionInteger(
                    (unsigned int)this[1],
                    (unsigned int)&v26,
                    (unsigned int)&pExceptionObject,
                    10,
                    (__int64)v25);
  *((_DWORD *)this + 61) = OptionInteger;
  if ( OptionInteger <= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, 87);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0x57u, 0, 0, v21, 61, 0x23u, L"batchsize");
    throw (EvtException *)&pExceptionObject;
  }
  *(_QWORD *)&v26 = L"sbm";
  *((_QWORD *)&v26 + 1) = 3;
  *(_QWORD *)&pExceptionObject = L"savebookmark";
  *((_QWORD *)&pExceptionObject + 1) = 12;
  CommandArguments::GetOptionString(
    (unsigned int)this[1],
    (unsigned int)&pExceptionObject,
    (unsigned int)&v26,
    (unsigned int)&ValueName,
    (__int64)v25);
  std::wstring::assign(this + 17);
  *(_QWORD *)&v26 = L"e";
  *((_QWORD *)&v26 + 1) = 1;
  *(_QWORD *)&pExceptionObject = L"element";
  *((_QWORD *)&pExceptionObject + 1) = 7;
  CommandArguments::GetOptionString(
    (unsigned int)this[1],
    (unsigned int)&pExceptionObject,
    (unsigned int)&v26,
    (unsigned int)&ValueName,
    (__int64)v25);
  v7 = this + 21;
  std::wstring::assign(this + 21);
  *(_QWORD *)&v26 = L"c";
  *((_QWORD *)&v26 + 1) = 1;
  *(_QWORD *)&pExceptionObject = L"count";
  *((_QWORD *)&pExceptionObject + 1) = 5;
  v8 = CommandArguments::GetOptionInteger(
         (unsigned int)this[1],
         (unsigned int)&pExceptionObject,
         (unsigned int)&v26,
         0,
         (__int64)v25);
  *((_DWORD *)this + 60) = v8;
  if ( v8 <= 0 )
  {
    *(_QWORD *)&v26 = L"c";
    *((_QWORD *)&v26 + 1) = 1;
    *(_QWORD *)&pExceptionObject = L"count";
    *((_QWORD *)&pExceptionObject + 1) = 5;
    if ( (unsigned __int8)CommandArguments::HasOption(this[1], &pExceptionObject, &v26) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, 87);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0x57u, 0, 0, v22, 69, 0x23u, L"count");
      throw (EvtException *)&pExceptionObject;
    }
  }
  *(_QWORD *)&v26 = L"rd";
  *((_QWORD *)&v26 + 1) = 2;
  *(_QWORD *)&pExceptionObject = L"reversedirection";
  *((_QWORD *)&pExceptionObject + 1) = 16;
  *((_BYTE *)this + 258) = CommandArguments::GetOptionBool(this[1], &pExceptionObject, &v26, v9, v25);
  *(_QWORD *)&v26 = L"q";
  *((_QWORD *)&v26 + 1) = 1;
  *(_QWORD *)&pExceptionObject = L"query";
  *((_QWORD *)&pExceptionObject + 1) = 5;
  CommandArguments::GetOptionString(
    (unsigned int)this[1],
    (unsigned int)&pExceptionObject,
    (unsigned int)&v26,
    (unsigned int)L"*",
    (__int64)v25);
  std::wstring::assign(this + 9);
  *(_QWORD *)&v26 = L"lf";
  *((_QWORD *)&v26 + 1) = 2;
  *(_QWORD *)&pExceptionObject = L"logfile";
  *((_QWORD *)&pExceptionObject + 1) = 7;
  *((_BYTE *)this + 256) = CommandArguments::GetOptionBool(this[1], &pExceptionObject, &v26, v10, v25);
  *(_QWORD *)&v26 = L"sq";
  *((_QWORD *)&v26 + 1) = 2;
  *(_QWORD *)&pExceptionObject = L"structuredquery";
  *((_QWORD *)&pExceptionObject + 1) = 15;
  *((_BYTE *)this + 257) = CommandArguments::GetOptionBool(this[1], &pExceptionObject, &v26, v11, v25);
  *(_QWORD *)&v26 = &EnumNameValueEventFormat;
  *((_QWORD *)&v26 + 1) = 3;
  *(_QWORD *)&pExceptionObject = L"f";
  *((_QWORD *)&pExceptionObject + 1) = 1;
  v27 = L"format";
  v28 = 6;
  Option = CommandArguments::GetOptionEnum<enum WevtUtilOutputFormat>(this[1], &v27, &pExceptionObject, &v26);
  *((_DWORD *)this + 63) = Option;
  if ( Option == 1 )
  {
    this[23] = 0;
    if ( (unsigned __int64)this[24] > 7 )
      v7 = (_QWORD *)*v7;
    *(_WORD *)v7 = 0;
  }
  if ( *((_BYTE *)this + 257) )
  {
    v27 = L"q";
    v28 = 1;
    *(_QWORD *)&v26 = L"query";
    *((_QWORD *)&v26 + 1) = 5;
    if ( (unsigned __int8)CommandArguments::HasOption(this[1], &v26, &v27) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, 87);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0x57u, 0, 0, v23, 87, 0x30u, 0);
      throw (EvtException *)&pExceptionObject;
    }
    if ( *((_BYTE *)this + 256) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, 87);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0x57u, 0, 0, v23, 92, 0xEu, 0);
      throw (EvtException *)&pExceptionObject;
    }
    if ( (unsigned __int64)this[8] <= 7 )
      v13 = (wchar_t *)(this + 5);
    else
      v13 = *v4;
    ReadTextFile(v13, (__int64)(this + 9));
    this[7] = 0;
    if ( (unsigned __int64)this[8] > 7 )
      v4 = (wchar_t **)*v4;
    *(_WORD *)v4 = 0;
  }
  v27 = L"bm";
  v28 = 2;
  *(_QWORD *)&v26 = L"bookmark";
  *((_QWORD *)&v26 + 1) = 8;
  if ( (unsigned __int8)CommandArguments::HasOption(this[1], &v26, &v27) )
  {
    v27 = L"bm";
    v28 = 2;
    *(_QWORD *)&v26 = L"bookmark";
    *((_QWORD *)&v26 + 1) = 8;
    OptionString = CommandArguments::GetOptionString(
                     (unsigned int)this[1],
                     (unsigned int)&v26,
                     (unsigned int)&v27,
                     (unsigned int)&ValueName,
                     (__int64)v25);
    std::wstring::wstring(&pExceptionObject, OptionString);
    p_pExceptionObject = (wchar_t *)&pExceptionObject;
    if ( v31 > 7 )
      p_pExceptionObject = (wchar_t *)pExceptionObject;
    ReadTextFile(p_pExceptionObject, (__int64)(this + 13));
    std::wstring::_Tidy_deallocate(&pExceptionObject);
  }
  v27 = L"l";
  v28 = 1;
  *(_QWORD *)&v26 = L"locale";
  *((_QWORD *)&v26 + 1) = 6;
  v16 = (const WCHAR *)CommandArguments::GetOptionString(
                         (unsigned int)this[1],
                         (unsigned int)&v26,
                         (unsigned int)&v27,
                         0,
                         (__int64)v25);
  Src = v16;
  if ( v16 && *v16 )
  {
    v18 = LocaleNameToLCID(v16, 0);
    *((_DWORD *)this + 62) = v18;
    if ( !v18 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids, LastError);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, LastError, 0, 0, v24, 116, 0x24u, Src);
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    *((_DWORD *)this + 62) = GetThreadLocale();
  }
  CoUninitialize();
}

```

## disassembly

```asm
0x14001c6b0  push    rbp
0x14001c6b2  push    rbx
0x14001c6b3  push    rsi
0x14001c6b4  push    rdi
0x14001c6b5  push    r12
0x14001c6b7  push    r13
0x14001c6b9  push    r14
0x14001c6bb  push    r15
0x14001c6bd  lea     rbp, [rsp-78h]
0x14001c6c2  sub     rsp, 178h
0x14001c6c9  mov     rax, cs:__security_cookie
0x14001c6d0  xor     rax, rsp
0x14001c6d3  mov     [rbp+0B0h+var_50], rax
0x14001c6d7  mov     rbx, rcx
0x14001c6da  lea     rax, aLogfile; "logfile"
0x14001c6e1  mov     [rbp+0B0h+var_100], rax
0x14001c6e5  lea     rax, aLf; "lf"
0x14001c6ec  mov     [rbp+0B0h+var_F8], rax
0x14001c6f0  lea     rax, aStructuredquer; "structuredquery"
0x14001c6f7  mov     [rbp+0B0h+var_F0], rax
0x14001c6fb  lea     rax, aSq; "sq"
0x14001c702  mov     [rbp+0B0h+var_E8], rax
0x14001c706  lea     rsi, aBatchsize; "batchsize"
0x14001c70d  mov     [rbp+0B0h+var_E0], rsi
0x14001c711  lea     rax, aBs; "bs"
0x14001c718  mov     [rbp+0B0h+var_D8], rax
0x14001c71c  lea     rax, aQuery; "query"
0x14001c723  mov     [rbp+0B0h+var_D0], rax
0x14001c727  lea     rax, aQ; "q"
0x14001c72e  mov     [rbp+0B0h+var_C8], rax
0x14001c732  lea     rax, aBookmark; "bookmark"
0x14001c739  mov     [rbp+0B0h+var_C0], rax
0x14001c73d  lea     rax, aBm; "bm"
0x14001c744  mov     [rbp+0B0h+var_B8], rax
0x14001c748  lea     rax, aSavebookmark; "savebookmark"
0x14001c74f  mov     [rbp+0B0h+var_B0], rax
0x14001c753  lea     rax, aSbm; "sbm"
0x14001c75a  mov     [rbp+0B0h+var_A8], rax
0x14001c75e  lea     rax, aReversdirectio; "reversdirection"
0x14001c765  mov     [rbp+0B0h+var_A0], rax
0x14001c769  lea     rax, aRd; "rd"
0x14001c770  mov     [rbp+0B0h+var_98], rax
0x14001c774  lea     r14, aCount; "count"
0x14001c77b  mov     [rbp+0B0h+var_90], r14
0x14001c77f  lea     rax, aC; "c"
0x14001c786  mov     [rbp+0B0h+var_88], rax
0x14001c78a  lea     rax, aLocale; "locale"
0x14001c791  mov     [rbp+0B0h+var_80], rax
0x14001c795  lea     rax, asc_1400387C0; "l"
0x14001c79c  mov     [rbp+0B0h+var_78], rax
0x14001c7a0  lea     rax, aFormat; "format"
0x14001c7a7  mov     [rbp+0B0h+var_70], rax
0x14001c7ab  lea     rax, asc_1400388B0; "f"
0x14001c7b2  mov     [rbp+0B0h+var_68], rax
0x14001c7b6  lea     rax, aElement; "element"
0x14001c7bd  mov     [rbp+0B0h+var_60], rax
0x14001c7c1  lea     rax, aE_0; "e"
0x14001c7c8  mov     [rbp+0B0h+var_58], rax
0x14001c7cc  mov     r12d, 2
0x14001c7d2  mov     edx, r12d; unsigned __int64
0x14001c7d5  mov     rcx, [rcx+8]; this
0x14001c7d9  call    ?ValidateArgumentCount@CommandArguments@@QEBAX_K@Z; CommandArguments::ValidateArgumentCount(unsigned __int64)
0x14001c7de  lea     rax, [rbp+0B0h+var_100]
0x14001c7e2  mov     [rbp+0B0h+pExceptionObject], rax
0x14001c7e6  mov     [rbp+0B0h+var_128], 16h
0x14001c7ee  lea     rdx, [rbp+0B0h+pExceptionObject]
0x14001c7f2  mov     rcx, [rbx+8]
0x14001c7f6  call    ?ValidateOptions@CommandArguments@@QEBAXV?$span@PEB_W$0?0@utl@@@Z; CommandArguments::ValidateOptions(utl::span<wchar_t const *,-1>)
0x14001c7fb  xor     edx, edx; dwCoInit
0x14001c7fd  xor     ecx, ecx; pvReserved
0x14001c7ff  call    cs:__imp_CoInitializeEx
0x14001c805  mov     edi, eax
0x14001c807  xor     r15d, r15d
0x14001c80a  test    eax, eax
0x14001c80c  jns     short loc_14001C880
0x14001c80e  lea     rcx, WPP_GLOBAL_Control
0x14001c815  mov     r10, cs:WPP_GLOBAL_Control
0x14001c81c  cmp     r10, rcx
0x14001c81f  jz      short loc_14001C849
0x14001c821  test    dword ptr [r10+1Ch], 400000h
0x14001c829  jz      short loc_14001C849
0x14001c82b  cmp     [r10+19h], r12b
0x14001c82f  jb      short loc_14001C849
0x14001c831  lea     edx, [r12+8]
0x14001c836  mov     r9d, eax
0x14001c839  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14001c840  mov     rcx, [r10+10h]
0x14001c844  call    WPP_SF_d
0x14001c849  mov     [rsp+1B0h+Src], r15; Src
0x14001c84e  mov     [rsp+1B0h+var_180], 3; unsigned int
0x14001c856  mov     [rsp+1B0h+var_188], 34h ; '4'; int
0x14001c85e  xor     r9d, r9d; unsigned int
0x14001c861  xor     r8d, r8d; unsigned int
0x14001c864  mov     edx, edi; unsigned int
0x14001c866  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x14001c86a  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001c86f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001c876  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x14001c87a  call    _CxxThrowException_0
0x14001c880  mov     r13d, 1
0x14001c886  mov     [rsp+1B0h+var_13F], r13b
0x14001c88b  lea     rdi, [rbx+28h]
0x14001c88f  mov     edx, r13d
0x14001c892  mov     rcx, [rbx+8]
0x14001c896  call    ?GetArgument@CommandArguments@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; CommandArguments::GetArgument(unsigned __int64)
0x14001c89b  mov     rdx, rax
0x14001c89e  mov     rcx, rdi
0x14001c8a1  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14001c8a6  lea     rax, aBs; "bs"
0x14001c8ad  mov     [rbp+0B0h+pExceptionObject], rax
0x14001c8b1  mov     [rbp+0B0h+var_128], r12
0x14001c8b5  mov     [rsp+1B0h+var_160], rsi
0x14001c8ba  mov     [rsp+1B0h+var_158], 9
0x14001c8c3  lea     rax, [rsp+1B0h+var_170]
0x14001c8c8  mov     [rsp+1B0h+var_190], rax; char *
0x14001c8cd  lea     r9d, [r13+9]
0x14001c8d1  lea     r8, [rbp+0B0h+pExceptionObject]
0x14001c8d5  lea     rdx, [rsp+1B0h+var_160]
0x14001c8da  mov     rcx, [rbx+8]
0x14001c8de  call    ?GetOptionInteger@CommandArguments@@QEBAHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0HAEA_N@Z; CommandArguments::GetOptionInteger(std::wstring_view,std::wstring_view,int,bool &)
0x14001c8e3  mov     [rbx+0F4h], eax
0x14001c8e9  test    eax, eax
0x14001c8eb  jg      short loc_14001C960
0x14001c8ed  lea     rcx, WPP_GLOBAL_Control
0x14001c8f4  lea     ebx, [r13+56h]
0x14001c8f8  mov     rax, cs:WPP_GLOBAL_Control
0x14001c8ff  cmp     rax, rcx
0x14001c902  jz      short loc_14001C929
0x14001c904  test    dword ptr [rax+1Ch], 400000h
0x14001c90b  jz      short loc_14001C929
0x14001c90d  cmp     [rax+19h], r12b
0x14001c911  jb      short loc_14001C929
0x14001c913  lea     edx, [rbx-4Ch]
0x14001c916  mov     r9d, ebx
0x14001c919  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14001c920  mov     rcx, [rax+10h]
0x14001c924  call    WPP_SF_d
0x14001c929  mov     [rsp+1B0h+Src], rsi; Src
0x14001c92e  mov     [rsp+1B0h+var_180], 23h ; '#'; unsigned int
0x14001c936  mov     [rsp+1B0h+var_188], 3Dh ; '='; int
0x14001c93e  xor     r9d, r9d; unsigned int
0x14001c941  xor     r8d, r8d; unsigned int
0x14001c944  mov     edx, ebx; unsigned int
0x14001c946  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x14001c94a  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001c94f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001c956  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x14001c95a  call    _CxxThrowException_0
0x14001c960  lea     rax, aSbm; "sbm"
0x14001c967  mov     [rsp+1B0h+var_160], rax
0x14001c96c  mov     [rsp+1B0h+var_158], 3
0x14001c975  lea     rax, aSavebookmark; "savebookmark"
0x14001c97c  mov     [rbp+0B0h+pExceptionObject], rax
0x14001c980  mov     [rbp+0B0h+var_128], 0Ch
0x14001c988  lea     rax, [rsp+1B0h+var_170]
0x14001c98d  mov     [rsp+1B0h+var_190], rax
0x14001c992  lea     r9, ValueName
0x14001c999  lea     r8, [rsp+1B0h+var_160]
0x14001c99e  lea     rdx, [rbp+0B0h+pExceptionObject]
0x14001c9a2  mov     rcx, [rbx+8]
0x14001c9a6  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x14001c9ab  lea     rcx, [rbx+88h]
0x14001c9b2  mov     rdx, rax
0x14001c9b5  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14001c9ba  lea     rax, aE_0; "e"
0x14001c9c1  mov     [rsp+1B0h+var_160], rax
0x14001c9c6  mov     [rsp+1B0h+var_158], r13
0x14001c9cb  lea     rax, aElement; "element"
0x14001c9d2  mov     [rbp+0B0h+pExceptionObject], rax
0x14001c9d6  mov     [rbp+0B0h+var_128], 7
0x14001c9de  lea     rax, [rsp+1B0h+var_170]
0x14001c9e3  mov     [rsp+1B0h+var_190], rax
0x14001c9e8  lea     r9, ValueName
0x14001c9ef  lea     r8, [rsp+1B0h+var_160]
0x14001c9f4  lea     rdx, [rbp+0B0h+pExceptionObject]
0x14001c9f8  mov     rcx, [rbx+8]
0x14001c9fc  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x14001ca01  lea     rsi, [rbx+0A8h]
0x14001ca08  mov     rdx, rax
0x14001ca0b  mov     rcx, rsi
0x14001ca0e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14001ca13  lea     rax, aC; "c"
0x14001ca1a  mov     [rsp+1B0h+var_160], rax
0x14001ca1f  mov     [rsp+1B0h+var_158], r13
0x14001ca24  mov     [rbp+0B0h+pExceptionObject], r14
0x14001ca28  mov     [rbp+0B0h+var_128], 5
0x14001ca30  lea     rax, [rsp+1B0h+var_170]
0x14001ca35  mov     [rsp+1B0h+var_190], rax; char *
0x14001ca3a  xor     r9d, r9d
0x14001ca3d  lea     r8, [rsp+1B0h+var_160]
0x14001ca42  lea     rdx, [rbp+0B0h+pExceptionObject]
0x14001ca46  mov     rcx, [rbx+8]
0x14001ca4a  call    ?GetOptionInteger@CommandArguments@@QEBAHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0HAEA_N@Z; CommandArguments::GetOptionInteger(std::wstring_view,std::wstring_view,int,bool &)
0x14001ca4f  mov     [rbx+0F0h], eax
0x14001ca55  test    eax, eax
0x14001ca57  jg      loc_14001CB04
0x14001ca5d  lea     rax, aC; "c"
0x14001ca64  mov     [rsp+1B0h+var_160], rax
0x14001ca69  mov     [rsp+1B0h+var_158], r13
0x14001ca6e  mov     [rbp+0B0h+pExceptionObject], r14
0x14001ca72  mov     [rbp+0B0h+var_128], 5
0x14001ca7a  lea     r8, [rsp+1B0h+var_160]
0x14001ca7f  lea     rdx, [rbp+0B0h+pExceptionObject]
0x14001ca83  mov     rcx, [rbx+8]
0x14001ca87  call    ?HasOption@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::HasOption(std::wstring_view,std::wstring_view)
0x14001ca8c  test    al, al
0x14001ca8e  jz      short loc_14001CB04
0x14001ca90  lea     rcx, WPP_GLOBAL_Control
0x14001ca97  mov     ebx, 57h ; 'W'
0x14001ca9c  mov     rax, cs:WPP_GLOBAL_Control
0x14001caa3  cmp     rax, rcx
0x14001caa6  jz      short loc_14001CACD
0x14001caa8  test    dword ptr [rax+1Ch], 400000h
0x14001caaf  jz      short loc_14001CACD
0x14001cab1  cmp     [rax+19h], r12b
0x14001cab5  jb      short loc_14001CACD
0x14001cab7  lea     edx, [rbx-4Bh]
0x14001caba  mov     r9d, ebx
0x14001cabd  lea     r8, WPP_7bd34925a3543a347cbe4ddd5f03596d_Traceguids
0x14001cac4  mov     rcx, [rax+10h]
0x14001cac8  call    WPP_SF_d
0x14001cacd  mov     [rsp+1B0h+Src], r14; Src
0x14001cad2  mov     [rsp+1B0h+var_180], 23h ; '#'; unsigned int
0x14001cada  mov     [rsp+1B0h+var_188], 45h ; 'E'; int
0x14001cae2  xor     r9d, r9d; unsigned int
0x14001cae5  xor     r8d, r8d; unsigned int
0x14001cae8  mov     edx, ebx; unsigned int
0x14001caea  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x14001caee  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001caf3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001cafa  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x14001cafe  call    _CxxThrowException_0
0x14001cb04  lea     rax, aRd; "rd"
0x14001cb0b  mov     [rsp+1B0h+var_160], rax
0x14001cb10  mov     [rsp+1B0h+var_158], r12
0x14001cb15  lea     rax, aReversedirecti; "reversedirection"
0x14001cb1c  mov     [rbp+0B0h+pExceptionObject], rax
0x14001cb20  mov     [rbp+0B0h+var_128], 10h
0x14001cb28  lea     rax, [rsp+1B0h+var_170]
0x14001cb2d  mov     [rsp+1B0h+var_190], rax
0x14001cb32  lea     r8, [rsp+1B0h+var_160]
0x14001cb37  lea     rdx, [rbp+0B0h+pExceptionObject]
0x14001cb3b  mov     rcx, [rbx+8]
0x14001cb3f  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x14001cb44  mov     [rbx+102h], al
0x14001cb4a  lea     rax, aQ; "q"
0x14001cb51  mov     [rsp+1B0h+var_160], rax
0x14001cb56  mov     [rsp+1B0h+var_158], r13
0x14001cb5b  lea     rax, aQuery; "query"
0x14001cb62  mov     [rbp+0B0h+pExceptionObject], rax
0x14001cb66  mov     [rbp+0B0h+var_128], 5
0x14001cb6e  lea     rax, [rsp+1B0h+var_170]
0x14001cb73  mov     [rsp+1B0h+var_190], rax
0x14001cb78  lea     r9, asc_14003879C; "*"
0x14001cb7f  lea     r8, [rsp+1B0h+var_160]
0x14001cb84  lea     rdx, [rbp+0B0h+pExceptionObject]
0x14001cb88  mov     rcx, [rbx+8]
0x14001cb8c  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x14001cb91  mov     rdx, rax
0x14001cb94  lea     rcx, [rbx+48h]
0x14001cb98  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14001cb9d  lea     rax, aLf; "lf"
0x14001cba4  mov     [rsp+1B0h+var_160], rax
0x14001cba9  mov     [rsp+1B0h+var_158], r12
0x14001cbae  lea     rax, aLogfile; "logfile"
0x14001cbb5  mov     [rbp+0B0h+pExceptionObject], rax
0x14001cbb9  mov     [rbp+0B0h+var_128], 7
0x14001cbc1  lea     rax, [rsp+1B0h+var_170]
0x14001cbc6  mov     [rsp+1B0h+var_190], rax
0x14001cbcb  lea     r8, [rsp+1B0h+var_160]
0x14001cbd0  lea     rdx, [rbp+0B0h+pExceptionObject]
0x14001cbd4  mov     rcx, [rbx+8]
0x14001cbd8  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x14001cbdd  mov     [rbx+100h], al
0x14001cbe3  lea     rax, aSq; "sq"
0x14001cbea  mov     [rsp+1B0h+var_160], rax
0x14001cbef  mov     [rsp+1B0h+var_158], r12
0x14001cbf4  lea     rax, aStructuredquer; "structuredquery"
0x14001cbfb  mov     [rbp+0B0h+pExceptionObject], rax
0x14001cbff  mov     [rbp+0B0h+var_128], 0Fh
0x14001cc07  lea     rax, [rsp+1B0h+var_170]
0x14001cc0c  mov     [rsp+1B0h+var_190], rax; char *
0x14001cc11  lea     r8, [rsp+1B0h+var_160]
0x14001cc16  lea     rdx, [rbp+0B0h+pExceptionObject]
0x14001cc1a  mov     rcx, [rbx+8]
0x14001cc1e  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x14001cc23  mov     [rbx+101h], al
0x14001cc29  lea     rax, ?EnumNameValueEventFormat@@3QBU?$ENUM_NAMEVALUE_PAIR@W4WevtUtilEventFormat@@@@B; ENUM_NAMEVALUE_PAIR<WevtUtilEventFormat> const near * const EnumNameValueEventFormat
0x14001cc30  mov     [rsp+1B0h+var_160], rax
0x14001cc35  mov     [rsp+1B0h+var_158], 3
0x14001cc3e  lea     rax, asc_1400388B0; "f"
0x14001cc45  mov     [rbp+0B0h+pExceptionObject], rax
0x14001cc49  mov     [rbp+0B0h+var_128], r13
0x14001cc4d  lea     rax, aFormat; "format"
0x14001cc54  mov     [rsp+1B0h+var_150], rax
0x14001cc59  mov     [rsp+1B0h+var_148], 6
0x14001cc62  lea     r9, [rsp+1B0h+var_160]
0x14001cc67  lea     r8, [rbp+0B0h+pExceptionObject]
0x14001cc6b  lea     rdx, [rsp+1B0h+var_150]
0x14001cc70  mov     rcx, [rbx+8]
  ... truncated ...
```
