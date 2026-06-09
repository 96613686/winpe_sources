# HandleIncomingPacket(AuthType,uchar *,uint,sockaddr_storage *,uint,char *,ulong,NtTimeEpoch *,__int64 *,unsigned __int64 *)

- ea: `0x18001bdb0`
- end: `0x18001d992`
- name: `?HandleIncomingPacket@@YAJW4AuthType@@PEAEIPEAUsockaddr_storage@@IPEADKPEAUNtTimeEpoch@@PEA_JPEA_K@Z`
- size: `7138`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *, unsigned int, __int64, unsigned int, __int64, unsigned int, const WCHAR *, __int64 *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003784c`

## callees

- `0x18000a7e0`
- `0x180014718`
- `0x180014774`
- `0x1800164b0`
- `0x180018138`
- `0x180018dfc`
- `0x18001a780`
- `0x18001ab1c`
- `0x18001ab6c`
- `0x18001ae80`
- `0x18001b170`
- `0x18001bb4c`
- `0x18001bdb0`
- `0x18001d9a0`
- `0x18002c918`
- `0x18002cc6c`
- `0x18002d518`
- `0x18002e768`
- `0x180034e9c`
- `0x18003d270`
- `0x18003dd2c`
- `0x18003f485`
- `0x180041fc8`
- `0x180042000`
- `0x180042044`
- `0x180042108`
- `0x1800425ec`
- `0x1800456c8`
- `0x180046f8c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001bec0`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001d8c7`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001bec0`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001d8c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c8bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d625`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d92a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c8bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d625`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d92a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d943`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d3d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d3d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c024`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c26a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c695`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c75c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d273`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d775`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d8f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d911`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c024`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c26a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c695`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c75c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d273`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d775`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d8f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d911`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001befe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c101`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c537`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cffb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d2b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001befe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c101`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c537`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cffb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d2b7`
- `logoncli!I_NetlogonComputeClientDigest` at `0x18001c068`
- `logoncli!I_NetlogonComputeClientDigest` at `0x18001c068`
- `logoncli!I_NetlogonComputeClientSignature` at `0x18001c0dc`
- `logoncli!I_NetlogonComputeClientSignature` at `0x18001c0dc`
- `ntdll!RtlInitUnicodeString` at `0x18001c867`
- `ntdll!RtlInitUnicodeString` at `0x18001c87e`
- `ntdll!RtlInitUnicodeString` at `0x18001c9a7`
- `ntdll!RtlInitUnicodeString` at `0x18001cb5e`
- `ntdll!RtlInitUnicodeString` at `0x18001cd14`
- `ntdll!RtlInitUnicodeString` at `0x18001d5b2`
- `ntdll!RtlInitUnicodeString` at `0x18001c867`
- `ntdll!RtlInitUnicodeString` at `0x18001c87e`
- `ntdll!RtlInitUnicodeString` at `0x18001c9a7`
- `ntdll!RtlInitUnicodeString` at `0x18001cb5e`
- `ntdll!RtlInitUnicodeString` at `0x18001cd14`
- `ntdll!RtlInitUnicodeString` at `0x18001d5b2`
- `WS2_32!__imp_sendto` at `0x18001c6d7`
- `WS2_32!__imp_sendto` at `0x18001d7ac`
- `WS2_32!__imp_sendto` at `0x18001c6d7`
- `WS2_32!__imp_sendto` at `0x18001d7ac`
- `WS2_32!__imp_WSAGetLastError` at `0x18001c6ea`
- `WS2_32!__imp_WSAGetLastError` at `0x18001d7bd`
- `WS2_32!__imp_WSAGetLastError` at `0x18001c6ea`
- `WS2_32!__imp_WSAGetLastError` at `0x18001d7bd`

## string_xrefs

- `0x18001c2b5`: `ListeningThread STC:%I64u\n`
- `0x18001c823`: `Logging warning: NtpClient encountered an error while validating the computer account for this machine, so NtpClient cannot determine whether the response received from %s has a valid signature. The response will be ignored. The error was: %s\n`
- `0x18001c8d6`: `Can't verify packet because compute digest failed. Ignoring packet.\n`
- `0x18001cdf5`: `Ignoring packet invalid mode combination (in:%d out:%d).\n`
- `0x18001d077`: `  Considering peer=%s with peertype=%d.\n`
- `0x18001d331`: ` has exceeded cache limit (%d). Could not remove any stale host entries.\n.`
- `0x18001d3a6`: ` has exceeded cache limit (%d). Entries were removed, but none for this host.\n.`
- `0x18001d60b`: `RODC: could not fwd incoming signature pkt to downlevel DC %s because client's RID (0x%x(%d))has TRUST_RID_OLD_DIGEST_BIT bit set\n`
- `0x18001d866`: `ListeningThread -- demobilize long term peer (NYI).\n`
- `0x18001d882`: `Ignoring packet that would create dynamic peer\n`
- `0x18001d89a`: `ListeningThread -- save response from new long term peer (NYI)\n`

## pseudocode

