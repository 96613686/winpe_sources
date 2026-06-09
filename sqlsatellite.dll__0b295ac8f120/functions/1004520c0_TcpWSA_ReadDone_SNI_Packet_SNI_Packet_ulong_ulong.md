# TcpWSA::ReadDone(SNI_Packet * *,SNI_Packet * *,ulong,ulong)

- ea: `0x1004520c0`
- end: `0x100452709`
- name: `?ReadDone@TcpWSA@@UEAAKPEAPEAVSNI_Packet@@0KK@Z`
- size: `1609`
- prototype: `unsigned int __usercall@<eax>(TcpWSA *__hidden this@<rcx>, struct SNI_Packet **@<rdx>, struct SNI_Packet **@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x10042c590`
- `0x1004349f0`
- `0x1004520c0`
- `0x100459f80`
- `0x10045a090`

## import_xrefs

- `WS2_32!WSAGetOverlappedResult` at `0x10045232e`
- `WS2_32!WSAGetOverlappedResult` at `0x10045232e`
- `WS2_32!WSARecv` at `0x10045252b`
- `WS2_32!WSARecv` at `0x10045252b`
- `WS2_32!__imp_WSAGetLastError` at `0x100452338`
- `WS2_32!__imp_WSAGetLastError` at `0x100452536`
- `WS2_32!__imp_WSAGetLastError` at `0x100452338`
- `WS2_32!__imp_WSAGetLastError` at `0x100452536`

## string_xrefs

