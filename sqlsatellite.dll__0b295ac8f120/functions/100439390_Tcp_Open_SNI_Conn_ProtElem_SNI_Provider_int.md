# Tcp::Open(SNI_Conn *,ProtElem *,SNI_Provider * *,int)

- ea: `0x100439390`
- end: `0x10043a041`
- name: `?Open@Tcp@@SAKPEAVSNI_Conn@@PEAVProtElem@@PEAPEAVSNI_Provider@@H@Z`
- size: `3249`
- prototype: `unsigned int __fastcall(struct SNI_Conn *, struct ProtElem *, struct SNI_Provider **, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100425000`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042bef0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100436f30`
- `0x100437960`
- `0x100437b30`
- `0x100438970`
- `0x100438f00`
- `0x100439390`
- `0x10045a2f0`
- `0x100486af0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x100439438`
- `KERNEL32!GetTickCount` at `0x100439822`
- `KERNEL32!GetTickCount` at `0x100439964`
- `KERNEL32!GetTickCount` at `0x1004399ce`
- `KERNEL32!GetTickCount` at `0x100439a47`
- `KERNEL32!GetTickCount` at `0x100439438`
- `KERNEL32!GetTickCount` at `0x100439822`
- `KERNEL32!GetTickCount` at `0x100439964`
- `KERNEL32!GetTickCount` at `0x1004399ce`
- `KERNEL32!GetTickCount` at `0x100439a47`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004394c3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043958e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004394c3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043958e`
- `sqldk!SystemThread_TlsIndex` at `0x100439463`
- `sqldk!SystemThread_TlsIndex` at `0x10043952f`
- `sqldk!SystemThread_TlsOffset` at `0x10043946c`
- `sqldk!SystemThread_TlsOffset` at `0x100439538`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100439487`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100439553`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100439487`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100439553`
- `WS2_32!GetAddrInfoW` at `0x100439670`
- `WS2_32!GetAddrInfoW` at `0x1004396b1`
- `WS2_32!GetAddrInfoW` at `0x100439670`
- `WS2_32!GetAddrInfoW` at `0x1004396b1`
- `WS2_32!FreeAddrInfoW` at `0x1004398da`
- `WS2_32!FreeAddrInfoW` at `0x100439d3e`
- `WS2_32!FreeAddrInfoW` at `0x1004398da`
- `WS2_32!FreeAddrInfoW` at `0x100439d3e`
- `WS2_32!WSAIoctl` at `0x100439bc8`
- `WS2_32!WSAIoctl` at `0x100439bc8`
- `WS2_32!__imp_closesocket` at `0x100439d69`
- `WS2_32!__imp_closesocket` at `0x100439d69`
- `WS2_32!__imp_getpeername` at `0x100439cd9`
- `WS2_32!__imp_getpeername` at `0x100439cd9`
- `WS2_32!__imp_getsockname` at `0x100439e54`
- `WS2_32!__imp_getsockname` at `0x100439e54`
- `WS2_32!__imp_ioctlsocket` at `0x100439f55`
- `WS2_32!__imp_ioctlsocket` at `0x100439f55`
- `WS2_32!__imp_setsockopt` at `0x100439b0a`
- `WS2_32!__imp_setsockopt` at `0x100439b0a`
- `WS2_32!__imp_shutdown` at `0x100439d5e`
- `WS2_32!__imp_shutdown` at `0x100439d5e`
- `WS2_32!__imp_WSAGetLastError` at `0x10043967a`
- `WS2_32!__imp_WSAGetLastError` at `0x1004396bb`
- `WS2_32!__imp_WSAGetLastError` at `0x100439b15`
- `WS2_32!__imp_WSAGetLastError` at `0x100439bdc`
- `WS2_32!__imp_WSAGetLastError` at `0x100439ce7`
- `WS2_32!__imp_WSAGetLastError` at `0x100439e5e`
- `WS2_32!__imp_WSAGetLastError` at `0x100439f60`
- `WS2_32!__imp_WSAGetLastError` at `0x10043967a`
- `WS2_32!__imp_WSAGetLastError` at `0x1004396bb`
- `WS2_32!__imp_WSAGetLastError` at `0x100439b15`
- `WS2_32!__imp_WSAGetLastError` at `0x100439bdc`
- `WS2_32!__imp_WSAGetLastError` at `0x100439ce7`
- `WS2_32!__imp_WSAGetLastError` at `0x100439e5e`
- `WS2_32!__imp_WSAGetLastError` at `0x100439f60`

## string_xrefs

