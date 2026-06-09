# ResolveManualPeer(AutoPtr<NtpPeer>)

- ea: `0x180019980`
- end: `0x18001a70e`
- name: `?ResolveManualPeer@@YAJV?$AutoPtr@UNtpPeer@@@@@Z`
- size: `3470`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180017e88`

## callees

- `0x18000a7e0`
- `0x18000bde0`
- `0x180014054`
- `0x1800144ac`
- `0x180014774`
- `0x1800164b0`
- `0x180018138`
- `0x180018180`
- `0x180019828`
- `0x180019980`
- `0x18001a714`
- `0x18001a780`
- `0x18001d9a0`
- `0x18002dbc4`
- `0x18002e768`
- `0x18003d270`
- `0x18003f491`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019a70`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019a70`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800199f9`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180019d4a`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800199f9`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180019d4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019b62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019d26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a132`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a26f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a6fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019b62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019d26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a132`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a26f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a6fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019e11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019f2d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a15c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019e11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019f2d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a15c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019ba5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019ba5`
- `ntdll!RtlInitUnicodeString` at `0x180019ca1`
- `ntdll!RtlInitUnicodeString` at `0x180019cdd`
- `ntdll!RtlInitUnicodeString` at `0x18001a484`
- `ntdll!RtlInitUnicodeString` at `0x18001a5eb`
- `ntdll!RtlInitUnicodeString` at `0x180019ca1`
- `ntdll!RtlInitUnicodeString` at `0x180019cdd`
- `ntdll!RtlInitUnicodeString` at `0x18001a484`
- `ntdll!RtlInitUnicodeString` at `0x18001a5eb`
- `WS2_32!GetAddrInfoW` at `0x180019b0d`
- `WS2_32!GetAddrInfoW` at `0x180019b0d`
- `WS2_32!FreeAddrInfoW` at `0x18001a143`
- `WS2_32!FreeAddrInfoW` at `0x18001a143`
- `WS2_32!__imp_WSAGetLastError` at `0x180019b21`
- `WS2_32!__imp_WSAGetLastError` at `0x180019b21`

## string_xrefs

- `0x18001a305`: `Attempted to resolve a manual peer with a NULL wszManualConfigID.  This could indicate that the time service is in an inconsistent state.  The peer will be discarded, and the time service will attempt to proceed.\n`
- `0x18001a68f`: `Logging warning: NtpClient was unable to set a manual peer to use as a time source because of DNS resolution error on '%s'. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n`
- `0x18001a61d`: `Logging warning: NtpClient was unable to set a manual peer to use as a time source because of duplicate error on '%s'. The same time source '%s' has been either specified as manual peer in NtpServer or selected as domain peer. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n`
- `0x18001a591`: `Logging warning: NtpClient was unable to set a manual peer to use as a time source because of an unexpected error. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall ResolveManualPeer(volatile signed __int32 **a1)
{
  unsigned __int64 *v2; // r13
  const wchar_t *v3; // r12
  wchar_t *v4; // rax
  wchar_t *v5; // r15
  int Error; // eax
  signed int NewActivePeers; // edi
  HLOCAL v8; // rax
  int v9; // eax
  unsigned __int64 v10; // r15
  int v11; // r15d
  __int64 v12; // rcx
  int SystemErrorString; // r15d
  WCHAR *v14; // r13
  int v15; // ebx
  PADDRINFOW v17; // rax
  unsigned int v18; // edi
  unsigned int v19; // edx
  _DWORD *v20; // r9
  unsigned __int64 v21; // rdi
  unsigned int v22; // r8d
  __int64 v23; // r10
  __int64 v24; // r10
  __int64 v25; // rax
  WCHAR *v26; // rcx
  unsigned int j; // ebx
  unsigned __int64 v28; // r10
  unsigned __int64 v29; // r9
  struct addrinfoW *v30; // rcx
  unsigned int v31; // edx
  PADDRINFOW v32; // rcx
  _NtpProvState *v33; // rcx
  unsigned int v34; // edx
  __int64 v35; // r8
  unsigned __int64 v36; // rbx
  unsigned int k; // eax
  volatile signed __int32 *v38; // rax
  unsigned __int64 v39; // rbx
  unsigned int v40; // eax
  PADDRINFOW v41; // rdx
  HLOCAL v42; // rcx
  __int64 v43; // rdi
  __int64 v44; // rdx
  int v45; // eax
  PADDRINFOW ppResult; // [rsp+78h] [rbp-1D0h] BYREF
  unsigned __int64 v47; // [rsp+80h] [rbp-1C8h] BYREF
  int v48; // [rsp+88h] [rbp-1C0h]
  PCWSTR SourceString; // [rsp+90h] [rbp-1B8h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-1B0h]
  int v51; // [rsp+A0h] [rbp-1A8h]
  unsigned int v52; // [rsp+A4h] [rbp-1A4h]
  unsigned int v53; // [rsp+A8h] [rbp-1A0h]
  unsigned int v54; // [rsp+ACh] [rbp-19Ch]
  __int64 v55; // [rsp+B0h] [rbp-198h] BYREF
  int v56; // [rsp+B8h] [rbp-190h]
  HLOCAL v57; // [rsp+C0h] [rbp-188h]
  unsigned __int64 v58; // [rsp+C8h] [rbp-180h]
  HLOCAL v59; // [rsp+D0h] [rbp-178h]
  HLOCAL v60; // [rsp+D8h] [rbp-170h]
  PCWSTR v61; // [rsp+E0h] [rbp-168h]
  unsigned int i; // [rsp+E8h] [rbp-160h]
  volatile signed __int32 **v63; // [rsp+F0h] [rbp-158h]
  unsigned __int64 v64; // [rsp+F8h] [rbp-150h] BYREF
  unsigned __int64 v65; // [rsp+100h] [rbp-148h]
  __int64 *v66; // [rsp+108h] [rbp-140h]
  struct _UNICODE_STRING v67; // [rsp+110h] [rbp-138h] BYREF
  unsigned __int64 v68; // [rsp+120h] [rbp-128h] BYREF
  unsigned __int64 *v69; // [rsp+128h] [rbp-120h]
  unsigned __int64 v70; // [rsp+130h] [rbp-118h]
  unsigned __int64 v71; // [rsp+138h] [rbp-110h]
  __int64 v72; // [rsp+148h] [rbp-100h]
  struct _UNICODE_STRING DestinationString; // [rsp+150h] [rbp-F8h] BYREF
  struct _UNICODE_STRING v74; // [rsp+160h] [rbp-E8h] BYREF
  struct _UNICODE_STRING v75; // [rsp+170h] [rbp-D8h] BYREF
  __int64 v76; // [rsp+180h] [rbp-C8h]
  ADDRINFOW pHints; // [rsp+188h] [rbp-C0h] BYREF
  _BYTE v78[32]; // [rsp+1F0h] [rbp-58h] BYREF

  v63 = a1;
  v65 = 0;
  v53 = 0;
  LODWORD(SourceString) = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v72 = _set_se_translator(SeTransFunc);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v47 = (unsigned __int64)g_pnpstate;
  v2 = (unsigned __int64 *)((char *)g_pnpstate + 432);
  v3 = *(const wchar_t **)(*((_QWORD *)*a1 + 1) + 72LL);
  if ( v3 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(50) )
      FileLogAdd(L"Resolving manual peer: %s\n", v3);
    v4 = wcschr(v3, 0x2Cu);
    v5 = v4;
    if ( v4 )
      *v4 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
    v51 = 0;
    v52 = 0;
    v57 = 0;
    hMem = 0;
    ppResult = 0;
    memset(&pHints, 0, sizeof(pHints));
    pHints.ai_family = 0;
    pHints.ai_socktype = 2;
    if ( GetAddrInfoW(v3, L"123", &pHints, &ppResult) )
    {
      Error = WSAGetLastError();
      NewActivePeers = Error;
      if ( Error > 0 )
        NewActivePeers = (unsigned __int16)Error | 0x80070000;
      goto LABEL_9;
    }
    v17 = ppResult;
    v18 = 0;
    v52 = 0;
    while ( v17 )
    {
      v52 = ++v18;
      v17 = v17->ai_next;
    }
    v69 = 0;
    if ( is_mul_ok(0x80u, v18) )
    {
      v57 = LocalAlloc(0x40u, (unsigned __int64)v18 << 7);
      if ( !v57 )
      {
        NewActivePeers = -2147024882;
        goto LABEL_9;
      }
      v58 = 0;
      if ( is_mul_ok(4u, v18) )
      {
        v8 = LocalAlloc(0x40u, 4LL * v18);
        hMem = v8;
        if ( v8 )
        {
          v40 = 0;
          v51 = 0;
          v41 = ppResult;
          v42 = hMem;
          while ( 1 )
          {
            v55 = (__int64)v41;
            if ( v40 >= v18 )
              break;
            v43 = v40;
            memcpy_0((char *)v57 + 128 * (unsigned __int64)v40, v41->ai_addr, v41->ai_addrlen);
            v44 = v55;
            v42 = hMem;
            *((_DWORD *)hMem + v43) = *(_DWORD *)(v55 + 16);
            v40 = ++v51;
            v41 = *(PADDRINFOW *)(v44 + 40);
            v18 = v52;
          }
          v59 = v57;
          v57 = 0;
          v60 = v42;
          v8 = 0;
          hMem = 0;
          v53 = v18;
          NewActivePeers = 0;
        }
        else
        {
          NewActivePeers = -2147024882;
        }
LABEL_10:
        if ( v57 )
        {
          LocalFree(v57);
          v8 = hMem;
        }
        if ( v8 )
          LocalFree(v8);
        if ( ppResult )
          FreeAddrInfoW(ppResult);
        v9 = 0;
        if ( NewActivePeers < 0 )
          v9 = 3;
        LODWORD(ppResult) = v9;
        v56 = v9;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
        if ( v5 )
          *v5 = 44;
        v10 = v47;
        if ( NewActivePeers >= 0 )
        {
          v20 = v60;
          v21 = *(_QWORD *)(v47 + 408);
LABEL_49:
          v70 = v21;
          v58 = *(_QWORD *)(v10 + 416);
          if ( v21 == v58 )
          {
            NewActivePeers = 0;
          }
          else
          {
            v22 = 0;
            for ( i = 0; ; i = v22 )
            {
              if ( v22 >= v53 )
              {
                v58 = v21;
                v21 += 8LL;
                goto LABEL_49;
              }
              v23 = *(_QWORD *)(*(_QWORD *)v21 + 8LL);
              if ( *(_DWORD *)(v23 + 264) == v20[v22]
                && IsAddrEqual((struct sockaddr_storage *)(v23 + 136), (struct sockaddr_storage *)v59 + v22) )
              {
                break;
              }
              ++v22;
            }
            v25 = -1;
            do
              ++v25;
            while ( *(_WORD *)(*(_QWORD *)(v24 + 72) + 2 * v25) );
            v47 = v25 + 1;
            v26 = (WCHAR *)LocalAlloc(0x40u, 2 * (v25 + 1));
            v61 = v26;
            if ( !v26 )
            {
              NewActivePeers = -2147024882;
              goto LABEL_102;
            }
            NewActivePeers = StringCchCopyW(
                               v26,
                               v47,
                               *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)v21 + 8LL) + 72LL));
            if ( NewActivePeers >= 0 )
            {
              NewActivePeers = -2147023136;
              goto LABEL_102;
            }
          }
          if ( NewActivePeers >= 0 )
          {
            v55 = (__int64)(*(_QWORD *)(v10 + 416) - *(_QWORD *)(v10 + 408)) >> 3;
            v76 = v55;
            NewActivePeers = CreateNewActivePeers(
                               (struct sockaddr_storage *)v59,
                               (unsigned int *)v60,
                               v53,
                               (unsigned int *)&SourceString);
            if ( NewActivePeers >= 0 )
            {
              if ( *(_BYTE *)(*((_QWORD *)*a1 + 1) + 1544LL) )
              {
                v74 = 0;
                RtlInitUnicodeString(&v74, v3);
                if ( (unsigned __int8)FileLogAllowEntry(4) )
                  FileLogAdd(
                    L"Logging warning: NtpClient succeeds in resolving manual peer %s after a previous failure.\n",
                    v3);
                LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MANUAL_PEER_SUCCESS_ERROR, L"u", &v74);
              }
              for ( j = 0; ; ++j )
              {
                v54 = j;
                if ( j >= (unsigned int)SourceString )
                  break;
                v30 = *(struct addrinfoW **)(*(_QWORD *)(v10 + 408) + 8 * (v55 + j));
                ppResult = v30;
                v58 = (unsigned __int64)v30;
                if ( v30 )
                  _InterlockedIncrement(&v30->ai_flags);
                v69 = &v47;
                v47 = (unsigned __int64)v30;
                if ( v30 )
                  _InterlockedIncrement(&v30->ai_flags);
                NewActivePeers = MyFillInActivePeersDetail(&v47, 0, 0, L"Manual", v3, 0);
                v32 = ppResult;
                if ( ppResult && _InterlockedExchangeAdd(&ppResult->ai_flags, 0xFFFFFFFF) == 1 )
                  Ref<NtpPeer>::`scalar deleting destructor'(v32, v31);
              }
              v28 = v2[1];
              v58 = v28;
              v29 = *v2;
              v58 = *v2;
              while ( 1 )
              {
                v71 = v29;
                if ( v29 == v28 || (unsigned int)AutoPtr<NtpPeer>::operator==(v29, a1) )
                  break;
                v29 += 8LL;
              }
              v64 = v28;
              if ( v28 != v29 )
                std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v2, &v64);
              goto LABEL_30;
            }
            v11 = 5;
            LODWORD(ppResult) = 5;
            v56 = 5;
LABEL_22:
            *(_DWORD *)(*((_QWORD *)*a1 + 1) + 1528LL) = NewActivePeers;
            *(_DWORD *)(*((_QWORD *)*a1 + 1) + 1532LL) = 112;
            ++*(_DWORD *)(*((_QWORD *)*a1 + 1) + 52LL);
            v33 = g_pnpstate;
            v34 = *((_DWORD *)g_pnpstate + 45);
            v35 = *((_QWORD *)*a1 + 1);
            if ( *(_DWORD *)(v35 + 52) > v34 )
            {
              *(_DWORD *)(v35 + 52) = v34;
              v33 = g_pnpstate;
            }
            v36 = 600000000LL * *((unsigned int *)v33 + 44);
            v65 = v36;
            for ( k = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 52LL); ; --k )
            {
              v54 = k;
              if ( k <= 1 )
                break;
              v36 *= 2LL;
              v65 = v36;
            }
            v66 = &v55;
            v38 = *a1;
            v55 = (__int64)v38;
            if ( v38 )
              _InterlockedIncrement(v38);
            SetPeerTimeRemaining(&v55, v36);
            if ( (unsigned __int8)FileLogAllowEntry(5) )
              FileLogAdd(L"Retrying name resolution for %s in %u minutes.\n", v3, (unsigned int)(v36 / 0x23C34600));
            v12 = *((_QWORD *)*a1 + 1);
            if ( *(_BYTE *)(v12 + 1544) && *(_DWORD *)(v12 + 1548) == v11 )
              goto LABEL_30;
            v48 = 0;
            SourceString = 0;
            v67 = 0;
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, v3);
            SystemErrorString = GetSystemErrorString(NewActivePeers, (unsigned __int16 **)&SourceString);
            v48 = SystemErrorString;
            if ( SystemErrorString < 0 )
              goto LABEL_30;
            v14 = (WCHAR *)SourceString;
            RtlInitUnicodeString(&v67, SourceString);
            SourceString = (PCWSTR)(v36 / 0x23C34600);
            v15 = (int)ppResult;
            switch ( (_DWORD)ppResult )
            {
              case 3:
                if ( (unsigned __int8)FileLogAllowEntry(4) )
                  FileLogAdd(
                    L"Logging warning: NtpClient was unable to set a manual peer to use as a time source because of DNS re"
                     "solution error on '%s'. NtpClient will try again in %s minutes and double the reattempt interval th"
                     "ereafter. The error was: %s\n",
                    v3,
                    v78,
                    v14);
                v45 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MANUAL_PEER_DNS_ERROR, L"udu", &v67);
                break;
              case 4:
                v75 = 0;
                RtlInitUnicodeString(&v75, v61);
                if ( (unsigned __int8)FileLogAllowEntry(4) )
                  FileLogAdd(
                    L"Logging warning: NtpClient was unable to set a manual peer to use as a time source because of duplic"
                     "ate error on '%s'. The same time source '%s' has been either specified as manual peer in NtpServer "
                     "or selected as domain peer. NtpClient will try again in %s minutes and double the reattempt interva"
                     "l thereafter. The error was: %s\n",
                    v3,
                    v61,
                    v78,
                    v14);
                v45 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MANUAL_PEER_DUPLICATE_ERROR, L"uduu", &v67);
                break;
              case 5:
                if ( (unsigned __int8)FileLogAllowEntry(4) )
                  FileLogAdd(
                    L"Logging warning: NtpClient was unable to set a manual peer to use as a time source because of an une"
                     "xpected error. NtpClient will try again in %s minutes and double the reattempt interval thereafter."
                     " The error was: %s\n",
                    v78,
                    v14);
                v45 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MANUAL_PEER_UNEXPECTED_ERROR, L"ud", &v67);
                break;
              default:
                goto LABEL_28;
            }
            SystemErrorString = v45;
            v48 = v45;
LABEL_28:
            LocalFree(v14);
            if ( SystemErrorString >= 0 )
            {
              *(_BYTE *)(*((_QWORD *)*a1 + 1) + 1544LL) = 1;
              *(_DWORD *)(*((_QWORD *)*a1 + 1) + 1548LL) = v15;
            }
LABEL_30:
            _set_se_translator(v72);
            if ( NewActivePeers >= 0 )
              NewActivePeers = 0;
            if ( v59 )
              LocalFree(v59);
            if ( v60 )
              LocalFree(v60);
            if ( v61 )
              LocalFree((HLOCAL)v61);
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
            if ( *a1 && _InterlockedExchangeAdd(*a1, 0xFFFFFFFF) == 1 )
            {
              if ( *a1 )
                Ref<NtpPeer>::`scalar deleting destructor'(*a1, v19);
            }
            return (unsigned int)NewActivePeers;
          }
LABEL_102:
          LODWORD(ppResult) = 4;
          v56 = 4;
        }
        v11 = (int)ppResult;
        goto LABEL_22;
      }
    }
    NewActivePeers = -2147024362;
