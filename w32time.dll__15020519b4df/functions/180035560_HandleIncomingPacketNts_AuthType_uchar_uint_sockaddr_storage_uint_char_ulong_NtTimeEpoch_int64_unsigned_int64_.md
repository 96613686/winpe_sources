# HandleIncomingPacketNts(AuthType,uchar *,uint,sockaddr_storage *,uint,char *,ulong,NtTimeEpoch *,__int64 *,unsigned __int64 *,ulong)

- ea: `0x180035560`
- end: `0x1800370b3`
- name: `?HandleIncomingPacketNts@@YAJW4AuthType@@PEAEIPEAUsockaddr_storage@@IPEADKPEAUNtTimeEpoch@@PEA_JPEA_KK@Z`
- size: `6995`
- prototype: `__int64 __fastcall(unsigned int, _OWORD *, unsigned int, __int64, unsigned int, SOCKET, unsigned int, const WCHAR *, __int64 *, struct _LIST_ENTRY *, int)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004348c`

## callees

- `0x18000a7e0`
- `0x1800144f0`
- `0x180014718`
- `0x1800164b0`
- `0x180018138`
- `0x180018dfc`
- `0x18001a780`
- `0x18001ae80`
- `0x18001d9a0`
- `0x18002c918`
- `0x18002cc6c`
- `0x18002d518`
- `0x18002dbc4`
- `0x18002e768`
- `0x180034e9c`
- `0x180035560`
- `0x18003a718`
- `0x18003b8fc`
- `0x18003d270`
- `0x18003dd2c`
- `0x18003f485`
- `0x180041348`
- `0x180041fc8`
- `0x180042000`
- `0x180042044`
- `0x180042108`
- `0x1800425ec`
- `0x1800456c8`
- `0x180046f8c`
- `0x180055a28`
- `0x180055bfc`
- `0x18005b1f8`
- `0x18005b38c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800356a4`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180036ffb`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800356a4`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180036ffb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036cb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003705d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037076`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036cb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003705d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037076`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036b10`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036b10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800357b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035b19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035d97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035e50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036de8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037044`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800357b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035b19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035d97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035e50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036de8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037044`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800356e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800359ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035c3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800366d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800356e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800359ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035c3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800366d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a09`
- `logoncli!I_NetlogonComputeClientDigest` at `0x1800357f9`
- `logoncli!I_NetlogonComputeClientDigest` at `0x1800357f9`
- `logoncli!I_NetlogonComputeClientSignature` at `0x18003588f`
- `logoncli!I_NetlogonComputeClientSignature` at `0x18003588f`
- `ntdll!RtlInitUnicodeString` at `0x180035f5e`
- `ntdll!RtlInitUnicodeString` at `0x180035f75`
- `ntdll!RtlInitUnicodeString` at `0x1800360a2`
- `ntdll!RtlInitUnicodeString` at `0x18003624c`
- `ntdll!RtlInitUnicodeString` at `0x1800364b2`
- `ntdll!RtlInitUnicodeString` at `0x180036c46`
- `ntdll!RtlInitUnicodeString` at `0x180035f5e`
- `ntdll!RtlInitUnicodeString` at `0x180035f75`
- `ntdll!RtlInitUnicodeString` at `0x1800360a2`
- `ntdll!RtlInitUnicodeString` at `0x18003624c`
- `ntdll!RtlInitUnicodeString` at `0x1800364b2`
- `ntdll!RtlInitUnicodeString` at `0x180036c46`
- `WS2_32!__imp_sendto` at `0x180035dd4`
- `WS2_32!__imp_sendto` at `0x180036e1c`
- `WS2_32!__imp_sendto` at `0x180035dd4`
- `WS2_32!__imp_sendto` at `0x180036e1c`
- `WS2_32!__imp_WSAGetLastError` at `0x180035de7`
- `WS2_32!__imp_WSAGetLastError` at `0x180036e2d`
- `WS2_32!__imp_WSAGetLastError` at `0x180035de7`
- `WS2_32!__imp_WSAGetLastError` at `0x180036e2d`

## string_xrefs

- `0x180035b61`: `ListeningThread STC:%I64u\n`
- `0x180035f1a`: `Logging warning: NtpClient encountered an error while validating the computer account for this machine, so NtpClient cannot determine whether the response received from %s has a valid signature. The response will be ignored. The error was: %s\n`
- `0x180035fca`: `Can't verify packet because compute digest failed. Ignoring packet.\n`
- `0x180036585`: `Ignoring packet invalid mode combination (in:%d out:%d).\n`
- `0x180036744`: `  Considering peer=%s with peertype=%d.\n`
- `0x180036a7f`: ` has exceeded cache limit (%d). Could not remove any stale host entries.\n.`
- `0x180036aeb`: ` has exceeded cache limit (%d). Entries were removed, but none for this host.\n.`
- `0x180036c99`: `RODC: could not fwd incoming signature pkt to downlevel DC %s because client's RID (0x%x(%d))has TRUST_RID_OLD_DIGEST_BIT bit set\n`
- `0x180036ed0`: `ListeningThread -- demobilize long term peer (NYI).\n`
- `0x180036fc1`: `Ignoring packet that would create dynamic peer\n`
- `0x180036fd9`: `ListeningThread -- save response from new long term peer (NYI)\n`
- `0x1800355e3`: `Failing as we are attempting to call HandleIncomingPacketNts when nts feature is not enabled.\n`

## pseudocode