- `0x100452658`: `SNIReceive Packet, BytesRead:%d{DWORD}\n`
- `0x1004520f3`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100452354`: `ERR|SNIInconsistent result from Windows - GetQueuedCompletionStatus gave an error but WSAGetOverlappedResult gave no error.\n`
- `0x1004520fe`: `TcpWSA::ReadDone`
- `0x100452432`: `ERR|SNISuccessful 0-byte TCP read, indicating either graceful termination or multiple reads were posted and the later reads were aborted without error.\n`
- `0x10045240c`: `ERR|SNISuccessful 0-byte TCP read: returning WSAECONNRESET.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpWSA::ReadDone(
        TcpWSA *this,
        struct SNI_Packet **a2,
        struct SNI_Packet **a3,
        const wchar_t *a4,
        DWORD dwFlags)
{
  int v5; // ebx
  unsigned int Error; // esi
  unsigned int v10; // ebx
  char *v11; // rax
  __int16 v12; // ax
  LPDWORD lpdwFlags; // [rsp+20h] [rbp-98h]
  LPWSAOVERLAPPED lpOverlapped; // [rsp+28h] [rbp-90h]
  LPWSAOVERLAPPED_COMPLETION_ROUTINE lpCompletionRoutine; // [rsp+30h] [rbp-88h]
  DWORD Flags; // [rsp+50h] [rbp-68h] BYREF
  __int64 v18; // [rsp+58h] [rbp-60h]
  struct _WSABUF Buffers; // [rsp+60h] [rbp-58h] BYREF
  const char *v20; // [rsp+70h] [rbp-48h]
  const char *v21; // [rsp+78h] [rbp-40h]
  int v22; // [rsp+80h] [rbp-38h]
  DWORD cbTransfer; // [rsp+D0h] [rbp+18h] BYREF

  v18 = -2;
  v5 = (int)a4;
  v20 = "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp";
  v21 = "TcpWSA::ReadDone";
  v22 = 705;
  Error = dwFlags;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::ReadDone",
      705,
      L"API|SNI%u#, ppPacket: %p{SNI_Packet**}, ppLeftOver: %p{SNI_Packet**}, dwBytes: %d, dwError: %d{WINERR}\n",
      *((_DWORD *)this + 11),
      a2,
      a3,
      (_DWORD)a4,
      dwFlags);
  *a3 = 0;
  if ( Error )
  {
    if ( Error == 995 && (*((_BYTE *)*a2 + 236) & 1) != 0 )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 74, 1, 1) == 1 )
      {
        v10 = 10038;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(lpCompletionRoutine) = 10038;
          LODWORD(lpOverlapped) = 0;
          LODWORD(lpdwFlags) = 7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
            "TcpWSA::ReadDone",
            724,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            lpdwFlags,
            lpOverlapped,
            lpCompletionRoutine);
        }
        SNISetLastError(7u, 0x2736u, 0xC3B4u);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(lpdwFlags) = 10038;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
            "TcpWSA::ReadDone",
            725,
            L"RET|SNI%d{WINERR}\n",
            lpdwFlags);
        }
      }
      else if ( SNI::detail::Transport::FAddHandleRef(this) )
      {
        v10 = (*(__int64 (__fastcall **)(TcpWSA *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 24LL))(
                this,
                *a2,
                (unsigned int)(*((_DWORD *)*a2 + 45) - *((_DWORD *)*a2 + 44)),
                0);
        SNI::detail::Transport::ReleaseHandleRef(this);
        if ( v10 == 997 )
        {
          v10 = 0;
          *a2 = 0;
        }
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(lpdwFlags) = v10;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
            "TcpWSA::ReadDone",
            757,
            L"RET|SNI%d{WINERR}\n",
            lpdwFlags);
        }
      }
      else
      {
        v10 = 10038;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(lpCompletionRoutine) = 10038;
          LODWORD(lpOverlapped) = 0;
          LODWORD(lpdwFlags) = 7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
            "TcpWSA::ReadDone",
            736,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            lpdwFlags,
            lpOverlapped,
            lpCompletionRoutine);
        }
        SNISetLastError(7u, 0x2736u, 0xC3B4u);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(lpdwFlags) = 10038;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
            "TcpWSA::ReadDone",
            737,
            L"RET|SNI%d{WINERR}\n",
            lpdwFlags);
        }
      }
      goto LABEL_68;
    }
    if ( !*((_DWORD *)this + 74) && *((_QWORD *)this + 8) != -1 )
    {
      cbTransfer = 0;
      dwFlags = 0;
      if ( WSAGetOverlappedResult(*((_QWORD *)this + 8), (LPWSAOVERLAPPED)((char *)*a2 + 16), &cbTransfer, 0, &dwFlags) )
      {
        if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
        {
LABEL_28:
          SNISetLastError(7u, Error, 0xC3B4u);
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            LODWORD(lpdwFlags) = Error;
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
              "TcpWSA::ReadDone",
              786,
              L"RET|SNI%d{WINERR}\n",
              lpdwFlags);
          }
          v10 = Error;
          goto LABEL_68;
        }
        LODWORD(lpdwFlags) = 10038;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
          "TcpWSA::ReadDone",
          780,
          L"ERR|SNIInconsistent result from Windows - GetQueuedCompletionStatus gave an error but WSAGetOverlappedResult gave no error.\n",
          lpdwFlags);
      }
      else
      {
        Error = WSAGetLastError();
      }
    }
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(lpCompletionRoutine) = Error;
      LODWORD(lpOverlapped) = 0;
      LODWORD(lpdwFlags) = 7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
        "TcpWSA::ReadDone",
        784,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        lpdwFlags,
        lpOverlapped,
        lpCompletionRoutine);
    }
    goto LABEL_28;
  }
  if ( !v5 )
  {
    v11 = (char *)*a2;
    v10 = 10054;
    if ( (*((_BYTE *)*a2 + 236) & 4) != 0 )
      v10 = 0;
    if ( g_osviSNI.dwMajorVersion >= 6 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      {
LABEL_59:
        SNISetLastError(7u, v10, 0xC3B4u);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(lpdwFlags) = v10;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
            "TcpWSA::ReadDone",
            899,
            L"RET|SNI%d{WINERR}\n",
            lpdwFlags);
        }
        goto LABEL_68;
      }
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
        "TcpWSA::ReadDone",
        817,
        L"ERR|SNISuccessful 0-byte TCP read: returning WSAECONNRESET.\n");