- `0x1004393de`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004395f5`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100439613`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100439852`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100439931`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100439998`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100439a0e`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100439a8c`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100439ace`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100439b35`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100439a07`: `Tcp::ParallelOpen`
- `0x100439a85`: `Tcp::ParallelOpen`
- `0x1004393e9`: `Tcp::Open`
- `0x1004395ee`: `Tcp::Open`
- `0x10043984b`: `Tcp::Open`
- `0x10043992a`: `Tcp::Open`
- `0x100439991`: `Tcp::Open`
- `0x100439ac7`: `Tcp::Open`
- `0x100439d16`: `Tcp::Open`
- `0x100439d9e`: `Tcp::Open`
- `0x100439dbf`: `Tcp::Open`
- `0x100439fb9`: `Tcp::Open`
- `0x100439ff7`: `Tcp::Open`
- `0x10043a02c`: `Tcp::Open`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Tcp::Open(struct SNI_Conn *a1, const WCHAR *a2, struct SNI_Provider **a3, int a4)
{
  int v4; // r14d
  unsigned int v7; // r13d
  signed int v8; // esi
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v10; // rbx
  __int64 v11; // rax
  struct IMemObj *v12; // rax
  struct IMemObj *v13; // r12
  __int64 v14; // rbx
  __int64 v15; // rax
  struct IMemObj *v16; // rax
  unsigned int Error; // ebx
  int v18; // r8d
  __int64 v19; // r8
  __int64 v20; // rdx
  const wchar_t *v21; // r9
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rax
  char v25; // al
  unsigned int v26; // edx
  PADDRINFOW i; // rax
  int ai_family; // ecx
  unsigned int v29; // ecx
  struct IMemObj *v30; // rax
  PADDRINFOW v31; // rdi
  int v32; // eax
  DWORD v33; // eax
  const void *v34; // rsi
  SOCKET v35; // rcx
  DWORD v36; // ecx
  const struct addrinfoW *v37; // rdi
  unsigned int v38; // ebx
  int v39; // eax
  DWORD v40; // eax
  DWORD v41; // eax
  unsigned int v42; // r14d
  const wchar_t *v43; // r9
  int v44; // eax
  int v45; // eax
  SOCKET v46; // rcx
  unsigned int v48; // eax
  int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  int v52; // eax
  char v53; // al
  int optlen[2]; // [rsp+20h] [rbp-E0h]
  DWORD cbOutBuffer[2]; // [rsp+28h] [rbp-D8h]
  DWORD cbOutBuffera[2]; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbBytesReturned; // [rsp+30h] [rbp-D0h]
  LPDWORD lpcbBytesReturneda; // [rsp+30h] [rbp-D0h]
  bool v59; // [rsp+50h] [rbp-B0h]
  char optval[4]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD TickCount; // [rsp+58h] [rbp-A8h]
  int v62; // [rsp+5Ch] [rbp-A4h]
  PADDRINFOW ppResult; // [rsp+60h] [rbp-A0h] BYREF
  int v64; // [rsp+68h] [rbp-98h] BYREF
  int v65; // [rsp+6Ch] [rbp-94h]
  struct IMemObj *v66; // [rsp+70h] [rbp-90h]
  struct SNI_Conn *v67; // [rsp+78h] [rbp-88h]
  struct SNI_Provider **v68; // [rsp+80h] [rbp-80h]
  struct IMemObj *v69; // [rsp+88h] [rbp-78h]
  ADDRINFOW pHints; // [rsp+90h] [rbp-70h] BYREF
  __int64 v71; // [rsp+C0h] [rbp-40h]
  const char *v72; // [rsp+C8h] [rbp-38h]
  const char *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  const char *v75; // [rsp+E0h] [rbp-20h]
  const char *v76; // [rsp+E8h] [rbp-18h]
  int v77; // [rsp+F0h] [rbp-10h]
  __int64 vInBuffer; // [rsp+F8h] [rbp-8h] BYREF
  int v79; // [rsp+100h] [rbp+0h]
  struct sockaddr name; // [rsp+110h] [rbp+10h] BYREF
  struct sockaddr v81; // [rsp+190h] [rbp+90h] BYREF

  v71 = -2;
  v4 = a4;
  v68 = a3;
  vInBuffer = (__int64)a2;
  v67 = a1;
  v72 = "sql\\common\\dk\\sni\\src\\tcp.cpp";
  v73 = "Tcp::Open";
  v74 = 6942;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "Tcp::Open",
      6942,
      L"API|SNIpConn: %p{SNI_Conn*}, pProtElem: %p{ProtElem}, ppProv: %p{SNI_Provider**}, timeout: %d\n",
      a1,
      a2,
      a3,
      a4);
  v7 = 0;
  ppResult = 0;
  TickCount = GetTickCount();
  v8 = v4;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  if ( *((_BYTE *)a2 + 1552) )
  {
    v62 = 6955;
    v10 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v11 = *(_QWORD *)(v10 + 256);
    if ( !v11 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v11 = *(_QWORD *)(v10 + 256);
    }
    v66 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v11 + 992) + 56LL) + 8LL);
    v12 = (struct IMemObj *)operator new(0x188u, v66, 1, "sql\\common\\dk\\sni\\src\\tcp.cpp", 6955, 6u);
    v13 = v12;
    v69 = v12;
    if ( v12 )
    {
      Tcp::Tcp(v12, a1);
      *(_QWORD *)v13 = &TcpRIO::`vftable';
      *((_QWORD *)v13 + 43) = 0;
      *((_QWORD *)v13 + 44) = 0;
      *((_QWORD *)v13 + 45) = 0;
      *((_QWORD *)v13 + 46) = 0;
      *((_BYTE *)v13 + 376) = 0;
      *(_QWORD *)((char *)v13 + 380) = 0;
    }
    else
    {
      v13 = 0;
    }
  }
  else
  {
    v62 = 6959;
    v14 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v15 = *(_QWORD *)(v14 + 256);
    if ( !v15 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v15 = *(_QWORD *)(v14 + 256);
    }
    v69 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v15 + 992) + 56LL) + 8LL);
    v16 = (struct IMemObj *)operator new(0x158u, v69, 1, "sql\\common\\dk\\sni\\src\\tcp.cpp", 6959, 6u);
    v13 = v16;
    v66 = v16;
    if ( v16 )
    {
      Tcp::Tcp(v16, a1);
      *(_QWORD *)v13 = &TcpWSA::`vftable';
    }
    else
    {
      v13 = 0;
    }
  }
  if ( !v13 )
  {
    Error = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      v18 = 6966;
LABEL_17:
      LODWORD(lpcbBytesReturned) = Error;
      cbOutBuffer[0] = 0;
      optlen[0] = 7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\tcp.cpp",
        "Tcp::Open",
        v18,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        *(_QWORD *)optlen,
        *(_QWORD *)cbOutBuffer,
        lpcbBytesReturned);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  Error = (*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v13 + 152LL))(v13);
  if ( Error )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_18;
    v18 = 6974;
    goto LABEL_17;
  }
  memset(&pHints, 0, sizeof(pHints));
  pHints.ai_socktype = 1;
  Error = 0;
  if ( GetAddrInfoW(a2 + 4, a2 + 516, &pHints, &ppResult) )
    Error = WSAGetLastError();
  if ( Error )
  {
    if ( Error != 11001 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
        goto LABEL_18;
      v18 = 7009;
      goto LABEL_17;
    }
    pHints.ai_flags |= 4u;
    Error = 0;
    if ( GetAddrInfoW(a2 + 4, a2 + 516, &pHints, &ppResult) )
      Error = WSAGetLastError();
    if ( Error )
    {
      v22 = *((_QWORD *)v67 + 1619);
      if ( v22 )
      {
        if ( (*(_BYTE *)(v22 + 12946) & 1) != 0 && *(int *)(v22 + 12552) < 82 )
        {
          v23 = _InterlockedIncrement((volatile signed __int32 *)(v22 + 12552));
          if ( v23 < 82 )
          {
            v24 = 152LL * (v23 - 1);
            *(_DWORD *)(v24 + v22 + 88) = 19;
            *(_DWORD *)(v24 + v22 + 92) = Error;
            *(_QWORD *)(v24 + v22 + 96) = 0;
            *(_DWORD *)(v24 + v22 + 232) = 0;
          }
        }
      }
      if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
        goto LABEL_18;
      v18 = 7003;
      goto LABEL_17;
    }
  }
  if ( *(_BYTE *)(vInBuffer + 1544) )
    goto LABEL_78;
  v25 = *(_BYTE *)(vInBuffer + 1545);
  if ( v25 != 1 )
  {
    if ( v25 != 2 )
    {
      v64 = 2;
      v65 = 23;
      v59 = 0;
      goto LABEL_51;
    }
LABEL_78:
    v37 = ppResult;
    v38 = v4;
    if ( v4 != -1 )
    {
      v39 = 0;
      if ( v4 >= 0 )
        v39 = v4;
      v4 = v39;
      v40 = GetTickCount() - TickCount;
      if ( v4 < v40 )
      {
        v38 = 1500;
      }
      else
      {
        v38 = v4 - v40;
        if ( v4 - v40 < 0x5DC )
          v38 = 1500;
      }
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        optlen[0] = v38;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "Tcp::ParallelOpen",
          6911,
          L"SNItimeout remaining: %d\n",
          *(_QWORD *)optlen);
      }
    }
    v34 = (const void *)vInBuffer;
    Error = Tcp::SocketOpenParallel(v13, v37, v38, (struct ProtElem *)vInBuffer);
    if ( !Error )
    {
      if ( v4 != -1 && (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        v41 = GetTickCount() - TickCount;
        if ( v4 >= v41 )
        {
          v42 = v4 - v41;
          if ( v42 < 0x5DC )
            v42 = 1500;
        }
        else
        {
          v42 = 0;
        }
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          optlen[0] = v42;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "Tcp::ParallelOpen",
            6928,
            L"SNItimeout remaining after successful connection: %d\n",
            *(_QWORD *)optlen);
        }
      }
      Error = 0;
      goto LABEL_68;
    }
    goto LABEL_124;
  }
  v26 = 0;
  for ( i = ppResult; i; i = i->ai_next )
  {
    ai_family = i->ai_family;
    if ( ai_family == 2 || ai_family == 23 )
      ++v26;
  }
  v59 = v26 > 0x40;
  v64 = 2;
  v65 = 23;
  if ( v26 > 0x40 )
  {
    v4 = *(_DWORD *)(vInBuffer + 1548);
    v59 = v26 > 0x40;
  }