```c
__int64 __fastcall HandleIncomingPacket(
        unsigned int a1,
        unsigned __int8 *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        const WCHAR *a8,
        __int64 *a9,
        struct _LIST_ENTRY *a10)
{
  PCWSTR v12; // rbx
  __int64 v13; // rsi
  _NtpProvState *v14; // rdi
  volatile signed __int32 *i; // rbx
  __int64 v16; // r8
  __int16 v17; // ax
  int v18; // eax
  __int64 v19; // rdx
  volatile signed __int32 *v20; // rbx
  _NtpProvState *v21; // rax
  volatile signed __int32 *v22; // r8
  _NtpProvState *v23; // r9
  struct sockaddr_storage *v24; // r10
  __int64 v25; // rax
  char v26; // al
  char v27; // al
  unsigned int v28; // ecx
  unsigned __int8 v29; // al
  __int64 v30; // rcx
  unsigned int v31; // edx
  unsigned __int8 v32; // cl
  bool v33; // al
  char v34; // al
  bool v35; // cl
  _NtpProvState *v36; // r8
  struct _LIST_ENTRY *v37; // r14
  SOCKET v38; // rdi
  _NtpProvState *v39; // rcx
  int v40; // r8d
  unsigned int v41; // ebx
  int v42; // r10d
  int v43; // ecx
  unsigned int v44; // eax
  char v45; // al
  WCHAR *v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rdx
  const wchar_t *v49; // r8
  __int64 v50; // rax
  __int64 v51; // rdx
  const wchar_t *v52; // r8
  int v53; // eax
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rax
  int v57; // ebx
  _BOOL8 v58; // r9
  int v59; // eax
  __int64 v60; // rcx
  _NtpProvState *v61; // r14
  __int64 v62; // rbx
  volatile signed __int32 *v63; // rdi
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rax
  struct sockaddr *v68; // rbx
  __int64 v69; // rcx
  int v70; // r14d
  _QWORD *v71; // rax
  _QWORD *v72; // rbx
  unsigned int v73; // r14d
  _OWORD *v74; // rax
  unsigned int v75; // edi
  int v76; // r14d
  char *v77; // rax
  _NtpProvState **v78; // rdx
  _NtpProvState *v79; // rax
  char v81; // [rsp+50h] [rbp-3A8h]
  char v82; // [rsp+51h] [rbp-3A7h]
  bool v83; // [rsp+52h] [rbp-3A6h]
  signed int dwMessageId; // [rsp+58h] [rbp-3A0h]
  DWORD dwMessageIda; // [rsp+58h] [rbp-3A0h]
  DWORD dwMessageIdb; // [rsp+58h] [rbp-3A0h]
  volatile signed __int32 *v87; // [rsp+60h] [rbp-398h] BYREF
  unsigned int v88; // [rsp+68h] [rbp-390h]
  volatile signed __int32 *v89; // [rsp+70h] [rbp-388h] BYREF
  __int64 v90; // [rsp+78h] [rbp-380h] BYREF
  PCWSTR SourceString; // [rsp+80h] [rbp-378h] BYREF
  int v92; // [rsp+88h] [rbp-370h]
  int v93; // [rsp+8Ch] [rbp-36Ch]
  _NtpProvState *v94; // [rsp+90h] [rbp-368h] BYREF
  struct _LIST_ENTRY *v95; // [rsp+98h] [rbp-360h] BYREF
  unsigned int v96; // [rsp+A0h] [rbp-358h] BYREF
  unsigned int v97; // [rsp+A4h] [rbp-354h] BYREF
  struct _UNICODE_STRING v98; // [rsp+A8h] [rbp-350h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-340h] BYREF
  _OWORD *v100; // [rsp+C8h] [rbp-330h]
  HLOCAL hMem; // [rsp+D0h] [rbp-328h] BYREF
  HLOCAL v102; // [rsp+D8h] [rbp-320h] BYREF
  volatile signed __int32 *v103; // [rsp+E0h] [rbp-318h] BYREF
  _QWORD v104[2]; // [rsp+E8h] [rbp-310h] BYREF
  volatile signed __int32 *v105; // [rsp+F8h] [rbp-300h]
  __int64 v106; // [rsp+100h] [rbp-2F8h]
  __int64 v107; // [rsp+108h] [rbp-2F0h]
  struct _UNICODE_STRING v108; // [rsp+110h] [rbp-2E8h] BYREF
  struct _UNICODE_STRING v109; // [rsp+120h] [rbp-2D8h] BYREF
  struct _UNICODE_STRING v110; // [rsp+130h] [rbp-2C8h] BYREF
  struct _UNICODE_STRING v111; // [rsp+140h] [rbp-2B8h] BYREF
  int v112; // [rsp+190h] [rbp-268h] BYREF
  char v113; // [rsp+194h] [rbp-264h]
  unsigned int v114; // [rsp+198h] [rbp-260h]
  unsigned __int8 v115; // [rsp+19Ch] [rbp-25Ch]
  unsigned __int8 v116; // [rsp+19Dh] [rbp-25Bh]
  char v117; // [rsp+19Eh] [rbp-25Ah]
  __int64 v118; // [rsp+1A0h] [rbp-258h]
  __int64 v119; // [rsp+1A8h] [rbp-250h]
  int v120; // [rsp+1B0h] [rbp-248h]
  __int64 v121; // [rsp+1B8h] [rbp-240h]
  __int64 v122; // [rsp+1C0h] [rbp-238h]
  __int64 v123; // [rsp+1C8h] [rbp-230h]
  __int64 v124; // [rsp+1D0h] [rbp-228h]
  __int64 v125; // [rsp+1D8h] [rbp-220h]
  __int64 v126; // [rsp+1E0h] [rbp-218h]
  __int64 v127; // [rsp+1E8h] [rbp-210h]
  struct _LIST_ENTRY *Flink; // [rsp+208h] [rbp-1F0h]
  __int64 v129; // [rsp+210h] [rbp-1E8h]
  int v130; // [rsp+218h] [rbp-1E0h]
  int v131; // [rsp+21Ch] [rbp-1DCh]
  int v132; // [rsp+220h] [rbp-1D8h]
  int v133; // [rsp+224h] [rbp-1D4h]
  int v134; // [rsp+228h] [rbp-1D0h]
  unsigned int v135; // [rsp+22Ch] [rbp-1CCh]
  char v136; // [rsp+238h] [rbp-1C0h]
  char v137; // [rsp+239h] [rbp-1BFh]
  bool v138; // [rsp+23Ah] [rbp-1BEh]
  bool v139; // [rsp+23Bh] [rbp-1BDh]
  char v140; // [rsp+23Ch] [rbp-1BCh]
  _OWORD v141[3]; // [rsp+240h] [rbp-1B8h] BYREF
  int v142; // [rsp+270h] [rbp-188h]
  struct sockaddr to; // [rsp+290h] [rbp-168h] BYREF
  struct _LIST_ENTRY v144; // [rsp+2A0h] [rbp-158h]
  struct _LIST_ENTRY v145; // [rsp+2B0h] [rbp-148h]
  struct _LIST_ENTRY v146; // [rsp+2C0h] [rbp-138h]
  struct _LIST_ENTRY v147; // [rsp+2D0h] [rbp-128h]
  struct _LIST_ENTRY v148; // [rsp+2E0h] [rbp-118h]
  struct _LIST_ENTRY v149; // [rsp+2F0h] [rbp-108h]
  struct _LIST_ENTRY v150; // [rsp+300h] [rbp-F8h]
  struct sockaddr v151; // [rsp+310h] [rbp-E8h] BYREF
  __int128 v152; // [rsp+320h] [rbp-D8h]
  __int128 v153; // [rsp+330h] [rbp-C8h]
  __int128 v154; // [rsp+340h] [rbp-B8h]
  __int128 v155; // [rsp+350h] [rbp-A8h]
  __int128 v156; // [rsp+360h] [rbp-98h]
  __int128 v157; // [rsp+370h] [rbp-88h]
  __int128 v158; // [rsp+380h] [rbp-78h]
  _BYTE Buf1[16]; // [rsp+390h] [rbp-68h] BYREF
  _BYTE v160[16]; // [rsp+3A0h] [rbp-58h] BYREF

  *(_QWORD *)&DestinationString.Length = a4;
  v88 = a3;
  *(_QWORD *)&v98.Length = a6;
  v12 = a8;
  SourceString = a8;
  v95 = a10;
  v83 = *((_BYTE *)g_pnpstate + 49) == 1 && (*((_BYTE *)g_pnpstate + 144) & 4) != 0;
  dwMessageId = 50;
  v13 = 0;
  v90 = 0;
  v14 = g_pnpstate;
  v94 = g_pnpstate;
  hMem = 0;
  v96 = 0;
  v102 = 0;
  v97 = 0;
  v104[0] = 0;
  memset_0(&v112, 0, 0xB0u);
  (*((void (__fastcall **)(__int64, _QWORD *))v14 + 2))(3, v104);
  v81 = 0;
  v82 = 0;
  v107 = _set_se_translator(SeTransFunc);
  if ( *((_BYTE *)g_pnpstate + 49) == 1 && (*a2 & 7) != 3 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
    v81 = 1;
    for ( i = (volatile signed __int32 *)*((_QWORD *)v14 + 51); ; i += 2 )
    {
      v104[1] = i;
      v89 = (volatile signed __int32 *)*((_QWORD *)v14 + 52);
      if ( i == v89 )
        break;
      v16 = *(_QWORD *)(*(_QWORD *)i + 8LL);
      if ( *(_QWORD *)(v16 + 272) == *(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * v88)
        && *(_DWORD *)(v16 + 264) == a5
        && *(_WORD *)(v16 + 138) == *(_WORD *)(*(_QWORD *)&DestinationString.Length + 2LL) )
      {
        v17 = **(_WORD **)&DestinationString.Length;
        if ( *(_WORD *)(v16 + 136) == 23 )
        {
          if ( v17 == 23
            && *(_DWORD *)(v16 + 160) == *(_DWORD *)(*(_QWORD *)&DestinationString.Length + 24LL)
            && *(_QWORD *)(v16 + 152) == *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 16LL)
            && *(_QWORD *)(v16 + 144) == *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 8LL) )
          {
            goto LABEL_20;
          }
        }
        else if ( v17 == 2 && *(_DWORD *)(v16 + 140) == *(_DWORD *)(*(_QWORD *)&DestinationString.Length + 4LL) )
        {
LABEL_20:
          if ( *(_QWORD *)i )
          {
            v13 = *(_QWORD *)i;
            v90 = v13;
            if ( v13 )
              _InterlockedIncrement((volatile signed __int32 *)v13);
          }
          break;
        }
      }
      v89 = i;
    }
    if ( a1 )
    {
      if ( !v13 )
        goto LABEL_50;
      if ( *(_QWORD *)(v13 + 8) )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
        if ( a1 == 1 )
        {
          v18 = I_NetlogonComputeClientDigest(0, *(_QWORD *)(*(_QWORD *)(v13 + 8) + 96LL), a2, 48, Buf1, v160);
        }
        else
        {
          v92 = 0;
          if ( a2[52] == 1 )
            v18 = I_NetlogonComputeClientSignature(
                    0,
                    *(_QWORD *)(*(_QWORD *)(v13 + 8) + 96LL),
                    1,
                    a2,
                    48,
                    &hMem,
                    &v96,
                    &v102,
                    &v97);
          else
            v18 = 50;
        }
        v92 = v18;
        dwMessageId = v18;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
        v81 = 1;
        v20 = 0;
        v103 = 0;
        v21 = v94;
        v22 = (volatile signed __int32 *)*((_QWORD *)v94 + 51);
        v105 = v22;
        v23 = g_pnpstate;
        v24 = *(struct sockaddr_storage **)&DestinationString.Length;
        while ( 1 )
        {
          v89 = (volatile signed __int32 *)*((_QWORD *)v21 + 52);
          if ( v22 == v89 )
            break;
          v19 = *(_QWORD *)(*(_QWORD *)v22 + 8LL);
          if ( *(_QWORD *)(v19 + 272) == *(_QWORD *)(*((_QWORD *)v23 + 8) + 8LL * v88)
            && *(_DWORD *)(v19 + 264) == a5
            && IsAddrEqual((struct sockaddr_storage *)(v19 + 136), v24) )
          {
            AutoPtr<NtpPeer>::operator=(&v103, v22);
            v20 = v103;
            break;
          }
          v89 = v22;
          v22 += 2;
          v105 = v22;
          v21 = v94;
        }
        if ( !v20 || (v25 = *((_QWORD *)v20 + 1)) == 0 || *(_QWORD *)(v13 + 8) != v25 )
        {
          AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v89, 0);
          AutoPtr<NtpPeer>::operator=(&v90, &v89);
          AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v89);
          v13 = v90;
        }
        if ( v20 && _InterlockedExchangeAdd(v20, 0xFFFFFFFF) == 1 )
          Ref<NtpPeer>::`scalar deleting destructor'(v20, v19);
      }
    }
    if ( v13 && *(_QWORD *)(v13 + 8) )
    {
      v26 = FileLogAllowEntry(106);
      v12 = SourceString;
      if ( !v26 )
        goto LABEL_52;
LABEL_51:
      FileLogNtpPacket(a2, *(_QWORD *)v12);
LABEL_52:
      if ( (unsigned __int8)FileLogAllowEntry(120) )
        FileLogAdd(L"ListeningThread STC:%I64u\n", v95->Flink);
      goto LABEL_56;
    }
