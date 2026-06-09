# TNameResolutionCache::AddName(ushort const *)

- ea: `0x1400088b0`
- end: `0x140009188`
- name: `?AddName@TNameResolutionCache@@QEAAJPEBG@Z`
- size: `2264`
- prototype: `int(TNameResolutionCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140008720`

## callees

- `0x140007bdc`
- `0x140007cec`
- `0x1400088b0`
- `0x1400095cc`
- `0x140009930`
- `0x14000f4c8`
- `0x14000f620`
- `0x14001128c`
- `0x1400140cc`
- `0x140014eb0`
- `0x1400153e0`
- `0x14002a830`
- `0x14002a870`
- `0x14002abc0`
- `0x14002bbcc`
- `0x14006f970`
- `0x14006fae4`
- `0x14006fcb0`
- `0x140070468`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x140009076`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x140009076`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140008938`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140008e60`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140008eb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140008938`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140008e60`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140008eb4`
- `ntdll!RtlNtStatusToDosError` at `0x140008d7d`
- `ntdll!RtlNtStatusToDosError` at `0x140008d7d`
- `ntdll!NtClose` at `0x14000917d`
- `ntdll!NtClose` at `0x14000917d`
- `ntdll!NtSetInformationThread` at `0x140008d6d`
- `ntdll!NtSetInformationThread` at `0x140008d6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000898a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000898a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400088fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400088fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008da7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008d50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008d85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000915a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009172`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008d50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008d85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000915a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009172`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008906`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140008daf`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140008daf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008e1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008ec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008e1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008ec1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140008d40`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140008d40`
- `KERNEL32!WideCharToMultiByte` at `0x140008bcf`
- `KERNEL32!WideCharToMultiByte` at `0x140008c1c`
- `KERNEL32!WideCharToMultiByte` at `0x140008bcf`
- `KERNEL32!WideCharToMultiByte` at `0x140008c1c`
- `WS2_32!FreeAddrInfoW` at `0x140008f7d`
- `WS2_32!FreeAddrInfoW` at `0x140008f7d`
- `WS2_32!GetAddrInfoW` at `0x140008a3d`
- `WS2_32!GetAddrInfoW` at `0x140008a3d`
- `WS2_32!GetNameInfoW` at `0x140008f61`
- `WS2_32!GetNameInfoW` at `0x140008f61`
- `WS2_32!__imp_WSAGetLastError` at `0x140008db6`
- `WS2_32!__imp_WSAGetLastError` at `0x140008db6`
- `WS2_32!__imp_WSAStartup` at `0x1400089f1`
- `WS2_32!__imp_WSAStartup` at `0x1400089f1`
- `WS2_32!__imp_WSACleanup` at `0x140008f8a`
- `WS2_32!__imp_WSACleanup` at `0x140008f8a`
- `srvcli!NetServerTransportEnum` at `0x140008b79`
- `srvcli!NetServerTransportEnum` at `0x140008b79`
- `srvcli!NetServerGetInfo` at `0x140009096`
- `srvcli!NetServerGetInfo` at `0x140009096`
- `netutils!NetApiBufferFree` at `0x140008c69`
- `netutils!NetApiBufferFree` at `0x1400090cf`
- `netutils!NetApiBufferFree` at `0x140008c69`
- `netutils!NetApiBufferFree` at `0x1400090cf`

## string_xrefs

- `0x140008d9b`: `ImpersonatePrinterClient`

## pseudocode

