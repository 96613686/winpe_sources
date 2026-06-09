# CreateUrl(ushort const *,ushort const *,ProxyResolveScheme,ushort,tagProxyResolveUrl * *)

- ea: `0x180043230`
- end: `0x180043835`
- name: `?CreateUrl@@YAJPEBG0W4ProxyResolveScheme@@GPEAPEAUtagProxyResolveUrl@@@Z`
- size: `1541`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030ab0`
- `0x180040650`
- `0x18004313c`

## callees

- `0x1800403d4`
- `0x180043230`
- `0x1800441f0`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800d650c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004373b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004373b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800433e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004350b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800436dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800433e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004350b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800436dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800435dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800435ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043600`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004370f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800435dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800435ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043600`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004370f`

## pseudocode

```c
__int64 __fastcall CreateUrl(_WORD *a1, const WCHAR *a2, int a3, __int16 a4, _QWORD *a5)
{
  _WORD *v5; // rbx
  const WCHAR *v6; // r12
  __int64 v7; // rax
  WCHAR *v8; // rsi
  void *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // r15
  __int64 v12; // r13
  unsigned __int64 v13; // r8
  __int64 v14; // rdx
  void *v15; // rax
  _WORD *v16; // rdx
  int v17; // ebx
  __int64 v18; // rax
  void *v19; // rbx
  _WORD *v20; // rax
  _WORD *v21; // r15
  unsigned __int64 v22; // r8
  void *v23; // rax
  _WORD *v24; // rdx
  int v25; // edx
  int v26; // ecx
  int v27; // r8d
  _WORD *v28; // rax
  signed int v30; // edx
  int v31; // eax
  SIZE_T v32; // r15
  WCHAR *v33; // rax
  signed int LastError; // eax
  size_t Size; // [rsp+48h] [rbp-C0h]
  size_t Sizea; // [rsp+48h] [rbp-C0h]
  int v37; // [rsp+50h] [rbp-B8h]
  int v38; // [rsp+50h] [rbp-B8h]
  int v39; // [rsp+50h] [rbp-B8h]
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+70h] [rbp-98h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-30h]
  DWORD pdwUrlLength; // [rsp+E8h] [rbp-20h] BYREF

  v5 = a1;
  v6 = a2;
  pdwUrlLength = 0;
  v43 = 0;
  memset(&UrlComponents.lpszScheme, 0, 96);
  if ( !a5 )
    return (unsigned int)-2147024809;
  *a5 = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v7 = -1;
  v8 = 0;
  v9 = 0;
  do
    ++v7;
  while ( a1[v7] );
  v37 = v7;
  Size = (unsigned int)(2 * v7 + 2);
  v10 = CoTaskMemAlloc((unsigned int)Size);
  v11 = v10;
  v12 = 2147483646;
  if ( !v10 )
  {
    v17 = -2147024882;
    goto LABEL_18;
  }
  memset_0(v10, 0, Size);
  v13 = (unsigned int)(v37 + 1);
  if ( v37 == -1 )
  {
    v17 = -2147024809;
    v15 = v11;
    goto LABEL_16;
  }
  if ( v13 <= 0x7FFFFFFF )
  {
    v14 = 2147483646;
    v15 = v11;
    do
    {
      if ( !v14 )
        break;
      if ( !*v5 )
        break;
      *v11++ = *v5++;
      --v14;
      --v13;
    }
    while ( v13 );
    v16 = v11 - 1;
    v17 = -2147024774;
    if ( v13 )
    {
      v16 = v11;
      v17 = 0;
    }
    *v16 = 0;
LABEL_16:
    if ( v17 >= 0 )
    {
      v9 = v15;
      goto LABEL_18;
    }
    goto LABEL_59;
  }
  v17 = -2147024809;
  *v11 = 0;
  v15 = v11;
LABEL_59:
  if ( v15 )
    CoTaskMemFree(v15);
LABEL_18:
  if ( v17 >= 0 )
  {
    if ( !*v6 )
      v6 = L"/";
    v18 = -1;
    v19 = 0;
    do
      ++v18;
    while ( v6[v18] );
    v38 = v18;
    Sizea = (unsigned int)(2 * v18 + 2);
    v20 = CoTaskMemAlloc((unsigned int)Sizea);
    v21 = v20;
    if ( !v20 )
    {
      v25 = -2147024882;
      v39 = -2147024882;
      goto LABEL_65;
    }
    memset_0(v20, 0, Sizea);
    v22 = (unsigned int)(v38 + 1);
    if ( v38 == -1 )
    {
      v25 = -2147024809;
      v23 = v21;
    }
    else
    {
      if ( v22 > 0x7FFFFFFF )
      {
        v25 = -2147024809;
        *v21 = 0;
        v23 = v21;
        v39 = -2147024809;
        goto LABEL_63;
      }
      v23 = v21;
      do
      {
        if ( !v12 )
          break;
        if ( !*v6 )
          break;
        *v21++ = *v6++;
        --v12;
        --v22;
      }
      while ( v22 );
      v24 = v21 - 1;
      if ( v22 )
        v24 = v21;
      *v24 = 0;
      v25 = -2147024774;
      if ( v22 )
        v25 = 0;
    }
    v39 = v25;
    if ( v25 >= 0 )
    {
      v19 = v23;
      v39 = v25;
LABEL_65:
      if ( v25 >= 0 )
      {
        LODWORD(UrlComponents.lpszScheme) = 104;
        switch ( a3 )
        {
          case 4:
            v31 = 2;
            break;
          case 3:
            v31 = 1;
            break;
          case -2:
          case -1:
          case 0:
            v31 = a3;
            break;
          case 1:
            v31 = 3;
            break;
          case 8:
            v31 = 4;
            break;
          default:
            v31 = -1;
            break;
        }
        WORD2(UrlComponents.lpszUserName) = a4;
        HIDWORD(UrlComponents.lpszHostName) = v31;
        *(_QWORD *)&UrlComponents.dwHostNameLength = v9;
        *(_QWORD *)&UrlComponents.dwUrlPathLength = v19;
        if ( WinHttpCreateUrl((LPURL_COMPONENTS)&UrlComponents.lpszScheme, 0, 0, &pdwUrlLength) || GetLastError() != 122 )
        {
          v39 = -2147418113;
        }
        else
        {
          v32 = 2 * pdwUrlLength;
          v33 = (WCHAR *)CoTaskMemAlloc(v32);
          v8 = v33;
          if ( v33 )
          {
            memset_0(v33, 0, v32);
            if ( WinHttpCreateUrl((LPURL_COMPONENTS)&UrlComponents.lpszScheme, 0, v8, &pdwUrlLength) )
            {
              if ( (xmmword_180107A60 & 0x20) != 0 )
                WPP_SF_SSSdd(v26, 10, v27, (_DWORD)v8, (__int64)v9, (__int64)v19, a3, a4);
              v28 = CoTaskMemAlloc(0x20u);
              if ( v28 )
              {
                v28[15] = 0;
                *(_QWORD *)v28 = v8;
                *((_QWORD *)v28 + 1) = v9;
                *((_QWORD *)v28 + 2) = v19;
                v17 = 0;
                *((_DWORD *)v28 + 6) = a3;
                v28[14] = a4;
                *a5 = v28;
                return (unsigned int)v17;
              }
              v39 = -2147024882;
            }
            else
            {
              LastError = GetLastError();
              v30 = LastError;
              if ( LastError > 0 )
                v30 = (unsigned __int16)LastError | 0x80070000;
              if ( v30 >= 0 )
                v30 = -2147418113;
              v39 = v30;
            }
          }
          else
          {
            v39 = -2147024882;
          }
        }
      }
      if ( v19 )
        CoTaskMemFree(v19);
      v17 = v39;
      goto LABEL_53;
    }
LABEL_63:
    if ( v23 )
    {
      CoTaskMemFree(v23);
      v25 = v39;
    }
    goto LABEL_65;
  }
LABEL_53:
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v8 )
    CoTaskMemFree(v8);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180043230  mov     r11, rsp
0x180043233  push    rbp
0x180043234  push    rbx
0x180043235  lea     rbp, [r11-38h]
0x180043239  sub     rsp, 128h
0x180043240  mov     rax, cs:__security_cookie
0x180043247  xor     rax, rsp
0x18004324a  mov     [rbp+30h+var_48], rax
0x18004324e  mov     rax, [rbp+30h+arg_20]
0x180043252  xorps   xmm0, xmm0
0x180043255  mov     [r11-28h], r12
0x180043259  mov     rbx, rcx
0x18004325c  xor     ecx, ecx
0x18004325e  mov     [r11-38h], r14
0x180043262  mov     r12, rdx
0x180043265  mov     word ptr [rsp+130h+var_E0], r9w
0x18004326b  xor     edx, edx
0x18004326d  mov     dword ptr [rsp+130h+var_E0+4], r8d
0x180043272  mov     [rsp+60h], rax
0x180043277  mov     r14d, edx
0x18004327a  mov     dword ptr [rsp+130h+Size+4], edx
0x18004327e  mov     [rsp+130h+var_D8], rdx
0x180043283  mov     [rbp+30h+pdwUrlLength], edx
0x180043286  mov     [rbp+30h+var_60], rcx
0x18004328a  movups  xmmword ptr [rsp+130h+UrlComponents.lpszScheme], xmm0
0x18004328f  movups  xmmword ptr [rbp+30h+UrlComponents.lpszHostName], xmm0
0x180043293  movups  xmmword ptr [rbp+30h+UrlComponents.lpszUserName], xmm0
0x180043297  movups  xmmword ptr [rbp+30h+UrlComponents.lpszPassword], xmm0
0x18004329b  movups  xmmword ptr [rbp+30h+UrlComponents.lpszUrlPath], xmm0
0x18004329f  movups  xmmword ptr [rbp+30h+UrlComponents.lpszExtraInfo], xmm0
0x1800432a3  test    rax, rax
0x1800432a6  jz      loc_1800434B2
0x1800432ac  mov     [rax], rdx
0x1800432af  test    rbx, rbx
0x1800432b2  jz      loc_180043759
0x1800432b8  test    r12, r12
0x1800432bb  jz      loc_18004359F
0x1800432c1  mov     [r11-18h], rsi
0x1800432c5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800432cc  mov     [r11-20h], rdi
0x1800432d0  mov     esi, edx
0x1800432d2  mov     [r11-30h], r13
0x1800432d6  mov     edi, edx
0x1800432d8  mov     [r11-40h], r15
0x1800432dc  mov     dword ptr [rsp+130h+Size+4], edx
0x1800432e0  inc     rax
0x1800432e3  cmp     [rbx+rax*2], cx
0x1800432e7  jnz     short loc_1800432E0
0x1800432e9  mov     qword ptr [rsp+130h+var_E8], rax
0x1800432ee  lea     eax, ds:2[rax*2]
0x1800432f5  mov     dword ptr [rsp+130h+Size+4], edx
0x1800432f9  mov     ecx, eax; cb
0x1800432fb  mov     [rsp+130h+Size], rax
0x180043300  call    cs:__imp_CoTaskMemAlloc
0x180043306  mov     r15, rax
0x180043309  mov     r13d, 7FFFFFFEh
0x18004330f  test    rax, rax
0x180043312  jz      loc_18004347A
0x180043318  mov     r8, [rsp+130h+Size]; Size
0x18004331d  xor     edx, edx; Val
0x18004331f  mov     rcx, rax; void *
0x180043322  call    memset_0
0x180043327  mov     rax, qword ptr [rsp+130h+var_E8]
0x18004332c  add     eax, 1
0x18004332f  mov     r8d, eax
0x180043332  jz      loc_18004360B
0x180043338  cmp     r8, 7FFFFFFFh
0x18004333f  ja      loc_180043613
0x180043345  mov     edx, r13d
0x180043348  mov     rax, r15
0x18004334b  nop     dword ptr [rax+rax+00h]
0x180043350  test    rdx, rdx
0x180043353  jz      short loc_180043372
0x180043355  movzx   ecx, word ptr [rbx]
0x180043358  test    cx, cx
0x18004335b  jz      short loc_180043372
0x18004335d  mov     [r15], cx
0x180043361  add     rbx, 2
0x180043365  add     r15, 2
0x180043369  dec     rdx
0x18004336c  sub     r8, 1
0x180043370  jnz     short loc_180043350
0x180043372  test    r8, r8
0x180043375  lea     rdx, [r15-2]
0x180043379  mov     ebx, 8007007Ah
0x18004337e  cmovnz  rdx, r15
0x180043382  xor     ecx, ecx
0x180043384  test    r8, r8
0x180043387  cmovnz  ebx, ecx
0x18004338a  mov     [rdx], cx
0x18004338d  test    ebx, ebx
0x18004338f  js      loc_180043621
0x180043395  mov     rdi, rax
0x180043398  test    ebx, ebx
0x18004339a  js      loc_1800435B4
0x1800433a0  cmp     [r12], si
0x1800433a5  jz      loc_18004377E
0x1800433ab  xor     ecx, ecx
0x1800433ad  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800433b4  mov     dword ptr [rsp+130h+Size+4], ecx
0x1800433b8  mov     ebx, ecx
0x1800433ba  nop     word ptr [rax+rax+00h]
0x1800433c0  inc     rax
0x1800433c3  cmp     [r12+rax*2], cx
0x1800433c8  jnz     short loc_1800433C0
0x1800433ca  mov     dword ptr [rsp+130h+Size+4], ecx
0x1800433ce  mov     qword ptr [rsp+130h+var_E8], rax
0x1800433d3  lea     eax, ds:2[rax*2]
0x1800433da  mov     ecx, eax; cb
0x1800433dc  mov     [rsp+130h+Size], rax
0x1800433e1  call    cs:__imp_CoTaskMemAlloc
0x1800433e7  mov     r15, rax
0x1800433ea  test    rax, rax
0x1800433ed  jz      loc_180043494
0x1800433f3  mov     r8, [rsp+130h+Size]; Size
0x1800433f8  xor     edx, edx; Val
0x1800433fa  mov     rcx, rax; void *
0x1800433fd  call    memset_0
0x180043402  mov     rax, qword ptr [rsp+130h+var_E8]
0x180043407  add     eax, 1
0x18004340a  mov     r8d, eax
0x18004340d  jz      loc_180043640
0x180043413  cmp     r8, 7FFFFFFFh
0x18004341a  ja      loc_180043648
0x180043420  mov     rax, r15
0x180043423  test    r13, r13
0x180043426  jz      short loc_180043447
0x180043428  movzx   ecx, word ptr [r12]
0x18004342d  test    cx, cx
0x180043430  jz      short loc_180043447
0x180043432  mov     [r15], cx
0x180043436  add     r12, 2
0x18004343a  add     r15, 2
0x18004343e  dec     r13
0x180043441  sub     r8, 1
0x180043445  jnz     short loc_180043423
0x180043447  test    r8, r8
0x18004344a  lea     rdx, [r15-2]
0x18004344e  cmovnz  rdx, r15
0x180043452  xor     ecx, ecx
0x180043454  test    r8, r8
0x180043457  mov     [rdx], cx
0x18004345a  mov     edx, 8007007Ah
0x18004345f  cmovnz  edx, ecx
0x180043462  mov     [rsp+130h+var_E8], edx
0x180043466  test    edx, edx
0x180043468  js      loc_18004365A
0x18004346e  mov     rbx, rax
0x180043471  mov     [rsp+130h+var_E8], edx
0x180043475  jmp     loc_18004366B
0x18004347a  mov     dword ptr [rsp+130h+Size+4], 4Ch ; 'L'
0x180043482  mov     ebx, 8007000Eh
0x180043487  mov     dword ptr [rsp+130h+Size+4], 220h
0x18004348f  jmp     loc_180043398
0x180043494  mov     edx, 8007000Eh
0x180043499  mov     dword ptr [rsp+130h+Size+4], 4Ch ; 'L'
0x1800434a1  mov     [rsp+130h+var_E8], edx
0x1800434a5  mov     dword ptr [rsp+130h+Size+4], 220h
0x1800434ad  jmp     loc_18004366B
0x1800434b2  mov     dword ptr [rsp+130h+Size+4], 72h ; 'r'
0x1800434ba  mov     ebx, 80070057h
0x1800434bf  jmp     loc_180043568
0x1800434c4  mov     r8, r15; Size
0x1800434c7  xor     edx, edx; Val
0x1800434c9  mov     rcx, rsi; void *
0x1800434cc  call    memset_0
0x1800434d1  lea     r9, [rbp+30h+pdwUrlLength]; pdwUrlLength
0x1800434d5  mov     r8, rsi; pwszUrl
0x1800434d8  xor     edx, edx; dwFlags
0x1800434da  lea     rcx, [rsp+130h+UrlComponents.lpszScheme]; lpUrlComponents
0x1800434df  call    WinHttpCreateUrl
0x1800434e4  test    eax, eax
0x1800434e6  jz      loc_18004373B
0x1800434ec  test    byte ptr cs:xmmword_180107A60, 20h
0x1800434f3  jnz     loc_1800437DC
0x1800434f9  xor     r15d, r15d
0x1800434fc  mov     ecx, 20h ; ' '; cb
0x180043501  mov     dword ptr [rsp+130h+Size+4], r15d
0x180043506  mov     [rsp+130h+var_D8], r15
0x18004350b  call    cs:__imp_CoTaskMemAlloc
0x180043511  test    rax, rax
0x180043514  jz      loc_180043802
0x18004351a  mov     [rax+1Eh], r15w
0x18004351f  mov     rcx, [rsp+60h]
0x180043524  mov     [rax], rsi
0x180043527  mov     [rax+8], rdi
0x18004352b  mov     [rax+10h], rbx
0x18004352f  mov     ebx, r15d
0x180043532  mov     [rax+18h], r12d
0x180043536  mov     [rax+1Ch], r13w
0x18004353b  mov     [rcx], rax
0x18004353e  mov     [rsp+130h+var_D8], r15
0x180043543  mov     [rsp+130h+var_E8], r15d
0x180043548  mov     r13, [rsp+130h+var_28]
0x180043550  mov     rdi, [rsp+130h+var_18]
0x180043558  mov     rsi, [rsp+120h]
0x180043560  mov     r15, [rsp+130h+var_38]
0x180043568  mov     r12, [rsp+130h+var_20]
0x180043570  test    r14, r14
0x180043573  mov     r14, [rsp+130h+var_30]
0x18004357b  jz      short loc_180043587
0x18004357d  lea     rcx, [rsp+130h+var_D8]; struct tagProxyResolveUrl **
0x180043582  call    ?FreeProxyResolveUrl@@YAXPEAPEAUtagProxyResolveUrl@@@Z; FreeProxyResolveUrl(tagProxyResolveUrl * *)
0x180043587  mov     eax, ebx
0x180043589  mov     rcx, [rbp+30h+var_48]
0x18004358d  xor     rcx, rsp; StackCookie
0x180043590  call    __security_check_cookie
0x180043595  add     rsp, 128h
0x18004359c  pop     rbx
0x18004359d  pop     rbp
0x18004359e  retn
0x18004359f  mov     eax, 80070057h
0x1800435a4  mov     dword ptr [rsp+130h+Size+4], 76h ; 'v'
0x1800435ac  mov     [rsp+130h+var_E8], eax
0x1800435b0  mov     ebx, eax
0x1800435b2  jmp     short loc_180043568
0x1800435b4  mov     dword ptr [rsp+130h+Size+4], 78h ; 'x'
0x1800435bc  jmp     short loc_1800435E6
0x1800435be  test    edx, edx
0x1800435c0  mov     dword ptr [rsp+130h+Size+4], 93h
0x1800435c8  mov     eax, 8000FFFFh
0x1800435cd  cmovns  edx, eax
0x1800435d0  mov     [rsp+130h+var_E8], edx
0x1800435d4  test    rbx, rbx
0x1800435d7  jz      short loc_1800435E2
0x1800435d9  mov     rcx, rbx; pv
0x1800435dc  call    cs:__imp_CoTaskMemFree
0x1800435e2  mov     ebx, [rsp+130h+var_E8]
0x1800435e6  test    rdi, rdi
0x1800435e9  jz      short loc_1800435F4
0x1800435eb  mov     rcx, rdi; pv
0x1800435ee  call    cs:__imp_CoTaskMemFree
0x1800435f4  test    rsi, rsi
0x1800435f7  jz      loc_180043548
0x1800435fd  mov     rcx, rsi; pv
0x180043600  call    cs:__imp_CoTaskMemFree
0x180043606  jmp     loc_180043548
0x18004360b  test    eax, eax
0x18004360d  jz      loc_180043771
0x180043613  xor     eax, eax
0x180043615  mov     ebx, 80070057h
0x18004361a  mov     [r15], ax
0x18004361e  mov     rax, r15
0x180043621  mov     dword ptr [rsp+130h+Size+4], 224h
0x180043629  test    rax, rax
0x18004362c  jz      loc_180043398
0x180043632  mov     rcx, rax; pv
0x180043635  call    cs:__imp_CoTaskMemFree
0x18004363b  jmp     loc_180043398
0x180043640  test    eax, eax
0x180043642  jz      loc_18004378A
0x180043648  xor     eax, eax
0x18004364a  mov     edx, 80070057h
0x18004364f  mov     [r15], ax
0x180043653  mov     rax, r15
0x180043656  mov     [rsp+130h+var_E8], edx
0x18004365a  mov     dword ptr [rsp+130h+Size+4], 224h
0x180043662  test    rax, rax
0x180043665  jnz     loc_18004370C
0x18004366b  test    edx, edx
0x18004366d  js      loc_18004372E
0x180043673  mov     r12d, dword ptr [rsp+130h+var_E0+4]
0x180043678  mov     dword ptr [rsp+130h+UrlComponents.lpszScheme], 68h ; 'h'
0x180043680  cmp     r12d, 4
0x180043684  jnz     loc_18004371E
0x18004368a  mov     eax, 2
0x18004368f  movzx   r13d, word ptr [rsp+130h+var_E0]
0x180043695  lea     r9, [rbp+30h+pdwUrlLength]; pdwUrlLength
0x180043699  xor     r8d, r8d; pwszUrl
0x18004369c  mov     word ptr [rbp+30h+UrlComponents.lpszUserName+4], r13w
0x1800436a1  xor     edx, edx; dwFlags
0x1800436a3  mov     dword ptr [rbp+30h+UrlComponents.lpszHostName+4], eax
0x1800436a6  lea     rcx, [rsp+130h+UrlComponents.lpszScheme]; lpUrlComponents
0x1800436ab  mov     qword ptr [rbp+30h+UrlComponents.dwHostNameLength], rdi
0x1800436af  mov     qword ptr [rbp+30h+UrlComponents.dwUrlPathLength], rbx
0x1800436b3  call    WinHttpCreateUrl
0x1800436b8  test    eax, eax
0x1800436ba  jnz     loc_18004381F
0x1800436c0  call    cs:__imp_GetLastError
0x1800436c6  cmp     eax, 7Ah ; 'z'
0x1800436c9  jnz     loc_18004381F
0x1800436cf  mov     eax, [rbp+30h+pdwUrlLength]
0x1800436d2  add     eax, eax
0x1800436d4  mov     dword ptr [rsp+130h+Size+4], esi
0x1800436d8  mov     ecx, eax; cb
0x1800436da  mov     r15d, eax
0x1800436dd  call    cs:__imp_CoTaskMemAlloc
0x1800436e3  mov     rsi, rax
0x1800436e6  test    rax, rax
0x1800436e9  jnz     loc_1800434C4
0x1800436ef  mov     dword ptr [rsp+130h+Size+4], 4Ch ; 'L'
0x1800436f7  mov     dword ptr [rsp+130h+Size+4], 8Eh
0x1800436ff  mov     [rsp+130h+var_E8], 8007000Eh
0x180043707  jmp     loc_1800435D4
0x18004370c  mov     rcx, rax; pv
0x18004370f  call    cs:__imp_CoTaskMemFree
0x180043715  mov     edx, [rsp+130h+var_E8]
0x180043719  jmp     loc_18004366B
0x18004371e  cmp     r12d, 3
0x180043722  jnz     short loc_180043797
  ... truncated ...
```