LABEL_50:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
    v81 = 0;
    v27 = FileLogAllowEntry(115);
    v12 = SourceString;
    if ( !v27 )
      goto LABEL_52;
    goto LABEL_51;
  }
  if ( (unsigned __int8)FileLogAllowEntry(118) )
    FileLogNtpPacket(a2, *(_QWORD *)a8);
LABEL_56:
  v135 = a1;
  v140 = 1;
  v137 = 0;
  v136 = 0;
  v138 = 0;
  v139 = 0;
  v28 = *a2;
  v29 = ((unsigned __int8)v28 >> 3) & 7;
  if ( !v29 )
  {
    if ( !(unsigned __int8)FileLogAllowEntry(14) )
      goto LABEL_65;
    goto LABEL_58;
  }
  if ( v29 <= 4u )
  {
    v113 = ((unsigned __int8)v28 >> 3) & 7;
    if ( (unsigned __int8)((v28 & 7) - 1) <= 3u )
    {
      v112 = v28 & 7;
      v114 = v28 >> 6;
      v115 = a2[1];
      v32 = a2[2];
      v33 = (unsigned __int8)(v32 - 4) <= 0xDu || !v32;
      v139 = v33;
      v116 = v32;
      v34 = a2[3];
      v35 = v34 <= -3 || !v34;
      v138 = v35;
      v117 = v34;
      v120 = *((_DWORD *)a2 + 3);
      v118 = NtTimeOffsetFromNtpTimeOffset(*((unsigned int *)a2 + 1));
      v119 = NtTimePeriodFromNtpTimePeriod(*((unsigned int *)a2 + 2));
      v121 = NtTimeEpochFromNtpTimeEpoch(*((_QWORD *)a2 + 2));
      v122 = NtTimeEpochFromNtpTimeEpoch(*((_QWORD *)a2 + 3));
      v123 = *((_QWORD *)a2 + 3);
      v124 = NtTimeEpochFromNtpTimeEpoch(*((_QWORD *)a2 + 4));
      v125 = NtTimeEpochFromNtpTimeEpoch(*((_QWORD *)a2 + 5));
      v126 = *((_QWORD *)a2 + 5);
      v127 = *(_QWORD *)v12;
      v30 = *a9;
      v129 = *a9;
      Flink = v95->Flink;
      v140 = 0;
      goto LABEL_77;
    }
    if ( (unsigned __int8)FileLogAllowEntry(14) )
      FileLogAdd(L"Rejecting packet w/ bad mode\n");
  }
  else if ( (unsigned __int8)FileLogAllowEntry(14) )
  {
LABEL_58:
    FileLogAdd(L"Rejecting packet w/ bad version\n");
  }
LABEL_65:
  if ( v140 == 1 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(14) )
      FileLogAdd(L"Ignoring garbage packet.\n");
    goto LABEL_279;
  }
