# TcpConnection::FInitForAsync(void)

- ea: `0x1004368f0`
- end: `0x100436bbf`
- name: `?FInitForAsync@TcpConnection@@QEAAKXZ`
- size: `719`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100438970`
- `0x100438f00`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004368f0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1004369fe`
- `KERNEL32!CreateEventW` at `0x1004369fe`
- `KERNEL32!GetLastError` at `0x100436a10`
- `KERNEL32!GetLastError` at `0x100436a10`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004369c6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004369c6`
- `sqldk!SystemThread_TlsIndex` at `0x10043696c`
- `sqldk!SystemThread_TlsOffset` at `0x100436975`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100436990`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100436990`
- `WS2_32!GetAddrInfoW` at `0x100436aa4`
- `WS2_32!GetAddrInfoW` at `0x100436aa4`
- `WS2_32!FreeAddrInfoW` at `0x100436b52`
- `WS2_32!FreeAddrInfoW` at `0x100436b52`
- `WS2_32!__imp_bind` at `0x100436aff`
- `WS2_32!__imp_bind` at `0x100436aff`
- `WS2_32!__imp_WSAGetLastError` at `0x100436aae`
- `WS2_32!__imp_WSAGetLastError` at `0x100436b0a`
- `WS2_32!__imp_WSAGetLastError` at `0x100436aae`
- `WS2_32!__imp_WSAGetLastError` at `0x100436b0a`

## string_xrefs

- `0x100436912`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100436a33`: `ERR|SNICreateEvent(): %d{WINERR}\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpConnection::FInitForAsync(TcpConnection *this)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  _OWORD *v4; // rax
  const wchar_t *v5; // r9
  unsigned int Error; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-68h]
  ADDRINFOW pHints; // [rsp+50h] [rbp-38h] BYREF
  PADDRINFOW ppResult; // [rsp+90h] [rbp+8h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "TcpConnection::FInitForAsync",
      3668,
      L"API|SNI%u#\n",
      *((_DWORD *)this + 11));
  ppResult = 0;
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  v4 = operator new(
         0x20u,
         *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v3 + 992) + 56LL) + 8LL),
         1,
         "sql\\common\\dk\\sni\\src\\tcp.cpp",
         3676,
         6u);
  *(_QWORD *)this = v4;
  if ( v4 )
  {
    *v4 = 0;
    v4[1] = 0;
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 2) = EventW;
    if ( EventW )
    {
      *(_QWORD *)(*(_QWORD *)this + 24LL) = EventW;
      memset(&pHints.ai_protocol, 0, 36);
      pHints.ai_family = *(_DWORD *)(*((_QWORD *)this + 1) + 4LL);
      pHints.ai_socktype = 1;
      pHints.ai_flags = 1;
      Error = 0;
      if ( GetAddrInfoW(0, L"0", &pHints, &ppResult) )
        Error = WSAGetLastError();
      if ( Error )
      {
        *((_DWORD *)this + 9) = Error;
        *((_DWORD *)this + 10) = 3;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v11) = Error;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "TcpConnection::FInitForAsync",
            3718,
            L"ERR|SNIgetaddrinfo(): %d{WINERR}\n",
            v11);
        }
      }
      else if ( bind(*((_QWORD *)this + 3), ppResult->ai_addr, ppResult->ai_addrlen) == -1 )
      {
        v9 = WSAGetLastError();
        Error = v9;
        *((_DWORD *)this + 9) = v9;
        *((_DWORD *)this + 10) = 5;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v11) = v9;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "TcpConnection::FInitForAsync",
            3728,
            L"ERR|SNIbind(): %d{WINERR}\n",
            v11);
        }
      }
      else
      {
        Error = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      Error = LastError;
      *((_DWORD *)this + 9) = LastError;
      *((_DWORD *)this + 10) = 3;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v11) = LastError;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "TcpConnection::FInitForAsync",
          3693,
          L"ERR|SNICreateEvent(): %d{WINERR}\n",
          v11);
      }
    }
  }
  else
  {
    Error = 14;
    *((_DWORD *)this + 9) = 14;
    *((_DWORD *)this + 10) = 2;
  }
  if ( ppResult )
  {
    FreeAddrInfoW(ppResult);
    ppResult = 0;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v11) = Error;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "TcpConnection::FInitForAsync",
      3748,
      L"RET|SNI%d{WINERR}\n",
      v11);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "TcpConnection::FInitForAsync", 3668, v5);
  return Error;
}

```

