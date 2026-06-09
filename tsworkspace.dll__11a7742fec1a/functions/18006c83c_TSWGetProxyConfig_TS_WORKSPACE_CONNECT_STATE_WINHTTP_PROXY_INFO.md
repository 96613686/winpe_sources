# TSWGetProxyConfig(TS_WORKSPACE_CONNECT_STATE *,_WINHTTP_PROXY_INFO &)

- ea: `0x18006c83c`
- end: `0x18006ca12`
- name: `?TSWGetProxyConfig@@YAJPEAUTS_WORKSPACE_CONNECT_STATE@@AEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `470`
- prototype: `int(struct TS_WORKSPACE_CONNECT_STATE *, struct _WINHTTP_PROXY_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006cb60`

## callees

- `0x18000d8d4`
- `0x18006c83c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c8d7`
- `KERNEL32!GlobalFree` at `0x18006c973`
- `KERNEL32!GlobalFree` at `0x18006c9ca`
- `KERNEL32!GlobalFree` at `0x18006c9e3`
- `KERNEL32!GlobalFree` at `0x18006c9f2`
- `KERNEL32!GlobalFree` at `0x18006ca01`
- `KERNEL32!GlobalFree` at `0x18006c973`
- `KERNEL32!GlobalFree` at `0x18006c9ca`
- `KERNEL32!GlobalFree` at `0x18006c9e3`
- `KERNEL32!GlobalFree` at `0x18006c9f2`
- `KERNEL32!GlobalFree` at `0x18006ca01`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18006c868`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18006c868`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18006c8cd`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18006c8cd`

## pseudocode

```c
__int64 __fastcall TSWGetProxyConfig(HINTERNET *a1, struct _WINHTTP_PROXY_INFO *a2)
{
  DWORD dwFlags; // eax
  const WCHAR *v5; // rax
  unsigned int v6; // ebx
  LPWSTR lpszProxy; // rcx
  LPWSTR lpszProxyBypass; // rax
  _BYTE *v9; // rcx
  unsigned __int16 *v10; // rax
  int v11; // r9d
  int v12; // edx
  unsigned __int16 *v13; // rax
  int v14; // r9d
  int v15; // edx
  _BYTE *v16; // rcx
  unsigned __int16 *v17; // rax
  int v18; // r8d
  int v19; // edx
  unsigned __int16 *v20; // rax
  int v21; // r8d
  int v22; // edx
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+20h] [rbp-48h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+40h] [rbp-28h] BYREF

  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
  {
    if ( pProxyConfig.fAutoDetect )
    {
      dwFlags = 1;
      pAutoProxyOptions.dwAutoDetectFlags = 3;
      pAutoProxyOptions.dwFlags = 1;
    }
    else
    {
      dwFlags = pAutoProxyOptions.dwFlags;
    }
    if ( pProxyConfig.lpszAutoConfigUrl )
    {
      pAutoProxyOptions.lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
      pAutoProxyOptions.dwFlags = dwFlags | 2;
    }
  }
  else
  {
    pAutoProxyOptions.dwFlags = 1;
    pAutoProxyOptions.dwAutoDetectFlags = 3;
  }
  pAutoProxyOptions.fAutoLogonIfChallenged = 1;
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 6);
  if ( !WinHttpGetProxyForUrl(a1[1], v5, &pAutoProxyOptions, (WINHTTP_PROXY_INFO *)a2) )
  {
    if ( GetLastError() == 12017 )
    {
      v6 = -2147012879;
      goto LABEL_34;
    }
    lpszProxy = pProxyConfig.lpszProxy;
    if ( pProxyConfig.lpszProxy )
    {
      lpszProxyBypass = pProxyConfig.lpszProxyBypass;
      pProxyConfig.lpszProxyBypass = 0;
      *(_DWORD *)a2 = 3;
      pProxyConfig.lpszProxy = 0;
      *((_QWORD *)a2 + 1) = lpszProxy;
      *((_QWORD *)a2 + 2) = lpszProxyBypass;
    }
  }
  v9 = (_BYTE *)*((_QWORD *)a2 + 1);
  if ( v9 )
  {
    v10 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
    do
    {
      v11 = *(unsigned __int16 *)((char *)v10 + (char *)asc_1800EE9EC - v9);
      v12 = *v10 - v11;
      if ( v12 )
        break;
      ++v10;
    }
    while ( v11 );
    if ( !v12 )
      goto LABEL_22;
    v13 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
    do
    {
      v14 = *(unsigned __int16 *)((char *)v13 + (char *)asc_1800EE9E4 - v9);
      v15 = *v13 - v14;
      if ( v15 )
        break;
      ++v13;
    }
    while ( v14 );
    if ( !v15 )
    {
LABEL_22:
      GlobalFree(v9);
      *((_QWORD *)a2 + 1) = 0;
    }
  }
  v16 = (_BYTE *)*((_QWORD *)a2 + 2);
  if ( v16 )
  {
    v17 = (unsigned __int16 *)*((_QWORD *)a2 + 2);
    do
    {
      v18 = *(unsigned __int16 *)((char *)v17 + (char *)asc_1800EE9EC - v16);
      v19 = *v17 - v18;
      if ( v19 )
        break;
      ++v17;
    }
    while ( v18 );
    if ( !v19 )
      goto LABEL_32;
    v20 = (unsigned __int16 *)*((_QWORD *)a2 + 2);
    do
    {
      v21 = *(unsigned __int16 *)((char *)v20 + (char *)asc_1800EE9E4 - v16);
      v22 = *v20 - v21;
      if ( v22 )
        break;
      ++v20;
    }
    while ( v21 );
    if ( !v22 )
    {
LABEL_32:
      GlobalFree(v16);
      *((_QWORD *)a2 + 2) = 0;
    }
  }
  v6 = 0;
