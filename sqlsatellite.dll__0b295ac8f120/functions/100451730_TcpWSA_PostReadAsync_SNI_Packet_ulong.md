# TcpWSA::PostReadAsync(SNI_Packet *,ulong)

- ea: `0x100451730`
- end: `0x100451a6e`
- name: `?PostReadAsync@TcpWSA@@AEAAKPEAVSNI_Packet@@K@Z`
- size: `830`
- prototype: `unsigned int __fastcall(TcpWSA *__hidden this, struct SNI_Packet *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1004515b0`
- `0x100451f30`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x10042c590`
- `0x1004349f0`
- `0x100451730`
- `0x10045a4d0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x1004518bd`
- `KERNEL32!GetOverlappedResult` at `0x1004518bd`
- `KERNEL32!GetLastError` at `0x1004518c7`
- `KERNEL32!GetLastError` at `0x1004518c7`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100451838`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100451838`
- `WS2_32!WSARecv` at `0x100451870`
- `WS2_32!WSARecv` at `0x100451870`
- `WS2_32!__imp_WSAGetLastError` at `0x10045187b`
- `WS2_32!__imp_WSAGetLastError` at `0x10045187b`

## string_xrefs

- `0x100451974`: `SNIReceive Packet, BytesRead:%d{DWORD}\n`
- `0x1004519c4`: `SNISuppressing successful read completion and returning ERROR_IO_PENDING.\n`
- `0x100451757`: `sql\common\dk\sni\src\sni_tcpwsaprovider.cpp`
- `0x100451762`: `TcpWSA::PostReadAsync`
- `0x100451930`: `ERR|SNISuccessful 0-byte TCP read: returning WSAECONNRESET\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpWSA::PostReadAsync(TcpWSA *this, struct SNI_Packet *a2, ULONG a3)
{
  char v6; // al
  unsigned int Error; // ebx
  char *v8; // r14
  int v9; // r8d
  const wchar_t *v10; // r9
  DWORD v11; // eax
  __int64 v12; // rax
  __int64 v13; // rdi
  LPDWORD lpFlags; // [rsp+20h] [rbp-88h]
  LPWSAOVERLAPPED lpOverlapped; // [rsp+28h] [rbp-80h]
  LPWSAOVERLAPPED_COMPLETION_ROUTINE lpCompletionRoutine; // [rsp+30h] [rbp-78h]
  struct _WSABUF Buffers; // [rsp+48h] [rbp-60h] BYREF
  const char *v19; // [rsp+58h] [rbp-50h]
  const char *v20; // [rsp+60h] [rbp-48h]
  int v21; // [rsp+68h] [rbp-40h]
  DWORD Flags; // [rsp+B0h] [rbp+8h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+C0h] [rbp+18h] BYREF

  v19 = "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp";
  v20 = "TcpWSA::PostReadAsync";
  v21 = 342;
  v6 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::PostReadAsync",
      342,
      L"API|SNI%u#, cbBuffer: %d{DWORD}, pPacket: %p{SNI_Packet*}\n",
      *((_DWORD *)this + 11),
      a3,
      a2);
    v6 = g_XeSniPkg_enabledBitmap;
  }
  Error = 0;
  NumberOfBytesTransferred = 0;
  Flags = 0;
  v8 = (char *)a2 + 16;
  Buffers.buf = (CHAR *)(*((unsigned int *)a2 + 44) + *((_QWORD *)a2 + 21) + *((unsigned int *)a2 + 46));
  Buffers.len = a3;
  if ( *((_QWORD *)this + 36) )
  {
    Error = 5023;
    if ( (v6 & 2) == 0 )
    {
LABEL_7:
      SNISetLastError(7u, Error, 0xC3B4u);
      goto LABEL_28;
    }
    v9 = 360;
LABEL_6:
    LODWORD(lpCompletionRoutine) = Error;
    LODWORD(lpOverlapped) = 0;
    LODWORD(lpFlags) = 7;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::PostReadAsync",
      v9,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      lpFlags,
      lpOverlapped,
      lpCompletionRoutine);
    goto LABEL_7;
  }
  CGlobalTraceFlags::GetUlTraceFlags();
  SNI::detail::Transport::PrepareForAsyncCall(this, a2);
  if ( WSARecv(*((_QWORD *)this + 8), &Buffers, 1u, 0, &Flags, (LPWSAOVERLAPPED)((char *)a2 + 16), 0) == -1 )
  {
    Error = WSAGetLastError();
    if ( Error != 997 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
        goto LABEL_7;
      v9 = 390;
      goto LABEL_6;
    }
    goto LABEL_27;
  }
  if ( !*((_BYTE *)this + 61) )
  {
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
        "TcpWSA::PostReadAsync",
        436,
        L"SNISuppressing successful read completion and returning ERROR_IO_PENDING.\n");
