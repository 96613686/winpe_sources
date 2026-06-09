# SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration(void)

- ea: `0x180005b40`
- end: `0x180005eb9`
- name: `?GetPersonalizationParamsFromDefaultConfiguration@SharedDataManager@@AEAAPEAUHrtfPersonalizationParams@@XZ`
- size: `889`
- prototype: `struct HrtfPersonalizationParams *__fastcall(SharedDataManager *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005ec0`
- `0x1800069f0`

## callees

- `0x180002988`
- `0x180002a88`
- `0x18000424c`
- `0x1800051cc`
- `0x180005b40`
- `0x1800073ec`
- `0x180007484`
- `0x1800078e4`
- `0x18000e990`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005e52`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005e7b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005e52`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005e6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005e6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005d75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005dc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005d75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005dc2`
- `ext-ms-win-audiocore-spatial-l1-1-0!TryGetCustomModelPaths` at `0x180005c63`
- `ext-ms-win-audiocore-spatial-l1-1-0!TryGetCustomModelPaths` at `0x180005c63`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct HrtfPersonalizationParams *__fastcall SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration(
        HKEY *this)
{
  char *v2; // r14
  int v3; // r15d
  char *v4; // rdi
  char *v5; // rsi
  __int64 *v6; // rbx
  __int64 v7; // rbx
  __int64 v8; // rdx
  int v9; // r15d
  char *v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // r14
  HKEY v15; // r15
  DWORD LastError; // ebx
  signed int v17; // eax
  unsigned int v18; // r15d
  unsigned __int64 v19; // rdi
  __int64 v20; // rbx
  int phkResult; // [rsp+20h] [rbp-79h]
  unsigned __int16 v23; // [rsp+30h] [rbp-69h] BYREF
  __int128 v24; // [rsp+38h] [rbp-61h] BYREF
  char *v25; // [rsp+48h] [rbp-51h]
  HKEY hKey; // [rsp+50h] [rbp-49h] BYREF
  _QWORD *v27; // [rsp+58h] [rbp-41h] BYREF
  __int64 *v28; // [rsp+60h] [rbp-39h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-31h] BYREF
  HKEY *v30[2]; // [rsp+70h] [rbp-29h] BYREF
  void *v31[4]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v24 = 0;
  v2 = 0;
  v25 = 0;
  lpSubKey = L"Software\\Microsoft\\Multimedia\\Audio\\Hrtf";
  v23 = 8;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  do
  {
    v6 = &qword_18001FA60[4 * v3];
    if ( (unsigned __int64)v6[3] >= 8 )
      v6 = (__int64 *)*v6;
    v28 = v6;
    if ( &v28 >= (__int64 **)v4 || v5 > (char *)&v28 )
    {
      if ( v4 == v2 )
      {
        std::vector<wchar_t const *>::_Reserve(&v24, qword_18001FA60);
        v2 = v25;
        v4 = (char *)*((_QWORD *)&v24 + 1);
        v5 = (char *)v24;
      }
      *(_QWORD *)v4 = v6;
    }
    else
    {
      v7 = ((char *)&v28 - v5) >> 3;
      if ( v4 == v2 )
      {
        std::vector<wchar_t const *>::_Reserve(&v24, qword_18001FA60);
        v2 = v25;
        v4 = (char *)*((_QWORD *)&v24 + 1);
        v5 = (char *)v24;
      }
      *(_QWORD *)v4 = *(_QWORD *)&v5[8 * v7];
    }
    v4 += 8;
    *((_QWORD *)&v24 + 1) = v4;
    ++v3;
  }
  while ( v3 < v23 );
  if ( (unsigned __int8)IsGetHrtfMinFrameCountPresent(8, qword_18001FA60) )
  {
    v27 = 0;
    if ( (int)TryGetCustomModelPaths(&lpSubKey, &v27, &v23) >= 0 )
    {
      v9 = 0;
      if ( v23 )
      {
        do
        {
          v10 = (char *)&v27[v9];
          if ( v10 >= v4 || v5 > v10 )
          {
            if ( v4 == v2 )
            {
              std::vector<wchar_t const *>::_Reserve(&v24, v8);
              v2 = v25;
              v4 = (char *)*((_QWORD *)&v24 + 1);
              v5 = (char *)v24;
            }
            v12 = *(_QWORD *)v10;
          }
          else
          {
            v11 = (v10 - v5) >> 3;
            if ( v4 == v2 )
            {
              std::vector<wchar_t const *>::_Reserve(&v24, v8);
              v2 = v25;
              v4 = (char *)*((_QWORD *)&v24 + 1);
              v5 = (char *)v24;
            }
            v12 = *(_QWORD *)&v5[8 * v11];
          }
          *(_QWORD *)v4 = v12;
          v4 += 8;
          *((_QWORD *)&v24 + 1) = v4;
          ++v9;
        }
        while ( v9 < v23 );
      }
    }
  }
  v13 = operator new(0x58u);
  v14 = (__int64)v13;
  v27 = v13;
  if ( v13 )
  {
    *(_DWORD *)v13 = LODWORD(FInf._Float) ^ _xmm;
    v13[1] = 0;
    v13[2] = 0;
    v13[3] = 0;
    v13[4] = 0;
    v13[5] = 0;
    v13[6] = 0;
    v13[7] = 0;
    v13[8] = 0;
    v13[9] = 0;
    *((_BYTE *)v13 + 80) = 0;
    std::vector<HrtfDataDesc>::resize(v13 + 7, (v4 - v5) >> 3);
  }
  else
  {
    v14 = 0;
  }
  v27 = (_QWORD *)v14;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey) )
  {
    v15 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v15);
      SetLastError(LastError);
    }
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20219u, &hKey) )
    {
      v17 = 0;
    }
    else
    {
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
    }
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE1,
        (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\spatialsounddatamanager.cpp",
        (const char *)(unsigned int)v17,
        phkResult);
  }
  v30[0] = &hKey;
  v30[1] = this;
  lambda_7cd2be893801233c536126fec0c0929b_::operator()(v30, (const WCHAR *)&qword_18001FB60, v14);
  v18 = 0;
  v19 = (v4 - v5) >> 3;
  if ( v19 )
  {
    do
    {
      v20 = *(_QWORD *)(v14 + 56) + 56LL * v18;
      std::wstring::wstring(v31, *(void **)&v5[8 * v18]);
      lambda_7cd2be893801233c536126fec0c0929b_::operator()(v30, (const WCHAR *)v31, v20);
      if ( v31[3] >= (void *)8 )
        operator delete(v31[0]);
      ++v18;
    }
    while ( v18 < v19 );
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    operator delete(v5);
  return (struct HrtfPersonalizationParams *)v14;
}

```

