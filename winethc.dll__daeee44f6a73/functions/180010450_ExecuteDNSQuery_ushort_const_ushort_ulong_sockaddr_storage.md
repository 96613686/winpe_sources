# ExecuteDNSQuery(ushort const *,ushort,ulong,sockaddr_storage *)

- ea: `0x180010450`
- end: `0x18001058a`
- name: `?ExecuteDNSQuery@@YAJPEBGGKPEAUsockaddr_storage@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(PCWSTR pNodeName, unsigned __int16, unsigned int, struct sockaddr_storage *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180005b30`
- `0x180009858`
- `0x18000f5f8`

## callees

- `0x180010450`
- `0x180012d62`
- `0x180012d6e`
- `0x180012db0`

## import_xrefs

- `WS2_32!GetAddrInfoW` at `0x1800104f9`
- `WS2_32!GetAddrInfoW` at `0x1800104f9`
- `WS2_32!FreeAddrInfoW` at `0x18001054a`
- `WS2_32!FreeAddrInfoW` at `0x18001054a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800104af`
- `WS2_32!__imp_WSAGetLastError` at `0x180010509`
- `WS2_32!__imp_WSAGetLastError` at `0x1800104af`
- `WS2_32!__imp_WSAGetLastError` at `0x180010509`
- `WS2_32!__imp_WSAStartup` at `0x18001049f`
- `WS2_32!__imp_WSAStartup` at `0x18001049f`
- `WS2_32!__imp_WSACleanup` at `0x180010556`
- `WS2_32!__imp_WSACleanup` at `0x180010556`

## pseudocode

```c
__int64 __fastcall ExecuteDNSQuery(PCWSTR pNodeName, __int64 a2, __int64 a3, struct sockaddr_storage *a4)
{
  int Error; // eax
  unsigned int v7; // ebx
  int v8; // eax
  struct addrinfoW *v9; // rdi
  PADDRINFOW ppResult; // [rsp+20h] [rbp-1F8h] BYREF
  ADDRINFOW pHints; // [rsp+28h] [rbp-1F0h] BYREF
  struct WSAData WSAData; // [rsp+60h] [rbp-1B8h] BYREF

  ppResult = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( WSAStartup(0x202u, &WSAData) )
  {
    Error = WSAGetLastError();
    v7 = Error;
    if ( Error > 0 )
      return (unsigned __int16)Error | 0x80070000;
  }
  else
  {
    memset(&pHints, 0, sizeof(pHints));
    if ( GetAddrInfoW(pNodeName, L"0", &pHints, &ppResult) )
    {
      v8 = WSAGetLastError();
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      v9 = ppResult;
      v7 = 0;
      if ( ppResult )
      {
        if ( a4 )
          memcpy_0(a4, ppResult->ai_addr, ppResult->ai_addrlen);
        FreeAddrInfoW(v9);
      }
    }
    WSACleanup();
  }
  return v7;
}

```

## disassembly

```asm
0x180010450  mov     [rsp+arg_8], rbx
0x180010455  mov     [rsp+arg_10], rsi
0x18001045a  push    rdi
0x18001045b  sub     rsp, 210h
0x180010462  mov     rax, cs:__security_cookie
0x180010469  xor     rax, rsp
0x18001046c  mov     [rsp+218h+var_18], rax
0x180010474  mov     rbx, rcx
0x180010477  mov     [rsp+218h+ppResult], 0
0x180010480  lea     rcx, [rsp+218h+WSAData]; void *
0x180010485  xor     edx, edx; Val
0x180010487  mov     r8d, 198h; Size
0x18001048d  mov     rsi, r9
0x180010490  call    memset_0
0x180010495  mov     ecx, 202h; wVersionRequested
0x18001049a  lea     rdx, [rsp+218h+WSAData]; lpWSAData
0x18001049f  call    cs:__imp_WSAStartup
0x1800104a6  nop     dword ptr [rax+rax+00h]
0x1800104ab  test    eax, eax
0x1800104ad  jz      short loc_1800104D3
0x1800104af  call    cs:__imp_WSAGetLastError
0x1800104b6  nop     dword ptr [rax+rax+00h]
0x1800104bb  mov     ebx, eax
0x1800104bd  test    eax, eax
0x1800104bf  jle     loc_180010562
0x1800104c5  movzx   ebx, ax
0x1800104c8  or      ebx, 80070000h
0x1800104ce  jmp     loc_180010562
0x1800104d3  xorps   xmm0, xmm0
0x1800104d6  lea     r9, [rsp+218h+ppResult]; ppResult
0x1800104db  lea     r8, [rsp+218h+pHints]; pHints
0x1800104e0  mov     rcx, rbx; pNodeName
0x1800104e3  lea     rdx, pServiceName; "0"
0x1800104ea  movups  xmmword ptr [rsp+218h+pHints.ai_flags], xmm0
0x1800104ef  movups  xmmword ptr [rsp+218h+pHints.ai_addrlen], xmm0
0x1800104f4  movups  xmmword ptr [rsp+218h+pHints.ai_addr], xmm0
0x1800104f9  call    cs:__imp_GetAddrInfoW
0x180010500  nop     dword ptr [rax+rax+00h]
0x180010505  test    eax, eax
0x180010507  jz      short loc_180010526
0x180010509  call    cs:__imp_WSAGetLastError
0x180010510  nop     dword ptr [rax+rax+00h]
0x180010515  mov     ebx, eax
0x180010517  test    eax, eax
0x180010519  jle     short loc_180010556
0x18001051b  movzx   ebx, ax
0x18001051e  or      ebx, 80070000h
0x180010524  jmp     short loc_180010556
0x180010526  mov     rdi, [rsp+218h+ppResult]
0x18001052b  xor     ebx, ebx
0x18001052d  test    rdi, rdi
0x180010530  jz      short loc_180010556
0x180010532  test    rsi, rsi
0x180010535  jz      short loc_180010547
0x180010537  mov     r8, [rdi+10h]; Size
0x18001053b  mov     rcx, rsi; void *
0x18001053e  mov     rdx, [rdi+20h]; Src
0x180010542  call    memcpy_0
0x180010547  mov     rcx, rdi; pAddrInfo
0x18001054a  call    cs:__imp_FreeAddrInfoW
0x180010551  nop     dword ptr [rax+rax+00h]
0x180010556  call    cs:__imp_WSACleanup
0x18001055d  nop     dword ptr [rax+rax+00h]
0x180010562  mov     eax, ebx
0x180010564  mov     rcx, [rsp+218h+var_18]
0x18001056c  xor     rcx, rsp; StackCookie
0x18001056f  call    __security_check_cookie
0x180010574  lea     r11, [rsp+218h+var_8]
0x18001057c  mov     rbx, [r11+18h]
0x180010580  mov     rsi, [r11+20h]
0x180010584  mov     rsp, r11
0x180010587  pop     rdi
0x180010588  retn
```