LABEL_57:
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(lpCompletionRoutine) = v10;
        LODWORD(lpOverlapped) = 0;
        LODWORD(lpdwFlags) = 7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
          "TcpWSA::ReadDone",
          897,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpdwFlags,
          lpOverlapped,
          lpCompletionRoutine);
      }
      goto LABEL_59;
    }
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
        "TcpWSA::ReadDone",
        822,
        L"ERR|SNISuccessful 0-byte TCP read, indicating either graceful termination or multiple reads were posted and the "
         "later reads were aborted without error.\n");
      v11 = (char *)*a2;
    }
    if ( (v11[236] & 2) == 0 )
      goto LABEL_57;
    Buffers.buf = (CHAR *)&dwFlags;
    Buffers.len = 1;
    cbTransfer = 0;
    Flags = 2;
    if ( !SNI::detail::Transport::FAddHandleRef(this) )
    {
      v10 = 10038;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(lpCompletionRoutine) = 10038;
        LODWORD(lpOverlapped) = 0;
        LODWORD(lpdwFlags) = 7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
          "TcpWSA::ReadDone",
          842,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpdwFlags,
          lpOverlapped,
          lpCompletionRoutine);
      }
      SNISetLastError(7u, 0x2736u, 0xC3B4u);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(lpdwFlags) = 10038;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
          "TcpWSA::ReadDone",
          843,
          L"RET|SNI%d{WINERR}\n",
          lpdwFlags);
      }
      goto LABEL_68;
    }
    if ( WSARecv(*((_QWORD *)this + 8), &Buffers, 1u, &cbTransfer, &Flags, 0, 0) == -1 )
    {
      v10 = WSAGetLastError();
      if ( v10 == 10035 )
      {
        v10 = 995;
        goto LABEL_51;
      }
    }
    else if ( cbTransfer == 1 )
    {
      v10 = 995;
LABEL_51:
      if ( (*((_BYTE *)*a2 + 236) & 1) != 0 )
      {
        v10 = (*(__int64 (__fastcall **)(TcpWSA *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 24LL))(
                this,
                *a2,
                (unsigned int)(*((_DWORD *)*a2 + 45) - *((_DWORD *)*a2 + 44)),
                0);
        SNI::detail::Transport::ReleaseHandleRef(this);
        if ( v10 == 997 )
        {
          v10 = 0;
          *a2 = 0;
        }
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(lpdwFlags) = v10;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
            "TcpWSA::ReadDone",
            884,
            L"RET|SNI%d{WINERR}\n",
            lpdwFlags);
        }
        goto LABEL_68;
      }
LABEL_56:
      SNI::detail::Transport::ReleaseHandleRef(this);
      goto LABEL_57;
    }
    if ( v10 != 995 )
      goto LABEL_56;
    goto LABEL_51;
  }
  v12 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpdwFlags) = v5;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::ReadDone",
      903,
      L"SNIReceive Packet, BytesRead:%d{DWORD}\n",
      lpdwFlags);
    v12 = g_XeSniPkg_enabledBitmap;
  }
  if ( (v12 & 0x100) != 0 )
  {
    SNIXE_SNI_SNIPKT_DATA_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::ReadDone",
      904,
      (const void *)(*((_QWORD *)*a2 + 21) + *((unsigned int *)*a2 + 46)),
      v5);
    LOBYTE(v12) = g_XeSniPkg_enabledBitmap;
  }
  if ( (v12 & 1) != 0 )
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::ReadDone",
      906,
      L"RET|SNI%d{WINERR}\n",
      0);
  v10 = 0;
LABEL_68:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp", "TcpWSA::ReadDone", 705, a4);
  return v10;
}