## disassembly

```asm
0x180005b40  push    rbp
0x180005b42  push    rbx
0x180005b43  push    rsi
0x180005b44  push    rdi
0x180005b45  push    r12
0x180005b47  push    r13
0x180005b49  push    r14
0x180005b4b  push    r15
0x180005b4d  lea     rbp, [rsp-1Fh]
0x180005b52  sub     rsp, 0B8h
0x180005b59  mov     rax, cs:__security_cookie
0x180005b60  xor     rax, rsp
0x180005b63  mov     [rbp+57h+var_50], rax
0x180005b67  mov     r12, rcx
0x180005b6a  xorps   xmm0, xmm0
0x180005b6d  movdqu  [rbp+57h+var_B8], xmm0
0x180005b72  xor     r13d, r13d
0x180005b75  mov     r14d, r13d
0x180005b78  mov     [rbp+57h+var_A8], r13
0x180005b7c  lea     rax, SubKey; "Software\\Microsoft\\Multimedia\\Audio"...
0x180005b83  mov     [rbp+57h+lpSubKey], rax
0x180005b87  lea     ecx, [r13+8]
0x180005b8b  mov     [rbp+57h+var_C0], cx
0x180005b8f  mov     r15d, r13d
0x180005b92  lea     rdx, qword_18001FA60
0x180005b99  mov     rdi, qword ptr [rbp+57h+var_B8+8]
0x180005b9d  mov     rsi, qword ptr [rbp+57h+var_B8]
0x180005ba1  movsxd  rax, r15d
0x180005ba4  shl     rax, 5
0x180005ba8  lea     rbx, [rax+rdx]
0x180005bac  cmp     [rax+rdx+18h], rcx
0x180005bb1  jb      short loc_180005BB6
0x180005bb3  mov     rbx, [rbx]
0x180005bb6  mov     [rbp+57h+var_90], rbx
0x180005bba  lea     rax, [rbp+57h+var_90]
0x180005bbe  cmp     rax, rdi
0x180005bc1  jnb     short loc_180005C06
0x180005bc3  lea     rax, [rbp+57h+var_90]
0x180005bc7  cmp     rsi, rax
0x180005bca  ja      short loc_180005C06
0x180005bcc  lea     rbx, [rbp+57h+var_90]
0x180005bd0  sub     rbx, rsi
0x180005bd3  sar     rbx, 3
0x180005bd7  cmp     rdi, r14
0x180005bda  jnz     short loc_180005BFD
0x180005bdc  lea     rcx, [rbp+57h+var_B8]
0x180005be0  call    ?_Reserve@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@IEAAX_K@Z; std::vector<wchar_t const *>::_Reserve(unsigned __int64)
0x180005be5  mov     r14, [rbp+57h+var_A8]
0x180005be9  mov     rdi, qword ptr [rbp+57h+var_B8+8]
0x180005bed  mov     rsi, qword ptr [rbp+57h+var_B8]
0x180005bf1  mov     ecx, 8
0x180005bf6  lea     rdx, qword_18001FA60
0x180005bfd  mov     rax, [rsi+rbx*8]
0x180005c01  mov     [rdi], rax
0x180005c04  jmp     short loc_180005C2F
0x180005c06  cmp     rdi, r14
0x180005c09  jnz     short loc_180005C2C
0x180005c0b  lea     rcx, [rbp+57h+var_B8]
0x180005c0f  call    ?_Reserve@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@IEAAX_K@Z; std::vector<wchar_t const *>::_Reserve(unsigned __int64)
0x180005c14  mov     r14, [rbp+57h+var_A8]
0x180005c18  mov     rdi, qword ptr [rbp+57h+var_B8+8]
0x180005c1c  mov     rsi, qword ptr [rbp+57h+var_B8]
0x180005c20  mov     ecx, 8
0x180005c25  lea     rdx, qword_18001FA60
0x180005c2c  mov     [rdi], rbx
0x180005c2f  add     rdi, rcx
0x180005c32  mov     qword ptr [rbp+57h+var_B8+8], rdi
0x180005c36  inc     r15d
0x180005c39  movzx   eax, [rbp+57h+var_C0]
0x180005c3d  cmp     r15d, eax
0x180005c40  jl      loc_180005BA1
0x180005c46  call    IsGetHrtfMinFrameCountPresent
0x180005c4b  test    al, al
0x180005c4d  jz      loc_180005CE7
0x180005c53  mov     [rbp+57h+var_98], r13
0x180005c57  lea     r8, [rbp+57h+var_C0]
0x180005c5b  lea     rdx, [rbp+57h+var_98]
0x180005c5f  lea     rcx, [rbp+57h+lpSubKey]
0x180005c63  call    cs:__imp_TryGetCustomModelPaths
0x180005c69  test    eax, eax
0x180005c6b  js      short loc_180005CE7
0x180005c6d  mov     r15d, r13d
0x180005c70  cmp     r13w, [rbp+57h+var_C0]
0x180005c75  jnb     short loc_180005CE7
0x180005c77  movsxd  rcx, r15d
0x180005c7a  mov     rax, [rbp+57h+var_98]
0x180005c7e  lea     rbx, [rax+rcx*8]
0x180005c82  cmp     rbx, rdi
0x180005c85  jnb     short loc_180005CB3
0x180005c87  cmp     rsi, rbx
0x180005c8a  ja      short loc_180005CB3
0x180005c8c  sub     rbx, rsi
0x180005c8f  sar     rbx, 3
0x180005c93  cmp     rdi, r14
0x180005c96  jnz     short loc_180005CAD
0x180005c98  lea     rcx, [rbp+57h+var_B8]
0x180005c9c  call    ?_Reserve@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@IEAAX_K@Z; std::vector<wchar_t const *>::_Reserve(unsigned __int64)
0x180005ca1  mov     r14, [rbp+57h+var_A8]
0x180005ca5  mov     rdi, qword ptr [rbp+57h+var_B8+8]
0x180005ca9  mov     rsi, qword ptr [rbp+57h+var_B8]
0x180005cad  mov     rax, [rsi+rbx*8]
0x180005cb1  jmp     short loc_180005CD0
0x180005cb3  cmp     rdi, r14
0x180005cb6  jnz     short loc_180005CCD
0x180005cb8  lea     rcx, [rbp+57h+var_B8]
0x180005cbc  call    ?_Reserve@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@IEAAX_K@Z; std::vector<wchar_t const *>::_Reserve(unsigned __int64)
0x180005cc1  mov     r14, [rbp+57h+var_A8]
0x180005cc5  mov     rdi, qword ptr [rbp+57h+var_B8+8]
0x180005cc9  mov     rsi, qword ptr [rbp+57h+var_B8]
0x180005ccd  mov     rax, [rbx]
0x180005cd0  mov     [rdi], rax
0x180005cd3  add     rdi, 8
0x180005cd7  mov     qword ptr [rbp+57h+var_B8+8], rdi
0x180005cdb  inc     r15d
0x180005cde  movzx   eax, [rbp+57h+var_C0]
0x180005ce2  cmp     r15d, eax
0x180005ce5  jl      short loc_180005C77
0x180005ce7  mov     ecx, 58h ; 'X'; Size
0x180005cec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005cf1  mov     r14, rax
0x180005cf4  mov     [rbp+57h+var_98], rax
0x180005cf8  test    rax, rax
0x180005cfb  jz      short loc_180005D4D
0x180005cfd  mov     rdx, rdi
0x180005d00  sub     rdx, rsi
0x180005d03  sar     rdx, 3
0x180005d07  movss   xmm0, dword ptr cs:_FInf
0x180005d0f  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180005d16  movss   dword ptr [rax], xmm0
0x180005d1a  mov     [rax+8], r13
0x180005d1e  mov     [rax+10h], r13
0x180005d22  mov     [rax+18h], r13
0x180005d26  mov     [rax+20h], r13
0x180005d2a  mov     [rax+28h], r13
0x180005d2e  mov     [rax+30h], r13
0x180005d32  lea     rcx, [rax+38h]
0x180005d36  mov     [rcx], r13
0x180005d39  mov     [rcx+8], r13
0x180005d3d  mov     [rcx+10h], r13
0x180005d41  mov     [rax+50h], r13b
0x180005d45  call    ?resize@?$vector@UHrtfDataDesc@@V?$allocator@UHrtfDataDesc@@@std@@@std@@QEAAX_K@Z; std::vector<HrtfDataDesc>::resize(unsigned __int64)
0x180005d4a  nop
0x180005d4b  jmp     short loc_180005D50
0x180005d4d  mov     r14, r13
0x180005d50  mov     [rbp+57h+var_98], r14
0x180005d54  mov     [rbp+57h+hKey], r13
0x180005d58  lea     rax, [rbp+57h+hKey]
0x180005d5c  mov     qword ptr [rsp+0F0h+phkResult], rax; phkResult
0x180005d61  mov     r9d, 20119h; samDesired
0x180005d67  xor     r8d, r8d; ulOptions
0x180005d6a  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180005d6e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005d75  call    cs:__imp_RegOpenKeyExW
0x180005d7b  test    eax, eax
0x180005d7d  jz      short loc_180005DEF
0x180005d7f  mov     r15, [rbp+57h+hKey]
0x180005d83  test    r15, r15
0x180005d86  jz      short loc_180005DA1
0x180005d88  call    cs:__imp_GetLastError
0x180005d8e  mov     ebx, eax
0x180005d90  mov     rcx, r15; hKey
0x180005d93  call    cs:__imp_RegCloseKey
0x180005d99  mov     ecx, ebx; dwErrCode
0x180005d9b  call    cs:__imp_SetLastError
0x180005da1  mov     [rbp+57h+hKey], r13
0x180005da5  lea     rax, [rbp+57h+hKey]
0x180005da9  mov     qword ptr [rsp+0F0h+phkResult], rax; int
0x180005dae  mov     r9d, 20219h; samDesired
0x180005db4  xor     r8d, r8d; ulOptions
0x180005db7  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180005dbb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005dc2  call    cs:__imp_RegOpenKeyExW
0x180005dc8  test    eax, eax
0x180005dca  jnz     short loc_180005DE0
0x180005dcc  call    cs:__imp_GetLastError
0x180005dd2  test    eax, eax
0x180005dd4  jle     short loc_180005DE3
0x180005dd6  movzx   eax, ax
0x180005dd9  or      eax, 80070000h
0x180005dde  jmp     short loc_180005DE3
0x180005de0  mov     eax, r13d
0x180005de3  mov     rcx, [rbp+5Fh]; this
0x180005de7  test    eax, eax
0x180005de9  js      loc_180005EA4
0x180005def  lea     rax, [rbp+57h+hKey]
0x180005df3  mov     [rbp+57h+var_80], rax
0x180005df7  mov     [rbp+57h+var_78], r12
0x180005dfb  mov     r8, r14
0x180005dfe  lea     rdx, qword_18001FB60
0x180005e05  lea     rcx, [rbp+57h+var_80]
0x180005e09  call    _lambda_7cd2be893801233c536126fec0c0929b___operator__
0x180005e0e  mov     r15d, r13d
0x180005e11  sub     rdi, rsi
0x180005e14  sar     rdi, 3
0x180005e18  test    rdi, rdi
0x180005e1b  jz      short loc_180005E63
0x180005e1d  mov     edx, r15d
0x180005e20  imul    rbx, rdx, 38h ; '8'
0x180005e24  add     rbx, [r14+38h]
0x180005e28  mov     rdx, [rsi+rdx*8]; Src
0x180005e2c  lea     rcx, [rbp+57h+var_70]; void *
0x180005e30  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180005e35  nop
0x180005e36  mov     r8, rbx
0x180005e39  lea     rdx, [rbp+57h+var_70]
0x180005e3d  lea     rcx, [rbp+57h+var_80]
0x180005e41  call    _lambda_7cd2be893801233c536126fec0c0929b___operator__
0x180005e46  nop
0x180005e47  cmp     [rbp+57h+var_58], 8
0x180005e4c  jb      short loc_180005E58
0x180005e4e  mov     rcx, [rbp+57h+var_70]
0x180005e52  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005e58  inc     r15d
0x180005e5b  mov     eax, r15d
0x180005e5e  cmp     rax, rdi
0x180005e61  jb      short loc_180005E1D
0x180005e63  mov     rcx, [rbp+57h+hKey]; hKey
0x180005e67  test    rcx, rcx
0x180005e6a  jz      short loc_180005E73
0x180005e6c  call    cs:__imp_RegCloseKey
0x180005e72  nop
0x180005e73  test    rsi, rsi
0x180005e76  jz      short loc_180005E81
0x180005e78  mov     rcx, rsi
0x180005e7b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005e81  mov     rax, r14
0x180005e84  mov     rcx, [rbp+57h+var_50]
0x180005e88  xor     rcx, rsp; StackCookie
0x180005e8b  call    __security_check_cookie
0x180005e90  add     rsp, 0B8h
0x180005e97  pop     r15
0x180005e99  pop     r14
0x180005e9b  pop     r13
0x180005e9d  pop     r12
0x180005e9f  pop     rdi
0x180005ea0  pop     rsi
0x180005ea1  pop     rbx
0x180005ea2  pop     rbp
0x180005ea3  retn
0x180005ea4  mov     r9d, eax; char *
0x180005ea7  lea     r8, aAvcoreXaudioHr_3; "avcore\\xaudio\\hrtf\\ssdm\\lib\\spatia"...
0x180005eae  mov     edx, 0E1h; void *
0x180005eb3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
