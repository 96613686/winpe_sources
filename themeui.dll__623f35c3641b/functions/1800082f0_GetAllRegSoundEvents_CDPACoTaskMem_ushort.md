# GetAllRegSoundEvents(CDPACoTaskMem<ushort> *)

- ea: `0x1800082f0`
- end: `0x1800089ae`
- name: `?GetAllRegSoundEvents@@YAHPEAV?$CDPACoTaskMem@G@@@Z`
- size: `1726`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008a50`
- `0x18000eeb0`
- `0x180010b20`
- `0x180041a2c`

## callees

- `0x1800082f0`
- `0x1800089c0`
- `0x180012b60`
- `0x1800151e0`
- `0x1800358c0`
- `0x18003633c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008740`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008740`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000895f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000895f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000882d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800088d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008928`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008974`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000882d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800088d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008928`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008346`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000850d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008864`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008346`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000850d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008864`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800088b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800088b6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800083f0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008560`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800083f0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008560`

## pseudocode

```c
__int64 __fastcall GetAllRegSoundEvents(HDPA *a1)
{
  LSTATUS v2; // eax
  bool v3; // sf
  DWORD i; // r13d
  LSTATUS v6; // eax
  bool v7; // sf
  __int64 v8; // rcx
  const wchar_t *v9; // rdx
  __int64 v10; // r8
  WCHAR *v11; // r9
  WCHAR *v12; // rcx
  __int64 v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // r9
  WCHAR *v16; // r8
  bool v17; // zf
  __int64 v18; // rdx
  __int64 v19; // rcx
  WCHAR *v20; // r9
  WCHAR *v21; // rcx
  LSTATUS v22; // eax
  bool v23; // sf
  DWORD j; // r15d
  LSTATUS v25; // eax
  signed int v26; // r14d
  __int64 v27; // rcx
  WCHAR *v28; // rdx
  __int64 v29; // r8
  WCHAR *v30; // r9
  WCHAR *v31; // rcx
  __int64 v32; // rcx
  WCHAR *v33; // rax
  __int64 v34; // r9
  const wchar_t *v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rcx
  WCHAR *v38; // r9
  WCHAR *v39; // rcx
  __int64 v40; // rcx
  WCHAR *v41; // rax
  __int64 v42; // r9
  WCHAR *v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rcx
  WCHAR *v46; // r9
  WCHAR *v47; // rcx
  unsigned __int64 v48; // rbx
  unsigned __int64 v49; // rdi
  _WORD *v50; // rsi
  int v51; // eax
  WCHAR *v52; // rcx
  unsigned __int64 v53; // rdx
  _WORD *v54; // r8
  __int64 v55; // r9
  _WORD *v56; // rcx
  __int64 v57; // r10
  int v58; // eax
  LSTATUS v59; // eax
  bool v60; // sf
  LSTATUS v61; // eax
  bool v62; // sf
  __int64 v63; // rdi
  bool v64; // cf
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY v67; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v70; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR v73[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v75[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR Name[264]; // [rsp+6A0h] [rbp+5A0h] BYREF
  WCHAR v77[264]; // [rsp+8B0h] [rbp+7B0h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_CURRENT_USER, L"AppEvents\\Schemes\\Apps", 0, 0x20019u, &hKey);
  v3 = v2 < 0;
  if ( v2 > 0 )
    v3 = 1;
  if ( !v3 )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      v6 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      v7 = v6 < 0;
      if ( v6 > 0 )
        v7 = 1;
      if ( v7 )
      {
        RegCloseKey(hKey);
        goto LABEL_4;
      }
      v8 = 2147483646;
      v9 = L"AppEvents\\Schemes\\Apps\\";
      v10 = 260;
      v11 = SubKey;
      do
      {
        if ( !v8 )
          break;
        if ( !*v9 )
          break;
        *v11++ = *v9++;
        --v8;
        --v10;
      }
      while ( v10 );
      v12 = v11 - 1;
      if ( v10 )
        v12 = v11;
      *v12 = 0;
      if ( v10 )
      {
        v13 = 260;
        v14 = SubKey;
        do
        {
          if ( !*v14 )
            break;
          ++v14;
          --v13;
        }
        while ( v13 );
        v15 = 260 - v13;
        if ( v13 )
        {
          v16 = Name;
          v18 = v13;
          v17 = v15 == 260;
          v19 = 2147483646;
          v20 = &SubKey[v15];
          if ( !v17 )
          {
            do
            {
              if ( !v19 )
                break;
              if ( !*v16 )
                break;
              *v20++ = *v16++;
              --v19;
              --v18;
            }
            while ( v18 );
          }
          v21 = v20 - 1;
          if ( v18 )
            v21 = v20;
          *v21 = 0;
          if ( v18 )
          {
            phkResult = 0;
            v22 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, &phkResult);
            v23 = v22 < 0;
            if ( v22 > 0 )
              v23 = 1;
            if ( !v23 )
              break;
          }
        }
      }
LABEL_85:
      ;
    }
    for ( j = 0; ; ++j )
    {
      while ( 1 )
      {
        v70 = 260;
        v25 = RegEnumKeyExW(phkResult, j, v75, &v70, 0, 0, 0, 0);
        v26 = v25;
        if ( v25 > 0 )
          v26 = (unsigned __int16)v25 | 0x80070000;
        if ( v26 < 0 )
          goto LABEL_83;
        v67 = 0;
        if ( (int)StringCchPrintfW(v77, 0x104u, L"Appevents\\eventlabels\\%s", v75) >= 0 )
        {
          v59 = RegOpenKeyExW(HKEY_CURRENT_USER, v77, 0, 0x20019u, &v67);
          v60 = v59 < 0;
          if ( v59 > 0 )
            v60 = 1;
          if ( !v60 )
            break;
        }
LABEL_36:
        v27 = 2147483646;
        v28 = SubKey;
        v29 = 260;
        v30 = v73;
        do
        {
          if ( !v27 )
            break;
          if ( !*v28 )
            break;
          *v30++ = *v28++;
          --v27;
          --v29;
        }
        while ( v29 );
        v31 = v30 - 1;
        if ( v29 )
          v31 = v30;
        *v31 = 0;
        if ( !v29 )
          goto LABEL_83;
        v32 = 260;
        v33 = v73;
        do
        {
          if ( !*v33 )
            break;
          ++v33;
          --v32;
        }
        while ( v32 );
        v34 = 260 - v32;
        if ( !v32 )
          goto LABEL_83;
        v35 = L"\\";
        v36 = v32;
        v17 = v34 == 260;
        v37 = 2147483646;
        v38 = &v73[v34];
        if ( !v17 )
        {
          do
          {
            if ( !v37 )
              break;
            if ( !*v35 )
              break;
            *v38++ = *v35++;
            --v37;
            --v36;
          }
          while ( v36 );
        }
        v39 = v38 - 1;
        if ( v36 )
          v39 = v38;
        *v39 = 0;
        if ( !v36 )
          goto LABEL_83;
        v40 = 260;
        v41 = v73;
        do
        {
          if ( !*v41 )
            break;
          ++v41;
          --v40;
        }
        while ( v40 );
        v42 = 260 - v40;
        if ( !v40 )
          goto LABEL_83;
        v43 = v75;
        v44 = v40;
        v17 = v42 == 260;
        v45 = 2147483646;
        v46 = &v73[v42];
        if ( !v17 )
        {
          do
          {
            if ( !v45 )
              break;
            if ( !*v43 )
              break;
            *v46++ = *v43++;
            --v45;
            --v44;
          }
          while ( v44 );
        }
        v47 = v46 - 1;
        if ( v44 )
          v47 = v46;
        *v47 = 0;
        if ( !v44 )
          goto LABEL_83;
        v48 = -1;
        do
          ++v48;
        while ( v73[v48] );
        v49 = v48 + 1;
        if ( v48 + 1 < v48 )
        {
          ++j;
        }
        else
        {
          *(_QWORD *)Data = 0;
          if ( !is_mul_ok(v49, 2u) )
            goto LABEL_83;
          v50 = CoTaskMemAlloc(2 * v49);
          v51 = -2147024882;
          if ( v50 )
            v51 = 0;
          if ( v51 < 0 )
            goto LABEL_83;
          if ( (v50 || v48 == -1) && v49 <= 0x7FFFFFFF )
          {
            if ( v48 >= 0x7FFFFFFF )
            {
              if ( v48 != -1 )
                *v50 = 0;
            }
            else
            {
              v52 = v73;
              v53 = v48 + 1;
              v54 = v50;
              v55 = 0;
              do
              {
                if ( !v48 )
                  break;
                if ( !*v52 )
                  break;
                *v54++ = *v52++;
                --v48;
                ++v55;
                --v53;
              }
              while ( v53 );
              v56 = v54 - 1;
              v57 = v55 - 1;
              if ( v53 )
              {
                v56 = v54;
                v57 = v55;
              }
              *v56 = 0;
              if ( v53 )
              {
                v64 = v49 == v57;
                v63 = v49 - v57;
                if ( !v64 && v63 != 1 && (unsigned __int64)(2 * v63) > 2 )
                  memset_0(&v50[v57 + 1], 0, 2 * v63 - 2);
              }
            }
          }
          else
          {
            *v50 = 0;
          }
          v58 = DPA_Search(*a1, v50, 0, DPA_FindString, 0, 5u);
          if ( DPA_InsertPtr(*a1, v58, v50) == -1 )
          {
            CoTaskMemFree(v50);
            ++j;
          }
          else
          {
LABEL_83:
            ++j;
            if ( v26 < 0 )
            {
              RegCloseKey(phkResult);
              goto LABEL_85;
            }
          }
        }
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      v61 = RegQueryValueExW(v67, L"ExcludeFromCPL", 0, &Type, Data, &cbData);
      v62 = v61 < 0;
      if ( v61 > 0 )
        v62 = 1;
      if ( v62 || Type != 4 || cbData < 4 || !*(_DWORD *)Data )
      {
        RegCloseKey(v67);
        goto LABEL_36;
      }
      RegCloseKey(v67);
    }
  }
LABEL_4:
  if ( *a1 )
    return *(unsigned int *)*a1;
  else
    return 0;
}