LABEL_77:
  v36 = g_pnpstate;
  if ( !*((_BYTE *)g_pnpstate + 548) && *((_BYTE *)g_pnpstate + 508) && (*a2 & 7) == 4 )
  {
    v95 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
    if ( (unsigned __int8)FileLogAllowEntry(131) )
      FileLogAdd(L"RODC: Checking for table entry.\n");
    ChainTableDump();
    if ( ChainTableContainsEntry(*((_DWORD *)a2 + 12), (struct NtpTimeEpoch *)(a2 + 24), (struct RodcCacheEntry **)&v95) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"RODC: Forwarding response to client ");
      v37 = v95;
      FileLogSockaddrInEx2(
        1,
        (struct sockaddr *)&v95[1],
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * SLODWORD(v95[9].Flink)) + 128LL));
      FileLogAppend(L"\n");
      memset_0(&to, 0, 0x80u);
      v38 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8LL * SLODWORD(v37[9].Flink)) + 136LL);
      to = (struct sockaddr)v37[1];
      v144 = v37[2];
      v145 = v37[3];
      v146 = v37[4];
      v147 = v37[5];
      v148 = v37[6];
      v149 = v37[7];
      v150 = v37[8];
      ChainTableRemoveEntry(v37);
      v39 = g_pnpstate;
      ++*((_DWORD *)g_pnpstate + 125);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v39 + 368));
      v82 = 0;
      v40 = 68;
      if ( a1 != 1 )
        v40 = 120;
      v41 = sendto(v38, (const char *)a2, v40, 0, &to, 128);
      if ( v41 == -1 )
      {
        WSAGetLastError();
        if ( (unsigned __int8)FileLogAllowEntry(2) )
          FileLogAdd(L"RODC: Logging information: NtpClient got SOCKET_ERROR sending response to client.\n");
      }
      else if ( (unsigned __int8)FileLogAllowEntry(131) )
      {
        FileLogAdd(L"RODC: response (0x%x bytes) sent to client.\n", v41);
      }
      goto LABEL_279;
    }
    if ( (unsigned __int8)FileLogAllowEntry(131) )
      FileLogAdd(L"RODC: No matching table entry. Processing locally.\n");
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
    v82 = 0;
    v36 = g_pnpstate;
  }
  if ( a1 )
  {
    if ( (unsigned int)operator!=(v30, &v90) )
    {
      v43 = *(_DWORD *)(*(_QWORD *)(v13 + 8) + 56LL);
      v131 = v43;
      if ( v43 )
      {
        v44 = dwMessageId;
        if ( dwMessageId )
        {
          if ( dwMessageId > 0 )
            v44 = (unsigned __int16)dwMessageId | 0x80070000;
          SourceString = 0;
          if ( (int)GetSystemErrorString(v44, (unsigned __int16 **)&SourceString) >= 0 )
          {
            *(_DWORD *)(*(_QWORD *)(v13 + 8) + 1528LL) = -2147467259;
            *(_DWORD *)(*(_QWORD *)(v13 + 8) + 1532LL) = 105;
            v45 = FileLogAllowEntry(7);
            v46 = (WCHAR *)SourceString;
            if ( v45 )
              FileLogAdd(
                L"Logging warning: NtpClient encountered an error while validating the computer account for this machine, "
                 "so NtpClient cannot determine whether the response received from %s has a valid signature. The response"
                 " will be ignored. The error was: %s\n",
                *(_QWORD *)(*(_QWORD *)(v13 + 8) + 88LL),
                SourceString);
            if ( (*((_DWORD *)g_pnpstate + 48) & 4) != 0 )
            {
              DestinationString = 0;
              v98 = 0;
              RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(*(_QWORD *)(v13 + 8) + 88LL));
              RtlInitUnicodeString(&v98, v46);
              LogEvent(
                &_W32TimeRegistrationHandle,
                W32TIME_EVENT_COMPUTE_CLIENT_DIGEST_FAILED,
                L"uu",
                &DestinationString);
            }
            LocalFree(v46);
          }
          if ( (unsigned __int8)FileLogAllowEntry(7) )
            FileLogAdd(L"Can't verify packet because compute digest failed. Ignoring packet.\n");
          goto LABEL_279;
        }
      }
      if ( v42 == 1 )
      {
        if ( memcmp_0(Buf1, a2 + 52, 0x10u) && memcmp_0(v160, a2 + 52, 0x10u) )
        {
          v47 = *(_QWORD *)(v13 + 8);
          if ( *(_BYTE *)(v47 + 118) )
          {
            *(_DWORD *)(v47 + 1528) = -2147467259;
            *(_DWORD *)(*(_QWORD *)(v13 + 8) + 1532LL) = 106;
            if ( (unsigned __int8)FileLogAllowEntry(7) )
              FileLogAdd(
                L"Logging warning: NtpClient: The response received from domain controller %s has an bad signature. The re"
                 "sponse may have been tampered with and will be ignored.\n",
                *(_QWORD *)(*(_QWORD *)(v13 + 8) + 88LL));
            if ( (*((_DWORD *)g_pnpstate + 48) & 4) != 0 )
            {
              v108 = 0;
              RtlInitUnicodeString(&v108, *(PCWSTR *)(*(_QWORD *)(v13 + 8) + 88LL));
              LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_BAD_SIGNATURE, L"u", &v108);
            }
            if ( (unsigned __int8)FileLogAllowEntry(7) )
              FileLogAdd(L"Digest shows packet tampered with. Ignoring packet.\n");
            *(_BYTE *)(*(_QWORD *)(v13 + 8) + 117LL) = 0;
          }
          else
          {
            if ( (unsigned __int8)FileLogAllowEntry(7) )
            {
              v48 = *(_QWORD *)(v13 + 8);
              v49 = L"TRUE";
              if ( !*(_BYTE *)(v48 + 117) )
                v49 = L"FALSE";
              FileLogAdd(
                L"Response received from domain controller %s failed to authenticate.  Using old server digest: %s.\n",
                *(_QWORD *)(v48 + 88),
                v49);
            }
            *(_BYTE *)(*(_QWORD *)(v13 + 8) + 118LL) = 1;
            *(_BYTE *)(*(_QWORD *)(v13 + 8) + 117LL) = *(_BYTE *)(*(_QWORD *)(v13 + 8) + 117LL) == 0;
          }
          goto LABEL_279;
        }
        if ( (unsigned __int8)FileLogAllowEntry(7) )
          FileLogAdd(
            L"Response received from domain controller %s authenticated successfully (using digest format)\n",
            *(_QWORD *)(*(_QWORD *)(v13 + 8) + 88LL));
LABEL_163:
        *(_BYTE *)(*(_QWORD *)(v13 + 8) + 118LL) = 0;
        v36 = g_pnpstate;
        goto LABEL_164;
      }
      if ( v42 == 2 )
      {
        if ( (v96 < 0x40 || memcmp_0(hMem, a2 + 56, 0x40u)) && (v97 < 0x40 || memcmp_0(v102, a2 + 56, 0x40u)) )
        {
          v50 = *(_QWORD *)(v13 + 8);
          if ( *(_BYTE *)(v50 + 118) )
          {
            *(_DWORD *)(v50 + 1528) = -2147467259;
            *(_DWORD *)(*(_QWORD *)(v13 + 8) + 1532LL) = 106;
            if ( (unsigned __int8)FileLogAllowEntry(7) )
              FileLogAdd(
                L"Logging warning: NtpClient: The response received from domain controller %s has an bad signature. The re"
                 "sponse may have been tampered with and will be ignored.\n",
                *(_QWORD *)(*(_QWORD *)(v13 + 8) + 88LL));
            if ( (*((_DWORD *)g_pnpstate + 48) & 4) != 0 )
            {
              v109 = 0;
              RtlInitUnicodeString(&v109, *(PCWSTR *)(*(_QWORD *)(v13 + 8) + 88LL));
              LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_BAD_SIGNATURE, L"u", &v109);
            }
            if ( (unsigned __int8)FileLogAllowEntry(7) )
              FileLogAdd(L"Digest shows packet tampered with. Ignoring packet.\n");
            *(_BYTE *)(*(_QWORD *)(v13 + 8) + 117LL) = 0;
          }
          else
          {
            if ( (unsigned __int8)FileLogAllowEntry(7) )
            {
              v51 = *(_QWORD *)(v13 + 8);
              v52 = L"TRUE";
              if ( !*(_BYTE *)(v51 + 117) )
                v52 = L"FALSE";
              FileLogAdd(
                L"Response received from domain controller %s failed to authenticate.  Using old server digest: %s.\n",
                *(_QWORD *)(v51 + 88),
                v52);
            }
            *(_BYTE *)(*(_QWORD *)(v13 + 8) + 118LL) = 1;
            *(_BYTE *)(*(_QWORD *)(v13 + 8) + 117LL) = *(_BYTE *)(*(_QWORD *)(v13 + 8) + 117LL) == 0;
          }
          goto LABEL_279;
        }
        if ( (unsigned __int8)FileLogAllowEntry(7) )
          FileLogAdd(
            L"Response received from domain controller %s authenticated successfully (using signature format)\n",
            *(_QWORD *)(*(_QWORD *)(v13 + 8) + 88LL));
        goto LABEL_163;
      }
      if ( !v43 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(7) )
          FileLogAdd(L"non-auth peer set authenticated packet!\n");
        goto LABEL_279;
      }
    }
    else
    {
      v53 = *((_DWORD *)a2 + 12);
      if ( a1 == 1 )
      {
        v131 = 1;
        v132 = v53;
      }
      else
      {
        v131 = 2;
        v132 = v53;
        v133 = a2[54] & 1;
        v134 = a2[53];
      }
    }
  }
  else
  {
    v131 = 0;
    if ( v13 )
    {
      v54 = *(_QWORD *)(v13 + 8);
      if ( v54 )
      {
        v55 = *(_DWORD *)(v54 + 56);
        if ( v55 )
        {
          if ( (unsigned int)(v55 - 1) <= 1 )
          {
            *(_DWORD *)(v54 + 1528) = -2147467259;
            *(_DWORD *)(*(_QWORD *)(v13 + 8) + 1532LL) = 107;
            if ( (unsigned __int8)FileLogAllowEntry(7) )
              FileLogAdd(
                L"Logging warning: NtpClient: The response received from domain controller %s is missing the signature. Th"
                 "e response may have been tampered with and will be ignored.\n",
                *(_QWORD *)(*(_QWORD *)(v13 + 8) + 88LL));
            if ( (*((_DWORD *)g_pnpstate + 48) & 4) != 0 )
            {
              v110 = 0;
              RtlInitUnicodeString(&v110, *(PCWSTR *)(*(_QWORD *)(v13 + 8) + 88LL));
              LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_MISSING_SIGNATURE, L"u", &v110);
            }
          }
          if ( (unsigned __int8)FileLogAllowEntry(7) )
            FileLogAdd(L"Unauthenticated packet recieved from authenticated peer.\n");
          goto LABEL_279;
        }
      }
    }
  }