```c
__int64 __fastcall HandleIncomingPacketNts(
        unsigned int a1,
        _OWORD *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        SOCKET a6,
        unsigned int a7,
        const WCHAR *a8,
        __int64 *a9,
        struct _LIST_ENTRY *a10,
        int a11)
{
  signed int v14; // r13d
  _NtpProvState *v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rax
  volatile signed __int32 *v18; // r8
  _NtpProvState *v19; // r9
  struct sockaddr_storage *v20; // r10
  unsigned int v21; // r11d
  __int64 v22; // rdx
  volatile signed __int32 *v23; // rbx
  signed int v24; // eax
  __int64 v25; // rdx
  int v26; // esi
  __int64 v27; // rdx
  __int64 v28; // rax
  volatile signed __int32 *v29; // r8
  _NtpProvState *v30; // r9
  __int64 v31; // rdx
  __int64 v32; // rcx
  struct _LIST_ENTRY *v33; // rsi
  SOCKET v34; // rdi
  _NtpProvState *v35; // rcx
  int v36; // r8d
  unsigned int v37; // ebx
  __int64 v38; // rcx
  char v39; // r8
  char v40; // al
  WCHAR *v41; // rsi
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rdx
  const wchar_t *v46; // r8
  __int64 v47; // rax
  __int64 v48; // rdx
  const wchar_t *v49; // r8
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rdi
  int v53; // r13d
  int v54; // eax
  char v55; // al
  __int64 v56; // rcx
  __int64 v57; // rax
  SOCKET v58; // rbx
  __int64 v59; // rcx
  unsigned int v60; // esi
  volatile signed __int32 *v61; // rdi
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rax
  struct sockaddr *v65; // rbx
  __int64 v66; // rcx
  int tolen; // r13d
  int v68; // esi
  _QWORD *v69; // rax
  _QWORD *v70; // rbx
  _OWORD *v71; // rax
  unsigned int v72; // edi
  int v73; // esi
  _NtpProvState *v74; // rax
  char *v75; // rdx
  _NtpProvState **v76; // r8
  volatile signed __int32 **v77; // rax
  volatile signed __int32 **v78; // rax
  struct sockaddr *to; // [rsp+20h] [rbp-3F8h]
  char v80; // [rsp+50h] [rbp-3C8h]
  char v81; // [rsp+51h] [rbp-3C7h]
  char v82; // [rsp+52h] [rbp-3C6h]
  bool v83; // [rsp+53h] [rbp-3C5h]
  volatile signed __int32 *v84; // [rsp+58h] [rbp-3C0h] BYREF
  unsigned int v85; // [rsp+60h] [rbp-3B8h]
  volatile signed __int32 *v86; // [rsp+68h] [rbp-3B0h] BYREF
  unsigned int v87; // [rsp+70h] [rbp-3A8h]
  PCWSTR SourceString; // [rsp+78h] [rbp-3A0h] BYREF
  volatile signed __int32 *v89; // [rsp+80h] [rbp-398h] BYREF
  int v90; // [rsp+88h] [rbp-390h]
  SOCKET s; // [rsp+90h] [rbp-388h] BYREF
  struct _LIST_ENTRY *p_s; // [rsp+98h] [rbp-380h] BYREF
  unsigned int v93; // [rsp+A0h] [rbp-378h] BYREF
  unsigned int v94; // [rsp+A4h] [rbp-374h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-370h] BYREF
  volatile signed __int32 *v96; // [rsp+B8h] [rbp-360h] BYREF
  struct _UNICODE_STRING v97; // [rsp+C0h] [rbp-358h] BYREF
  _OWORD *v98; // [rsp+D0h] [rbp-348h]
  void *Buf1; // [rsp+D8h] [rbp-340h] BYREF
  HLOCAL hMem; // [rsp+E0h] [rbp-338h] BYREF
  __int64 v101; // [rsp+E8h] [rbp-330h] BYREF
  volatile signed __int32 *v102; // [rsp+F0h] [rbp-328h]
  volatile signed __int32 *v103; // [rsp+F8h] [rbp-320h]
  SOCKET v104; // [rsp+100h] [rbp-318h]
  __int64 v105; // [rsp+108h] [rbp-310h]
  struct _UNICODE_STRING v106; // [rsp+110h] [rbp-308h] BYREF
  struct _UNICODE_STRING v107; // [rsp+120h] [rbp-2F8h] BYREF
  struct _UNICODE_STRING v108; // [rsp+130h] [rbp-2E8h] BYREF
  struct _UNICODE_STRING v109; // [rsp+140h] [rbp-2D8h] BYREF
  _BYTE v110[40]; // [rsp+188h] [rbp-290h] BYREF
  _DWORD v111[35]; // [rsp+1B0h] [rbp-268h] BYREF
  int v112; // [rsp+23Ch] [rbp-1DCh]
  int v113; // [rsp+240h] [rbp-1D8h]
  int v114; // [rsp+244h] [rbp-1D4h]
  int v115; // [rsp+248h] [rbp-1D0h]
  unsigned int v116; // [rsp+24Ch] [rbp-1CCh]
  char v117; // [rsp+258h] [rbp-1C0h]
  char v118; // [rsp+25Ah] [rbp-1BEh]
  char v119; // [rsp+25Bh] [rbp-1BDh]
  char v120; // [rsp+25Ch] [rbp-1BCh]
  _OWORD v121[3]; // [rsp+260h] [rbp-1B8h] BYREF
  int v122; // [rsp+290h] [rbp-188h]
  struct sockaddr v123; // [rsp+2B0h] [rbp-168h] BYREF
  struct _LIST_ENTRY v124; // [rsp+2C0h] [rbp-158h]
  struct _LIST_ENTRY v125; // [rsp+2D0h] [rbp-148h]
  struct _LIST_ENTRY v126; // [rsp+2E0h] [rbp-138h]
  struct _LIST_ENTRY v127; // [rsp+2F0h] [rbp-128h]
  struct _LIST_ENTRY v128; // [rsp+300h] [rbp-118h]
  struct _LIST_ENTRY v129; // [rsp+310h] [rbp-108h]
  struct _LIST_ENTRY v130; // [rsp+320h] [rbp-F8h]
  struct sockaddr v131; // [rsp+330h] [rbp-E8h] BYREF
  __int128 v132; // [rsp+340h] [rbp-D8h]
  __int128 v133; // [rsp+350h] [rbp-C8h]
  __int128 v134; // [rsp+360h] [rbp-B8h]
  __int128 v135; // [rsp+370h] [rbp-A8h]
  __int128 v136; // [rsp+380h] [rbp-98h]
  __int128 v137; // [rsp+390h] [rbp-88h]
  __int128 v138; // [rsp+3A0h] [rbp-78h]
  _QWORD v139[2]; // [rsp+3B0h] [rbp-68h] BYREF
  _QWORD v140[2]; // [rsp+3C0h] [rbp-58h] BYREF

  *(_QWORD *)&v97.Length = a4;
  v87 = a3;
  v85 = a1;
  s = a6;
  SourceString = a8;
  p_s = a10;
  if ( !*((_BYTE *)g_pnpstate + 50) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Failing as we are attempting to call HandleIncomingPacketNts when nts feature is not enabled.\n");
    return 2147500033LL;
  }
  if ( *((_BYTE *)g_pnpstate + 49) != 1 || (v82 = 1, (*((_BYTE *)g_pnpstate + 144) & 4) == 0) )
    v82 = 0;
  v14 = 50;
  AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v84, 0);
  v15 = g_pnpstate;
  *(_QWORD *)&DestinationString.Length = g_pnpstate;
  Buf1 = 0;
  v93 = 0;
  hMem = 0;
  v94 = 0;
  v101 = 0;
  v83 = a1 - 1 <= 1;
  memset_0(v111, 0, 0xB0u);
  (*((void (__fastcall **)(__int64, __int64 *))v15 + 2))(3, &v101);
  v80 = 0;
  v81 = 0;
  v105 = _set_se_translator(SeTransFunc);
  if ( *((_BYTE *)g_pnpstate + 49) == 1 && (*(_BYTE *)a2 & 7) != 3 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
    v80 = 1;
    v17 = *(_QWORD *)&DestinationString.Length;
    v18 = *(volatile signed __int32 **)(*(_QWORD *)&DestinationString.Length + 408LL);
    v102 = v18;
    v19 = g_pnpstate;
    v20 = *(struct sockaddr_storage **)&v97.Length;
    v21 = a5;
    while ( 1 )
    {
      v89 = *(volatile signed __int32 **)(v17 + 416);
      if ( v18 == v89 )
        break;
      v22 = *(_QWORD *)(*(_QWORD *)v18 + 8LL);
      v16 = *(_QWORD *)(*((_QWORD *)v19 + 8) + 8LL * v87);
      if ( *(_QWORD *)(v22 + 272) == v16
        && *(_DWORD *)(v22 + 264) == v21
        && IsAddrEqual((struct sockaddr_storage *)(v22 + 136), v20) )
      {
        AutoPtr<NtpPeer>::operator=(&v84, v18);
        v19 = g_pnpstate;
        break;
      }
      v89 = v18;
      v18 += 2;
      v102 = v18;
      v17 = *(_QWORD *)&DestinationString.Length;
    }
    if ( !a1 || !(unsigned int)operator!=(v16, &v84) )
    {
      v23 = v84;
LABEL_55:
      if ( v23 && *((_QWORD *)v23 + 1) )
      {
        v32 = 106;
      }
      else
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 328));
        v80 = 0;
        v32 = 115;
      }
      if ( (unsigned __int8)FileLogAllowEntry(v32) )
        FileLogNtpPacket(a2, *(_QWORD *)SourceString);
      if ( (unsigned __int8)FileLogAllowEntry(120) )
        FileLogAdd(L"ListeningThread STC:%I64u\n", p_s->Flink);
      goto LABEL_66;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 328));
    v80 = 0;
    switch ( a1 )
    {
      case 1u:
        v23 = v84;
        v24 = I_NetlogonComputeClientDigest(0, *(_QWORD *)(*((_QWORD *)v84 + 1) + 96LL), a2, 48, v139, v140);
LABEL_24:
        v14 = v24;
        goto LABEL_42;
      case 2u:
        v23 = v84;
        if ( *((_BYTE *)a2 + 52) != 1 )
          goto LABEL_42;
        v24 = I_NetlogonComputeClientSignature(
                0,
                *(_QWORD *)(*((_QWORD *)v84 + 1) + 96LL),
                1,
                a2,
                48,
                &Buf1,
                &v93,
                &hMem,
                &v94);
        goto LABEL_24;
      case 3u:
        if ( *((_BYTE *)g_pnpstate + 50) )
        {
          v23 = v84;
          v25 = *((_QWORD *)v84 + 1);
          if ( *(_DWORD *)(v25 + 56) != 3 )
          {
            v26 = -2147024809;
            goto LABEL_290;
          }
          std::wstring::wstring(v110, *(_QWORD *)(v25 + 72));
          if ( a11 == 84 )
          {
            ValidateNtsKodPacket(v110, a2, &a11);
            if ( (unsigned __int8)FileLogAllowEntry(200) )
              FileLogAdd(L"Done with KOD packet\n");
            std::wstring::~wstring((__int64)v110);
            goto LABEL_289;
          }
          v26 = ValidateNtsNtpPacket(v110, a2, &a11);
          if ( v26 < 0 )
          {
            std::wstring::~wstring((__int64)v110);
            goto LABEL_290;
          }
          std::wstring::~wstring((__int64)v110);
LABEL_42:
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
          v80 = 1;
          AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v96, 0);
          v28 = *(_QWORD *)&DestinationString.Length;
          v29 = *(volatile signed __int32 **)(*(_QWORD *)&DestinationString.Length + 408LL);
          v103 = v29;
          v30 = g_pnpstate;
          while ( 1 )
          {
            v89 = *(volatile signed __int32 **)(v28 + 416);
            if ( v29 == v89 )
              break;
            v31 = *(_QWORD *)(*(_QWORD *)v29 + 8LL);
            if ( *(_QWORD *)(v31 + 272) == *(_QWORD *)(*((_QWORD *)v30 + 8) + 8LL * v87)
              && *(_DWORD *)(v31 + 264) == a5
              && IsAddrEqual((struct sockaddr_storage *)(v31 + 136), *(struct sockaddr_storage **)&v97.Length) )
            {
              AutoPtr<NtpPeer>::operator=(&v96, v29);
              break;
            }
            v89 = v29;
            v29 += 2;
            v103 = v29;
            v28 = *(_QWORD *)&DestinationString.Length;
          }
          if ( !v96 || !*((_QWORD *)v96 + 1) || !(unsigned int)AutoPtr<NtpPeer>::operator==(&v84, &v96) )
          {
            AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v89, 0);
            AutoPtr<NtpPeer>::operator=(&v84, &v89);
            AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v89);
            v23 = v84;
          }
          AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v96);
          v19 = g_pnpstate;
          goto LABEL_55;
        }
        if ( (unsigned __int8)FileLogAllowEntry(14) )
        {
          v27 = 3;
LABEL_40:
          FileLogAdd(L"Received unexpected type: %d.\n", v27);
        }
        break;
      default:
        if ( (unsigned __int8)FileLogAllowEntry(14) )
        {
          v27 = a1;
          goto LABEL_40;
        }
        break;
    }
    v23 = v84;
    goto LABEL_42;
  }
  if ( (unsigned __int8)FileLogAllowEntry(118) )
    FileLogNtpPacket(a2, *(_QWORD *)SourceString);
  v23 = v84;
LABEL_66:
  v116 = v85;
  ParseNtpPacketStep1(
    (struct NtpSimplePeer *)v111,
    (struct NtpPacket *)a2,
    (struct NtTimeEpoch *)SourceString,
    a9,
    (unsigned __int64 *)p_s);
  if ( v120 == 1 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(14) )
      FileLogAdd(L"Ignoring garbage packet.\n");
    goto LABEL_289;
  }
  if ( v83 && !*((_BYTE *)g_pnpstate + 548) && *((_BYTE *)g_pnpstate + 508) && (*(_BYTE *)a2 & 7) == 4 )
  {
    p_s = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
    if ( (unsigned __int8)FileLogAllowEntry(131) )
      FileLogAdd(L"RODC: Checking for table entry.\n");
    ChainTableDump();
    if ( ChainTableContainsEntry(
           *((_DWORD *)a2 + 12),
           (struct NtpTimeEpoch *)((char *)a2 + 24),
           (struct RodcCacheEntry **)&p_s) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"RODC: Forwarding response to client ");
      v33 = p_s;
      FileLogSockaddrInEx2(
        1,
        (struct sockaddr *)&p_s[1],
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * SLODWORD(p_s[9].Flink)) + 128LL));
      FileLogAppend(L"\n");
      memset_0(&v123, 0, 0x80u);
      v34 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * SLODWORD(v33[9].Flink)) + 136LL);
      v123 = (struct sockaddr)v33[1];
      v124 = v33[2];
      v125 = v33[3];
      v126 = v33[4];
      v127 = v33[5];
      v128 = v33[6];
      v129 = v33[7];
      v130 = v33[8];
      ChainTableRemoveEntry(v33);
      v35 = g_pnpstate;
      ++*((_DWORD *)g_pnpstate + 125);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v35 + 368));
      v81 = 0;
      v36 = 68;
      if ( v85 != 1 )
        v36 = 120;
      v37 = sendto(v34, (const char *)a2, v36, 0, &v123, 128);
      if ( v37 == -1 )
      {
        WSAGetLastError();
        if ( (unsigned __int8)FileLogAllowEntry(2) )
          FileLogAdd(L"RODC: Logging information: NtpClient got SOCKET_ERROR sending response to client.\n");
      }
      else if ( (unsigned __int8)FileLogAllowEntry(131) )
      {
        FileLogAdd(L"RODC: response (0x%x bytes) sent to client.\n", v37);
      }
      goto LABEL_289;
    }
    if ( (unsigned __int8)FileLogAllowEntry(131) )
      FileLogAdd(L"RODC: No matching table entry. Processing locally.\n");
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
    v81 = 0;
  }
  if ( !v85 )
  {
    v112 = 0;
    if ( (unsigned int)operator!=(0, &v84) )
    {
      v51 = *((_QWORD *)v23 + 1);
      v38 = *(unsigned int *)(v51 + 56);
      if ( (_DWORD)v38 )
      {
        if ( (unsigned int)(v38 - 1) <= 1 )
        {
          *(_DWORD *)(v51 + 1528) = -2147467259;
          *(_DWORD *)(*((_QWORD *)v23 + 1) + 1532LL) = 107;
          if ( (unsigned __int8)FileLogAllowEntry(7) )
            FileLogAdd(
              L"Logging warning: NtpClient: The response received from domain controller %s is missing the signature. The "
               "response may have been tampered with and will be ignored.\n",
              *(_QWORD *)(*((_QWORD *)v23 + 1) + 88LL));
          if ( (*((_DWORD *)g_pnpstate + 48) & 4) != 0 )
          {
            v108 = 0;
            RtlInitUnicodeString(&v108, *(PCWSTR *)(*((_QWORD *)v23 + 1) + 88LL));
            LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MISSING_SIGNATURE, L"u", &v108);
          }
        }
        else if ( (_DWORD)v38 == 3 )
        {
          *(_DWORD *)(v51 + 1528) = -2147467259;
          *(_DWORD *)(*((_QWORD *)v23 + 1) + 1532LL) = 107;
          if ( (unsigned __int8)FileLogAllowEntry(7) )
            FileLogAdd(L"Logging warning: NtpClient: This is an invalid NTS packet.\n");
          if ( !*((_BYTE *)a2 + 1) && (unsigned __int8)FileLogAllowEntry(7) )
          {
            LODWORD(to) = *((unsigned __int8 *)a2 + 15);
            FileLogAdd(
              L"Logging warning: NtpClient: Invalid NTS packet has stratum 0, log refid in case bad KOD packet %d, %d, %d, %d.\n",
              *((unsigned __int8 *)a2 + 12),
              *((unsigned __int8 *)a2 + 13),
              *((unsigned __int8 *)a2 + 14),
              to);
          }
        }
        if ( (unsigned __int8)FileLogAllowEntry(7) )
          FileLogAdd(L"Unauthenticated packet recieved from authenticated peer.\n");
        goto LABEL_289;
      }
    }
    goto LABEL_173;
  }
  if ( (unsigned int)operator!=(v85, &v84) )
  {
    v38 = *(unsigned int *)(*((_QWORD *)v23 + 1) + 56LL);
    v112 = v38;
    if ( (_DWORD)v38 && v14 && v39 )
    {
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      SourceString = 0;
      if ( (int)GetSystemErrorString(v14, (unsigned __int16 **)&SourceString) >= 0 )
      {
        *(_DWORD *)(*((_QWORD *)v23 + 1) + 1528LL) = -2147467259;
        *(_DWORD *)(*((_QWORD *)v23 + 1) + 1532LL) = 105;
        v40 = FileLogAllowEntry(7);
        v41 = (WCHAR *)SourceString;
        if ( v40 )
          FileLogAdd(
            L"Logging warning: NtpClient encountered an error while validating the computer account for this machine, so N"
             "tpClient cannot determine whether the response received from %s has a valid signature. The response will be"
             " ignored. The error was: %s\n",
            *(_QWORD *)(*((_QWORD *)v23 + 1) + 88LL),
            SourceString);
        if ( (*((_DWORD *)g_pnpstate + 48) & 4) != 0 )
        {
          DestinationString = 0;
          v97 = 0;
          RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(*((_QWORD *)v23 + 1) + 88LL));
          RtlInitUnicodeString(&v97, v41);
          LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_COMPUTE_CLIENT_DIGEST_FAILED, L"uu", &DestinationString);
        }
        LocalFree(v41);
      }
      if ( (unsigned __int8)FileLogAllowEntry(7) )
        FileLogAdd(L"Can't verify packet because compute digest failed. Ignoring packet.\n");
      goto LABEL_289;
    }
    if ( v116 == 1 )
    {
      v42 = v139[0] - *(_QWORD *)((char *)a2 + 52);
      if ( v139[0] == *(_QWORD *)((char *)a2 + 52) )
        v42 = v139[1] - *(_QWORD *)((char *)a2 + 60);
      if ( v42 )
      {
        v43 = v140[0] - *(_QWORD *)((char *)a2 + 52);
        if ( v140[0] == *(_QWORD *)((char *)a2 + 52) )
          v43 = v140[1] - *(_QWORD *)((char *)a2 + 60);
        if ( v43 )
        {
          v44 = *((_QWORD *)v23 + 1);
          if ( *(_BYTE *)(v44 + 118) )
          {
            *(_DWORD *)(v44 + 1528) = -2147467259;
            *(_DWORD *)(*((_QWORD *)v23 + 1) + 1532LL) = 106;
            if ( (unsigned __int8)FileLogAllowEntry(7) )
              FileLogAdd(
                L"Logging warning: NtpClient: The response received from domain controller %s has an bad signature. The re"
                 "sponse may have been tampered with and will be ignored.\n",
                *(_QWORD *)(*((_QWORD *)v23 + 1) + 88LL));
            if ( (*((_DWORD *)g_pnpstate + 48) & 4) != 0 )
            {
              v106 = 0;
              RtlInitUnicodeString(&v106, *(PCWSTR *)(*((_QWORD *)v23 + 1) + 88LL));
              LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_BAD_SIGNATURE, L"u", &v106);
            }
            if ( (unsigned __int8)FileLogAllowEntry(7) )
              FileLogAdd(L"Digest shows packet tampered with. Ignoring packet.\n");
            *(_BYTE *)(*((_QWORD *)v23 + 1) + 117LL) = 0;
          }
          else
          {
            if ( (unsigned __int8)FileLogAllowEntry(7) )
            {
              v45 = *((_QWORD *)v23 + 1);
              v46 = L"TRUE";
              if ( !*(_BYTE *)(v45 + 117) )
                v46 = L"FALSE";
              FileLogAdd(
                L"Response received from domain controller %s failed to authenticate.  Using old server digest: %s.\n",
                *(_QWORD *)(v45 + 88),
                v46);
            }
            *(_BYTE *)(*((_QWORD *)v23 + 1) + 118LL) = 1;
            *(_BYTE *)(*((_QWORD *)v23 + 1) + 117LL) = *(_BYTE *)(*((_QWORD *)v23 + 1) + 117LL) == 0;
          }
          goto LABEL_289;
        }
      }
      if ( (unsigned __int8)FileLogAllowEntry(7) )
        FileLogAdd(
          L"Response received from domain controller %s authenticated successfully (using digest format)\n",
          *(_QWORD *)(*((_QWORD *)v23 + 1) + 88LL));
    }
    else
    {
      if ( v116 != 2 )
      {
        if ( !(_DWORD)v38 )
        {
          if ( (unsigned __int8)FileLogAllowEntry(7) )
            FileLogAdd(L"non-auth peer set authenticated packet!\n");
          goto LABEL_289;
        }
        goto LABEL_173;
      }
      if ( (v93 < 0x40 || memcmp_0(Buf1, (char *)a2 + 56, 0x40u))
        && (v94 < 0x40 || memcmp_0(hMem, (char *)a2 + 56, 0x40u)) )
      {
        v47 = *((_QWORD *)v23 + 1);
        if ( *(_BYTE *)(v47 + 118) )
        {
          *(_DWORD *)(v47 + 1528) = -2147467259;
          *(_DWORD *)(*((_QWORD *)v23 + 1) + 1532LL) = 106;
          if ( (unsigned __int8)FileLogAllowEntry(7) )
            FileLogAdd(
              L"Logging warning: NtpClient: The response received from domain controller %s has an bad signature. The resp"
               "onse may have been tampered with and will be ignored.\n",
              *(_QWORD *)(*((_QWORD *)v23 + 1) + 88LL));
          if ( (*((_DWORD *)g_pnpstate + 48) & 4) != 0 )
          {
            v107 = 0;
            RtlInitUnicodeString(&v107, *(PCWSTR *)(*((_QWORD *)v23 + 1) + 88LL));
            LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_BAD_SIGNATURE, L"u", &v107);
          }
          if ( (unsigned __int8)FileLogAllowEntry(7) )
            FileLogAdd(L"Digest shows packet tampered with. Ignoring packet.\n");
          *(_BYTE *)(*((_QWORD *)v23 + 1) + 117LL) = 0;
        }
        else
        {
          if ( (unsigned __int8)FileLogAllowEntry(7) )
          {
            v48 = *((_QWORD *)v23 + 1);
            v49 = L"TRUE";
            if ( !*(_BYTE *)(v48 + 117) )
              v49 = L"FALSE";
            FileLogAdd(
              L"Response received from domain controller %s failed to authenticate.  Using old server digest: %s.\n",
              *(_QWORD *)(v48 + 88),
              v49);
          }
          *(_BYTE *)(*((_QWORD *)v23 + 1) + 118LL) = 1;
          *(_BYTE *)(*((_QWORD *)v23 + 1) + 117LL) = *(_BYTE *)(*((_QWORD *)v23 + 1) + 117LL) == 0;
        }
        goto LABEL_289;
      }
      if ( (unsigned __int8)FileLogAllowEntry(7) )
        FileLogAdd(
          L"Response received from domain controller %s authenticated successfully (using signature format)\n",
          *(_QWORD *)(*((_QWORD *)v23 + 1) + 88LL));
    }
    *(_BYTE *)(*((_QWORD *)v23 + 1) + 118LL) = 0;
  }
  else if ( v39 )
  {
    v50 = *((_DWORD *)a2 + 12);
    if ( (_DWORD)v38 == 1 )
    {
      v112 = 1;
      v113 = v50;
    }
    else
    {
      v112 = 2;
      v113 = v50;
      v114 = *((_BYTE *)a2 + 54) & 1;
      v115 = *((unsigned __int8 *)a2 + 53);
    }
  }
  else if ( (_DWORD)v38 == 3 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(7) )
      FileLogAdd(L"We received an NTS packet from an unknown peer. Therefore we can't validate the packet so we will discard.\n");
  }
  else if ( (unsigned __int8)FileLogAllowEntry(7) )
  {
    FileLogAdd(L"unknown auth type: %d\n", v85);
  }
LABEL_173:
  v52 = v111[0];
  if ( (unsigned int)operator!=(v38, &v84) )
  {
    v53 = *(_DWORD *)(*((_QWORD *)v23 + 1) + 804LL);
  }
  else if ( *((_BYTE *)g_pnpstate + 48) != 1 || v112 == 3 )
  {
    v53 = 0;
  }
  else if ( (_DWORD)v52 == 3 || !v82 )
  {
    v53 = 4;
  }
  else
  {
    v53 = 2;
  }
  v111[34] = v53;
  v54 = *((_DWORD *)&qword_180072230[4 * v52] + v53);
  switch ( v54 )
  {
    case 0:
      if ( (unsigned __int8)FileLogAllowEntry(14) )
        FileLogAdd(L"Ignoring packet invalid mode combination (in:%d out:%d).\n", (unsigned int)v52, (unsigned int)v53);
      goto LABEL_289;
    case 5:
      if ( *((_BYTE *)g_pnpstate + 168) != 1 )
      {
        if ( !(unsigned __int8)FileLogAllowEntry(14) )
          goto LABEL_289;
        goto LABEL_188;
      }
      goto LABEL_273;
    case 6:
      if ( *((_BYTE *)g_pnpstate + 259) != 1 )
      {
        if ( !(unsigned __int8)FileLogAllowEntry(14) )
          goto LABEL_289;
LABEL_188:
        FileLogAdd(L"Ignoring packet in nonstandard mode.\n");
        goto LABEL_289;
      }
      break;
    case 3:
      if ( v117 == 1 )
      {
        v55 = v82;
        if ( v82 )
        {
LABEL_274:
          if ( v23 && *((_QWORD *)v23 + 1) )
          {
            if ( !v119 )
            {
              if ( (unsigned __int8)FileLogAllowEntry(14) )
                FileLogAdd(L"Rejecting packet w/ bad poll interval\n");
              goto LABEL_289;
            }
            if ( !v118 )
            {
              if ( (unsigned __int8)FileLogAllowEntry(14) )
                FileLogAdd(L"Rejecting packet w/ bad precision\n");
              goto LABEL_289;
            }
            p_s = (struct _LIST_ENTRY *)&s;
            v77 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>((volatile signed __int32 **)&s, &v84);
            ParseNtpPacketStep2(v77, v111, a2);
            SourceString = (PCWSTR)&v89;
            v78 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v89, &v84);
            ProcessPeerUpdate(v78, v111);
          }
          else
          {
            if ( !v55 )
            {
              if ( (unsigned __int8)FileLogAllowEntry(14) )
                FileLogAdd(L"Ignoring packet that would create dynamic peer\n");
              goto LABEL_289;
            }
            if ( (unsigned __int8)FileLogAllowEntry(14) )
              FileLogAdd(L"ListeningThread -- save response from new long term peer (NYI)\n");
          }
LABEL_288:
          _set_se_translator(v105);
          goto LABEL_289;
        }
      }
      break;
    case 2:
      break;
    default:
LABEL_273:
      v55 = v82;
      goto LABEL_274;
  }
  if ( !*((_BYTE *)g_pnpstate + 48) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(14) )
      FileLogAdd(L"Ignoring packet because server not running.\n");
    goto LABEL_289;
  }
  Increment(&g_ullNtpServerIncomingRequestRate);
  if ( !TransmitResponse(
          (struct NtpSimplePeer *)v111,
          *(struct sockaddr_storage **)&v97.Length,
          a5,
          (char *)s,
          a7,
          *(struct NicSocket **)(*((_QWORD *)g_pnpstate + 8) + 8LL * v87)) )
  {
    if ( (unsigned int)operator!=(v56, &v84) && (unsigned __int8)FileLogAllowEntry(14) )
      FileLogAdd(L"ListeningThread -- demobilize long term peer (NYI).\n");
    goto LABEL_288;
  }
  AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v86, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v80 = 1;
  if ( (unsigned __int8)FileLogAllowEntry(131) )
    FileLogAdd(L"BEGIN: peer search for chaining.\n");
  v57 = *(_QWORD *)&DestinationString.Length;
  v58 = *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 408LL);
  v104 = v58;
  while ( 1 )
  {
    s = *(_QWORD *)(v57 + 416);
    if ( v58 == s )
    {
      v60 = v85;
      goto LABEL_223;
    }
    if ( (unsigned __int8)FileLogAllowEntry(131) )
      FileLogAdd(
        L"  Considering peer=%s with peertype=%d.\n",
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v58 + 8LL) + 88LL),
        *(unsigned int *)(*(_QWORD *)(*(_QWORD *)v58 + 8LL) + 48LL));
    v59 = *(_QWORD *)(*(_QWORD *)v58 + 8LL);
    if ( *(_DWORD *)(v59 + 48) != 1 )
      goto LABEL_219;
    v60 = v85;
    if ( v85 != 2 )
      break;
    if ( *(_DWORD *)(v59 + 56) == 2 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(
          L"  Choosing peer=%s for chaining (signature mode).\n",
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v58 + 8LL) + 88LL));
      AutoPtr<NtpPeer>::operator=(&v86, v58);
      goto LABEL_223;
    }
    if ( !v86 || !*((_QWORD *)v86 + 1) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"  Saving candidate downlevel peer=%s.\n", *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v58 + 8LL) + 88LL));
      AutoPtr<NtpPeer>::operator=(&v86, v58);
    }
LABEL_219:
    s = v58;
    v58 += 8LL;
    v104 = v58;
    v57 = *(_QWORD *)&DestinationString.Length;
  }
  AutoPtr<NtpPeer>::operator=(&v86, v58);
  if ( (unsigned __int8)FileLogAllowEntry(131) )
    FileLogAdd(
      L"  Choosing peer=%s for chaining (digest mode).\n",
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v58 + 8LL) + 88LL));
LABEL_223:
  if ( (unsigned __int8)FileLogAllowEntry(131) )
    FileLogAdd(L"END: peer search for chaining.\n");
  v61 = v86;
  if ( !v86 || !*((_QWORD *)v86 + 1) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(131) )
      FileLogAdd(L"Logging warning: Unable to locate an NT5DS Peer Chaining Deferred.\n");
    goto LABEL_269;
  }
  if ( (unsigned __int8)FileLogAllowEntry(131) )
  {
    v62 = AuthTypeToSz(*(unsigned int *)(*((_QWORD *)v61 + 1) + 56LL));
    FileLogAdd(L"RODC: Using Time Source %s (%s)\n", v63 + 290, v62);
  }
  if ( (unsigned __int8)FileLogAllowEntry(131) )
  {
    v64 = AuthTypeToSz(v60);
    FileLogAdd(L"RODC: Forwarding %s request from client ", v64);
  }
  v65 = *(struct sockaddr **)&v97.Length;
  FileLogSockaddrInEx2(1, *(struct sockaddr **)&v97.Length, a5);
  FileLogAppend(L" to server ");
  FileLogSockaddrInEx2(1, (struct sockaddr *)(*((_QWORD *)v61 + 1) + 136LL), 0x80u);
  FileLogAppend(L" \n");
  memset_0(&v131, 0, 0x80u);
  v66 = *((_QWORD *)v61 + 1);
  tolen = *(_DWORD *)(v66 + 264);
  s = *(_QWORD *)(*(_QWORD *)(v66 + 272) + 136LL);
  v131 = *(struct sockaddr *)(v66 + 136);
  v132 = *(_OWORD *)(v66 + 152);
  v133 = *(_OWORD *)(v66 + 168);
  v134 = *(_OWORD *)(v66 + 184);
  v135 = *(_OWORD *)(v66 + 200);
  v136 = *(_OWORD *)(v66 + 216);
  v137 = *(_OWORD *)(v66 + 232);
  v138 = *(_OWORD *)(v66 + 248);
  v68 = *(_DWORD *)(*((_QWORD *)v61 + 1) + 56LL);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v80 = 0;
  memset_0(v121, 0, 0x48u);
  v98 = 0;
  v90 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
  v81 = 1;
  RemoveStaleEntries(0);
  if ( FailedSecurityCheck((struct sockaddr_storage *)v65) )
  {
    if ( !RemoveStaleEntries(1) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"RODC: Peer ");
      FileLogSockaddrInEx2(1, v65, a5);
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(
          L" has exceeded cache limit (%d). Could not remove any stale host entries.\n.",
          *((unsigned int *)g_pnpstate + 139));
      goto LABEL_269;
    }
    if ( FailedSecurityCheck((struct sockaddr_storage *)v65) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"RODC: Peer ");
      FileLogSockaddrInEx2(1, v65, a5);
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(
          L" has exceeded cache limit (%d). Entries were removed, but none for this host.\n.",
          *((unsigned int *)g_pnpstate + 139));
      goto LABEL_269;
    }
  }
  v69 = LocalAlloc(0x40u, 0xB0u);
  v70 = v69;
  if ( !v69 )
  {
    v26 = -2147024882;
    AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v86);
    goto LABEL_291;
  }
  memset_0(v69, 0, 0xB0u);
  v70[19] = v101;
  v70[20] = *((_QWORD *)a2 + 5);
  *((_DWORD *)v70 + 36) = v87;
  v71 = *(_OWORD **)&v97.Length;
  *((_OWORD *)v70 + 1) = *(_OWORD *)*(_QWORD *)&v97.Length;
  *((_OWORD *)v70 + 2) = v71[1];
  *((_OWORD *)v70 + 3) = v71[2];
  *((_OWORD *)v70 + 4) = v71[3];
  *((_OWORD *)v70 + 5) = v71[4];
  *((_OWORD *)v70 + 6) = v71[5];
  *((_OWORD *)v70 + 7) = v71[6];
  *((_OWORD *)v70 + 8) = v71[7];
  if ( v68 == 1 || v85 == 1 )
  {
    v73 = *((_DWORD *)a2 + 12);
    if ( v85 == 2 )
    {
      if ( v73 < 0 )
      {
        v109 = 0;
        RtlInitUnicodeString(&v109, (PCWSTR)(*((_QWORD *)v61 + 1) + 290LL));
        LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_RODCUNABLETOFWDREQUEST, L"du", *((unsigned int *)a2 + 12));
        if ( (unsigned __int8)FileLogAllowEntry(6) )
          FileLogAdd(
            L"RODC: could not fwd incoming signature pkt to downlevel DC %s because client's RID (0x%x(%d))has TRUST_RID_O"
             "LD_DIGEST_BIT bit set\n",
            *((_QWORD *)v61 + 1) + 290LL,
            *((unsigned int *)a2 + 12),
            *((unsigned int *)a2 + 12),
            &v109);
        v26 = -2147467259;
        LocalFree(v70);
        AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v86);
        goto LABEL_291;
      }
      memset_0(v121, 0, 0x48u);
      v121[0] = *a2;
      v121[1] = a2[1];
      v121[2] = a2[2];
      v122 = v73;
      *((_DWORD *)v70 + 37) = v73;
      a2 = v121;
      v98 = v121;
      v72 = 68;
      v90 = 68;
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"RODC: downgrading client request from signature to digest format.\n");
    }
    else
    {
      v98 = a2;
      v72 = 68;
      v90 = 68;
      *((_DWORD *)v70 + 37) = v73;
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"RODC: forwarding client's digest packet as-is.\n");
    }
    *((_DWORD *)v70 + 42) = 1;
    goto LABEL_258;
  }
  v98 = a2;
  v72 = 120;
  v90 = 120;
  *((_DWORD *)v70 + 37) = *((_DWORD *)a2 + 12);
  *((_DWORD *)v70 + 42) = 1;
  if ( (unsigned __int8)FileLogAllowEntry(131) )
    FileLogAdd(L"RODC: forwarding client's signature packet as-is.\n");
LABEL_258:
  if ( (unsigned __int8)FileLogAllowEntry(131) )
    FileLogAdd(L"RODC: Adding request to table : \n");
  v74 = g_pnpstate;
  v75 = (char *)g_pnpstate + 528;
  v76 = (_NtpProvState **)*((_QWORD *)g_pnpstate + 67);
  if ( *v76 != (_NtpProvState *)((char *)g_pnpstate + 528) )
    __fastfail(3u);
  *v70 = v75;
  v70[1] = v76;
  *v76 = (_NtpProvState *)v70;
  *((_QWORD *)v75 + 1) = v70;
  ++*((_DWORD *)v74 + 136);
  ++*((_DWORD *)v74 + 124);
  ChainTableDump();
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
  v81 = 0;
  if ( sendto(s, (const char *)a2, v72, 0, &v131, tolen) == -1 )
  {
    WSAGetLastError();
    if ( (unsigned __int8)FileLogAllowEntry(2) )
      FileLogAdd(L"RODC: Logging information: NtpClient fails sending response to client.\n");
  }
  else if ( (unsigned __int8)FileLogAllowEntry(131) )
  {
    FileLogAdd(L"RODC: sent packet (0x%x(%d) bytes) to peer DC.\n", v72, v72);
  }
LABEL_269:
  AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v86);
LABEL_289:
  v26 = 0;
LABEL_290:
  if ( v81 )
LABEL_291:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
  if ( v80 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  if ( Buf1 )
    LocalFree(Buf1);
  if ( hMem )
    LocalFree(hMem);
  AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v84);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180035560  push    rbx
0x180035562  push    rsi
0x180035563  push    rdi
0x180035564  push    r12
0x180035566  push    r13
0x180035568  push    r14
0x18003556a  push    r15
0x18003556c  sub     rsp, 3E0h
0x180035573  mov     rax, cs:__security_cookie
0x18003557a  xor     rax, rsp
0x18003557d  mov     [rsp+418h+var_48], rax
0x180035585  mov     qword ptr [rsp+418h+var_358.Length], r9
0x18003558d  mov     [rsp+418h+var_3A8], r8d
0x180035592  mov     r15, rdx
0x180035595  mov     ebx, ecx
0x180035597  mov     [rsp+418h+var_3B8], ecx
0x18003559b  mov     rax, [rsp+418h+arg_28]
0x1800355a3  mov     [rsp+418h+s], rax
0x1800355ab  mov     rax, [rsp+418h+arg_38]
0x1800355b3  mov     [rsp+418h+SourceString], rax
0x1800355b8  mov     rax, [rsp+418h+arg_48]
0x1800355c0  mov     [rsp+418h+var_380], rax
0x1800355c8  xor     r14d, r14d
0x1800355cb  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800355d2  cmp     [rax+32h], r14b
0x1800355d6  jnz     short loc_1800355F9
0x1800355d8  xor     ecx, ecx
0x1800355da  call    FileLogAllowEntry
0x1800355df  test    al, al
0x1800355e1  jz      short loc_1800355EF
0x1800355e3  lea     rcx, aFailingAsWeAre_0; "Failing as we are attempting to call Ha"...
0x1800355ea  call    FileLogAdd
0x1800355ef  mov     eax, 80004001h
0x1800355f4  jmp     loc_18003708F
0x1800355f9  mov     r12d, 4
0x1800355ff  cmp     byte ptr [rax+31h], 1
0x180035603  jnz     short loc_180035613
0x180035605  test    [rax+90h], r12b
0x18003560c  mov     [rsp+418h+var_3C6], 1
0x180035611  jnz     short loc_180035618
0x180035613  mov     [rsp+418h+var_3C6], r14b
0x180035618  xor     edx, edx
0x18003561a  lea     r13d, [rdx+32h]
0x18003561e  lea     rcx, [rsp+418h+var_3C0]
0x180035623  call    ??0?$AutoPtr@UNtpPeer@@@@QEAA@PEAUNtpPeer@@@Z; AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(NtpPeer *)
0x180035628  nop
0x180035629  mov     rdi, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180035630  mov     qword ptr [rsp+418h+DestinationString.Length], rdi
0x180035638  mov     [rsp+418h+Buf1], r14
0x180035640  mov     [rsp+418h+var_378], r14d
0x180035648  mov     [rsp+418h+hMem], r14
0x180035650  mov     [rsp+418h+var_374], r14d
0x180035658  mov     [rsp+418h+var_330], r14
0x180035660  lea     eax, [rbx-1]
0x180035663  cmp     eax, 1
0x180035666  setbe   [rsp+418h+var_3C5]
0x18003566b  xor     edx, edx; Val
0x18003566d  lea     r8d, [r13+7Eh]; Size
0x180035671  lea     rcx, [rsp+418h+var_268]; void *
0x180035679  call    memset_0
0x18003567e  lea     rdx, [rsp+418h+var_330]
0x180035686  lea     ecx, [r13-2Fh]
0x18003568a  mov     rax, [rdi+10h]
0x18003568e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035693  mov     [rsp+418h+var_3C8], r14b
0x180035698  mov     [rsp+418h+var_3C7], r14b
0x18003569d  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800356a4  call    cs:__imp__set_se_translator
0x1800356ab  nop     dword ptr [rax+rax+00h]
0x1800356b0  mov     [rsp+418h+var_310], rax
0x1800356b8  mov     esi, r14d
0x1800356bb  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800356c2  lea     edi, [r13-2Bh]
0x1800356c6  cmp     byte ptr [rcx+31h], 1
0x1800356ca  jnz     loc_180035B6F
0x1800356d0  mov     al, [r15]
0x1800356d3  and     al, dil
0x1800356d6  cmp     al, 3
0x1800356d8  jz      loc_180035B6F
0x1800356de  add     rcx, 148h; lpCriticalSection
0x1800356e5  call    cs:__imp_EnterCriticalSection
0x1800356ec  nop     dword ptr [rax+rax+00h]
0x1800356f1  mov     [rsp+418h+var_3C8], 1
0x1800356f6  mov     rax, qword ptr [rsp+418h+DestinationString.Length]
0x1800356fe  mov     r8, [rax+198h]
0x180035705  mov     [rsp+418h+var_328], r8
0x18003570d  mov     r9, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180035714  mov     r10, qword ptr [rsp+418h+var_358.Length]
0x18003571c  mov     r11d, [rsp+418h+arg_20]
0x180035724  mov     rax, [rax+1A0h]
0x18003572b  mov     [rsp+418h+var_398], rax
0x180035733  cmp     r8, rax
0x180035736  jz      short loc_180035790
0x180035738  mov     rax, [r8]
0x18003573b  mov     rdx, [rax+8]
0x18003573f  mov     ecx, [rsp+418h+var_3A8]
0x180035743  mov     rax, [r9+40h]
0x180035747  mov     rcx, [rax+rcx*8]
0x18003574b  cmp     [rdx+110h], rcx
0x180035752  jnz     loc_18003580A
0x180035758  cmp     [rdx+108h], r11d
0x18003575f  jnz     loc_18003580A
0x180035765  lea     rcx, [rdx+88h]; struct sockaddr_storage *
0x18003576c  mov     rdx, r10; struct sockaddr_storage *
0x18003576f  call    ?IsAddrEqual@@YA_NPEAUsockaddr_storage@@0@Z; IsAddrEqual(sockaddr_storage *,sockaddr_storage *)
0x180035774  cmp     al, 1
0x180035776  jnz     loc_18003580A
0x18003577c  mov     rdx, r8
0x18003577f  lea     rcx, [rsp+418h+var_3C0]
0x180035784  call    ??4?$AutoPtr@UNtpPeer@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<NtpPeer>::operator=(AutoPtr<NtpPeer> const &)
0x180035789  mov     r9, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180035790  test    ebx, ebx
0x180035792  jz      loc_180035AF4
0x180035798  lea     rdx, [rsp+418h+var_3C0]
0x18003579d  call    ??9@YAHPEBXAEBV?$AutoPtr@UNtpPeer@@@@@Z; operator!=(void const *,AutoPtr<NtpPeer> const &)
0x1800357a2  test    eax, eax
0x1800357a4  jz      loc_180035AF4
0x1800357aa  lea     rcx, [r9+148h]; lpCriticalSection
0x1800357b1  call    cs:__imp_LeaveCriticalSection
0x1800357b8  nop     dword ptr [rax+rax+00h]
0x1800357bd  mov     [rsp+418h+var_3C8], r14b
0x1800357c2  cmp     ebx, 1
0x1800357c5  jnz     short loc_18003582B
0x1800357c7  mov     rbx, [rsp+418h+var_3C0]
0x1800357cc  mov     rdx, [rbx+8]
0x1800357d0  lea     rax, [rsp+418h+var_58]
0x1800357d8  mov     qword ptr [rsp+418h+tolen], rax
0x1800357dd  lea     rax, [rsp+418h+var_68]
0x1800357e5  mov     [rsp+418h+to], rax
0x1800357ea  mov     r9d, 30h ; '0'
0x1800357f0  mov     r8, r15
0x1800357f3  mov     rdx, [rdx+60h]
0x1800357f7  xor     ecx, ecx
0x1800357f9  call    cs:__imp_I_NetlogonComputeClientDigest
0x180035800  nop     dword ptr [rax+rax+00h]
0x180035805  jmp     loc_18003589B
0x18003580a  mov     [rsp+418h+var_398], r8
0x180035812  add     r8, 8
0x180035816  mov     [rsp+418h+var_328], r8
0x18003581e  mov     rax, qword ptr [rsp+418h+DestinationString.Length]
0x180035826  jmp     loc_180035724
0x18003582b  cmp     ebx, 2
0x18003582e  jnz     short loc_1800358A3
0x180035830  mov     rbx, [rsp+418h+var_3C0]
0x180035835  cmp     byte ptr [r15+34h], 1
0x18003583a  jnz     loc_18003599F
0x180035840  mov     rdx, [rbx+8]
0x180035844  lea     rax, [rsp+418h+var_374]
0x18003584c  mov     [rsp+418h+var_3D8], rax
0x180035851  lea     rax, [rsp+418h+hMem]
0x180035859  mov     [rsp+418h+var_3E0], rax
0x18003585e  lea     rax, [rsp+418h+var_378]
0x180035866  mov     [rsp+418h+var_3E8], rax
0x18003586b  lea     rax, [rsp+418h+Buf1]
0x180035873  mov     qword ptr [rsp+418h+tolen], rax
0x180035878  mov     dword ptr [rsp+418h+to], 30h ; '0'
0x180035880  mov     r9, r15
0x180035883  mov     r8d, 1
0x180035889  mov     rdx, [rdx+60h]
0x18003588d  xor     ecx, ecx
0x18003588f  call    cs:__imp_I_NetlogonComputeClientSignature
0x180035896  nop     dword ptr [rax+rax+00h]
0x18003589b  mov     r13d, eax
0x18003589e  jmp     loc_18003599F
0x1800358a3  cmp     ebx, 3
0x1800358a6  jnz     loc_18003597E
0x1800358ac  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800358b3  cmp     [rax+32h], r14b
0x1800358b7  jz      loc_180035969
0x1800358bd  mov     rbx, [rsp+418h+var_3C0]
0x1800358c2  mov     rdx, [rbx+8]
0x1800358c6  cmp     dword ptr [rdx+38h], 3
0x1800358ca  jz      short loc_1800358DA
0x1800358cc  mov     esi, 80070057h
0x1800358d1  mov     [rsp+418h+var_3C4], esi
0x1800358d5  jmp     loc_18003700E
0x1800358da  mov     rdx, [rdx+48h]
0x1800358de  lea     rcx, [rsp+418h+var_290]
0x1800358e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800358eb  nop
0x1800358ec  lea     r8, [rsp+418h+arg_50]
0x1800358f4  mov     rdx, r15
0x1800358f7  lea     rcx, [rsp+418h+var_290]
0x1800358ff  cmp     [rsp+418h+arg_50], 54h ; 'T'
0x180035907  jnz     short loc_180035940
0x180035909  call    ?ValidateNtsKodPacket@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEADAEAK@Z; ValidateNtsKodPacket(std::wstring &,char *,ulong &)
0x18003590e  mov     [rsp+418h+var_3C4], eax
0x180035912  mov     ecx, 0C8h
0x180035917  call    FileLogAllowEntry
0x18003591c  test    al, al
0x18003591e  jz      short loc_18003592D
0x180035920  lea     rcx, aDoneWithKodPac; "Done with KOD packet\n"
0x180035927  call    FileLogAdd
0x18003592c  nop
0x18003592d  lea     rcx, [rsp+418h+var_290]
0x180035935  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003593a  nop
0x18003593b  jmp     loc_18003700B
0x180035940  call    ?ValidateNtsNtpPacket@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEADAEAK@Z; ValidateNtsNtpPacket(std::wstring &,char *,ulong &)
0x180035945  mov     esi, eax
0x180035947  mov     [rsp+418h+var_3C4], eax
0x18003594b  lea     rcx, [rsp+418h+var_290]
0x180035953  test    eax, eax
0x180035955  jns     short loc_180035962
0x180035957  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003595c  nop
0x18003595d  jmp     loc_18003700E
0x180035962  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035967  jmp     short loc_18003599F
0x180035969  mov     ecx, 0Eh
0x18003596e  call    FileLogAllowEntry
0x180035973  test    al, al
0x180035975  jz      short loc_18003599A
0x180035977  mov     edx, 3
0x18003597c  jmp     short loc_18003598E
0x18003597e  mov     ecx, 0Eh
0x180035983  call    FileLogAllowEntry
0x180035988  test    al, al
0x18003598a  jz      short loc_18003599A
0x18003598c  mov     edx, ebx
0x18003598e  lea     rcx, aReceivedUnexpe; "Received unexpected type: %d.\n"
0x180035995  call    FileLogAdd
0x18003599a  mov     rbx, [rsp+418h+var_3C0]
0x18003599f  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800359a6  add     rcx, 148h; lpCriticalSection
0x1800359ad  call    cs:__imp_EnterCriticalSection
0x1800359b4  nop     dword ptr [rax+rax+00h]
0x1800359b9  mov     [rsp+418h+var_3C8], 1
0x1800359be  xor     edx, edx
0x1800359c0  lea     rcx, [rsp+418h+var_360]
0x1800359c8  call    ??0?$AutoPtr@UNtpPeer@@@@QEAA@PEAUNtpPeer@@@Z; AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(NtpPeer *)
0x1800359cd  nop
0x1800359ce  mov     rax, qword ptr [rsp+418h+DestinationString.Length]
0x1800359d6  mov     r8, [rax+198h]
0x1800359dd  mov     [rsp+418h+var_320], r8
0x1800359e5  mov     r9, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800359ec  mov     rax, [rax+1A0h]
0x1800359f3  mov     [rsp+418h+var_398], rax
0x1800359fb  cmp     r8, rax
0x1800359fe  jz      short loc_180035A5F
0x180035a00  mov     rax, [r8]
0x180035a03  mov     rdx, [rax+8]
0x180035a07  mov     ecx, [rsp+418h+var_3A8]
0x180035a0b  mov     rax, [r9+40h]
0x180035a0f  mov     rcx, [rax+rcx*8]
0x180035a13  cmp     [rdx+110h], rcx
0x180035a1a  jnz     loc_180035AD3
0x180035a20  mov     eax, [rsp+418h+arg_20]
0x180035a27  cmp     [rdx+108h], eax
0x180035a2d  jnz     loc_180035AD3
0x180035a33  lea     rcx, [rdx+88h]; struct sockaddr_storage *
0x180035a3a  mov     rdx, qword ptr [rsp+418h+var_358.Length]; struct sockaddr_storage *
0x180035a42  call    ?IsAddrEqual@@YA_NPEAUsockaddr_storage@@0@Z; IsAddrEqual(sockaddr_storage *,sockaddr_storage *)
0x180035a47  cmp     al, 1
0x180035a49  jnz     loc_180035AD3
0x180035a4f  mov     rdx, r8
0x180035a52  lea     rcx, [rsp+418h+var_360]
0x180035a5a  call    ??4?$AutoPtr@UNtpPeer@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<NtpPeer>::operator=(AutoPtr<NtpPeer> const &)
0x180035a5f  mov     rax, [rsp+418h+var_360]
0x180035a67  test    rax, rax
0x180035a6a  jz      short loc_180035A88
0x180035a6c  cmp     [rax+8], r14
0x180035a70  jz      short loc_180035A88
0x180035a72  lea     rdx, [rsp+418h+var_360]
0x180035a7a  lea     rcx, [rsp+418h+var_3C0]
0x180035a7f  call    ??8?$AutoPtr@UNtpPeer@@@@QEAAHAEBV0@@Z; AutoPtr<NtpPeer>::operator==(AutoPtr<NtpPeer> const &)
0x180035a84  test    eax, eax
0x180035a86  jnz     short loc_180035ABD
0x180035a88  xor     edx, edx
0x180035a8a  lea     rcx, [rsp+418h+var_398]
0x180035a92  call    ??0?$AutoPtr@UNtpPeer@@@@QEAA@PEAUNtpPeer@@@Z; AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(NtpPeer *)
0x180035a97  nop
0x180035a98  lea     rdx, [rsp+418h+var_398]
0x180035aa0  lea     rcx, [rsp+418h+var_3C0]
0x180035aa5  call    ??4?$AutoPtr@UNtpPeer@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<NtpPeer>::operator=(AutoPtr<NtpPeer> const &)
0x180035aaa  nop
0x180035aab  lea     rcx, [rsp+418h+var_398]
0x180035ab3  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x180035ab8  mov     rbx, [rsp+418h+var_3C0]
0x180035abd  lea     rcx, [rsp+418h+var_360]
0x180035ac5  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x180035aca  mov     r9, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180035ad1  jmp     short loc_180035AF9
0x180035ad3  mov     [rsp+418h+var_398], r8
0x180035adb  add     r8, 8
0x180035adf  mov     [rsp+418h+var_320], r8
0x180035ae7  mov     rax, qword ptr [rsp+418h+DestinationString.Length]
0x180035aef  jmp     loc_1800359EC
0x180035af4  mov     rbx, [rsp+418h+var_3C0]
0x180035af9  test    rbx, rbx
0x180035afc  jz      short loc_180035B0B
0x180035afe  cmp     [rbx+8], r14
0x180035b02  jz      short loc_180035B0B
0x180035b04  mov     ecx, 6Ah ; 'j'
0x180035b09  jmp     short loc_180035B2F
0x180035b0b  cmp     [rsp+418h+var_3C8], r14b
0x180035b10  jz      short loc_180035B2A
0x180035b12  lea     rcx, [r9+148h]; lpCriticalSection
0x180035b19  call    cs:__imp_LeaveCriticalSection
0x180035b20  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
