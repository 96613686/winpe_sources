# CWwanIpAddr::IpAddr_Initialize(void)

- ea: `0x1800568b8`
- end: `0x180056aa5`
- name: `?IpAddr_Initialize@CWwanIpAddr@@AEAAJXZ`
- size: `493`
- prototype: `__int64 __fastcall(CWwanIpAddr *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180056738`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180014f1c`
- `0x180056838`
- `0x1800568b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005698f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005698f`
- `WS2_32!WSAIoctl` at `0x1800569f2`
- `WS2_32!WSAIoctl` at `0x1800569f2`
- `WS2_32!WSAEventSelect` at `0x1800569b6`
- `WS2_32!WSAEventSelect` at `0x1800569b6`
- `WS2_32!__imp_socket` at `0x180056970`
- `WS2_32!__imp_socket` at `0x180056970`
- `WS2_32!__imp_WSAGetLastError` at `0x18005692d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800569fd`
- `WS2_32!__imp_WSAGetLastError` at `0x180056a38`
- `WS2_32!__imp_WSAGetLastError` at `0x18005692d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800569fd`
- `WS2_32!__imp_WSAGetLastError` at `0x180056a38`
- `WS2_32!__imp_WSAStartup` at `0x180056921`
- `WS2_32!__imp_WSAStartup` at `0x180056921`

## string_xrefs

- `0x180056a46`: `Failed to create socket for af %d`
- `0x180056a2c`: `WSACreateEventFailed. 0x%x`

## pseudocode

```c
__int64 __fastcall CWwanIpAddr::IpAddr_Initialize(CWwanIpAddr *this)
{
  unsigned int Error; // eax
  unsigned int i; // ebx
  int *v5; // r15
  SOCKET v6; // rax
  HANDLE EventW; // rax
  SOCKET v8; // rcx
  const unsigned __int16 *v9; // rbp
  unsigned int v10; // ebx
  unsigned int v11; // eax
  DWORD cbBytesReturned[4]; // [rsp+50h] [rbp-1F8h] BYREF
  WSAData WSAData; // [rsp+60h] [rbp-1E8h] BYREF

  WwanLog::Info("CWwanIpAddr::IpAddr_Initialize", 0, L" IpAddr_Initialize ..\n");
  memset_0(&WSAData, 0, sizeof(WSAData));
  *((_DWORD *)this + 12) = 2;
  *((_DWORD *)this + 13) = 23;
  if ( WSAStartup(0x202u, &WSAData) )
  {
    Error = WSAGetLastError();
    WwanLog::Error("CWwanIpAddr::IpAddr_Initialize", 0, L"WSAStartup failed. 0x%x", Error);
    return 2147500037LL;
  }
  else
  {
    for ( i = 0; i < 2; ++i )
    {
      v5 = (int *)((char *)this + 4 * i + 48);
      v6 = socket(*v5, 1, 0);
      *((_QWORD *)this + i + 7) = v6;
      if ( v6 == -1 )
      {
        v11 = *v5;
        v9 = L"Failed to create socket for af %d";
        v10 = -2147467259;
        goto LABEL_16;
      }
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + i + 9) = EventW;
      *((_QWORD *)this + i + 11) = v5;
      if ( !EventW )
      {
        v9 = L"WSACreateEventFailed. 0x%x";
LABEL_14:
        v10 = -2147467259;
        v11 = WSAGetLastError();
LABEL_16:
        WwanLog::Error("CWwanIpAddr::IpAddr_Initialize", 0, v9, v11);
        CWwanIpAddr::IpAddr_DeInitialize(this);
        return v10;
      }
      if ( WSAEventSelect(*((_QWORD *)this + i + 7), EventW, 512) == -1 )
      {
        v9 = L"WSAEventSelect failed. 0x%x";
        goto LABEL_14;
      }
      v8 = *((_QWORD *)this + i + 7);
      cbBytesReturned[0] = 0;
      if ( WSAIoctl(v8, 0x28000017u, 0, 0, 0, 0, cbBytesReturned, 0, 0) == -1 && WSAGetLastError() != 10035 )
      {
        v9 = L"WSAIoctl failed. 0x%x";
        goto LABEL_14;
      }
    }
    v10 = 0;
    WwanLog::Info("CWwanIpAddr::IpAddr_Initialize", 0, L" IPAddr Initialize exit. hr=0x%x", 0);
    return v10;
  }
}

