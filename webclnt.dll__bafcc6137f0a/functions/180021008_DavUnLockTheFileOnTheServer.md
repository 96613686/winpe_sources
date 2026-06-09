# DavUnLockTheFileOnTheServer

- ea: `0x180021008`
- end: `0x1800214a7`
- name: `DavUnLockTheFileOnTheServer`
- size: `1183`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800196d0`
- `0x18001f190`

## callees

- `0x18000b43c`
- `0x18000b4f0`
- `0x18000b7dc`
- `0x18000b93c`
- `0x180012468`
- `0x1800134d8`
- `0x180013c08`
- `0x180021008`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002124f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002124f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021414`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021414`
- `KERNEL32!LocalFree` at `0x180021486`
- `KERNEL32!LocalFree` at `0x180021486`
- `KERNEL32!LocalAlloc` at `0x180021241`
- `KERNEL32!LocalAlloc` at `0x1800212b1`
- `KERNEL32!LocalAlloc` at `0x180021241`
- `KERNEL32!LocalAlloc` at `0x1800212b1`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18002117f`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800213ba`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18002117f`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800213ba`
- `WINHTTP!WinHttpSetOption` at `0x18002112e`
- `WINHTTP!WinHttpSetOption` at `0x18002112e`
- `WINHTTP!WinHttpCloseHandle` at `0x180021478`
- `WINHTTP!WinHttpCloseHandle` at `0x180021478`

## string_xrefs

- `0x180021280`: `Lock-Token: `
- `0x1800212f0`: `Lock-Token: `

## pseudocode

```c
__int64 __fastcall DavUnLockTheFileOnTheServer(__int64 a1)
{
  wchar_t *v2; // rbp
  __int64 v3; // r9
  const wchar_t *v4; // rdi
  int v5; // eax
  void *v6; // r14
  DWORD LastError; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // r9d
  __int64 v14; // rbx
  __int64 v15; // rax
  SIZE_T v16; // rbx
  wchar_t *v17; // rax
  SIZE_T v18; // r15
  wchar_t *v19; // rax
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // rax
  _WORD *v22; // rdx
  _WORD *v23; // rcx
  _WORD *v24; // rcx
  DWORD v25; // eax
  __int64 v26; // r9
  DWORD v28; // [rsp+20h] [rbp-78h]
  DWORD v29; // [rsp+28h] [rbp-70h]
  int v30; // [rsp+30h] [rbp-68h]
  int v31; // [rsp+30h] [rbp-68h]
  __int64 v32; // [rsp+40h] [rbp-58h]
  __int64 v33; // [rsp+58h] [rbp-40h]
  int Buffer; // [rsp+A0h] [rbp+8h] BYREF
  HINTERNET hInternet; // [rsp+A8h] [rbp+10h] BYREF

  v2 = 0;
  hInternet = 0;
  Buffer = 0;
  if ( *(_DWORD *)(a1 + 48) )
  {
    v4 = *(const wchar_t **)(a1 + 680);
    v3 = *(_QWORD *)(a1 + 672) + 2LL;
  }
  else
  {
    v3 = *(_QWORD *)(a1 + 568);
    v4 = (const wchar_t *)(a1 + 3896);
  }
  v5 = DavHttpOpenRequestW(
         *(void **)(*(_QWORD *)(a1 + 496) + 32LL),
         *(void **)(*(_QWORD *)(a1 + 496) + 40LL),
         L"UNLOCK",
         v3,
         v28,
         v29,
         v30,
         0x100u,
         v32,
         (int *)L"DavUnLockTheFileOnTheServer",
         *(_DWORD *)(*(_QWORD *)(a1 + 504) + 32LL),
         v33,
         &hInternet);
  v6 = hInternet;
  if ( !v5 )
  {
    LastError = GetLastError();
LABEL_67:
    if ( v6 )
      WinHttpCloseHandle(v6);
    if ( v2 )
      LocalFree(v2);
    return LastError;
  }
  if ( hInternet )
  {
    Buffer = 1;
    if ( g_DisableCookies && !WinHttpSetOption(hInternet, 0x3Fu, &Buffer, 4u) )
    {
      v9 = GetLastError();
      LastError = v9;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_67;
      v11 = 78;
      goto LABEL_65;
    }
    if ( !WinHttpAddRequestHeaders(v6, L"translate: f\n", 0xFFFFFFFF, 0xA0000000) )
    {
      v9 = GetLastError();
      LastError = v9;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_67;
      v11 = 79;
      goto LABEL_65;
    }
    v12 = *(_QWORD *)(a1 + 496);
    if ( !v12 || (v13 = 0, *(_DWORD *)(v12 + 104) != 2) )
      v13 = 1;
    v9 = DavInternetSetOption(a1, 0, v6, v13, 0);
    LastError = v9;
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_67;
      v11 = 80;
      goto LABEL_65;
    }
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( v4[v15] );
    if ( *(_DWORD *)(a1 + 48) )
    {
      v18 = (unsigned int)(2 * v15 + 14);
      v19 = (wchar_t *)LocalAlloc(0x40u, v18);
      v2 = v19;
      if ( !v19 )
      {
        v9 = GetLastError();
        LastError = v9;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_67;
        v11 = 82;
        goto LABEL_65;
      }
      StringCbCopyW(v19, v18, L"Lock-Token: ");
      do
        ++v14;
      while ( v4[v14] );
      v20 = (v18 - 24) >> 1;
      if ( v20 - 1 <= 0x7FFFFFFE )
      {
        v21 = (v14 - 6) & 0x7FFFFFFFFFFFFFFFLL;
        v22 = v2 + 12;
        if ( v21 <= 0x7FFFFFFE )
        {
          v23 = v4 + 5;
          do
          {
            if ( !v21 )
              break;
            if ( !*v23 )
              break;
            *v22++ = *v23++;
            --v21;
            --v20;
          }
          while ( v20 );
          v24 = v22 - 1;
          if ( v20 )
            v24 = v22;
          *v24 = 0;
        }
        else
        {
          *v22 = 0;
        }
      }
    }
    else
    {
      v16 = (unsigned int)(2 * v15 + 26);
      v17 = (wchar_t *)LocalAlloc(0x40u, v16);
      v2 = v17;
      if ( !v17 )
      {
        v9 = GetLastError();
        LastError = v9;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_67;
        v11 = 81;
        goto LABEL_65;
      }
      StringCbCopyW(v17, v16, L"Lock-Token: ");
      StringCbCatW(v2, v16, v4);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v2);
    if ( WinHttpAddRequestHeaders(v6, v2, 0xFFFFFFFF, 0xA0000000) )
    {
      v25 = DavSendRequest(v6, 0, 0, 0, 0, 0, v31, a1);
      LastError = v25;
      if ( v25 )
      {
        SetLastError(v25);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_67;
        v11 = 85;
        v26 = LastError;
        goto LABEL_66;
      }
      v9 = DavQueryAndParseResponseEx(v6, 0);
      LastError = v9;
      if ( !v9 )
        goto LABEL_67;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_67;
      v11 = 86;
    }
    else
    {
      v9 = GetLastError();
      LastError = v9;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_67;
      v11 = 84;
    }
LABEL_65:
    v26 = v9;
LABEL_66:
    WPP_SF_d(v10[2], v11, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v26);
    goto LABEL_67;
  }
  v8 = GetLastError();
  LastError = v8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v8);
  return LastError;
}

