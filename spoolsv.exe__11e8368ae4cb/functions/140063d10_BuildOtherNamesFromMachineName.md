# BuildOtherNamesFromMachineName

- ea: `0x140063d10`
- end: `0x140063f6b`
- name: `BuildOtherNamesFromMachineName`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140065710`

## callees

- `0x1400041c0`
- `0x14000a620`
- `0x1400140cc`
- `0x14002abc0`
- `0x14002b810`
- `0x140063d10`
- `0x1400646b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140063dd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140063f00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140063dd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140063f00`
- `KERNEL32!GetComputerNameW` at `0x140063dff`
- `KERNEL32!GetComputerNameW` at `0x140063dff`
- `WS2_32!FreeAddrInfoW` at `0x140063f3c`
- `WS2_32!FreeAddrInfoW` at `0x140063f3c`
- `WS2_32!GetAddrInfoW` at `0x140063e18`
- `WS2_32!GetAddrInfoW` at `0x140063e18`
- `WS2_32!GetNameInfoW` at `0x140063eb0`
- `WS2_32!GetNameInfoW` at `0x140063eb0`
- `WS2_32!__imp_WSAGetLastError` at `0x140063f10`
- `WS2_32!__imp_WSAGetLastError` at `0x140063f10`
- `WS2_32!__imp_WSAStartup` at `0x140063daa`
- `WS2_32!__imp_WSAStartup` at `0x140063daa`
- `WS2_32!__imp_WSACleanup` at `0x140063f2c`
- `WS2_32!__imp_WSACleanup` at `0x140063f2c`

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
0x140063d10  mov     [rsp-8+arg_10], rbx
0x140063d15  push    rbp
0x140063d16  push    rsi
0x140063d17  push    rdi
0x140063d18  push    r14
0x140063d1a  push    r15
0x140063d1c  lea     rbp, [rsp-960h]
0x140063d24  sub     rsp, 0A60h
0x140063d2b  mov     rax, cs:__security_cookie
0x140063d32  xor     rax, rsp
0x140063d35  mov     [rbp+980h+var_30], rax
0x140063d3c  xorps   xmm0, xmm0
0x140063d3f  mov     [rsp+0A80h+ppResult], 0
0x140063d48  mov     rbx, rdx
0x140063d4b  mov     [rsp+0A80h+dwErrCode], 0
0x140063d53  mov     rsi, rcx
0x140063d56  xor     edx, edx; Val
0x140063d58  lea     rcx, [rbp+980h+WSAData]; void *
0x140063d5c  mov     r8d, 198h; Size
0x140063d62  movups  xmmword ptr [rsp+0A80h+pHints.ai_flags], xmm0
0x140063d67  movups  xmmword ptr [rsp+0A80h+pHints.ai_addrlen], xmm0
0x140063d6c  movups  xmmword ptr [rsp+0A80h+pHints.ai_addr], xmm0
0x140063d71  call    memset_0
0x140063d76  xor     edx, edx; Val
0x140063d78  lea     rcx, [rbp+980h+pNodeBuffer]; void *
0x140063d7f  mov     r8d, 802h; Size
0x140063d85  call    memset_0
0x140063d8a  xorps   xmm0, xmm0
0x140063d8d  mov     dword ptr [rbx], 0
0x140063d93  mov     ecx, 202h; wVersionRequested
0x140063d98  lea     rdx, [rbp+980h+WSAData]; lpWSAData
0x140063d9c  movups  xmmword ptr [rbp+980h+Buffer], xmm0
0x140063da3  movups  [rbp+980h+var_850], xmm0
0x140063daa  call    cs:__imp_WSAStartup
0x140063db0  mov     [rsp+0A80h+dwErrCode], eax
0x140063db4  test    eax, eax
0x140063db6  jz      short loc_140063DDF
0x140063db8  mov     r8d, eax
0x140063dbb  lea     rdx, aWsastartupFail; "WSAStartup failed.  Error %d."
0x140063dc2  lea     rcx, aBuildothername; "BuildOtherNamesFromMachineName"
0x140063dc9  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140063dce  mov     ecx, [rsp+0A80h+dwErrCode]; dwErrCode
0x140063dd2  call    cs:__imp_SetLastError
0x140063dd8  xor     eax, eax
0x140063dda  jmp     loc_140063F45
0x140063ddf  lea     rdx, [rsp+0A80h+dwErrCode]; nSize
0x140063de4  mov     qword ptr [rsp+0A80h+pHints.ai_flags], 2
0x140063ded  lea     rcx, [rbp+980h+Buffer]; lpBuffer
0x140063df4  mov     [rsp+0A80h+dwErrCode], 10h
0x140063dfc  xor     r15d, r15d
0x140063dff  call    cs:__imp_GetComputerNameW
0x140063e05  lea     r9, [rsp+0A80h+ppResult]; ppResult
0x140063e0a  xor     edx, edx; pServiceName
0x140063e0c  lea     r8, [rsp+0A80h+pHints]; pHints
0x140063e11  lea     rcx, [rbp+980h+Buffer]; pNodeName
0x140063e18  call    cs:__imp_GetAddrInfoW
0x140063e1e  test    eax, eax
0x140063e20  jnz     loc_140063F10
0x140063e26  mov     rax, [rsp+0A80h+ppResult]
0x140063e2b  xor     ecx, ecx
0x140063e2d  jmp     short loc_140063E37
0x140063e2f  inc     ecx
0x140063e31  mov     [rbx], ecx
0x140063e33  mov     rax, [rax+28h]
0x140063e37  test    rax, rax
0x140063e3a  jnz     short loc_140063E2F
0x140063e3c  add     ecx, 2
0x140063e3f  mov     [rbx], ecx
0x140063e41  shl     ecx, 3; dwBytes
0x140063e44  call    DllAllocSplMem
0x140063e49  mov     [rsi], rax
0x140063e4c  test    rax, rax
0x140063e4f  jnz     short loc_140063E59
0x140063e51  mov     [rbx], r15d
0x140063e54  jmp     loc_140063F2C
0x140063e59  lea     rcx, Buffer; Src
0x140063e60  call    AllocSplStr
0x140063e65  mov     rcx, [rsi]
0x140063e68  mov     [rcx], rax
0x140063e6b  mov     rcx, [rsp+0A80h+ppResult]
0x140063e70  mov     rcx, [rcx+18h]; Src
0x140063e74  call    AllocSplStr
0x140063e79  mov     rcx, [rsi]
0x140063e7c  xor     r14d, r14d
0x140063e7f  mov     [rcx+8], rax
0x140063e83  mov     rdi, [rsp+0A80h+ppResult]
0x140063e88  jmp     short loc_140063ED8
0x140063e8a  mov     edx, [rdi+10h]; SockaddrLength
0x140063e8d  lea     r8, [rbp+980h+pNodeBuffer]; pNodeBuffer
0x140063e94  mov     rcx, [rdi+20h]; pSockaddr
0x140063e98  mov     r9d, 401h; NodeBufferSize
0x140063e9e  mov     [rsp+0A80h+Flags], 2; Flags
0x140063ea6  mov     [rsp+0A80h+ServiceBufferSize], r15d; ServiceBufferSize
0x140063eab  mov     [rsp+0A80h+pServiceBuffer], r15; pServiceBuffer
0x140063eb0  call    cs:__imp_GetNameInfoW
0x140063eb6  test    eax, eax
0x140063eb8  jnz     short loc_140063EDD
0x140063eba  lea     rcx, [rbp+980h+pNodeBuffer]; Src
0x140063ec1  call    AllocSplStr
0x140063ec6  mov     rcx, [rsi]
0x140063ec9  lea     edx, [r14+2]
0x140063ecd  inc     r14d
0x140063ed0  mov     [rcx+rdx*8], rax
0x140063ed4  mov     rdi, [rdi+28h]
0x140063ed8  test    rdi, rdi
0x140063edb  jnz     short loc_140063E8A
0x140063edd  xor     edx, edx
0x140063edf  cmp     edx, [rbx]
0x140063ee1  jnb     short loc_140063F08
0x140063ee3  mov     rax, [rsi]
0x140063ee6  cmp     [rax+rdx*8], r15
0x140063eea  jz      short loc_140063EF0
0x140063eec  inc     edx
0x140063eee  jmp     short loc_140063EDF
0x140063ef0  mov     rdx, rbx
0x140063ef3  mov     rcx, rsi
0x140063ef6  call    FreeOtherNames
0x140063efb  mov     ecx, 8; dwErrCode
0x140063f00  call    cs:__imp_SetLastError
0x140063f06  jmp     short loc_140063F2C
0x140063f08  mov     r15d, 1
0x140063f0e  jmp     short loc_140063F2C
0x140063f10  call    cs:__imp_WSAGetLastError
0x140063f16  mov     r8d, eax
0x140063f19  lea     rdx, aGetaddrinfoFai; "getaddrinfo() failed with %d."
0x140063f20  lea     rcx, aBuildothername; "BuildOtherNamesFromMachineName"
0x140063f27  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140063f2c  call    cs:__imp_WSACleanup
0x140063f32  mov     rcx, [rsp+0A80h+ppResult]; pAddrInfo
0x140063f37  test    rcx, rcx
0x140063f3a  jz      short loc_140063F42
0x140063f3c  call    cs:__imp_FreeAddrInfoW
0x140063f42  mov     eax, r15d
0x140063f45  mov     rcx, [rbp+980h+var_30]
0x140063f4c  xor     rcx, rsp; StackCookie
0x140063f4f  call    __security_check_cookie
0x140063f54  mov     rbx, [rsp+0A80h+arg_10]
0x140063f5c  add     rsp, 0A60h
0x140063f63  pop     r15
0x140063f65  pop     r14
0x140063f67  pop     rdi
0x140063f68  pop     rsi
0x140063f69  pop     rbp
0x140063f6a  retn
```
