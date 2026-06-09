# TcpWSA::ReadSync(SNI_Packet * *,int)

- ea: `0x100452710`
- end: `0x100452c3d`
- name: `?ReadSync@TcpWSA@@UEAAKPEAPEAVSNI_Packet@@H@Z`
- size: `1325`
- prototype: `unsigned int __fastcall(TcpWSA *__hidden this, struct SNI_Packet **, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x10041ec10`
- `0x10041f180`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042bb70`
- `0x10042c270`
- `0x10042c430`
- `0x10042c590`
- `0x1004349f0`
- `0x100452710`
- `0x10045a400`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x100452876`
- `KERNEL32!WaitForSingleObject` at `0x100452876`
- `KERNEL32!GetTickCount` at `0x100452849`
- `KERNEL32!GetTickCount` at `0x100452867`
- `KERNEL32!GetTickCount` at `0x1004528ef`
- `KERNEL32!GetTickCount` at `0x100452849`
- `KERNEL32!GetTickCount` at `0x100452867`
- `KERNEL32!GetTickCount` at `0x1004528ef`
- `WS2_32!WSAGetOverlappedResult` at `0x1004528ae`
- `WS2_32!WSAGetOverlappedResult` at `0x1004528ae`
- `WS2_32!WSARecv` at `0x10045282b`
- `WS2_32!WSARecv` at `0x10045282b`
- `WS2_32!__imp_WSAGetLastError` at `0x100452836`
- `WS2_32!__imp_WSAGetLastError` at `0x1004528bc`
- `WS2_32!__imp_WSAGetLastError` at `0x100452836`
- `WS2_32!__imp_WSAGetLastError` at `0x1004528bc`

## string_xrefs