LABEL_51:
  v29 = 0;
  *(_DWORD *)optval = 0;
  v30 = (struct IMemObj *)&v64;
  v66 = (struct IMemObj *)&v64;
  while ( 1 )
  {
    v31 = ppResult;
    if ( ppResult )
      break;
LABEL_66:
    *(_DWORD *)optval = ++v29;
    v30 = (struct IMemObj *)((char *)v30 + 4);
    v66 = v30;
    if ( v29 >= 2 )
      goto LABEL_67;
  }
  v32 = *(_DWORD *)v30;
  v62 = v32;
  while ( 1 )
  {
    if ( v31->ai_family != v32 )
      goto LABEL_64;
    if ( v4 != -1 )
    {
      v33 = GetTickCount();
      v8 = v4 + TickCount - v33;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        optlen[0] = v4 + TickCount - v33;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "Tcp::Open",
          7066,
          L"SNItimeout: %d\n",
          *(_QWORD *)optlen);
      }
      if ( v8 <= 0 || v8 > v4 )
        break;
    }
    Error = Tcp::SocketOpenSync(v13, v31, v8, (struct ProtElem *)vInBuffer);
    if ( !Error )
    {
      if ( v4 != -1 )
      {
        v36 = v4 + TickCount - GetTickCount();
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          optlen[0] = v36;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "Tcp::Open",
            7093,
            L"SNItimeout: %d\n",
            *(_QWORD *)optlen);
        }
      }
      goto LABEL_67;
    }
    if ( *(_BYTE *)(vInBuffer + 1545) == 1 && !v59 )
      goto LABEL_67;
    v32 = v62;