LABEL_27:
    Error = 997;
    goto LABEL_28;
  }
  if ( !GetOverlappedResult(*((HANDLE *)this + 8), (LPOVERLAPPED)((char *)a2 + 16), &NumberOfBytesTransferred, 0) )
  {
    Error = GetLastError();
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_7;
    LODWORD(lpFlags) = Error;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::PostReadAsync",
      407,
      L"ERR|SNIGetOverlappedResult: %d{WINERR}\n",
      lpFlags);
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_7;
    v9 = 408;
    goto LABEL_6;
  }
  v11 = NumberOfBytesTransferred;
  if ( !NumberOfBytesTransferred )
  {
    Error = 10054;
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_7;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::PostReadAsync",
      415,
      L"ERR|SNISuccessful 0-byte TCP read: returning WSAECONNRESET\n");
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_7;
    v9 = 416;
    goto LABEL_6;
  }
  *((_DWORD *)a2 + 44) += NumberOfBytesTransferred;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpFlags) = v11;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::PostReadAsync",
      426,
      L"SNIReceive Packet, BytesRead:%d{DWORD}\n",
      lpFlags);
    v11 = NumberOfBytesTransferred;
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x100) != 0 )
    SNIXE_SNI_SNIPKT_DATA_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::PostReadAsync",
      427,
      Buffers.buf,
      v11);
LABEL_28:
  v12 = *((_QWORD *)this + 4);
  v13 = *(_QWORD *)(v12 + 12992);
  if ( *(_BYTE *)(v12 + 12717) )
  {
    if ( Error == 997 )
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v13 + 24LL))(v13, v8);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 32LL))(v13, 0);
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpFlags) = Error;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp",
      "TcpWSA::PostReadAsync",
      446,
      L"RET|SNI%d{WINERR}\n",
      lpFlags);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_tcpwsaprovider.cpp", "TcpWSA::PostReadAsync", 342, v10);
  return Error;
}