```

## disassembly

```asm
0x1800568b8  push    rbx
0x1800568ba  push    rbp
0x1800568bb  push    rsi
0x1800568bc  push    rdi
0x1800568bd  push    r14
0x1800568bf  push    r15
0x1800568c1  sub     rsp, 218h
0x1800568c8  mov     rax, cs:__security_cookie
0x1800568cf  xor     rax, rsp
0x1800568d2  mov     [rsp+248h+var_48], rax
0x1800568da  mov     r14, rcx
0x1800568dd  lea     rdi, aCwwanipaddrIpa_0; "CWwanIpAddr::IpAddr_Initialize"
0x1800568e4  mov     rcx, rdi; char *
0x1800568e7  lea     r8, aIpaddrInitiali_0; " IpAddr_Initialize ..\n"
0x1800568ee  xor     edx, edx; struct _GUID *
0x1800568f0  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800568f5  xor     edx, edx; Val
0x1800568f7  lea     rcx, [rsp+248h+WSAData]; void *
0x1800568fc  mov     r8d, 198h; Size
0x180056902  call    memset_0
0x180056907  mov     ecx, 202h; wVersionRequested
0x18005690c  mov     dword ptr [r14+30h], 2
0x180056914  lea     rdx, [rsp+248h+WSAData]; lpWSAData
0x180056919  mov     dword ptr [r14+34h], 17h
0x180056921  call    cs:__imp_WSAStartup
0x180056927  xor     ebp, ebp
0x180056929  test    eax, eax
0x18005692b  jz      short loc_180056951
0x18005692d  call    cs:__imp_WSAGetLastError
0x180056933  lea     r8, aWsastartupFail; "WSAStartup failed. 0x%x"
0x18005693a  xor     edx, edx; struct _GUID *
0x18005693c  mov     r9d, eax
0x18005693f  mov     rcx, rdi; char *
0x180056942  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180056947  mov     eax, 80004005h
0x18005694c  jmp     loc_180056A85
0x180056951  mov     ebx, ebp
0x180056953  cmp     ebx, 2
0x180056956  jnb     loc_180056A6D
0x18005695c  xor     r8d, r8d; protocol
0x18005695f  mov     esi, ebx
0x180056961  lea     r15, [r14+30h]
0x180056965  lea     r15, [r15+rsi*4]
0x180056969  mov     ecx, [r15]; af
0x18005696c  lea     edx, [r8+1]; type
0x180056970  call    cs:__imp_socket
0x180056976  mov     [r14+rsi*8+38h], rax
0x18005697b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005697f  jz      loc_180056A40
0x180056985  xor     r9d, r9d; lpName
0x180056988  xor     r8d, r8d; bInitialState
0x18005698b  xor     edx, edx; bManualReset
0x18005698d  xor     ecx, ecx; lpEventAttributes
0x18005698f  call    cs:__imp_CreateEventW
0x180056995  mov     [r14+rsi*8+48h], rax
0x18005699a  mov     [r14+rsi*8+58h], r15
0x18005699f  test    rax, rax
0x1800569a2  jz      loc_180056A29
0x1800569a8  mov     rcx, [r14+rsi*8+38h]; s
0x1800569ad  mov     r8d, 200h; lNetworkEvents
0x1800569b3  mov     rdx, rax; hEventObject
0x1800569b6  call    cs:__imp_WSAEventSelect
0x1800569bc  cmp     eax, 0FFFFFFFFh
0x1800569bf  jz      short loc_180056A1D
0x1800569c1  mov     rcx, [r14+rsi*8+38h]; s
0x1800569c6  lea     rax, [rsp+248h+cbBytesReturned]
0x1800569cb  mov     [rsp+248h+lpCompletionRoutine], rbp; lpCompletionRoutine
0x1800569d0  xor     r9d, r9d; cbInBuffer
0x1800569d3  mov     [rsp+248h+lpOverlapped], rbp; lpOverlapped
0x1800569d8  xor     r8d, r8d; lpvInBuffer
0x1800569db  mov     [rsp+248h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800569e0  mov     edx, 28000017h; dwIoControlCode
0x1800569e5  mov     [rsp+248h+cbOutBuffer], ebp; cbOutBuffer
0x1800569e9  mov     [rsp+248h+lpvOutBuffer], rbp; lpvOutBuffer
0x1800569ee  mov     [rsp+248h+cbBytesReturned], ebp
0x1800569f2  call    cs:__imp_WSAIoctl
0x1800569f8  cmp     eax, 0FFFFFFFFh
0x1800569fb  jnz     short loc_180056A0A
0x1800569fd  call    cs:__imp_WSAGetLastError
0x180056a03  cmp     eax, 2733h
0x180056a08  jnz     short loc_180056A11
0x180056a0a  inc     ebx
0x180056a0c  jmp     loc_180056953
0x180056a11  mov     rsi, rbp
0x180056a14  lea     rbp, aWsaioctlFailed; "WSAIoctl failed. 0x%x"
0x180056a1b  jmp     short loc_180056A33
0x180056a1d  mov     rsi, rbp
0x180056a20  lea     rbp, aWsaeventselect; "WSAEventSelect failed. 0x%x"
0x180056a27  jmp     short loc_180056A33
0x180056a29  mov     rsi, rbp
0x180056a2c  lea     rbp, aWsacreateevent; "WSACreateEventFailed. 0x%x"
0x180056a33  mov     ebx, 80004005h
0x180056a38  call    cs:__imp_WSAGetLastError
0x180056a3e  jmp     short loc_180056A52
0x180056a40  mov     eax, [r15]
0x180056a43  mov     rsi, rbp
0x180056a46  lea     rbp, aFailedToCreate_8; "Failed to create socket for af %d"
0x180056a4d  mov     ebx, 80004005h
0x180056a52  mov     r9d, eax
0x180056a55  mov     r8, rbp; unsigned __int16 *
0x180056a58  mov     rdx, rsi; struct _GUID *
0x180056a5b  mov     rcx, rdi; char *
0x180056a5e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180056a63  mov     rcx, r14; this
0x180056a66  call    ?IpAddr_DeInitialize@CWwanIpAddr@@AEAAXXZ; CWwanIpAddr::IpAddr_DeInitialize(void)
0x180056a6b  jmp     short loc_180056A83
0x180056a6d  xor     r9d, r9d
0x180056a70  lea     r8, aIpaddrInitiali; " IPAddr Initialize exit. hr=0x%x"
0x180056a77  xor     edx, edx; struct _GUID *
0x180056a79  mov     rcx, rdi; char *
0x180056a7c  mov     ebx, ebp
0x180056a7e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180056a83  mov     eax, ebx
0x180056a85  mov     rcx, [rsp+248h+var_48]
0x180056a8d  xor     rcx, rsp; StackCookie
0x180056a90  call    __security_check_cookie
0x180056a95  add     rsp, 218h
0x180056a9c  pop     r15
0x180056a9e  pop     r14
0x180056aa0  pop     rdi
0x180056aa1  pop     rsi
0x180056aa2  pop     rbp
0x180056aa3  pop     rbx
0x180056aa4  retn
```
