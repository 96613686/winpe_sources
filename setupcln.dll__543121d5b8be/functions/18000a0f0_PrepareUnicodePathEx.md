# PrepareUnicodePathEx

- ea: `0x18000a0f0`
- end: `0x18000a779`
- name: `PrepareUnicodePathEx`
- size: `1673`
- prototype: `wchar_t *__fastcall(STRSAFE_LPCWSTR pszSrc, wchar_t **)`
- caller_count: `9`
- callee_count: `8`
- tags: ``

## callers

- `0x1800099c0`
- `0x180009dd4`
- `0x18000aa40`
- `0x18000b044`
- `0x18000b0ec`
- `0x18000b230`
- `0x18000bb18`
- `0x18000c048`
- `0x18000c17c`

## callees

- `0x1800029a5`
- `0x18000946c`
- `0x180009d30`
- `0x180009f8c`
- `0x18000a0f0`
- `0x18000a780`
- `0x1800131ae`
- `0x1800131e0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000a1ea`
- `msvcrt!_wcsnicmp` at `0x18000a382`
- `msvcrt!_wcsnicmp` at `0x18000a39a`
- `msvcrt!_wcsnicmp` at `0x18000a3b3`
- `msvcrt!_wcsnicmp` at `0x18000a3e4`
- `msvcrt!_wcsnicmp` at `0x18000a431`
- `msvcrt!_wcsnicmp` at `0x18000a455`
- `msvcrt!_wcsnicmp` at `0x18000a5df`
- `msvcrt!_wcsnicmp` at `0x18000a607`
- `msvcrt!_wcsnicmp` at `0x18000a63a`
- `msvcrt!_wcsnicmp` at `0x18000a65e`
- `msvcrt!_wcsnicmp` at `0x18000a67b`
- `msvcrt!_wcsnicmp` at `0x18000a6ab`
- `msvcrt!_wcsnicmp` at `0x18000a1ea`
- `msvcrt!_wcsnicmp` at `0x18000a382`
- `msvcrt!_wcsnicmp` at `0x18000a39a`
- `msvcrt!_wcsnicmp` at `0x18000a3b3`
- `msvcrt!_wcsnicmp` at `0x18000a3e4`
- `msvcrt!_wcsnicmp` at `0x18000a431`
- `msvcrt!_wcsnicmp` at `0x18000a455`
- `msvcrt!_wcsnicmp` at `0x18000a5df`
- `msvcrt!_wcsnicmp` at `0x18000a607`
- `msvcrt!_wcsnicmp` at `0x18000a63a`
- `msvcrt!_wcsnicmp` at `0x18000a65e`
- `msvcrt!_wcsnicmp` at `0x18000a67b`
- `msvcrt!_wcsnicmp` at `0x18000a6ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a73a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a74a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a73a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a74a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a16b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a23f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a16b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a23f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a573`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a723`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a573`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a723`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a581`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a70a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a731`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a581`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a70a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a731`

## pseudocode

```c
wchar_t *__fastcall PrepareUnicodePathEx(STRSAFE_LPCWSTR pszSrc, wchar_t **a2)
{
  WCHAR *v3; // r13
  signed int v4; // edi
  signed int LastError; // eax
  bool v6; // sf
  signed int v7; // eax
  __int64 v8; // r15
  unsigned __int64 v9; // rax
  wchar_t *v10; // rsi
  int v11; // eax
  const wchar_t *v12; // rdx
  wchar_t *v13; // rcx
  signed int v14; // eax
  bool v15; // sf
  signed int v16; // eax
  signed int v17; // eax
  bool v18; // sf
  signed int v19; // eax
  const wchar_t *i; // r15
  wchar_t *j; // r15
  wchar_t *v22; // rbx
  int v23; // eax
  void *v24; // r14
  wchar_t v25; // cx
  int v26; // eax
  HANDLE ProcessHeap; // rax
  const wchar_t *v28; // rcx
  wchar_t *v29; // rax
  wchar_t *v30; // rax
  const wchar_t *v31; // rbx
  const wchar_t *k; // rbx
  wchar_t *m; // rbx
  HANDLE v34; // rax
  HANDLE v35; // rax
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t **v38; // [rsp+28h] [rbp-D8h]
  wchar_t String2[4]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszSrca[8]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t v41[12]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v42[12]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v43[12]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t v44[20]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v45[16]; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t v46[16]; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t v47[16]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t v48[16]; // [rsp+118h] [rbp+18h] BYREF
  wchar_t v49[24]; // [rsp+138h] [rbp+38h] BYREF

  v38 = a2;
  wcscpy(String2, L"\\\\?");
  wcscpy(pszSrca, L"\\\\?\\UNC");
  if ( !pszSrc || !*pszSrc )
  {
    SetLastError(0x57u);
    return 0;
  }
  v3 = FormFullPathName(pszSrc);
  if ( v3 )
  {
    v4 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError < 0;
    if ( LastError > 0 )
      v6 = 1;
    if ( !v6 )
    {
      LOWORD(v4) = 16389;
      goto LABEL_102;
    }
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_102;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( v3[v9] );
  if ( v9 < 0x104 )
    goto LABEL_30;
  v10 = 0;
  if ( wcsncmp_0(v3, String2, 3u) && _wcsnicmp(v3, pszSrca, 7u) )
  {
    v37 = 0;
    v11 = ParseUncPathEx(v3, &v37, 0);
    LOWORD(v4) = v11;
    if ( v11 < 0 )
      goto LABEL_102;
    if ( v37 == 1 )
    {
      v12 = v3 + 1;
      v13 = pszSrca;
    }
    else
    {
      v12 = v3;
      v13 = String2;
    }
    v10 = BuildPath(v13, v12);
    if ( v10 )
    {
      v4 = 0;
    }
    else
    {
      v14 = GetLastError();
      v15 = v14 < 0;
      if ( v14 > 0 )
        v15 = 1;
      if ( v15 )
      {
        v16 = GetLastError();
        v4 = v16;
        if ( v16 > 0 )
          v4 = (unsigned __int16)v16 | 0x80070000;
      }
      else
      {
        v4 = -2147467259;
      }
    }
  }
  if ( v4 < 0 )
    goto LABEL_98;
  if ( !v10 )
  {
LABEL_30:
    v10 = (wchar_t *)StrDupe(pszSrc);
    if ( v10 )
    {
      v4 = 0;
      goto LABEL_38;
    }
    v17 = GetLastError();
    v18 = v17 < 0;
    if ( v17 > 0 )
      v18 = 1;
    if ( v18 )
    {
      v19 = GetLastError();
      v4 = v19;
      if ( v19 > 0 )
        v4 = (unsigned __int16)v19 | 0x80070000;
      if ( v4 < 0 )
        goto LABEL_102;
      goto LABEL_38;
    }
    LOWORD(v4) = 16389;
LABEL_102:
    v10 = 0;
    goto LABEL_103;
  }
LABEL_38:
  if ( !v38 )
    goto LABEL_103;
  wcscpy(v47, L"\\\\?\\GLBALROOT");
  wcscpy(v48, L"\\??\\GLBALROOT");
  wcscpy(v45, L"\\\\arddisk");
  wcscpy(v46, L"\\?arddisk");
  wcscpy(v41, L"Partition");
  wcscpy(v42, L"\\\\?\\Volume{");
  wcscpy(v43, L"\\??\\Volume{");
  if ( _wcsnicmp(v10, v47, 0xEu) && _wcsnicmp(v10, v48, 0xEu) )
  {
    if ( !_wcsnicmp(v10, v45, 0xCu) )
    {
      for ( i = v10 + 13; (unsigned __int16)(*i - 48) <= 9u; ++i )
        ;
      if ( !_wcsnicmp(i, v41, 9u) )
      {
        for ( j = (wchar_t *)(i + 10); (unsigned __int16)(*j - 48) <= 9u; ++j )
          ;
        v22 = 0;
        if ( *j == 92 )
          v22 = j;
        goto LABEL_97;
      }
LABEL_96:
      v22 = 0;
      goto LABEL_97;
    }
    if ( !_wcsnicmp(v10, v42, 0xBu) )
    {
      v22 = v10 + 48;
      goto LABEL_97;
    }
    v22 = 0;
    if ( _wcsnicmp(v10, pszSrca, 7u) )
    {
      if ( !wcsncmp_0(v10, String2, 3u) )
      {
        v25 = v10[4];
        if ( ((unsigned __int16)(v25 - 97) <= 0x19u || (unsigned __int16)(v25 - 65) <= 0x19u) && v10[5] == 58 )
        {
          v22 = v10 + 6;
          if ( v10[6] == 92 )
            goto LABEL_97;
        }
        goto LABEL_96;
      }
      if ( ((unsigned __int16)(*v10 - 97) <= 0x19u || (unsigned __int16)(*v10 - 65) <= 0x19u)
        && v10[1] == 58
        && v10[2] == 92 )
      {
        v22 = v10 + 2;
        goto LABEL_97;
      }
      v37 = 0;
      *(_QWORD *)String2 = 0;
      v26 = ParseUncPathEx(v10, &v37, (LPVOID *)String2);
      v24 = *(void **)String2;
      v4 = v26;
      if ( v26 < 0 || v37 != 1 )
        goto LABEL_74;
      do
        ++v8;
      while ( *(_WORD *)(*(_QWORD *)String2 + 2 * v8) );
    }
    else
    {
      v37 = 0;
      *(_QWORD *)String2 = 0;
      v23 = ParseUncPathEx(v10, &v37, (LPVOID *)String2);
      v24 = *(void **)String2;
      v4 = v23;
      if ( v23 < 0 || v37 != 1 )
      {
LABEL_74:
        if ( v24 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v24);
        }
        goto LABEL_97;
      }
      do
        ++v8;
      while ( *(_WORD *)(*(_QWORD *)String2 + 2 * v8) );
    }
    v22 = &v10[v8];
    goto LABEL_74;
  }
  v22 = v10 + 14;
  wcscpy(v49, L"\\Device\\HarddikVolume");
  wcscpy(v44, L"\\Device\\Harddisk");
  if ( !_wcsnicmp(v10 + 14, v49, 0x16u) )
  {
    v28 = v10 + 37;
LABEL_78:
    v29 = wcschr_0(v28, 0x5Cu);
    goto LABEL_95;
  }
  if ( !_wcsnicmp(v10 + 14, v44, 0x10u) )
  {
    v30 = wcschr_0(v10 + 31, 0x5Cu);
    if ( !v30 )
      goto LABEL_96;
    v31 = v30 + 1;
    if ( _wcsnicmp(v30 + 1, v41, 9u) )
      goto LABEL_96;
    v28 = v31;
    goto LABEL_78;
  }
  if ( !_wcsnicmp(v10 + 14, v43, 0xBu) )
  {
    v22 = v10 + 62;
    goto LABEL_97;
  }
  if ( !_wcsnicmp(v10 + 14, v46, 0xCu) )
  {
    for ( k = v10 + 27; (unsigned __int16)(*k - 48) <= 9u; ++k )
      ;
    if ( _wcsnicmp(k, v41, 9u) )
      goto LABEL_96;
    for ( m = (wchar_t *)(k + 10); (unsigned __int16)(*m - 48) <= 9u; ++m )
      ;
    v29 = 0;
    if ( *m == 92 )
      v29 = m;
LABEL_95:
    v22 = v29;
  }
LABEL_97:
  *v38 = v22;
  if ( v4 < 0 )
  {
LABEL_98:
    if ( v10 )
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v10);
    }
    goto LABEL_102;
  }
