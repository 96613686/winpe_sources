# RdpWinRadcHttpRequest::GetProxyConfig(void *,_WINHTTP_PROXY_INFO *)

- ea: `0x1800903b0`
- end: `0x180090579`
- name: `?GetProxyConfig@RdpWinRadcHttpRequest@@AEAAJPEAXPEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `457`
- prototype: `int(RdpWinRadcHttpRequest *__hidden this, void *, struct _WINHTTP_PROXY_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180091acc`

## callees

- `0x1800903b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090445`
- `KERNEL32!GlobalFree` at `0x1800904ce`
- `KERNEL32!GlobalFree` at `0x180090521`
- `KERNEL32!GlobalFree` at `0x18009053a`
- `KERNEL32!GlobalFree` at `0x180090551`
- `KERNEL32!GlobalFree` at `0x180090568`
- `KERNEL32!GlobalFree` at `0x1800904ce`
- `KERNEL32!GlobalFree` at `0x180090521`
- `KERNEL32!GlobalFree` at `0x18009053a`
- `KERNEL32!GlobalFree` at `0x180090551`
- `KERNEL32!GlobalFree` at `0x180090568`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800903df`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800903df`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18009043b`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18009043b`

## pseudocode

```c
__int64 __fastcall RdpWinRadcHttpRequest::GetProxyConfig(
        RdpWinRadcHttpRequest *this,
        void *a2,
        struct _WINHTTP_PROXY_INFO *a3)
{
  DWORD dwFlags; // eax
  const WCHAR *v7; // rdx
  unsigned int v8; // ebx
  LPWSTR lpszProxy; // rcx
  LPWSTR lpszProxyBypass; // rax
  unsigned __int16 *v11; // r8
  int v12; // edx
  int v13; // ecx
  unsigned __int16 *v14; // r8
  int v15; // edx
  int v16; // ecx
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
  v7 = (const WCHAR *)*((_QWORD *)this + 7);
  pAutoProxyOptions.fAutoLogonIfChallenged = 1;
  if ( !WinHttpGetProxyForUrl(a2, v7, &pAutoProxyOptions, (WINHTTP_PROXY_INFO *)a3) )
  {
    if ( GetLastError() == 12017 )
    {
      v8 = -2147012879;
      goto LABEL_32;
    }
    lpszProxy = pProxyConfig.lpszProxy;
    if ( pProxyConfig.lpszProxy )
    {
      lpszProxyBypass = pProxyConfig.lpszProxyBypass;
      pProxyConfig.lpszProxyBypass = 0;
      *(_DWORD *)a3 = 3;
      pProxyConfig.lpszProxy = 0;
      *((_QWORD *)a3 + 1) = lpszProxy;
      *((_QWORD *)a3 + 2) = lpszProxyBypass;
    }
  }
  v11 = (unsigned __int16 *)*((_QWORD *)a3 + 1);
  if ( v11 )
  {
    v12 = *v11 - 58;
    if ( *v11 == 58 )
      v12 = v11[1];
    if ( !v12 )
      goto LABEL_21;
    v13 = *v11 - 58;
    if ( *v11 == 58 )
    {
      v13 = v11[1] - 58;
      if ( v11[1] == 58 )
        v13 = v11[2];
    }
    if ( !v13 )
    {
LABEL_21:
      GlobalFree(*((HGLOBAL *)a3 + 1));
      *((_QWORD *)a3 + 1) = 0;
    }
  }
  v14 = (unsigned __int16 *)*((_QWORD *)a3 + 2);
  if ( v14 )
  {
    v15 = *v14 - 58;
    if ( *v14 == 58 )
      v15 = v14[1];
    if ( !v15 )
      goto LABEL_30;
    v16 = *v14 - 58;
    if ( *v14 == 58 )
    {
      v16 = v14[1] - 58;
      if ( v14[1] == 58 )
        v16 = v14[2];
    }
    if ( !v16 )
    {
LABEL_30:
      GlobalFree(*((HGLOBAL *)a3 + 2));
      *((_QWORD *)a3 + 2) = 0;
    }
  }
  v8 = 0;
LABEL_32:
  if ( pProxyConfig.lpszAutoConfigUrl )
  {
    GlobalFree(pProxyConfig.lpszAutoConfigUrl);
    pProxyConfig.lpszAutoConfigUrl = 0;
  }
  if ( pProxyConfig.lpszProxy )
  {
    GlobalFree(pProxyConfig.lpszProxy);
    pProxyConfig.lpszProxy = 0;
  }
  if ( pProxyConfig.lpszProxyBypass )
    GlobalFree(pProxyConfig.lpszProxyBypass);
  return v8;
}

```

## disassembly

```asm
0x1800903b0  push    rbp
0x1800903b2  push    rbx
0x1800903b3  push    rsi
0x1800903b4  push    rdi
0x1800903b5  mov     rbp, rsp
0x1800903b8  sub     rsp, 68h
0x1800903bc  xorps   xmm0, xmm0
0x1800903bf  xorps   xmm1, xmm1
0x1800903c2  mov     rsi, rcx
0x1800903c5  mov     rbx, r8
0x1800903c8  lea     rcx, [rbp+pProxyConfig]; pProxyConfig
0x1800903cc  mov     rdi, rdx
0x1800903cf  movups  xmmword ptr [rbp+pProxyConfig.fAutoDetect], xmm0
0x1800903d3  movups  xmmword ptr [rbp+pProxyConfig.lpszProxy], xmm0
0x1800903d7  movups  xmmword ptr [rbp+pAutoProxyOptions.dwFlags], xmm1
0x1800903db  movups  xmmword ptr [rbp+pAutoProxyOptions.lpvReserved], xmm1
0x1800903df  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800903e5  test    eax, eax
0x1800903e7  jz      short loc_180090418
0x1800903e9  cmp     [rbp+pProxyConfig.fAutoDetect], 0
0x1800903ed  jz      short loc_180090400
0x1800903ef  mov     eax, 1
0x1800903f4  mov     [rbp+pAutoProxyOptions.dwAutoDetectFlags], 3
0x1800903fb  mov     [rbp+pAutoProxyOptions.dwFlags], eax
0x1800903fe  jmp     short loc_180090403
0x180090400  mov     eax, [rbp+pAutoProxyOptions.dwFlags]
0x180090403  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]
0x180090407  test    rcx, rcx
0x18009040a  jz      short loc_180090426
0x18009040c  or      eax, 2
0x18009040f  mov     [rbp+pAutoProxyOptions.lpszAutoConfigUrl], rcx
0x180090413  mov     [rbp+pAutoProxyOptions.dwFlags], eax
0x180090416  jmp     short loc_180090426
0x180090418  mov     [rbp+pAutoProxyOptions.dwFlags], 1
0x18009041f  mov     [rbp+pAutoProxyOptions.dwAutoDetectFlags], 3
0x180090426  mov     rdx, [rsi+38h]; lpcwszUrl
0x18009042a  lea     r8, [rbp+pAutoProxyOptions]; pAutoProxyOptions
0x18009042e  mov     r9, rbx; pProxyInfo
0x180090431  mov     [rbp+pAutoProxyOptions.fAutoLogonIfChallenged], 1
0x180090438  mov     rcx, rdi; hSession
0x18009043b  call    cs:__imp_WinHttpGetProxyForUrl
0x180090441  test    eax, eax
0x180090443  jnz     short loc_180090484
0x180090445  call    cs:__imp_GetLastError
0x18009044b  cmp     eax, 2EF1h
0x180090450  jnz     short loc_18009045C
0x180090452  mov     ebx, 80072EF1h
0x180090457  jmp     loc_180090531
0x18009045c  mov     rcx, [rbp+pProxyConfig.lpszProxy]
0x180090460  test    rcx, rcx
0x180090463  jz      short loc_180090484
0x180090465  mov     rax, [rbp+pProxyConfig.lpszProxyBypass]
0x180090469  xorps   xmm0, xmm0
0x18009046c  movdqu  xmmword ptr [rbp+pProxyConfig.lpszProxy], xmm0
0x180090471  mov     dword ptr [rbx], 3
0x180090477  movq    [rbp+pProxyConfig.lpszProxy], xmm0
0x18009047c  mov     [rbx+8], rcx
0x180090480  mov     [rbx+10h], rax
0x180090484  mov     r8, [rbx+8]
0x180090488  mov     edi, 3Ah ; ':'
0x18009048d  test    r8, r8
0x180090490  jz      short loc_1800904DC
0x180090492  movzx   edx, word ptr [r8]
0x180090496  sub     edx, edi
0x180090498  jnz     short loc_1800904A6
0x18009049a  movzx   edx, word ptr [r8+2]
0x18009049f  xor     eax, eax
0x1800904a1  movzx   ecx, ax
0x1800904a4  sub     edx, ecx
0x1800904a6  test    edx, edx
0x1800904a8  jz      short loc_1800904CB
0x1800904aa  movzx   ecx, word ptr [r8]
0x1800904ae  sub     ecx, edi
0x1800904b0  jnz     short loc_1800904C7
0x1800904b2  movzx   ecx, word ptr [r8+2]
0x1800904b7  sub     ecx, edi
0x1800904b9  jnz     short loc_1800904C7
0x1800904bb  movzx   ecx, word ptr [r8+4]
0x1800904c0  xor     eax, eax
0x1800904c2  movzx   edx, ax
0x1800904c5  sub     ecx, edx
0x1800904c7  test    ecx, ecx
0x1800904c9  jnz     short loc_1800904DC
0x1800904cb  mov     rcx, r8; hMem
0x1800904ce  call    cs:__imp_GlobalFree
0x1800904d4  mov     qword ptr [rbx+8], 0
0x1800904dc  mov     r8, [rbx+10h]
0x1800904e0  test    r8, r8
0x1800904e3  jz      short loc_18009052F
0x1800904e5  movzx   edx, word ptr [r8]
0x1800904e9  sub     edx, edi
0x1800904eb  jnz     short loc_1800904F9
0x1800904ed  movzx   edx, word ptr [r8+2]
0x1800904f2  xor     eax, eax
0x1800904f4  movzx   ecx, ax
0x1800904f7  sub     edx, ecx
0x1800904f9  test    edx, edx
0x1800904fb  jz      short loc_18009051E
0x1800904fd  movzx   ecx, word ptr [r8]
0x180090501  sub     ecx, edi
0x180090503  jnz     short loc_18009051A
0x180090505  movzx   ecx, word ptr [r8+2]
0x18009050a  sub     ecx, edi
0x18009050c  jnz     short loc_18009051A
0x18009050e  movzx   ecx, word ptr [r8+4]
0x180090513  xor     eax, eax
0x180090515  movzx   edx, ax
0x180090518  sub     ecx, edx
0x18009051a  test    ecx, ecx
0x18009051c  jnz     short loc_18009052F
0x18009051e  mov     rcx, r8; hMem
0x180090521  call    cs:__imp_GlobalFree
0x180090527  mov     qword ptr [rbx+10h], 0
0x18009052f  xor     ebx, ebx
0x180090531  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]; hMem
0x180090535  test    rcx, rcx
0x180090538  jz      short loc_180090548
0x18009053a  call    cs:__imp_GlobalFree
0x180090540  mov     [rbp+pProxyConfig.lpszAutoConfigUrl], 0
0x180090548  mov     rcx, [rbp+pProxyConfig.lpszProxy]; hMem
0x18009054c  test    rcx, rcx
0x18009054f  jz      short loc_18009055F
0x180090551  call    cs:__imp_GlobalFree
0x180090557  mov     [rbp+pProxyConfig.lpszProxy], 0
0x18009055f  mov     rcx, [rbp+pProxyConfig.lpszProxyBypass]; hMem
0x180090563  test    rcx, rcx
0x180090566  jz      short loc_18009056E
0x180090568  call    cs:__imp_GlobalFree
0x18009056e  mov     eax, ebx
0x180090570  add     rsp, 68h
0x180090574  pop     rdi
0x180090575  pop     rsi
0x180090576  pop     rbx
0x180090577  pop     rbp
0x180090578  retn
```