## disassembly

```asm
0x1004368f0  mov     rax, rsp
0x1004368f3  push    rdi
0x1004368f4  sub     rsp, 80h
0x1004368fb  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x100436903  mov     [rax+10h], rbx
0x100436907  mov     [rax+18h], rbp
0x10043690b  mov     [rax+20h], rsi
0x10043690f  mov     rdi, rcx
0x100436912  lea     rsi, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100436919  mov     [rax-50h], rsi
0x10043691d  lea     rbp, aTcpconnectionF; "TcpConnection::FInitForAsync"
0x100436924  mov     [rax-48h], rbp
0x100436928  mov     dword ptr [rax-40h], 0E54h
0x10043692f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100436936  jz      short loc_100436957
0x100436938  mov     eax, [rcx+2Ch]
0x10043693b  mov     dword ptr [rsp+88h+var_68], eax
0x10043693f  lea     r9, aApiSniU; "API|SNI%u#\n"
0x100436946  mov     r8d, 0E54h; int
0x10043694c  mov     rdx, rbp; char *
0x10043694f  mov     rcx, rsi; char *
0x100436952  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100436957  mov     [rsp+88h+ppResult], 0
0x100436963  mov     rdx, gs:58h
0x10043696c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100436973  mov     ecx, [rax]
0x100436975  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043697c  mov     ebx, [rax]
0x10043697e  add     rbx, [rdx+rcx*8]
0x100436982  mov     rax, [rbx+100h]
0x100436989  test    rax, rax
0x10043698c  jnz     short loc_10043699D
0x10043698e  xor     ecx, ecx
0x100436990  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100436996  mov     rax, [rbx+100h]
0x10043699d  mov     rax, [rax+3E0h]
0x1004369a4  mov     rcx, [rax+38h]
0x1004369a8  mov     [rsp+88h+var_60], 6
0x1004369ad  mov     dword ptr [rsp+88h+var_68], 0E5Ch
0x1004369b5  mov     r9, rsi
0x1004369b8  mov     r8d, 1
0x1004369be  mov     rdx, [rcx+8]
0x1004369c2  lea     ecx, [r8+1Fh]
0x1004369c6  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004369cc  mov     [rdi], rax
0x1004369cf  test    rax, rax
0x1004369d2  jnz     short loc_1004369E8
0x1004369d4  mov     ebx, 0Eh
0x1004369d9  mov     [rdi+24h], ebx
0x1004369dc  mov     dword ptr [rdi+28h], 2
0x1004369e3  jmp     loc_100436B45
0x1004369e8  xorps   xmm0, xmm0
0x1004369eb  movups  xmmword ptr [rax], xmm0
0x1004369ee  movups  xmmword ptr [rax+10h], xmm0
0x1004369f2  xor     r9d, r9d; lpName
0x1004369f5  xor     r8d, r8d; bInitialState
0x1004369f8  lea     edx, [r9+1]; bManualReset
0x1004369fc  xor     ecx, ecx; lpEventAttributes
0x1004369fe  call    cs:__imp_CreateEventW
0x100436a04  mov     rcx, rax
0x100436a07  mov     [rdi+10h], rax
0x100436a0b  test    rax, rax
0x100436a0e  jnz     short loc_100436A50
0x100436a10  call    cs:__imp_GetLastError
0x100436a16  mov     ebx, eax
0x100436a18  mov     [rdi+24h], eax
0x100436a1b  mov     dword ptr [rdi+28h], 3
0x100436a22  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100436a29  jz      loc_100436B45
0x100436a2f  mov     dword ptr [rsp+88h+var_68], eax
0x100436a33  lea     r9, aErrSnicreateev; "ERR|SNICreateEvent(): %d{WINERR}\n"
0x100436a3a  mov     r8d, 0E6Dh; int
0x100436a40  mov     rdx, rbp; char *
0x100436a43  mov     rcx, rsi; char *
0x100436a46  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100436a4b  jmp     loc_100436B45
0x100436a50  mov     rax, [rdi]
0x100436a53  mov     [rax+18h], rcx
0x100436a57  xorps   xmm0, xmm0
0x100436a5a  movdqu  xmmword ptr [rsp+88h+pHints.ai_protocol], xmm0
0x100436a60  xorps   xmm1, xmm1
0x100436a63  movdqu  xmmword ptr [rsp+88h+pHints.ai_canonname+4], xmm1
0x100436a69  mov     dword ptr [rsp+88h+pHints.ai_next+4], 0
0x100436a71  mov     rax, [rdi+8]
0x100436a75  mov     ecx, [rax+4]
0x100436a78  mov     [rsp+88h+pHints.ai_family], ecx
0x100436a7c  mov     [rsp+88h+pHints.ai_socktype], 1
0x100436a84  mov     [rsp+88h+pHints.ai_flags], 1
0x100436a8c  xor     ebx, ebx
0x100436a8e  lea     r9, [rsp+88h+ppResult]; ppResult
0x100436a96  lea     r8, [rsp+88h+pHints]; pHints
0x100436a9b  lea     rdx, a0; "0"
0x100436aa2  xor     ecx, ecx; pNodeName
0x100436aa4  call    cs:__imp_GetAddrInfoW
0x100436aaa  test    eax, eax
0x100436aac  jz      short loc_100436AB6
0x100436aae  call    cs:__imp_WSAGetLastError
0x100436ab4  mov     ebx, eax
0x100436ab6  test    ebx, ebx
0x100436ab8  jz      short loc_100436AEB
0x100436aba  mov     [rdi+24h], ebx
0x100436abd  mov     dword ptr [rdi+28h], 3
0x100436ac4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100436acb  jz      short loc_100436B45
0x100436acd  mov     dword ptr [rsp+88h+var_68], ebx
0x100436ad1  lea     r9, aErrSnigetaddri; "ERR|SNIgetaddrinfo(): %d{WINERR}\n"
0x100436ad8  mov     r8d, 0E86h; int
0x100436ade  mov     rdx, rbp; char *
0x100436ae1  mov     rcx, rsi; char *
0x100436ae4  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100436ae9  jmp     short loc_100436B45
0x100436aeb  mov     rdx, [rsp+88h+ppResult]
0x100436af3  mov     r8d, [rdx+10h]; namelen
0x100436af7  mov     rdx, [rdx+20h]; name
0x100436afb  mov     rcx, [rdi+18h]; s
0x100436aff  call    cs:__imp_bind
0x100436b05  cmp     eax, 0FFFFFFFFh
0x100436b08  jnz     short loc_100436B43
0x100436b0a  call    cs:__imp_WSAGetLastError
0x100436b10  mov     ebx, eax
0x100436b12  mov     [rdi+24h], eax
0x100436b15  mov     dword ptr [rdi+28h], 5
0x100436b1c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100436b23  jz      short loc_100436B45
0x100436b25  mov     dword ptr [rsp+88h+var_68], eax
0x100436b29  lea     r9, aErrSnibindDWin; "ERR|SNIbind(): %d{WINERR}\n"
0x100436b30  mov     r8d, 0E90h; int
0x100436b36  mov     rdx, rbp; char *
0x100436b39  mov     rcx, rsi; char *
0x100436b3c  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100436b41  jmp     short loc_100436B45
0x100436b43  xor     ebx, ebx
0x100436b45  mov     rcx, [rsp+88h+ppResult]; pAddrInfo
0x100436b4d  test    rcx, rcx
0x100436b50  jz      short loc_100436B64
0x100436b52  call    cs:__imp_FreeAddrInfoW
0x100436b58  mov     [rsp+88h+ppResult], 0
0x100436b64  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100436b6b  jz      short loc_100436B8A
0x100436b6d  mov     dword ptr [rsp+88h+var_68], ebx
0x100436b71  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100436b78  mov     r8d, 0EA4h; int
0x100436b7e  mov     rdx, rbp; char *
0x100436b81  mov     rcx, rsi; char *
0x100436b84  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100436b89  nop
0x100436b8a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100436b91  jz      short loc_100436BA4
0x100436b93  mov     r8d, 0E54h; int
0x100436b99  mov     rdx, rbp; char *
0x100436b9c  mov     rcx, rsi; char *
0x100436b9f  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100436ba4  mov     eax, ebx
0x100436ba6  lea     r11, [rsp+88h+var_8]
0x100436bae  mov     rbx, [r11+18h]
0x100436bb2  mov     rbp, [r11+20h]
0x100436bb6  mov     rsi, [r11+28h]
0x100436bba  mov     rsp, r11
0x100436bbd  pop     rdi
0x100436bbe  retn
```
