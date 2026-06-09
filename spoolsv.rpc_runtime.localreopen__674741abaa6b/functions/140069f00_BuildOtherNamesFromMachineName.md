# BuildOtherNamesFromMachineName

- ea: `0x140069f00`
- end: `0x14006a192`
- name: `BuildOtherNamesFromMachineName`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14006bb40`

## callees

- `0x140004790`
- `0x14000b4b0`
- `0x140015378`
- `0x14002d0a0`
- `0x14002dd20`
- `0x140069f00`
- `0x14006a940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140069fc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006a10e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140069fc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006a10e`
- `KERNEL32!GetComputerNameW` at `0x140069ffb`
- `KERNEL32!GetComputerNameW` at `0x140069ffb`
- `WS2_32!FreeAddrInfoW` at `0x14006a15c`
- `WS2_32!FreeAddrInfoW` at `0x14006a15c`
- `WS2_32!GetAddrInfoW` at `0x14006a01a`
- `WS2_32!GetAddrInfoW` at `0x14006a01a`
- `WS2_32!GetNameInfoW` at `0x14006a0b8`
- `WS2_32!GetNameInfoW` at `0x14006a0b8`
- `WS2_32!__imp_WSAGetLastError` at `0x14006a124`
- `WS2_32!__imp_WSAGetLastError` at `0x14006a124`
- `WS2_32!__imp_WSAStartup` at `0x140069f9a`
- `WS2_32!__imp_WSAStartup` at `0x140069f9a`
- `WS2_32!__imp_WSACleanup` at `0x14006a146`
- `WS2_32!__imp_WSACleanup` at `0x14006a146`

## pseudocode

```c
__int64 __fastcall BuildOtherNamesFromMachineName(__int64 a1, _DWORD *a2)
{
  DWORD v4; // eax
  unsigned int v6; // r15d
  PADDRINFOW v7; // rax
  int v8; // ecx
  int v9; // ecx
  __int64 v10; // rax
  int v11; // r14d
  PADDRINFOW i; // rdi
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 j; // rdx
  unsigned int Error; // eax
  DWORD dwErrCode; // [rsp+40h] [rbp-C0h] BYREF
  PADDRINFOW ppResult; // [rsp+48h] [rbp-B8h] BYREF
  ADDRINFOW pHints; // [rsp+50h] [rbp-B0h] BYREF
  struct WSAData WSAData; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[8]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v22; // [rsp+230h] [rbp+130h]
  WCHAR pNodeBuffer[1032]; // [rsp+240h] [rbp+140h] BYREF

  ppResult = 0;
  memset(&pHints, 0, sizeof(pHints));
  memset_0(&WSAData, 0, sizeof(WSAData));
  memset_0(pNodeBuffer, 0, 0x802u);
  *a2 = 0;
  *(_OWORD *)Buffer = 0;
  v22 = 0;
  v4 = WSAStartup(0x202u, &WSAData);
  dwErrCode = v4;
  if ( v4 )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError("BuildOtherNamesFromMachineName", L"WSAStartup failed.  Error %d.", v4);
    SetLastError(dwErrCode);
    return 0;
  }
  else
  {
    *(_QWORD *)&pHints.ai_flags = 2;
    dwErrCode = 16;
    v6 = 0;
    GetComputerNameW(Buffer, &dwErrCode);
    if ( GetAddrInfoW(Buffer, 0, &pHints, &ppResult) )
    {
      Error = WSAGetLastError();
      PrvSpoolssTelemetry::WriteDbgTraceError("BuildOtherNamesFromMachineName", L"getaddrinfo() failed with %d.", Error);
    }
    else
    {
      v7 = ppResult;
      v8 = 0;
      while ( v7 )
      {
        *a2 = ++v8;
        v7 = v7->ai_next;
      }
      v9 = v8 + 2;
      *a2 = v9;
      v10 = DllAllocSplMem((unsigned int)(8 * v9));
      *(_QWORD *)a1 = v10;
      if ( v10 )
      {
        **(_QWORD **)a1 = AllocSplStr(&::Buffer);
        v11 = 0;
        *(_QWORD *)(*(_QWORD *)a1 + 8LL) = AllocSplStr(ppResult->ai_canonname);
        for ( i = ppResult; i && !GetNameInfoW(i->ai_addr, i->ai_addrlen, pNodeBuffer, 0x401u, 0, 0, 2); i = i->ai_next )
        {
          v13 = AllocSplStr(pNodeBuffer);
          v14 = (unsigned int)(v11 + 2);
          ++v11;
          *(_QWORD *)(*(_QWORD *)a1 + 8 * v14) = v13;
        }
        for ( j = 0; (unsigned int)j < *a2; j = (unsigned int)(j + 1) )
        {
          if ( !*(_QWORD *)(*(_QWORD *)a1 + 8 * j) )
          {
            FreeOtherNames(a1, a2);
            SetLastError(8u);
            goto LABEL_20;
          }
        }
        v6 = 1;
      }
      else
      {
        *a2 = 0;
      }
    }
LABEL_20:
    WSACleanup();
    if ( ppResult )
      FreeAddrInfoW(ppResult);
    return v6;
  }
}

