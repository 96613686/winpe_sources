# GetAutoProxyInfo(ushort const *,_WINHTTP_PROXY_INFO *,_WINHTTP_AUTOPROXY_OPTIONS *,int *)

- ea: `0x18000de18`
- end: `0x18000dfe1`
- name: `?GetAutoProxyInfo@@YAJPEBGPEAU_WINHTTP_PROXY_INFO@@PEAU_WINHTTP_AUTOPROXY_OPTIONS@@PEAH@Z`
- size: `457`
- prototype: `__int64 __fastcall(LPCWSTR lpcwszUrl, WINHTTP_PROXY_INFO *pProxyInfo, WINHTTP_AUTOPROXY_OPTIONS *pAutoProxyOptions, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010250`

## callees

- `0x18000de18`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000de89`
- `KERNEL32!GetLastError` at `0x18000decb`
- `KERNEL32!GetLastError` at `0x18000df1c`
- `KERNEL32!GetLastError` at `0x18000df5a`
- `KERNEL32!GetLastError` at `0x18000dfa8`
- `KERNEL32!GetLastError` at `0x18000de89`
- `KERNEL32!GetLastError` at `0x18000decb`
- `KERNEL32!GetLastError` at `0x18000df1c`
- `KERNEL32!GetLastError` at `0x18000df5a`
- `KERNEL32!GetLastError` at `0x18000dfa8`
- `WINHTTP!WinHttpCloseHandle` at `0x18000df85`
- `WINHTTP!WinHttpCloseHandle` at `0x18000df85`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18000df98`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18000df98`
- `WINHTTP!WinHttpOpen` at `0x18000de6f`
- `WINHTTP!WinHttpOpen` at `0x18000de6f`
- `WINHTTP!WinHttpSetOption` at `0x18000debb`
- `WINHTTP!WinHttpSetOption` at `0x18000df0c`
- `WINHTTP!WinHttpSetOption` at `0x18000debb`
- `WINHTTP!WinHttpSetOption` at `0x18000df0c`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000df4a`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18000df4a`

## pseudocode

```c
__int64 __fastcall GetAutoProxyInfo(
        LPCWSTR lpcwszUrl,
        WINHTTP_PROXY_INFO *pProxyInfo,
        WINHTTP_AUTOPROXY_OPTIONS *pAutoProxyOptions,
        int *a4)
{
  signed int v8; // ebx
  void *v9; // rdi
  signed int LastError; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v15; // eax
  int Buffer[4]; // [rsp+30h] [rbp-38h] BYREF
  int v17; // [rsp+70h] [rbp+8h] BYREF

  Buffer[0] = 10000;
  v17 = 0;
  if ( lpcwszUrl && pProxyInfo )
  {
    v8 = 0;
    v9 = WinHttpOpen(L"Microsoft Windows Network Diagnostics", 0, 0, 0, 0);
    if ( !v9 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 < 0 )
        return (unsigned int)v8;
    }
    if ( WinHttpSetOption(v9, 3u, Buffer, 4u) )
      goto LABEL_14;
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    if ( v8 >= 0 )
    {
LABEL_14:
      BYTE2(v17) = 0;
      LOWORD(v17) = 1000;
      if ( WinHttpSetOption(v9, 0x71u, &v17, 4u) )
        goto LABEL_15;
      v12 = GetLastError();
      v8 = v12;
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
      if ( v8 >= 0 )
      {
LABEL_15:
        if ( (pAutoProxyOptions->dwFlags & 3) != 0 )
        {
          if ( !WinHttpGetProxyForUrl(v9, lpcwszUrl, pAutoProxyOptions, pProxyInfo) )
          {
            v13 = GetLastError();
            v8 = v13;
            if ( v13 > 0 )
              v8 = (unsigned __int16)v13 | 0x80070000;
            if ( v8 < 0 )
              goto LABEL_21;
          }
        }
        else if ( !WinHttpGetDefaultProxyConfiguration(pProxyInfo) )
        {
          v15 = GetLastError();
          v8 = v15;
          if ( v15 > 0 )
            v8 = (unsigned __int16)v15 | 0x80070000;
          goto LABEL_21;
        }
        *a4 = 1;
      }
    }
LABEL_21:
    if ( v9 )
      WinHttpCloseHandle(v9);
    return (unsigned int)v8;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000de18  mov     rax, rsp
0x18000de1b  mov     [rax+10h], rbx
0x18000de1f  mov     [rax+18h], rbp
0x18000de23  push    rsi
0x18000de24  push    rdi
0x18000de25  push    r13
0x18000de27  push    r14
0x18000de29  push    r15
0x18000de2b  sub     rsp, 40h
0x18000de2f  mov     dword ptr [rax-38h], 2710h
0x18000de36  mov     r14, r9
0x18000de39  mov     dword ptr [rax+8], 0
0x18000de40  mov     rbp, r8
0x18000de43  mov     rsi, rdx
0x18000de46  mov     r15, rcx
0x18000de49  test    rcx, rcx
0x18000de4c  jz      loc_18000DFC2
0x18000de52  test    rdx, rdx
0x18000de55  jz      loc_18000DFC2
0x18000de5b  xor     ebx, ebx
0x18000de5d  lea     rcx, pszAgentW; "Microsoft Windows Network Diagnostics"
0x18000de64  xor     r9d, r9d; pszProxyBypassW
0x18000de67  mov     [rax-48h], ebx
0x18000de6a  xor     r8d, r8d; pszProxyW
0x18000de6d  xor     edx, edx; dwAccessType
0x18000de6f  call    cs:__imp_WinHttpOpen
0x18000de76  nop     dword ptr [rax+rax+00h]
0x18000de7b  mov     rdi, rax
0x18000de7e  mov     r13d, 80070000h
0x18000de84  test    rax, rax
0x18000de87  jnz     short loc_18000DEA9
0x18000de89  call    cs:__imp_GetLastError
0x18000de90  nop     dword ptr [rax+rax+00h]
0x18000de95  mov     ebx, eax
0x18000de97  test    eax, eax
0x18000de99  jle     short loc_18000DEA1
0x18000de9b  movzx   ebx, ax
0x18000de9e  or      ebx, r13d
0x18000dea1  test    ebx, ebx
0x18000dea3  js      loc_18000DF91
0x18000dea9  mov     r9d, 4; dwBufferLength
0x18000deaf  lea     r8, [rsp+68h+Buffer]; lpBuffer
0x18000deb4  mov     rcx, rdi; hInternet
0x18000deb7  lea     edx, [r9-1]; dwOption
0x18000debb  call    cs:__imp_WinHttpSetOption
0x18000dec2  nop     dword ptr [rax+rax+00h]
0x18000dec7  test    eax, eax
0x18000dec9  jnz     short loc_18000DEEB
0x18000decb  call    cs:__imp_GetLastError
0x18000ded2  nop     dword ptr [rax+rax+00h]
0x18000ded7  mov     ebx, eax
0x18000ded9  test    eax, eax
0x18000dedb  jle     short loc_18000DEE3
0x18000dedd  movzx   ebx, ax
0x18000dee0  or      ebx, r13d
0x18000dee3  test    ebx, ebx
0x18000dee5  js      loc_18000DF7D
0x18000deeb  mov     r9d, 4; dwBufferLength
0x18000def1  mov     [rsp+68h+arg_2], 0
0x18000def6  mov     eax, 3E8h
0x18000defb  lea     r8, [rsp+68h+arg_0]; lpBuffer
0x18000df00  mov     rcx, rdi; hInternet
0x18000df03  mov     [rsp+68h+arg_0], ax
0x18000df08  lea     edx, [r9+6Dh]; dwOption
0x18000df0c  call    cs:__imp_WinHttpSetOption
0x18000df13  nop     dword ptr [rax+rax+00h]
0x18000df18  test    eax, eax
0x18000df1a  jnz     short loc_18000DF38
0x18000df1c  call    cs:__imp_GetLastError
0x18000df23  nop     dword ptr [rax+rax+00h]
0x18000df28  mov     ebx, eax
0x18000df2a  test    eax, eax
0x18000df2c  jle     short loc_18000DF34
0x18000df2e  movzx   ebx, ax
0x18000df31  or      ebx, r13d
0x18000df34  test    ebx, ebx
0x18000df36  js      short loc_18000DF7D
0x18000df38  test    byte ptr [rbp+0], 3
0x18000df3c  jz      short loc_18000DF95
0x18000df3e  mov     r9, rsi; pProxyInfo
0x18000df41  mov     r8, rbp; pAutoProxyOptions
0x18000df44  mov     rdx, r15; lpcwszUrl
0x18000df47  mov     rcx, rdi; hSession
0x18000df4a  call    cs:__imp_WinHttpGetProxyForUrl
0x18000df51  nop     dword ptr [rax+rax+00h]
0x18000df56  test    eax, eax
0x18000df58  jnz     short loc_18000DF76
0x18000df5a  call    cs:__imp_GetLastError
0x18000df61  nop     dword ptr [rax+rax+00h]
0x18000df66  mov     ebx, eax
0x18000df68  test    eax, eax
0x18000df6a  jle     short loc_18000DF72
0x18000df6c  movzx   ebx, ax
0x18000df6f  or      ebx, r13d
0x18000df72  test    ebx, ebx
0x18000df74  js      short loc_18000DF7D
0x18000df76  mov     dword ptr [r14], 1
0x18000df7d  test    rdi, rdi
0x18000df80  jz      short loc_18000DF91
0x18000df82  mov     rcx, rdi; hInternet
0x18000df85  call    cs:__imp_WinHttpCloseHandle
0x18000df8c  nop     dword ptr [rax+rax+00h]
0x18000df91  mov     eax, ebx
0x18000df93  jmp     short loc_18000DFC7
0x18000df95  mov     rcx, rsi; pProxyInfo
0x18000df98  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18000df9f  nop     dword ptr [rax+rax+00h]
0x18000dfa4  test    eax, eax
0x18000dfa6  jnz     short loc_18000DF76
0x18000dfa8  call    cs:__imp_GetLastError
0x18000dfaf  nop     dword ptr [rax+rax+00h]
0x18000dfb4  mov     ebx, eax
0x18000dfb6  test    eax, eax
0x18000dfb8  jle     short loc_18000DF7D
0x18000dfba  movzx   ebx, ax
0x18000dfbd  or      ebx, r13d
0x18000dfc0  jmp     short loc_18000DF7D
0x18000dfc2  mov     eax, 80070057h
0x18000dfc7  lea     r11, [rsp+68h+var_28]
0x18000dfcc  mov     rbx, [r11+38h]
0x18000dfd0  mov     rbp, [r11+40h]
0x18000dfd4  mov     rsp, r11
0x18000dfd7  pop     r15
0x18000dfd9  pop     r14
0x18000dfdb  pop     r13
0x18000dfdd  pop     rdi
0x18000dfde  pop     rsi
0x18000dfdf  retn
```