```

## disassembly

```asm
0x180021008  mov     rax, rsp
0x18002100b  mov     [rax+18h], rbx
0x18002100f  mov     [rax+20h], rbp
0x180021013  push    rsi
0x180021014  push    rdi
0x180021015  push    r12
0x180021017  push    r14
0x180021019  push    r15
0x18002101b  sub     rsp, 70h
0x18002101f  xor     r12d, r12d
0x180021022  mov     rsi, rcx
0x180021025  mov     ebp, r12d
0x180021028  mov     [rax+10h], r12
0x18002102c  mov     [rax+8], r12d
0x180021030  cmp     [rcx+30h], r12d
0x180021034  jnz     short loc_180021046
0x180021036  mov     r9, [rcx+238h]
0x18002103d  lea     rdi, [rcx+0F38h]
0x180021044  jmp     short loc_180021058
0x180021046  mov     r9, [rcx+2A0h]
0x18002104d  mov     rdi, [rcx+2A8h]
0x180021054  add     r9, 2
0x180021058  mov     rax, [rsi+1F8h]
0x18002105f  lea     rdx, [rsp+98h+hInternet]
0x180021067  mov     rcx, [rcx+1F0h]
0x18002106e  lea     r8, aUnlock; "UNLOCK"
0x180021075  mov     [rsp+98h+var_38], rdx
0x18002107a  mov     eax, [rax+20h]
0x18002107d  mov     rdx, [rcx+28h]
0x180021081  mov     rcx, [rcx+20h]
0x180021085  mov     [rsp+98h+var_48], eax
0x180021089  lea     rax, aDavunlockthefi; "DavUnLockTheFileOnTheServer"
0x180021090  mov     [rsp+98h+var_50], rax
0x180021095  mov     dword ptr [rsp+98h+var_60], 100h
0x18002109d  call    DavHttpOpenRequestW
0x1800210a2  mov     r14, [rsp+98h+hInternet]
0x1800210aa  test    eax, eax
0x1800210ac  jnz     short loc_1800210BB
0x1800210ae  call    cs:__imp_GetLastError
0x1800210b4  mov     ebx, eax
0x1800210b6  jmp     loc_180021470
0x1800210bb  test    r14, r14
0x1800210be  jnz     short loc_180021105
0x1800210c0  call    cs:__imp_GetLastError
0x1800210c6  mov     ebx, eax
0x1800210c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210cf  lea     rdi, WPP_GLOBAL_Control
0x1800210d6  cmp     rcx, rdi
0x1800210d9  jz      loc_18002148C
0x1800210df  test    byte ptr [rcx+1Ch], 1
0x1800210e3  jz      loc_18002148C
0x1800210e9  mov     rcx, [rcx+10h]
0x1800210ed  lea     edx, [r14+4Dh]
0x1800210f1  mov     r9d, eax
0x1800210f4  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x1800210fb  call    WPP_SF_d
0x180021100  jmp     loc_18002148C
0x180021105  cmp     cs:g_DisableCookies, r12d
0x18002110c  mov     [rsp+98h+Buffer], 1
0x180021117  jz      short loc_18002116B
0x180021119  mov     r9d, 4; dwBufferLength
0x18002111f  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x180021127  mov     rcx, r14; hInternet
0x18002112a  lea     edx, [r9+3Bh]; dwOption
0x18002112e  call    cs:__imp_WinHttpSetOption
0x180021134  test    eax, eax
0x180021136  jnz     short loc_18002116B
0x180021138  call    cs:__imp_GetLastError
0x18002113e  mov     ebx, eax
0x180021140  mov     rcx, cs:WPP_GLOBAL_Control
0x180021147  lea     rdi, WPP_GLOBAL_Control
0x18002114e  cmp     rcx, rdi
0x180021151  jz      loc_180021470
0x180021157  test    byte ptr [rcx+1Ch], 1
0x18002115b  jz      loc_180021470
0x180021161  mov     edx, 4Eh ; 'N'
0x180021166  jmp     loc_18002145D
0x18002116b  mov     r9d, 0A0000000h; dwModifiers
0x180021171  lea     rdx, szHeaders; "translate: f\n"
0x180021178  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x18002117c  mov     rcx, r14; hRequest
0x18002117f  call    cs:__imp_WinHttpAddRequestHeaders
0x180021185  test    eax, eax
0x180021187  jnz     short loc_1800211BC
0x180021189  call    cs:__imp_GetLastError
0x18002118f  mov     ebx, eax
0x180021191  mov     rcx, cs:WPP_GLOBAL_Control
0x180021198  lea     rdi, WPP_GLOBAL_Control
0x18002119f  cmp     rcx, rdi
0x1800211a2  jz      loc_180021470
0x1800211a8  test    byte ptr [rcx+1Ch], 1
0x1800211ac  jz      loc_180021470
0x1800211b2  mov     edx, 4Fh ; 'O'
0x1800211b7  jmp     loc_18002145D
0x1800211bc  mov     rax, [rsi+1F0h]
0x1800211c3  test    rax, rax
0x1800211c6  jz      short loc_1800211D1
0x1800211c8  cmp     dword ptr [rax+68h], 2
0x1800211cc  mov     r9d, r12d
0x1800211cf  jz      short loc_1800211D7
0x1800211d1  mov     r9d, 1
0x1800211d7  mov     r8, r14
0x1800211da  mov     [rsp+98h+var_78], r12d
0x1800211df  xor     edx, edx
0x1800211e1  mov     rcx, rsi
0x1800211e4  call    DavInternetSetOption
0x1800211e9  mov     ebx, eax
0x1800211eb  test    eax, eax
0x1800211ed  jz      short loc_18002121A
0x1800211ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211f6  lea     rdi, WPP_GLOBAL_Control
0x1800211fd  cmp     rcx, rdi
0x180021200  jz      loc_180021470
0x180021206  test    byte ptr [rcx+1Ch], 1
0x18002120a  jz      loc_180021470
0x180021210  mov     edx, 50h ; 'P'
0x180021215  jmp     loc_18002145D
0x18002121a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002121e  mov     rax, rbx
0x180021221  inc     rax
0x180021224  cmp     [rdi+rax*2], r12w
0x180021229  jnz     short loc_180021221
0x18002122b  mov     ecx, 40h ; '@'; uFlags
0x180021230  cmp     [rsi+30h], r12d
0x180021234  jnz     short loc_1800212A5
0x180021236  lea     eax, ds:1Ah[rax*2]
0x18002123d  mov     edx, eax; uBytes
0x18002123f  mov     ebx, eax
0x180021241  call    cs:__imp_LocalAlloc
0x180021247  mov     rbp, rax
0x18002124a  test    rax, rax
0x18002124d  jnz     short loc_180021280
0x18002124f  call    cs:__imp_GetLastError
0x180021255  mov     ebx, eax
0x180021257  mov     rcx, cs:WPP_GLOBAL_Control
0x18002125e  lea     rdi, WPP_GLOBAL_Control
0x180021265  cmp     rcx, rdi
0x180021268  jz      loc_180021470
0x18002126e  test    byte ptr [rcx+1Ch], 1
0x180021272  jz      loc_180021470
0x180021278  lea     edx, [rbp+51h]
0x18002127b  jmp     loc_18002145D
0x180021280  lea     r8, aLockToken; "Lock-Token: "
0x180021287  mov     rdx, rbx; cbDest
0x18002128a  mov     rcx, rbp; pszDest
0x18002128d  call    StringCbCopyW
0x180021292  mov     r8, rdi; pszSrc
0x180021295  mov     rdx, rbx; cbDest
0x180021298  mov     rcx, rbp; pszDest
0x18002129b  call    StringCbCatW
0x1800212a0  jmp     loc_180021379
0x1800212a5  lea     eax, ds:0Eh[rax*2]
0x1800212ac  mov     edx, eax; uBytes
0x1800212ae  mov     r15d, eax
0x1800212b1  call    cs:__imp_LocalAlloc
0x1800212b7  mov     rbp, rax
0x1800212ba  test    rax, rax
0x1800212bd  jnz     short loc_1800212F0
0x1800212bf  call    cs:__imp_GetLastError
0x1800212c5  mov     ebx, eax
0x1800212c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212ce  lea     rdi, WPP_GLOBAL_Control
0x1800212d5  cmp     rcx, rdi
0x1800212d8  jz      loc_180021470
0x1800212de  test    byte ptr [rcx+1Ch], 1
0x1800212e2  jz      loc_180021470
0x1800212e8  lea     edx, [rbp+52h]
0x1800212eb  jmp     loc_18002145D
0x1800212f0  lea     r8, aLockToken; "Lock-Token: "
0x1800212f7  mov     rdx, r15; cbDest
0x1800212fa  mov     rcx, rbp; pszDest
0x1800212fd  call    StringCbCopyW
0x180021302  inc     rbx
0x180021305  cmp     [rdi+rbx*2], r12w
0x18002130a  jnz     short loc_180021302
0x18002130c  lea     r8, [r15-18h]
0x180021310  mov     r9d, 7FFFFFFEh
0x180021316  shr     r8, 1
0x180021319  lea     rax, [r8-1]
0x18002131d  cmp     rax, r9
0x180021320  ja      short loc_180021379
0x180021322  lea     rax, [rbx-6]
0x180021326  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180021330  and     rax, rcx
0x180021333  lea     rdx, [rbp+18h]
0x180021337  cmp     rax, r9
0x18002133a  jbe     short loc_180021342
0x18002133c  mov     [rdx], r12w
0x180021340  jmp     short loc_180021379
0x180021342  lea     rcx, [rdi+0Ah]
0x180021346  test    rax, rax
0x180021349  jz      short loc_18002136A
0x18002134b  movzx   r9d, word ptr [rcx]
0x18002134f  test    r9w, r9w
0x180021353  jz      short loc_18002136A
0x180021355  mov     [rdx], r9w
0x180021359  add     rcx, 2
0x18002135d  add     rdx, 2
0x180021361  dec     rax
0x180021364  sub     r8, 1
0x180021368  jnz     short loc_180021346
0x18002136a  test    r8, r8
0x18002136d  lea     rcx, [rdx-2]
0x180021371  cmovnz  rcx, rdx
0x180021375  mov     [rcx], r12w
0x180021379  mov     rcx, cs:WPP_GLOBAL_Control
0x180021380  lea     rdi, WPP_GLOBAL_Control
0x180021387  cmp     rcx, rdi
0x18002138a  jz      short loc_1800213AA
0x18002138c  test    byte ptr [rcx+1Ch], 2
0x180021390  jz      short loc_1800213AA
0x180021392  mov     rcx, [rcx+10h]
0x180021396  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x18002139d  mov     edx, 53h ; 'S'
0x1800213a2  mov     r9, rbp
0x1800213a5  call    WPP_SF_S
0x1800213aa  mov     r9d, 0A0000000h; dwModifiers
0x1800213b0  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x1800213b4  mov     rdx, rbp; lpszHeaders
0x1800213b7  mov     rcx, r14; hRequest
0x1800213ba  call    cs:__imp_WinHttpAddRequestHeaders
0x1800213c0  test    eax, eax
0x1800213c2  jnz     short loc_1800213ED
0x1800213c4  call    cs:__imp_GetLastError
0x1800213ca  mov     ebx, eax
0x1800213cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213d3  cmp     rcx, rdi
0x1800213d6  jz      loc_180021470
0x1800213dc  test    byte ptr [rcx+1Ch], 1
0x1800213e0  jz      loc_180021470
0x1800213e6  mov     edx, 54h ; 'T'
0x1800213eb  jmp     short loc_18002145D
0x1800213ed  mov     [rsp+98h+var_60], rsi; __int64
0x1800213f2  xor     r9d, r9d
0x1800213f5  mov     [rsp+98h+var_70], r12d; DWORD
0x1800213fa  xor     r8d, r8d
0x1800213fd  xor     edx, edx
0x1800213ff  mov     [rsp+98h+var_78], r12d; DWORD
0x180021404  mov     rcx, r14; hRequest
0x180021407  call    DavSendRequest
0x18002140c  mov     ebx, eax
0x18002140e  test    eax, eax
0x180021410  jz      short loc_180021436
0x180021412  mov     ecx, eax; dwErrCode
0x180021414  call    cs:__imp_SetLastError
0x18002141a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021421  cmp     rcx, rdi
0x180021424  jz      short loc_180021470
0x180021426  test    byte ptr [rcx+1Ch], 1
0x18002142a  jz      short loc_180021470
0x18002142c  mov     edx, 55h ; 'U'
0x180021431  mov     r9d, ebx
0x180021434  jmp     short loc_180021460
0x180021436  xor     edx, edx
0x180021438  mov     rcx, r14
0x18002143b  call    DavQueryAndParseResponseEx
0x180021440  mov     ebx, eax
0x180021442  test    eax, eax
0x180021444  jz      short loc_180021470
0x180021446  mov     rcx, cs:WPP_GLOBAL_Control
0x18002144d  cmp     rcx, rdi
0x180021450  jz      short loc_180021470
0x180021452  test    byte ptr [rcx+1Ch], 1
0x180021456  jz      short loc_180021470
0x180021458  mov     edx, 56h ; 'V'
0x18002145d  mov     r9d, eax
0x180021460  mov     rcx, [rcx+10h]
0x180021464  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x18002146b  call    WPP_SF_d
0x180021470  test    r14, r14
0x180021473  jz      short loc_18002147E
0x180021475  mov     rcx, r14; hInternet
0x180021478  call    cs:__imp_WinHttpCloseHandle
0x18002147e  test    rbp, rbp
0x180021481  jz      short loc_18002148C
0x180021483  mov     rcx, rbp; hMem
0x180021486  call    cs:__imp_LocalFree
0x18002148c  lea     r11, [rsp+98h+var_28]
0x180021491  mov     eax, ebx
0x180021493  mov     rbx, [r11+40h]
0x180021497  mov     rbp, [r11+48h]
0x18002149b  mov     rsp, r11
0x18002149e  pop     r15
0x1800214a0  pop     r14
0x1800214a2  pop     r12
0x1800214a4  pop     rdi
0x1800214a5  pop     rsi
0x1800214a6  retn
```
