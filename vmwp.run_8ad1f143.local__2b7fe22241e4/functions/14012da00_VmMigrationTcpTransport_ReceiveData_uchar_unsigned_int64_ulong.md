# VmMigrationTcpTransport::ReceiveData(uchar *,unsigned __int64,ulong)

- ea: `0x14012da00`
- end: `0x14012dc53`
- name: `?ReceiveData@VmMigrationTcpTransport@@IEAAJPEAE_KK@Z`
- size: `595`
- prototype: `int(VmMigrationTcpTransport *__hidden this, unsigned __int8 *, unsigned __int64, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14012d840`
- `0x1401df1f0`
- `0x1401e0310`
- `0x1401e0400`

## callees

- `0x14006af58`
- `0x14008c984`
- `0x14009d7cc`
- `0x14012da00`
- `0x140132960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14012da8b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14012da8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012dacf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012dacf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14012da28`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14012da28`
- `WS2_32!WSAEnumNetworkEvents` at `0x14012db29`
- `WS2_32!WSAEnumNetworkEvents` at `0x14012db29`
- `WS2_32!__imp_recv` at `0x14012db9b`
- `WS2_32!__imp_recv` at `0x14012db9b`
- `WS2_32!__imp_WSAGetLastError` at `0x14012db3a`
- `WS2_32!__imp_WSAGetLastError` at `0x14012dbaf`
- `WS2_32!__imp_WSAGetLastError` at `0x14012db3a`
- `WS2_32!__imp_WSAGetLastError` at `0x14012dbaf`

## string_xrefs

- `0x14012dabe`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dae6`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012db05`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012db51`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012db7a`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dbd1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dbf4`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dc21`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

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
0x14012da00  push    rbx
0x14012da02  push    rsi
0x14012da03  push    rdi
0x14012da04  sub     rsp, 80h
0x14012da0b  mov     rax, cs:__security_cookie
0x14012da12  xor     rax, rsp
0x14012da15  mov     [rsp+98h+var_20], rax
0x14012da1a  mov     rbx, r8
0x14012da1d  mov     rsi, rdx
0x14012da20  mov     rdi, rcx
0x14012da23  mov     [rsp+98h+var_68], r9d
0x14012da28  call    cs:__imp_GetTickCount
0x14012da2f  nop     dword ptr [rax+rax+00h]
0x14012da34  mov     [rsp+98h+var_64], eax
0x14012da38  mov     rax, [rdi+2D8h]
0x14012da3f  mov     [rsp+98h+Handles], rax
0x14012da44  mov     rax, [rdi+210h]
0x14012da4b  mov     [rsp+98h+var_28], rax
0x14012da50  test    ebx, ebx
0x14012da52  jle     loc_14012DC32
0x14012da58  xorps   xmm0, xmm0
0x14012da5b  movups  xmmword ptr [rsp+98h+NetworkEvents.lNetworkEvents], xmm0
0x14012da60  movups  xmmword ptr [rsp+98h+NetworkEvents.iErrorCode+0Ch], xmm0
0x14012da65  movups  xmmword ptr [rsp+98h+NetworkEvents.iErrorCode+18h], xmm0
0x14012da6a  lea     rcx, [rsp+98h+var_68]; this
0x14012da6f  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x14012da74  mov     r9d, eax; dwMilliseconds
0x14012da77  mov     [rsp+98h+bAlertable], 0; int
0x14012da7f  xor     r8d, r8d; bWaitAll
0x14012da82  lea     rdx, [rsp+98h+Handles]; lpHandles
0x14012da87  lea     ecx, [r8+2]; nCount
0x14012da8b  call    cs:__imp_WaitForMultipleObjectsEx
0x14012da92  nop     dword ptr [rax+rax+00h]
0x14012da97  test    eax, eax
0x14012da99  jz      loc_14012DC13
0x14012da9f  cmp     eax, 1
0x14012daa2  jz      short loc_14012DB16
0x14012daa4  cmp     eax, 102h
0x14012daa9  jz      short loc_14012DAF7
0x14012daab  cmp     eax, 0FFFFFFFFh
0x14012daae  jz      short loc_14012DACF
0x14012dab0  mov     rcx, [rsp+98h]; this
0x14012dab8  mov     r9d, 8000FFFFh; char *
0x14012dabe  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012dac5  mov     edx, 0A74h; void *
0x14012daca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14012dacf  call    cs:__imp_GetLastError
0x14012dad6  nop     dword ptr [rax+rax+00h]
0x14012dadb  mov     r9d, eax; char *
0x14012dade  mov     rcx, [rsp+98h]; this
0x14012dae6  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012daed  mov     edx, 0A71h; void *
0x14012daf2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012daf7  mov     rcx, [rsp+98h]; this
0x14012daff  mov     r9d, 800705B4h; char *
0x14012db05  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012db0c  mov     edx, 0A6Dh; void *
0x14012db11  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14012db16  lea     r8, [rsp+98h+NetworkEvents]; lpNetworkEvents
0x14012db1b  mov     rdx, [rdi+210h]; hEventObject
0x14012db22  mov     rcx, [rdi+208h]; s
0x14012db29  call    cs:__imp_WSAEnumNetworkEvents
0x14012db30  nop     dword ptr [rax+rax+00h]
0x14012db35  cmp     eax, 0FFFFFFFFh
0x14012db38  jnz     short loc_14012DB62
0x14012db3a  call    cs:__imp_WSAGetLastError
0x14012db41  nop     dword ptr [rax+rax+00h]
0x14012db46  mov     r9d, eax; char *
0x14012db49  mov     rcx, [rsp+98h]; this
0x14012db51  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012db58  mov     edx, 0A55h; void *
0x14012db5d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012db62  mov     eax, [rsp+98h+NetworkEvents.lNetworkEvents]
0x14012db66  and     al, 21h
0x14012db68  cmp     al, 20h ; ' '
0x14012db6a  jnz     short loc_14012DB8B
0x14012db6c  mov     rcx, [rsp+98h]; this
0x14012db74  mov     r9d, 2746h; char *
0x14012db7a  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012db81  mov     edx, 0A63h; void *
0x14012db86  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012db8b  xor     r9d, r9d; flags
0x14012db8e  mov     r8d, ebx; len
0x14012db91  mov     rdx, rsi; buf
0x14012db94  mov     rcx, [rdi+208h]; s
0x14012db9b  call    cs:__imp_recv
0x14012dba2  nop     dword ptr [rax+rax+00h]
0x14012dba7  movsxd  rcx, eax
0x14012dbaa  cmp     ecx, 0FFFFFFFFh
0x14012dbad  jnz     short loc_14012DBE2
0x14012dbaf  call    cs:__imp_WSAGetLastError
0x14012dbb6  nop     dword ptr [rax+rax+00h]
0x14012dbbb  cmp     eax, 2733h
0x14012dbc0  jz      loc_14012DA50
0x14012dbc6  mov     rcx, [rsp+98h]; this
0x14012dbce  mov     r9d, eax; char *
0x14012dbd1  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012dbd8  mov     edx, 0A8Ah; void *
0x14012dbdd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012dbe2  test    eax, eax
0x14012dbe4  jnz     short loc_14012DC05
0x14012dbe6  mov     rcx, [rsp+98h]; this
0x14012dbee  mov     r9d, 2746h; char *
0x14012dbf4  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012dbfb  mov     edx, 0A8Fh; void *
0x14012dc00  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012dc05  cmp     ecx, ebx
0x14012dc07  jge     short loc_14012DC32
0x14012dc09  add     rsi, rcx
0x14012dc0c  sub     ebx, ecx
0x14012dc0e  jmp     loc_14012DA50
0x14012dc13  mov     rcx, [rsp+98h]; this
0x14012dc1b  mov     r9d, 800704C7h; char *
0x14012dc21  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012dc28  mov     edx, 0A4Dh; void *
0x14012dc2d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14012dc32  xor     eax, eax
0x14012dc34  jmp     short loc_14012DC3A
0x14012dc36  mov     eax, [rsp+98h+var_68]
0x14012dc3a  mov     rcx, [rsp+98h+var_20]
0x14012dc3f  xor     rcx, rsp; StackCookie
0x14012dc42  call    __security_check_cookie
0x14012dc47  add     rsp, 80h
0x14012dc4e  pop     rdi
0x14012dc4f  pop     rsi
0x14012dc50  pop     rbx
0x14012dc51  retn
```
