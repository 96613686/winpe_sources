# CPspGeneral::Init(uint,ushort const *)

- ea: `0x1800072c4`
- end: `0x180007697`
- name: `?Init@CPspGeneral@@QEAAJIPEBG@Z`
- size: `979`
- prototype: `__int64 __fastcall(CPspGeneral *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009e90`

## callees

- `0x1800072c4`
- `0x18000acd0`
- `0x18000adfc`
- `0x18000b240`
- `0x18000b49c`
- `0x18000d1c0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180007345`
- `msvcrt!wcscpy_s` at `0x18000735b`
- `msvcrt!wcscpy_s` at `0x18000740d`
- `msvcrt!wcscpy_s` at `0x18000761b`
- `msvcrt!wcscpy_s` at `0x180007345`
- `msvcrt!wcscpy_s` at `0x18000735b`
- `msvcrt!wcscpy_s` at `0x18000740d`
- `msvcrt!wcscpy_s` at `0x18000761b`
- `msvcrt!strcpy_s` at `0x18000754f`
- `msvcrt!strcpy_s` at `0x18000754f`
- `KERNEL32!GetLastError` at `0x180007578`
- `KERNEL32!GetLastError` at `0x180007578`
- `KERNEL32!MultiByteToWideChar` at `0x18000756e`
- `KERNEL32!MultiByteToWideChar` at `0x18000756e`
- `KERNEL32!WideCharToMultiByte` at `0x1800074a9`
- `KERNEL32!WideCharToMultiByte` at `0x1800074dd`
- `KERNEL32!WideCharToMultiByte` at `0x180007512`
- `KERNEL32!WideCharToMultiByte` at `0x1800074a9`
- `KERNEL32!WideCharToMultiByte` at `0x1800074dd`
- `KERNEL32!WideCharToMultiByte` at `0x180007512`
- `KERNEL32!lstrcmpiA` at `0x1800075e7`
- `KERNEL32!lstrcmpiA` at `0x1800075e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800073be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800073be`
- `SHLWAPI!PathFindExtensionA` at `0x180007521`
- `SHLWAPI!PathFindExtensionA` at `0x1800075da`
- `SHLWAPI!PathFindExtensionA` at `0x180007521`
- `SHLWAPI!PathFindExtensionA` at `0x1800075da`
- `SHLWAPI!PathFindExtensionW` at `0x18000738e`
- `SHLWAPI!PathFindExtensionW` at `0x180007448`
- `SHLWAPI!PathFindExtensionW` at `0x18000738e`
- `SHLWAPI!PathFindExtensionW` at `0x180007448`

## pseudocode

