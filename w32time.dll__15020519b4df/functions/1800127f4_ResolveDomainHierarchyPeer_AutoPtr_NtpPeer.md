# ResolveDomainHierarchyPeer(AutoPtr<NtpPeer>)

- ea: `0x1800127f4`
- end: `0x1800136c9`
- name: `?ResolveDomainHierarchyPeer@@YAJV?$AutoPtr@UNtpPeer@@@@@Z`
- size: `3797`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017e88`

## callees

- `0x18000a7e0`
- `0x1800127f4`
- `0x1800136d0`
- `0x180014054`
- `0x1800144ac`
- `0x180014774`
- `0x1800164b0`
- `0x180018138`
- `0x180018180`
- `0x180019828`
- `0x18001a714`
- `0x18001a780`
- `0x18001d9a0`
- `0x18002dbc4`
- `0x18002dd98`
- `0x18003d270`
- `0x18003f491`
- `0x18004d9ac`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001288d`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800135de`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001288d`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800135de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013594`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001361d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013636`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001364f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013668`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013684`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013594`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001361d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013636`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001364f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013668`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013684`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012b9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012be4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012b9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012be4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001297f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013604`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001297f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013604`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800128af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012d2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800128af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012d2c`
- `logoncli!I_NetlogonGetTrustRid` at `0x180012a58`
- `logoncli!I_NetlogonGetTrustRid` at `0x180012a58`
- `ntdll!RtlInitUnicodeString` at `0x180012ec1`
- `ntdll!RtlInitUnicodeString` at `0x1800131f6`
- `ntdll!RtlInitUnicodeString` at `0x180013235`
- `ntdll!RtlInitUnicodeString` at `0x1800132d2`
- `ntdll!RtlInitUnicodeString` at `0x1800133ae`
- `ntdll!RtlInitUnicodeString` at `0x180012ec1`
- `ntdll!RtlInitUnicodeString` at `0x1800131f6`
- `ntdll!RtlInitUnicodeString` at `0x180013235`
- `ntdll!RtlInitUnicodeString` at `0x1800132d2`
- `ntdll!RtlInitUnicodeString` at `0x1800133ae`
- `WS2_32!GetAddrInfoW` at `0x180012b1c`
- `WS2_32!GetAddrInfoW` at `0x180012b1c`
- `WS2_32!FreeAddrInfoW` at `0x180012cea`
- `WS2_32!FreeAddrInfoW` at `0x180012cea`
- `WS2_32!__imp_WSAGetLastError` at `0x180012b2c`
- `WS2_32!__imp_WSAGetLastError` at `0x180012b2c`

## string_xrefs

- `0x180013188`: `Logging warning: NtpClient was unable to communicate with Netlogon. Error code: 0x%x\n`
- `0x18001355b`: `Logging warning: NtpClient: This machine is the PDC of the domain at the root of the forest, so there is no machine above it in the domain hierarchy to use as a time source. NtpClient will fall back to the remaining configured time sources, if any are available.\n`
- `0x180013505`: `Logging warning: NtpClient: This machine is in an NT4 domain. NT4 domains do not have a time service, so there is no machine in the domain hierarchy to use as a time source. NtpClient will fall back to the remaining configured time sources, if any are available.\n`
- `0x1800134a6`: `Logging warning: NtpClient was unable to set a domain peer to use as a time source because of discovery error. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n`
- `0x180013477`: `Logging warning: NtpClient: This machine is configured to use the domain hierarchy to determine its time source, but it is not a member of a domain. NtpClient will attempt to use an alternate configured external time source if available.  If an external time source is not configured or used for this computer, you may choose to disable the NtpClient.\n`
- `0x1800133d9`: `Logging warning: NtpClient was unable to set a domain peer to use as a time source because of failure in establishing a trust relationship between this computer and the '%s' domain in order to securely synchronize time. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n`
- `0x180013302`: `Logging warning: NtpClient was unable to set a domain peer to use as a time source because of duplicate error on '%s'. The same time source '%s' has been specified as manual peer in NtpServer. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n`
- `0x180013284`: `Logging warning: NtpClient was unable to set a domain peer to use a time source because of an unexpected error. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall ResolveDomainHierarchyPeer(volatile signed __int32 **a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // ecx
  unsigned int v4; // eax
  signed int DomainHierarchyIpAddrs; // esi
  _NtpProvState *v6; // rax
  int v7; // r15d
  int TrustRid; // eax
  char *v9; // rbx
  int Error; // eax
  PADDRINFOW v11; // rax
  unsigned int v12; // esi
  unsigned int v13; // r13d
  PADDRINFOW ai_next; // rdx
  void *v15; // rcx
  PADDRINFOW v16; // rdx
  char v17; // al
  volatile signed __int32 *v18; // r13
  volatile signed __int32 *v19; // rbx
  __int64 v20; // r15
  unsigned int v21; // r14d
  volatile signed __int32 *v22; // rbx
  __int64 v23; // rcx
  PCWSTR v24; // r10
  PCWSTR v25; // rax
  __int64 v26; // rcx
  int v27; // edx
  int v28; // esi
  PCWSTR v29; // r9
  __int64 v30; // r8
  unsigned int v31; // edx
  volatile signed __int32 *v32; // r11
  volatile signed __int32 *v33; // r10
  volatile signed __int32 *v34; // r9
  int v35; // r13d
  volatile signed __int32 *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  int SystemErrorString; // ebx
  WCHAR *v40; // r13
  int v41; // eax
  PCWSTR v42; // rbx
  __int64 *v43; // rdx
  __int64 v44; // r9
  __int64 *v45; // rdx
  signed int v46; // eax
  _NtpProvState *v47; // rax
  __int64 v48; // r9
  __int64 v50; // [rsp+20h] [rbp-238h]
  __int64 v51; // [rsp+28h] [rbp-230h]
  __int64 v52; // [rsp+30h] [rbp-228h]
  char v53; // [rsp+70h] [rbp-1E8h]
  bool v54; // [rsp+78h] [rbp-1E0h]
  unsigned int v55; // [rsp+7Ch] [rbp-1DCh]
  PCWSTR pNodeName; // [rsp+88h] [rbp-1D0h] BYREF
  volatile signed __int32 *v57; // [rsp+90h] [rbp-1C8h] BYREF
  unsigned int v58; // [rsp+98h] [rbp-1C0h]
  unsigned int v59; // [rsp+9Ch] [rbp-1BCh]
  int v60; // [rsp+A0h] [rbp-1B8h] BYREF
  volatile signed __int32 *v61; // [rsp+A8h] [rbp-1B0h] BYREF
  PADDRINFOW ppResult; // [rsp+B0h] [rbp-1A8h] BYREF
  PCWSTR v63; // [rsp+B8h] [rbp-1A0h] BYREF
  PCWSTR SourceString; // [rsp+C0h] [rbp-198h] BYREF
  unsigned int v65; // [rsp+C8h] [rbp-190h] BYREF
  unsigned int v66; // [rsp+CCh] [rbp-18Ch]
  unsigned int v67; // [rsp+D0h] [rbp-188h]
  int v68; // [rsp+D4h] [rbp-184h] BYREF
  unsigned int v69; // [rsp+D8h] [rbp-180h] BYREF
  int v70; // [rsp+DCh] [rbp-17Ch] BYREF
  PADDRINFOW v71; // [rsp+E0h] [rbp-178h] BYREF
  char *v72; // [rsp+E8h] [rbp-170h]
  HLOCAL v73; // [rsp+F0h] [rbp-168h]
  HLOCAL hMem; // [rsp+F8h] [rbp-160h]
  HLOCAL v75; // [rsp+100h] [rbp-158h]
  volatile signed __int32 **v76; // [rsp+108h] [rbp-150h]
  PCWSTR v77; // [rsp+110h] [rbp-148h] BYREF
  unsigned int v78[2]; // [rsp+118h] [rbp-140h] BYREF
  volatile signed __int32 *v79; // [rsp+120h] [rbp-138h]
  unsigned int v80; // [rsp+128h] [rbp-130h]
  struct _UNICODE_STRING v81; // [rsp+130h] [rbp-128h] BYREF
  __int64 v82; // [rsp+140h] [rbp-118h]
  PADDRINFOW *v83; // [rsp+148h] [rbp-110h]
  volatile signed __int32 *v84; // [rsp+150h] [rbp-108h]
  struct _UNICODE_STRING v85; // [rsp+158h] [rbp-100h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+168h] [rbp-F0h] BYREF
  struct _UNICODE_STRING v87; // [rsp+178h] [rbp-E0h] BYREF
  struct _UNICODE_STRING v88; // [rsp+188h] [rbp-D0h] BYREF
  __int64 v89; // [rsp+198h] [rbp-C0h]
  ADDRINFOW pHints; // [rsp+1A0h] [rbp-B8h] BYREF
  _BYTE v91[32]; // [rsp+208h] [rbp-50h] BYREF

  v76 = a1;
  v58 = 0;
  v78[0] = 0;
  v68 = 0;
  v70 = 0;
  v65 = 0;
  v60 = 0;
  v69 = 0;
  hMem = 0;
  v75 = 0;
  pNodeName = 0;
  v63 = 0;
  v77 = 0;
  v82 = _set_se_translator(SeTransFunc);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  SourceString = (PCWSTR)((char *)g_pnpstate + 408);
  v61 = (volatile signed __int32 *)((char *)g_pnpstate + 432);
  if ( (unsigned __int8)FileLogAllowEntry(52) )
    FileLogAdd(L"Resolving domain peer\n");
  v2 = *((_DWORD *)g_pnpstate + 44);
  v55 = v2;
  v80 = v2;
  v3 = *((_DWORD *)g_pnpstate + 45);
  if ( *(_DWORD *)(*((_QWORD *)*a1 + 1) + 52LL) + 1 <= v3 )
    v3 = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 52LL) + 1;
  LODWORD(v79) = v3;
  v4 = v3;
  v59 = v3;
  while ( v4 > 1 )
  {
    v2 *= 2;
    v55 = v2;
    v80 = v2;
    v59 = --v4;
  }
  (*((void (__fastcall **)(__int64, unsigned int *))g_pnpstate + 2))(13, &v65);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v53 = 0;
  DomainHierarchyIpAddrs = GetDomainHierarchyIpAddrs(
                             *(_DWORD *)(*((_QWORD *)*a1 + 1) + 112LL),
                             *((unsigned int *)g_pnpstate + 43),
                             v65,
                             (unsigned __int16 **)&pNodeName,
                             &v63,
                             &v70,
                             &v60,
                             (int *)&v69);
  v54 = ((v60 - 2) & 0xFFFFFFFD) != 0;
  if ( DomainHierarchyIpAddrs < 0 )
  {
    v7 = 1;
  }
  else
  {
    v6 = g_pnpstate;
    *((_BYTE *)g_pnpstate + 481) = 0;
    *((_BYTE *)v6 + 482) = 1;
    v7 = 0;
  }
  if ( DomainHierarchyIpAddrs < 0 )
    goto LABEL_44;
  TrustRid = I_NetlogonGetTrustRid(0, v63, &v68);
  if ( TrustRid )
  {
    if ( TrustRid > 0 )
      DomainHierarchyIpAddrs = (unsigned __int16)TrustRid | 0x80070000;
    else
      DomainHierarchyIpAddrs = TrustRid;
    v7 = 2;
  }
  if ( DomainHierarchyIpAddrs < 0 )
    goto LABEL_44;
  if ( !pNodeName )
  {
    DomainHierarchyIpAddrs = -2147418113;
    goto LABEL_137;
  }
  v67 = 0;
  v66 = 0;
  v9 = 0;
  v72 = 0;
  v73 = 0;
  ppResult = 0;
  memset(&pHints, 0, sizeof(pHints));
  pHints.ai_family = 0;
  pHints.ai_socktype = 2;
  if ( GetAddrInfoW(pNodeName, L"123", &pHints, &ppResult) )
  {
    Error = WSAGetLastError();
    DomainHierarchyIpAddrs = Error;
    if ( Error > 0 )
      DomainHierarchyIpAddrs = (unsigned __int16)Error | 0x80070000;
    goto LABEL_39;
  }
  v11 = ppResult;
  v12 = 0;
  v66 = 0;
  while ( v11 )
  {
    v66 = ++v12;
    v11 = v11->ai_next;
  }
  v83 = 0;
  if ( !is_mul_ok(0x80u, v12) )
    goto LABEL_36;
  v9 = (char *)LocalAlloc(0x40u, (unsigned __int64)v12 << 7);
  v72 = v9;
  if ( v9 )
  {
    v57 = 0;
    if ( is_mul_ok(4u, v12) )
    {
      v73 = LocalAlloc(0x40u, 4LL * v12);
      if ( v73 )
      {
        v13 = 0;
        v67 = 0;
        ai_next = ppResult;
        v15 = v73;
        while ( 1 )
        {
          v71 = ai_next;
          if ( v13 >= v12 )
            break;
          memcpy_0(&v72[128 * (unsigned __int64)v13], ai_next->ai_addr, ai_next->ai_addrlen);
          v16 = v71;
          v15 = v73;
          *((_DWORD *)v73 + v13++) = v71->ai_addrlen;
          v67 = v13;
          ai_next = v16->ai_next;
        }
        hMem = v72;
        v72 = 0;
        v75 = v15;
        v73 = 0;
        v58 = v12;
        DomainHierarchyIpAddrs = 0;
        goto LABEL_39;
      }
      DomainHierarchyIpAddrs = -2147024882;
LABEL_37:
      if ( v9 )
        LocalFree(v9);
      goto LABEL_39;
    }
LABEL_36:
    DomainHierarchyIpAddrs = -2147024362;
    goto LABEL_37;
  }
  DomainHierarchyIpAddrs = -2147024882;
