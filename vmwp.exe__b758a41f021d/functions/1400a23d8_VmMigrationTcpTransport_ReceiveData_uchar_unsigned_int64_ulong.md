# VmMigrationTcpTransport::ReceiveData(uchar *,unsigned __int64,ulong)

- ea: `0x1400a23d8`
- end: `0x1400a262b`
- name: `?ReceiveData@VmMigrationTcpTransport@@IEAAJPEAE_KK@Z`
- size: `595`
- prototype: `int(VmMigrationTcpTransport *__hidden this, unsigned __int8 *, unsigned __int64, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400a2c10`
- `0x1401ce8a0`
- `0x1401cf9c0`
- `0x1401cfab0`

## callees

- `0x140078628`
- `0x1400a06d0`
- `0x1400a23d8`
- `0x1400ba144`
- `0x14011ea40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400a2463`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400a2463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a24a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a24a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400a2400`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400a2400`
- `WS2_32!WSAEnumNetworkEvents` at `0x1400a2501`
- `WS2_32!WSAEnumNetworkEvents` at `0x1400a2501`
- `WS2_32!__imp_recv` at `0x1400a2573`
- `WS2_32!__imp_recv` at `0x1400a2573`
- `WS2_32!__imp_WSAGetLastError` at `0x1400a2512`
- `WS2_32!__imp_WSAGetLastError` at `0x1400a2587`
- `WS2_32!__imp_WSAGetLastError` at `0x1400a2512`
- `WS2_32!__imp_WSAGetLastError` at `0x1400a2587`

## string_xrefs