```

## disassembly

```asm
0x100451730  mov     rax, rsp
0x100451733  push    rbp
0x100451734  push    rsi
0x100451735  push    rdi
0x100451736  push    r12
0x100451738  push    r13
0x10045173a  push    r14
0x10045173c  push    r15
0x10045173e  sub     rsp, 70h
0x100451742  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x10045174a  mov     [rax+10h], rbx
0x10045174e  mov     ebp, r8d
0x100451751  mov     rdi, rdx
0x100451754  mov     rsi, rcx
0x100451757  lea     r15, aSqlCommonDkSni_1; "sql\\common\\dk\\sni\\src\\sni_tcpwsapr"...
0x10045175e  mov     [rax-50h], r15
0x100451762  lea     r12, aTcpwsaPostread; "TcpWSA::PostReadAsync"
0x100451769  mov     [rax-48h], r12
0x10045176d  mov     dword ptr [rax-40h], 156h
0x100451774  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045177a  test    al, 40h
0x10045177c  jz      short loc_1004517AD
0x10045177e  mov     [rsp+0A8h+lpCompletionRoutine], rdx
0x100451783  mov     dword ptr [rsp+0A8h+lpOverlapped], r8d
0x100451788  mov     eax, [rcx+2Ch]
0x10045178b  mov     dword ptr [rsp+0A8h+lpFlags], eax
0x10045178f  lea     r9, aApiSniUCbbuffe; "API|SNI%u#, cbBuffer: %d{DWORD}, pPacke"...
0x100451796  mov     r8d, 156h; int
0x10045179c  mov     rdx, r12; char *
0x10045179f  mov     rcx, r15; char *
0x1004517a2  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004517a7  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004517ad  xor     r13d, r13d
0x1004517b0  mov     ebx, r13d
0x1004517b3  mov     [rsp+0A8h+NumberOfBytesTransferred], r13d
0x1004517bb  mov     [rsp+0A8h+Flags], r13d
0x1004517c3  lea     r14, [rdi+10h]
0x1004517c7  mov     edx, [rdi+0B8h]
0x1004517cd  add     rdx, [rdi+0A8h]
0x1004517d4  mov     ecx, [rdi+0B0h]
0x1004517da  add     rdx, rcx
0x1004517dd  mov     [rsp+0A8h+Buffers.buf], rdx
0x1004517e2  mov     [rsp+0A8h+Buffers.len], ebp
0x1004517e6  cmp     [rsi+120h], rbx
0x1004517ed  jz      short loc_100451838
0x1004517ef  mov     ebx, 139Fh
0x1004517f4  test    al, 2
0x1004517f6  jz      short loc_100451821
0x1004517f8  mov     r8d, 168h; int
0x1004517fe  mov     dword ptr [rsp+0A8h+lpCompletionRoutine], ebx
0x100451802  mov     dword ptr [rsp+0A8h+lpOverlapped], r13d
0x100451807  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10045180e  mov     dword ptr [rsp+0A8h+lpFlags], 7
0x100451816  mov     rdx, r12; char *
0x100451819  mov     rcx, r15; char *
0x10045181c  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100451821  mov     r8d, 0C3B4h
0x100451827  mov     edx, ebx
0x100451829  mov     ecx, 7
0x10045182e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100451833  jmp     loc_1004519E1
0x100451838  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10045183e  mov     rdx, rdi; struct SNI_Packet *
0x100451841  mov     rcx, rsi; this
0x100451844  call    ?PrepareForAsyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForAsyncCall(SNI_Packet *)
0x100451849  mov     [rsp+0A8h+lpCompletionRoutine], r13; lpCompletionRoutine
0x10045184e  mov     [rsp+0A8h+lpOverlapped], r14; lpOverlapped
0x100451853  lea     rax, [rsp+0A8h+Flags]
0x10045185b  mov     [rsp+0A8h+lpFlags], rax; lpFlags
0x100451860  xor     r9d, r9d; lpNumberOfBytesRecvd
0x100451863  lea     r8d, [r9+1]; dwBufferCount
0x100451867  lea     rdx, [rsp+0A8h+Buffers]; lpBuffers
0x10045186c  mov     rcx, [rsi+40h]; s
0x100451870  call    cs:__imp_WSARecv
0x100451876  cmp     eax, 0FFFFFFFFh
0x100451879  jnz     short loc_1004518A2
0x10045187b  call    cs:__imp_WSAGetLastError
0x100451881  mov     ebx, eax
0x100451883  cmp     eax, 3E5h
0x100451888  jz      loc_1004519DC
0x10045188e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100451895  jz      short loc_100451821
0x100451897  mov     r8d, 186h
0x10045189d  jmp     loc_1004517FE
0x1004518a2  cmp     [rsi+3Dh], bl
0x1004518a5  jz      loc_1004519BB
0x1004518ab  xor     r9d, r9d; bWait
0x1004518ae  lea     r8, [rsp+0A8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1004518b6  mov     rdx, r14; lpOverlapped
0x1004518b9  mov     rcx, [rsi+40h]; hFile
0x1004518bd  call    cs:__imp_GetOverlappedResult
0x1004518c3  test    eax, eax
0x1004518c5  jnz     short loc_100451912
0x1004518c7  call    cs:__imp_GetLastError
0x1004518cd  mov     ebx, eax
0x1004518cf  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004518d5  test    al, 2
0x1004518d7  jz      loc_100451821
0x1004518dd  mov     dword ptr [rsp+0A8h+lpFlags], ebx
0x1004518e1  lea     r9, aErrSnigetoverl_0; "ERR|SNIGetOverlappedResult: %d{WINERR}"...
0x1004518e8  mov     r8d, 197h; int
0x1004518ee  mov     rdx, r12; char *
0x1004518f1  mov     rcx, r15; char *
0x1004518f4  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004518f9  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004518ff  test    al, 2
0x100451901  jz      loc_100451821
0x100451907  mov     r8d, 198h
0x10045190d  jmp     loc_1004517FE
0x100451912  mov     eax, [rsp+0A8h+NumberOfBytesTransferred]
0x100451919  test    eax, eax
0x10045191b  jnz     short loc_100451961
0x10045191d  mov     ebx, 2746h
0x100451922  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100451928  test    al, 2
0x10045192a  jz      loc_100451821
0x100451930  lea     r9, aErrSnisuccessf; "ERR|SNISuccessful 0-byte TCP read: retu"...
0x100451937  mov     r8d, 19Fh; int
0x10045193d  mov     rdx, r12; char *
0x100451940  mov     rcx, r15; char *
0x100451943  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100451948  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045194e  test    al, 2
0x100451950  jz      loc_100451821
0x100451956  mov     r8d, 1A0h
0x10045195c  jmp     loc_1004517FE
0x100451961  add     [rdi+0B0h], eax
0x100451967  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045196e  jz      short loc_100451993
0x100451970  mov     dword ptr [rsp+0A8h+lpFlags], eax
0x100451974  lea     r9, aSnireceivePack; "SNIReceive Packet, BytesRead:%d{DWORD}"...
0x10045197b  mov     r8d, 1AAh; int
0x100451981  mov     rdx, r12; char *
0x100451984  mov     rcx, r15; char *
0x100451987  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10045198c  mov     eax, [rsp+0A8h+NumberOfBytesTransferred]
0x100451993  test    cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 100h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045199d  jz      short loc_1004519E1
0x10045199f  mov     dword ptr [rsp+0A8h+lpFlags], eax; int
0x1004519a3  mov     r9, [rsp+0A8h+Buffers.buf]; void *
0x1004519a8  mov     r8d, 1ABh; int
0x1004519ae  mov     rdx, r12; char *
0x1004519b1  mov     rcx, r15; char *
0x1004519b4  call    ?SNIXE_SNI_SNIPKT_DATA_ON@@YAXPEBD0HPEBXH@Z; SNIXE_SNI_SNIPKT_DATA_ON(char const *,char const *,int,void const *,int)
0x1004519b9  jmp     short loc_1004519E1
0x1004519bb  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004519c2  jz      short loc_1004519DC
0x1004519c4  lea     r9, aSnisuppressing_0; "SNISuppressing successful read completi"...
0x1004519cb  mov     r8d, 1B4h; int
0x1004519d1  mov     rdx, r12; char *
0x1004519d4  mov     rcx, r15; char *
0x1004519d7  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004519dc  mov     ebx, 3E5h
0x1004519e1  mov     rax, [rsi+20h]
0x1004519e5  mov     rdi, [rax+32C0h]
0x1004519ec  cmp     [rax+31ADh], r13b
0x1004519f3  jz      short loc_100451A14
0x1004519f5  cmp     ebx, 3E5h
0x1004519fb  jnz     short loc_100451A09
0x1004519fd  mov     rax, [rdi]
0x100451a00  mov     rdx, r14
0x100451a03  mov     rcx, rdi
0x100451a06  call    qword ptr [rax+18h]
0x100451a09  mov     rax, [rdi]
0x100451a0c  xor     edx, edx
0x100451a0e  mov     rcx, rdi
0x100451a11  call    qword ptr [rax+20h]
0x100451a14  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100451a1b  jz      short loc_100451A3A
0x100451a1d  mov     dword ptr [rsp+0A8h+lpFlags], ebx
0x100451a21  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100451a28  mov     r8d, 1BEh; int
0x100451a2e  mov     rdx, r12; char *
0x100451a31  mov     rcx, r15; char *
0x100451a34  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100451a39  nop
0x100451a3a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100451a41  jz      short loc_100451A54
0x100451a43  mov     r8d, 156h; int
0x100451a49  mov     rdx, r12; char *
0x100451a4c  mov     rcx, r15; char *
0x100451a4f  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100451a54  mov     eax, ebx
0x100451a56  mov     rbx, [rsp+0A8h+arg_8]
0x100451a5e  add     rsp, 70h
0x100451a62  pop     r15
0x100451a64  pop     r14
0x100451a66  pop     r13
0x100451a68  pop     r12
0x100451a6a  pop     rdi
0x100451a6b  pop     rsi
0x100451a6c  pop     rbp
0x100451a6d  retn
```
