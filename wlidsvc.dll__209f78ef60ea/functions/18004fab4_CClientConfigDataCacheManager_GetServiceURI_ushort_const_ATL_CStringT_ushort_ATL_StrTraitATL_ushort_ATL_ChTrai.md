# CClientConfigDataCacheManager::GetServiceURI(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18004fab4`
- end: `0x18004fe36`
- name: `?GetServiceURI@CClientConfigDataCacheManager@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `898`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004908c`
- `0x18004fa80`
- `0x18005cd10`
- `0x180086320`
- `0x1800990c0`
- `0x1800f1f20`

## callees

- `0x18000c050`
- `0x18000c280`
- `0x18000e488`
- `0x18000ed04`
- `0x180013510`
- `0x180014330`
- `0x180014490`
- `0x180014640`
- `0x1800151c4`
- `0x180015860`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180026c18`
- `0x180030a8c`
- `0x18003722c`
- `0x18004fab4`
- `0x1800a4778`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fc8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd7f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fbd3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fc30`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fc51`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fbd3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fc30`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fc51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fba8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fbe0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fba8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fbe0`
- `WINHTTP!WinHttpCreateUrl` at `0x18004fd75`
- `WINHTTP!WinHttpCreateUrl` at `0x18004fd75`
- `WINHTTP!WinHttpCrackUrl` at `0x18004fc80`
- `WINHTTP!WinHttpCrackUrl` at `0x18004fc80`

## string_xrefs

- `0x18004fb25`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x18004fb5a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x18004fcb5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x18004fdb8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x18004faf6`: `CClientConfigDataCacheManager::GetServiceURI`
- `0x18004fdb1`: `CClientConfigDataCacheManager::GetServiceURI`
- `0x18004fca8`: `InternetCrackUrl failed for Config value: %ls, it may not be a URL. (0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CClientConfigDataCacheManager::GetServiceURI(__int64 a1, __int64 a2, LPCWSTR *a3)
{
  LPCWSTR *v3; // rsi
  volatile signed __int32 *v6; // r15
  volatile signed __int32 *v7; // r14
  _QWORD *v8; // rax
  signed int v9; // eax
  INTERNET_PORT OneBoxSSLPort; // ax
  LPCWSTR *v11; // rcx
  WCHAR *Buffer; // rax
  signed int LastError; // eax
  unsigned int v14; // edi
  char *v16; // [rsp+20h] [rbp-F8h]
  __int64 v17; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v18; // [rsp+38h] [rbp-E0h] BYREF
  int v19; // [rsp+40h] [rbp-D8h] BYREF
  _QWORD v20[5]; // [rsp+48h] [rbp-D0h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+70h] [rbp-A8h] BYREF
  int v22; // [rsp+128h] [rbp+10h] BYREF
  LPCWSTR *v23; // [rsp+130h] [rbp+18h]
  __int64 pdwUrlLength; // [rsp+138h] [rbp+20h] BYREF

  v23 = a3;
  v3 = a3;
  v22 = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v18);
  v20[0] = "CClientConfigDataCacheManager::GetServiceURI";
  v20[1] = &v22;
  v20[2] = 0;
  v20[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    "CClientConfigDataCacheManager::GetServiceURI",
    (const char *)0x804,
    0,
    (const unsigned __int16 *)v16);
  if ( a2 )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v18, a2);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v18);
    pdwUrlLength = a1 + 832;
    v6 = (volatile signed __int32 *)(a1 + 844);
    do
    {
      if ( *(int *)(a1 + 840) > 0 )
      {
        v7 = v6;
        if ( WaitForSingleObject(*(HANDLE *)(a1 + 856), 0xFFFFFFFF) )
          break;
      }
      v6 = (volatile signed __int32 *)(a1 + 844);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 844));
      v7 = (volatile signed __int32 *)(a1 + 844);
      if ( *(int *)(a1 + 840) <= 0 )
        break;
      if ( _InterlockedExchangeAdd(v6, 0xFFFFFFFF) == 1 )
        SetEvent(*(HANDLE *)(a1 + 848));
    }
    while ( !WaitForSingleObject(*(HANDLE *)(a1 + 856), 0xFFFFFFFF) );
    v8 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&v18);
    if ( (unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Lookup(
                            a1 + 48,
                            *v8,
                            v3) )
    {
      if ( _InterlockedExchangeAdd(v7, 0xFFFFFFFF) == 1 && *(int *)(a1 + 840) > 0 )
        SetEvent(*(HANDLE *)(a1 + 848));
      UrlComponents.dwStructSize = 104;
      UrlComponents.dwHostNameLength = 1;
      UrlComponents.dwUrlPathLength = 1;
      if ( WinHttpCrackUrl(*v3, *((_DWORD *)*v3 - 4), 0, &UrlComponents) )
      {
        if ( UrlComponents.nScheme == INTERNET_SCHEME_GOPHER )
        {
          LODWORD(pdwUrlLength) = 0;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v17);
          ATL::CSimpleStringT<unsigned short,0>::SetString(
            &v17,
            UrlComponents.lpszHostName,
            UrlComponents.dwHostNameLength);
          OneBoxSSLPort = GetOneBoxSSLPort(&v17);
          if ( OneBoxSSLPort )
          {
            UrlComponents.nPort = OneBoxSSLPort;
            LODWORD(pdwUrlLength) = 2084;
            ATL::CSimpleStringT<unsigned short,0>::SetString(v3, &qword_18013DE20);
            try
            {
              ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(v3, (unsigned int)(pdwUrlLength + 1));
              v11 = v3;
            }
            catch ( ATL::CAtlException v19 )
            {
              v22 = v19;
              TracePrintW(
                2u,
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
                0x839u,
                L"Could not allocate memory for strVal. 0x%x",
                v19);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v17);
              v3 = v23;
              goto LABEL_31;
            }
            Buffer = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v11);
            if ( WinHttpCreateUrl(&UrlComponents, 0x80000000, Buffer, (LPDWORD)&pdwUrlLength) )
              goto LABEL_30;
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v22 = LastError;
            if ( LastError >= 0 )
LABEL_30:
              ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v3, 0xFFFFFFFFLL);
            else
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
                "CClientConfigDataCacheManager::GetServiceURI",
                0x83Du,
                LastError,
                "hr = HRESULT_FROM_WIN32(GetLastError())");
          }
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v17);
        }
      }
      else
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
          0x81Au,
          L"InternetCrackUrl failed for Config value: %ls, it may not be a URL. (0x%x)",
          *v3,
          v9);
      }
    }
    else
    {
      v22 = 1;
      if ( _InterlockedExchangeAdd(v7, 0xFFFFFFFF) == 1 && *(int *)(a1 + 840) > 0 )
        SetEvent(*(HANDLE *)(a1 + 848));
    }
  }
  else
  {
    v22 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "CClientConfigDataCacheManager::GetServiceURI",
      0x806u,
      -2147024809,
      "szPropName != nullptr");
  }
LABEL_31:
  v14 = v22;
  if ( v22 < 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      v3,
      &cchOriginalDestLength);
    v14 = v22;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v20);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v18);
  return v14;
}

```