```c
__int64 __fastcall CPspGeneral::Init(CPspGeneral *this, __int64 a2, const unsigned __int16 *a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rax
  wchar_t *v8; // r14
  unsigned int v9; // edx
  int v10; // eax
  __int64 v11; // rbx
  wchar_t *ExtensionW; // rax
  _OWORD *v13; // rdi
  signed int v14; // ebx
  HKEY v15; // rdx
  const unsigned __int16 *v16; // rax
  unsigned __int64 v17; // r8
  const wchar_t *v18; // r8
  char *ExtensionA; // rax
  HKEY v20; // rdx
  signed int LastError; // eax
  const CHAR *v22; // rax
  __int64 v23; // rax
  _OWORD *v24; // rcx
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  int v32; // eax
  __int128 v33; // xmm1
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  CHAR pszPath[260]; // [rsp+50h] [rbp-B0h] BYREF
  CHAR v36[12]; // [rsp+154h] [rbp+54h] BYREF
  CHAR Source[272]; // [rsp+160h] [rbp+60h] BYREF
  CHAR MultiByteStr[272]; // [rsp+270h] [rbp+170h] BYREF

  v3 = -1;
  *((_BYTE *)this + 50) = 1;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    if ( v5 >= 0x104 )
      return 2147942522LL;
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    if ( v6 >= 0x104 )
      return 2147942522LL;
  }
  v8 = (wchar_t *)((char *)this + 52);
  wcscpy_s((wchar_t *)this + 26, 0x104u, a3);
  wcscpy_s((wchar_t *)this + 286, 0x104u, v8);
  bstrString = 0;
  v10 = LoadStr(&bstrString, v9);
  v11 = v10;
  if ( !v10 )
    return 2147500037LL;
  if ( Global::g_fWindowsNT )
  {
    ExtensionW = PathFindExtensionW((LPCWSTR)this + 286);
    v13 = (_OWORD *)((char *)this + 1092);
    if ( &ExtensionW[v11 + 1] > (wchar_t *)this + 546 )
    {
LABEL_13:
      v14 = -2147024774;
      goto LABEL_14;
    }
    wcscpy_s(ExtensionW, 260 - (((char *)ExtensionW - (char *)this - 572) >> 1), bstrString);
    v14 = CSettings::LoadFromRegistry((CPspGeneral *)((char *)this + 1092), v15);
    if ( v14 >= 0 )
    {
      v14 = CSettings::LoadFromFile((CPspGeneral *)((char *)this + 1092), (const unsigned __int16 *)this + 286);
      if ( (int)(v14 + 0x80000000) < 0 || v14 == -2147024894 )
      {
        v16 = PathFindExtensionW(v8);
        if ( (unsigned int)CompareStrsCaseInsensitive(bstrString, v16, v17) )
          goto LABEL_40;
        v18 = (const wchar_t *)((char *)this + 1120);
        if ( this == (CPspGeneral *)-1120LL )
          goto LABEL_39;
        do
          ++v3;
        while ( v18[v3] );
        goto LABEL_38;
      }
    }
  }
  else
  {
    if ( !WideCharToMultiByte(0, 0, v8, -1, MultiByteStr, 260, 0, 0)
      || !WideCharToMultiByte(0, 0, v8, -1, pszPath, 260, 0, 0)
      || !WideCharToMultiByte(0, 0, bstrString, -1, Source, 260, 0, 0) )
    {
      goto LABEL_30;
    }
    ExtensionA = PathFindExtensionA(pszPath);
    if ( &ExtensionA[v11 + 1] > v36 )
    {
      v14 = -2147024774;
      goto LABEL_14;
    }
    strcpy_s(ExtensionA, v36 - ExtensionA, Source);
    if ( !MultiByteToWideChar(0, 0, pszPath, -1, (LPWSTR)this + 286, 260) )
    {
LABEL_30:
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_14;
    }
    v13 = (_OWORD *)((char *)this + 1092);
    v14 = CSettings::LoadFromRegistry((CPspGeneral *)((char *)this + 1092), v20);
    if ( v14 >= 0 )
    {
      v14 = CSettings::LoadFromFile((CPspGeneral *)((char *)this + 1092), (const unsigned __int16 *)this + 286);
      if ( (int)(v14 + 0x80000000) < 0 || v14 == -2147024894 )
      {
        v22 = PathFindExtensionA(MultiByteStr);
        if ( lstrcmpiA(Source, v22) )
          goto LABEL_40;
        v18 = (const wchar_t *)((char *)this + 1120);
        if ( this == (CPspGeneral *)-1120LL )
        {
LABEL_39:
          wcscpy_s(v8, 0x104u, v18);
LABEL_40:
          v23 = 4;
          v24 = (_OWORD *)((char *)this + 1640);
          do
          {
            v25 = v13[1];
            *v24 = *v13;
            v26 = v13[2];
            v24[1] = v25;
            v27 = v13[3];
            v24[2] = v26;
            v28 = v13[4];
            v24[3] = v27;
            v29 = v13[5];
            v24[4] = v28;
            v30 = v13[6];
            v24[5] = v29;
            v31 = v13[7];
            v13 += 8;
            v24[6] = v30;
            v24[7] = v31;
            v24 += 8;
            --v23;
          }
          while ( v23 );
          v32 = *((_DWORD *)v13 + 8);
          v33 = v13[1];
          *v24 = *v13;
          v14 = 0;
          v24[1] = v33;
          *((_DWORD *)v24 + 8) = v32;
          goto LABEL_14;
        }
        do
          ++v3;
        while ( v18[v3] );
LABEL_38:
        if ( v3 >= 0x104 )
          goto LABEL_13;
        goto LABEL_39;
      }
    }
  }
LABEL_14:
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800072c4  mov     [rsp-8+arg_8], rbx
0x1800072c9  mov     [rsp-8+arg_18], rsi
0x1800072ce  push    rbp
0x1800072cf  push    rdi
0x1800072d0  push    r12
0x1800072d2  push    r14
0x1800072d4  push    r15
0x1800072d6  lea     rbp, [rsp-290h]
0x1800072de  sub     rsp, 390h
0x1800072e5  mov     rax, cs:__security_cookie
0x1800072ec  xor     rax, rsp
0x1800072ef  mov     [rbp+2B0h+var_30], rax
0x1800072f6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800072fa  mov     byte ptr [rcx+32h], 1
0x1800072fe  xor     edi, edi
0x180007300  mov     r15, rcx
0x180007303  mov     ebx, 104h
0x180007308  test    r8, r8
0x18000730b  jz      short loc_18000733B
0x18000730d  mov     rax, rsi
0x180007310  inc     rax
0x180007313  cmp     [r8+rax*2], di
0x180007318  jnz     short loc_180007310
0x18000731a  cmp     rax, rbx
0x18000731d  jnb     short loc_180007331
0x18000731f  mov     rax, rsi
0x180007322  inc     rax
0x180007325  cmp     [r8+rax*2], di
0x18000732a  jnz     short loc_180007322
0x18000732c  cmp     rax, rbx
0x18000732f  jb      short loc_18000733B
0x180007331  mov     eax, 8007007Ah
0x180007336  jmp     loc_1800073C6
0x18000733b  lea     r14, [rcx+34h]
0x18000733f  mov     rdx, rbx; SizeInWords
0x180007342  mov     rcx, r14; Destination
0x180007345  call    cs:__imp_wcscpy_s
0x18000734b  lea     r12, [r15+23Ch]
0x180007352  mov     r8, r14; Source
0x180007355  mov     rcx, r12; Destination
0x180007358  mov     rdx, rbx; SizeInWords
0x18000735b  call    cs:__imp_wcscpy_s
0x180007361  lea     rcx, [rsp+3B0h+bstrString]; unsigned __int16 **
0x180007366  mov     [rsp+3B0h+bstrString], rdi
0x18000736b  call    ?LoadStr@@YAHPEAPEAGI@Z; LoadStr(ushort * *,uint)
0x180007370  movsxd  rbx, eax
0x180007373  test    eax, eax
0x180007375  jnz     short loc_18000737E
0x180007377  mov     eax, 80004005h
0x18000737c  jmp     short loc_1800073C6
0x18000737e  cmp     cs:?g_fWindowsNT@Global@@2_NA, dil; bool Global::g_fWindowsNT
0x180007385  jz      loc_180007481
0x18000738b  mov     rcx, r12; pszPath
0x18000738e  call    cs:__imp_PathFindExtensionW
0x180007394  lea     rdx, [rbx+1]
0x180007398  mov     r9, rax
0x18000739b  lea     rdi, [r15+444h]
0x1800073a2  lea     rdx, [rax+rdx*2]
0x1800073a6  cmp     rdx, rdi
0x1800073a9  jbe     short loc_1800073F1
0x1800073ab  mov     ebx, 8007007Ah
0x1800073b0  xor     edi, edi
0x1800073b2  cmp     [rsp+3B0h+bstrString], rdi
0x1800073b7  jz      short loc_1800073C4
0x1800073b9  mov     rcx, [rsp+3B0h+bstrString]; bstrString
0x1800073be  call    cs:__imp_SysFreeString
0x1800073c4  mov     eax, ebx
0x1800073c6  mov     rcx, [rbp+2B0h+var_30]
0x1800073cd  xor     rcx, rsp; StackCookie
0x1800073d0  call    __security_check_cookie
0x1800073d5  lea     r11, [rsp+3B0h+var_20]
0x1800073dd  mov     rbx, [r11+38h]
0x1800073e1  mov     rsi, [r11+48h]
0x1800073e5  mov     rsp, r11
0x1800073e8  pop     r15
0x1800073ea  pop     r14
0x1800073ec  pop     r12
0x1800073ee  pop     rdi
0x1800073ef  pop     rbp
0x1800073f0  retn
0x1800073f1  mov     r8, [rsp+3B0h+bstrString]; Source
0x1800073f6  sub     rax, r15
0x1800073f9  sub     rax, 23Ch
0x1800073ff  mov     edx, 104h
0x180007404  sar     rax, 1
0x180007407  mov     rcx, r9; Destination
0x18000740a  sub     rdx, rax; SizeInWords
0x18000740d  call    cs:__imp_wcscpy_s
0x180007413  mov     rcx, rdi; this
0x180007416  call    ?LoadFromRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z; CSettings::LoadFromRegistry(HKEY__ *)
0x18000741b  mov     ebx, eax
0x18000741d  test    eax, eax
0x18000741f  js      short loc_1800073B0
0x180007421  mov     rdx, r12; unsigned __int16 *
0x180007424  mov     rcx, rdi; this
0x180007427  call    ?LoadFromFile@CSettings@@QEAAJPEBG@Z; CSettings::LoadFromFile(ushort const *)
0x18000742c  mov     ecx, 80000000h
0x180007431  mov     ebx, eax
0x180007433  add     eax, ecx
0x180007435  test    ecx, eax
0x180007437  jnz     short loc_180007445
0x180007439  cmp     ebx, 80070002h
0x18000743f  jnz     loc_1800073B0
0x180007445  mov     rcx, r14; pszPath
0x180007448  call    cs:__imp_PathFindExtensionW
0x18000744e  mov     rcx, [rsp+3B0h+bstrString]; unsigned __int16 *
0x180007453  mov     rdx, rax; unsigned __int16 *
0x180007456  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x18000745b  xor     ecx, ecx
0x18000745d  test    eax, eax
0x18000745f  jnz     loc_180007621
0x180007465  lea     r8, [rdi+1Ch]
0x180007469  test    r8, r8
0x18000746c  jz      loc_180007613
0x180007472  inc     rsi
0x180007475  cmp     [r8+rsi*2], cx
0x18000747a  jnz     short loc_180007472
0x18000747c  jmp     loc_180007606
0x180007481  mov     [rsp+3B0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180007486  lea     rax, [rbp+2B0h+MultiByteStr]
0x18000748d  mov     [rsp+3B0h+lpDefaultChar], rdi; lpDefaultChar
0x180007492  mov     r9d, esi; cchWideChar
0x180007495  mov     [rsp+3B0h+cbMultiByte], 104h; cbMultiByte
0x18000749d  mov     r8, r14; lpWideCharStr
0x1800074a0  xor     edx, edx; dwFlags
0x1800074a2  mov     [rsp+3B0h+lpMultiByteStr], rax; lpMultiByteStr
0x1800074a7  xor     ecx, ecx; CodePage
0x1800074a9  call    cs:__imp_WideCharToMultiByte
0x1800074af  test    eax, eax
0x1800074b1  jz      loc_180007578
0x1800074b7  mov     [rsp+3B0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800074bc  lea     rax, [rsp+3B0h+pszPath]
0x1800074c1  mov     [rsp+3B0h+lpDefaultChar], rdi; lpDefaultChar
0x1800074c6  mov     r9d, esi; cchWideChar
0x1800074c9  mov     [rsp+3B0h+cbMultiByte], 104h; cbMultiByte
0x1800074d1  mov     r8, r14; lpWideCharStr
0x1800074d4  xor     edx, edx; dwFlags
0x1800074d6  mov     [rsp+3B0h+lpMultiByteStr], rax; lpMultiByteStr
0x1800074db  xor     ecx, ecx; CodePage
0x1800074dd  call    cs:__imp_WideCharToMultiByte
0x1800074e3  test    eax, eax
0x1800074e5  jz      loc_180007578
0x1800074eb  mov     r8, [rsp+3B0h+bstrString]; lpWideCharStr
0x1800074f0  lea     rax, [rbp+2B0h+Source]
0x1800074f4  mov     [rsp+3B0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800074f9  mov     r9d, esi; cchWideChar
0x1800074fc  mov     [rsp+3B0h+lpDefaultChar], rdi; lpDefaultChar
0x180007501  xor     edx, edx; dwFlags
0x180007503  mov     [rsp+3B0h+cbMultiByte], 104h; cbMultiByte
0x18000750b  xor     ecx, ecx; CodePage
0x18000750d  mov     [rsp+3B0h+lpMultiByteStr], rax; lpMultiByteStr
0x180007512  call    cs:__imp_WideCharToMultiByte
0x180007518  test    eax, eax
0x18000751a  jz      short loc_180007578
0x18000751c  lea     rcx, [rsp+3B0h+pszPath]; pszPath
0x180007521  call    cs:__imp_PathFindExtensionA
0x180007527  lea     rdx, [rbx+1]
0x18000752b  add     rdx, rax
0x18000752e  lea     rcx, [rbp+2B0h+var_25C]
0x180007532  cmp     rdx, rcx
0x180007535  jbe     short loc_180007541
0x180007537  mov     ebx, 8007007Ah
0x18000753c  jmp     loc_1800073B2
0x180007541  lea     rdx, [rbp+2B0h+var_25C]
0x180007545  mov     rcx, rax; Destination
0x180007548  sub     rdx, rax; SizeInBytes
0x18000754b  lea     r8, [rbp+2B0h+Source]; Source
0x18000754f  call    cs:__imp_strcpy_s
0x180007555  mov     r9d, esi; cbMultiByte
0x180007558  mov     [rsp+3B0h+cbMultiByte], 104h; cchWideChar
0x180007560  lea     r8, [rsp+3B0h+pszPath]; lpMultiByteStr
0x180007565  mov     [rsp+3B0h+lpMultiByteStr], r12; lpWideCharStr
0x18000756a  xor     edx, edx; dwFlags
0x18000756c  xor     ecx, ecx; CodePage
0x18000756e  call    cs:__imp_MultiByteToWideChar
0x180007574  test    eax, eax
0x180007576  jnz     short loc_180007596
0x180007578  call    cs:__imp_GetLastError
0x18000757e  mov     ebx, eax
0x180007580  test    eax, eax
0x180007582  jle     loc_1800073B2
0x180007588  movzx   ebx, ax
0x18000758b  or      ebx, 80070000h
0x180007591  jmp     loc_1800073B2
0x180007596  lea     rdi, [r15+444h]
0x18000759d  mov     rcx, rdi; this
0x1800075a0  call    ?LoadFromRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z; CSettings::LoadFromRegistry(HKEY__ *)
0x1800075a5  mov     ebx, eax
0x1800075a7  test    eax, eax
0x1800075a9  js      loc_1800073B0
0x1800075af  mov     rdx, r12; unsigned __int16 *
0x1800075b2  mov     rcx, rdi; this
0x1800075b5  call    ?LoadFromFile@CSettings@@QEAAJPEBG@Z; CSettings::LoadFromFile(ushort const *)
0x1800075ba  mov     ecx, 80000000h
0x1800075bf  mov     ebx, eax
0x1800075c1  add     eax, ecx
0x1800075c3  test    ecx, eax
0x1800075c5  jnz     short loc_1800075D3
0x1800075c7  cmp     ebx, 80070002h
0x1800075cd  jnz     loc_1800073B0
0x1800075d3  lea     rcx, [rbp+2B0h+MultiByteStr]; pszPath
0x1800075da  call    cs:__imp_PathFindExtensionA
0x1800075e0  mov     rdx, rax; lpString2
0x1800075e3  lea     rcx, [rbp+2B0h+Source]; lpString1
0x1800075e7  call    cs:__imp_lstrcmpiA
0x1800075ed  xor     ecx, ecx
0x1800075ef  test    eax, eax
0x1800075f1  jnz     short loc_180007621
0x1800075f3  lea     r8, [rdi+1Ch]; Source
0x1800075f7  test    r8, r8
0x1800075fa  jz      short loc_180007613
0x1800075fc  inc     rsi
0x1800075ff  cmp     [r8+rsi*2], cx
0x180007604  jnz     short loc_1800075FC
0x180007606  cmp     rsi, 104h
0x18000760d  jnb     loc_1800073AB
0x180007613  mov     edx, 104h; SizeInWords
0x180007618  mov     rcx, r14; Destination
0x18000761b  call    cs:__imp_wcscpy_s
0x180007621  mov     eax, 4
0x180007626  lea     rcx, [r15+668h]
0x18000762d  lea     edx, [rax+7Ch]
0x180007630  movups  xmm0, xmmword ptr [rdi]
0x180007633  movups  xmm1, xmmword ptr [rdi+10h]
0x180007637  movups  xmmword ptr [rcx], xmm0
0x18000763a  movups  xmm0, xmmword ptr [rdi+20h]
0x18000763e  movups  xmmword ptr [rcx+10h], xmm1
0x180007642  movups  xmm1, xmmword ptr [rdi+30h]
0x180007646  movups  xmmword ptr [rcx+20h], xmm0
0x18000764a  movups  xmm0, xmmword ptr [rdi+40h]
0x18000764e  movups  xmmword ptr [rcx+30h], xmm1
0x180007652  movups  xmm1, xmmword ptr [rdi+50h]
0x180007656  movups  xmmword ptr [rcx+40h], xmm0
0x18000765a  movups  xmm0, xmmword ptr [rdi+60h]
0x18000765e  movups  xmmword ptr [rcx+50h], xmm1
0x180007662  movups  xmm1, xmmword ptr [rdi+70h]
0x180007666  add     rdi, rdx
0x180007669  movups  xmmword ptr [rcx+60h], xmm0
0x18000766d  movups  xmmword ptr [rcx+70h], xmm1
0x180007671  add     rcx, rdx
0x180007674  sub     rax, 1
0x180007678  jnz     short loc_180007630
0x18000767a  movups  xmm0, xmmword ptr [rdi]
0x18000767d  mov     eax, [rdi+20h]
0x180007680  movups  xmm1, xmmword ptr [rdi+10h]
0x180007684  xor     edi, edi
0x180007686  movups  xmmword ptr [rcx], xmm0
0x180007689  mov     ebx, edi
0x18000768b  movups  xmmword ptr [rcx+10h], xmm1
0x18000768f  mov     [rcx+20h], eax
0x180007692  jmp     loc_1800073B2
```