LABEL_64:
    v31 = v31->ai_next;
    if ( !v31 )
    {
      v30 = v66;
      v29 = *(_DWORD *)optval;
      goto LABEL_66;
    }
  }
  if ( !Error )
    Error = 258;
LABEL_67:
  v34 = (const void *)vInBuffer;
LABEL_68:
  FreeAddrInfoW(ppResult);
  ppResult = 0;
  v35 = *((_QWORD *)v13 + 8);
  if ( v35 != -1 )
  {
    *(_DWORD *)optval = 1;
    if ( setsockopt(v35, 6, 1, optval, 4) != -1 )
    {
      v75 = "sql\\common\\dk\\sni\\src\\tcp.cpp";
      v76 = "Tcp::SetKeepAliveOption";
      v77 = 7297;
      if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
      {
        optlen[0] = *((_DWORD *)v13 + 11);
        SNIXE_SNI_ENTER_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "Tcp::SetKeepAliveOption",
          7297,
          L"API|SNI%u#\n",
          *(_QWORD *)optlen);
      }
      *(_DWORD *)optval = 0;
      vInBuffer = 0x753000000001LL;
      v79 = 1000;
      if ( WSAIoctl(*((_QWORD *)v13 + 8), 0x98000004, &vInBuffer, 0xCu, 0, 0, (LPDWORD)optval, 0, 0) == -1 )
      {
        v44 = WSAGetLastError();
        Error = v44;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(lpcbBytesReturneda) = v44;
          cbOutBuffera[0] = 0;
          optlen[0] = 7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "Tcp::SetKeepAliveOption",
            7334,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            *(_QWORD *)optlen,
            *(_QWORD *)cbOutBuffera,
            lpcbBytesReturneda);
        }
        SNISetLastError(7, Error, 50100);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          optlen[0] = Error;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "Tcp::SetKeepAliveOption",
            7336,
            L"RET|SNI%d{WINERR}\n",
            *(_QWORD *)optlen);
        }
        if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
          SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::SetKeepAliveOption", 7297, v21);
        if ( Error )
          goto LABEL_124;
      }
      else
      {
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "Tcp::SetKeepAliveOption",
            7361,
            L"RET|SNI%d{WINERR}\n",
            0);
        if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
          SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::SetKeepAliveOption", 7297, v43);
      }
      Error = (*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v13 + 296LL))(v13);
      if ( Error )
        goto LABEL_124;
      *(_DWORD *)optval = 128;
      if ( getpeername(*((_QWORD *)v13 + 8), &name, (int *)optval) )
      {
        v45 = WSAGetLastError();
        Error = v45;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(lpcbBytesReturneda) = v45;
          cbOutBuffera[0] = 0;
          optlen[0] = 7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "Tcp::Open",
            7175,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            *(_QWORD *)optlen,
            *(_QWORD *)cbOutBuffera,
            lpcbBytesReturneda);
        }
      }
      else
      {
        v48 = Tcp::SetPeerAddrInfo(v13, &name, *(int *)optval);
        Error = v48;
        if ( v48 )
        {
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(lpcbBytesReturneda) = v48;
            cbOutBuffera[0] = 0;
            optlen[0] = 7;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::Open",
              7182,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              *(_QWORD *)optlen,
              *(_QWORD *)cbOutBuffera,
              lpcbBytesReturneda);
          }
        }
        else
        {
          *(_DWORD *)optval = 128;
          if ( getsockname(*((_QWORD *)v13 + 8), &v81, (int *)optval) )
          {
            v49 = WSAGetLastError();
            Error = v49;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(lpcbBytesReturneda) = v49;
              cbOutBuffera[0] = 0;
              optlen[0] = 7;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\tcp.cpp",
                "Tcp::Open",
                7195,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                *(_QWORD *)optlen,
                *(_QWORD *)cbOutBuffera,
                lpcbBytesReturneda);
            }
          }
          else
          {
            v50 = Tcp::SetLocalAddrInfo(v13, &v81, *(int *)optval);
            Error = v50;
            if ( v50 )
            {
              if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
              {
                LODWORD(lpcbBytesReturneda) = v50;
                cbOutBuffera[0] = 0;
                optlen[0] = 7;
                SNIXE_SNI_ERROR_ON(
                  "sql\\common\\dk\\sni\\src\\tcp.cpp",
                  "Tcp::Open",
                  7202,
                  L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                  *(_QWORD *)optlen,
                  *(_QWORD *)cbOutBuffera,
                  lpcbBytesReturneda);
              }
            }
            else
            {
              *((_QWORD *)v13 + 2) = *((_QWORD *)v13 + 8);
              v51 = SNI::detail::Transport::DWSetSkipCompletionPortOnSuccess(v13);
              Error = v51;
              if ( v51 )
              {
                if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
                {
                  LODWORD(lpcbBytesReturneda) = v51;
                  cbOutBuffera[0] = 0;
                  optlen[0] = 7;
                  SNIXE_SNI_ERROR_ON(
                    "sql\\common\\dk\\sni\\src\\tcp.cpp",
                    "Tcp::Open",
                    7214,
                    L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                    *(_QWORD *)optlen,
                    *(_QWORD *)cbOutBuffera,
                    lpcbBytesReturneda);
                }
              }
              else
              {
                if ( *((_BYTE *)v13 + 61)
                  || (*(_DWORD *)optval = 1, (*((_BYTE *)v67 + 12804) & 1) != 0)
                  || ioctlsocket(*((_QWORD *)v13 + 8), -2147195266, (u_long *)optval) != -1 )
                {
                  v53 = g_XeSniPkg_enabledBitmap;
                  if ( (g_XeSniPkg_enabledBitmap & 0x20) != 0 )
                  {
                    SNIXE_SNI_UPDATE_ID_ON(
                      *((_DWORD *)v13 + 11),
                      "sql\\common\\dk\\sni\\src\\tcp.cpp",
                      "Tcp::Open",
                      7236,
                      "ID|SNIconnection: %p{ProtElem}",
                      v34);
                    v53 = g_XeSniPkg_enabledBitmap;
                  }
                  if ( (v53 & 1) != 0 )
                  {
                    optlen[0] = *((_DWORD *)v13 + 11);
                    SNIXE_SNI_TRACE_ON(
                      "sql\\common\\dk\\sni\\src\\tcp.cpp",
                      "Tcp::Open",
                      7241,
                      L"SNI%u#{Tcp}, m_sock: %Iu{SOCKET}\n",
                      *(_QWORD *)optlen,
                      *((_QWORD *)v13 + 8));
                  }
                  *v68 = v13;
                  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
                    SNIXE_SNI_TRACE_ON(
                      "sql\\common\\dk\\sni\\src\\tcp.cpp",
                      "Tcp::Open",
                      7252,
                      L"RET|SNI%d{WINERR}\n",
                      0);
                  goto LABEL_133;
                }
                v52 = WSAGetLastError();
                Error = v52;
                if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
                {
                  LODWORD(lpcbBytesReturneda) = v52;
                  cbOutBuffera[0] = 0;
                  optlen[0] = 7;
                  SNIXE_SNI_ERROR_ON(
                    "sql\\common\\dk\\sni\\src\\tcp.cpp",
                    "Tcp::Open",
                    7228,
                    L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                    *(_QWORD *)optlen,
                    *(_QWORD *)cbOutBuffera,
                    lpcbBytesReturneda);
                }
              }
            }
          }
        }
      }
      SNISetLastError(7, Error, 50100);
      goto LABEL_124;
    }
    Error = WSAGetLastError();
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      v18 = 7148;
      goto LABEL_17;
    }