- `0x1400a2496`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a24be`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a24dd`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a2529`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a2552`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a25a9`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a25cc`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a25f9`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall VmMigrationTcpTransport::ReceiveData(VmMigrationTcpTransport *this, char *a2, int a3, int a4)
{
  DWORD TimeRemaining; // eax
  DWORD v8; // eax
  DWORD LastError; // eax
  unsigned int Error; // eax
  int v11; // eax
  unsigned int v12; // eax
  BOOL bAlertable; // [rsp+20h] [rbp-78h]
  _DWORD v15[2]; // [rsp+30h] [rbp-68h] BYREF
  _WSANETWORKEVENTS NetworkEvents; // [rsp+38h] [rbp-60h] BYREF
  HANDLE Handles[2]; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v15[0] = a4;
  v15[1] = GetTickCount();
  Handles[0] = *((HANDLE *)this + 91);
  Handles[1] = *((HANDLE *)this + 66);
  while ( a3 > 0 )
  {
    memset(&NetworkEvents, 0, sizeof(NetworkEvents));
    TimeRemaining = Vml::VmTimeoutTimer::GetTimeRemaining((Vml::VmTimeoutTimer *)v15);
    v8 = WaitForMultipleObjectsEx(2u, Handles, 0, TimeRemaining, 0);
    if ( !v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA4D,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x800704C7LL,
        bAlertable);
    if ( v8 != 1 )
    {
      if ( v8 != 258 )
      {
        if ( v8 != -1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA74,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x8000FFFFLL,
            bAlertable);
        LastError = GetLastError();
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xA71,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)LastError,
          bAlertable);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA6D,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x800705B4LL,
        bAlertable);
    }
    if ( WSAEnumNetworkEvents(*((_QWORD *)this + 65), *((HANDLE *)this + 66), &NetworkEvents) == -1 )
    {
      Error = WSAGetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA55,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)Error,
        bAlertable);
    }
    if ( (NetworkEvents.lNetworkEvents & 0x21) == 0x20 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA63,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x2746,
        bAlertable);
    v11 = recv(*((_QWORD *)this + 65), a2, a3, 0);
    if ( v11 == -1 )
    {
      v12 = WSAGetLastError();
      if ( v12 != 10035 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xA8A,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)v12,
          bAlertable);
    }
    else
    {
      if ( !v11 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xA8F,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)0x2746,
          bAlertable);
      if ( v11 >= a3 )
        return 0;
      a2 += v11;
      a3 -= v11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400a23d8  push    rbx
0x1400a23da  push    rsi
0x1400a23db  push    rdi
0x1400a23dc  sub     rsp, 80h
0x1400a23e3  mov     rax, cs:__security_cookie
0x1400a23ea  xor     rax, rsp
0x1400a23ed  mov     [rsp+98h+var_20], rax
0x1400a23f2  mov     rbx, r8
0x1400a23f5  mov     rsi, rdx
0x1400a23f8  mov     rdi, rcx
0x1400a23fb  mov     [rsp+98h+var_68], r9d
0x1400a2400  call    cs:__imp_GetTickCount
0x1400a2407  nop     dword ptr [rax+rax+00h]
0x1400a240c  mov     [rsp+98h+var_64], eax
0x1400a2410  mov     rax, [rdi+2D8h]
0x1400a2417  mov     [rsp+98h+Handles], rax
0x1400a241c  mov     rax, [rdi+210h]
0x1400a2423  mov     [rsp+98h+var_28], rax
0x1400a2428  test    ebx, ebx
0x1400a242a  jle     loc_1400A260A
0x1400a2430  xorps   xmm0, xmm0
0x1400a2433  movups  xmmword ptr [rsp+98h+NetworkEvents.lNetworkEvents], xmm0
0x1400a2438  movups  xmmword ptr [rsp+98h+NetworkEvents.iErrorCode+0Ch], xmm0
0x1400a243d  movups  xmmword ptr [rsp+98h+NetworkEvents.iErrorCode+18h], xmm0
0x1400a2442  lea     rcx, [rsp+98h+var_68]; this
0x1400a2447  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x1400a244c  mov     r9d, eax; dwMilliseconds
0x1400a244f  mov     [rsp+98h+bAlertable], 0; int
0x1400a2457  xor     r8d, r8d; bWaitAll
0x1400a245a  lea     rdx, [rsp+98h+Handles]; lpHandles
0x1400a245f  lea     ecx, [r8+2]; nCount
0x1400a2463  call    cs:__imp_WaitForMultipleObjectsEx
0x1400a246a  nop     dword ptr [rax+rax+00h]
0x1400a246f  test    eax, eax
0x1400a2471  jz      loc_1400A25EB
0x1400a2477  cmp     eax, 1
0x1400a247a  jz      short loc_1400A24EE
0x1400a247c  cmp     eax, 102h
0x1400a2481  jz      short loc_1400A24CF
0x1400a2483  cmp     eax, 0FFFFFFFFh
0x1400a2486  jz      short loc_1400A24A7
0x1400a2488  mov     rcx, [rsp+98h]; this
0x1400a2490  mov     r9d, 8000FFFFh; char *
0x1400a2496  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400a249d  mov     edx, 0A74h; void *
0x1400a24a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a24a7  call    cs:__imp_GetLastError
0x1400a24ae  nop     dword ptr [rax+rax+00h]
0x1400a24b3  mov     r9d, eax; char *
0x1400a24b6  mov     rcx, [rsp+98h]; this
0x1400a24be  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400a24c5  mov     edx, 0A71h; void *
0x1400a24ca  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a24cf  mov     rcx, [rsp+98h]; this
0x1400a24d7  mov     r9d, 800705B4h; char *
0x1400a24dd  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400a24e4  mov     edx, 0A6Dh; void *
0x1400a24e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a24ee  lea     r8, [rsp+98h+NetworkEvents]; lpNetworkEvents
0x1400a24f3  mov     rdx, [rdi+210h]; hEventObject
0x1400a24fa  mov     rcx, [rdi+208h]; s
0x1400a2501  call    cs:__imp_WSAEnumNetworkEvents
0x1400a2508  nop     dword ptr [rax+rax+00h]
0x1400a250d  cmp     eax, 0FFFFFFFFh
0x1400a2510  jnz     short loc_1400A253A
0x1400a2512  call    cs:__imp_WSAGetLastError
0x1400a2519  nop     dword ptr [rax+rax+00h]
0x1400a251e  mov     r9d, eax; char *
0x1400a2521  mov     rcx, [rsp+98h]; this
0x1400a2529  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400a2530  mov     edx, 0A55h; void *
0x1400a2535  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a253a  mov     eax, [rsp+98h+NetworkEvents.lNetworkEvents]
0x1400a253e  and     al, 21h
0x1400a2540  cmp     al, 20h ; ' '
0x1400a2542  jnz     short loc_1400A2563
0x1400a2544  mov     rcx, [rsp+98h]; this
0x1400a254c  mov     r9d, 2746h; char *
0x1400a2552  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400a2559  mov     edx, 0A63h; void *
0x1400a255e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a2563  xor     r9d, r9d; flags
0x1400a2566  mov     r8d, ebx; len
0x1400a2569  mov     rdx, rsi; buf
0x1400a256c  mov     rcx, [rdi+208h]; s
0x1400a2573  call    cs:__imp_recv
0x1400a257a  nop     dword ptr [rax+rax+00h]
0x1400a257f  movsxd  rcx, eax
0x1400a2582  cmp     ecx, 0FFFFFFFFh
0x1400a2585  jnz     short loc_1400A25BA
0x1400a2587  call    cs:__imp_WSAGetLastError
0x1400a258e  nop     dword ptr [rax+rax+00h]
0x1400a2593  cmp     eax, 2733h
0x1400a2598  jz      loc_1400A2428
0x1400a259e  mov     rcx, [rsp+98h]; this
0x1400a25a6  mov     r9d, eax; char *
0x1400a25a9  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400a25b0  mov     edx, 0A8Ah; void *
0x1400a25b5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a25ba  test    eax, eax
0x1400a25bc  jnz     short loc_1400A25DD
0x1400a25be  mov     rcx, [rsp+98h]; this
0x1400a25c6  mov     r9d, 2746h; char *
0x1400a25cc  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400a25d3  mov     edx, 0A8Fh; void *
0x1400a25d8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a25dd  cmp     ecx, ebx
0x1400a25df  jge     short loc_1400A260A
0x1400a25e1  add     rsi, rcx
0x1400a25e4  sub     ebx, ecx
0x1400a25e6  jmp     loc_1400A2428
0x1400a25eb  mov     rcx, [rsp+98h]; this
0x1400a25f3  mov     r9d, 800704C7h; char *
0x1400a25f9  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400a2600  mov     edx, 0A4Dh; void *
0x1400a2605  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a260a  xor     eax, eax
0x1400a260c  jmp     short loc_1400A2612
0x1400a260e  mov     eax, [rsp+98h+var_68]
0x1400a2612  mov     rcx, [rsp+98h+var_20]
0x1400a2617  xor     rcx, rsp; StackCookie
0x1400a261a  call    __security_check_cookie
0x1400a261f  add     rsp, 80h
0x1400a2626  pop     rdi
0x1400a2627  pop     rsi
0x1400a2628  pop     rbx
0x1400a2629  retn
```