LABEL_34:
  if ( pProxyConfig.lpszAutoConfigUrl )
    GlobalFree(pProxyConfig.lpszAutoConfigUrl);
  if ( pProxyConfig.lpszProxy )
    GlobalFree(pProxyConfig.lpszProxy);
  if ( pProxyConfig.lpszProxyBypass )
    GlobalFree(pProxyConfig.lpszProxyBypass);
  return v6;
}

```

## disassembly

```asm
0x18006c83c  push    rbp
0x18006c83e  push    rbx
0x18006c83f  push    rsi
0x18006c840  push    rdi
0x18006c841  mov     rbp, rsp
0x18006c844  sub     rsp, 68h
0x18006c848  xorps   xmm0, xmm0
0x18006c84b  xorps   xmm1, xmm1
0x18006c84e  mov     rdi, rcx
0x18006c851  mov     rbx, rdx
0x18006c854  lea     rcx, [rbp+pProxyConfig]; pProxyConfig
0x18006c858  movups  xmmword ptr [rbp+pProxyConfig.fAutoDetect], xmm0
0x18006c85c  movups  xmmword ptr [rbp+pProxyConfig.lpszProxy], xmm0
0x18006c860  movups  xmmword ptr [rbp+pAutoProxyOptions.dwFlags], xmm1
0x18006c864  movups  xmmword ptr [rbp+pAutoProxyOptions.lpvReserved], xmm1
0x18006c868  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18006c86e  test    eax, eax
0x18006c870  jz      short loc_18006C8A1
0x18006c872  cmp     [rbp+pProxyConfig.fAutoDetect], 0
0x18006c876  jz      short loc_18006C889
0x18006c878  mov     eax, 1
0x18006c87d  mov     [rbp+pAutoProxyOptions.dwAutoDetectFlags], 3
0x18006c884  mov     [rbp+pAutoProxyOptions.dwFlags], eax
0x18006c887  jmp     short loc_18006C88C
0x18006c889  mov     eax, [rbp+pAutoProxyOptions.dwFlags]
0x18006c88c  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]
0x18006c890  test    rcx, rcx
0x18006c893  jz      short loc_18006C8AF
0x18006c895  or      eax, 2
0x18006c898  mov     [rbp+pAutoProxyOptions.lpszAutoConfigUrl], rcx
0x18006c89c  mov     [rbp+pAutoProxyOptions.dwFlags], eax
0x18006c89f  jmp     short loc_18006C8AF
0x18006c8a1  mov     [rbp+pAutoProxyOptions.dwFlags], 1
0x18006c8a8  mov     [rbp+pAutoProxyOptions.dwAutoDetectFlags], 3
0x18006c8af  lea     rcx, [rdi+30h]
0x18006c8b3  mov     [rbp+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x18006c8ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006c8bf  mov     rcx, [rdi+8]; hSession
0x18006c8c3  lea     r8, [rbp+pAutoProxyOptions]; pAutoProxyOptions
0x18006c8c7  mov     r9, rbx; pProxyInfo
0x18006c8ca  mov     rdx, rax; lpcwszUrl
0x18006c8cd  call    cs:__imp_WinHttpGetProxyForUrl
0x18006c8d3  test    eax, eax
0x18006c8d5  jnz     short loc_18006C916
0x18006c8d7  call    cs:__imp_GetLastError
0x18006c8dd  cmp     eax, 2EF1h
0x18006c8e2  jnz     short loc_18006C8EE
0x18006c8e4  mov     ebx, 80072EF1h
0x18006c8e9  jmp     loc_18006C9DA
0x18006c8ee  mov     rcx, [rbp+pProxyConfig.lpszProxy]
0x18006c8f2  test    rcx, rcx
0x18006c8f5  jz      short loc_18006C916
0x18006c8f7  mov     rax, [rbp+pProxyConfig.lpszProxyBypass]
0x18006c8fb  xorps   xmm0, xmm0
0x18006c8fe  movdqu  xmmword ptr [rbp+pProxyConfig.lpszProxy], xmm0
0x18006c903  mov     dword ptr [rbx], 3
0x18006c909  movq    [rbp+pProxyConfig.lpszProxy], xmm0
0x18006c90e  mov     [rbx+8], rcx
0x18006c912  mov     [rbx+10h], rax
0x18006c916  mov     rcx, [rbx+8]; hMem
0x18006c91a  lea     rdi, asc_1800EE9EC; ":"
0x18006c921  lea     rsi, asc_1800EE9E4; "::"
0x18006c928  test    rcx, rcx
0x18006c92b  jz      short loc_18006C981
0x18006c92d  mov     r8, rdi
0x18006c930  mov     rax, rcx
0x18006c933  sub     r8, rcx
0x18006c936  movzx   edx, word ptr [rax]
0x18006c939  movzx   r9d, word ptr [rax+r8]
0x18006c93e  sub     edx, r9d
0x18006c941  jnz     short loc_18006C94C
0x18006c943  add     rax, 2
0x18006c947  test    r9d, r9d
0x18006c94a  jnz     short loc_18006C936
0x18006c94c  test    edx, edx
0x18006c94e  jz      short loc_18006C973
0x18006c950  mov     r8, rsi
0x18006c953  mov     rax, rcx
0x18006c956  sub     r8, rcx
0x18006c959  movzx   edx, word ptr [rax]
0x18006c95c  movzx   r9d, word ptr [rax+r8]
0x18006c961  sub     edx, r9d
0x18006c964  jnz     short loc_18006C96F
0x18006c966  add     rax, 2
0x18006c96a  test    r9d, r9d
0x18006c96d  jnz     short loc_18006C959
0x18006c96f  test    edx, edx
0x18006c971  jnz     short loc_18006C981
0x18006c973  call    cs:__imp_GlobalFree
0x18006c979  mov     qword ptr [rbx+8], 0
0x18006c981  mov     rcx, [rbx+10h]; hMem
0x18006c985  test    rcx, rcx
0x18006c988  jz      short loc_18006C9D8
0x18006c98a  mov     rax, rcx
0x18006c98d  sub     rdi, rcx
0x18006c990  movzx   edx, word ptr [rax]
0x18006c993  movzx   r8d, word ptr [rax+rdi]
0x18006c998  sub     edx, r8d
0x18006c99b  jnz     short loc_18006C9A6
0x18006c99d  add     rax, 2
0x18006c9a1  test    r8d, r8d
0x18006c9a4  jnz     short loc_18006C990
0x18006c9a6  test    edx, edx
0x18006c9a8  jz      short loc_18006C9CA
0x18006c9aa  mov     rax, rcx
0x18006c9ad  sub     rsi, rcx
0x18006c9b0  movzx   edx, word ptr [rax]
0x18006c9b3  movzx   r8d, word ptr [rax+rsi]
0x18006c9b8  sub     edx, r8d
0x18006c9bb  jnz     short loc_18006C9C6
0x18006c9bd  add     rax, 2
0x18006c9c1  test    r8d, r8d
0x18006c9c4  jnz     short loc_18006C9B0
0x18006c9c6  test    edx, edx
0x18006c9c8  jnz     short loc_18006C9D8
0x18006c9ca  call    cs:__imp_GlobalFree
0x18006c9d0  mov     qword ptr [rbx+10h], 0
0x18006c9d8  xor     ebx, ebx
0x18006c9da  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]; hMem
0x18006c9de  test    rcx, rcx
0x18006c9e1  jz      short loc_18006C9E9
0x18006c9e3  call    cs:__imp_GlobalFree
0x18006c9e9  mov     rcx, [rbp+pProxyConfig.lpszProxy]; hMem
0x18006c9ed  test    rcx, rcx
0x18006c9f0  jz      short loc_18006C9F8
0x18006c9f2  call    cs:__imp_GlobalFree
0x18006c9f8  mov     rcx, [rbp+pProxyConfig.lpszProxyBypass]; hMem
0x18006c9fc  test    rcx, rcx
0x18006c9ff  jz      short loc_18006CA07
0x18006ca01  call    cs:__imp_GlobalFree
0x18006ca07  mov     eax, ebx
0x18006ca09  add     rsp, 68h
0x18006ca0d  pop     rdi
0x18006ca0e  pop     rsi
0x18006ca0f  pop     rbx
0x18006ca10  pop     rbp
0x18006ca11  retn
```
