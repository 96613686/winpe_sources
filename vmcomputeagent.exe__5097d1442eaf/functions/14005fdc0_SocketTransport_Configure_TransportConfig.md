# SocketTransport::Configure(TransportConfig *)

- ea: `0x14005fdc0`
- end: `0x14006017a`
- name: `?Configure@SocketTransport@@UEAAXPEAVTransportConfig@@@Z`
- size: `954`
- prototype: `void __fastcall(SocketTransport *__hidden this, struct TransportConfig *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x1400341ac`
- `0x14003ac0c`
- `0x14005f9cc`
- `0x14005fdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005ff18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14005ff18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005fed0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005fed0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fed6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005fed6`
- `WS2_32!WSAIoctl` at `0x140060034`
- `WS2_32!WSAIoctl` at `0x140060077`
- `WS2_32!WSAIoctl` at `0x140060034`
- `WS2_32!WSAIoctl` at `0x140060077`
- `WS2_32!WSASocketW` at `0x14005ffe1`
- `WS2_32!WSASocketW` at `0x14005ffe1`
- `WS2_32!__imp_closesocket` at `0x140060094`
- `WS2_32!__imp_closesocket` at `0x140060094`
- `WS2_32!__imp_WSAGetLastError` at `0x1400600c1`
- `WS2_32!__imp_WSAGetLastError` at `0x140060136`
- `WS2_32!__imp_WSAGetLastError` at `0x140060158`
- `WS2_32!__imp_WSAGetLastError` at `0x1400600c1`
- `WS2_32!__imp_WSAGetLastError` at `0x140060136`
- `WS2_32!__imp_WSAGetLastError` at `0x140060158`
- `WS2_32!__imp_WSAStartup` at `0x14005ff95`
- `WS2_32!__imp_WSAStartup` at `0x14005ff95`

## string_xrefs

- `0x1400600d2`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400600f1`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x14006010f`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060124`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060146`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060168`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall SocketTransport::Configure(SocketTransport *this, struct TransportConfig *a2)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v8; // r8d
  int v9; // ecx
  SOCKET v10; // rbx
  unsigned int v11; // eax
  unsigned int Error; // eax
  unsigned int v13; // eax
  unsigned int g; // [rsp+20h] [rbp-E0h]
  unsigned int ga; // [rsp+20h] [rbp-E0h]
  unsigned int gb; // [rsp+20h] [rbp-E0h]
  unsigned int gc; // [rsp+20h] [rbp-E0h]
  _QWORD v18[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h]
  char *v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbBytesReturned; // [rsp+7Ch] [rbp-84h] BYREF
  _DWORD vInBuffer[4]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v24[4]; // [rsp+90h] [rbp-70h] BYREF
  WSAData WSAData; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  memset_0(&WSAData, 0, sizeof(WSAData));
  vInBuffer[0] = -1254720015;
  vInBuffer[1] = 298830764;
  vInBuffer[2] = -2147431787;
  vInBuffer[3] = -1834923937;
  v24[0] = 631375801;
  v24[1] = 1180753395;
  v24[2] = -445191794;
  v24[3] = 1040610444;
  cbBytesReturned = 0;
  v21 = 0;
  if ( *(_DWORD *)a2 == 2 )
  {
    *(_OWORD *)((char *)this + 52) = *(_OWORD *)a2;
    *(_OWORD *)((char *)this + 68) = *((_OWORD *)a2 + 1);
    *((_OWORD *)this + 5) = *(_OWORD *)((char *)a2 + 28);
    *((_DWORD *)this + 25) = 34;
    *((_DWORD *)this + 26) = 1;
  }
  else
  {
    if ( *(_DWORD *)a2 == 3 )
    {
      *(_OWORD *)((char *)this + 8) = *(_OWORD *)a2;
      *((_DWORD *)this + 25) = 2;
    }
    else
    {
      if ( *(_DWORD *)a2 != 4 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xC6,
          (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
          (const char *)0x57,
          g);
      *(_OWORD *)((char *)this + 24) = *(_OWORD *)a2;
      *(_OWORD *)((char *)this + 36) = *(_OWORD *)((char *)a2 + 12);
      *((_DWORD *)this + 25) = 23;
    }
    *((_DWORD *)this + 26) = 6;
  }
  *((_DWORD *)this + 24) = *(_DWORD *)a2;
  *((_BYTE *)this + 108) = *((_BYTE *)a2 + 4);
  AcquireSRWLockExclusive((PSRWLOCK)this + 25);
  *((_DWORD *)this + 52) = GetCurrentThreadId();
  v20 = (char *)this + 200;
  v4 = *((_DWORD *)this + 57);
  v21 = v4;
  if ( v4 )
  {
    if ( v4 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)0x139F,
        g);
    *((_BYTE *)this + 232) = 1;
    v5 = 3;
  }
  else
  {
    v5 = 1;
  }
  *((_DWORD *)this + 57) = v5;
  *((_DWORD *)this + 52) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
  v19 = 256;
  v18[0] = this;
  v18[1] = &v21;
  if ( *((_DWORD *)this + 25) == 34 )
  {
    *((_DWORD *)this + 44) = 52;
    v6 = 104;
  }
  else if ( *((_DWORD *)this + 25) == 2 )
  {
    *((_DWORD *)this + 44) = 32;
    v6 = 64;
  }
  else
  {
    *((_DWORD *)this + 44) = 44;
    v6 = 88;
  }
  std::vector<unsigned char>::resize((char *)this + 152, v6);
  v7 = WSAStartup(0x202u, &WSAData);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)v7,
      g);
  *((_BYTE *)this + 384) = 1;
  if ( *((_DWORD *)this + 25) == 34 )
  {
    v8 = 1;
    v9 = 34;
  }
  else
  {
    v8 = 6;
    v9 = 2;
    if ( *((_DWORD *)this + 25) != 2 )
      v9 = 23;
  }
  v10 = WSASocketW(v9, 1, v8, 0, 0, 0);
  if ( v10 == -1 )
  {
    Error = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)Error,
      ga);
  }
  if ( WSAIoctl(v10, 0xC8000006, vInBuffer, 0x10u, (char *)this + 184, 8u, &cbBytesReturned, 0, 0) )
  {
    v13 = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)v13,
      gb);
  }
  if ( WSAIoctl(v10, 0xC8000006, v24, 0x10u, (char *)this + 192, 8u, &cbBytesReturned, 0, 0) )
  {
    v11 = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)v11,
      gc);
  }
  BYTE1(v19) = 0;
  wil::details::ScopeExitFnGuard__lambda_f7ca47784f5b5f848b74f9c6192a0e9e___::operator()(v18);
  closesocket(v10);
}

```