```

## disassembly

```asm
0x1800082f0  push    rbp
0x1800082f2  push    rsi
0x1800082f3  lea     rbp, [rsp-9E8h]
0x1800082fb  sub     rsp, 0AE8h
0x180008302  mov     rax, cs:__security_cookie
0x180008309  xor     rax, rsp
0x18000830c  mov     [rbp+9F0h+var_30], rax
0x180008313  lea     rax, [rsp+0AF0h+hKey]
0x180008318  mov     [rsp+0AF0h+arg_18], r12
0x180008320  mov     r12, rcx
0x180008323  mov     [rsp+0AF0h+phkResult], rax; phkResult
0x180008328  xor     esi, esi
0x18000832a  lea     rdx, String1; "AppEvents\\Schemes\\Apps"
0x180008331  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180008338  mov     [rsp+0AF0h+hKey], rsi
0x18000833d  mov     r9d, 20019h; samDesired
0x180008343  xor     r8d, r8d; ulOptions
0x180008346  call    cs:__imp_RegOpenKeyExW
0x18000834c  test    eax, eax
0x18000834e  jle     short loc_18000835A
0x180008350  movzx   eax, ax
0x180008353  or      eax, 80070000h
0x180008358  test    eax, eax
0x18000835a  jns     short loc_18000838C
0x18000835c  mov     rax, [r12]
0x180008360  mov     r12, [rsp+0AF0h+arg_18]
0x180008368  test    rax, rax
0x18000836b  jnz     loc_1800089A7
0x180008371  mov     eax, esi
0x180008373  mov     rcx, [rbp+9F0h+var_30]
0x18000837a  xor     rcx, rsp; StackCookie
0x18000837d  call    __security_check_cookie
0x180008382  add     rsp, 0AE8h
0x180008389  pop     rsi
0x18000838a  pop     rbp
0x18000838b  retn
0x18000838c  mov     [rsp+0AF0h+arg_8], rbx
0x180008394  mov     [rsp+0AF0h+arg_10], rdi
0x18000839c  mov     [rsp+0AF0h+var_10], r13
0x1800083a4  mov     r13d, esi
0x1800083a7  mov     [rsp+0AF0h+var_18], r14
0x1800083af  mov     [rsp+0AF0h+var_20], r15
0x1800083b7  nop     word ptr [rax+rax+00000000h]
0x1800083c0  mov     rcx, [rsp+0AF0h+hKey]; hKey
0x1800083c5  lea     r9, [rsp+0AF0h+cchName]; lpcchName
0x1800083ca  mov     [rsp+0AF0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800083cf  lea     r8, [rbp+9F0h+Name]; lpName
0x1800083d6  mov     [rsp+0AF0h+lpcchClass], rsi; lpcchClass
0x1800083db  mov     edx, r13d; dwIndex
0x1800083de  mov     [rsp+0AF0h+lpClass], rsi; lpClass
0x1800083e3  mov     [rsp+0AF0h+phkResult], rsi; lpReserved
0x1800083e8  mov     [rsp+0AF0h+cchName], 104h
0x1800083f0  call    cs:__imp_RegEnumKeyExW
0x1800083f6  test    eax, eax
0x1800083f8  jle     short loc_180008404
0x1800083fa  movzx   eax, ax
0x1800083fd  or      eax, 80070000h
0x180008402  test    eax, eax
0x180008404  js      loc_18000896F
0x18000840a  mov     ecx, 7FFFFFFEh
0x18000840f  lea     rdx, aAppeventsSchem_25; "AppEvents\\Schemes\\Apps\\"
0x180008416  mov     r8d, 104h
0x18000841c  lea     r9, [rbp+9F0h+SubKey]
0x180008423  test    rcx, rcx
0x180008426  jz      short loc_180008445
0x180008428  movzx   eax, word ptr [rdx]
0x18000842b  test    ax, ax
0x18000842e  jz      short loc_180008445
0x180008430  mov     [r9], ax
0x180008434  add     rdx, 2
0x180008438  add     r9, 2
0x18000843c  dec     rcx
0x18000843f  sub     r8, 1
0x180008443  jnz     short loc_180008423
0x180008445  test    r8, r8
0x180008448  lea     rcx, [r9-2]
0x18000844c  cmovnz  rcx, r9
0x180008450  mov     [rcx], si
0x180008453  jz      loc_180008833
0x180008459  mov     ecx, 104h
0x18000845e  lea     rax, [rbp+9F0h+SubKey]
0x180008465  cmp     word ptr [rax], 0
0x180008469  jz      short loc_180008475
0x18000846b  add     rax, 2
0x18000846f  sub     rcx, 1
0x180008473  jnz     short loc_180008465
0x180008475  mov     r9d, 104h
0x18000847b  sub     r9, rcx
0x18000847e  test    rcx, rcx
0x180008481  cmovz   r9, rsi
0x180008485  jz      loc_180008833
0x18000848b  mov     edx, 104h
0x180008490  lea     r8, [rbp+9F0h+Name]
0x180008497  sub     rdx, r9
0x18000849a  mov     ecx, 7FFFFFFEh
0x18000849f  lea     r9, [rbp+r9*2+9F0h+SubKey]
0x1800084a7  jz      short loc_1800084D3
0x1800084a9  nop     dword ptr [rax+00000000h]
0x1800084b0  test    rcx, rcx
0x1800084b3  jz      short loc_1800084D3
0x1800084b5  movzx   eax, word ptr [r8]
0x1800084b9  test    ax, ax
0x1800084bc  jz      short loc_1800084D3
0x1800084be  mov     [r9], ax
0x1800084c2  add     r8, 2
0x1800084c6  add     r9, 2
0x1800084ca  dec     rcx
0x1800084cd  sub     rdx, 1
0x1800084d1  jnz     short loc_1800084B0
0x1800084d3  test    rdx, rdx
0x1800084d6  lea     rcx, [r9-2]
0x1800084da  cmovnz  rcx, r9
0x1800084de  mov     [rcx], si
0x1800084e1  jz      loc_180008833
0x1800084e7  lea     rax, [rsp+0AF0h+var_A90]
0x1800084ec  mov     [rsp+0AF0h+var_A90], rsi
0x1800084f1  mov     r9d, 20019h; samDesired
0x1800084f7  mov     [rsp+0AF0h+phkResult], rax; phkResult
0x1800084fc  xor     r8d, r8d; ulOptions
0x1800084ff  lea     rdx, [rbp+9F0h+SubKey]; lpSubKey
0x180008506  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000850d  call    cs:__imp_RegOpenKeyExW
0x180008513  test    eax, eax
0x180008515  jle     short loc_180008521
0x180008517  movzx   eax, ax
0x18000851a  or      eax, 80070000h
0x18000851f  test    eax, eax
0x180008521  js      loc_180008833
0x180008527  mov     r15d, esi
0x18000852a  nop     word ptr [rax+rax+00h]
0x180008530  mov     rcx, [rsp+0AF0h+var_A90]; hKey
0x180008535  lea     r9, [rsp+0AF0h+var_A94]; lpcchName
0x18000853a  mov     [rsp+0AF0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18000853f  lea     r8, [rbp+9F0h+var_660]; lpName
0x180008546  mov     [rsp+0AF0h+lpcchClass], rsi; lpcchClass
0x18000854b  mov     edx, r15d; dwIndex
0x18000854e  mov     [rsp+0AF0h+lpClass], rsi; lpClass
0x180008553  mov     [rsp+0AF0h+phkResult], rsi; lpReserved
0x180008558  mov     [rsp+0AF0h+var_A94], 104h
0x180008560  call    cs:__imp_RegEnumKeyExW
0x180008566  mov     r14d, eax
0x180008569  test    eax, eax
0x18000856b  jle     short loc_180008578
0x18000856d  movzx   r14d, ax
0x180008571  or      r14d, 80070000h
0x180008578  test    r14d, r14d
0x18000857b  js      loc_18000881C
0x180008581  lea     r9, [rbp+9F0h+var_660]
0x180008588  mov     [rsp+0AF0h+var_AA8], rsi
0x18000858d  lea     r8, aAppeventsEvent; "Appevents\\eventlabels\\%s"
0x180008594  mov     edx, 104h; unsigned __int64
0x180008599  lea     rcx, [rbp+9F0h+var_240]; unsigned __int16 *
0x1800085a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800085a5  test    eax, eax
0x1800085a7  jns     loc_180008843
0x1800085ad  mov     ecx, 7FFFFFFEh
0x1800085b2  lea     rdx, [rbp+9F0h+SubKey]
0x1800085b9  mov     r8d, 104h
0x1800085bf  lea     r9, [rsp+0AF0h+var_A80]
0x1800085c4  test    rcx, rcx
0x1800085c7  jz      short loc_1800085E6
0x1800085c9  movzx   eax, word ptr [rdx]
0x1800085cc  test    ax, ax
0x1800085cf  jz      short loc_1800085E6
0x1800085d1  mov     [r9], ax
0x1800085d5  add     rdx, 2
0x1800085d9  add     r9, 2
0x1800085dd  dec     rcx
0x1800085e0  sub     r8, 1
0x1800085e4  jnz     short loc_1800085C4
0x1800085e6  test    r8, r8
0x1800085e9  lea     rcx, [r9-2]
0x1800085ed  cmovnz  rcx, r9
0x1800085f1  mov     [rcx], si
0x1800085f4  jz      loc_18000881C
0x1800085fa  mov     ecx, 104h
0x1800085ff  lea     rax, [rsp+0AF0h+var_A80]
0x180008604  cmp     word ptr [rax], 0
0x180008608  jz      short loc_180008614
0x18000860a  add     rax, 2
0x18000860e  sub     rcx, 1
0x180008612  jnz     short loc_180008604
0x180008614  mov     r9d, 104h
0x18000861a  sub     r9, rcx
0x18000861d  test    rcx, rcx
0x180008620  cmovz   r9, rsi
0x180008624  jz      loc_18000881C
0x18000862a  mov     r8d, 104h
0x180008630  lea     rdx, Control; "\\"
0x180008637  sub     r8, r9
0x18000863a  mov     ecx, 7FFFFFFEh
0x18000863f  lea     r9, [rsp+r9*2+0AF0h+var_A80]
0x180008644  jz      short loc_180008668
0x180008646  test    rcx, rcx
0x180008649  jz      short loc_180008668
0x18000864b  movzx   eax, word ptr [rdx]
0x18000864e  test    ax, ax
0x180008651  jz      short loc_180008668
0x180008653  mov     [r9], ax
0x180008657  add     rdx, 2
0x18000865b  add     r9, 2
0x18000865f  dec     rcx
0x180008662  sub     r8, 1
0x180008666  jnz     short loc_180008646
0x180008668  test    r8, r8
0x18000866b  lea     rcx, [r9-2]
0x18000866f  cmovnz  rcx, r9
0x180008673  mov     [rcx], si
0x180008676  jz      loc_18000881C
0x18000867c  mov     ecx, 104h
0x180008681  lea     rax, [rsp+0AF0h+var_A80]
0x180008686  cmp     word ptr [rax], 0
0x18000868a  jz      short loc_180008696
0x18000868c  add     rax, 2
0x180008690  sub     rcx, 1
0x180008694  jnz     short loc_180008686
0x180008696  mov     r9d, 104h
0x18000869c  sub     r9, rcx
0x18000869f  test    rcx, rcx
0x1800086a2  cmovz   r9, rsi
0x1800086a6  jz      loc_18000881C
0x1800086ac  mov     r8d, 104h
0x1800086b2  lea     rdx, [rbp+9F0h+var_660]
0x1800086b9  sub     r8, r9
0x1800086bc  mov     ecx, 7FFFFFFEh
0x1800086c1  lea     r9, [rsp+r9*2+0AF0h+var_A80]
0x1800086c6  jz      short loc_1800086EA
0x1800086c8  test    rcx, rcx
0x1800086cb  jz      short loc_1800086EA
0x1800086cd  movzx   eax, word ptr [rdx]
0x1800086d0  test    ax, ax
0x1800086d3  jz      short loc_1800086EA
0x1800086d5  mov     [r9], ax
0x1800086d9  add     rdx, 2
0x1800086dd  add     r9, 2
0x1800086e1  dec     rcx
0x1800086e4  sub     r8, 1
0x1800086e8  jnz     short loc_1800086C8
0x1800086ea  test    r8, r8
0x1800086ed  lea     rcx, [r9-2]
0x1800086f1  cmovnz  rcx, r9
0x1800086f5  mov     [rcx], si
0x1800086f8  jz      loc_18000881C
0x1800086fe  lea     rax, [rsp+0AF0h+var_A80]
0x180008703  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000870a  nop     word ptr [rax+rax+00h]
0x180008710  inc     rbx
0x180008713  cmp     word ptr [rax+rbx*2], 0
0x180008718  jnz     short loc_180008710
0x18000871a  lea     rdi, [rbx+1]
0x18000871e  cmp     rdi, rbx
0x180008721  jb      loc_18000883B
0x180008727  mov     eax, 2
0x18000872c  mov     qword ptr [rsp+0AF0h+Data], rsi
0x180008731  mul     rdi
0x180008734  test    rdx, rdx
0x180008737  jnz     loc_18000881C
0x18000873d  mov     rcx, rax; cb
0x180008740  call    cs:__imp_CoTaskMemAlloc
0x180008746  mov     rsi, rax
0x180008749  xor     ecx, ecx
0x18000874b  test    rsi, rsi
0x18000874e  mov     eax, 8007000Eh
0x180008753  cmovnz  eax, ecx
0x180008756  test    eax, eax
0x180008758  js      loc_18000881A
0x18000875e  test    rsi, rsi
0x180008761  jz      loc_180008936
0x180008767  cmp     rdi, 7FFFFFFFh
0x18000876e  ja      loc_18000893F
0x180008774  cmp     rbx, 7FFFFFFFh
0x18000877b  jnb     loc_180008949
0x180008781  test    rdi, rdi
0x180008784  jz      short loc_1800087DA
0x180008786  lea     rcx, [rsp+0AF0h+var_A80]
0x18000878b  mov     rdx, rdi
0x18000878e  mov     r8, rsi
0x180008791  xor     r9d, r9d
0x180008794  test    rbx, rbx
0x180008797  jz      short loc_1800087B9
0x180008799  movzx   eax, word ptr [rcx]
0x18000879c  test    ax, ax
0x18000879f  jz      short loc_1800087B9
0x1800087a1  mov     [r8], ax
0x1800087a5  add     rcx, 2
0x1800087a9  add     r8, 2
0x1800087ad  dec     rbx
0x1800087b0  inc     r9
0x1800087b3  sub     rdx, 1
0x1800087b7  jnz     short loc_180008794
0x1800087b9  test    rdx, rdx
0x1800087bc  lea     rcx, [r8-2]
0x1800087c0  lea     r10, [r9-1]
0x1800087c4  cmovnz  rcx, r8
0x1800087c8  cmovnz  r10, r9
0x1800087cc  xor     eax, eax
0x1800087ce  mov     [rcx], ax
0x1800087d1  test    rdx, rdx
0x1800087d4  jnz     loc_1800088DC
0x1800087da  mov     rcx, [r12]; hdpa
  ... truncated ...
```