LABEL_9:
    v8 = hMem;
    goto LABEL_10;
  }
  if ( (unsigned __int8)FileLogAllowEntry(5) )
    FileLogAdd(
      L"Attempted to resolve a manual peer with a NULL wszManualConfigID.  This could indicate that the time service is in"
       " an inconsistent state.  The peer will be discarded, and the time service will attempt to proceed.\n");
  v47 = v2[1];
  v39 = v47;
  v47 = *v2;
  std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,AutoPtr<NtpPeer>>(
    &v47,
    v47,
    v39,
    a1);
  v68 = v39;
  if ( v39 != v47 )
    std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v2, &v68);
  AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(a1);
  return 0;
}

```

## disassembly

```asm
0x180019980  mov     [rsp+arg_8], rbx
0x180019985  mov     [rsp+arg_10], rsi
0x18001998a  push    rdi
0x18001998b  push    r12
0x18001998d  push    r13
0x18001998f  push    r14
0x180019991  push    r15
0x180019993  sub     rsp, 220h
0x18001999a  mov     rax, cs:__security_cookie
0x1800199a1  xor     rax, rsp
0x1800199a4  mov     [rsp+248h+var_38], rax
0x1800199ac  mov     r14, rcx
0x1800199af  mov     [rsp+248h+var_158], rcx
0x1800199b7  xor     esi, esi
0x1800199b9  mov     ebx, esi
0x1800199bb  mov     [rsp+248h+var_148], rbx
0x1800199c3  mov     [rsp+248h+var_1A0], esi
0x1800199ca  mov     dword ptr [rsp+248h+SourceString], esi
0x1800199d1  mov     [rsp+248h+var_1D7], 1
0x1800199d6  mov     [rsp+248h+var_1D8], bl
0x1800199da  mov     [rsp+248h+var_178], rsi
0x1800199e2  mov     [rsp+248h+var_170], rsi
0x1800199ea  mov     [rsp+248h+var_168], rsi
0x1800199f2  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800199f9  call    cs:__imp__set_se_translator
0x180019a00  nop     dword ptr [rax+rax+00h]
0x180019a05  mov     [rsp+248h+var_100], rax
0x180019a0d  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180019a14  add     rcx, 148h; lpCriticalSection
0x180019a1b  call    cs:__imp_EnterCriticalSection
0x180019a22  nop     dword ptr [rax+rax+00h]
0x180019a27  mov     [rsp+248h+var_1D8], 1
0x180019a2c  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180019a33  mov     [rsp+248h+var_1C8], rax
0x180019a3b  lea     r13, [rax+1B0h]
0x180019a42  mov     rax, [r14]
0x180019a45  mov     rcx, [rax+8]
0x180019a49  mov     r12, [rcx+48h]
0x180019a4d  test    r12, r12
0x180019a50  jz      loc_18001A2F7
0x180019a56  mov     ecx, 32h ; '2'
0x180019a5b  call    FileLogAllowEntry
0x180019a60  test    al, al
0x180019a62  jnz     loc_18001A313
0x180019a68  mov     edx, 2Ch ; ','; Ch
0x180019a6d  mov     rcx, r12; Str
0x180019a70  call    cs:__imp_wcschr
0x180019a77  nop     dword ptr [rax+rax+00h]
0x180019a7c  mov     r15, rax
0x180019a7f  test    rax, rax
0x180019a82  jz      short loc_180019A87
0x180019a84  mov     [rax], si
0x180019a87  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180019a8e  add     rcx, 148h; lpCriticalSection
0x180019a95  call    cs:__imp_LeaveCriticalSection
0x180019a9c  nop     dword ptr [rax+rax+00h]
0x180019aa1  mov     [rsp+248h+var_1D8], 0
0x180019aa6  mov     [rsp+248h+var_1A8], esi
0x180019aad  mov     [rsp+248h+var_1A4], esi
0x180019ab4  mov     [rsp+248h+var_188], rsi
0x180019abc  mov     [rsp+248h+hMem], rsi
0x180019ac4  mov     [rsp+248h+ppResult], rsi
0x180019ac9  xorps   xmm0, xmm0
0x180019acc  movups  xmmword ptr [rsp+248h+pHints.ai_flags], xmm0
0x180019ad4  movups  xmmword ptr [rsp+248h+pHints.ai_addrlen], xmm0
0x180019adc  movups  xmmword ptr [rsp+248h+pHints.ai_addr], xmm0
0x180019ae4  mov     [rsp+248h+pHints.ai_family], esi
0x180019aeb  mov     [rsp+248h+pHints.ai_socktype], 2
0x180019af6  lea     r9, [rsp+248h+ppResult]; ppResult
0x180019afb  lea     r8, [rsp+248h+pHints]; pHints
0x180019b03  lea     rdx, ?wszPort@NtpConst@@2QBGB; "123"
0x180019b0a  mov     rcx, r12; pNodeName
0x180019b0d  call    cs:__imp_GetAddrInfoW
0x180019b14  nop     dword ptr [rax+rax+00h]
0x180019b19  test    eax, eax
0x180019b1b  jz      loc_180019DDF
0x180019b21  call    cs:__imp_WSAGetLastError
0x180019b28  nop     dword ptr [rax+rax+00h]
0x180019b2d  mov     edi, eax
0x180019b2f  test    eax, eax
0x180019b31  jle     short loc_180019B3C
0x180019b33  movzx   edi, ax
0x180019b36  or      edi, 80070000h
0x180019b3c  mov     rax, [rsp+248h+hMem]
0x180019b44  mov     [rsp+248h+var_1D7], 1
0x180019b49  mov     rcx, [rsp+248h+var_188]; hMem
0x180019b51  test    rcx, rcx
0x180019b54  jnz     loc_18001A3DC
0x180019b5a  test    rax, rax
0x180019b5d  jz      short loc_180019B6E
0x180019b5f  mov     rcx, rax; hMem
0x180019b62  call    cs:__imp_LocalFree
0x180019b69  nop     dword ptr [rax+rax+00h]
0x180019b6e  mov     rcx, [rsp+248h+ppResult]; pAddrInfo
0x180019b73  test    rcx, rcx
0x180019b76  jnz     loc_18001A143
0x180019b7c  mov     [rsp+248h+var_1D4], edi
0x180019b80  mov     eax, esi
0x180019b82  mov     ecx, 3
0x180019b87  test    edi, edi
0x180019b89  cmovs   eax, ecx
0x180019b8c  mov     dword ptr [rsp+248h+ppResult], eax
0x180019b90  mov     [rsp+248h+var_190], eax
0x180019b97  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180019b9e  add     rcx, 148h; lpCriticalSection
0x180019ba5  call    cs:__imp_EnterCriticalSection
0x180019bac  nop     dword ptr [rax+rax+00h]
0x180019bb1  mov     [rsp+248h+var_1D8], 1
0x180019bb6  test    r15, r15
0x180019bb9  jz      short loc_180019BC4
0x180019bbb  mov     eax, 2Ch ; ','
0x180019bc0  mov     [r15], ax
0x180019bc4  mov     r15, [rsp+248h+var_1C8]
0x180019bcc  test    edi, edi
0x180019bce  jns     loc_180019E82
0x180019bd4  mov     r15d, dword ptr [rsp+248h+ppResult]
0x180019bd9  mov     rax, [r14]
0x180019bdc  mov     rcx, [rax+8]
0x180019be0  mov     [rcx+5F8h], edi
0x180019be6  mov     rax, [r14]
0x180019be9  mov     rcx, [rax+8]
0x180019bed  mov     dword ptr [rcx+5FCh], 70h ; 'p'
0x180019bf7  cmp     [rsp+248h+var_1D7], 0
0x180019bfc  jnz     loc_18001A183
0x180019c02  mov     ecx, 5
0x180019c07  call    FileLogAllowEntry
0x180019c0c  test    al, al
0x180019c0e  jnz     loc_18001A526
0x180019c14  mov     r10, [r13+8]
0x180019c18  mov     [rsp+248h+var_150], r10
0x180019c20  mov     r9, [r13+0]
0x180019c24  mov     [rsp+248h+var_150], r9
0x180019c2c  mov     [rsp+248h+var_108], r9
0x180019c34  cmp     r9, r10
0x180019c37  jnz     loc_18001A53A
0x180019c3d  mov     [rsp+248h+var_140], r10
0x180019c45  cmp     r10, r9
0x180019c48  jz      short loc_180019C5D
0x180019c4a  mov     r8, r9
0x180019c4d  lea     rdx, [rsp+248h+var_140]
0x180019c55  mov     rcx, r13
0x180019c58  call    ?erase@?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@@Z; std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>)
0x180019c5d  mov     rax, [r14]
0x180019c60  mov     rcx, [rax+8]
0x180019c64  cmp     byte ptr [rcx+608h], 0
0x180019c6b  jnz     loc_18001A25D
0x180019c71  mov     [rsp+248h+var_1C0], esi
0x180019c78  mov     [rsp+248h+SourceString], rsi
0x180019c80  xorps   xmm0, xmm0
0x180019c83  movups  xmmword ptr [rsp+248h+var_138.Length], xmm0
0x180019c8b  xorps   xmm1, xmm1
0x180019c8e  movups  xmmword ptr [rsp+248h+DestinationString.Length], xmm1
0x180019c96  mov     rdx, r12; SourceString
0x180019c99  lea     rcx, [rsp+248h+DestinationString]; DestinationString
0x180019ca1  call    cs:__imp_RtlInitUnicodeString
0x180019ca8  nop     dword ptr [rax+rax+00h]
0x180019cad  lea     rdx, [rsp+248h+SourceString]; unsigned __int16 **
0x180019cb5  mov     ecx, edi; dwMessageId
0x180019cb7  call    ?GetSystemErrorString@@YAJJPEAPEAG@Z; GetSystemErrorString(long,ushort * *)
0x180019cbc  mov     r15d, eax
0x180019cbf  mov     [rsp+248h+var_1C0], eax
0x180019cc6  test    eax, eax
0x180019cc8  js      short loc_180019D3B
0x180019cca  mov     r13, [rsp+248h+SourceString]
0x180019cd2  mov     rdx, r13; SourceString
0x180019cd5  lea     rcx, [rsp+248h+var_138]; DestinationString
0x180019cdd  call    cs:__imp_RtlInitUnicodeString
0x180019ce4  nop     dword ptr [rax+rax+00h]
0x180019ce9  mov     rax, 0E5109EC205D7BEA7h
0x180019cf3  mul     rbx
0x180019cf6  shr     rdx, 1Dh
0x180019cfa  mov     [rsp+248h+SourceString], rdx
0x180019d02  mov     ebx, dword ptr [rsp+248h+ppResult]
0x180019d06  mov     eax, ebx
0x180019d08  sub     eax, 3
0x180019d0b  jz      loc_18001A673
0x180019d11  sub     eax, 1
0x180019d14  jz      loc_18001A5D0
0x180019d1a  cmp     eax, 1
0x180019d1d  jz      loc_18001A578
0x180019d23  mov     rcx, r13; hMem
0x180019d26  call    cs:__imp_LocalFree
0x180019d2d  nop     dword ptr [rax+rax+00h]
0x180019d32  test    r15d, r15d
0x180019d35  jns     loc_180019F5B
0x180019d3b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180019d42  mov     rcx, [rsp+248h+var_100]
0x180019d4a  call    cs:__imp__set_se_translator
0x180019d51  nop     dword ptr [rax+rax+00h]
0x180019d56  test    edi, edi
0x180019d58  js      short loc_180019D5C
0x180019d5a  mov     edi, esi
0x180019d5c  mov     rcx, [rsp+248h+var_178]; hMem
0x180019d64  test    rcx, rcx
0x180019d67  jnz     loc_18001A26F
0x180019d6d  mov     rcx, [rsp+248h+var_170]; hMem
0x180019d75  test    rcx, rcx
0x180019d78  jnz     loc_18001A132
0x180019d7e  mov     rcx, [rsp+248h+var_168]; hMem
0x180019d86  test    rcx, rcx
0x180019d89  jnz     loc_18001A6FC
0x180019d8f  cmp     [rsp+248h+var_1D8], 0
0x180019d94  jnz     loc_180019E63
0x180019d9a  mov     rax, [r14]
0x180019d9d  test    rax, rax
0x180019da0  jz      short loc_180019DAF
0x180019da2  lock xadd [rax], ebx
0x180019da6  cmp     ebx, 1
0x180019da9  jz      loc_18001A247
0x180019daf  mov     eax, edi
0x180019db1  mov     rcx, [rsp+248h+var_38]
0x180019db9  xor     rcx, rsp; StackCookie
0x180019dbc  call    __security_check_cookie
0x180019dc1  lea     r11, [rsp+248h+var_28]
0x180019dc9  mov     rbx, [r11+38h]
0x180019dcd  mov     rsi, [r11+40h]
0x180019dd1  mov     rsp, r11
0x180019dd4  pop     r15
0x180019dd6  pop     r14
0x180019dd8  pop     r13
0x180019dda  pop     r12
0x180019ddc  pop     rdi
0x180019ddd  retn
0x180019ddf  mov     rax, [rsp+248h+ppResult]
0x180019de4  mov     edi, esi
0x180019de6  mov     [rsp+248h+var_1A4], esi
0x180019ded  test    rax, rax
0x180019df0  jnz     short loc_180019E54
0x180019df2  mov     [rsp+248h+var_120], rsi
0x180019dfa  mov     eax, edi
0x180019dfc  mov     ecx, 80h
0x180019e01  mul     rcx
0x180019e04  test    rdx, rdx
0x180019e07  jnz     short loc_180019E4A
0x180019e09  mov     rdx, rax; uBytes
0x180019e0c  mov     ecx, 40h ; '@'; uFlags
0x180019e11  call    cs:__imp_LocalAlloc
0x180019e18  nop     dword ptr [rax+rax+00h]
0x180019e1d  mov     [rsp+248h+var_188], rax
0x180019e25  test    rax, rax
0x180019e28  jz      loc_18001A327
0x180019e2e  mov     [rsp+248h+var_180], rsi
0x180019e36  mov     r8d, 4
0x180019e3c  mov     eax, edi
0x180019e3e  mul     r8
0x180019e41  test    rdx, rdx
0x180019e44  jz      loc_18001A154
0x180019e4a  mov     edi, 80070216h
0x180019e4f  jmp     loc_180019B3C
0x180019e54  inc     edi
0x180019e56  mov     [rsp+248h+var_1A4], edi
0x180019e5d  mov     rax, [rax+28h]
0x180019e61  jmp     short loc_180019DED
0x180019e63  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180019e6a  add     rcx, 148h; lpCriticalSection
0x180019e71  call    cs:__imp_LeaveCriticalSection
0x180019e78  nop     dword ptr [rax+rax+00h]
0x180019e7d  jmp     loc_180019D9A
0x180019e82  mov     r9, [rsp+248h+var_170]
0x180019e8a  mov     rdi, [r15+198h]
0x180019e91  mov     [rsp+248h+var_118], rdi
0x180019e99  mov     rax, [r15+1A0h]
0x180019ea0  mov     [rsp+248h+var_180], rax
0x180019ea8  cmp     rdi, rax
0x180019eab  jz      loc_180019F7B
0x180019eb1  mov     r8d, esi
0x180019eb4  mov     [rsp+248h+var_160], esi
0x180019ebb  cmp     r8d, [rsp+248h+var_1A0]
0x180019ec3  jnb     loc_18001A445
0x180019ec9  mov     rax, [rdi]
0x180019ecc  mov     r10, [rax+8]
0x180019ed0  mov     edx, r8d
0x180019ed3  mov     eax, [r9+rdx*4]
0x180019ed7  cmp     [r10+108h], eax
0x180019ede  jnz     loc_18001A435
0x180019ee4  shl     rdx, 7
0x180019ee8  add     rdx, [rsp+248h+var_178]; struct sockaddr_storage *
0x180019ef0  lea     rcx, [r10+88h]; struct sockaddr_storage *
0x180019ef7  call    ?IsAddrEqual@@YA_NPEAUsockaddr_storage@@0@Z; IsAddrEqual(sockaddr_storage *,sockaddr_storage *)
0x180019efc  cmp     al, 1
0x180019efe  jnz     loc_18001A435
0x180019f04  mov     rcx, [r10+48h]
0x180019f08  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019f0f  inc     rax
0x180019f12  cmp     word ptr [rcx+rax*2], 0
0x180019f17  jnz     short loc_180019F0F
0x180019f19  inc     rax
0x180019f1c  mov     [rsp+248h+var_1C8], rax
0x180019f24  lea     rdx, [rax+rax]; uBytes
0x180019f28  mov     ecx, 40h ; '@'; uFlags
0x180019f2d  call    cs:__imp_LocalAlloc
0x180019f34  nop     dword ptr [rax+rax+00h]
0x180019f39  mov     rcx, rax; unsigned __int16 *
0x180019f3c  mov     [rsp+248h+var_168], rax
0x180019f44  test    rax, rax
0x180019f47  jnz     loc_18001A3F5
0x180019f4d  mov     edi, 8007000Eh
0x180019f52  mov     [rsp+248h+var_1D4], edi
0x180019f56  jmp     loc_18001A420
0x180019f5b  mov     rax, [r14]
  ... truncated ...
```
