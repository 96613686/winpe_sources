# SetPrefBinCookie

- ea: `0x180037488`
- end: `0x18003789f`
- name: `SetPrefBinCookie`
- size: `1047`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18003799c`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x18000a914`
- `0x18000af40`
- `0x18000b1d8`
- `0x18000ba8c`
- `0x18000be18`
- `0x18000cc9c`
- `0x18000e784`
- `0x18000e870`
- `0x18000ecc4`
- `0x180037488`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037783`
- `WININET!InternetGetCookieW` at `0x180037628`
- `WININET!InternetGetCookieW` at `0x18003767d`
- `WININET!InternetGetCookieW` at `0x180037628`
- `WININET!InternetGetCookieW` at `0x18003767d`
- `WININET!InternetSetCookieExW` at `0x180037779`
- `WININET!InternetSetCookieExW` at `0x180037779`

## string_xrefs

- `0x1800376da`: `%d; path=/; domain=%s; expires=%s`
- `0x180037721`: `%s; path=/; domain=%s; expires=%s`
- `0x18003775a`: `CP="CAO DSP COR ADMa DEV CONo TELo CUR PSA PSD TAI IVDo OUR SAMi BUS DEM NAV STA UNI COM INT PHY ONL FIN PUR LOCi CNT"`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SetPrefBinCookie(__int64 a1, unsigned __int8 a2)
{
  unsigned int v2; // r15d
  __int64 v4; // rdx
  volatile signed __int32 *v5; // rcx
  volatile signed __int32 *v6; // rbx
  int *v7; // rdi
  volatile signed __int32 *v8; // rbx
  const WCHAR *v9; // rdi
  const WCHAR *v10; // rsi
  signed int LastError; // eax
  unsigned __int64 v12; // rcx
  signed int v13; // eax
  __int64 v14; // rdx
  volatile signed __int32 *v15; // rcx
  int *v16; // r14
  volatile signed __int32 *v17; // rbx
  unsigned int v18; // r14d
  const unsigned __int16 *dwReserved; // [rsp+20h] [rbp-E0h]
  DWORD_PTR dwReserveda; // [rsp+20h] [rbp-E0h]
  signed int v22; // [rsp+30h] [rbp-D0h] BYREF
  volatile signed __int32 *v23; // [rsp+38h] [rbp-C8h] BYREF
  DWORD dwSize[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpszCookieData; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszUrl; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v30[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h]
  WCHAR szCookieData[8]; // [rsp+90h] [rbp-70h] BYREF
  char v33[1008]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = a2;
  v22 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v23);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&lpszUrl);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v29);
  memset_0(szCookieData, 0, 0x400u);
  v25 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&lpszCookieData);
  v30[0] = "SetPrefBinCookie";
  v30[1] = &v22;
  v30[2] = 0;
  v31 = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\Live\\identity\\Include\\prefbin.h",
    "SetPrefBinCookie",
    (const char *)0x1B,
    0,
    dwReserved);
  v4 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                    a1,
                    dwSize,
                    L",;",
                    &v25);
  v5 = (volatile signed __int32 *)(v4 - 24);
  v6 = v23;
  v7 = (int *)(v23 - 6);
  if ( (volatile signed __int32 *)(v4 - 24) != v23 - 6 )
  {
    if ( v7[4] >= 0 && *(_QWORD *)v5 == *(_QWORD *)v7 )
    {
      v8 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v5);
      ATL::CStringData::Release((ATL::CStringData *)v7);
      v6 = v8 + 6;
      v23 = v6;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, v4, *(unsigned int *)(v4 - 16));
      v6 = v23;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)dwSize - 24LL));
  v9 = lpszUrl;
  v10 = lpszCookieData;
  while ( *((_DWORD *)v6 - 4) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&v23);
    v6 = v23;
    if ( !*((_DWORD *)v23 - 4) )
      goto LABEL_28;
    dwSize[0] = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &lpszUrl,
      L"https://%s",
      v23);
    szCookieData[0] = 0;
    dwSize[0] = 512;
    v9 = lpszUrl;
    if ( (_BYTE)v2 == 1 && (InternetGetCookieW(lpszUrl, L"ANON", szCookieData, dwSize) || GetLastError() != 259) )
    {
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\Live\\identity\\Include\\prefbin.h",
        0x32u,
        L"ANON cookie exists or we could not prove its absence, not setting PrefBin");
      goto LABEL_28;
    }
    szCookieData[0] = 0;
    dwSize[0] = 512;
    if ( !InternetGetCookieW(v9, L"PREFBIN", szCookieData, dwSize) )
    {
      LastError = GetLastError();
      if ( LastError != 259 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v22 = LastError;
        LODWORD(dwReserveda) = LastError;
        TracePrintW(
          2u,
          "clientcore\\ds\\ext\\Live\\identity\\Include\\prefbin.h",
          0x46u,
          L"Could not get internet cookie PREFBIN. 0x%x",
          dwReserveda);
        v22 = 0;
        goto LABEL_24;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &lpszCookieData,
        L"%d; path=/; domain=%s; expires=%s",
        v2,
        v6,
        L"Fri, 01-Jan-2021 00:00:00 GMT");
      goto LABEL_23;
    }
    v12 = -1;
    do
      ++v12;
    while ( szCookieData[v12] );
    if ( v12 > 8 )
    {
      szCookieData[v12 - 1] = v2 + 48;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &lpszCookieData,
        L"%s; path=/; domain=%s; expires=%s",
        v33,
        v6,
        L"Fri, 01-Jan-2021 00:00:00 GMT");
LABEL_23:
      v10 = lpszCookieData;
    }
LABEL_24:
    TracePrintW(
      5u,
      "clientcore\\ds\\ext\\Live\\identity\\Include\\prefbin.h",
      0x62u,
      L"Setting PrefBin=%ls in domain=%ls",
      v10,
      v9);
    if ( !InternetSetCookieExW(
            v9,
            L"PREFBIN",
            v10,
            0x40u,
            (DWORD_PTR)L"CP=\"CAO DSP COR ADMa DEV CONo TELo CUR PSA PSD TAI IVDo OUR SAMi BUS DEM NAV STA UNI COM INT PHY"
                        " ONL FIN PUR LOCi CNT\"") )
    {
      v13 = GetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      v22 = v13;
      LODWORD(dwReserveda) = v13;
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\Live\\identity\\Include\\prefbin.h",
        0x67u,
        L"Could not set internet cookie. 0x%x",
        dwReserveda);
    }
LABEL_28:
    v14 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                       a1,
                       &v28,
                       L",;",
                       &v25);
    v15 = (volatile signed __int32 *)(v14 - 24);
    v16 = (int *)(v6 - 6);
    if ( (volatile signed __int32 *)(v14 - 24) != v6 - 6 )
    {
      if ( v16[4] >= 0 && *(_QWORD *)v15 == *(_QWORD *)v16 )
      {
        v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v15);
        ATL::CStringData::Release((ATL::CStringData *)v16);
        v6 = v17 + 6;
        v23 = v6;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, v14, *(unsigned int *)(v14 - 16));
        v6 = v23;
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
  }
  v18 = v22;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v30);
  ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v6 - 6));
  return v18;
}

```