```c
__int64 __fastcall TNameResolutionCache::AddName(TNameResolutionCache *this, WCHAR *a2)
{
  TNameResolutionCache *v3; // r13
  char *v4; // r14
  _QWORD *v5; // rsi
  _QWORD *v6; // rdi
  __int64 v7; // r12
  signed int LastErrorAsHResult; // ebx
  __int64 v9; // rbx
  unsigned __int16 *v11; // r14
  unsigned __int16 *v12; // rdi
  int v13; // eax
  TNameResolutionCache *v14; // rcx
  signed int v15; // ebx
  INT AddrInfoW; // eax
  __int64 v17; // rsi
  unsigned __int64 v18; // rdx
  unsigned __int16 *v19; // r12
  signed int v20; // eax
  bool v21; // zf
  __int64 v22; // rdi
  int v23; // eax
  int v24; // ebx
  CHAR *v25; // rax
  CHAR *v26; // rsi
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  __int64 j; // r13
  const unsigned int **v30; // rdi
  const unsigned int **v31; // rcx
  const unsigned int **v32; // rdi
  DWORD LastError; // edi
  int v34; // eax
  ULONG v35; // eax
  DWORD v36; // eax
  UINT v37; // eax
  int Error; // eax
  const unsigned int **v39; // rcx
  int v40; // r12d
  DWORD TickCount; // r13d
  __int64 i; // rdi
  __int64 v43; // rcx
  __int64 v44; // r13
  DWORD v45; // eax
  WCHAR *v46; // rax
  WCHAR *v47; // rbx
  unsigned __int64 v48; // rdx
  int IsNameInSomeNodeList; // ebx
  unsigned __int64 v50; // rdx
  TStringNode *v51; // rax
  TStringNode *v52; // rax
  TStringNode *v53; // r10
  LPBYTE v54; // rcx
  int v55; // eax
  DWORD TokenInformation; // [rsp+40h] [rbp-C0h] BYREF
  PADDRINFOW ppResult; // [rsp+48h] [rbp-B8h] BYREF
  LPBYTE bufptr; // [rsp+50h] [rbp-B0h] BYREF
  TNameResolutionCache *v59; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *ThreadInformation; // [rsp+60h] [rbp-A0h] BYREF
  LPBYTE v61; // [rsp+68h] [rbp-98h] BYREF
  ADDRINFOW pHints; // [rsp+70h] [rbp-90h] BYREF
  int v63; // [rsp+A0h] [rbp-60h]
  const unsigned int *v64; // [rsp+A8h] [rbp-58h] BYREF
  int v65; // [rsp+B0h] [rbp-50h]
  const unsigned int **v66; // [rsp+B8h] [rbp-48h]
  const unsigned int **v67; // [rsp+C0h] [rbp-40h]
  int v68; // [rsp+C8h] [rbp-38h] BYREF
  const unsigned int *v69; // [rsp+D0h] [rbp-30h] BYREF
  int v70; // [rsp+D8h] [rbp-28h]
  const unsigned int **v71; // [rsp+E0h] [rbp-20h]
  const unsigned int **v72; // [rsp+E8h] [rbp-18h]
  int v73; // [rsp+F0h] [rbp-10h]
  WSAData WSAData; // [rsp+F8h] [rbp-8h] BYREF
  signed int v75; // [rsp+290h] [rbp+190h]

  if ( !a2 )
    return (unsigned int)-2147024809;
  v3 = g_pNameCache;
  v59 = g_pNameCache;
  v4 = (char *)g_pNameCache + 56;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pNameCache + 56));
  ++*((_DWORD *)v4 + 11);
  v5 = (_QWORD *)((char *)v3 + 120);
  v6 = 0;
  *((_DWORD *)v4 + 10) = GetCurrentThreadId();
  if ( v3 != (TNameResolutionCache *)-120LL )
    v6 = (_QWORD *)*((_QWORD *)v3 + 17);
  v7 = 0;
  LastErrorAsHResult = 1;
  if ( v3 != (TNameResolutionCache *)-120LL )
  {
    while ( v6 != v5 )
    {
      if ( !(unsigned int)_o__wcsicmp(v6[5], a2) )
      {
        LastErrorAsHResult = 0;
        break;
      }
      v9 = v6[8] + 8LL;
      if ( v6[8] != -8 )
      {
        v44 = *(_QWORD *)(v6[8] + 24LL);
        while ( v44 != v9 )
        {
          if ( !(unsigned int)_o__wcsicmp(a2, *(_QWORD *)(v44 + 40)) )
          {
            v7 = v44;
            v45 = GetTickCount() - *(_DWORD *)(v44 + 48);
            v3 = v59;
            if ( v45 <= *((_DWORD *)v59 + 1) )
            {
              v7 = 0;
              LastErrorAsHResult = 0;
            }
            else
            {
              LastErrorAsHResult = 1;
              *(_QWORD *)(*(_QWORD *)(v7 + 16) + 24LL) = *(_QWORD *)(v7 + 24);
              *(_QWORD *)(*(_QWORD *)(v7 + 24) + 16LL) = *(_QWORD *)(v7 + 16);
              *(_QWORD *)(v7 + 16) = v7;
              *(_QWORD *)(v7 + 24) = v7;
            }
            goto LABEL_14;
          }
          if ( v44 )
            v44 = *(_QWORD *)(v44 + 16);
        }
      }
      LastErrorAsHResult = 1;
      if ( v6 )
        v6 = (_QWORD *)v6[2];
    }
    v3 = v59;
  }
LABEL_14:
  v21 = (*((_DWORD *)v4 + 11))-- == 1;
  if ( v21 )
    *((_DWORD *)v4 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  if ( v7 )
    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
  if ( LastErrorAsHResult == 1 )
  {
    v11 = (unsigned __int16 *)RevertToPrinterSelf();
    if ( *a2 )
    {
      v73 = 1414746967;
      v12 = 0;
      v13 = WSAStartup(0x202u, &WSAData);
      v15 = v13;
      if ( v13 > 0 )
        v15 = (unsigned __int16)v13 | 0x80070000;
      v75 = v15;
      if ( v15 >= 0 )
      {
        ppResult = 0;
        *(_QWORD *)&pHints.ai_flags = 4;
        memset(&pHints.ai_socktype, 0, 40);
        AddrInfoW = GetAddrInfoW(a2, 0, &pHints, &ppResult);
        if ( AddrInfoW )
        {
          if ( AddrInfoW == 11001 )
          {
            v15 = 1;
          }
          else
          {
            Error = WSAGetLastError();
            v15 = Error;
            if ( Error > 0 )
              v15 = (unsigned __int16)Error | 0x80070000;
          }
        }
        else
        {
          if ( (int)IsIPv6StyleName(a2) >= 0 )
          {
            v46 = (WCHAR *)operator new[](0x804u);
            v47 = v46;
            if ( v46 )
            {
              if ( GetNameInfoW(ppResult->ai_addr, ppResult->ai_addrlen, v46, 0x401u, 0, 0, 2) )
                operator delete(v47, v48);
              else
                v12 = v47;
            }
          }
          FreeAddrInfoW(ppResult);
          v15 = 0;
        }
      }
      if ( !v75 )
        WSACleanup();
      if ( !v15 )
      {
        if ( v12 )
        {
          bufptr = 0;
          IsNameInSomeNodeList = TNameResolutionCache::IsNameInSomeNodeList(
                                   v14,
                                   v12,
                                   (struct TResolutionCacheNode **)&bufptr);
          operator delete(v12, v50);
          if ( !IsNameInSomeNodeList )
          {
            v51 = (TStringNode *)operator new(0x38u);
            if ( v51 )
            {
              v52 = TStringNode::TStringNode(v51, a2);
              v53 = v52;
              if ( v52 )
              {
                if ( *((int *)v52 + 13) < 0
                  || (int)NCoreLibrary::TList<TResolutionCacheNode>::AddAtHead(*((_QWORD *)bufptr + 8), v52) < 0 )
                {
                  (**(void (__fastcall ***)(TStringNode *, __int64))v53)(v53, 1);
                }
              }
            }
          }
        }
        LastErrorAsHResult = -2147467259;
LABEL_66:
        ThreadInformation = v11;
        if ( v11 )
        {
          TokenInformation = 0;
          LODWORD(ppResult) = 0;
          LastError = GetLastError();
          if ( GetTokenInformation(v11, TokenType, &TokenInformation, 4u, (PDWORD)&ppResult) && TokenInformation != 2 )
          {
            SetLastError(LastError);
            goto LABEL_122;
          }
          SetLastError(LastError);
          v34 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
          if ( v34 >= 0 )
          {
LABEL_122:
            NtClose(ThreadInformation);
            return (unsigned int)LastErrorAsHResult;
          }
          v35 = RtlNtStatusToDosError(v34);
          SetLastError(v35);
          v36 = GetLastError();
          PrvSpoolssTelemetry::WriteDbgTraceError("ImpersonatePrinterClient", L"Failed.  Error %d.", v36);
        }
        else
        {
          SetLastError(6u);
        }
        v37 = GetLastError();
        ExitProcess(v37);
      }
    }
    v17 = *((_QWORD *)v3 + 19);
    v71 = &v69;
    v68 = 1953721460;
    v72 = &v69;
    v66 = &v64;
    v67 = &v64;
    v69 = &NCoreLibrary::TLink::`vftable';
    v70 = 1802398836;
    v63 = 1953721460;
    v64 = &NCoreLibrary::TLink::`vftable';
    v65 = 1802398836;
    if ( *(_BYTE *)(v17 + 88) )
    {
      v40 = 1;
      NCoreLibrary::TCriticalSection::Enter((NCoreLibrary::TCriticalSection *)(v17 + 32));
      TickCount = GetTickCount();
      for ( i = 0; (unsigned int)i < *(_DWORD *)(v17 + 8); i = (unsigned int)(i + 1) )
      {
        v43 = *(_QWORD *)(v17 + 24);
        if ( *(_QWORD *)(v43 + 24 * i)
          && TickCount - *(_DWORD *)(v43 + 24 * i + 8) < *(_DWORD *)(v17 + 12)
          && !(unsigned int)_o__wcsicmp(a2, *(_QWORD *)(v43 + 24 * i)) )
        {
          v40 = 0;
          break;
        }
      }
      NCoreLibrary::TCriticalSection::Leave((NCoreLibrary::TCriticalSection *)(v17 + 32));
      if ( v40 != 1 )
      {
LABEL_38:
        v21 = *a2 == 0;
        v19 = &NCoreLibrary::TString::gszNullState;
        ThreadInformation = &NCoreLibrary::TString::gszNullState;
        LastErrorAsHResult = -2147024809;
        if ( v21 )
        {
LABEL_55:
          if ( v19 != &NCoreLibrary::TString::gszNullState && v19 != (unsigned __int16 *)&word_1400CB516 )
            operator delete(v19, v18);
          goto LABEL_58;
        }
        bufptr = 0;
        TokenInformation = 0;
        LODWORD(ppResult) = 0;
        v20 = NetServerTransportEnum(0, 0, &bufptr, 0xFFFFFFFF, &TokenInformation, (LPDWORD)&ppResult, 0);
        LastErrorAsHResult = v20;
        if ( v20 )
        {
          if ( v20 > 0 )
            LastErrorAsHResult = (unsigned __int16)v20 | 0x80070000;
          v21 = LastErrorAsHResult == 0;
          if ( LastErrorAsHResult < 0 )
          {
LABEL_53:
            if ( v21 )
              LastErrorAsHResult = TNameResolutionCache::AddNetBiosName(v59, v19, a2);
            goto LABEL_55;
          }
        }
        v22 = -1;
        v23 = WideCharToMultiByte(3u, 0, a2, -1, 0, 0, 0, 0);
        v24 = v23;
        if ( v23 )
        {
          v25 = (CHAR *)operator new[](v23);
          v26 = v25;
          if ( !v25 )
          {
            LastErrorAsHResult = -2147024882;
            goto LABEL_52;
          }
          if ( WideCharToMultiByte(3u, 0, a2, -1, v25, v24, 0, 0) )
            goto LABEL_48;
          LastErrorAsHResult = GetLastErrorAsHResult();
          operator delete(v26, v28);
        }
        else
        {
          v26 = 0;
          LastErrorAsHResult = GetLastErrorAsHResult();
        }
        if ( LastErrorAsHResult >= 0 )
        {
          do
LABEL_48:
            ++v22;
          while ( v26[v22] );
          LastErrorAsHResult = 1;
          for ( j = 0; (unsigned int)j < TokenInformation; j = (unsigned int)(j + 1) )
          {
            if ( *(_DWORD *)&bufptr[40 * j + 24] == (_DWORD)v22
              && !_strnicmp(v26, *(const char **)&bufptr[40 * j + 16], (unsigned int)v22) )
            {
              v61 = 0;
              if ( !NetServerGetInfo(a2, 0x65u, &v61) )
              {
                v54 = v61;
                if ( (*((_DWORD *)v61 + 6) & 0x5000000) == 0 )
                {
                  v55 = NCoreLibrary::TString::Update((NCoreLibrary::TString *)&ThreadInformation, &Buffer);
                  v54 = v61;
                  LastErrorAsHResult = v55;
                  v19 = ThreadInformation;
                }
                NetApiBufferFree(v54);
              }
              break;
            }
          }
          operator delete(v26, v27);
        }
LABEL_52:
        NetApiBufferFree(bufptr);
        v21 = LastErrorAsHResult == 0;
        goto LABEL_53;
      }
      v3 = v59;
    }
    LastErrorAsHResult = TNameResolutionCache::CacheGetAddrInfo(v3, a2);
    if ( (_WORD)LastErrorAsHResult == 11001 )
      TFastCache<NullCacheEntry>::AddString(*((_QWORD *)v3 + 19), a2);
    if ( LastErrorAsHResult )
    {
      if ( (_WORD)LastErrorAsHResult == 11001 )
        goto LABEL_38;
    }
    else
    {
      LastErrorAsHResult = TNameResolutionCache::AddNameUsingIPList(v3, a2, &v68);
    }
LABEL_58:
    v30 = v66;
    if ( v66 != &v64 )
    {
      do
      {
        v31 = v30;
        v30 = (const unsigned int **)v30[2];
        if ( v31 )
          (*(void (__fastcall **)(const unsigned int **, __int64))*v31)(v31, 1);
      }
      while ( v30 != &v64 );
      v30 = v66;
    }
    v64 = &NCoreLibrary::TLink::`vftable';
    if ( v30 != &v64 && v67 != &v64 )
    {
      v30[3] = (const unsigned int *)v67;
      v67[2] = (const unsigned int *)v66;
      v66 = &v64;
      v67 = &v64;
    }
    v32 = v71;
    if ( v71 != &v69 )
    {
      do
      {
        v39 = v32;
        v32 = (const unsigned int **)v32[2];
        if ( v39 )
          (*(void (__fastcall **)(const unsigned int **, __int64))*v39)(v39, 1);
      }
      while ( v32 != &v69 );
      v32 = v71;
    }
    if ( v32 != &v69 && v72 != &v69 )
    {
      v32[3] = (const unsigned int *)v72;
      v72[2] = (const unsigned int *)v71;
    }
    goto LABEL_66;
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x1400088b0  push    rbp
0x1400088b2  push    rbx
0x1400088b3  push    rsi
0x1400088b4  push    rdi
0x1400088b5  push    r12
0x1400088b7  push    r13
0x1400088b9  push    r14
0x1400088bb  push    r15
0x1400088bd  lea     rbp, [rsp-1B8h]
0x1400088c5  sub     rsp, 2B8h
0x1400088cc  mov     rax, cs:__security_cookie
0x1400088d3  xor     rax, rsp
0x1400088d6  mov     [rbp+1F0h+var_50], rax
0x1400088dd  mov     r15, rdx
0x1400088e0  test    rdx, rdx
0x1400088e3  jz      loc_1400089C3
0x1400088e9  mov     r13, cs:?g_pNameCache@@3PEAVTNameResolutionCache@@EA; TNameResolutionCache * g_pNameCache
0x1400088f0  mov     [rsp+2F0h+var_298], r13
0x1400088f5  lea     r14, [r13+38h]
0x1400088f9  mov     rcx, r14; lpCriticalSection
0x1400088fc  call    cs:__imp_EnterCriticalSection
0x140008902  inc     dword ptr [r14+2Ch]
0x140008906  call    cs:__imp_GetCurrentThreadId
0x14000890c  lea     rsi, [r13+78h]
0x140008910  xor     edi, edi
0x140008912  mov     [r14+28h], eax
0x140008916  test    rsi, rsi
0x140008919  jz      short loc_14000891F
0x14000891b  mov     rdi, [rsi+10h]
0x14000891f  xor     r12d, r12d
0x140008922  mov     ebx, 1
0x140008927  test    rsi, rsi
0x14000892a  jz      short loc_140008978
0x14000892c  cmp     rdi, rsi
0x14000892f  jz      short loc_140008973
0x140008931  mov     rcx, [rdi+28h]
0x140008935  mov     rdx, r15
0x140008938  call    cs:__imp__o__wcsicmp
0x14000893e  test    eax, eax
0x140008940  jz      short loc_140008971
0x140008942  mov     rbx, [rdi+40h]
0x140008946  xor     r13d, r13d
0x140008949  add     rbx, 8
0x14000894d  jnz     loc_140008EA4
0x140008953  test    rbx, rbx
0x140008956  jz      short loc_140008961
0x140008958  cmp     r13, rbx
0x14000895b  jnz     loc_140008EAD
0x140008961  mov     ebx, 1
0x140008966  test    rdi, rdi
0x140008969  jz      short loc_14000892C
0x14000896b  mov     rdi, [rdi+10h]
0x14000896f  jmp     short loc_14000892C
0x140008971  xor     ebx, ebx
0x140008973  mov     r13, [rsp+2F0h+var_298]
0x140008978  add     dword ptr [r14+2Ch], 0FFFFFFFFh
0x14000897d  mov     eax, [r14+2Ch]
0x140008981  jz      loc_140008F10
0x140008987  mov     rcx, r14; lpCriticalSection
0x14000898a  call    cs:__imp_LeaveCriticalSection
0x140008990  test    r12, r12
0x140008993  jnz     loc_140008E6F
0x140008999  cmp     ebx, 1
0x14000899c  jz      short loc_1400089CA
0x14000899e  mov     eax, ebx
0x1400089a0  mov     rcx, [rbp+1F0h+var_50]
0x1400089a7  xor     rcx, rsp; StackCookie
0x1400089aa  call    __security_check_cookie
0x1400089af  add     rsp, 2B8h
0x1400089b6  pop     r15
0x1400089b8  pop     r14
0x1400089ba  pop     r13
0x1400089bc  pop     r12
0x1400089be  pop     rdi
0x1400089bf  pop     rsi
0x1400089c0  pop     rbx
0x1400089c1  pop     rbp
0x1400089c2  retn
0x1400089c3  mov     ebx, 80070057h
0x1400089c8  jmp     short loc_14000899E
0x1400089ca  call    RevertToPrinterSelf
0x1400089cf  cmp     word ptr [r15], 0
0x1400089d4  mov     r14, rax
0x1400089d7  jz      loc_140008A6F
0x1400089dd  xor     esi, esi
0x1400089df  mov     [rbp+1F0h+var_200], 54535357h
0x1400089e6  mov     ecx, 202h; wVersionRequested
0x1400089eb  lea     rdx, [rbp+1F0h+WSAData]; lpWSAData
0x1400089ef  mov     edi, esi
0x1400089f1  call    cs:__imp_WSAStartup
0x1400089f7  mov     ebx, eax
0x1400089f9  test    eax, eax
0x1400089fb  jg      loc_140008DD4
0x140008a01  mov     [rbp+1F0h+var_60], ebx
0x140008a07  test    ebx, ebx
0x140008a09  js      short loc_140008A5B
0x140008a0b  xorps   xmm0, xmm0
0x140008a0e  mov     [rsp+2F0h+ppResult], rsi
0x140008a13  xorps   xmm1, xmm1
0x140008a16  mov     [rbp+1F0h+pHints.ai_next], rsi
0x140008a1a  lea     r9, [rsp+2F0h+ppResult]; ppResult
0x140008a1f  mov     qword ptr [rsp+2F0h+pHints.ai_flags], 4
0x140008a28  lea     r8, [rsp+2F0h+pHints]; pHints
0x140008a2d  xor     edx, edx; pServiceName
0x140008a2f  mov     rcx, r15; pNodeName
0x140008a32  movdqu  xmmword ptr [rsp+2F0h+pHints.ai_socktype], xmm0
0x140008a38  movdqu  xmmword ptr [rbp+1F0h+pHints.ai_canonname], xmm1
0x140008a3d  call    cs:__imp_GetAddrInfoW
0x140008a43  test    eax, eax
0x140008a45  jz      loc_140008F1D
0x140008a4b  cmp     eax, 2AF9h
0x140008a50  jnz     loc_140008DB6
0x140008a56  mov     ebx, 1
0x140008a5b  cmp     [rbp+1F0h+var_60], esi
0x140008a61  jz      loc_140008F8A
0x140008a67  test    ebx, ebx
0x140008a69  jz      loc_140008F95
0x140008a6f  mov     rsi, [r13+98h]
0x140008a76  lea     rax, [rbp+1F0h+var_220]
0x140008a7a  mov     [rbp+1F0h+var_210], rax
0x140008a7e  lea     rcx, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x140008a85  lea     rax, [rbp+1F0h+var_220]
0x140008a89  mov     [rbp+1F0h+var_228], 74736C74h
0x140008a90  mov     [rbp+1F0h+var_208], rax
0x140008a94  lea     rax, [rbp+1F0h+var_248]
0x140008a98  mov     [rbp+1F0h+var_238], rax
0x140008a9c  lea     rax, [rbp+1F0h+var_248]
0x140008aa0  mov     [rbp+1F0h+var_230], rax
0x140008aa4  mov     [rbp+1F0h+var_220], rcx
0x140008aa8  mov     [rbp+1F0h+var_218], 6B6E6C74h
0x140008aaf  mov     [rbp+1F0h+var_250], 74736C74h
0x140008ab6  mov     [rbp+1F0h+var_248], rcx
0x140008aba  mov     [rbp+1F0h+var_240], 6B6E6C74h
0x140008ac1  cmp     byte ptr [rsi+58h], 0
0x140008ac5  jnz     loc_140008E10
0x140008acb  lea     r9, [rbp+1F0h+var_250]
0x140008acf  mov     rdx, r15; unsigned __int16 *
0x140008ad2  lea     r8, [rbp+1F0h+var_228]
0x140008ad6  mov     rcx, r13; this
0x140008ad9  call    ?CacheGetAddrInfo@TNameResolutionCache@@AEAAJPEBGPEAV?$TList@VTStringNode@@@NCoreLibrary@@1@Z; TNameResolutionCache::CacheGetAddrInfo(ushort const *,NCoreLibrary::TList<TStringNode> *,NCoreLibrary::TList<TStringNode> *)
0x140008ade  mov     ebx, eax
0x140008ae0  cmp     ax, 2AF9h
0x140008ae4  jz      loc_140009013
0x140008aea  test    ebx, ebx
0x140008aec  jz      loc_140009027
0x140008af2  cmp     bx, 2AF9h
0x140008af7  jnz     loc_140008C97
0x140008afd  jmp     short loc_140008B15
0x140008aff  xor     r12d, r12d
0x140008b02  lea     rcx, [rsi+20h]; this
0x140008b06  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x140008b0b  cmp     r12d, 1
0x140008b0f  jz      loc_140008E88
0x140008b15  cmp     word ptr [r15], 0
0x140008b1a  lea     rdi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x140008b21  mov     r12, rdi
0x140008b24  mov     [rsp+2F0h+ThreadInformation], rdi
0x140008b29  mov     ebx, 80070057h
0x140008b2e  jz      loc_140008C7E
0x140008b34  lea     rax, [rsp+2F0h+ppResult]
0x140008b39  mov     [rsp+2F0h+resume_handle], 0; resume_handle
0x140008b42  mov     [rsp+2F0h+totalentries], rax; totalentries
0x140008b47  lea     r8, [rsp+2F0h+bufptr]; bufptr
0x140008b4c  lea     rax, [rsp+2F0h+TokenInformation]
0x140008b51  mov     [rsp+2F0h+bufptr], 0
0x140008b5a  mov     r9d, 0FFFFFFFFh; prefmaxlen
0x140008b60  mov     [rsp+2F0h+entriesread], rax; entriesread
0x140008b65  xor     edx, edx; level
0x140008b67  mov     [rsp+2F0h+TokenInformation], 0
0x140008b6f  xor     ecx, ecx; servername
0x140008b71  mov     dword ptr [rsp+2F0h+ppResult], 0
0x140008b79  call    cs:__imp_NetServerTransportEnum
0x140008b7f  mov     ebx, eax
0x140008b81  test    eax, eax
0x140008b83  jz      short loc_140008B98
0x140008b85  jle     short loc_140008B90
0x140008b87  movzx   ebx, ax
0x140008b8a  or      ebx, 80070000h
0x140008b90  test    ebx, ebx
0x140008b92  js      loc_140008C78
0x140008b98  mov     [rsp+2F0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140008ba1  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x140008ba8  mov     [rsp+2F0h+resume_handle], 0; lpDefaultChar
0x140008bb1  mov     r9d, edi; cchWideChar
0x140008bb4  mov     dword ptr [rsp+2F0h+totalentries], 0; cbMultiByte
0x140008bbc  mov     r8, r15; lpWideCharStr
0x140008bbf  xor     edx, edx; dwFlags
0x140008bc1  mov     [rsp+2F0h+entriesread], 0; lpMultiByteStr
0x140008bca  mov     ecx, 3; CodePage
0x140008bcf  call    cs:__imp_WideCharToMultiByte
0x140008bd5  movsxd  rbx, eax
0x140008bd8  test    eax, eax
0x140008bda  jz      loc_140009047
0x140008be0  mov     rcx, rbx; unsigned __int64
0x140008be3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140008be8  mov     rsi, rax
0x140008beb  test    rax, rax
0x140008bee  jz      loc_14000903D
0x140008bf4  mov     [rsp+2F0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140008bfd  mov     r9d, edi; cchWideChar
0x140008c00  mov     [rsp+2F0h+resume_handle], 0; lpDefaultChar
0x140008c09  mov     r8, r15; lpWideCharStr
0x140008c0c  mov     dword ptr [rsp+2F0h+totalentries], ebx; cbMultiByte
0x140008c10  xor     edx, edx; dwFlags
0x140008c12  mov     ecx, 3; CodePage
0x140008c17  mov     [rsp+2F0h+entriesread], rax; lpMultiByteStr
0x140008c1c  call    cs:__imp_WideCharToMultiByte
0x140008c22  test    eax, eax
0x140008c24  jnz     short loc_140008C40
0x140008c26  call    GetLastErrorAsHResult
0x140008c2b  mov     rcx, rsi; void *
0x140008c2e  mov     ebx, eax
0x140008c30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008c35  test    ebx, ebx
0x140008c37  js      short loc_140008C64
0x140008c39  nop     dword ptr [rax+00000000h]
0x140008c40  inc     rdi
0x140008c43  cmp     byte ptr [rsi+rdi], 0
0x140008c47  jnz     short loc_140008C40
0x140008c49  mov     ebx, 1
0x140008c4e  xor     r13d, r13d
0x140008c51  cmp     r13d, [rsp+2F0h+TokenInformation]
0x140008c56  jb      loc_140009055
0x140008c5c  mov     rcx, rsi; void *
0x140008c5f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008c64  mov     rcx, [rsp+2F0h+bufptr]; Buffer
0x140008c69  call    cs:__imp_NetApiBufferFree
0x140008c6f  test    ebx, ebx
0x140008c71  lea     rdi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x140008c78  jz      loc_1400090E2
0x140008c7e  cmp     r12, rdi
0x140008c81  jz      short loc_140008C97
0x140008c83  lea     rax, word_1400CB516
0x140008c8a  cmp     r12, rax
0x140008c8d  jz      short loc_140008C97
0x140008c8f  mov     rcx, r12; void *
0x140008c92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008c97  mov     rdi, [rbp+1F0h+var_238]
0x140008c9b  lea     rax, [rbp+1F0h+var_248]
0x140008c9f  cmp     rdi, rax
0x140008ca2  jz      short loc_140008CCD
0x140008ca4  mov     rcx, rdi
0x140008ca7  mov     rdi, [rdi+10h]
0x140008cab  test    rcx, rcx
0x140008cae  jz      short loc_140008CC0
0x140008cb0  mov     rax, [rcx]
0x140008cb3  mov     edx, 1
0x140008cb8  mov     rax, [rax]
0x140008cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008cc0  lea     rax, [rbp+1F0h+var_248]
0x140008cc4  cmp     rdi, rax
0x140008cc7  jnz     short loc_140008CA4
0x140008cc9  mov     rdi, [rbp+1F0h+var_238]
0x140008ccd  lea     rax, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x140008cd4  mov     [rbp+1F0h+var_248], rax
0x140008cd8  lea     rax, [rbp+1F0h+var_248]
0x140008cdc  cmp     rdi, rax
0x140008cdf  jnz     loc_1400090F9
0x140008ce5  mov     rdi, [rbp+1F0h+var_210]
0x140008ce9  lea     rax, [rbp+1F0h+var_220]
0x140008ced  cmp     rdi, rax
0x140008cf0  jnz     loc_140008DE2
0x140008cf6  lea     rax, [rbp+1F0h+var_220]
0x140008cfa  xor     esi, esi
0x140008cfc  cmp     rdi, rax
0x140008cff  jnz     loc_14000912F
0x140008d05  mov     [rsp+2F0h+ThreadInformation], r14
0x140008d0a  test    r14, r14
0x140008d0d  jz      loc_140009155
0x140008d13  mov     [rsp+2F0h+TokenInformation], esi
0x140008d17  mov     dword ptr [rsp+2F0h+ppResult], esi
0x140008d1b  call    cs:__imp_GetLastError
0x140008d21  mov     r9d, 4; TokenInformationLength
0x140008d27  lea     r8, [rsp+2F0h+TokenInformation]; TokenInformation
0x140008d2c  mov     edi, eax
0x140008d2e  mov     edx, 8; TokenInformationClass
0x140008d33  lea     rax, [rsp+2F0h+ppResult]
0x140008d38  mov     rcx, r14; TokenHandle
0x140008d3b  mov     [rsp+2F0h+entriesread], rax; ReturnLength
0x140008d40  call    cs:__imp_GetTokenInformation
0x140008d46  test    eax, eax
0x140008d48  jnz     loc_140009165
0x140008d4e  mov     ecx, edi; dwErrCode
0x140008d50  call    cs:__imp_SetLastError
0x140008d56  mov     r9d, 8; ThreadInformationLength
0x140008d5c  lea     r8, [rsp+2F0h+ThreadInformation]; ThreadInformation
0x140008d61  mov     edx, 5; ThreadInformationClass
0x140008d66  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140008d6d  call    cs:__imp_NtSetInformationThread
0x140008d73  test    eax, eax
0x140008d75  jns     loc_140009178
0x140008d7b  mov     ecx, eax; Status
0x140008d7d  call    cs:__imp_RtlNtStatusToDosError
0x140008d83  mov     ecx, eax; dwErrCode
0x140008d85  call    cs:__imp_SetLastError
0x140008d8b  call    cs:__imp_GetLastError
0x140008d91  mov     r8d, eax
0x140008d94  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140008d9b  lea     rcx, aImpersonatepri; "ImpersonatePrinterClient"
0x140008da2  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
  ... truncated ...
```