LABEL_164:
  dwMessageIda = v112;
  if ( v13 && (v56 = *(_QWORD *)(v13 + 8)) != 0 )
  {
    v57 = *(_DWORD *)(v56 + 804);
    v58 = v83;
  }
  else
  {
    v58 = v83;
    if ( *((_BYTE *)v36 + 48) == 1 )
    {
      if ( v112 == 3 || (v57 = 2, !v83) )
        v57 = 4;
    }
    else
    {
      v57 = 0;
    }
  }
  v130 = v57;
  v59 = *((_DWORD *)&qword_180072230[4 * v112] + v57);
  if ( !v59 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(14) )
      FileLogAdd(L"Ignoring packet invalid mode combination (in:%d out:%d).\n", dwMessageIda, (unsigned int)v57);
    goto LABEL_279;
  }
  if ( v59 == 5 )
  {
    if ( *((_BYTE *)v36 + 168) != 1 )
    {
      if ( !(unsigned __int8)FileLogAllowEntry(14) )
        goto LABEL_279;
      goto LABEL_178;
    }
    goto LABEL_186;
  }
  if ( v59 != 6 )
  {
    if ( v59 == 3 )
    {
      if ( v136 != 1 || !v58 )
        goto LABEL_196;
    }
    else if ( v59 == 2 )
    {
      goto LABEL_196;
    }
LABEL_186:
    if ( v13 && *(_QWORD *)(v13 + 8) )
    {
      if ( !v139 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(14) )
          FileLogAdd(L"Rejecting packet w/ bad poll interval\n");
        goto LABEL_279;
      }
      if ( !v138 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(14) )
          FileLogAdd(L"Rejecting packet w/ bad precision\n");
        goto LABEL_279;
      }
      *(_QWORD *)&v98.Length = &v89;
      v89 = (volatile signed __int32 *)v13;
      _InterlockedIncrement((volatile signed __int32 *)v13);
      ParsePacket2(&v89, &v112, a2, v58);
      v95 = (struct _LIST_ENTRY *)&v94;
      v94 = (_NtpProvState *)v13;
      _InterlockedIncrement((volatile signed __int32 *)v13);
      ProcessPeerUpdate(&v94, &v112);
LABEL_278:
      _set_se_translator(v107);
      goto LABEL_279;
    }
    if ( v58 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(14) )
        FileLogAdd(L"ListeningThread -- save response from new long term peer (NYI)\n");
      goto LABEL_278;
    }
    if ( (unsigned __int8)FileLogAllowEntry(14) )
      FileLogAdd(L"Ignoring packet that would create dynamic peer\n");
LABEL_279:
    v73 = 0;
    if ( !v82 )
      goto LABEL_281;
    goto LABEL_280;
  }
  if ( *((_BYTE *)v36 + 259) != 1 )
  {
    if ( !(unsigned __int8)FileLogAllowEntry(14) )
      goto LABEL_279;
LABEL_178:
    FileLogAdd(L"Ignoring packet in nonstandard mode.\n");
    goto LABEL_279;
  }
LABEL_196:
  if ( !*((_BYTE *)v36 + 48) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(14) )
      FileLogAdd(L"Ignoring packet because server not running.\n");
    goto LABEL_279;
  }
  if ( g_ullNtpServerIncomingRequestRate != -1 )
    ++g_ullNtpServerIncomingRequestRate;
  if ( !TransmitResponse(
          (struct NtpSimplePeer *)&v112,
          *(struct sockaddr_storage **)&DestinationString.Length,
          a5,
          *(char **)&v98.Length,
          a7,
          *(struct NicSocket **)(*((_QWORD *)v36 + 8) + 8LL * v88)) )
  {
    if ( (unsigned int)operator!=(v60, &v90) && (unsigned __int8)FileLogAllowEntry(14) )
      FileLogAdd(L"ListeningThread -- demobilize long term peer (NYI).\n");
    goto LABEL_278;
  }
  AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v87, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v81 = 1;
  if ( (unsigned __int8)FileLogAllowEntry(131) )
    FileLogAdd(L"BEGIN: peer search for chaining.\n");
  v61 = v94;
  v62 = *((_QWORD *)v94 + 51);
  v106 = v62;
  v63 = v87;
  while ( 1 )
  {
    *(_QWORD *)&v98.Length = *((_QWORD *)v61 + 52);
    if ( v62 == *(_QWORD *)&v98.Length )
      break;
    if ( (unsigned __int8)FileLogAllowEntry(131) )
      FileLogAdd(
        L"  Considering peer=%s with peertype=%d.\n",
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v62 + 8LL) + 88LL),
        *(unsigned int *)(*(_QWORD *)(*(_QWORD *)v62 + 8LL) + 48LL));
    v64 = *(_QWORD *)(*(_QWORD *)v62 + 8LL);
    if ( *(_DWORD *)(v64 + 48) == 1 )
    {
      if ( a1 != 2 )
      {
        AutoPtr<NtpPeer>::operator=(&v87, v62);
        if ( (unsigned __int8)FileLogAllowEntry(131) )
          FileLogAdd(
            L"  Choosing peer=%s for chaining (digest mode).\n",
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v62 + 8LL) + 88LL));
        goto LABEL_214;
      }
      if ( *(_DWORD *)(v64 + 56) == 2 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(131) )
          FileLogAdd(
            L"  Choosing peer=%s for chaining (signature mode).\n",
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v62 + 8LL) + 88LL));
        AutoPtr<NtpPeer>::operator=(&v87, v62);