## disassembly

```asm
0x180037488  mov     [rsp-8+arg_10], rbx
0x18003748d  push    rbp
0x18003748e  push    rsi
0x18003748f  push    rdi
0x180037490  push    r12
0x180037492  push    r13
0x180037494  push    r14
0x180037496  push    r15
0x180037498  lea     rbp, [rsp-3A0h]
0x1800374a0  sub     rsp, 4A0h
0x1800374a7  mov     rax, cs:__security_cookie
0x1800374ae  xor     rax, rsp
0x1800374b1  mov     [rbp+3D0h+var_40], rax
0x1800374b8  movzx   r15d, dl
0x1800374bc  mov     r12, rcx
0x1800374bf  xor     r13d, r13d
0x1800374c2  mov     [rsp+4D0h+var_4A0], r13d
0x1800374c7  lea     rcx, [rsp+4D0h+var_498]
0x1800374cc  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800374d1  nop
0x1800374d2  lea     rcx, [rsp+4D0h+lpszUrl]
0x1800374d7  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800374dc  nop
0x1800374dd  lea     rcx, [rsp+4D0h+var_468]
0x1800374e2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800374e7  nop
0x1800374e8  xor     edx, edx; Val
0x1800374ea  mov     r8d, 400h; Size
0x1800374f0  lea     rcx, [rbp+3D0h+szCookieData]; void *
0x1800374f4  call    memset_0
0x1800374f9  mov     [rsp+4D0h+var_488], r13d
0x1800374fe  lea     rcx, [rsp+4D0h+lpszCookieData]
0x180037503  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180037508  nop
0x180037509  lea     rdx, aSetprefbincook_1; "SetPrefBinCookie"
0x180037510  mov     [rsp+4D0h+var_460], rdx
0x180037515  lea     rax, [rsp+4D0h+var_4A0]
0x18003751a  mov     [rsp+4D0h+var_458], rax
0x18003751f  mov     [rbp+3D0h+var_450], r13
0x180037523  mov     [rbp+3D0h+var_448], r13
0x180037527  xor     r9d, r9d; unsigned int
0x18003752a  lea     r8d, [r13+1Bh]; char *
0x18003752e  lea     r14, aClientcoreDsEx_8; "clientcore\\ds\\ext\\Live\\identity\\In"...
0x180037535  mov     rcx, r14; this
0x180037538  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003753d  nop
0x18003753e  lea     r9, [rsp+4D0h+var_488]
0x180037543  lea     r8, asc_1800715A8; ",;"
0x18003754a  lea     rdx, [rsp+4D0h+dwSize]
0x18003754f  mov     rcx, r12
0x180037552  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x180037557  nop
0x180037558  mov     rdx, [rax]
0x18003755b  lea     rcx, [rdx-18h]
0x18003755f  mov     rbx, [rsp+4D0h+var_498]
0x180037564  lea     rdi, [rbx-18h]
0x180037568  cmp     rcx, rdi
0x18003756b  jz      short loc_1800375A9
0x18003756d  cmp     [rdi+10h], r13d
0x180037571  jl      short loc_180037596
0x180037573  mov     rax, [rdi]
0x180037576  cmp     [rcx], rax
0x180037579  jnz     short loc_180037596
0x18003757b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180037580  mov     rbx, rax
0x180037583  mov     rcx, rdi; this
0x180037586  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003758b  add     rbx, 18h
0x18003758f  mov     [rsp+4D0h+var_498], rbx
0x180037594  jmp     short loc_1800375A9
0x180037596  mov     r8d, [rdx-10h]
0x18003759a  lea     rcx, [rsp+4D0h+var_498]
0x18003759f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800375a4  mov     rbx, [rsp+4D0h+var_498]
0x1800375a9  mov     rcx, qword ptr [rsp+4D0h+dwSize]
0x1800375ae  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800375b2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800375b7  mov     rdi, [rsp+4D0h+lpszUrl]
0x1800375bc  mov     rsi, [rsp+4D0h+lpszCookieData]
0x1800375c1  cmp     [rbx-10h], r13d
0x1800375c5  jz      loc_180037836
0x1800375cb  lea     rcx, [rsp+4D0h+var_498]
0x1800375d0  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x1800375d5  mov     rbx, [rsp+4D0h+var_498]
0x1800375da  cmp     [rbx-10h], r13d
0x1800375de  jz      loc_1800377B6
0x1800375e4  mov     [rsp+4D0h+dwSize], r13d
0x1800375e9  mov     r8, rbx
0x1800375ec  lea     rdx, aHttpsS; "https://%s"
0x1800375f3  lea     rcx, [rsp+4D0h+lpszUrl]
0x1800375f8  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800375fd  mov     [rbp+3D0h+szCookieData], r13w
0x180037602  mov     [rsp+4D0h+dwSize], 200h
0x18003760a  mov     rdi, [rsp+4D0h+lpszUrl]
0x18003760f  cmp     r15b, 1
0x180037613  jnz     short loc_18003765D
0x180037615  lea     r9, [rsp+4D0h+dwSize]; lpdwSize
0x18003761a  lea     r8, [rbp+3D0h+szCookieData]; lpszCookieData
0x18003761e  lea     rdx, szCookieName; "ANON"
0x180037625  mov     rcx, rdi; lpszUrl
0x180037628  call    cs:__imp_InternetGetCookieW
0x18003762e  test    eax, eax
0x180037630  jnz     short loc_18003763F
0x180037632  call    cs:__imp_GetLastError
0x180037638  cmp     eax, 103h
0x18003763d  jz      short loc_18003765D
0x18003763f  lea     r9, aAnonCookieExis; "ANON cookie exists or we could not prov"...
0x180037646  mov     r8d, 32h ; '2'; unsigned int
0x18003764c  mov     rdx, r14; char *
0x18003764f  lea     ecx, [r8-2Dh]; unsigned __int8
0x180037653  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180037658  jmp     loc_1800377B6
0x18003765d  mov     [rbp+3D0h+szCookieData], r13w
0x180037662  mov     [rsp+4D0h+dwSize], 200h
0x18003766a  lea     r9, [rsp+4D0h+dwSize]; lpdwSize
0x18003766f  lea     r8, [rbp+3D0h+szCookieData]; lpszCookieData
0x180037673  lea     rdx, aPrefbin; "PREFBIN"
0x18003767a  mov     rcx, rdi; lpszUrl
0x18003767d  call    cs:__imp_InternetGetCookieW
0x180037683  test    eax, eax
0x180037685  jnz     short loc_1800376ED
0x180037687  call    cs:__imp_GetLastError
0x18003768d  cmp     eax, 103h
0x180037692  jz      short loc_1800376C8
0x180037694  test    eax, eax
0x180037696  jle     short loc_1800376A0
0x180037698  movzx   eax, ax
0x18003769b  or      eax, 80070000h
0x1800376a0  mov     [rsp+4D0h+var_4A0], eax
0x1800376a4  mov     dword ptr [rsp+4D0h+dwReserved], eax
0x1800376a8  lea     r9, aCouldNotGetInt_0; "Could not get internet cookie PREFBIN. "...
0x1800376af  mov     r8d, 46h ; 'F'; unsigned int
0x1800376b5  mov     rdx, r14; char *
0x1800376b8  lea     ecx, [r8-44h]; unsigned __int8
0x1800376bc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800376c1  mov     [rsp+4D0h+var_4A0], r13d
0x1800376c6  jmp     short loc_180037737
0x1800376c8  mov     r8d, r15d
0x1800376cb  lea     rax, aFri01Jan202100; "Fri, 01-Jan-2021 00:00:00 GMT"
0x1800376d2  mov     [rsp+4D0h+dwReserved], rax
0x1800376d7  mov     r9, rbx
0x1800376da  lea     rdx, aDPathDomainSEx; "%d; path=/; domain=%s; expires=%s"
0x1800376e1  lea     rcx, [rsp+4D0h+lpszCookieData]
0x1800376e6  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800376eb  jmp     short loc_180037732
0x1800376ed  lea     rax, [rbp+3D0h+szCookieData]
0x1800376f1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800376f5  inc     rcx
0x1800376f8  cmp     [rax+rcx*2], r13w
0x1800376fd  jnz     short loc_1800376F5
0x1800376ff  cmp     rcx, 8
0x180037703  jbe     short loc_180037737
0x180037705  lea     eax, [r15+30h]
0x180037709  mov     word ptr [rbp+rcx*2+3D0h+var_448+6], ax
0x18003770e  lea     rax, aFri01Jan202100; "Fri, 01-Jan-2021 00:00:00 GMT"
0x180037715  mov     [rsp+4D0h+dwReserved], rax
0x18003771a  mov     r9, rbx
0x18003771d  lea     r8, [rbp+3D0h+var_430]
0x180037721  lea     rdx, aSPathDomainSEx; "%s; path=/; domain=%s; expires=%s"
0x180037728  lea     rcx, [rsp+4D0h+lpszCookieData]
0x18003772d  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180037732  mov     rsi, [rsp+4D0h+lpszCookieData]
0x180037737  mov     [rsp+4D0h+var_4A8], rdi
0x18003773c  mov     [rsp+4D0h+dwReserved], rsi
0x180037741  lea     r9, aSettingPrefbin; "Setting PrefBin=%ls in domain=%ls"
0x180037748  mov     r8d, 62h ; 'b'; unsigned int
0x18003774e  mov     rdx, r14; char *
0x180037751  lea     ecx, [r8-5Dh]; unsigned __int8
0x180037755  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003775a  lea     rax, dwReserved; "CP=\"CAO DSP COR ADMa DEV CONo TELo CUR"...
0x180037761  mov     [rsp+4D0h+dwReserved], rax; dwReserved
0x180037766  mov     r9d, 40h ; '@'; dwFlags
0x18003776c  mov     r8, rsi; lpszCookieData
0x18003776f  lea     rdx, aPrefbin; "PREFBIN"
0x180037776  mov     rcx, rdi; lpszUrl
0x180037779  call    cs:__imp_InternetSetCookieExW
0x18003777f  test    eax, eax
0x180037781  jnz     short loc_1800377B6
0x180037783  call    cs:__imp_GetLastError
0x180037789  test    eax, eax
0x18003778b  jle     short loc_180037795
0x18003778d  movzx   eax, ax
0x180037790  or      eax, 80070000h
0x180037795  mov     [rsp+4D0h+var_4A0], eax
0x180037799  mov     dword ptr [rsp+4D0h+dwReserved], eax
0x18003779d  lea     r9, aCouldNotSetInt; "Could not set internet cookie. 0x%x"
0x1800377a4  mov     r8d, 67h ; 'g'; unsigned int
0x1800377aa  mov     rdx, r14; char *
0x1800377ad  lea     ecx, [r8-65h]; unsigned __int8
0x1800377b1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800377b6  lea     r9, [rsp+4D0h+var_488]
0x1800377bb  lea     r8, asc_1800715A8; ",;"
0x1800377c2  lea     rdx, [rsp+4D0h+var_470]
0x1800377c7  mov     rcx, r12
0x1800377ca  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x1800377cf  nop
0x1800377d0  mov     rdx, [rax]
0x1800377d3  lea     rcx, [rdx-18h]
0x1800377d7  lea     r14, [rbx-18h]
0x1800377db  cmp     rcx, r14
0x1800377de  jz      short loc_18003781C
0x1800377e0  cmp     [r14+10h], r13d
0x1800377e4  jl      short loc_180037809
0x1800377e6  mov     rax, [r14]
0x1800377e9  cmp     [rcx], rax
0x1800377ec  jnz     short loc_180037809
0x1800377ee  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800377f3  mov     rbx, rax
0x1800377f6  mov     rcx, r14; this
0x1800377f9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800377fe  add     rbx, 18h
0x180037802  mov     [rsp+4D0h+var_498], rbx
0x180037807  jmp     short loc_18003781C
0x180037809  mov     r8d, [rdx-10h]
0x18003780d  lea     rcx, [rsp+4D0h+var_498]
0x180037812  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180037817  mov     rbx, [rsp+4D0h+var_498]
0x18003781c  mov     rcx, [rsp+4D0h+var_470]
0x180037821  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180037825  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003782a  lea     r14, aClientcoreDsEx_8; "clientcore\\ds\\ext\\Live\\identity\\In"...
0x180037831  jmp     loc_1800375C1
0x180037836  mov     r14d, [rsp+4D0h+var_4A0]
0x18003783b  lea     rcx, [rsp+4D0h+var_460]
0x180037840  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180037845  nop
0x180037846  lea     rcx, [rsi-18h]; this
0x18003784a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003784f  nop
0x180037850  mov     rcx, [rsp+4D0h+var_468]
0x180037855  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180037859  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003785e  nop
0x18003785f  lea     rcx, [rdi-18h]; this
0x180037863  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037868  nop
0x180037869  lea     rcx, [rbx-18h]; this
0x18003786d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037872  mov     eax, r14d
0x180037875  mov     rcx, [rbp+3D0h+var_40]
0x18003787c  xor     rcx, rsp; StackCookie
0x18003787f  call    __security_check_cookie
0x180037884  mov     rbx, [rsp+4D0h+arg_10]
0x18003788c  add     rsp, 4A0h
0x180037893  pop     r15
0x180037895  pop     r14
0x180037897  pop     r13
0x180037899  pop     r12
0x18003789b  pop     rdi
0x18003789c  pop     rsi
0x18003789d  pop     rbp
0x18003789e  retn
```
