# IsURLValid(ushort const *)

- ea: `0x180078650`
- end: `0x180078890`
- name: `?IsURLValid@@YAHPEBG@Z`
- size: `576`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180021dc0`
- `0x1800236f0`
- `0x180040774`
- `0x1800759bc`

## callees

- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ec94`
- `0x180020bf0`
- `0x180078650`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800786d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800786d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078767`
- `KERNEL32!CompareStringOrdinal` at `0x1800787a3`
- `KERNEL32!CompareStringOrdinal` at `0x1800787a3`
- `WININET!InternetCanonicalizeUrlW` at `0x1800786ab`
- `WININET!InternetCanonicalizeUrlW` at `0x1800786ab`
- `WININET!InternetCrackUrlW` at `0x18007873e`
- `WININET!InternetCrackUrlW` at `0x18007873e`

## pseudocode

```c
__int64 __fastcall IsURLValid(const unsigned __int16 *a1)
{
  unsigned int v2; // edi
  signed int LastError; // eax
  unsigned int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  signed int v7; // eax
  unsigned int v8; // eax
  int v9; // edx
  DWORD dwBufferLength[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szBuffer[2088]; // [rsp+B0h] [rbp-50h] BYREF

  dwBufferLength[0] = 2084;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  v2 = 0;
  if ( !InternetCanonicalizeUrlW(a1, szBuffer, dwBufferLength, 0) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 21;
LABEL_8:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_8f87464425bd38a0257d033d5861bd18_Traceguids,
      CurrentThreadActivityIdPrefix,
      v4);
LABEL_9:
    GetLastError();
    return v2;
  }
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.dwUrlPathLength = 1;
  UrlComponents.dwSchemeLength = 1;
  if ( !InternetCrackUrlW(szBuffer, 0, 0, &UrlComponents) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 22;
    goto LABEL_8;
  }
  if ( CompareStringOrdinal(UrlComponents.lpszScheme, UrlComponents.dwSchemeLength, L"radc-aad", -1, 1) == 2
    || UrlComponents.nScheme == INTERNET_SCHEME_HTTPS )
  {
    if ( UrlComponents.lpszHostName )
    {
      if ( UrlComponents.lpszUrlPath )
        return 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 25;
        goto LABEL_23;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 24;
      goto LABEL_23;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 23;
LABEL_23:
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_8f87464425bd38a0257d033d5861bd18_Traceguids,
      v8,
      (__int64)a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180078650  push    rbp
0x180078652  push    rbx
0x180078653  push    rsi
0x180078654  push    rdi
0x180078655  lea     rbp, [rsp-1018h]
0x18007865d  mov     eax, 1118h
0x180078662  call    _alloca_probe
0x180078667  sub     rsp, rax
0x18007866a  mov     rax, cs:__security_cookie
0x180078671  xor     rax, rsp
0x180078674  mov     [rbp+1030h+var_30], rax
0x18007867b  mov     rbx, rcx
0x18007867e  mov     [rsp+1130h+dwBufferLength], 824h
0x180078686  mov     esi, 68h ; 'h'
0x18007868b  lea     rcx, [rsp+1130h+UrlComponents]; void *
0x180078690  mov     r8d, esi; Size
0x180078693  xor     edx, edx; Val
0x180078695  call    memset_0
0x18007869a  xor     r9d, r9d; dwFlags
0x18007869d  lea     r8, [rsp+1130h+dwBufferLength]; lpdwBufferLength
0x1800786a2  lea     rdx, [rbp+1030h+szBuffer]; lpszBuffer
0x1800786a6  mov     rcx, rbx; lpszUrl
0x1800786a9  xor     edi, edi
0x1800786ab  call    cs:__imp_InternetCanonicalizeUrlW
0x1800786b1  test    eax, eax
0x1800786b3  jnz     short loc_18007871C
0x1800786b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800786bc  lea     rax, WPP_GLOBAL_Control
0x1800786c3  cmp     rcx, rax
0x1800786c6  jz      short loc_180078711
0x1800786c8  test    byte ptr [rcx+1Ch], 8
0x1800786cc  jz      short loc_180078711
0x1800786ce  cmp     byte ptr [rcx+19h], 2
0x1800786d2  jb      short loc_180078711
0x1800786d4  call    cs:__imp_GetLastError
0x1800786da  mov     ebx, eax
0x1800786dc  test    eax, eax
0x1800786de  jle     short loc_1800786E9
0x1800786e0  movzx   ebx, ax
0x1800786e3  or      ebx, 80070000h
0x1800786e9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800786ee  mov     edx, 15h
0x1800786f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800786fa  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x180078701  mov     r9d, eax
0x180078704  mov     [rsp+1130h+bIgnoreCase], ebx
0x180078708  mov     rcx, [rcx+10h]
0x18007870c  call    WPP_SF_Dd
0x180078711  call    cs:__imp_GetLastError
0x180078717  jmp     loc_180078873
0x18007871c  mov     [rsp+1130h+UrlComponents.dwStructSize], esi
0x180078720  lea     r9, [rsp+1130h+UrlComponents]; lpUrlComponents
0x180078725  mov     esi, 1
0x18007872a  lea     rcx, [rbp+1030h+szBuffer]; lpszUrl
0x18007872e  xor     r8d, r8d; dwFlags
0x180078731  mov     [rsp+1130h+UrlComponents.dwHostNameLength], esi
0x180078735  xor     edx, edx; dwUrlLength
0x180078737  mov     [rbp+1030h+UrlComponents.dwUrlPathLength], esi
0x18007873a  mov     [rsp+1130h+UrlComponents.dwSchemeLength], esi
0x18007873e  call    cs:__imp_InternetCrackUrlW
0x180078744  test    eax, eax
0x180078746  jnz     short loc_18007878B
0x180078748  mov     rcx, cs:WPP_GLOBAL_Control
0x18007874f  lea     rax, WPP_GLOBAL_Control
0x180078756  cmp     rcx, rax
0x180078759  jz      short loc_180078711
0x18007875b  test    byte ptr [rcx+1Ch], 8
0x18007875f  jz      short loc_180078711
0x180078761  cmp     byte ptr [rcx+19h], 2
0x180078765  jb      short loc_180078711
0x180078767  call    cs:__imp_GetLastError
0x18007876d  mov     ebx, eax
0x18007876f  test    eax, eax
0x180078771  jle     short loc_18007877C
0x180078773  movzx   ebx, ax
0x180078776  or      ebx, 80070000h
0x18007877c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078781  mov     edx, 16h
0x180078786  jmp     loc_1800786F3
0x18007878b  mov     edx, [rsp+1130h+UrlComponents.dwSchemeLength]; cchCount1
0x18007878f  lea     r8, aRadcAad; "radc-aad"
0x180078796  mov     rcx, [rsp+1130h+UrlComponents.lpszScheme]; lpString1
0x18007879b  or      r9d, 0FFFFFFFFh; cchCount2
0x18007879f  mov     [rsp+1130h+bIgnoreCase], esi; bIgnoreCase
0x1800787a3  call    cs:__imp_CompareStringOrdinal
0x1800787a9  cmp     eax, 2
0x1800787ac  jz      short loc_18007880B
0x1800787ae  cmp     [rsp+1130h+UrlComponents.nScheme], 4
0x1800787b3  jz      short loc_18007880B
0x1800787b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800787bc  lea     rax, WPP_GLOBAL_Control
0x1800787c3  cmp     rcx, rax
0x1800787c6  jz      loc_180078873
0x1800787cc  test    byte ptr [rcx+1Ch], 8
0x1800787d0  jz      loc_180078873
0x1800787d6  cmp     byte ptr [rcx+19h], 2
0x1800787da  jb      loc_180078873
0x1800787e0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800787e5  mov     edx, 17h
0x1800787ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800787f1  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x1800787f8  mov     r9d, eax
0x1800787fb  mov     qword ptr [rsp+1130h+bIgnoreCase], rbx
0x180078800  mov     rcx, [rcx+10h]
0x180078804  call    WPP_SF_DS
0x180078809  jmp     short loc_180078873
0x18007880b  cmp     [rsp+1130h+UrlComponents.lpszHostName], rdi
0x180078810  jnz     short loc_18007883D
0x180078812  mov     rcx, cs:WPP_GLOBAL_Control
0x180078819  lea     rax, WPP_GLOBAL_Control
0x180078820  cmp     rcx, rax
0x180078823  jz      short loc_180078873
0x180078825  test    byte ptr [rcx+1Ch], 8
0x180078829  jz      short loc_180078873
0x18007882b  cmp     byte ptr [rcx+19h], 2
0x18007882f  jb      short loc_180078873
0x180078831  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078836  mov     edx, 18h
0x18007883b  jmp     short loc_1800787EA
0x18007883d  cmp     [rbp+1030h+UrlComponents.lpszUrlPath], rdi
0x180078841  jnz     short loc_180078871
0x180078843  mov     rcx, cs:WPP_GLOBAL_Control
0x18007884a  lea     rax, WPP_GLOBAL_Control
0x180078851  cmp     rcx, rax
0x180078854  jz      short loc_180078873
0x180078856  test    byte ptr [rcx+1Ch], 8
0x18007885a  jz      short loc_180078873
0x18007885c  cmp     byte ptr [rcx+19h], 2
0x180078860  jb      short loc_180078873
0x180078862  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078867  mov     edx, 19h
0x18007886c  jmp     loc_1800787EA
0x180078871  mov     edi, esi
0x180078873  mov     eax, edi
0x180078875  mov     rcx, [rbp+1030h+var_30]
0x18007887c  xor     rcx, rsp; StackCookie
0x18007887f  call    __security_check_cookie
0x180078884  add     rsp, 1118h
0x18007888b  pop     rdi
0x18007888c  pop     rsi
0x18007888d  pop     rbx
0x18007888e  pop     rbp
0x18007888f  retn
```