LABEL_214:
        v63 = v87;
        break;
      }
      if ( !v63 || !*((_QWORD *)v63 + 1) )
      {
        if ( (unsigned __int8)FileLogAllowEntry(131) )
          FileLogAdd(L"  Saving candidate downlevel peer=%s.\n", *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v62 + 8LL) + 88LL));
        AutoPtr<NtpPeer>::operator=(&v87, v62);
        v63 = v87;
      }
    }
    *(_QWORD *)&v98.Length = v62;
    v62 += 8;
    v106 = v62;
  }
  if ( (unsigned __int8)FileLogAllowEntry(131) )
    FileLogAdd(L"END: peer search for chaining.\n");
  if ( !v63 || !*((_QWORD *)v63 + 1) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(131) )
      FileLogAdd(L"Logging warning: Unable to locate an NT5DS Peer Chaining Deferred.\n");
    goto LABEL_269;
  }
  if ( (unsigned __int8)FileLogAllowEntry(131) )
  {
    v65 = AuthTypeToSz(*(unsigned int *)(*((_QWORD *)v63 + 1) + 56LL));
    FileLogAdd(L"RODC: Using Time Source %s (%s)\n", v66 + 290, v65);
  }
  if ( (unsigned __int8)FileLogAllowEntry(131) )
  {
    v67 = AuthTypeToSz(a1);
    FileLogAdd(L"RODC: Forwarding %s request from client ", v67);
  }
  v68 = *(struct sockaddr **)&DestinationString.Length;
  FileLogSockaddrInEx2(1, *(struct sockaddr **)&DestinationString.Length, a5);
  FileLogAppend(L" to server ");
  FileLogSockaddrInEx2(1, (struct sockaddr *)(*((_QWORD *)v63 + 1) + 136LL), 0x80u);
  FileLogAppend(L" \n");
  memset_0(&v151, 0, 0x80u);
  v69 = *((_QWORD *)v63 + 1);
  dwMessageIdb = *(_DWORD *)(v69 + 264);
  *(_QWORD *)&v98.Length = *(_QWORD *)(*(_QWORD *)(v69 + 272) + 136LL);
  v151 = *(struct sockaddr *)(v69 + 136);
  v152 = *(_OWORD *)(v69 + 152);
  v153 = *(_OWORD *)(v69 + 168);
  v154 = *(_OWORD *)(v69 + 184);
  v155 = *(_OWORD *)(v69 + 200);
  v156 = *(_OWORD *)(v69 + 216);
  v157 = *(_OWORD *)(v69 + 232);
  v158 = *(_OWORD *)(v69 + 248);
  v70 = *(_DWORD *)(*((_QWORD *)v63 + 1) + 56LL);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v81 = 0;
  memset_0(v141, 0, 0x48u);
  v100 = 0;
  v93 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
  v82 = 1;
  RemoveStaleEntries(0);
  if ( FailedSecurityCheck((struct sockaddr_storage *)v68) )
  {
    if ( !RemoveStaleEntries(1) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"RODC: Peer ");
      FileLogSockaddrInEx2(1, v68, a5);
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(
          L" has exceeded cache limit (%d). Could not remove any stale host entries.\n.",
          *((unsigned int *)g_pnpstate + 139));
LABEL_269:
      AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v87);
      goto LABEL_279;
    }
    if ( FailedSecurityCheck((struct sockaddr_storage *)v68) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"RODC: Peer ");
      FileLogSockaddrInEx2(1, v68, a5);
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(
          L" has exceeded cache limit (%d). Entries were removed, but none for this host.\n.",
          *((unsigned int *)g_pnpstate + 139));
      goto LABEL_269;
    }
  }
  v71 = LocalAlloc(0x40u, 0xB0u);
  v72 = v71;
  if ( v71 )
  {
    memset_0(v71, 0, 0xB0u);
    v72[19] = v104[0];
    v72[20] = *((_QWORD *)a2 + 5);
    *((_DWORD *)v72 + 36) = v88;
    v74 = *(_OWORD **)&DestinationString.Length;
    *((_OWORD *)v72 + 1) = *(_OWORD *)*(_QWORD *)&DestinationString.Length;
    *((_OWORD *)v72 + 2) = v74[1];
    *((_OWORD *)v72 + 3) = v74[2];
    *((_OWORD *)v72 + 4) = v74[3];
    *((_OWORD *)v72 + 5) = v74[4];
    *((_OWORD *)v72 + 6) = v74[5];
    *((_OWORD *)v72 + 7) = v74[6];
    *((_OWORD *)v72 + 8) = v74[7];
    if ( v70 == 1 || a1 == 1 )
    {
      v76 = *((_DWORD *)a2 + 12);
      if ( a1 == 2 )
      {
        if ( v76 < 0 )
        {
          v111 = 0;
          RtlInitUnicodeString(&v111, (PCWSTR)(*((_QWORD *)v63 + 1) + 290LL));
          LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_RODCUNABLETOFWDREQUEST, L"du", *((unsigned int *)a2 + 12));
          if ( (unsigned __int8)FileLogAllowEntry(6) )
            FileLogAdd(
              L"RODC: could not fwd incoming signature pkt to downlevel DC %s because client's RID (0x%x(%d))has TRUST_RID"
               "_OLD_DIGEST_BIT bit set\n",
              *((_QWORD *)v63 + 1) + 290LL,
              *((unsigned int *)a2 + 12),
              *((unsigned int *)a2 + 12),
              &v111);
          v73 = -2147467259;
          LocalFree(v72);
          AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v87);
          goto LABEL_280;
        }
        memset_0(v141, 0, 0x48u);
        v141[0] = *(_OWORD *)a2;
        v141[1] = *((_OWORD *)a2 + 1);
        v141[2] = *((_OWORD *)a2 + 2);
        v142 = v76;
        *((_DWORD *)v72 + 37) = v76;
        a2 = (unsigned __int8 *)v141;
        v100 = v141;
        v75 = 68;
        v93 = 68;
        if ( (unsigned __int8)FileLogAllowEntry(131) )
          FileLogAdd(L"RODC: downgrading client request from signature to digest format.\n");
      }
      else
      {
        v100 = a2;
        v75 = 68;
        v93 = 68;
        *((_DWORD *)v72 + 37) = v76;
        if ( (unsigned __int8)FileLogAllowEntry(131) )
          FileLogAdd(L"RODC: forwarding client's digest packet as-is.\n");
      }
      *((_DWORD *)v72 + 42) = 1;
    }
    else
    {
      v100 = a2;
      v75 = 120;
      v93 = 120;
      *((_DWORD *)v72 + 37) = *((_DWORD *)a2 + 12);
      *((_DWORD *)v72 + 42) = 1;
      if ( (unsigned __int8)FileLogAllowEntry(131) )
        FileLogAdd(L"RODC: forwarding client's signature packet as-is.\n");
    }
    if ( (unsigned __int8)FileLogAllowEntry(131) )
      FileLogAdd(L"RODC: Adding request to table : \n");
    v77 = (char *)g_pnpstate + 528;
    v78 = (_NtpProvState **)*((_QWORD *)g_pnpstate + 67);
    if ( *v78 != (_NtpProvState *)((char *)g_pnpstate + 528) )
      __fastfail(3u);
    *v72 = v77;
    v72[1] = v78;
    *v78 = (_NtpProvState *)v72;
    *((_QWORD *)v77 + 1) = v72;
    v79 = g_pnpstate;
    ++*((_DWORD *)g_pnpstate + 136);
    ++*((_DWORD *)v79 + 124);
    ChainTableDump();
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
    v82 = 0;
    if ( sendto(*(SOCKET *)&v98.Length, (const char *)a2, v75, 0, &v151, dwMessageIdb) == -1 )
    {
      WSAGetLastError();
      if ( (unsigned __int8)FileLogAllowEntry(2) )
        FileLogAdd(L"RODC: Logging information: NtpClient fails sending response to client.\n");
    }
    else if ( (unsigned __int8)FileLogAllowEntry(131) )
    {
      FileLogAdd(L"RODC: sent packet (0x%x(%d) bytes) to peer DC.\n", v75, v75);
    }
    goto LABEL_269;
  }
  v73 = -2147024882;
  AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v87);
LABEL_280:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 368));
LABEL_281:
  if ( v81 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  if ( hMem )
    LocalFree(hMem);
  if ( v102 )
    LocalFree(v102);
  if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 )
    Ref<NtpPeer>::`scalar deleting destructor'((_QWORD *)v13, v31);
  return v73;
}

```

## disassembly