- `0x100452a64`: `SNIReceive Packet, BytesRead:%d{DWORD}\n`
- `0x10045273a`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452968`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452979`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x1004529c5`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452a32`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452a78`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452ab6`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452ae8`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452b36`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452b47`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452b94`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452bc9`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452c14`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452745`: `TcpWSA::ReadSync`
- `0x100452961`: `TcpWSA::ReadSync`
- `0x1004529be`: `TcpWSA::ReadSync`
- `0x100452a2b`: `TcpWSA::ReadSync`
- `0x100452a71`: `TcpWSA::ReadSync`
- `0x100452aaf`: `TcpWSA::ReadSync`
- `0x100452ae1`: `TcpWSA::ReadSync`
- `0x100452b2f`: `TcpWSA::ReadSync`
- `0x100452b8d`: `TcpWSA::ReadSync`
- `0x100452bee`: `TcpWSA::ReadSync`
- `0x100452c0d`: `TcpWSA::ReadSync`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpWSA::ReadSync(TcpWSA *this, struct SNI_Packet **a2, signed int a3)
{
  signed int v3; // ebp
  struct SNI_Packet *v6; // rdi
  struct SNI_Packet *Ex2; // rax
  struct _OVERLAPPED *v8; // r15
  unsigned int Error; // ebx
  DWORD TickCount; // r14d
  DWORD v11; // eax
  const wchar_t *v12; // r9
  int v13; // r8d
  int v14; // r8d
  __int64 v15; // rdx
  __int16 v16; // ax
  LPDWORD lpFlags; // [rsp+20h] [rbp-98h]
  LPWSAOVERLAPPED lpOverlapped; // [rsp+28h] [rbp-90h]
  LPWSAOVERLAPPED_COMPLETION_ROUTINE lpCompletionRoutine; // [rsp+30h] [rbp-88h]
  DWORD dwFlags; // [rsp+40h] [rbp-78h] BYREF
  __int64 v22; // [rsp+48h] [rbp-70h]
  struct _WSABUF Buffers; // [rsp+50h] [rbp-68h] BYREF
  const char *v24; // [rsp+60h] [rbp-58h]
  const char *v25; // [rsp+68h] [rbp-50h]
  int v26; // [rsp+70h] [rbp-48h]
  DWORD cbTransfer; // [rsp+C0h] [rbp+8h] BYREF
  DWORD Flags; // [rsp+D8h] [rbp+20h] BYREF

  v22 = -2;
  v3 = a3;
  v24 = "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp";
  v25 = "TcpWSA::ReadSync";
  v26 = 917;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::ReadSync",
      917,
      L"API|SNI%u#, ppNewPacket: %p{SNI_Packet**}, timeout: %d\n",
      *((_DWORD *)this + 11),
      a2,
      a3);
  cbTransfer = 0;
  dwFlags = 0;
  while ( 1 )
  {
    v6 = (struct SNI_Packet *)*((_QWORD *)this + 36);
    if ( v6 )
    {
      v8 = (struct _OVERLAPPED *)((char *)v6 + 16);
      *((_QWORD *)this + 36) = 0;
      TickCount = GetTickCount();
    }
    else
    {
      Ex2 = (struct SNI_Packet *)SNIPacketAllocateEx2(*((_QWORD *)this + 4), 0);
      v6 = Ex2;
      if ( !Ex2 )
      {
        Error = 14;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(lpCompletionRoutine) = 14;
          LODWORD(lpOverlapped) = 0;
          LODWORD(lpFlags) = 7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
            "TcpWSA::ReadSync",
            957,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            lpFlags,
            lpOverlapped,
            lpCompletionRoutine);
        }
        SNISetLastError(7, 14, 50100);
        goto LABEL_49;
      }
      SNI::detail::Transport::PrepareForSyncCall(this, Ex2);
      Buffers.buf = (CHAR *)(*((_QWORD *)v6 + 21) + *((unsigned int *)v6 + 46));
      Buffers.len = *((_DWORD *)v6 + 45);
      Flags = 0;
      v8 = (struct _OVERLAPPED *)((char *)v6 + 16);
      *((_QWORD *)v6 + 4) = 0;
      Error = 0;
      if ( WSARecv(*((_QWORD *)this + 8), &Buffers, 1u, 0, &Flags, (LPWSAOVERLAPPED)((char *)v6 + 16), 0) == -1 )
      {
        Error = WSAGetLastError();
        if ( Error != 997 )
        {
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            v14 = 1000;
            goto LABEL_26;
          }
LABEL_27:
          SNISetLastError(7, Error, 50100);
          if ( Error != 258 )
          {
LABEL_47:
            if ( v6 )
            {
              SNIPacketRelease(v6);
              *((_QWORD *)this + 36) = 0;
            }
          }
LABEL_49:
          *a2 = 0;
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            LODWORD(lpFlags) = Error;
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
              "TcpWSA::ReadSync",
              1119,
              L"RET|SNI%d{WINERR}\n",
              lpFlags);
          }
          goto LABEL_51;
        }
      }
      TickCount = GetTickCount();
      if ( Error != 997 )
        goto LABEL_13;
    }
    v11 = WaitForSingleObject(v8->hEvent, v3);
    Error = v11;
    if ( v11 == -1 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(lpCompletionRoutine) = -1;
        LODWORD(lpOverlapped) = 0;
        LODWORD(lpFlags) = 7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
          "TcpWSA::ReadSync",
          1027,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpFlags,
          lpOverlapped,
          lpCompletionRoutine);
      }
      v15 = 0xFFFFFFFFLL;
      goto LABEL_46;
    }
    if ( v11 == 258 )
    {
      *((_QWORD *)this + 36) = v6;
      Error = 258;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        v13 = 1035;
LABEL_41:
        LODWORD(lpCompletionRoutine) = 258;
        LODWORD(lpOverlapped) = 11;
        LODWORD(lpFlags) = 7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
          "TcpWSA::ReadSync",
          v13,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpFlags,
          lpOverlapped,
          lpCompletionRoutine);
      }
LABEL_42:
      SNISetLastError(7, 258, 50111);
      goto LABEL_49;
    }
LABEL_13:
    if ( WSAGetOverlappedResult(*((_QWORD *)this + 8), v8, &cbTransfer, 0, &dwFlags) )
      break;
    Error = WSAGetLastError();
    if ( Error != 995 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        v14 = 1075;
LABEL_26:
        LODWORD(lpCompletionRoutine) = Error;
        LODWORD(lpOverlapped) = 0;
        LODWORD(lpFlags) = 7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
          "TcpWSA::ReadSync",
          v14,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpFlags,
          lpOverlapped,
          lpCompletionRoutine);
      }
      goto LABEL_27;
    }
    SNIPacketRelease(v6);
    *((_QWORD *)this + 36) = 0;
    cbTransfer = 0;
    if ( v3 != -1 )
    {
      v3 += TickCount - GetTickCount();
      if ( v3 <= 0 )
      {
        Error = 258;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          v13 = 1066;
          goto LABEL_41;
        }
        goto LABEL_42;
      }
    }
  }
  if ( !cbTransfer )
  {
    Error = 10054;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(lpCompletionRoutine) = 10054;
      LODWORD(lpOverlapped) = 0;
      LODWORD(lpFlags) = 7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
        "TcpWSA::ReadSync",
        1090,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        lpFlags,
        lpOverlapped,
        lpCompletionRoutine);
    }
    v15 = 10054;
LABEL_46:
    SNISetLastError(7, v15, 50100);
    goto LABEL_47;
  }
  *((_DWORD *)v6 + 44) = cbTransfer;
  *a2 = v6;
  v16 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 4) != 0 )
  {
    LODWORD(lpFlags) = cbTransfer;
    SNIXE_SNI_SNIPKT_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::ReadSync",
      1099,
      L"SNIReceive Packet, BytesRead:%d{DWORD}\n",
      lpFlags);
    v16 = g_XeSniPkg_enabledBitmap;
  }
  if ( (v16 & 0x100) != 0 )
  {
    SNIXE_SNI_SNIPKT_DATA_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::ReadSync",
      1100,
      (const void *)(*((_QWORD *)v6 + 21) + *((unsigned int *)v6 + 46)),
      cbTransfer);
    LOBYTE(v16) = g_XeSniPkg_enabledBitmap;
  }
  if ( (v16 & 1) != 0 )
  {
    LODWORD(lpFlags) = Error;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::ReadSync",
      1102,
      L"RET|SNI%d{WINERR}\n",
      lpFlags);
  }
LABEL_51:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp", "TcpWSA::ReadSync", 917, v12);
  return Error;
}

```