LABEL_18:
    v19 = 50100;
    v20 = Error;
    goto LABEL_19;
  }
  if ( Error )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(lpcbBytesReturned) = Error;
      cbOutBuffer[0] = 0;
      optlen[0] = 7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\tcp.cpp",
        "Tcp::Open",
        7134,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        *(_QWORD *)optlen,
        *(_QWORD *)cbOutBuffer,
        lpcbBytesReturned);
    }
    v19 = 50100;
    v20 = Error;
  }
  else
  {
    Error = -1;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(lpcbBytesReturned) = -1;
      cbOutBuffer[0] = 17;
      optlen[0] = 7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\tcp.cpp",
        "Tcp::Open",
        7130,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        *(_QWORD *)optlen,
        *(_QWORD *)cbOutBuffer,
        lpcbBytesReturned);
    }
    v19 = 50117;
    v20 = 0xFFFFFFFFLL;
  }
LABEL_19:
  SNISetLastError(7, v20, v19);
LABEL_124:
  if ( ppResult )
  {
    FreeAddrInfoW(ppResult);
    ppResult = 0;
  }
  if ( v13 )
  {
    v46 = *((_QWORD *)v13 + 8);
    if ( v46 != -1 )
    {
      shutdown(v46, 1);
      closesocket(*((_QWORD *)v13 + 8));
    }
    (**(void (__fastcall ***)(struct IMemObj *, __int64))v13)(v13, 1);
  }
  *v68 = 0;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    optlen[0] = Error;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "Tcp::Open",
      7283,
      L"RET|SNI%d{WINERR}\n",
      *(_QWORD *)optlen);
  }
  v7 = Error;
LABEL_133:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::Open", 6942, v21);
  return v7;
}