```

## disassembly

```asm
0x1004520c0  mov     rax, rsp
0x1004520c3  push    rdi
0x1004520c4  push    r12
0x1004520c6  push    r13
0x1004520c8  push    r14
0x1004520ca  push    r15
0x1004520cc  sub     rsp, 90h
0x1004520d3  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x1004520db  mov     [rax+8], rbx
0x1004520df  mov     [rax+10h], rbp
0x1004520e3  mov     [rax+20h], rsi
0x1004520e7  mov     ebx, r9d
0x1004520ea  mov     r15, r8
0x1004520ed  mov     r14, rdx
0x1004520f0  mov     rdi, rcx
0x1004520f3  lea     rbp, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x1004520fa  mov     [rax-48h], rbp
0x1004520fe  lea     r12, aTcpwsaReaddone; "TcpWSA::ReadDone"
0x100452105  mov     [rax-40h], r12
0x100452109  mov     dword ptr [rax-38h], 2C1h
0x100452110  mov     esi, [rsp+0B8h+dwFlags]
0x100452117  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045211e  jz      short loc_10045214F
0x100452120  mov     [rax-78h], esi
0x100452123  mov     [rax-80h], ebx
0x100452126  mov     [rsp+0B8h+lpCompletionRoutine], r8
0x10045212b  mov     [rsp+0B8h+lpOverlapped], rdx
0x100452130  mov     eax, [rcx+2Ch]
0x100452133  mov     dword ptr [rsp+0B8h+lpdwFlags], eax
0x100452137  lea     r9, aApiSniUPppacke_0; "API|SNI%u#, ppPacket: %p{SNI_Packet**},"...
0x10045213e  mov     r8d, 2C1h; int
0x100452144  mov     rdx, r12; char *
0x100452147  mov     rcx, rbp; char *
0x10045214a  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10045214f  xor     r13d, r13d
0x100452152  mov     [r15], r13
0x100452155  test    esi, esi
0x100452157  jz      loc_1004523DC
0x10045215d  cmp     esi, 3E3h
0x100452163  jnz     loc_1004522E7
0x100452169  mov     rax, [r14]
0x10045216c  test    byte ptr [rax+0ECh], 1
0x100452173  jz      loc_1004522E7
0x100452179  mov     esi, 1
0x10045217e  mov     eax, esi
0x100452180  lock cmpxchg [rdi+128h], esi
0x100452188  jnz     short loc_100452201
0x10045218a  mov     ebx, 2736h
0x10045218f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452196  jz      short loc_1004521C1
0x100452198  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], ebx
0x10045219c  mov     dword ptr [rsp+0B8h+lpOverlapped], r13d
0x1004521a1  mov     dword ptr [rsp+0B8h+lpdwFlags], 7
0x1004521a9  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004521b0  mov     r8d, 2D4h; int
0x1004521b6  mov     rdx, r12; char *
0x1004521b9  mov     rcx, rbp; char *
0x1004521bc  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004521c1  mov     r8d, 0C3B4h
0x1004521c7  mov     edx, ebx
0x1004521c9  mov     ecx, 7
0x1004521ce  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004521d3  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, sil; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004521da  jz      loc_1004526CC
0x1004521e0  mov     dword ptr [rsp+0B8h+lpdwFlags], ebx
0x1004521e4  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004521eb  mov     r8d, 2D5h; int
0x1004521f1  mov     rdx, r12; char *
0x1004521f4  mov     rcx, rbp; char *
0x1004521f7  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004521fc  jmp     loc_1004526CC
0x100452201  mov     rcx, rdi; this
0x100452204  call    ?FAddHandleRef@Transport@detail@SNI@@IEAA_NXZ; SNI::detail::Transport::FAddHandleRef(void)
0x100452209  test    al, al
0x10045220b  jnz     short loc_100452284
0x10045220d  mov     ebx, 2736h
0x100452212  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452219  jz      short loc_100452244
0x10045221b  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], ebx
0x10045221f  mov     dword ptr [rsp+0B8h+lpOverlapped], r13d
0x100452224  mov     dword ptr [rsp+0B8h+lpdwFlags], 7
0x10045222c  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100452233  mov     r8d, 2E0h; int
0x100452239  mov     rdx, r12; char *
0x10045223c  mov     rcx, rbp; char *
0x10045223f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100452244  mov     r8d, 0C3B4h
0x10045224a  mov     edx, ebx
0x10045224c  mov     ecx, 7
0x100452251  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100452256  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, sil; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045225d  jz      loc_1004526CC
0x100452263  mov     dword ptr [rsp+0B8h+lpdwFlags], ebx
0x100452267  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10045226e  mov     r8d, 2E1h; int
0x100452274  mov     rdx, r12; char *
0x100452277  mov     rcx, rbp; char *
0x10045227a  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10045227f  jmp     loc_1004526CC
0x100452284  mov     rdx, [r14]
0x100452287  mov     rax, [rdi]
0x10045228a  mov     r8d, [rdx+0B4h]
0x100452291  sub     r8d, [rdx+0B0h]
0x100452298  xor     r9d, r9d
0x10045229b  mov     rcx, rdi
0x10045229e  call    qword ptr [rax+18h]
0x1004522a1  mov     ebx, eax
0x1004522a3  mov     rcx, rdi; this
0x1004522a6  call    ?ReleaseHandleRef@Transport@detail@SNI@@IEAAXXZ; SNI::detail::Transport::ReleaseHandleRef(void)
0x1004522ab  cmp     ebx, 3E5h
0x1004522b1  jnz     short loc_1004522B9
0x1004522b3  mov     ebx, r13d
0x1004522b6  mov     [r14], r13
0x1004522b9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, sil; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004522c0  jz      loc_1004526CC
0x1004522c6  mov     dword ptr [rsp+0B8h+lpdwFlags], ebx
0x1004522ca  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004522d1  mov     r8d, 2F5h; int
0x1004522d7  mov     rdx, r12; char *
0x1004522da  mov     rcx, rbp; char *
0x1004522dd  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004522e2  jmp     loc_1004526CC
0x1004522e7  mov     eax, [rdi+128h]
0x1004522ed  test    eax, eax
0x1004522ef  jnz     short loc_10045236C
0x1004522f1  mov     rax, [rdi+40h]
0x1004522f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1004522f9  jz      short loc_10045236C
0x1004522fb  mov     [rsp+0B8h+cbTransfer], r13d
0x100452303  mov     [rsp+0B8h+dwFlags], r13d
0x10045230b  mov     rdx, [r14]
0x10045230e  add     rdx, 10h; lpOverlapped
0x100452312  lea     rax, [rsp+0B8h+dwFlags]
0x10045231a  mov     [rsp+0B8h+lpdwFlags], rax; lpdwFlags
0x10045231f  xor     r9d, r9d; fWait
0x100452322  lea     r8, [rsp+0B8h+cbTransfer]; lpcbTransfer
0x10045232a  mov     rcx, [rdi+40h]; s
0x10045232e  call    cs:__imp_WSAGetOverlappedResult
0x100452334  test    eax, eax
0x100452336  jnz     short loc_100452342
0x100452338  call    cs:__imp_WSAGetLastError
0x10045233e  mov     esi, eax
0x100452340  jmp     short loc_10045236C
0x100452342  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452349  jz      short loc_10045239E
0x10045234b  mov     ebx, 2736h
0x100452350  mov     dword ptr [rsp+0B8h+lpdwFlags], ebx
0x100452354  lea     r9, aErrSniinconsis; "ERR|SNIInconsistent result from Windows"...
0x10045235b  mov     r8d, 30Ch; int
0x100452361  mov     rdx, r12; char *
0x100452364  mov     rcx, rbp; char *
0x100452367  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10045236c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452373  jz      short loc_10045239E
0x100452375  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], esi
0x100452379  mov     dword ptr [rsp+0B8h+lpOverlapped], r13d
0x10045237e  mov     dword ptr [rsp+0B8h+lpdwFlags], 7
0x100452386  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10045238d  mov     r8d, 310h; int
0x100452393  mov     rdx, r12; char *
0x100452396  mov     rcx, rbp; char *
0x100452399  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10045239e  mov     r8d, 0C3B4h
0x1004523a4  mov     edx, esi
0x1004523a6  mov     ecx, 7
0x1004523ab  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004523b0  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004523b7  jz      short loc_1004523D5
0x1004523b9  mov     dword ptr [rsp+0B8h+lpdwFlags], esi
0x1004523bd  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004523c4  mov     r8d, 312h; int
0x1004523ca  mov     rdx, r12; char *
0x1004523cd  mov     rcx, rbp; char *
0x1004523d0  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004523d5  mov     ebx, esi
0x1004523d7  jmp     loc_1004526CC
0x1004523dc  test    ebx, ebx
0x1004523de  jnz     loc_10045264A
0x1004523e4  mov     rax, [r14]
0x1004523e7  test    byte ptr [rax+0ECh], 4
0x1004523ee  mov     ebx, 2746h
0x1004523f3  cmovnz  ebx, esi
0x1004523f6  cmp     cs:?g_osviSNI@@3U_OSVERSIONINFOEXW@@A.dwMajorVersion, 6; _OSVERSIONINFOEXW g_osviSNI ...
0x1004523fd  jb      short loc_100452429
0x1004523ff  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452406  jz      loc_10045260A
0x10045240c  lea     r9, aErrSnisuccessf_1; "ERR|SNISuccessful 0-byte TCP read: retu"...
0x100452413  mov     r8d, 331h; int
0x100452419  mov     rdx, r12; char *
0x10045241c  mov     rcx, rbp; char *
0x10045241f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100452424  jmp     loc_1004525D8
0x100452429  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452430  jz      short loc_10045244D
0x100452432  lea     r9, aErrSnisuccessf_2; "ERR|SNISuccessful 0-byte TCP read, indi"...
0x100452439  mov     r8d, 336h; int
0x10045243f  mov     rdx, r12; char *
0x100452442  mov     rcx, rbp; char *
0x100452445  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10045244a  mov     rax, [r14]
0x10045244d  test    byte ptr [rax+0ECh], 2
0x100452454  jz      loc_1004525D8
0x10045245a  lea     rax, [rsp+0B8h+dwFlags]
0x100452462  mov     [rsp+0B8h+Buffers.buf], rax
0x100452467  mov     esi, 1
0x10045246c  mov     [rsp+0B8h+Buffers.len], esi
0x100452470  mov     [rsp+0B8h+cbTransfer], r13d
0x100452478  mov     [rsp+0B8h+Flags], 2
0x100452480  mov     rcx, rdi; this
0x100452483  call    ?FAddHandleRef@Transport@detail@SNI@@IEAA_NXZ; SNI::detail::Transport::FAddHandleRef(void)
0x100452488  test    al, al
0x10045248a  jnz     short loc_100452503
0x10045248c  mov     ebx, 2736h
0x100452491  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100452498  jz      short loc_1004524C3
0x10045249a  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], ebx
0x10045249e  mov     dword ptr [rsp+0B8h+lpOverlapped], r13d
0x1004524a3  mov     dword ptr [rsp+0B8h+lpdwFlags], 7
0x1004524ab  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004524b2  mov     r8d, 34Ah; int
0x1004524b8  mov     rdx, r12; char *
0x1004524bb  mov     rcx, rbp; char *
0x1004524be  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004524c3  mov     r8d, 0C3B4h
0x1004524c9  mov     edx, ebx
0x1004524cb  mov     ecx, 7
0x1004524d0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004524d5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, sil; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004524dc  jz      loc_1004526CC
0x1004524e2  mov     dword ptr [rsp+0B8h+lpdwFlags], ebx
0x1004524e6  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004524ed  mov     r8d, 34Bh; int
0x1004524f3  mov     rdx, r12; char *
0x1004524f6  mov     rcx, rbp; char *
0x1004524f9  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004524fe  jmp     loc_1004526CC
0x100452503  mov     [rsp+0B8h+lpCompletionRoutine], r13; lpCompletionRoutine
0x100452508  mov     [rsp+0B8h+lpOverlapped], r13; lpOverlapped
0x10045250d  lea     rax, [rsp+0B8h+Flags]
0x100452512  mov     [rsp+0B8h+lpdwFlags], rax; lpFlags
0x100452517  lea     r9, [rsp+0B8h+cbTransfer]; lpNumberOfBytesRecvd
0x10045251f  mov     r8d, esi; dwBufferCount
0x100452522  lea     rdx, [rsp+0B8h+Buffers]; lpBuffers
0x100452527  mov     rcx, [rdi+40h]; s
0x10045252b  call    cs:__imp_WSARecv
0x100452531  cmp     eax, 0FFFFFFFFh
0x100452534  jnz     short loc_10045254C
0x100452536  call    cs:__imp_WSAGetLastError
0x10045253c  mov     ebx, eax
0x10045253e  cmp     eax, 2733h
0x100452543  jnz     short loc_10045255C
0x100452545  mov     ebx, 3E3h
0x10045254a  jmp     short loc_100452564
0x10045254c  cmp     [rsp+0B8h+cbTransfer], esi
0x100452553  jnz     short loc_10045255C
0x100452555  mov     ebx, 3E3h
0x10045255a  jmp     short loc_100452564
0x10045255c  cmp     ebx, 3E3h
0x100452562  jnz     short loc_1004525D0
0x100452564  mov     rdx, [r14]
0x100452567  test    [rdx+0ECh], sil
0x10045256e  jz      short loc_1004525D0
0x100452570  mov     rax, [rdi]
0x100452573  mov     r8d, [rdx+0B4h]
0x10045257a  sub     r8d, [rdx+0B0h]
0x100452581  xor     r9d, r9d
0x100452584  mov     rcx, rdi
0x100452587  call    qword ptr [rax+18h]
0x10045258a  mov     ebx, eax
0x10045258c  mov     rcx, rdi; this
0x10045258f  call    ?ReleaseHandleRef@Transport@detail@SNI@@IEAAXXZ; SNI::detail::Transport::ReleaseHandleRef(void)
0x100452594  cmp     ebx, 3E5h
0x10045259a  jnz     short loc_1004525A2
0x10045259c  mov     ebx, r13d
0x10045259f  mov     [r14], r13
0x1004525a2  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, sil; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004525a9  jz      loc_1004526CC
0x1004525af  mov     dword ptr [rsp+0B8h+lpdwFlags], ebx
0x1004525b3  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004525ba  mov     r8d, 374h; int
0x1004525c0  mov     rdx, r12; char *
0x1004525c3  mov     rcx, rbp; char *
0x1004525c6  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004525cb  jmp     loc_1004526CC
0x1004525d0  mov     rcx, rdi; this
0x1004525d3  call    ?ReleaseHandleRef@Transport@detail@SNI@@IEAAXXZ; SNI::detail::Transport::ReleaseHandleRef(void)
0x1004525d8  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004525df  jz      short loc_10045260A
0x1004525e1  mov     dword ptr [rsp+0B8h+lpCompletionRoutine], ebx
0x1004525e5  mov     dword ptr [rsp+0B8h+lpOverlapped], r13d
0x1004525ea  mov     dword ptr [rsp+0B8h+lpdwFlags], 7
0x1004525f2  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004525f9  mov     r8d, 381h; int
0x1004525ff  mov     rdx, r12; char *
0x100452602  mov     rcx, rbp; char *
0x100452605  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10045260a  mov     r8d, 0C3B4h
0x100452610  mov     edx, ebx
0x100452612  mov     ecx, 7
0x100452617  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
  ... truncated ...
```