```

## disassembly

```asm
0x140069f00  mov     [rsp-8+arg_10], rbx
0x140069f05  push    rbp
0x140069f06  push    rsi
0x140069f07  push    rdi
0x140069f08  push    r14
0x140069f0a  push    r15
0x140069f0c  lea     rbp, [rsp-960h]
0x140069f14  sub     rsp, 0A60h
0x140069f1b  mov     rax, cs:__security_cookie
0x140069f22  xor     rax, rsp
0x140069f25  mov     [rbp+980h+var_30], rax
0x140069f2c  xorps   xmm0, xmm0
0x140069f2f  mov     [rsp+0A80h+ppResult], 0
0x140069f38  mov     rbx, rdx
0x140069f3b  mov     [rsp+0A80h+dwErrCode], 0
0x140069f43  mov     rsi, rcx
0x140069f46  xor     edx, edx; Val
0x140069f48  lea     rcx, [rbp+980h+WSAData]; void *
0x140069f4c  mov     r8d, 198h; Size
0x140069f52  movups  xmmword ptr [rsp+0A80h+pHints.ai_flags], xmm0
0x140069f57  movups  xmmword ptr [rsp+0A80h+pHints.ai_addrlen], xmm0
0x140069f5c  movups  xmmword ptr [rsp+0A80h+pHints.ai_addr], xmm0
0x140069f61  call    memset_0
0x140069f66  xor     edx, edx; Val
0x140069f68  lea     rcx, [rbp+980h+pNodeBuffer]; void *
0x140069f6f  mov     r8d, 802h; Size
0x140069f75  call    memset_0
0x140069f7a  xorps   xmm0, xmm0
0x140069f7d  mov     dword ptr [rbx], 0
0x140069f83  mov     ecx, 202h; wVersionRequested
0x140069f88  lea     rdx, [rbp+980h+WSAData]; lpWSAData
0x140069f8c  movups  xmmword ptr [rbp+980h+Buffer], xmm0
0x140069f93  movups  [rbp+980h+var_850], xmm0
0x140069f9a  call    cs:__imp_WSAStartup
0x140069fa1  nop     dword ptr [rax+rax+00h]
0x140069fa6  mov     [rsp+0A80h+dwErrCode], eax
0x140069faa  test    eax, eax
0x140069fac  jz      short loc_140069FDB
0x140069fae  mov     r8d, eax
0x140069fb1  lea     rdx, aWsastartupFail; "WSAStartup failed.  Error %d."
0x140069fb8  lea     rcx, aBuildothername; "BuildOtherNamesFromMachineName"
0x140069fbf  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140069fc4  mov     ecx, [rsp+0A80h+dwErrCode]; dwErrCode
0x140069fc8  call    cs:__imp_SetLastError
0x140069fcf  nop     dword ptr [rax+rax+00h]
0x140069fd4  xor     eax, eax
0x140069fd6  jmp     loc_14006A16B
0x140069fdb  lea     rdx, [rsp+0A80h+dwErrCode]; nSize
0x140069fe0  mov     qword ptr [rsp+0A80h+pHints.ai_flags], 2
0x140069fe9  lea     rcx, [rbp+980h+Buffer]; lpBuffer
0x140069ff0  mov     [rsp+0A80h+dwErrCode], 10h
0x140069ff8  xor     r15d, r15d
0x140069ffb  call    cs:__imp_GetComputerNameW
0x14006a002  nop     dword ptr [rax+rax+00h]
0x14006a007  lea     r9, [rsp+0A80h+ppResult]; ppResult
0x14006a00c  xor     edx, edx; pServiceName
0x14006a00e  lea     r8, [rsp+0A80h+pHints]; pHints
0x14006a013  lea     rcx, [rbp+980h+Buffer]; pNodeName
0x14006a01a  call    cs:__imp_GetAddrInfoW
0x14006a021  nop     dword ptr [rax+rax+00h]
0x14006a026  test    eax, eax
0x14006a028  jnz     loc_14006A124
0x14006a02e  mov     rax, [rsp+0A80h+ppResult]
0x14006a033  xor     ecx, ecx
0x14006a035  jmp     short loc_14006A03F
0x14006a037  inc     ecx
0x14006a039  mov     [rbx], ecx
0x14006a03b  mov     rax, [rax+28h]
0x14006a03f  test    rax, rax
0x14006a042  jnz     short loc_14006A037
0x14006a044  add     ecx, 2
0x14006a047  mov     [rbx], ecx
0x14006a049  shl     ecx, 3; dwBytes
0x14006a04c  call    DllAllocSplMem
0x14006a051  mov     [rsi], rax
0x14006a054  test    rax, rax
0x14006a057  jnz     short loc_14006A061
0x14006a059  mov     [rbx], r15d
0x14006a05c  jmp     loc_14006A146
0x14006a061  lea     rcx, Buffer; Src
0x14006a068  call    AllocSplStr
0x14006a06d  mov     rcx, [rsi]
0x14006a070  mov     [rcx], rax
0x14006a073  mov     rcx, [rsp+0A80h+ppResult]
0x14006a078  mov     rcx, [rcx+18h]; Src
0x14006a07c  call    AllocSplStr
0x14006a081  mov     rcx, [rsi]
0x14006a084  xor     r14d, r14d
0x14006a087  mov     [rcx+8], rax
0x14006a08b  mov     rdi, [rsp+0A80h+ppResult]
0x14006a090  jmp     short loc_14006A0E6
0x14006a092  mov     edx, [rdi+10h]; SockaddrLength
0x14006a095  lea     r8, [rbp+980h+pNodeBuffer]; pNodeBuffer
0x14006a09c  mov     rcx, [rdi+20h]; pSockaddr
0x14006a0a0  mov     r9d, 401h; NodeBufferSize
0x14006a0a6  mov     [rsp+0A80h+Flags], 2; Flags
0x14006a0ae  mov     [rsp+0A80h+ServiceBufferSize], r15d; ServiceBufferSize
0x14006a0b3  mov     [rsp+0A80h+pServiceBuffer], r15; pServiceBuffer
0x14006a0b8  call    cs:__imp_GetNameInfoW
0x14006a0bf  nop     dword ptr [rax+rax+00h]
0x14006a0c4  test    eax, eax
0x14006a0c6  jnz     short loc_14006A0EB
0x14006a0c8  lea     rcx, [rbp+980h+pNodeBuffer]; Src
0x14006a0cf  call    AllocSplStr
0x14006a0d4  mov     rcx, [rsi]
0x14006a0d7  lea     edx, [r14+2]
0x14006a0db  inc     r14d
0x14006a0de  mov     [rcx+rdx*8], rax
0x14006a0e2  mov     rdi, [rdi+28h]
0x14006a0e6  test    rdi, rdi
0x14006a0e9  jnz     short loc_14006A092
0x14006a0eb  xor     edx, edx
0x14006a0ed  cmp     edx, [rbx]
0x14006a0ef  jnb     short loc_14006A11C
0x14006a0f1  mov     rax, [rsi]
0x14006a0f4  cmp     [rax+rdx*8], r15
0x14006a0f8  jz      short loc_14006A0FE
0x14006a0fa  inc     edx
0x14006a0fc  jmp     short loc_14006A0ED
0x14006a0fe  mov     rdx, rbx
0x14006a101  mov     rcx, rsi
0x14006a104  call    FreeOtherNames
0x14006a109  mov     ecx, 8; dwErrCode
0x14006a10e  call    cs:__imp_SetLastError
0x14006a115  nop     dword ptr [rax+rax+00h]
0x14006a11a  jmp     short loc_14006A146
0x14006a11c  mov     r15d, 1
0x14006a122  jmp     short loc_14006A146
0x14006a124  call    cs:__imp_WSAGetLastError
0x14006a12b  nop     dword ptr [rax+rax+00h]
0x14006a130  mov     r8d, eax
0x14006a133  lea     rdx, aGetaddrinfoFai; "getaddrinfo() failed with %d."
0x14006a13a  lea     rcx, aBuildothername; "BuildOtherNamesFromMachineName"
0x14006a141  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a146  call    cs:__imp_WSACleanup
0x14006a14d  nop     dword ptr [rax+rax+00h]
0x14006a152  mov     rcx, [rsp+0A80h+ppResult]; pAddrInfo
0x14006a157  test    rcx, rcx
0x14006a15a  jz      short loc_14006A168
0x14006a15c  call    cs:__imp_FreeAddrInfoW
0x14006a163  nop     dword ptr [rax+rax+00h]
0x14006a168  mov     eax, r15d
0x14006a16b  mov     rcx, [rbp+980h+var_30]
0x14006a172  xor     rcx, rsp; StackCookie
0x14006a175  call    __security_check_cookie
0x14006a17a  mov     rbx, [rsp+0A80h+arg_10]
0x14006a182  add     rsp, 0A60h
0x14006a189  pop     r15
0x14006a18b  pop     r14
0x14006a18d  pop     rdi
0x14006a18e  pop     rsi
0x14006a18f  pop     rbp
0x14006a190  retn
```