```

## disassembly

```asm
0x100439390  push    rbp
0x100439392  push    rbx
0x100439393  push    rsi
0x100439394  push    rdi
0x100439395  push    r12
0x100439397  push    r13
0x100439399  push    r14
0x10043939b  push    r15
0x10043939d  lea     rbp, [rsp-128h]
0x1004393a5  sub     rsp, 228h
0x1004393ac  mov     [rbp+160h+var_1A0], 0FFFFFFFFFFFFFFFEh
0x1004393b4  mov     rax, cs:__security_cookie
0x1004393bb  xor     rax, rsp
0x1004393be  mov     [rbp+160h+var_50], rax
0x1004393c5  mov     r14d, r9d
0x1004393c8  mov     rax, r8
0x1004393cb  mov     [rbp+160h+var_1E0], rax
0x1004393cf  mov     r15, rdx
0x1004393d2  mov     [rbp+160h+vInBuffer], rdx
0x1004393d6  mov     rdi, rcx
0x1004393d9  mov     [rsp+260h+var_1E8], rcx
0x1004393de  lea     r12, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x1004393e5  mov     [rbp+160h+var_198], r12
0x1004393e9  lea     rcx, aTcpOpen; "Tcp::Open"
0x1004393f0  mov     [rbp+160h+var_190], rcx
0x1004393f4  mov     [rbp+160h+var_188], 1B1Eh
0x1004393fb  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100439402  jz      short loc_100439430
0x100439404  mov     dword ptr [rsp+260h+lpOverlapped], r9d
0x100439409  mov     [rsp+260h+lpcbBytesReturned], rax
0x10043940e  mov     qword ptr [rsp+260h+cbOutBuffer], rdx
0x100439413  mov     qword ptr [rsp+260h+optlen], rdi
0x100439418  lea     r9, aApiSnipconnPSn_9; "API|SNIpConn: %p{SNI_Conn*}, pProtElem:"...
0x10043941f  mov     r8d, 1B1Eh; int
0x100439425  mov     rdx, rcx; char *
0x100439428  mov     rcx, r12; char *
0x10043942b  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100439430  xor     r13d, r13d
0x100439433  mov     [rsp+260h+ppResult], r13
0x100439438  call    cs:__imp_GetTickCount
0x10043943e  mov     [rsp+260h+var_208], eax
0x100439442  mov     esi, r14d
0x100439445  mov     rdx, gs:58h
0x10043944e  cmp     [r15+610h], r13b
0x100439455  jz      loc_100439527
0x10043945b  mov     [rsp+260h+var_204], 1B2Bh
0x100439463  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043946a  mov     ecx, [rax]
0x10043946c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100439473  mov     ebx, [rax]
0x100439475  add     rbx, [rdx+rcx*8]
0x100439479  mov     rax, [rbx+100h]
0x100439480  test    rax, rax
0x100439483  jnz     short loc_100439494
0x100439485  xor     ecx, ecx
0x100439487  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043948d  mov     rax, [rbx+100h]
0x100439494  mov     rax, [rax+3E0h]
0x10043949b  mov     rcx, [rax+38h]
0x10043949f  mov     rdx, [rcx+8]
0x1004394a3  mov     [rsp+260h+var_1F0], rdx
0x1004394a8  mov     byte ptr [rsp+260h+cbOutBuffer], 6
0x1004394ad  mov     [rsp+260h+optlen], 1B2Bh
0x1004394b5  mov     r9, r12
0x1004394b8  mov     ecx, 188h
0x1004394bd  mov     r8d, 1
0x1004394c3  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004394c9  mov     r12, rax
0x1004394cc  mov     [rbp+160h+var_1D8], rax
0x1004394d0  test    rax, rax
0x1004394d3  jz      short loc_10043951F
0x1004394d5  mov     rdx, rdi; struct SNI_Conn *
0x1004394d8  mov     rcx, rax; this
0x1004394db  call    ??0Tcp@@QEAA@PEAVSNI_Conn@@@Z; Tcp::Tcp(SNI_Conn *)
0x1004394e0  nop
0x1004394e1  lea     rax, ??_7TcpRIO@@6B@; const TcpRIO::`vftable'
0x1004394e8  mov     [r12], rax
0x1004394ec  mov     [r12+158h], r13
0x1004394f4  mov     [r12+160h], r13
0x1004394fc  mov     [r12+168h], r13
0x100439504  mov     [r12+170h], r13
0x10043950c  mov     byte ptr [r12+178h], 0
0x100439515  mov     [r12+17Ch], r13
0x10043951d  jmp     short loc_100439522
0x10043951f  mov     r12, r13
0x100439522  jmp     loc_1004395BD
0x100439527  mov     [rsp+260h+var_204], 1B2Fh
0x10043952f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100439536  mov     ecx, [rax]
0x100439538  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043953f  mov     ebx, [rax]
0x100439541  add     rbx, [rdx+rcx*8]
0x100439545  mov     rax, [rbx+100h]
0x10043954c  test    rax, rax
0x10043954f  jnz     short loc_100439560
0x100439551  xor     ecx, ecx
0x100439553  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100439559  mov     rax, [rbx+100h]
0x100439560  mov     rax, [rax+3E0h]
0x100439567  mov     rcx, [rax+38h]
0x10043956b  mov     rdx, [rcx+8]
0x10043956f  mov     [rbp+160h+var_1D8], rdx
0x100439573  mov     byte ptr [rsp+260h+cbOutBuffer], 6
0x100439578  mov     [rsp+260h+optlen], 1B2Fh
0x100439580  mov     r9, r12
0x100439583  mov     ecx, 158h
0x100439588  mov     r8d, 1
0x10043958e  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100439594  mov     r12, rax
0x100439597  mov     [rsp+260h+var_1F0], rax
0x10043959c  test    rax, rax
0x10043959f  jz      short loc_1004395BA
0x1004395a1  mov     rdx, rdi; struct SNI_Conn *
0x1004395a4  mov     rcx, rax; this
0x1004395a7  call    ??0Tcp@@QEAA@PEAVSNI_Conn@@@Z; Tcp::Tcp(SNI_Conn *)
0x1004395ac  nop
0x1004395ad  lea     rax, ??_7TcpWSA@@6B@; const TcpWSA::`vftable'
0x1004395b4  mov     [r12], rax
0x1004395b8  jmp     short loc_1004395BD
0x1004395ba  mov     r12, r13
0x1004395bd  test    r12, r12
0x1004395c0  jnz     short loc_10043961F
0x1004395c2  lea     ebx, [r12+0Eh]
0x1004395c7  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004395ce  jz      short loc_100439601
0x1004395d0  mov     r8d, 1B36h; int
0x1004395d6  mov     dword ptr [rsp+260h+lpcbBytesReturned], ebx
0x1004395da  mov     [rsp+260h+cbOutBuffer], r13d
0x1004395df  mov     [rsp+260h+optlen], 7
0x1004395e7  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004395ee  lea     rdx, aTcpOpen; "Tcp::Open"
0x1004395f5  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x1004395fc  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100439601  mov     r8d, 0C3B4h
0x100439607  mov     edx, ebx
0x100439609  mov     ecx, 7
0x10043960e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100439613  lea     r15, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x10043961a  jmp     loc_100439D34
0x10043961f  mov     rax, [r12]
0x100439623  mov     rcx, r12
0x100439626  call    qword ptr [rax+98h]
0x10043962c  mov     ebx, eax
0x10043962e  test    eax, eax
0x100439630  jz      short loc_100439643
0x100439632  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100439639  jz      short loc_100439601
0x10043963b  mov     r8d, 1B3Eh
0x100439641  jmp     short loc_1004395D6
0x100439643  xorps   xmm0, xmm0
0x100439646  movups  xmmword ptr [rbp+160h+pHints.ai_flags], xmm0
0x10043964a  movups  xmmword ptr [rbp+160h+pHints.ai_addrlen], xmm0
0x10043964e  movups  xmmword ptr [rbp+160h+pHints.ai_addr], xmm0
0x100439652  mov     [rbp+160h+pHints.ai_socktype], 1
0x100439659  mov     ebx, r13d
0x10043965c  lea     r9, [rsp+260h+ppResult]; ppResult
0x100439661  lea     r8, [rbp+160h+pHints]; pHints
0x100439665  lea     rdx, [r15+408h]; pServiceName
0x10043966c  lea     rcx, [r15+8]; pNodeName
0x100439670  call    cs:__imp_GetAddrInfoW
0x100439676  test    eax, eax
0x100439678  jz      short loc_100439682
0x10043967a  call    cs:__imp_WSAGetLastError
0x100439680  mov     ebx, eax
0x100439682  test    ebx, ebx
0x100439684  jz      loc_100439759
0x10043968a  cmp     ebx, 2AF9h
0x100439690  jnz     loc_100439741
0x100439696  or      [rbp+160h+pHints.ai_flags], 4
0x10043969a  mov     ebx, r13d
0x10043969d  lea     r9, [rsp+260h+ppResult]; ppResult
0x1004396a2  lea     r8, [rbp+160h+pHints]; pHints
0x1004396a6  lea     rdx, [r15+408h]; pServiceName
0x1004396ad  lea     rcx, [r15+8]; pNodeName
0x1004396b1  call    cs:__imp_GetAddrInfoW
0x1004396b7  test    eax, eax
0x1004396b9  jz      short loc_1004396C3
0x1004396bb  call    cs:__imp_WSAGetLastError
0x1004396c1  mov     ebx, eax
0x1004396c3  test    ebx, ebx
0x1004396c5  jz      loc_100439759
0x1004396cb  mov     rax, [rsp+260h+var_1E8]
0x1004396d0  mov     rdx, [rax+3298h]
0x1004396d7  test    rdx, rdx
0x1004396da  jz      short loc_100439729
0x1004396dc  test    byte ptr [rdx+3292h], 1
0x1004396e3  jz      short loc_100439729
0x1004396e5  mov     eax, [rdx+3108h]
0x1004396eb  cmp     eax, 52h ; 'R'
0x1004396ee  jge     short loc_100439729
0x1004396f0  mov     eax, 1
0x1004396f5  lock xadd [rdx+3108h], eax
0x1004396fd  inc     eax
0x1004396ff  cmp     eax, 52h ; 'R'
0x100439702  jge     short loc_100439729
0x100439704  dec     eax
0x100439706  movsxd  rcx, eax
0x100439709  imul    rax, rcx, 98h
0x100439710  mov     dword ptr [rax+rdx+58h], 13h
0x100439718  mov     [rax+rdx+5Ch], ebx
0x10043971c  mov     [rax+rdx+60h], r13
0x100439721  mov     [rax+rdx+0E8h], r13d
0x100439729  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100439730  jz      loc_100439601
0x100439736  mov     r8d, 1B5Bh
0x10043973c  jmp     loc_1004395D6
0x100439741  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100439748  jz      loc_100439601
0x10043974e  mov     r8d, 1B61h
0x100439754  jmp     loc_1004395D6
0x100439759  mov     rdi, [rbp+160h+vInBuffer]
0x10043975d  cmp     byte ptr [rdi+608h], 0
0x100439764  jnz     loc_1004399A9
0x10043976a  movzx   eax, byte ptr [rdi+609h]
0x100439771  cmp     al, 1
0x100439773  jnz     short loc_1004397C5
0x100439775  mov     edx, r13d
0x100439778  mov     rax, [rsp+260h+ppResult]
0x10043977d  test    rax, rax
0x100439780  jz      short loc_10043979A
0x100439782  mov     ecx, [rax+4]
0x100439785  cmp     ecx, 2
0x100439788  jz      short loc_10043978F
0x10043978a  cmp     ecx, 17h
0x10043978d  jnz     short loc_100439791
0x10043978f  inc     edx
0x100439791  mov     rax, [rax+28h]
0x100439795  test    rax, rax
0x100439798  jnz     short loc_100439782
0x10043979a  cmp     edx, 40h ; '@'
0x10043979d  setnbe  al
0x1004397a0  mov     [rsp+260h+var_210], al
0x1004397a4  mov     [rsp+260h+var_1F8], 2
0x1004397ac  mov     [rsp+260h+var_1F4], 17h
0x1004397b4  test    al, al
0x1004397b6  jz      short loc_1004397E2
0x1004397b8  mov     r14d, [rdi+60Ch]
0x1004397bf  mov     [rsp+260h+var_210], al
0x1004397c3  jmp     short loc_1004397E2
0x1004397c5  cmp     al, 2
0x1004397c7  jz      loc_1004399A9
0x1004397cd  mov     [rsp+260h+var_1F8], 2
0x1004397d5  mov     [rsp+260h+var_1F4], 17h
0x1004397dd  mov     [rsp+260h+var_210], 0
0x1004397e2  mov     ecx, r13d
0x1004397e5  mov     dword ptr [rsp+260h+optval], ecx
0x1004397e9  lea     rax, [rsp+260h+var_1F8]
0x1004397ee  mov     [rsp+260h+var_1F0], rax
0x1004397f3  mov     r15d, 0FFFFFFFFh
0x1004397f9  nop     dword ptr [rax+00000000h]
0x100439800  mov     rdi, [rsp+260h+ppResult]
0x100439805  test    rdi, rdi
0x100439808  jz      loc_1004398B9
0x10043980e  mov     eax, [rax]
0x100439810  mov     [rsp+260h+var_204], eax
0x100439814  cmp     [rdi+4], eax
0x100439817  jnz     loc_1004398A3
0x10043981d  cmp     r14d, r15d
0x100439820  jz      short loc_10043986F
0x100439822  call    cs:__imp_GetTickCount
0x100439828  mov     esi, [rsp+260h+var_208]
0x10043982c  add     esi, r14d
0x10043982f  sub     esi, eax
0x100439831  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100439838  jz      short loc_10043985E
0x10043983a  mov     [rsp+260h+optlen], esi
0x10043983e  lea     r9, aSnitimeoutD; "SNItimeout: %d\n"
0x100439845  mov     r8d, 1B9Ah; int
0x10043984b  lea     rdx, aTcpOpen; "Tcp::Open"
0x100439852  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100439859  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043985e  test    esi, esi
0x100439860  jle     loc_10043994D
0x100439866  cmp     esi, r14d
0x100439869  jg      loc_10043994D
0x10043986f  mov     r9, [rbp+160h+vInBuffer]; struct ProtElem *
0x100439873  mov     r8d, esi; dwMilliseconds
0x100439876  mov     rdx, rdi; struct addrinfoW *
0x100439879  mov     rcx, r12; this
0x10043987c  call    ?SocketOpenSync@Tcp@@QEAAKPEAUaddrinfoW@@HPEAVProtElem@@@Z; Tcp::SocketOpenSync(addrinfoW *,int,ProtElem *)
0x100439881  mov     ebx, eax
0x100439883  test    eax, eax
0x100439885  jz      loc_10043995B
0x10043988b  mov     rax, [rbp+160h+vInBuffer]
0x10043988f  cmp     byte ptr [rax+609h], 1
0x100439896  jnz     short loc_10043989F
0x100439898  cmp     [rsp+260h+var_210], 0
0x10043989d  jz      short loc_1004398D1
0x10043989f  mov     eax, [rsp+260h+var_204]
0x1004398a3  mov     rdi, [rdi+28h]
0x1004398a7  test    rdi, rdi
0x1004398aa  jnz     loc_100439814
0x1004398b0  mov     rax, [rsp+260h+var_1F0]
0x1004398b5  mov     ecx, dword ptr [rsp+260h+optval]
0x1004398b9  inc     ecx
0x1004398bb  mov     dword ptr [rsp+260h+optval], ecx
0x1004398bf  add     rax, 4
0x1004398c3  mov     [rsp+260h+var_1F0], rax
0x1004398c8  cmp     ecx, 2
0x1004398cb  jb      loc_100439800
  ... truncated ...
```