## disassembly

```asm
0x100452710  mov     rax, rsp
0x100452713  push    rbp
0x100452714  push    rsi
0x100452715  push    rdi
0x100452716  push    r12
0x100452718  push    r13
0x10045271a  push    r14
0x10045271c  push    r15
0x10045271e  sub     rsp, 80h
0x100452725  mov     qword ptr [rax-70h], 0FFFFFFFFFFFFFFFEh
0x10045272d  mov     [rax+10h], rbx
0x100452731  mov     ebp, r8d
0x100452734  mov     r12, rdx
0x100452737  mov     rsi, rcx
0x10045273a  lea     r15, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452741  mov     [rax-58h], r15
0x100452745  lea     rcx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x10045274c  mov     [rax-50h], rcx
0x100452750  mov     dword ptr [rax-48h], 395h
0x100452757  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045275e  jz      short loc_100452789
0x100452760  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], r8d
0x100452765  mov     [rsp+0B8h+lpOverlapped], rdx
0x10045276a  mov     eax, [rsi+2Ch]
0x10045276d  mov     dword ptr [rsp+0B8h+lpFlags], eax
0x100452771  lea     r9, aApiSniUPpnewpa_1; "API|SNI%u#, ppNewPacket: %p{SNI_Packet*"...
0x100452778  mov     r8d, 395h; int
0x10045277e  mov     rdx, rcx; char *
0x100452781  mov     rcx, r15; char *
0x100452784  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100452789  xor     r13d, r13d
0x10045278c  mov     [rsp+0B8h+cbTransfer], r13d
0x100452794  mov     [rsp+0B8h+dwFlags], r13d
0x100452799  nop     dword ptr [rax+00000000h]
0x1004527a0  mov     rdi, [rsi+120h]
0x1004527a7  test    rdi, rdi
0x1004527aa  jnz     loc_10045285C
0x1004527b0  xor     r8d, r8d
0x1004527b3  xor     edx, edx
0x1004527b5  mov     rcx, [rsi+20h]
0x1004527b9  call    SNIPacketAllocateEx2
0x1004527be  mov     rdi, rax
0x1004527c1  test    rax, rax
0x1004527c4  jz      loc_100452935
0x1004527ca  mov     rdx, rax; struct SNI_Packet *
0x1004527cd  mov     rcx, rsi; this
0x1004527d0  call    ?PrepareForSyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForSyncCall(SNI_Packet *)
0x1004527d5  mov     ecx, [rdi+0B8h]
0x1004527db  add     rcx, [rdi+0A8h]
0x1004527e2  mov     [rsp+0B8h+Buffers.buf], rcx
0x1004527e7  mov     ecx, [rdi+0B4h]
0x1004527ed  mov     [rsp+0B8h+Buffers.len], ecx
0x1004527f1  mov     [rsp+0B8h+Flags], r13d
0x1004527f9  lea     r15, [rdi+10h]
0x1004527fd  mov     [r15+10h], r13
0x100452801  mov     ebx, r13d
0x100452804  mov     [rsp+0B8h+lpCompletionRoutine], r13; lpCompletionRoutine
0x100452809  mov     [rsp+0B8h+lpOverlapped], r15; lpOverlapped
0x10045280e  lea     rax, [rsp+0B8h+Flags]
0x100452816  mov     [rsp+0B8h+lpFlags], rax; lpFlags
0x10045281b  xor     r9d, r9d; lpNumberOfBytesRecvd
0x10045281e  lea     r8d, [r9+1]; dwBufferCount
0x100452822  lea     rdx, [rsp+0B8h+Buffers]; lpBuffers
0x100452827  mov     rcx, [rsi+40h]; s
0x10045282b  call    cs:__imp_WSARecv
0x100452831  cmp     eax, 0FFFFFFFFh
0x100452834  jnz     short loc_100452849
0x100452836  call    cs:__imp_WSAGetLastError
0x10045283c  mov     ebx, eax
0x10045283e  cmp     eax, 3E5h
0x100452843  jnz     loc_100452920
0x100452849  call    cs:__imp_GetTickCount
0x10045284f  mov     r14d, eax
0x100452852  cmp     ebx, 3E5h
0x100452858  jnz     short loc_100452892
0x10045285a  jmp     short loc_100452870
0x10045285c  lea     r15, [rdi+10h]
0x100452860  mov     [rsi+120h], r13
0x100452867  call    cs:__imp_GetTickCount
0x10045286d  mov     r14d, eax
0x100452870  mov     edx, ebp; dwMilliseconds
0x100452872  mov     rcx, [r15+18h]; hHandle
0x100452876  call    cs:__imp_WaitForSingleObject
0x10045287c  mov     ebx, eax
0x10045287e  cmp     eax, 0FFFFFFFFh
0x100452881  jz      loc_100452B62
0x100452887  cmp     eax, 102h
0x10045288c  jz      loc_100452AF9
0x100452892  lea     rax, [rsp+0B8h+dwFlags]
0x100452897  mov     [rsp+0B8h+lpFlags], rax; lpdwFlags
0x10045289c  xor     r9d, r9d; fWait
0x10045289f  lea     r8, [rsp+0B8h+cbTransfer]; lpcbTransfer
0x1004528a7  mov     rdx, r15; lpOverlapped
0x1004528aa  mov     rcx, [rsi+40h]; s
0x1004528ae  call    cs:__imp_WSAGetOverlappedResult
0x1004528b4  test    eax, eax
0x1004528b6  jnz     loc_1004529F4
0x1004528bc  call    cs:__imp_WSAGetLastError
0x1004528c2  mov     ebx, eax
0x1004528c4  cmp     eax, 3E3h
0x1004528c9  jnz     loc_100452997
0x1004528cf  mov     rcx, rdi; struct SNI_Packet *
0x1004528d2  call    SNIPacketRelease
0x1004528d7  mov     [rsi+120h], r13
0x1004528de  mov     [rsp+0B8h+cbTransfer], r13d
0x1004528e6  cmp     ebp, 0FFFFFFFFh
0x1004528e9  jz      loc_1004527A0
0x1004528ef  call    cs:__imp_GetTickCount
0x1004528f5  sub     r14d, eax
0x1004528f8  add     ebp, r14d
0x1004528fb  test    ebp, ebp
0x1004528fd  jg      loc_1004527A0
0x100452903  mov     ebx, 102h
0x100452908  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045290f  jz      loc_100452B47
0x100452915  mov     r8d, 42Ah
0x10045291b  jmp     loc_100452B14
0x100452920  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452927  jz      loc_1004529D1
0x10045292d  mov     r8d, 3E8h
0x100452933  jmp     short loc_1004529A6
0x100452935  mov     ebx, 0Eh
0x10045293a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452941  jz      short loc_100452979
0x100452943  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], ebx
0x100452947  mov     dword ptr [rsp+0B8h+lpOverlapped], r13d
0x10045294c  mov     dword ptr [rsp+0B8h+lpFlags], 7
0x100452954  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10045295b  mov     r8d, 3BDh; int
0x100452961  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x100452968  lea     r15, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x10045296f  mov     rcx, r15; char *
0x100452972  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100452977  jmp     short loc_100452980
0x100452979  lea     r15, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452980  mov     r8d, 0C3B4h
0x100452986  mov     edx, ebx
0x100452988  mov     ecx, 7
0x10045298d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100452992  jmp     loc_100452BD0
0x100452997  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045299e  jz      short loc_1004529D1
0x1004529a0  mov     r8d, 433h; int
0x1004529a6  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], ebx
0x1004529aa  mov     dword ptr [rsp+0B8h+lpOverlapped], r13d
0x1004529af  mov     dword ptr [rsp+0B8h+lpFlags], 7
0x1004529b7  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004529be  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x1004529c5  lea     rcx, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x1004529cc  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004529d1  mov     r8d, 0C3B4h
0x1004529d7  mov     edx, ebx
0x1004529d9  mov     ecx, 7
0x1004529de  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004529e3  cmp     ebx, 102h
0x1004529e9  jz      loc_100452BC9
0x1004529ef  jmp     loc_100452BB5
0x1004529f4  mov     eax, [rsp+0B8h+cbTransfer]
0x1004529fb  test    eax, eax
0x1004529fd  jnz     short loc_100452A45
0x1004529ff  mov     ebx, 2746h
0x100452a04  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452a0b  jz      short loc_100452A3E
0x100452a0d  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], ebx
0x100452a11  mov     dword ptr [rsp+0B8h+lpOverlapped], r13d
0x100452a16  mov     dword ptr [rsp+0B8h+lpFlags], 7
0x100452a1e  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100452a25  mov     r8d, 442h; int
0x100452a2b  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x100452a32  lea     rcx, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452a39  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100452a3e  mov     edx, ebx
0x100452a40  jmp     loc_100452BA5
0x100452a45  mov     [rdi+0B0h], eax
0x100452a4b  mov     [r12], rdi
0x100452a4f  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452a55  test    al, 4
0x100452a57  jz      short loc_100452A8A
0x100452a59  mov     eax, [rsp+0B8h+cbTransfer]
0x100452a60  mov     dword ptr [rsp+0B8h+lpFlags], eax
0x100452a64  lea     r9, aSnireceivePack; "SNIReceive Packet, BytesRead:%d{DWORD}"...
0x100452a6b  mov     r8d, 44Bh; int
0x100452a71  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x100452a78  lea     rcx, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452a7f  call    ?SNIXE_SNI_SNIPKT_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_SNIPKT_ON(char const *,char const *,int,wchar_t const *,...)
0x100452a84  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452a8a  bt      eax, 8
0x100452a8e  jnb     short loc_100452AC8
0x100452a90  mov     r9d, [rdi+0B8h]
0x100452a97  add     r9, [rdi+0A8h]; void *
0x100452a9e  mov     eax, [rsp+0B8h+cbTransfer]
0x100452aa5  mov     dword ptr [rsp+0B8h+lpFlags], eax; int
0x100452aa9  mov     r8d, 44Ch; int
0x100452aaf  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x100452ab6  lea     rcx, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452abd  call    ?SNIXE_SNI_SNIPKT_DATA_ON@@YAXPEBD0HPEBXH@Z; SNIXE_SNI_SNIPKT_DATA_ON(char const *,char const *,int,void const *,int)
0x100452ac2  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452ac8  test    al, 1
0x100452aca  jz      loc_100452BFE
0x100452ad0  mov     dword ptr [rsp+0B8h+lpFlags], ebx
0x100452ad4  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100452adb  mov     r8d, 44Eh; int
0x100452ae1  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x100452ae8  lea     rcx, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452aef  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100452af4  jmp     loc_100452BFE
0x100452af9  mov     [rsi+120h], rdi
0x100452b00  mov     ebx, 102h
0x100452b05  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452b0c  jz      short loc_100452B47
0x100452b0e  mov     r8d, 40Bh; int
0x100452b14  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], ebx
0x100452b18  mov     dword ptr [rsp+0B8h+lpOverlapped], 0Bh
0x100452b20  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100452b27  mov     dword ptr [rsp+0B8h+lpFlags], 7
0x100452b2f  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x100452b36  lea     r15, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452b3d  mov     rcx, r15; char *
0x100452b40  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100452b45  jmp     short loc_100452B4E
0x100452b47  lea     r15, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452b4e  mov     edx, ebx
0x100452b50  mov     ecx, 7
0x100452b55  mov     r8d, 0C3BFh
0x100452b5b  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100452b60  jmp     short loc_100452BD0
0x100452b62  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452b69  jz      short loc_100452BA0
0x100452b6b  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], 0FFFFFFFFh
0x100452b73  mov     dword ptr [rsp+0B8h+lpOverlapped], r13d
0x100452b78  mov     dword ptr [rsp+0B8h+lpFlags], 7
0x100452b80  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100452b87  mov     r8d, 403h; int
0x100452b8d  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x100452b94  lea     rcx, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452b9b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100452ba0  mov     edx, 0FFFFFFFFh
0x100452ba5  mov     r8d, 0C3B4h
0x100452bab  mov     ecx, 7
0x100452bb0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100452bb5  test    rdi, rdi
0x100452bb8  jz      short loc_100452BC9
0x100452bba  mov     rcx, rdi; struct SNI_Packet *
0x100452bbd  call    SNIPacketRelease
0x100452bc2  mov     [rsi+120h], r13
0x100452bc9  lea     r15, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452bd0  mov     [r12], r13
0x100452bd4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452bdb  jz      short loc_100452BFE
0x100452bdd  mov     dword ptr [rsp+0B8h+lpFlags], ebx
0x100452be1  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100452be8  mov     r8d, 45Fh; int
0x100452bee  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x100452bf5  mov     rcx, r15; char *
0x100452bf8  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100452bfd  nop
0x100452bfe  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452c05  jz      short loc_100452C20
0x100452c07  mov     r8d, 395h; int
0x100452c0d  lea     rdx, aTcpwsaReadsync; "TcpWSA::ReadSync"
0x100452c14  lea     rcx, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x100452c1b  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100452c20  mov     eax, ebx
0x100452c22  mov     rbx, [rsp+0B8h+arg_8]
0x100452c2a  add     rsp, 80h
0x100452c31  pop     r15
0x100452c33  pop     r14
0x100452c35  pop     r13
0x100452c37  pop     r12
0x100452c39  pop     rdi
0x100452c3a  pop     rsi
0x100452c3b  pop     rbp
0x100452c3c  retn
```