```asm
0x18001bdb0  push    rbx
0x18001bdb2  push    rsi
0x18001bdb3  push    rdi
0x18001bdb4  push    r12
0x18001bdb6  push    r13
0x18001bdb8  push    r14
0x18001bdba  push    r15
0x18001bdbc  sub     rsp, 3C0h
0x18001bdc3  mov     rax, cs:__security_cookie
0x18001bdca  xor     rax, rsp
0x18001bdcd  mov     [rsp+3F8h+var_48], rax
0x18001bdd5  mov     qword ptr [rsp+3F8h+DestinationString.Length], r9
0x18001bddd  mov     [rsp+3F8h+var_390], r8d
0x18001bde2  mov     r12, rdx
0x18001bde5  mov     r13d, ecx
0x18001bde8  mov     rax, [rsp+3F8h+arg_28]
0x18001bdf0  mov     qword ptr [rsp+3F8h+var_350.Length], rax
0x18001bdf8  mov     rbx, [rsp+3F8h+arg_38]
0x18001be00  mov     [rsp+3F8h+SourceString], rbx
0x18001be08  mov     rax, [rsp+3F8h+arg_48]
0x18001be10  mov     [rsp+3F8h+var_360], rax
0x18001be18  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001be1f  cmp     byte ptr [rax+31h], 1
0x18001be23  jnz     short loc_18001BE35
0x18001be25  test    byte ptr [rax+90h], 4
0x18001be2c  jz      short loc_18001BE35
0x18001be2e  mov     [rsp+3F8h+var_3A6], 1
0x18001be33  jmp     short loc_18001BE3A
0x18001be35  mov     [rsp+3F8h+var_3A6], 0
0x18001be3a  mov     [rsp+3F8h+dwMessageId], 32h ; '2'
0x18001be42  xor     r15d, r15d
0x18001be45  mov     esi, r15d
0x18001be48  mov     [rsp+3F8h+var_380], r15
0x18001be4d  mov     rdi, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001be54  mov     [rsp+3F8h+var_368], rdi
0x18001be5c  mov     [rsp+3F8h+hMem], r15
0x18001be64  mov     [rsp+3F8h+var_358], r15d
0x18001be6c  mov     [rsp+3F8h+var_320], r15
0x18001be74  mov     [rsp+3F8h+var_354], r15d
0x18001be7c  mov     [rsp+3F8h+var_310], r15
0x18001be84  xor     edx, edx; Val
0x18001be86  mov     r8d, 0B0h; Size
0x18001be8c  lea     rcx, [rsp+3F8h+var_268]; void *
0x18001be94  call    memset_0
0x18001be99  lea     rdx, [rsp+3F8h+var_310]
0x18001bea1  mov     ecx, 3
0x18001bea6  mov     rax, [rdi+10h]
0x18001beaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beaf  mov     [rsp+3F8h+var_3A8], r15b
0x18001beb4  mov     [rsp+3F8h+var_3A7], r15b
0x18001beb9  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18001bec0  call    cs:__imp__set_se_translator
0x18001bec7  nop     dword ptr [rax+rax+00h]
0x18001becc  mov     [rsp+3F8h+var_2F0], rax
0x18001bed4  mov     r14d, r15d
0x18001bed7  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001bede  cmp     byte ptr [rcx+31h], 1
0x18001bee2  jnz     loc_18001C2C3
0x18001bee8  movzx   eax, byte ptr [r12]
0x18001beed  and     al, 7
0x18001beef  cmp     al, 3
0x18001bef1  jz      loc_18001C2C3
0x18001bef7  add     rcx, 148h; lpCriticalSection
0x18001befe  call    cs:__imp_EnterCriticalSection
0x18001bf05  nop     dword ptr [rax+rax+00h]
0x18001bf0a  mov     [rsp+3F8h+var_3A8], 1
0x18001bf0f  mov     rbx, [rdi+198h]
0x18001bf16  mov     r10d, [rsp+3F8h+var_390]
0x18001bf1b  mov     r11d, [rsp+3F8h+arg_20]
0x18001bf23  mov     [rsp+3F8h+var_308], rbx
0x18001bf2b  mov     rax, [rdi+1A0h]
0x18001bf32  mov     [rsp+3F8h+var_388], rax
0x18001bf37  cmp     rbx, rax
0x18001bf3a  jz      loc_18001BFF4
0x18001bf40  mov     r9, [rbx]
0x18001bf43  mov     r8, [r9+8]
0x18001bf47  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001bf4e  mov     rcx, [rax+40h]
0x18001bf52  mov     rax, [rcx+r10*8]
0x18001bf56  cmp     [r8+110h], rax
0x18001bf5d  jnz     short loc_18001BFB8
0x18001bf5f  cmp     [r8+108h], r11d
0x18001bf66  jnz     short loc_18001BFB8
0x18001bf68  mov     rcx, qword ptr [rsp+3F8h+DestinationString.Length]
0x18001bf70  movzx   eax, word ptr [rcx+2]
0x18001bf74  cmp     [r8+8Ah], ax
0x18001bf7c  jnz     short loc_18001BFB8
0x18001bf7e  movzx   eax, word ptr [rcx]
0x18001bf81  cmp     word ptr [r8+88h], 17h
0x18001bf8a  jnz     short loc_18001BFC6
0x18001bf8c  cmp     ax, 17h
0x18001bf90  jnz     short loc_18001BFB8
0x18001bf92  mov     eax, [rcx+18h]
0x18001bf95  cmp     [r8+0A0h], eax
0x18001bf9c  jnz     short loc_18001BFB8
0x18001bf9e  mov     rax, [rcx+10h]
0x18001bfa2  cmp     [r8+98h], rax
0x18001bfa9  jnz     short loc_18001BFB8
0x18001bfab  mov     rax, [rcx+8]
0x18001bfaf  cmp     [r8+90h], rax
0x18001bfb6  jz      short loc_18001BFD8
0x18001bfb8  mov     [rsp+3F8h+var_388], rbx
0x18001bfbd  add     rbx, 8
0x18001bfc1  jmp     loc_18001BF23
0x18001bfc6  cmp     ax, 2
0x18001bfca  jnz     short loc_18001BFB8
0x18001bfcc  mov     eax, [rcx+4]
0x18001bfcf  cmp     [r8+8Ch], eax
0x18001bfd6  jnz     short loc_18001BFB8
0x18001bfd8  cmp     r15, r9
0x18001bfdb  jz      short loc_18001BFF4
0x18001bfdd  mov     edi, 0FFFFFFFFh
0x18001bfe2  mov     rsi, [rbx]
0x18001bfe5  mov     [rsp+3F8h+var_380], rsi
0x18001bfea  test    rsi, rsi
0x18001bfed  jz      short loc_18001BFF9
0x18001bfef  lock inc dword ptr [rsi]
0x18001bff2  jmp     short loc_18001BFF9
0x18001bff4  mov     edi, 0FFFFFFFFh
0x18001bff9  test    r13d, r13d
0x18001bffc  jz      loc_18001C231
0x18001c002  test    rsi, rsi
0x18001c005  jz      loc_18001C255
0x18001c00b  cmp     qword ptr [rsi+8], 0
0x18001c010  jz      loc_18001C231
0x18001c016  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001c01d  add     rcx, 148h; lpCriticalSection
0x18001c024  call    cs:__imp_LeaveCriticalSection
0x18001c02b  nop     dword ptr [rax+rax+00h]
0x18001c030  mov     [rsp+3F8h+var_3A8], 0
0x18001c035  cmp     r13d, 1
0x18001c039  jnz     short loc_18001C076
0x18001c03b  mov     rdx, [rsi+8]
0x18001c03f  lea     rax, [rsp+3F8h+var_58]
0x18001c047  mov     qword ptr [rsp+3F8h+tolen], rax
0x18001c04c  lea     rax, [rsp+3F8h+Buf1]
0x18001c054  mov     [rsp+3F8h+to], rax
0x18001c059  mov     r9d, 30h ; '0'
0x18001c05f  mov     r8, r12
0x18001c062  mov     rdx, [rdx+60h]
0x18001c066  xor     ecx, ecx
0x18001c068  call    cs:__imp_I_NetlogonComputeClientDigest
0x18001c06f  nop     dword ptr [rax+rax+00h]
0x18001c074  jmp     short loc_18001C0E8
0x18001c076  mov     [rsp+3F8h+var_370], r15d
0x18001c07e  cmp     byte ptr [r12+34h], 1
0x18001c084  jz      short loc_18001C08D
0x18001c086  mov     eax, 32h ; '2'
0x18001c08b  jmp     short loc_18001C0E8
0x18001c08d  mov     rdx, [rsi+8]
0x18001c091  lea     rax, [rsp+3F8h+var_354]
0x18001c099  mov     [rsp+3F8h+var_3B8], rax
0x18001c09e  lea     rax, [rsp+3F8h+var_320]
0x18001c0a6  mov     [rsp+3F8h+var_3C0], rax
0x18001c0ab  lea     rax, [rsp+3F8h+var_358]
0x18001c0b3  mov     [rsp+3F8h+var_3C8], rax
0x18001c0b8  lea     rax, [rsp+3F8h+hMem]
0x18001c0c0  mov     qword ptr [rsp+3F8h+tolen], rax
0x18001c0c5  mov     dword ptr [rsp+3F8h+to], 30h ; '0'
0x18001c0cd  mov     r9, r12
0x18001c0d0  mov     r8d, 1
0x18001c0d6  mov     rdx, [rdx+60h]
0x18001c0da  xor     ecx, ecx
0x18001c0dc  call    cs:__imp_I_NetlogonComputeClientSignature
0x18001c0e3  nop     dword ptr [rax+rax+00h]
0x18001c0e8  mov     [rsp+3F8h+var_370], eax
0x18001c0ef  mov     [rsp+3F8h+dwMessageId], eax
0x18001c0f3  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001c0fa  add     rcx, 148h; lpCriticalSection
0x18001c101  call    cs:__imp_EnterCriticalSection
0x18001c108  nop     dword ptr [rax+rax+00h]
0x18001c10d  mov     [rsp+3F8h+var_3A8], 1
0x18001c112  mov     rbx, r15
0x18001c115  mov     [rsp+3F8h+var_318], rbx
0x18001c11d  mov     rax, [rsp+3F8h+var_368]
0x18001c125  mov     r8, [rax+198h]
0x18001c12c  mov     [rsp+3F8h+var_300], r8
0x18001c134  mov     r9, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001c13b  mov     r10, qword ptr [rsp+3F8h+DestinationString.Length]
0x18001c143  mov     rax, [rax+1A0h]
0x18001c14a  mov     [rsp+3F8h+var_388], rax
0x18001c14f  cmp     r8, rax
0x18001c152  jz      short loc_18001C1AA
0x18001c154  mov     rax, [r8]
0x18001c157  mov     rdx, [rax+8]
0x18001c15b  mov     ecx, [rsp+3F8h+var_390]
0x18001c15f  mov     rax, [r9+40h]
0x18001c163  mov     rcx, [rax+rcx*8]
0x18001c167  cmp     [rdx+110h], rcx
0x18001c16e  jnz     short loc_18001C1C5
0x18001c170  mov     eax, [rsp+3F8h+arg_20]
0x18001c177  cmp     [rdx+108h], eax
0x18001c17d  jnz     short loc_18001C1C5
0x18001c17f  lea     rcx, [rdx+88h]; struct sockaddr_storage *
0x18001c186  mov     rdx, r10; struct sockaddr_storage *
0x18001c189  call    ?IsAddrEqual@@YA_NPEAUsockaddr_storage@@0@Z; IsAddrEqual(sockaddr_storage *,sockaddr_storage *)
0x18001c18e  cmp     al, 1
0x18001c190  jnz     short loc_18001C1C5
0x18001c192  mov     rdx, r8
0x18001c195  lea     rcx, [rsp+3F8h+var_318]
0x18001c19d  call    ??4?$AutoPtr@UNtpPeer@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<NtpPeer>::operator=(AutoPtr<NtpPeer> const &)
0x18001c1a2  mov     rbx, [rsp+3F8h+var_318]
0x18001c1aa  test    rbx, rbx
0x18001c1ad  jz      short loc_18001C1E8
0x18001c1af  mov     rax, [rbx+8]
0x18001c1b3  test    rax, rax
0x18001c1b6  jz      short loc_18001C1E8
0x18001c1b8  test    rsi, rsi
0x18001c1bb  jz      short loc_18001C1E3
0x18001c1bd  cmp     [rsi+8], rax
0x18001c1c1  jnz     short loc_18001C1E8
0x18001c1c3  jmp     short loc_18001C214
0x18001c1c5  mov     [rsp+3F8h+var_388], r8
0x18001c1ca  add     r8, 8
0x18001c1ce  mov     [rsp+3F8h+var_300], r8
0x18001c1d6  mov     rax, [rsp+3F8h+var_368]
0x18001c1de  jmp     loc_18001C143
0x18001c1e3  cmp     rsi, rbx
0x18001c1e6  jz      short loc_18001C214
0x18001c1e8  xor     edx, edx
0x18001c1ea  lea     rcx, [rsp+3F8h+var_388]
0x18001c1ef  call    ??0?$AutoPtr@UNtpPeer@@@@QEAA@PEAUNtpPeer@@@Z; AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(NtpPeer *)
0x18001c1f4  nop
0x18001c1f5  lea     rdx, [rsp+3F8h+var_388]
0x18001c1fa  lea     rcx, [rsp+3F8h+var_380]
0x18001c1ff  call    ??4?$AutoPtr@UNtpPeer@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<NtpPeer>::operator=(AutoPtr<NtpPeer> const &)
0x18001c204  nop
0x18001c205  lea     rcx, [rsp+3F8h+var_388]
0x18001c20a  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x18001c20f  mov     rsi, [rsp+3F8h+var_380]
0x18001c214  test    rbx, rbx
0x18001c217  jz      short loc_18001C231
0x18001c219  mov     eax, edi
0x18001c21b  lock xadd [rbx], eax
0x18001c21f  cmp     eax, 1
0x18001c222  jnz     short loc_18001C231
0x18001c224  test    rbx, rbx
0x18001c227  jz      short loc_18001C231
0x18001c229  mov     rcx, rbx; void *
0x18001c22c  call    ??_G?$Ref@UNtpPeer@@@@QEAAPEAXI@Z; Ref<NtpPeer>::`scalar deleting destructor'(uint)
0x18001c231  test    rsi, rsi
0x18001c234  jz      short loc_18001C255
0x18001c236  cmp     qword ptr [rsi+8], 0
0x18001c23b  jz      short loc_18001C255
0x18001c23d  mov     ecx, 6Ah ; 'j'
0x18001c242  call    FileLogAllowEntry
0x18001c247  mov     rbx, [rsp+3F8h+SourceString]
0x18001c24f  test    al, al
0x18001c251  jz      short loc_18001C29C
0x18001c253  jmp     short loc_18001C291
0x18001c255  cmp     [rsp+3F8h+var_3A8], 0
0x18001c25a  jz      short loc_18001C27B
0x18001c25c  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001c263  add     rcx, 148h; lpCriticalSection
0x18001c26a  call    cs:__imp_LeaveCriticalSection
0x18001c271  nop     dword ptr [rax+rax+00h]
0x18001c276  mov     [rsp+3F8h+var_3A8], 0
0x18001c27b  mov     ecx, 73h ; 's'
0x18001c280  call    FileLogAllowEntry
0x18001c285  mov     rbx, [rsp+3F8h+SourceString]
0x18001c28d  test    al, al
0x18001c28f  jz      short loc_18001C29C
0x18001c291  mov     rdx, [rbx]
0x18001c294  mov     rcx, r12
0x18001c297  call    FileLogNtpPacket
0x18001c29c  mov     ecx, 78h ; 'x'
0x18001c2a1  call    FileLogAllowEntry
0x18001c2a6  test    al, al
0x18001c2a8  jz      short loc_18001C2E1
0x18001c2aa  mov     rdx, [rsp+3F8h+var_360]
0x18001c2b2  mov     rdx, [rdx]
0x18001c2b5  lea     rcx, aListeningthrea_2; "ListeningThread STC:%I64u\n"
0x18001c2bc  call    FileLogAdd
0x18001c2c1  jmp     short loc_18001C2E1
0x18001c2c3  mov     ecx, 76h ; 'v'
0x18001c2c8  call    FileLogAllowEntry
0x18001c2cd  test    al, al
0x18001c2cf  jz      short loc_18001C2DC
0x18001c2d1  mov     rdx, [rbx]
0x18001c2d4  mov     rcx, r12
0x18001c2d7  call    FileLogNtpPacket
0x18001c2dc  mov     edi, 0FFFFFFFFh
0x18001c2e1  mov     r10d, r13d
0x18001c2e4  mov     [rsp+3F8h+var_1CC], r13d
0x18001c2ec  mov     [rsp+3F8h+var_1BC], 1
0x18001c2f4  mov     [rsp+3F8h+var_1BF], 0
0x18001c2fc  mov     [rsp+3F8h+var_1C0], 0
0x18001c304  mov     [rsp+3F8h+var_1BE], 0
0x18001c30c  mov     [rsp+3F8h+var_1BD], 0
0x18001c314  movzx   ecx, byte ptr [r12]
0x18001c319  movzx   eax, cl
0x18001c31c  shr     al, 3
0x18001c31f  and     al, 7
0x18001c321  cmp     al, 1
0x18001c323  jnb     short loc_18001C33C
0x18001c325  mov     ecx, 0Eh
0x18001c32a  call    FileLogAllowEntry
0x18001c32f  test    al, al
0x18001c331  jz      short loc_18001C38A
0x18001c333  lea     rcx, aRejectingPacke_2; "Rejecting packet w/ bad version\n"
  ... truncated ...
```
