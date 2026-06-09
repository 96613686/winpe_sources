# SocketInit(ulong,ulong)

- ea: `0x18000d214`
- end: `0x18000d4c5`
- name: `?SocketInit@@YAHKK@Z`
- size: `689`
- prototype: `__int64 __fastcall(unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000c078`

## callees

- `0x18000d214`
- `0x1800271fc`
- `0x1800287d0`
- `0x18002911c`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d378`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2d0`
- `WS2_32!__imp_htons` at `0x18000d39f`
- `WS2_32!__imp_htons` at `0x18000d3ed`
- `WS2_32!__imp_htons` at `0x18000d434`
- `WS2_32!__imp_htons` at `0x18000d39f`
- `WS2_32!__imp_htons` at `0x18000d3ed`
- `WS2_32!__imp_htons` at `0x18000d434`
- `WS2_32!__imp_inet_addr` at `0x18000d3b9`
- `WS2_32!__imp_inet_addr` at `0x18000d3b9`
- `WS2_32!__imp_WSAStartup` at `0x18000d258`
- `WS2_32!__imp_WSAStartup` at `0x18000d258`
- `WS2_32!__imp_WSACleanup` at `0x18000d363`
- `WS2_32!__imp_WSACleanup` at `0x18000d363`

## pseudocode

