# TcpConnection::FInitForAsync(void)

- ea: `0x383ab3130`
- end: `0x383ab343f`
- name: `?FInitForAsync@TcpConnection@@QEAAKXZ`
- size: `783`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x38388d090`
- `0x383ab4360`

## callees

- `0x3838911c0`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab3130`

## import_xrefs

- `KERNEL32!CreateEventA` at `0x383ab31d5`
- `KERNEL32!CreateEventA` at `0x383ab31d5`
- `KERNEL32!GetLastError` at `0x383ab31e7`
- `KERNEL32!GetLastError` at `0x383ab31e7`
- `WS2_32!__imp_bind` at `0x383ab3330`
- `WS2_32!__imp_bind` at `0x383ab3330`
- `WS2_32!__imp_WSAGetLastError` at `0x383ab32d0`
- `WS2_32!__imp_WSAGetLastError` at `0x383ab333b`
- `WS2_32!__imp_WSAGetLastError` at `0x383ab32d0`
- `WS2_32!__imp_WSAGetLastError` at `0x383ab333b`
- `WS2_32!__imp_WSASetLastError` at `0x383ab32c6`
- `WS2_32!__imp_WSASetLastError` at `0x383ab32c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpConnection::FInitForAsync(TcpConnection *this)
{
  _QWORD *v2; // rax
  unsigned int Error; // ebx
  HANDLE EventA; // rax
  DWORD LastError; // eax
  char *l; // rax
  int v7; // ebx
  __int64 v8; // rdi
  char *v9; // rax
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF
  __int64 v13; // [rsp+40h] [rbp-38h]
  __int64 v14; // [rsp+48h] [rbp-30h]
  __int64 v15; // [rsp+50h] [rbp-28h]
  __int64 v16; // [rsp+58h] [rbp-20h]
  __int64 v17; // [rsp+60h] [rbp-18h]
  __int64 v18; // [rsp+80h] [rbp+8h] BYREF
  __int64 v19; // [rsp+88h] [rbp+10h] BYREF

  v19 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && `TcpConnection::FInitForAsync'::`7'::_bidPtrSA_040_2939[0] )
    bidScopeEnterA(&v19, `TcpConnection::FInitForAsync'::`7'::_bidPtrSA_040_2939[0], *((unsigned int *)this + 11));
  v18 = 0;
  v2 = (_QWORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 32);
  *(_QWORD *)this = v2;
  if ( v2 )
  {
    *v2 = 0;
    v2[1] = 0;
    v2[2] = 0;
    v2[3] = 0;
    EventA = CreateEventA(0, 1, 0, 0);
    *((_QWORD *)this + 2) = EventA;
    if ( EventA )
    {
      *(_QWORD *)(*(_QWORD *)this + 24LL) = EventA;
      v12 = 0;
      v13 = 0;
      v14 = 0;
      v15 = 0;
      v16 = 0;
      v17 = 0;
      HIDWORD(v12) = *(_DWORD *)(*((_QWORD *)this + 1) + 4LL);
      LODWORD(v13) = 1;
      LODWORD(v12) = 1;
      l = (char *)`WspiapiGetAddrInfo_l'::`2'::pfGetAddrInfo;
      if ( !`WspiapiGetAddrInfo_l'::`2'::pfGetAddrInfo )
      {
        l = WspiapiLoad_l(0, &`WspiapiGetAddrInfo_l'::`2'::bNeedsLocale);
        `WspiapiGetAddrInfo_l'::`2'::pfGetAddrInfo = (__int64)l;
      }
      if ( `WspiapiGetAddrInfo_l'::`2'::bNeedsLocale )
        v11 = 0;
      v7 = ((__int64 (__fastcall *)(_QWORD, const char *, __int64 *, __int64 *))l)(0, "0", &v12, &v18);
      WSASetLastError(v7);
      if ( v7 )
      {
        Error = WSAGetLastError();
        *((_DWORD *)this + 9) = Error;
        *((_DWORD *)this + 10) = 3;
        if ( (bidGblFlags & 2) != 0 && `TcpConnection::FInitForAsync'::`32'::_bidPtrSA_030_2978[0] )
          bidTraceA(
            `TcpConnection::FInitForAsync'::`32'::_bidSrcFileA[0],
            3049472,
            `TcpConnection::FInitForAsync'::`32'::_bidPtrSA_030_2978[0],
            Error,
            v11);
      }
      else if ( bind(*((_QWORD *)this + 3), *(const struct sockaddr **)(v18 + 32), *(_DWORD *)(v18 + 16)) == -1 )
      {
        Error = WSAGetLastError();
        *((_DWORD *)this + 9) = Error;
        *((_DWORD *)this + 10) = 5;
        if ( (bidGblFlags & 2) != 0 && `TcpConnection::FInitForAsync'::`42'::_bidPtrSA_030_2988[0] )
          bidTraceA(
            `TcpConnection::FInitForAsync'::`42'::_bidSrcFileA[0],
            3059712,
            `TcpConnection::FInitForAsync'::`42'::_bidPtrSA_030_2988[0],
            Error,
            v11);
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
      if ( (bidGblFlags & 2) != 0 && `TcpConnection::FInitForAsync'::`22'::_bidPtrSA_030_2963[0] )
        bidTraceA(
          `TcpConnection::FInitForAsync'::`22'::_bidSrcFileA[0],
          3034112,
          `TcpConnection::FInitForAsync'::`22'::_bidPtrSA_030_2963[0],
          LastError,
          v11);
    }
  }
  else
  {
    Error = 14;
    *((_DWORD *)this + 9) = 14;
    *((_DWORD *)this + 10) = 2;
  }
  v8 = v18;
  if ( v18 )
  {
    v9 = (char *)`WspiapiFreeAddrInfo'::`2'::pfFreeAddrInfo;
    if ( !`WspiapiFreeAddrInfo'::`2'::pfFreeAddrInfo )
    {
      v9 = WspiapiLoad_l(2u, `WspiapiFreeAddrInfo'::`2'::bNeedsLocale);
      `WspiapiFreeAddrInfo'::`2'::pfFreeAddrInfo = (__int64)v9;
    }
    ((void (__fastcall *)(__int64))v9)(v8);
    v18 = 0;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && `TcpConnection::FInitForAsync'::`52'::_bidPtrSA_030_3008[0] )
    bidTraceA(
      `TcpConnection::FInitForAsync'::`52'::_bidSrcFileA[0],
      3080192,
      `TcpConnection::FInitForAsync'::`52'::_bidPtrSA_030_3008[0],
      Error,
      v11);
  if ( v19 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return Error;
}

```

## disassembly

```asm
0x383ab3130  mov     r11, rsp
0x383ab3133  push    rdi
0x383ab3134  sub     rsp, 70h
0x383ab3138  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x383ab3140  mov     [r11+18h], rbx
0x383ab3144  mov     rdi, rcx
0x383ab3147  mov     qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x383ab314f  mov     eax, cs:_bidGblFlags
0x383ab3155  and     eax, 20004h
0x383ab315a  cmp     eax, 20004h
0x383ab315f  jnz     short loc_383AB3181
0x383ab3161  mov     rax, cs:?_bidPtrSA_040_2939@?6??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`7'::_bidPtrSA_040_2939
0x383ab3168  test    rax, rax
0x383ab316b  jz      short loc_383AB3181
0x383ab316d  mov     r8d, [rcx+2Ch]
0x383ab3171  mov     rdx, cs:?_bidPtrSA_040_2939@?6??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`7'::_bidPtrSA_040_2939
0x383ab3178  lea     rcx, [r11+10h]
0x383ab317c  call    _bidScopeEnterA
0x383ab3181  mov     [rsp+78h+arg_0], 0
0x383ab318d  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x383ab3194  mov     rax, [rcx]
0x383ab3197  mov     edx, 20h ; ' '
0x383ab319c  call    qword ptr [rax+58h]
0x383ab319f  mov     [rdi], rax
0x383ab31a2  test    rax, rax
0x383ab31a5  jnz     short loc_383AB31BB
0x383ab31a7  mov     ebx, 0Eh
0x383ab31ac  mov     [rdi+24h], ebx
0x383ab31af  mov     dword ptr [rdi+28h], 2
0x383ab31b6  jmp     loc_383AB3381
0x383ab31bb  xor     ecx, ecx; lpEventAttributes
0x383ab31bd  mov     [rax], rcx
0x383ab31c0  mov     [rax+8], rcx
0x383ab31c4  mov     [rax+10h], rcx
0x383ab31c8  mov     [rax+18h], rcx
0x383ab31cc  xor     r9d, r9d; lpName
0x383ab31cf  xor     r8d, r8d; bInitialState
0x383ab31d2  lea     edx, [rcx+1]; bManualReset
0x383ab31d5  call    cs:__imp_CreateEventA
0x383ab31db  mov     r11, rax
0x383ab31de  mov     [rdi+10h], rax
0x383ab31e2  test    rax, rax
0x383ab31e5  jnz     short loc_383AB3236
0x383ab31e7  call    cs:__imp_GetLastError
0x383ab31ed  mov     ebx, eax
0x383ab31ef  mov     [rdi+24h], eax
0x383ab31f2  mov     dword ptr [rdi+28h], 3
0x383ab31f9  test    byte ptr cs:_bidGblFlags, 2
0x383ab3200  jz      loc_383AB3381
0x383ab3206  mov     rcx, cs:?_bidPtrSA_030_2963@?BG@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`22'::_bidPtrSA_030_2963
0x383ab320d  test    rcx, rcx
0x383ab3210  jz      loc_383AB3381
0x383ab3216  mov     r9d, eax
0x383ab3219  mov     r8, cs:?_bidPtrSA_030_2963@?BG@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`22'::_bidPtrSA_030_2963
0x383ab3220  mov     edx, 2E4C00h
0x383ab3225  mov     rcx, cs:?_bidSrcFileA@?BG@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`22'::_bidSrcFileA
0x383ab322c  call    _bidTraceA
0x383ab3231  jmp     loc_383AB3381
0x383ab3236  mov     rax, [rdi]
0x383ab3239  mov     [rax+18h], r11
0x383ab323d  xor     eax, eax
0x383ab323f  mov     [rsp+78h+var_40], rax
0x383ab3244  mov     [rsp+78h+var_38], rax
0x383ab3249  mov     [rsp+78h+var_30], rax
0x383ab324e  mov     [rsp+78h+var_28], rax
0x383ab3253  mov     [rsp+78h+var_20], rax
0x383ab3258  mov     [rsp+78h+var_18], rax
0x383ab325d  mov     rax, [rdi+8]
0x383ab3261  mov     ecx, [rax+4]
0x383ab3264  mov     dword ptr [rsp+78h+var_40+4], ecx
0x383ab3268  mov     dword ptr [rsp+78h+var_38], 1
0x383ab3270  mov     dword ptr [rsp+78h+var_40], 1
0x383ab3278  mov     rax, cs:?pfGetAddrInfo@?1??WspiapiGetAddrInfo_l@@9@4P6A_JXZEA; __int64 (*`WspiapiGetAddrInfo_l'::`2'::pfGetAddrInfo)(void)
0x383ab327f  test    rax, rax
0x383ab3282  jnz     short loc_383AB3299
0x383ab3284  xor     ecx, ecx
0x383ab3286  lea     rdx, ?bNeedsLocale@?1??WspiapiGetAddrInfo_l@@9@4HA; int `WspiapiGetAddrInfo_l'::`2'::bNeedsLocale
0x383ab328d  call    WspiapiLoad_l
0x383ab3292  mov     cs:?pfGetAddrInfo@?1??WspiapiGetAddrInfo_l@@9@4P6A_JXZEA, rax; __int64 (*`WspiapiGetAddrInfo_l'::`2'::pfGetAddrInfo)(void)
0x383ab3299  lea     r9, [rsp+78h+arg_0]
0x383ab32a1  lea     r8, [rsp+78h+var_40]
0x383ab32a6  lea     rdx, a0; "0"
0x383ab32ad  xor     ecx, ecx
0x383ab32af  cmp     cs:?bNeedsLocale@?1??WspiapiGetAddrInfo_l@@9@4HA, ecx; int `WspiapiGetAddrInfo_l'::`2'::bNeedsLocale
0x383ab32b5  jz      short loc_383AB32C0
0x383ab32b7  mov     qword ptr [rsp+78h+var_58], rcx
0x383ab32bc  call    rax ; __int64 (*`WspiapiGetAddrInfo_l'::`2'::pfGetAddrInfo)(void)
0x383ab32be  jmp     short loc_383AB32C2
0x383ab32c0  call    rax ; __int64 (*`WspiapiGetAddrInfo_l'::`2'::pfGetAddrInfo)(void)
0x383ab32c2  mov     ebx, eax
0x383ab32c4  mov     ecx, eax; iError
0x383ab32c6  call    cs:__imp_WSASetLastError
0x383ab32cc  test    ebx, ebx
0x383ab32ce  jz      short loc_383AB331C
0x383ab32d0  call    cs:__imp_WSAGetLastError
0x383ab32d6  mov     ebx, eax
0x383ab32d8  mov     [rdi+24h], eax
0x383ab32db  mov     dword ptr [rdi+28h], 3
0x383ab32e2  test    byte ptr cs:_bidGblFlags, 2
0x383ab32e9  jz      loc_383AB3381
0x383ab32ef  mov     rax, cs:?_bidPtrSA_030_2978@?CA@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`32'::_bidPtrSA_030_2978
0x383ab32f6  test    rax, rax
0x383ab32f9  jz      loc_383AB3381
0x383ab32ff  mov     r9d, ebx
0x383ab3302  mov     r8, cs:?_bidPtrSA_030_2978@?CA@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`32'::_bidPtrSA_030_2978
0x383ab3309  mov     edx, 2E8800h
0x383ab330e  mov     rcx, cs:?_bidSrcFileA@?CA@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`32'::_bidSrcFileA
0x383ab3315  call    _bidTraceA
0x383ab331a  jmp     short loc_383AB3381
0x383ab331c  mov     rdx, [rsp+78h+arg_0]
0x383ab3324  mov     r8d, [rdx+10h]; namelen
0x383ab3328  mov     rdx, [rdx+20h]; name
0x383ab332c  mov     rcx, [rdi+18h]; s
0x383ab3330  call    cs:__imp_bind
0x383ab3336  cmp     eax, 0FFFFFFFFh
0x383ab3339  jnz     short loc_383AB337F
0x383ab333b  call    cs:__imp_WSAGetLastError
0x383ab3341  mov     ebx, eax
0x383ab3343  mov     [rdi+24h], eax
0x383ab3346  mov     dword ptr [rdi+28h], 5
0x383ab334d  test    byte ptr cs:_bidGblFlags, 2
0x383ab3354  jz      short loc_383AB3381
0x383ab3356  mov     rax, cs:?_bidPtrSA_030_2988@?CK@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`42'::_bidPtrSA_030_2988
0x383ab335d  test    rax, rax
0x383ab3360  jz      short loc_383AB3381
0x383ab3362  mov     r9d, ebx
0x383ab3365  mov     r8, cs:?_bidPtrSA_030_2988@?CK@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`42'::_bidPtrSA_030_2988
0x383ab336c  mov     edx, 2EB000h
0x383ab3371  mov     rcx, cs:?_bidSrcFileA@?CK@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`42'::_bidSrcFileA
0x383ab3378  call    _bidTraceA
0x383ab337d  jmp     short loc_383AB3381
0x383ab337f  xor     ebx, ebx
0x383ab3381  mov     rdi, [rsp+78h+arg_0]
0x383ab3389  test    rdi, rdi
0x383ab338c  jz      short loc_383AB33C1
0x383ab338e  mov     rax, cs:?pfFreeAddrInfo@?1??WspiapiFreeAddrInfo@@9@4P6AXPEAUaddrinfo@@@ZEA; void (*`WspiapiFreeAddrInfo'::`2'::pfFreeAddrInfo)(addrinfo *)
0x383ab3395  test    rax, rax
0x383ab3398  jnz     short loc_383AB33B0
0x383ab339a  lea     ecx, [rax+2]
0x383ab339d  lea     rdx, ?bNeedsLocale@?1??WspiapiFreeAddrInfo@@9@4HA; int `WspiapiFreeAddrInfo'::`2'::bNeedsLocale
0x383ab33a4  call    WspiapiLoad_l
0x383ab33a9  mov     cs:?pfFreeAddrInfo@?1??WspiapiFreeAddrInfo@@9@4P6AXPEAUaddrinfo@@@ZEA, rax; void (*`WspiapiFreeAddrInfo'::`2'::pfFreeAddrInfo)(addrinfo *)
0x383ab33b0  mov     rcx, rdi
0x383ab33b3  call    rax ; void (*`WspiapiFreeAddrInfo'::`2'::pfFreeAddrInfo)(addrinfo *)
0x383ab33b5  mov     [rsp+78h+arg_0], 0
0x383ab33c1  mov     eax, cs:_bidGblFlags
0x383ab33c7  and     eax, 20002h
0x383ab33cc  cmp     eax, 20002h
0x383ab33d1  jnz     short loc_383AB33FB
0x383ab33d3  mov     rax, cs:?_bidPtrSA_030_3008@?DE@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`52'::_bidPtrSA_030_3008
0x383ab33da  test    rax, rax
0x383ab33dd  jz      short loc_383AB33FB
0x383ab33df  mov     r9d, ebx
0x383ab33e2  mov     r8, cs:?_bidPtrSA_030_3008@?DE@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`52'::_bidPtrSA_030_3008
0x383ab33e9  mov     edx, 2F0000h
0x383ab33ee  mov     rcx, cs:?_bidSrcFileA@?DE@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`52'::_bidSrcFileA
0x383ab33f5  call    _bidTraceA
0x383ab33fa  nop
0x383ab33fb  cmp     [rsp+78h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383ab3404  jz      short loc_383AB342F
0x383ab3406  test    byte ptr cs:_bidGblFlags, 4
0x383ab340d  jz      short loc_383AB342F
0x383ab340f  mov     rcx, cs:_bidID
0x383ab3416  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ab341a  jz      short loc_383AB342F
0x383ab341c  lea     r9, [rsp+78h+arg_8]
0x383ab3424  xor     r8d, r8d
0x383ab3427  xor     edx, edx
0x383ab3429  call    cs:off_383B15058
0x383ab342f  mov     eax, ebx
0x383ab3431  mov     rbx, [rsp+78h+arg_10]
0x383ab3439  add     rsp, 70h
0x383ab343d  pop     rdi
0x383ab343e  retn
```