LABEL_103:
  if ( v3 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v3);
  }
  SetLastError((unsigned __int16)v4);
  return v10;
}

```

## disassembly

```asm
0x18000a0f0  mov     [rsp-8+arg_10], rbx
0x18000a0f5  push    rbp
0x18000a0f6  push    rsi
0x18000a0f7  push    rdi
0x18000a0f8  push    r12
0x18000a0fa  push    r13
0x18000a0fc  push    r14
0x18000a0fe  push    r15
0x18000a100  lea     rbp, [rsp-70h]
0x18000a105  sub     rsp, 170h
0x18000a10c  mov     rax, cs:__security_cookie
0x18000a113  xor     rax, rsp
0x18000a116  mov     [rbp+0A0h+var_38], rax
0x18000a11a  movups  xmm0, xmmword ptr cs:aUnc; "\\\\?\\UNC"
0x18000a121  xor     r12d, r12d
0x18000a124  mov     [rsp+1A0h+var_178], rdx
0x18000a129  mov     rax, 3F005C005Ch
0x18000a133  mov     r14, rcx
0x18000a136  mov     qword ptr [rsp+1A0h+String2], rax
0x18000a13b  movdqu  xmmword ptr [rsp+1A0h+pszSrc], xmm0
0x18000a141  test    rcx, rcx
0x18000a144  jz      loc_18000A745
0x18000a14a  cmp     r12w, [rcx]
0x18000a14e  jz      loc_18000A745
0x18000a154  call    FormFullPathName
0x18000a159  mov     r13, rax
0x18000a15c  mov     ebx, 80070000h
0x18000a161  test    rax, rax
0x18000a164  jz      short loc_18000A16B
0x18000a166  mov     edi, r12d
0x18000a169  jmp     short loc_18000A19B
0x18000a16b  call    cs:__imp_GetLastError
0x18000a171  test    eax, eax
0x18000a173  jle     short loc_18000A17C
0x18000a175  movzx   eax, ax
0x18000a178  or      eax, ebx
0x18000a17a  test    eax, eax
0x18000a17c  jns     loc_18000A716
0x18000a182  call    cs:__imp_GetLastError
0x18000a188  mov     edi, eax
0x18000a18a  test    eax, eax
0x18000a18c  jle     short loc_18000A193
0x18000a18e  movzx   edi, ax
0x18000a191  or      edi, ebx
0x18000a193  test    edi, edi
0x18000a195  js      loc_18000A71B
0x18000a19b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000a19f  mov     rax, r15
0x18000a1a2  inc     rax
0x18000a1a5  cmp     [r13+rax*2+0], r12w
0x18000a1ab  jnz     short loc_18000A1A2
0x18000a1ad  mov     ebx, 80004005h
0x18000a1b2  cmp     rax, 104h
0x18000a1b8  jb      loc_18000A27B
0x18000a1be  mov     r8d, 3; MaxCount
0x18000a1c4  lea     rdx, [rsp+1A0h+String2]; String2
0x18000a1c9  mov     rcx, r13; String1
0x18000a1cc  mov     rsi, r12
0x18000a1cf  call    wcsncmp_0
0x18000a1d4  test    eax, eax
0x18000a1d6  jz      loc_18000A26E
0x18000a1dc  mov     r8d, 7; MaxCount
0x18000a1e2  lea     rdx, [rsp+1A0h+pszSrc]; String2
0x18000a1e7  mov     rcx, r13; String1
0x18000a1ea  call    cs:__imp__wcsnicmp
0x18000a1f0  test    eax, eax
0x18000a1f2  jz      short loc_18000A26E
0x18000a1f4  xor     r8d, r8d
0x18000a1f7  mov     [rsp+1A0h+var_180], r12d
0x18000a1fc  lea     rdx, [rsp+1A0h+var_180]
0x18000a201  mov     rcx, r13; String1
0x18000a204  call    ParseUncPathEx
0x18000a209  mov     edi, eax
0x18000a20b  test    eax, eax
0x18000a20d  js      loc_18000A71B
0x18000a213  cmp     [rsp+1A0h+var_180], 1
0x18000a218  jnz     short loc_18000A235
0x18000a21a  lea     rdx, [r13+2]; STRSAFE_PCNZWCH
0x18000a21e  lea     rcx, [rsp+1A0h+pszSrc]; pszSrc
0x18000a223  call    BuildPath
0x18000a228  mov     rsi, rax
0x18000a22b  test    rax, rax
0x18000a22e  jz      short loc_18000A23F
0x18000a230  mov     edi, r12d
0x18000a233  jmp     short loc_18000A26E
0x18000a235  mov     rdx, r13
0x18000a238  lea     rcx, [rsp+1A0h+String2]
0x18000a23d  jmp     short loc_18000A223
0x18000a23f  call    cs:__imp_GetLastError
0x18000a245  test    eax, eax
0x18000a247  jle     short loc_18000A253
0x18000a249  movzx   eax, ax
0x18000a24c  or      eax, 80070000h
0x18000a251  test    eax, eax
0x18000a253  jns     short loc_18000A26C
0x18000a255  call    cs:__imp_GetLastError
0x18000a25b  mov     edi, eax
0x18000a25d  test    eax, eax
0x18000a25f  jle     short loc_18000A26E
0x18000a261  movzx   edi, ax
0x18000a264  or      edi, 80070000h
0x18000a26a  jmp     short loc_18000A26E
0x18000a26c  mov     edi, ebx
0x18000a26e  test    edi, edi
0x18000a270  js      loc_18000A6F7
0x18000a276  test    rsi, rsi
0x18000a279  jnz     short loc_18000A2C7
0x18000a27b  mov     rcx, r14; pszSrc
0x18000a27e  call    StrDupe
0x18000a283  mov     rsi, rax
0x18000a286  test    rax, rax
0x18000a289  jz      short loc_18000A290
0x18000a28b  mov     edi, r12d
0x18000a28e  jmp     short loc_18000A2C7
0x18000a290  call    cs:__imp_GetLastError
0x18000a296  test    eax, eax
0x18000a298  jle     short loc_18000A2A4
0x18000a29a  movzx   eax, ax
0x18000a29d  or      eax, 80070000h
0x18000a2a2  test    eax, eax
0x18000a2a4  jns     loc_18000A712
0x18000a2aa  call    cs:__imp_GetLastError
0x18000a2b0  mov     edi, eax
0x18000a2b2  test    eax, eax
0x18000a2b4  jle     short loc_18000A2BF
0x18000a2b6  movzx   edi, ax
0x18000a2b9  or      edi, 80070000h
0x18000a2bf  test    edi, edi
0x18000a2c1  js      loc_18000A71B
0x18000a2c7  cmp     [rsp+1A0h+var_178], r12
0x18000a2cc  jz      loc_18000A71E
0x18000a2d2  movups  xmm0, xmmword ptr cs:aGlobalroot; "\\\\?\\GLOBALROOT"
0x18000a2d9  mov     eax, dword ptr cs:aPartition+10h; "n"
0x18000a2df  mov     ebx, 0Eh
0x18000a2e4  movups  xmm1, xmmword ptr cs:aGlobalroot+0Eh; "BALROOT"
0x18000a2eb  mov     r8d, ebx; MaxCount
0x18000a2ee  lea     rdx, [rbp+0A0h+var_A8]; String2
0x18000a2f2  movups  xmmword ptr [rbp+0A0h+var_A8], xmm0
0x18000a2f6  mov     rcx, rsi; String1
0x18000a2f9  mov     [rsp+1A0h+var_148], eax
0x18000a2fd  movups  xmm0, xmmword ptr cs:aGlobalroot_0; "\\??\\GLOBALROOT"
0x18000a304  movups  xmmword ptr [rbp+0A0h+var_A8+0Eh], xmm1
0x18000a308  movups  xmm1, xmmword ptr cs:aGlobalroot_0+0Eh; "BALROOT"
0x18000a30f  movups  xmmword ptr [rbp+0A0h+var_88], xmm0
0x18000a313  movups  xmm0, xmmword ptr cs:aHarddisk; "\\\\?\\Harddisk"
0x18000a31a  movups  xmmword ptr [rbp+0A0h+var_88+0Eh], xmm1
0x18000a31e  movups  xmm1, xmmword ptr cs:aHarddisk+0Ah; "arddisk"
0x18000a325  movups  xmmword ptr [rbp+0A0h+var_E8], xmm0
0x18000a329  movups  xmm0, xmmword ptr cs:aHarddisk_0; "\\??\\Harddisk"
0x18000a330  movups  xmmword ptr [rbp+0A0h+var_E8+0Ah], xmm1
0x18000a334  movups  xmm1, xmmword ptr cs:aHarddisk_0+0Ah; "arddisk"
0x18000a33b  movups  xmmword ptr [rbp+0A0h+var_C8], xmm0
0x18000a33f  movups  xmm0, xmmword ptr cs:aPartition; "Partition"
0x18000a346  movups  xmmword ptr [rbp+0A0h+var_C8+0Ah], xmm1
0x18000a34a  movsd   xmm1, qword ptr cs:aVolume_0+10h; "me{"
0x18000a352  movups  xmmword ptr [rsp+1A0h+var_158], xmm0
0x18000a357  movups  xmm0, xmmword ptr cs:aVolume_0; "\\\\?\\Volume{"
0x18000a35e  movsd   [rsp+1A0h+var_130], xmm1
0x18000a364  movsd   xmm1, qword ptr cs:aVolume+10h; "me{"
0x18000a36c  movups  xmmword ptr [rsp+1A0h+var_140], xmm0
0x18000a371  movups  xmm0, xmmword ptr cs:aVolume; "\\??\\Volume{"
0x18000a378  movsd   [rbp+0A0h+var_118], xmm1
0x18000a37d  movups  xmmword ptr [rsp+1A0h+var_128], xmm0
0x18000a382  call    cs:__imp__wcsnicmp
0x18000a388  test    eax, eax
0x18000a38a  jz      loc_18000A58C
0x18000a390  mov     r8d, ebx; MaxCount
0x18000a393  lea     rdx, [rbp+0A0h+var_88]; String2
0x18000a397  mov     rcx, rsi; String1
0x18000a39a  call    cs:__imp__wcsnicmp
0x18000a3a0  test    eax, eax
0x18000a3a2  jz      loc_18000A58C
0x18000a3a8  lea     r8d, [rbx-2]; MaxCount
0x18000a3ac  mov     rcx, rsi; String1
0x18000a3af  lea     rdx, [rbp+0A0h+var_E8]; String2
0x18000a3b3  call    cs:__imp__wcsnicmp
0x18000a3b9  test    eax, eax
0x18000a3bb  jnz     short loc_18000A423
0x18000a3bd  lea     r15, [rsi+1Ah]
0x18000a3c1  lea     r12d, [rbx-5]
0x18000a3c5  movzx   eax, word ptr [r15]
0x18000a3c9  sub     ax, 30h ; '0'
0x18000a3cd  cmp     ax, r12w
0x18000a3d1  ja      short loc_18000A3D9
0x18000a3d3  add     r15, 2
0x18000a3d7  jmp     short loc_18000A3C5
0x18000a3d9  mov     r8, r12; MaxCount
0x18000a3dc  lea     rdx, [rsp+1A0h+var_158]; String2
0x18000a3e1  mov     rcx, r15; String1
0x18000a3e4  call    cs:__imp__wcsnicmp
0x18000a3ea  test    eax, eax
0x18000a3ec  jnz     loc_18000A6E5
0x18000a3f2  add     r15, 14h
0x18000a3f6  movzx   eax, word ptr [r15]
0x18000a3fa  sub     ax, 30h ; '0'
0x18000a3fe  cmp     ax, r12w
0x18000a402  ja      short loc_18000A40A
0x18000a404  add     r15, 2
0x18000a408  jmp     short loc_18000A3F6
0x18000a40a  xor     r12d, r12d
0x18000a40d  mov     r14d, 5Ch ; '\'
0x18000a413  cmp     r14w, [r15]
0x18000a417  mov     ebx, r12d
0x18000a41a  cmovz   rbx, r15
0x18000a41e  jmp     loc_18000A6EB
0x18000a423  mov     r8d, 0Bh; MaxCount
0x18000a429  lea     rdx, [rsp+1A0h+var_140]; String2
0x18000a42e  mov     rcx, rsi; String1
0x18000a431  call    cs:__imp__wcsnicmp
0x18000a437  test    eax, eax
0x18000a439  jnz     short loc_18000A444
0x18000a43b  lea     rbx, [rsi+60h]
0x18000a43f  jmp     loc_18000A6EB
0x18000a444  mov     r8d, 7; MaxCount
0x18000a44a  lea     rdx, [rsp+1A0h+pszSrc]; String2
0x18000a44f  mov     rcx, rsi; String1
0x18000a452  mov     rbx, r12
0x18000a455  call    cs:__imp__wcsnicmp
0x18000a45b  mov     rcx, rsi; String1
0x18000a45e  test    eax, eax
0x18000a460  jnz     short loc_18000A4A4
0x18000a462  lea     r8, [rsp+1A0h+String2]
0x18000a467  mov     [rsp+1A0h+var_180], r12d
0x18000a46c  lea     rdx, [rsp+1A0h+var_180]
0x18000a471  mov     qword ptr [rsp+1A0h+String2], r12
0x18000a476  call    ParseUncPathEx
0x18000a47b  mov     r14, qword ptr [rsp+1A0h+String2]
0x18000a480  mov     edi, eax
0x18000a482  test    eax, eax
0x18000a484  js      loc_18000A56A
0x18000a48a  cmp     [rsp+1A0h+var_180], 1
0x18000a48f  jnz     loc_18000A56A
0x18000a495  inc     r15
0x18000a498  cmp     [r14+r15*2], r12w
0x18000a49d  jnz     short loc_18000A495
0x18000a49f  jmp     loc_18000A566
0x18000a4a4  mov     r8d, 3; MaxCount
0x18000a4aa  lea     rdx, [rsp+1A0h+String2]; String2
0x18000a4af  call    wcsncmp_0
0x18000a4b4  test    eax, eax
0x18000a4b6  jnz     short loc_18000A4F9
0x18000a4b8  movzx   ecx, word ptr [rsi+8]
0x18000a4bc  lea     eax, [rcx-61h]
0x18000a4bf  cmp     ax, 19h
0x18000a4c3  jbe     short loc_18000A4D3
0x18000a4c5  sub     cx, 41h ; 'A'
0x18000a4c9  cmp     cx, 19h
0x18000a4cd  ja      loc_18000A6E8
0x18000a4d3  mov     eax, 3Ah ; ':'
0x18000a4d8  cmp     ax, [rsi+0Ah]
0x18000a4dc  jnz     loc_18000A6E8
0x18000a4e2  lea     rbx, [rsi+0Ch]
0x18000a4e6  lea     r14d, [rax+22h]
0x18000a4ea  cmp     r14w, [rbx]
0x18000a4ee  jz      loc_18000A6EB
0x18000a4f4  jmp     loc_18000A6E8
0x18000a4f9  movzx   ecx, word ptr [rsi]
0x18000a4fc  lea     eax, [rcx-61h]
0x18000a4ff  cmp     ax, 19h
0x18000a503  jbe     short loc_18000A50F
0x18000a505  sub     cx, 41h ; 'A'
0x18000a509  cmp     cx, 19h
0x18000a50d  ja      short loc_18000A52E
0x18000a50f  mov     eax, 3Ah ; ':'
0x18000a514  cmp     ax, [rsi+2]
0x18000a518  jnz     short loc_18000A52E
0x18000a51a  lea     r14d, [rax+22h]
0x18000a51e  cmp     r14w, [rsi+4]
0x18000a523  jnz     short loc_18000A52E
0x18000a525  lea     rbx, [rsi+4]
0x18000a529  jmp     loc_18000A6EB
0x18000a52e  lea     r8, [rsp+1A0h+String2]
0x18000a533  mov     [rsp+1A0h+var_180], r12d
0x18000a538  lea     rdx, [rsp+1A0h+var_180]
0x18000a53d  mov     qword ptr [rsp+1A0h+String2], r12
0x18000a542  mov     rcx, rsi; String1
0x18000a545  call    ParseUncPathEx
0x18000a54a  mov     r14, qword ptr [rsp+1A0h+String2]
0x18000a54f  mov     edi, eax
0x18000a551  test    eax, eax
0x18000a553  js      short loc_18000A56A
0x18000a555  cmp     [rsp+1A0h+var_180], 1
0x18000a55a  jnz     short loc_18000A56A
0x18000a55c  inc     r15
0x18000a55f  cmp     [r14+r15*2], r12w
0x18000a564  jnz     short loc_18000A55C
0x18000a566  lea     rbx, [rsi+r15*2]
0x18000a56a  test    r14, r14
0x18000a56d  jz      loc_18000A6EB
0x18000a573  call    cs:__imp_GetProcessHeap
0x18000a579  mov     r8, r14; lpMem
0x18000a57c  xor     edx, edx; dwFlags
0x18000a57e  mov     rcx, rax; hHeap
0x18000a581  call    cs:__imp_HeapFree
0x18000a587  jmp     loc_18000A6EB
0x18000a58c  movups  xmm0, xmmword ptr cs:aDeviceHarddisk_0; "\\Device\\HarddiskVolume"
0x18000a593  movzx   eax, word ptr cs:aDeviceHarddisk+20h; ""
0x18000a59a  lea     rbx, [rsi+1Ch]
0x18000a59e  movups  xmm1, xmmword ptr cs:aDeviceHarddisk_0+10h; "HarddiskVolume"
0x18000a5a5  mov     r8d, 16h; MaxCount
  ... truncated ...
```