LABEL_39:
  if ( ppResult )
    FreeAddrInfoW(ppResult);
  if ( DomainHierarchyIpAddrs < 0 )
    v7 = 3;
  v2 = v55;
LABEL_44:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v53 = 1;
  if ( DomainHierarchyIpAddrs >= 0 )
  {
    DomainHierarchyIpAddrs = CheckDuplicatePeers((_DWORD)SourceString, (_DWORD)hMem, (_DWORD)v75, v58, (__int64)&v77);
    if ( DomainHierarchyIpAddrs >= 0 )
    {
      v20 = (__int64)(*((_QWORD *)SourceString + 1) - *(_QWORD *)SourceString) >> 3;
      ppResult = (PADDRINFOW)v20;
      v89 = v20;
      DomainHierarchyIpAddrs = CreateNewActivePeers((struct sockaddr_storage *)hMem, (unsigned int *)v75, v58, v78);
      if ( DomainHierarchyIpAddrs >= 0 )
      {
        if ( *(_BYTE *)(*((_QWORD *)*a1 + 1) + 1545LL) )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, pNodeName);
          if ( (unsigned __int8)FileLogAllowEntry(4) )
            FileLogAdd(
              L"Logging warning: NtpClient succeeds in resolving domain peer %s after a previous failure.\n",
              pNodeName);
          LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_DOMAIN_PEER_SUCCESS_ERROR, L"u", &DestinationString);
        }
        v21 = 0;
        v59 = 0;
        while ( v21 < v78[0] )
        {
          v22 = *(volatile signed __int32 **)(*(_QWORD *)SourceString + 8 * (v20 + v21));
          v57 = v22;
          if ( v22 )
            _InterlockedIncrement(v22);
          v23 = *(_QWORD *)(*((_QWORD *)*a1 + 1) + 88LL);
          v24 = pNodeName;
          if ( v23 )
          {
            v25 = pNodeName;
            v26 = v23 - (_QWORD)pNodeName;
            do
            {
              v27 = *(PCWSTR)((char *)v25 + v26);
              if ( *v25 != v27 )
                break;
              ++v25;
            }
            while ( v27 );
          }
          v28 = v68;
          v29 = v63;
          v30 = v69;
          v83 = &v71;
          v71 = (PADDRINFOW)v22;
          v20 = (__int64)ppResult;
          if ( v22 )
            _InterlockedIncrement(v22);
          DomainHierarchyIpAddrs = MyFillInActivePeersDetail(&v71, 1, v30, v29, v24, v28);
          if ( v22 && _InterlockedExchangeAdd(v22, 0xFFFFFFFF) == 1 )
            Ref<NtpPeer>::`scalar deleting destructor'(v22, v31);
          v59 = ++v21;
        }
        v32 = v61;
        v33 = (volatile signed __int32 *)*((_QWORD *)v61 + 1);
        v57 = v33;
        v34 = *(volatile signed __int32 **)v61;
        v57 = *(volatile signed __int32 **)v61;
        while ( 1 )
        {
          v84 = v34;
          if ( v34 == v33 || (unsigned int)AutoPtr<NtpPeer>::operator==(v34, a1) )
            break;
          v34 += 2;
        }
        v79 = v33;
        if ( v33 != v34 )
          std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v32, &v57);
        goto LABEL_135;
      }
      v7 = 5;
    }
    else
    {
      v7 = 4;
    }
  }
  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 1528LL) = DomainHierarchyIpAddrs;
  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 1532LL) = 92;
  v17 = FileLogAllowEntry(4);
  if ( v54 )
  {
    v35 = (int)v79;
    if ( v17 )
      FileLogAdd(L"Retrying resolution for domain hierarchy. Retry %u will be in %u minutes.\n", (unsigned int)v79, v2);
    *(_QWORD *)(*((_QWORD *)*a1 + 1) + 280LL) = 600000000LL * v2;
    v36 = *a1;
    v37 = *(_QWORD *)(*((_QWORD *)*a1 + 1) + 280LL);
    v57 = (volatile signed __int32 *)&v61;
    v61 = v36;
    if ( v36 )
      _InterlockedIncrement(v36);
    SetPeerTimeRemaining(&v61, v37);
    *(_DWORD *)(*((_QWORD *)*a1 + 1) + 52LL) = v35;
    *(_DWORD *)(*((_QWORD *)*a1 + 1) + 112LL) = v70;
  }
  else
  {
    if ( v17 )
      FileLogAdd(L"Dropping domain hierarchy because name resolution failed.\n");
    v18 = v61;
    v57 = (volatile signed __int32 *)*((_QWORD *)v61 + 1);
    v19 = v57;
    v57 = *(volatile signed __int32 **)v61;
    std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,AutoPtr<NtpPeer>>(
      &v61,
      v57,
      v19,
      a1,
      v50,
      v51,
      v52);
    *(_QWORD *)v78 = v19;
    if ( v19 != v61 )
      std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v18, &v57);
  }
  v38 = *((_QWORD *)*a1 + 1);
  if ( !*(_BYTE *)(v38 + 1545) || *(_DWORD *)(v38 + 1548) != v7 )
  {
    if ( DomainHierarchyIpAddrs == -2147023179 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(4) )
        FileLogAdd(
          L"Logging warning: NtpClient was unable to communicate with Netlogon. Error code: 0x%x\n",
          2147944117LL);
      SystemErrorString = LogThrottledErrorMessage(0x800706B5);
      goto LABEL_133;
    }
    SourceString = 0;
    v85 = 0;
    v81 = 0;
    v87 = 0;
    RtlInitUnicodeString(&v85, pNodeName);
    SystemErrorString = GetSystemErrorString(DomainHierarchyIpAddrs, (unsigned __int16 **)&SourceString);
    if ( SystemErrorString >= 0 )
    {
      v40 = (WCHAR *)SourceString;
      RtlInitUnicodeString(&v81, SourceString);
      if ( v7 != 1 )
      {
        if ( v7 == 2 )
        {
          v88 = 0;
          RtlInitUnicodeString(&v88, v63);
          if ( (unsigned __int8)FileLogAllowEntry(4) )
            FileLogAdd(
              L"Logging warning: NtpClient was unable to set a domain peer to use as a time source because of failure in e"
               "stablishing a trust relationship between this computer and the '%s' domain in order to securely synchroni"
               "ze time. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n",
              v63,
              v91,
              v40);
          v43 = W32TIME_EVENT_DOMAIN_PEER_AUTHENTICATION_ERROR;
        }
        else
        {
          if ( v7 != 3 )
          {
            if ( v7 == 4 )
            {
              v42 = v77;
              RtlInitUnicodeString(&v87, v77);
              if ( (unsigned __int8)FileLogAllowEntry(4) )
                FileLogAdd(
                  L"Logging warning: NtpClient was unable to set a domain peer to use as a time source because of duplicat"
                   "e error on '%s'. The same time source '%s' has been specified as manual peer in NtpServer. NtpClient "
                   "will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n",
                  pNodeName,
                  v42,
                  v91,
                  v40);
              v41 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_DOMAIN_PEER_DUPLICATE_ERROR, L"uduu", &v81);
            }
            else
            {
              if ( v7 != 5 )
              {
LABEL_132:
                LocalFree(v40);
LABEL_133:
                if ( SystemErrorString >= 0 )
                {
                  *(_BYTE *)(*((_QWORD *)*a1 + 1) + 1545LL) = 1;
                  *(_DWORD *)(*((_QWORD *)*a1 + 1) + 1548LL) = v7;
                }
                goto LABEL_135;
              }
              if ( (unsigned __int8)FileLogAllowEntry(4) )
                FileLogAdd(
                  L"Logging warning: NtpClient was unable to set a domain peer to use a time source because of an unexpect"
                   "ed error. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n",
                  v91,
                  v40);
              v41 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_DOMAIN_PEER_UNEXPECTED_ERROR, L"ud", &v81);
            }
LABEL_108:
            SystemErrorString = v41;
            goto LABEL_132;
          }
          if ( (unsigned __int8)FileLogAllowEntry(4) )
            FileLogAdd(
              L"Logging warning: NtpClient was unable to set a domain peer to use as a time source because of DNS resoluti"
               "on error on '%s'. NtpClient will try again in %s minutes. The error was: %s\n",
              pNodeName,
              v91,
              v40);
          v43 = W32TIME_EVENT_DOMAIN_PEER_DNS_ERROR;
        }
        v41 = LogEvent(&_W32TimeRegistrationHandle, v43, L"udu", &v81);
        goto LABEL_108;
      }
      switch ( v60 )
      {
        case 1:
          v47 = g_pnpstate;
          if ( !*((_BYTE *)g_pnpstate + 482) )
          {
            if ( !*((_BYTE *)g_pnpstate + 257) )
            {
              *((_BYTE *)g_pnpstate + 257) = 1;
              if ( (unsigned __int8)FileLogAllowEntry(4) )
                FileLogAdd(
                  L"Logging warning: NtpClient: This machine is the PDC of the domain at the root of the forest, so there "
                   "is no machine above it in the domain hierarchy to use as a time source. NtpClient will fall back to t"
                   "he remaining configured time sources, if any are available.\n");
              DomainHierarchyIpAddrs = LogEvent(
                                         &_W32TimeRegistrationHandle,
                                         W32TIME_EVENT_DOMAIN_HIERARCHY_ROOT,
                                         0,
                                         v48);
              v47 = g_pnpstate;
            }
            *((_BYTE *)v47 + 481) = 1;
          }
          goto LABEL_132;
        case 2:
          if ( *((_BYTE *)g_pnpstate + 258) )
            goto LABEL_132;
          *((_BYTE *)g_pnpstate + 258) = 1;
          if ( (unsigned __int8)FileLogAllowEntry(4) )
            FileLogAdd(
              L"Logging warning: NtpClient: This machine is in an NT4 domain. NT4 domains do not have a time service, so t"
               "here is no machine in the domain hierarchy to use as a time source. NtpClient will fall back to the remai"
               "ning configured time sources, if any are available.\n");
          v45 = W32TIME_EVENT_NT4_DOMAIN;
          break;
        case 3:
          if ( (unsigned __int8)FileLogAllowEntry(4) )
            FileLogAdd(
              L"Logging warning: NtpClient was unable to set a domain peer to use as a time source because of discovery er"
               "ror. NtpClient will try again in %s minutes and double the reattempt interval thereafter. The error was: %s\n",
              v91,
              v40);
          v46 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_DOMAIN_PEER_DISCOVERY_ERROR, L"ud", &v81);
          goto LABEL_125;
        default:
          if ( v60 != 4 || *((_BYTE *)g_pnpstate + 256) )
            goto LABEL_132;
          *((_BYTE *)g_pnpstate + 256) = 1;
          if ( (unsigned __int8)FileLogAllowEntry(4) )
            FileLogAdd(
              L"Logging warning: NtpClient: This machine is configured to use the domain hierarchy to determine its time s"
               "ource, but it is not a member of a domain. NtpClient will attempt to use an alternate configured external"
               " time source if available.  If an external time source is not configured or used for this computer, you m"
               "ay choose to disable the NtpClient.\n");
          v45 = W32TIME_EVENT_NOT_DOMAIN_MEMBER;
          break;
      }
      v46 = LogEvent(&_W32TimeRegistrationHandle, v45, 0, v44);
LABEL_125:
      DomainHierarchyIpAddrs = v46;
      goto LABEL_132;
    }
  }
LABEL_135:
  _set_se_translator(v82);
  if ( DomainHierarchyIpAddrs >= 0 )
    DomainHierarchyIpAddrs = 0;
LABEL_137:
  if ( v53 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  if ( hMem )
    LocalFree(hMem);
  if ( v75 )
    LocalFree(v75);
  if ( pNodeName )
    LocalFree((HLOCAL)pNodeName);
  if ( v63 )
    LocalFree((HLOCAL)v63);
  if ( v77 )
    LocalFree((HLOCAL)v77);
  AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(a1);
  return (unsigned int)DomainHierarchyIpAddrs;
}

```

## disassembly

```asm
0x1800127f4  mov     r11, rsp
0x1800127f7  mov     [r11+10h], rbx
0x1800127fb  mov     [r11+18h], rsi
0x1800127ff  push    rdi
0x180012800  push    r12
0x180012802  push    r13
0x180012804  push    r14
0x180012806  push    r15
0x180012808  sub     rsp, 230h
0x18001280f  mov     rax, cs:__security_cookie
0x180012816  xor     rax, rsp
0x180012819  mov     [rsp+258h+var_30], rax
0x180012821  mov     r12, rcx
0x180012824  mov     [r11-150h], rcx
0x18001282b  xor     edi, edi
0x18001282d  mov     [rsp+258h+var_1E8], dil
0x180012832  mov     [rsp+258h+var_1C0], edi
0x180012839  mov     [rsp+258h+var_140], edi
0x180012840  mov     [rsp+258h+var_184], edi
0x180012847  mov     [rsp+258h+var_17C], edi
0x18001284e  mov     [rsp+258h+var_190], edi
0x180012855  mov     [rsp+258h+var_1B8], edi
0x18001285c  mov     [rsp+258h+var_180], edi
0x180012863  mov     [r11-160h], rdi
0x18001286a  mov     [r11-158h], rdi
0x180012871  mov     [r11-1D0h], rdi
0x180012878  mov     [r11-1A0h], rdi
0x18001287f  mov     [r11-148h], rdi
0x180012886  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18001288d  call    cs:__imp__set_se_translator
0x180012894  nop     dword ptr [rax+rax+00h]
0x180012899  mov     [rsp+258h+var_118], rax
0x1800128a1  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800128a8  add     rcx, 148h; lpCriticalSection
0x1800128af  call    cs:__imp_EnterCriticalSection
0x1800128b6  nop     dword ptr [rax+rax+00h]
0x1800128bb  mov     [rsp+258h+var_1E8], 1
0x1800128c0  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800128c7  lea     rcx, [rax+198h]
0x1800128ce  mov     [rsp+258h+SourceString], rcx
0x1800128d6  add     rax, 1B0h
0x1800128dc  mov     [rsp+258h+var_1B0], rax
0x1800128e4  lea     ecx, [rdi+34h]
0x1800128e7  call    FileLogAllowEntry
0x1800128ec  test    al, al
0x1800128ee  jz      short loc_1800128FC
0x1800128f0  lea     rcx, aResolvingDomai; "Resolving domain peer\n"
0x1800128f7  call    FileLogAdd
0x1800128fc  mov     r8, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180012903  mov     ebx, [r8+0B0h]
0x18001290a  mov     [rsp+258h+var_1DC], ebx
0x18001290e  mov     [rsp+258h+var_130], ebx
0x180012915  mov     rax, [r12]
0x180012919  mov     rcx, [rax+8]
0x18001291d  mov     eax, [rcx+34h]
0x180012920  inc     eax
0x180012922  mov     ecx, [r8+0B4h]
0x180012929  cmp     eax, ecx
0x18001292b  cmovbe  ecx, eax
0x18001292e  mov     dword ptr [rsp+258h+var_138], ecx
0x180012935  mov     eax, ecx
0x180012937  mov     [rsp+258h+var_1BC], ecx
0x18001293e  cmp     eax, 1
0x180012941  jbe     short loc_18001295B
0x180012943  add     ebx, ebx
0x180012945  mov     [rsp+258h+var_1DC], ebx
0x180012949  mov     [rsp+258h+var_130], ebx
0x180012950  dec     eax
0x180012952  mov     [rsp+258h+var_1BC], eax
0x180012959  jmp     short loc_18001293E
0x18001295b  lea     rdx, [rsp+258h+var_190]
0x180012963  mov     ecx, 0Dh
0x180012968  mov     rax, [r8+10h]
0x18001296c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012971  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180012978  add     rcx, 148h; lpCriticalSection
0x18001297f  call    cs:__imp_LeaveCriticalSection
0x180012986  nop     dword ptr [rax+rax+00h]
0x18001298b  mov     [rsp+258h+var_1E8], dil
0x180012990  mov     rax, [r12]
0x180012994  mov     rcx, [rax+8]
0x180012998  lea     rax, [rsp+258h+var_180]
0x1800129a0  mov     [rsp+258h+var_220], rax
0x1800129a5  lea     rax, [rsp+258h+var_1B8]
0x1800129ad  mov     [rsp+258h+var_228], rax
0x1800129b2  lea     rax, [rsp+258h+var_17C]
0x1800129ba  mov     [rsp+258h+var_230], rax
0x1800129bf  lea     rax, [rsp+258h+var_1A0]
0x1800129c7  mov     [rsp+258h+var_238], rax
0x1800129cc  lea     r9, [rsp+258h+pNodeName]
0x1800129d4  mov     r8d, [rsp+258h+var_190]
0x1800129dc  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800129e3  mov     edx, [rdx+0ACh]
0x1800129e9  mov     ecx, [rcx+70h]
0x1800129ec  call    ?GetDomainHierarchyIpAddrs@@YAJW4DiscoveryType@@KKPEAPEAG1PEAW41@PEAW4NtpDiscoveryError@@PEAW4AuthType@@@Z; GetDomainHierarchyIpAddrs(DiscoveryType,ulong,ulong,ushort * *,ushort * *,DiscoveryType *,NtpDiscoveryError *,AuthType *)
0x1800129f1  mov     esi, eax
0x1800129f3  mov     [rsp+258h+var_1E4], eax
0x1800129f7  mov     eax, [rsp+258h+var_1B8]
0x1800129fe  add     eax, 0FFFFFFFEh
0x180012a01  test    eax, 0FFFFFFFDh
0x180012a06  setnz   [rsp+258h+var_1E0]
0x180012a0b  test    esi, esi
0x180012a0d  js      short loc_180012A30
0x180012a0f  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180012a16  mov     [rax+1E1h], dil
0x180012a1d  mov     byte ptr [rax+1E2h], 1
0x180012a24  mov     r15d, edi
0x180012a27  mov     [rsp+258h+var_1D4], edi
0x180012a2e  jmp     short loc_180012A3E
0x180012a30  mov     r15d, 1
0x180012a36  mov     [rsp+258h+var_1D4], r15d
0x180012a3e  test    esi, esi
0x180012a40  js      loc_180012D14
0x180012a46  lea     r8, [rsp+258h+var_184]
0x180012a4e  mov     rdx, [rsp+258h+var_1A0]
0x180012a56  xor     ecx, ecx
0x180012a58  call    cs:__imp_I_NetlogonGetTrustRid
0x180012a5f  nop     dword ptr [rax+rax+00h]
0x180012a64  test    eax, eax
0x180012a66  jz      short loc_180012A89
0x180012a68  jg      short loc_180012A6E
0x180012a6a  mov     esi, eax
0x180012a6c  jmp     short loc_180012A77
0x180012a6e  movzx   esi, ax
0x180012a71  or      esi, 80070000h
0x180012a77  mov     [rsp+258h+var_1E4], esi
0x180012a7b  mov     r15d, 2
0x180012a81  mov     [rsp+258h+var_1D4], r15d
0x180012a89  test    esi, esi
0x180012a8b  js      loc_180012D14
0x180012a91  mov     rcx, [rsp+258h+pNodeName]; pNodeName
0x180012a99  test    rcx, rcx
0x180012a9c  jnz     short loc_180012AAC
0x180012a9e  mov     esi, 8000FFFFh
0x180012aa3  mov     [rsp+258h+var_1E4], esi
0x180012aa7  jmp     loc_1800135EF
0x180012aac  mov     [rsp+258h+var_188], edi
0x180012ab3  mov     [rsp+258h+var_18C], edi
0x180012aba  mov     rbx, rdi
0x180012abd  mov     [rsp+258h+var_170], rbx
0x180012ac5  mov     r13, rdi
0x180012ac8  mov     [rsp+258h+var_168], rdi
0x180012ad0  mov     [rsp+258h+ppResult], rdi
0x180012ad8  xorps   xmm0, xmm0
0x180012adb  movups  xmmword ptr [rsp+258h+pHints.ai_flags], xmm0
0x180012ae3  movups  xmmword ptr [rsp+258h+pHints.ai_addrlen], xmm0
0x180012aeb  movups  xmmword ptr [rsp+258h+pHints.ai_addr], xmm0
0x180012af3  mov     [rsp+258h+pHints.ai_family], edi
0x180012afa  mov     [rsp+258h+pHints.ai_socktype], 2
0x180012b05  lea     r9, [rsp+258h+ppResult]; ppResult
0x180012b0d  lea     r8, [rsp+258h+pHints]; pHints
0x180012b15  lea     rdx, ?wszPort@NtpConst@@2QBGB; "123"
0x180012b1c  call    cs:__imp_GetAddrInfoW
0x180012b23  nop     dword ptr [rax+rax+00h]
0x180012b28  test    eax, eax
0x180012b2a  jz      short loc_180012B52
0x180012b2c  call    cs:__imp_WSAGetLastError
0x180012b33  nop     dword ptr [rax+rax+00h]
0x180012b38  mov     esi, eax
0x180012b3a  test    eax, eax
0x180012b3c  jle     short loc_180012B47
0x180012b3e  movzx   esi, ax
0x180012b41  or      esi, 80070000h
0x180012b47  mov     r14d, 4
0x180012b4d  jmp     loc_180012CDD
0x180012b52  mov     rax, [rsp+258h+ppResult]
0x180012b5a  mov     esi, edi
0x180012b5c  mov     [rsp+258h+var_18C], edi
0x180012b63  test    rax, rax
0x180012b66  jz      short loc_180012B77
0x180012b68  inc     esi
0x180012b6a  mov     [rsp+258h+var_18C], esi
0x180012b71  mov     rax, [rax+28h]
0x180012b75  jmp     short loc_180012B63
0x180012b77  mov     [rsp+258h+var_110], rdi
0x180012b7f  mov     eax, esi
0x180012b81  mov     ecx, 80h
0x180012b86  mul     rcx
0x180012b89  test    rdx, rdx
0x180012b8c  jnz     loc_180012CAA
0x180012b92  mov     rdx, rax; uBytes
0x180012b95  mov     ecx, 40h ; '@'; uFlags
0x180012b9a  call    cs:__imp_LocalAlloc
0x180012ba1  nop     dword ptr [rax+rax+00h]
0x180012ba6  mov     rbx, rax
0x180012ba9  mov     [rsp+258h+var_170], rax
0x180012bb1  mov     r14d, 4
0x180012bb7  test    rax, rax
0x180012bba  jnz     short loc_180012BC6
0x180012bbc  mov     esi, 8007000Eh
0x180012bc1  jmp     loc_180012CC9
0x180012bc6  mov     [rsp+258h+var_1C8], rdi
0x180012bce  mov     eax, esi
0x180012bd0  mul     r14
0x180012bd3  test    rdx, rdx
0x180012bd6  jnz     loc_180012CB0
0x180012bdc  mov     rdx, rax; uBytes
0x180012bdf  mov     ecx, 40h ; '@'; uFlags
0x180012be4  call    cs:__imp_LocalAlloc
0x180012beb  nop     dword ptr [rax+rax+00h]
0x180012bf0  mov     r13, rax
0x180012bf3  mov     [rsp+258h+var_168], rax
0x180012bfb  test    rax, rax
0x180012bfe  jnz     short loc_180012C0A
0x180012c00  mov     esi, 8007000Eh
0x180012c05  jmp     loc_180012CB5
0x180012c0a  mov     r13d, edi
0x180012c0d  mov     [rsp+258h+var_188], edi
0x180012c14  mov     rdx, [rsp+258h+ppResult]
0x180012c1c  mov     rcx, [rsp+258h+var_168]
0x180012c24  mov     [rsp+258h+var_178], rdx
0x180012c2c  cmp     r13d, esi
0x180012c2f  jnb     short loc_180012C77
0x180012c31  mov     ebx, r13d
0x180012c34  mov     ecx, r13d
0x180012c37  shl     rcx, 7
0x180012c3b  add     rcx, [rsp+258h+var_170]; void *
0x180012c43  mov     r8, [rdx+10h]; Size
0x180012c47  mov     rdx, [rdx+20h]; Src
0x180012c4b  call    memcpy_0
0x180012c50  mov     rdx, [rsp+258h+var_178]
0x180012c58  mov     eax, [rdx+10h]
0x180012c5b  mov     rcx, [rsp+258h+var_168]
0x180012c63  mov     [rcx+rbx*4], eax
0x180012c66  inc     r13d
0x180012c69  mov     [rsp+258h+var_188], r13d
0x180012c71  mov     rdx, [rdx+28h]
0x180012c75  jmp     short loc_180012C24
0x180012c77  mov     rax, [rsp+258h+var_170]
0x180012c7f  mov     [rsp+258h+hMem], rax
0x180012c87  mov     [rsp+258h+var_170], rdi
0x180012c8f  mov     [rsp+258h+var_158], rcx
0x180012c97  mov     [rsp+258h+var_168], rdi
0x180012c9f  mov     [rsp+258h+var_1C0], esi
0x180012ca6  mov     esi, edi
0x180012ca8  jmp     short loc_180012CDD
0x180012caa  mov     r14d, 4
0x180012cb0  mov     esi, 80070216h
0x180012cb5  test    rbx, rbx
0x180012cb8  jz      short loc_180012CC9
0x180012cba  mov     rcx, rbx; hMem
0x180012cbd  call    cs:__imp_LocalFree
0x180012cc4  nop     dword ptr [rax+rax+00h]
0x180012cc9  test    r13, r13
0x180012ccc  jz      short loc_180012CDD
0x180012cce  mov     rcx, r13; hMem
0x180012cd1  call    cs:__imp_LocalFree
0x180012cd8  nop     dword ptr [rax+rax+00h]
0x180012cdd  mov     rcx, [rsp+258h+ppResult]; pAddrInfo
0x180012ce5  test    rcx, rcx
0x180012ce8  jz      short loc_180012CF6
0x180012cea  call    cs:__imp_FreeAddrInfoW
0x180012cf1  nop     dword ptr [rax+rax+00h]
0x180012cf6  mov     [rsp+258h+var_1E4], esi
0x180012cfa  mov     r13d, 3
0x180012d00  test    esi, esi
0x180012d02  cmovs   r15d, r13d
0x180012d06  mov     [rsp+258h+var_1D4], r15d
0x180012d0e  mov     ebx, [rsp+258h+var_1DC]
0x180012d12  jmp     short loc_180012D1E
0x180012d14  mov     r13d, 3
0x180012d1a  lea     r14d, [r13+1]
0x180012d1e  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180012d25  add     rcx, 148h; lpCriticalSection
0x180012d2c  call    cs:__imp_EnterCriticalSection
0x180012d33  nop     dword ptr [rax+rax+00h]
0x180012d38  mov     [rsp+258h+var_1E8], 1
0x180012d3d  test    esi, esi
0x180012d3f  js      short loc_180012D8C
0x180012d41  lea     rax, [rsp+258h+var_148]
0x180012d49  mov     [rsp+258h+var_238], rax
0x180012d4e  mov     r9d, [rsp+258h+var_1C0]
0x180012d56  mov     r8, [rsp+258h+var_158]
0x180012d5e  mov     rdx, [rsp+258h+hMem]
0x180012d66  mov     rcx, [rsp+258h+SourceString]
0x180012d6e  call    ?CheckDuplicatePeers@@YAJAEAV?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@PEAUsockaddr_storage@@PEAIIPEAPEAG@Z; CheckDuplicatePeers(std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>> &,sockaddr_storage *,uint *,uint,ushort * *)
0x180012d73  mov     esi, eax
0x180012d75  mov     [rsp+258h+var_1E4], eax
0x180012d79  test    eax, eax
0x180012d7b  jns     loc_180012E30
0x180012d81  mov     r15d, r14d
0x180012d84  mov     [rsp+258h+var_1D4], r14d
0x180012d8c  mov     rax, [r12]
0x180012d90  mov     rcx, [rax+8]
0x180012d94  mov     [rcx+5F8h], esi
0x180012d9a  mov     rax, [r12]
0x180012d9e  mov     rcx, [rax+8]
0x180012da2  mov     dword ptr [rcx+5FCh], 5Ch ; '\'
0x180012dac  mov     ecx, r14d
0x180012daf  call    FileLogAllowEntry
0x180012db4  cmp     [rsp+258h+var_1E0], dil
0x180012db9  jnz     loc_1800130BC
0x180012dbf  test    al, al
0x180012dc1  jz      short loc_180012DCF
0x180012dc3  lea     rcx, aDroppingDomain; "Dropping domain hierarchy because name "...
0x180012dca  call    FileLogAdd
0x180012dcf  mov     r13, [rsp+258h+var_1B0]
0x180012dd7  mov     rbx, [r13+8]
0x180012ddb  mov     [rsp+258h+var_1C8], rbx
0x180012de3  mov     rdx, [r13+0]
  ... truncated ...
```
