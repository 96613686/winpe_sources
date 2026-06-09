# SocketInit(ulong,ulong)

- ea: `0x18000b7c4`
- end: `0x18000ba37`
- name: `?SocketInit@@YAHKK@Z`
- size: `627`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000a768`

## callees

- `0x18000b7c4`
- `0x1800255a8`
- `0x180026a30`
- `0x18002735c`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b909`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b874`
- `WS2_32!__imp_htons` at `0x18000b92a`
- `WS2_32!__imp_htons` at `0x18000b96c`
- `WS2_32!__imp_htons` at `0x18000b9ad`
- `WS2_32!__imp_htons` at `0x18000b92a`
- `WS2_32!__imp_htons` at `0x18000b96c`
- `WS2_32!__imp_htons` at `0x18000b9ad`
- `WS2_32!__imp_inet_addr` at `0x18000b93e`
- `WS2_32!__imp_inet_addr` at `0x18000b93e`
- `WS2_32!__imp_WSAStartup` at `0x18000b808`
- `WS2_32!__imp_WSAStartup` at `0x18000b808`
- `WS2_32!__imp_WSACleanup` at `0x18000b8fa`
- `WS2_32!__imp_WSACleanup` at `0x18000b8fa`

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
  word_1800422B0 = 2;
  word_1800422B2 = htons(0x76Cu);
  v9 = inet_addr("239.255.255.250");
  dword_180042334 = 0;
  dword_1800422B4 = v9;
  word_180042330 = 23;
  dword_180042348 = 0;
  word_180042332 = htons(0x76Cu);
  xmmword_180042338 = xmmword_18003AED0;
  if ( (unsigned int)(v2 - 1) <= 4 )
  {
    word_1800422C0 = 23;
    dword_1800422C4 = 0;
    dword_1800422D8 = 0;
    word_1800422C2 = htons(0x76Cu);
    xmmword_1800422C8 = *(_OWORD *)&(&in6SSDPAddresses)[2 * v2];
  }
  _InterlockedAdd(&dword_180042630, 1u);
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000b7c4  mov     [rsp+arg_0], rbx
0x18000b7c9  mov     [rsp+arg_8], rbp
0x18000b7ce  push    rsi
0x18000b7cf  sub     rsp, 1D0h
0x18000b7d6  mov     rax, cs:__security_cookie
0x18000b7dd  xor     rax, rsp
0x18000b7e0  mov     [rsp+1D8h+var_18], rax
0x18000b7e8  mov     ebx, edx
0x18000b7ea  lea     rcx, [rsp+1D8h+WSAData]; void *
0x18000b7ef  xor     edx, edx; Val
0x18000b7f1  mov     r8d, 198h; Size
0x18000b7f7  call    memset_0
0x18000b7fc  mov     esi, 102h
0x18000b801  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x18000b806  mov     ecx, esi; wVersionRequested
0x18000b808  call    cs:__imp_WSAStartup
0x18000b80e  test    eax, eax
0x18000b810  jz      loc_18000B89B
0x18000b816  cmp     eax, 276Ch
0x18000b81b  jnz     short loc_18000B84F
0x18000b81d  mov     rdx, cs:WPP_GLOBAL_Control
0x18000b824  lea     rcx, WPP_GLOBAL_Control
0x18000b82b  cmp     rdx, rcx
0x18000b82e  jz      loc_18000B90F
0x18000b834  mov     eax, 1
0x18000b839  test    [rdx+1Ch], al
0x18000b83c  jz      loc_18000B90F
0x18000b842  call    cs:__imp_GetLastError
0x18000b848  mov     edx, 0Ah
0x18000b84d  jmp     short loc_18000B87F
0x18000b84f  mov     rdx, cs:WPP_GLOBAL_Control
0x18000b856  lea     rcx, WPP_GLOBAL_Control
0x18000b85d  cmp     rdx, rcx
0x18000b860  jz      loc_18000B90F
0x18000b866  mov     eax, 1
0x18000b86b  test    [rdx+1Ch], al
0x18000b86e  jz      loc_18000B90F
0x18000b874  call    cs:__imp_GetLastError
0x18000b87a  mov     edx, 0Bh
0x18000b87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b886  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x18000b88d  mov     r9d, eax
0x18000b890  mov     rcx, [rcx+10h]
0x18000b894  call    WPP_SF_d
0x18000b899  jmp     short loc_18000B90F
0x18000b89b  cmp     si, [rsp+1D8h+WSAData.wVersion]
0x18000b8a0  jz      short loc_18000B917
0x18000b8a2  mov     eax, 1
0x18000b8a7  cmp     [rsp+1D8h+WSAData.wHighVersion], ax
0x18000b8ac  jb      short loc_18000B8CC
0x18000b8ae  mov     r9, cs:WPP_GLOBAL_Control
0x18000b8b5  lea     rcx, WPP_GLOBAL_Control
0x18000b8bc  cmp     r9, rcx
0x18000b8bf  jz      short loc_18000B8FA
0x18000b8c1  test    [r9+1Ch], al
0x18000b8c5  jz      short loc_18000B8FA
0x18000b8c7  lea     edx, [rax+0Bh]
0x18000b8ca  jmp     short loc_18000B8EA
0x18000b8cc  mov     r9, cs:WPP_GLOBAL_Control
0x18000b8d3  lea     rcx, WPP_GLOBAL_Control
0x18000b8da  cmp     r9, rcx
0x18000b8dd  jz      short loc_18000B8FA
0x18000b8df  test    [r9+1Ch], al
0x18000b8e3  jz      short loc_18000B8FA
0x18000b8e5  mov     edx, 0Dh
0x18000b8ea  mov     rcx, [r9+10h]
0x18000b8ee  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x18000b8f5  call    WPP_SF_
0x18000b8fa  call    cs:__imp_WSACleanup
0x18000b900  test    eax, eax
0x18000b902  jnz     short loc_18000B90F
0x18000b904  mov     ecx, 276Ch; dwErrCode
0x18000b909  call    cs:__imp_SetLastError
0x18000b90f  or      eax, 0FFFFFFFFh
0x18000b912  jmp     loc_18000BA12
0x18000b917  mov     eax, 2
0x18000b91c  mov     esi, 76Ch
0x18000b921  mov     ecx, esi; hostshort
0x18000b923  mov     cs:word_1800422B0, ax
0x18000b92a  call    cs:__imp_htons
0x18000b930  lea     rcx, String; "239.255.255.250"
0x18000b937  mov     cs:word_1800422B2, ax
0x18000b93e  call    cs:__imp_inet_addr
0x18000b944  mov     ebp, 17h
0x18000b949  mov     cs:dword_180042334, 0
0x18000b953  mov     ecx, esi; hostshort
0x18000b955  mov     cs:dword_1800422B4, eax
0x18000b95b  mov     cs:word_180042330, bp
0x18000b962  mov     cs:dword_180042348, 0
0x18000b96c  call    cs:__imp_htons
0x18000b972  movaps  xmm0, cs:xmmword_18003AED0
0x18000b979  mov     cs:word_180042332, ax
0x18000b980  lea     eax, [rbx-1]
0x18000b983  movdqu  cs:xmmword_180042338, xmm0
0x18000b98b  cmp     eax, 4
0x18000b98e  ja      short loc_18000B9D3
0x18000b990  mov     ecx, esi; hostshort
0x18000b992  mov     cs:word_1800422C0, bp
0x18000b999  mov     cs:dword_1800422C4, 0
0x18000b9a3  mov     cs:dword_1800422D8, 0
0x18000b9ad  call    cs:__imp_htons
0x18000b9b3  mov     cs:word_1800422C2, ax
0x18000b9ba  lea     rcx, ?in6SSDPAddresses@@3PAUin6_addr@@A; in6_addr near * in6SSDPAddresses
0x18000b9c1  mov     rax, rbx
0x18000b9c4  add     rax, rax
0x18000b9c7  movups  xmm0, xmmword ptr [rcx+rax*8]
0x18000b9cb  movdqu  cs:xmmword_1800422C8, xmm0
0x18000b9d3  mov     eax, 1
0x18000b9d8  lock add cs:dword_180042630, eax
0x18000b9df  mov     rax, cs:WPP_GLOBAL_Control
0x18000b9e6  lea     rcx, WPP_GLOBAL_Control
0x18000b9ed  cmp     rax, rcx
0x18000b9f0  jz      short loc_18000BA10
0x18000b9f2  test    dword ptr [rax+1Ch], 2000h
0x18000b9f9  jz      short loc_18000BA10
0x18000b9fb  mov     rcx, [rax+10h]
0x18000b9ff  lea     r8, WPP_1d5d1dafa2a1394101ec19fd13ee7c68_Traceguids
0x18000ba06  mov     edx, 0Eh
0x18000ba0b  call    WPP_SF_
0x18000ba10  xor     eax, eax
0x18000ba12  mov     rcx, [rsp+1D8h+var_18]
0x18000ba1a  xor     rcx, rsp; StackCookie
0x18000ba1d  call    __security_check_cookie
0x18000ba22  lea     r11, [rsp+1D8h+var_8]
0x18000ba2a  mov     rbx, [r11+10h]
0x18000ba2e  mov     rbp, [r11+18h]
0x18000ba32  mov     rsp, r11
0x18000ba35  pop     rsi
0x18000ba36  retn
```