## disassembly

```asm
0x18004fab4  mov     rax, rsp
0x18004fab7  mov     [rax+18h], r8
0x18004fabb  push    rbx
0x18004fabc  push    rsi
0x18004fabd  push    rdi
0x18004fabe  push    r12
0x18004fac0  push    r13
0x18004fac2  push    r14
0x18004fac4  push    r15
0x18004fac6  sub     rsp, 0E0h
0x18004facd  mov     rsi, r8
0x18004fad0  mov     rdi, rdx
0x18004fad3  mov     r13, rcx
0x18004fad6  xor     ebx, ebx
0x18004fad8  mov     [rax+10h], ebx
0x18004fadb  xor     edx, edx; Val
0x18004fadd  lea     r8d, [rbx+68h]; Size
0x18004fae1  lea     rcx, [rsp+118h+UrlComponents]; void *
0x18004fae6  call    memset_0
0x18004faeb  lea     rcx, [rsp+118h+var_E0]
0x18004faf0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004faf5  nop
0x18004faf6  lea     r14, aCclientconfigd_9; "CClientConfigDataCacheManager::GetServi"...
0x18004fafd  mov     [rsp+118h+var_D0], r14
0x18004fb02  lea     rax, [rsp+118h+arg_8]
0x18004fb0a  mov     [rsp+118h+var_C8], rax
0x18004fb0f  mov     [rsp+118h+var_C0], rbx
0x18004fb14  mov     [rsp+118h+var_B8], rbx
0x18004fb19  xor     r9d, r9d; unsigned int
0x18004fb1c  mov     r8d, 804h; char *
0x18004fb22  mov     rdx, r14; char *
0x18004fb25  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004fb2c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18004fb31  nop
0x18004fb32  test    rdi, rdi
0x18004fb35  jnz     short loc_18004FB6B
0x18004fb37  mov     r9d, 80070057h; int
0x18004fb3d  mov     [rsp+118h+arg_8], r9d
0x18004fb45  lea     rax, aSzpropnameNull; "szPropName != nullptr"
0x18004fb4c  mov     [rsp+118h+var_F8], rax; char *
0x18004fb51  mov     r8d, 806h; unsigned int
0x18004fb57  mov     rdx, r14; char *
0x18004fb5a  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004fb61  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18004fb66  jmp     loc_18004FDEB
0x18004fb6b  mov     rdx, rdi
0x18004fb6e  lea     rcx, [rsp+118h+var_E0]
0x18004fb73  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004fb78  lea     rcx, [rsp+118h+var_E0]
0x18004fb7d  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x18004fb82  lea     rdi, [r13+340h]
0x18004fb89  mov     [rsp+118h+pdwUrlLength], rdi
0x18004fb91  lea     r15, [rdi+0Ch]
0x18004fb95  or      r12d, 0FFFFFFFFh
0x18004fb99  cmp     [rdi+8], ebx
0x18004fb9c  jle     short loc_18004FBB2
0x18004fb9e  mov     r14, r15
0x18004fba1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004fba4  mov     rcx, [rdi+18h]; hHandle
0x18004fba8  call    cs:__imp_WaitForSingleObject
0x18004fbae  test    eax, eax
0x18004fbb0  jnz     short loc_18004FBEA
0x18004fbb2  lea     r15, [rdi+0Ch]
0x18004fbb6  lock inc dword ptr [r15]
0x18004fbba  mov     r14, r15
0x18004fbbd  cmp     [rdi+8], ebx
0x18004fbc0  jle     short loc_18004FBEA
0x18004fbc2  mov     eax, r12d
0x18004fbc5  lock xadd [r15], eax
0x18004fbca  add     eax, r12d
0x18004fbcd  jnz     short loc_18004FBD9
0x18004fbcf  mov     rcx, [rdi+10h]; hEvent
0x18004fbd3  call    cs:__imp_SetEvent
0x18004fbd9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004fbdc  mov     rcx, [rdi+18h]; hHandle
0x18004fbe0  call    cs:__imp_WaitForSingleObject
0x18004fbe6  test    eax, eax
0x18004fbe8  jz      short loc_18004FB99
0x18004fbea  lea     rcx, [rsp+118h+var_E0]
0x18004fbef  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x18004fbf4  lea     rcx, [r13+30h]
0x18004fbf8  mov     r8, rsi
0x18004fbfb  mov     rdx, [rax]
0x18004fbfe  call    ?Lookup@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Lookup(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18004fc03  test    al, al
0x18004fc05  jnz     short loc_18004FC3B
0x18004fc07  mov     [rsp+118h+arg_8], 1
0x18004fc12  mov     eax, r12d
0x18004fc15  lock xadd [r14], eax
0x18004fc1a  add     eax, r12d
0x18004fc1d  jnz     loc_18004FDEB
0x18004fc23  cmp     [rdi+8], ebx
0x18004fc26  jle     loc_18004FDEB
0x18004fc2c  mov     rcx, [rdi+10h]; hEvent
0x18004fc30  call    cs:__imp_SetEvent
0x18004fc36  jmp     loc_18004FDEB
0x18004fc3b  mov     eax, r12d
0x18004fc3e  lock xadd [r14], eax
0x18004fc43  add     eax, r12d
0x18004fc46  jnz     short loc_18004FC57
0x18004fc48  cmp     [rdi+8], ebx
0x18004fc4b  jle     short loc_18004FC57
0x18004fc4d  mov     rcx, [rdi+10h]; hEvent
0x18004fc51  call    cs:__imp_SetEvent
0x18004fc57  mov     [rsp+118h+UrlComponents.dwStructSize], 68h ; 'h'
0x18004fc5f  mov     eax, 1
0x18004fc64  mov     [rsp+118h+UrlComponents.dwHostNameLength], eax
0x18004fc6b  mov     [rsp+118h+UrlComponents.dwUrlPathLength], eax
0x18004fc72  mov     rcx, [rsi]; pwszUrl
0x18004fc75  lea     r9, [rsp+118h+UrlComponents]; lpUrlComponents
0x18004fc7a  xor     r8d, r8d; dwFlags
0x18004fc7d  mov     edx, [rcx-10h]; dwUrlLength
0x18004fc80  call    cs:__imp_WinHttpCrackUrl
0x18004fc86  test    eax, eax
0x18004fc88  jnz     short loc_18004FCCB
0x18004fc8a  call    cs:__imp_GetLastError
0x18004fc90  test    eax, eax
0x18004fc92  jle     short loc_18004FC9C
0x18004fc94  movzx   eax, ax
0x18004fc97  or      eax, 80070000h
0x18004fc9c  mov     [rsp+118h+var_F0], eax
0x18004fca0  mov     rax, [rsi]
0x18004fca3  mov     [rsp+118h+var_F8], rax
0x18004fca8  lea     r9, aInternetcracku; "InternetCrackUrl failed for Config valu"...
0x18004fcaf  mov     r8d, 81Ah; unsigned int
0x18004fcb5  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004fcbc  mov     ecx, 2; unsigned __int8
0x18004fcc1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004fcc6  jmp     loc_18004FDEB
0x18004fccb  cmp     [rsp+118h+UrlComponents.nScheme], 2
0x18004fcd3  jnz     loc_18004FDEB
0x18004fcd9  mov     dword ptr [rsp+118h+pdwUrlLength], ebx
0x18004fce0  lea     rcx, [rsp+118h+var_E8]
0x18004fce5  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004fcea  nop
0x18004fceb  mov     r8d, [rsp+118h+UrlComponents.dwHostNameLength]
0x18004fcf3  mov     rdx, [rsp+118h+UrlComponents.lpszHostName]
0x18004fcfb  lea     rcx, [rsp+118h+var_E8]
0x18004fd00  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004fd05  lea     rcx, [rsp+118h+var_E8]
0x18004fd0a  call    ?GetOneBoxSSLPort@@YAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetOneBoxSSLPort(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18004fd0f  test    ax, ax
0x18004fd12  jnz     short loc_18004FD23
0x18004fd14  lea     rcx, [rsp+118h+var_E8]
0x18004fd19  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004fd1e  jmp     loc_18004FDEB
0x18004fd23  mov     [rsp+118h+UrlComponents.nPort], ax
0x18004fd2b  mov     dword ptr [rsp+118h+pdwUrlLength], 824h
0x18004fd36  lea     rdx, qword_18013DE20
0x18004fd3d  mov     rcx, rsi
0x18004fd40  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004fd45  nop
0x18004fd46  mov     edx, dword ptr [rsp+118h+pdwUrlLength]
0x18004fd4d  inc     edx
0x18004fd4f  mov     rcx, rsi
0x18004fd52  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x18004fd57  nop
0x18004fd58  mov     rcx, rsi
0x18004fd5b  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18004fd60  mov     r8, rax; pwszUrl
0x18004fd63  lea     r9, [rsp+118h+pdwUrlLength]; pdwUrlLength
0x18004fd6b  mov     edx, 80000000h; dwFlags
0x18004fd70  lea     rcx, [rsp+118h+UrlComponents]; lpUrlComponents
0x18004fd75  call    cs:__imp_WinHttpCreateUrl
0x18004fd7b  test    eax, eax
0x18004fd7d  jnz     short loc_18004FDC9
0x18004fd7f  call    cs:__imp_GetLastError
0x18004fd85  test    eax, eax
0x18004fd87  jle     short loc_18004FD91
0x18004fd89  movzx   eax, ax
0x18004fd8c  or      eax, 80070000h
0x18004fd91  mov     [rsp+118h+arg_8], eax
0x18004fd98  test    eax, eax
0x18004fd9a  jns     short loc_18004FDC9
0x18004fd9c  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18004fda3  mov     [rsp+118h+var_F8], rcx; char *
0x18004fda8  mov     r9d, eax; int
0x18004fdab  mov     r8d, 83Dh; unsigned int
0x18004fdb1  lea     rdx, aCclientconfigd_9; "CClientConfigDataCacheManager::GetServi"...
0x18004fdb8  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004fdbf  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18004fdc4  jmp     loc_18004FD14
0x18004fdc9  mov     edx, r12d
0x18004fdcc  mov     rcx, rsi
0x18004fdcf  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18004fdd4  jmp     loc_18004FD14
0x18004fdd9  lea     rcx, [rsp+118h+var_E8]
0x18004fdde  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004fde3  mov     rsi, [rsp+118h+arg_10]
0x18004fdeb  mov     edi, [rsp+118h+arg_8]
0x18004fdf2  test    edi, edi
0x18004fdf4  jns     short loc_18004FE0C
0x18004fdf6  lea     rdx, cchOriginalDestLength
0x18004fdfd  mov     rcx, rsi
0x18004fe00  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x18004fe05  mov     edi, [rsp+118h+arg_8]
0x18004fe0c  lea     rcx, [rsp+118h+var_D0]
0x18004fe11  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18004fe16  nop
0x18004fe17  lea     rcx, [rsp+118h+var_E0]
0x18004fe1c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004fe21  mov     eax, edi
0x18004fe23  add     rsp, 0E0h
0x18004fe2a  pop     r15
0x18004fe2c  pop     r14
0x18004fe2e  pop     r13
0x18004fe30  pop     r12
0x18004fe32  pop     rdi
0x18004fe33  pop     rsi
0x18004fe34  pop     rbx
0x18004fe35  retn
```