## disassembly

```asm
0x14005fdc0  mov     [rsp-8+arg_8], rbx
0x14005fdc5  mov     [rsp-8+arg_10], rsi
0x14005fdca  push    rbp
0x14005fdcb  push    rdi
0x14005fdcc  push    r14
0x14005fdce  lea     rbp, [rsp-150h]
0x14005fdd6  sub     rsp, 250h
0x14005fddd  mov     rax, cs:__security_cookie
0x14005fde4  xor     rax, rsp
0x14005fde7  mov     [rbp+160h+var_20], rax
0x14005fdee  mov     rbx, rdx
0x14005fdf1  mov     rdi, rcx
0x14005fdf4  xor     edx, edx; Val
0x14005fdf6  mov     r8d, 198h; Size
0x14005fdfc  lea     rcx, [rbp+160h+WSAData]; void *
0x14005fe00  call    memset_0
0x14005fe05  mov     [rsp+260h+var_210], 0FFFFFFFFFFFFFFFFh
0x14005fe0e  mov     [rbp+160h+vInBuffer], 0B5367DF1h
0x14005fe15  mov     [rbp+160h+var_1DC], 11CFCBACh
0x14005fe1c  mov     [rbp+160h+var_1D8], 8000CA95h
0x14005fe23  xor     esi, esi
0x14005fe25  mov     [rbp+160h+var_1D4], 92A1485Fh
0x14005fe2c  mov     [rbp+160h+var_1D0], 25A207B9h
0x14005fe33  mov     [rbp+160h+var_1CC], 4660DDF3h
0x14005fe3a  mov     [rbp+160h+var_1C8], 0E576E98Eh
0x14005fe41  mov     [rbp+160h+var_1C4], 3E06748Ch
0x14005fe48  mov     [rsp+260h+cbBytesReturned], esi
0x14005fe4c  mov     [rsp+260h+var_1E8], esi
0x14005fe50  mov     ecx, [rbx]
0x14005fe52  lea     r14d, [rsi+1]
0x14005fe56  sub     ecx, 2
0x14005fe59  jz      short loc_14005FE99
0x14005fe5b  sub     ecx, r14d
0x14005fe5e  jz      short loc_14005FE81
0x14005fe60  cmp     ecx, r14d
0x14005fe63  jnz     loc_1400600E4
0x14005fe69  movups  xmm0, xmmword ptr [rbx]
0x14005fe6c  movups  xmmword ptr [rdi+18h], xmm0
0x14005fe70  movups  xmm1, xmmword ptr [rbx+0Ch]
0x14005fe74  movups  xmmword ptr [rdi+24h], xmm1
0x14005fe78  mov     dword ptr [rdi+64h], 17h
0x14005fe7f  jmp     short loc_14005FE90
0x14005fe81  movups  xmm0, xmmword ptr [rbx]
0x14005fe84  movdqu  xmmword ptr [rdi+8], xmm0
0x14005fe89  mov     dword ptr [rdi+64h], 2
0x14005fe90  mov     dword ptr [rdi+68h], 6
0x14005fe97  jmp     short loc_14005FEBB
0x14005fe99  movups  xmm0, xmmword ptr [rbx]
0x14005fe9c  movups  xmmword ptr [rdi+34h], xmm0
0x14005fea0  movups  xmm1, xmmword ptr [rbx+10h]
0x14005fea4  movups  xmmword ptr [rdi+44h], xmm1
0x14005fea8  movups  xmm0, xmmword ptr [rbx+1Ch]
0x14005feac  movups  xmmword ptr [rdi+50h], xmm0
0x14005feb0  mov     dword ptr [rdi+64h], 22h ; '"'
0x14005feb7  mov     [rdi+68h], r14d
0x14005febb  mov     eax, [rbx]
0x14005febd  mov     [rdi+60h], eax
0x14005fec0  mov     al, [rbx+4]
0x14005fec3  mov     [rdi+6Ch], al
0x14005fec6  lea     rbx, [rdi+0C8h]
0x14005fecd  mov     rcx, rbx; SRWLock
0x14005fed0  call    cs:__imp_AcquireSRWLockExclusive
0x14005fed6  call    cs:__imp_GetCurrentThreadId
0x14005fedc  mov     [rbx+8], eax
0x14005fedf  mov     [rsp+260h+var_1F0], rbx
0x14005fee4  mov     eax, [rdi+0E4h]
0x14005feea  mov     [rsp+260h+var_1E8], eax
0x14005feee  test    eax, eax
0x14005fef0  jz      short loc_14005FF09
0x14005fef2  cmp     eax, 2
0x14005fef5  jnz     loc_140060102
0x14005fefb  mov     [rdi+0E8h], r14b
0x14005ff02  mov     eax, 3
0x14005ff07  jmp     short loc_14005FF0C
0x14005ff09  mov     eax, r14d
0x14005ff0c  mov     [rdi+0E4h], eax
0x14005ff12  mov     [rbx+8], esi
0x14005ff15  mov     rcx, rbx; SRWLock
0x14005ff18  call    cs:__imp_ReleaseSRWLockExclusive
0x14005ff1e  xorps   xmm0, xmm0
0x14005ff21  xor     eax, eax
0x14005ff23  movups  [rsp+260h+var_208], xmm0
0x14005ff28  mov     [rsp+260h+var_1F8], rax
0x14005ff2d  mov     qword ptr [rsp+260h+var_208], rdi
0x14005ff32  lea     rax, [rsp+260h+var_1E8]
0x14005ff37  mov     qword ptr [rsp+260h+var_208+8], rax
0x14005ff3c  mov     word ptr [rsp+260h+var_1F8], 100h
0x14005ff43  cmp     dword ptr [rdi+64h], 22h ; '"'
0x14005ff47  jnz     short loc_14005FF5A
0x14005ff49  mov     dword ptr [rdi+0B0h], 34h ; '4'
0x14005ff53  mov     edx, 68h ; 'h'
0x14005ff58  jmp     short loc_14005FF80
0x14005ff5a  cmp     dword ptr [rdi+64h], 2
0x14005ff5e  jnz     short loc_14005FF71
0x14005ff60  mov     dword ptr [rdi+0B0h], 20h ; ' '
0x14005ff6a  mov     edx, 40h ; '@'
0x14005ff6f  jmp     short loc_14005FF80
0x14005ff71  mov     dword ptr [rdi+0B0h], 2Ch ; ','
0x14005ff7b  mov     edx, 58h ; 'X'
0x14005ff80  lea     rcx, [rdi+98h]
0x14005ff87  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x14005ff8c  mov     ecx, 202h; wVersionRequested
0x14005ff91  lea     rdx, [rbp+160h+WSAData]; lpWSAData
0x14005ff95  call    cs:__imp_WSAStartup
0x14005ff9b  mov     rcx, [rbp+168h]; this
0x14005ffa2  test    eax, eax
0x14005ffa4  jnz     loc_140060121
0x14005ffaa  mov     [rdi+180h], r14b
0x14005ffb1  cmp     dword ptr [rdi+64h], 22h ; '"'
0x14005ffb5  jnz     short loc_14005FFBF
0x14005ffb7  mov     r8d, r14d
0x14005ffba  lea     ecx, [rax+22h]
0x14005ffbd  jmp     short loc_14005FFD3
0x14005ffbf  mov     r8d, 6; protocol
0x14005ffc5  cmp     dword ptr [rdi+64h], 2
0x14005ffc9  lea     ecx, [r8-4]
0x14005ffcd  jz      short loc_14005FFD3
0x14005ffcf  lea     ecx, [r8+11h]; af
0x14005ffd3  mov     [rsp+260h+dwFlags], esi; dwFlags
0x14005ffd7  mov     [rsp+260h+g], esi; unsigned int
0x14005ffdb  xor     r9d, r9d; lpProtocolInfo
0x14005ffde  mov     edx, r14d; type
0x14005ffe1  call    cs:__imp_WSASocketW
0x14005ffe7  mov     rbx, rax
0x14005ffea  mov     [rsp+260h+var_210], rax
0x14005ffef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005fff3  jz      loc_140060136
0x14005fff9  lea     rax, [rdi+0B8h]
0x140060000  mov     [rsp+260h+lpCompletionRoutine], rsi; lpCompletionRoutine
0x140060005  mov     [rsp+260h+lpOverlapped], rsi; lpOverlapped
0x14006000a  lea     rcx, [rsp+260h+cbBytesReturned]
0x14006000f  mov     [rsp+260h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x140060014  mov     r14d, 8
0x14006001a  mov     [rsp+260h+dwFlags], r14d; cbOutBuffer
0x14006001f  mov     qword ptr [rsp+260h+g], rax; unsigned int
0x140060024  lea     r9d, [r14+8]; cbInBuffer
0x140060028  lea     r8, [rbp+160h+vInBuffer]; lpvInBuffer
0x14006002c  mov     edx, 0C8000006h; dwIoControlCode
0x140060031  mov     rcx, rbx; s
0x140060034  call    cs:__imp_WSAIoctl
0x14006003a  test    eax, eax
0x14006003c  jnz     loc_140060158
0x140060042  lea     rax, [rdi+0C0h]
0x140060049  mov     [rsp+260h+lpCompletionRoutine], rsi; lpCompletionRoutine
0x14006004e  mov     [rsp+260h+lpOverlapped], rsi; lpOverlapped
0x140060053  lea     rcx, [rsp+260h+cbBytesReturned]
0x140060058  mov     [rsp+260h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x14006005d  mov     [rsp+260h+dwFlags], r14d; cbOutBuffer
0x140060062  mov     qword ptr [rsp+260h+g], rax; unsigned int
0x140060067  lea     r9d, [r14+8]; cbInBuffer
0x14006006b  lea     r8, [rbp+160h+var_1D0]; lpvInBuffer
0x14006006f  mov     edx, 0C8000006h; dwIoControlCode
0x140060074  mov     rcx, rbx; s
0x140060077  call    cs:__imp_WSAIoctl
0x14006007d  test    eax, eax
0x14006007f  jnz     short loc_1400600C1
0x140060081  mov     byte ptr [rsp+260h+var_1F8+1], sil
0x140060086  lea     rcx, [rsp+260h+var_208]
0x14006008b  call    wil__details__ScopeExitFnGuard__lambda_f7ca47784f5b5f848b74f9c6192a0e9e_____operator__
0x140060090  nop
0x140060091  mov     rcx, rbx; s
0x140060094  call    cs:__imp_closesocket
0x14006009a  mov     rcx, [rbp+160h+var_20]
0x1400600a1  xor     rcx, rsp; StackCookie
0x1400600a4  call    __security_check_cookie
0x1400600a9  lea     r11, [rsp+260h+var_10]
0x1400600b1  mov     rbx, [r11+28h]
0x1400600b5  mov     rsi, [r11+30h]
0x1400600b9  mov     rsp, r11
0x1400600bc  pop     r14
0x1400600be  pop     rdi
0x1400600bf  pop     rbp
0x1400600c0  retn
0x1400600c1  call    cs:__imp_WSAGetLastError
0x1400600c7  nop
0x1400600c8  mov     r9d, eax; char *
0x1400600cb  mov     rcx, [rbp+168h]; this
0x1400600d2  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x1400600d9  mov     edx, 135h; void *
0x1400600de  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400600e4  mov     rcx, [rbp+168h]; this
0x1400600eb  mov     r9d, 57h ; 'W'; char *
0x1400600f1  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x1400600f8  lea     edx, [r9+6Fh]; void *
0x1400600fc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060102  mov     rcx, [rbp+168h]; this
0x140060109  mov     r9d, 139Fh; char *
0x14006010f  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060116  mov     edx, 0E2h; void *
0x14006011b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060121  mov     r9d, eax; char *
0x140060124  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x14006012b  mov     edx, 105h; void *
0x140060130  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060136  call    cs:__imp_WSAGetLastError
0x14006013c  mov     r9d, eax; char *
0x14006013f  mov     rcx, [rbp+168h]; this
0x140060146  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x14006014d  mov     edx, 11Bh; void *
0x140060152  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060158  call    cs:__imp_WSAGetLastError
0x14006015e  mov     r9d, eax; char *
0x140060161  mov     rcx, [rbp+168h]; this
0x140060168  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x14006016f  mov     edx, 128h; void *
0x140060174  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