```c
__int64 __fastcall SocketInit(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbx
  int v3; // eax
  DWORD LastError; // eax
  __int64 v5; // rdx
  LPCSTR v6; // r9
  __int64 v7; // rdx
  unsigned int v9; // eax
  WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  v2 = a2;
  memset_0(&WSAData, 0, sizeof(WSAData));
  v3 = WSAStartup(0x102u, &WSAData);
  if ( v3 )
  {
    if ( v3 == 10092 )
    {
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        return 0xFFFFFFFFLL;
      LastError = GetLastError();
      v5 = 10;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        return 0xFFFFFFFFLL;
      LastError = GetLastError();
      v5 = 11;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids, LastError);
    return 0xFFFFFFFFLL;
  }
  if ( WSAData.wVersion != 258 )
  {
    if ( WSAData.wHighVersion )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 12;
LABEL_18:
        WPP_SF_(*((_QWORD *)v6 + 2), v7, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids);
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 13;
        goto LABEL_18;
      }
    }
    if ( !WSACleanup() )
      SetLastError(0x276Cu);
    return 0xFFFFFFFFLL;
  }
  word_1800453A0 = 2;
  word_1800453A2 = htons(0x76Cu);
  v9 = inet_addr("239.255.255.250");
  dword_180045424 = 0;
  dword_1800453A4 = v9;
  word_180045420 = 23;
  dword_180045438 = 0;
  word_180045422 = htons(0x76Cu);
  xmmword_180045428 = xmmword_18003DEE0;
  if ( (unsigned int)(v2 - 1) <= 4 )
  {
    word_1800453B0 = 23;
    dword_1800453B4 = 0;
    dword_1800453C8 = 0;
    word_1800453B2 = htons(0x76Cu);
    xmmword_1800453B8 = *(_OWORD *)&(&in6SSDPAddresses)[2 * v2];
  }
  _InterlockedAdd(&dword_180045718, 1u);
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000d214  mov     [rsp+arg_0], rbx
0x18000d219  mov     [rsp+arg_8], rbp
0x18000d21e  push    rsi
0x18000d21f  sub     rsp, 1D0h
0x18000d226  mov     rax, cs:__security_cookie
0x18000d22d  xor     rax, rsp
0x18000d230  mov     [rsp+1D8h+var_18], rax
0x18000d238  mov     ebx, edx
0x18000d23a  lea     rcx, [rsp+1D8h+WSAData]; void *
0x18000d23f  xor     edx, edx; Val
0x18000d241  mov     r8d, 198h; Size
0x18000d247  call    memset_0
0x18000d24c  mov     esi, 102h
0x18000d251  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x18000d256  mov     ecx, esi; wVersionRequested
0x18000d258  call    cs:__imp_WSAStartup
0x18000d25f  nop     dword ptr [rax+rax+00h]
0x18000d264  test    eax, eax
0x18000d266  jz      loc_18000D300
0x18000d26c  cmp     eax, 276Ch
0x18000d271  jnz     short loc_18000D2AB
0x18000d273  mov     rdx, cs:WPP_GLOBAL_Control
0x18000d27a  lea     rcx, WPP_GLOBAL_Control
0x18000d281  cmp     rdx, rcx
0x18000d284  jz      loc_18000D384
0x18000d28a  mov     eax, 1
0x18000d28f  test    [rdx+1Ch], al
0x18000d292  jz      loc_18000D384
0x18000d298  call    cs:__imp_GetLastError
0x18000d29f  nop     dword ptr [rax+rax+00h]
0x18000d2a4  mov     edx, 0Ah
0x18000d2a9  jmp     short loc_18000D2E1
0x18000d2ab  mov     rdx, cs:WPP_GLOBAL_Control
0x18000d2b2  lea     rcx, WPP_GLOBAL_Control
0x18000d2b9  cmp     rdx, rcx
0x18000d2bc  jz      loc_18000D384
0x18000d2c2  mov     eax, 1
0x18000d2c7  test    [rdx+1Ch], al
0x18000d2ca  jz      loc_18000D384
0x18000d2d0  call    cs:__imp_GetLastError
0x18000d2d7  nop     dword ptr [rax+rax+00h]
0x18000d2dc  mov     edx, 0Bh
0x18000d2e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2e8  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x18000d2ef  mov     r9d, eax
0x18000d2f2  mov     rcx, [rcx+10h]
0x18000d2f6  call    WPP_SF_d
0x18000d2fb  jmp     loc_18000D384
0x18000d300  cmp     si, [rsp+1D8h+WSAData.wVersion]
0x18000d305  jz      loc_18000D38C
0x18000d30b  mov     eax, 1
0x18000d310  cmp     [rsp+1D8h+WSAData.wHighVersion], ax
0x18000d315  jb      short loc_18000D335
0x18000d317  mov     r9, cs:WPP_GLOBAL_Control
0x18000d31e  lea     rcx, WPP_GLOBAL_Control
0x18000d325  cmp     r9, rcx
0x18000d328  jz      short loc_18000D363
0x18000d32a  test    [r9+1Ch], al
0x18000d32e  jz      short loc_18000D363
0x18000d330  lea     edx, [rax+0Bh]
0x18000d333  jmp     short loc_18000D353
0x18000d335  mov     r9, cs:WPP_GLOBAL_Control
0x18000d33c  lea     rcx, WPP_GLOBAL_Control
0x18000d343  cmp     r9, rcx
0x18000d346  jz      short loc_18000D363
0x18000d348  test    [r9+1Ch], al
0x18000d34c  jz      short loc_18000D363
0x18000d34e  mov     edx, 0Dh
0x18000d353  mov     rcx, [r9+10h]
0x18000d357  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x18000d35e  call    WPP_SF_
0x18000d363  call    cs:__imp_WSACleanup
0x18000d36a  nop     dword ptr [rax+rax+00h]
0x18000d36f  test    eax, eax
0x18000d371  jnz     short loc_18000D384
0x18000d373  mov     ecx, 276Ch; dwErrCode
0x18000d378  call    cs:__imp_SetLastError
0x18000d37f  nop     dword ptr [rax+rax+00h]
0x18000d384  or      eax, 0FFFFFFFFh
0x18000d387  jmp     loc_18000D49F
0x18000d38c  mov     eax, 2
0x18000d391  mov     esi, 76Ch
0x18000d396  mov     ecx, esi; hostshort
0x18000d398  mov     cs:word_1800453A0, ax
0x18000d39f  call    cs:__imp_htons
0x18000d3a6  nop     dword ptr [rax+rax+00h]
0x18000d3ab  lea     rcx, String; "239.255.255.250"
0x18000d3b2  mov     cs:word_1800453A2, ax
0x18000d3b9  call    cs:__imp_inet_addr
0x18000d3c0  nop     dword ptr [rax+rax+00h]
0x18000d3c5  mov     ebp, 17h
0x18000d3ca  mov     cs:dword_180045424, 0
0x18000d3d4  mov     ecx, esi; hostshort
0x18000d3d6  mov     cs:dword_1800453A4, eax
0x18000d3dc  mov     cs:word_180045420, bp
0x18000d3e3  mov     cs:dword_180045438, 0
0x18000d3ed  call    cs:__imp_htons
0x18000d3f4  nop     dword ptr [rax+rax+00h]
0x18000d3f9  movaps  xmm0, cs:xmmword_18003DEE0
0x18000d400  mov     cs:word_180045422, ax
0x18000d407  lea     eax, [rbx-1]
0x18000d40a  movdqu  cs:xmmword_180045428, xmm0
0x18000d412  cmp     eax, 4
0x18000d415  ja      short loc_18000D460
0x18000d417  mov     ecx, esi; hostshort
0x18000d419  mov     cs:word_1800453B0, bp
0x18000d420  mov     cs:dword_1800453B4, 0
0x18000d42a  mov     cs:dword_1800453C8, 0
0x18000d434  call    cs:__imp_htons
0x18000d43b  nop     dword ptr [rax+rax+00h]
0x18000d440  mov     cs:word_1800453B2, ax
0x18000d447  lea     rcx, ?in6SSDPAddresses@@3PAUin6_addr@@A; in6_addr near * in6SSDPAddresses
0x18000d44e  mov     rax, rbx
0x18000d451  add     rax, rax
0x18000d454  movups  xmm0, xmmword ptr [rcx+rax*8]
0x18000d458  movdqu  cs:xmmword_1800453B8, xmm0
0x18000d460  mov     eax, 1
0x18000d465  lock add cs:dword_180045718, eax
0x18000d46c  mov     rax, cs:WPP_GLOBAL_Control
0x18000d473  lea     rcx, WPP_GLOBAL_Control
0x18000d47a  cmp     rax, rcx
0x18000d47d  jz      short loc_18000D49D
0x18000d47f  test    dword ptr [rax+1Ch], 2000h
0x18000d486  jz      short loc_18000D49D
0x18000d488  mov     rcx, [rax+10h]
0x18000d48c  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x18000d493  mov     edx, 0Eh
0x18000d498  call    WPP_SF_
0x18000d49d  xor     eax, eax
0x18000d49f  mov     rcx, [rsp+1D8h+var_18]
0x18000d4a7  xor     rcx, rsp; StackCookie
0x18000d4aa  call    __security_check_cookie
0x18000d4af  lea     r11, [rsp+1D8h+var_8]
0x18000d4b7  mov     rbx, [r11+10h]
0x18000d4bb  mov     rbp, [r11+18h]
0x18000d4bf  mov     rsp, r11
0x18000d4c2  pop     rsi
0x18000d4c3  retn
```
