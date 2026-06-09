# CRegSetting::Load(HKEY__ *,ulong)

- ea: `0x140008220`
- end: `0x1400084ec`
- name: `?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z`
- size: `716`
- prototype: `int(CRegSetting *__hidden this, HKEY, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1400084f4`
- `0x14000964c`
- `0x14000e49c`

## callees

- `0x140002fbc`
- `0x140003224`
- `0x14000470c`
- `0x140008220`
- `0x14000b280`
- `0x14000e098`
- `0x14001c9a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008301`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400083e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008301`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400083e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400084d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400084d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400082c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400082c9`

## pseudocode

```c
__int64 __fastcall CRegSetting::Load(CRegSetting *this, HKEY a2, int a3)
{
  HKEY v4; // r14
  HKEY *phkResult; // rax
  int v8; // ebx
  __int64 v9; // r8
  DWORD v10; // eax
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // edx
  LPBYTE *v14; // rdi
  unsigned __int64 v15; // r15
  LPBYTE v16; // rax
  unsigned __int64 v17; // rbx
  bool v18; // zf
  __int64 v19; // r8
  __int64 v20; // r9
  LPBYTE v21; // rax
  __int64 v22; // rbx
  unsigned __int64 v23; // r14
  __int64 v24; // r8
  __int64 v25; // r9
  void *v26; // r14
  LPBYTE v27; // rax
  size_t v28; // rbx
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  void *Src; // [rsp+38h] [rbp-28h]
  char *v31; // [rsp+40h] [rbp-20h]
  _WORD v32[12]; // [rsp+48h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  Src = v32;
  Type = 0;
  v31 = (char *)v32;
  v4 = a2;
  cbData = 0;
  v32[0] = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 9) )
    return 2149285891LL;
  if ( !*((_BYTE *)this + 1) || *(_BYTE *)this )
    goto LABEL_45;
  if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
  {
LABEL_11:
    if ( RegQueryValueExW(v4, *((LPCWSTR *)this + 8), 0, &Type, 0, &cbData) )
      goto LABEL_9;
    v10 = cbData;
    if ( Type - 1 <= 1 )
    {
      v10 = cbData + 1;
    }
    else
    {
      if ( Type != 7 )
        goto LABEL_17;
      v10 = cbData + 2;
    }
    cbData = v10;
LABEL_17:
    v11 = 0;
    while ( CRegSetting::s_typeMapping[2 * v11 + 1] != Type )
    {
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= 0xB )
      {
        v12 = 9;
        goto LABEL_22;
      }
    }
    v12 = CRegSetting::s_typeMapping[2 * v11];
LABEL_22:
    v13 = *((_DWORD *)this + 1);
    if ( v13 != v12 && v13 != 9 && (v13 != 5 || v12 != 1) && (v13 != 1 || v12 != 5) && (v13 || v12 != 1) )
      goto LABEL_9;
    v14 = (LPBYTE *)((char *)this + 8);
    *((_DWORD *)this + 1) = v12;
    v15 = v10;
    v16 = (LPBYTE)*((_QWORD *)this + 1);
    v17 = *((_QWORD *)this + 2) - (_QWORD)v16;
    if ( v15 > v17 )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               (unsigned int)v15,
                               v9,
                               CRegSetting::s_typeMapping) )
      {
LABEL_32:
        v8 = -2147024882;
        goto LABEL_46;
      }
      memset_0(*((void **)this + 2), 0, v15 - v17);
      v16 = *v14;
    }
    *((_QWORD *)this + 2) = &v16[v15];
    v18 = RegQueryValueExW(v4, *((LPCWSTR *)this + 8), 0, &Type, *v14, &cbData) == 0;
    v21 = *v14;
    if ( !v18 )
    {
      v8 = -2147467259;
      *((_QWORD *)this + 2) = v21;
      goto LABEL_46;
    }
    v22 = cbData;
    v23 = *((_QWORD *)this + 2) - (_QWORD)v21;
    if ( cbData > v23 )
    {
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                              (char *)this + 8,
                              cbData,
                              v19,
                              v20) )
      {
        memset_0(*((void **)this + 2), 0, v22 - v23);
        *((_QWORD *)this + 2) = &(*v14)[v22];
      }
    }
    else
    {
      *((_QWORD *)this + 2) = &v21[cbData];
    }
    if ( *((_DWORD *)this + 1) == 5 )
    {
      v8 = UtilExpandEnvironmentStrings((LPCWSTR)*v14);
      if ( v8 < 0 )
        goto LABEL_46;
      v26 = Src;
      v27 = *v14;
      cbData = 2 * ((v31 - (_BYTE *)Src) >> 1) + 2;
      v28 = cbData;
      *((_QWORD *)this + 2) = v27;
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               v28,
                               v24,
                               v25) )
        goto LABEL_32;
      memcpy_0(*((void **)this + 2), v26, v28);
      *((_QWORD *)this + 2) += v28;
    }
    *(_BYTE *)this = 1;
LABEL_45:
    v8 = 0;
    goto LABEL_46;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( !RegOpenKeyExW(v4, *((LPCWSTR *)this + 4), 0, a3 | 0x20019, phkResult) )
  {
    v4 = hKey;
    goto LABEL_11;
  }
LABEL_9:
  v8 = -2147467259;
LABEL_46:
  if ( Src != v32 )
    operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140008220  mov     [rsp-28h+arg_0], rbx
0x140008225  push    rbp
0x140008226  push    rsi
0x140008227  push    rdi
0x140008228  push    r14
0x14000822a  push    r15
0x14000822c  mov     rbp, rsp
0x14000822f  sub     rsp, 60h
0x140008233  lea     rax, [rbp+var_18]
0x140008237  mov     [rbp+hKey], 0
0x14000823f  mov     [rbp+Src], rax
0x140008243  mov     ebx, r8d
0x140008246  lea     rax, [rbp+var_18]
0x14000824a  mov     [rbp+Type], 0
0x140008251  mov     [rbp+var_20], rax
0x140008255  mov     r14, rdx
0x140008258  xor     eax, eax
0x14000825a  mov     [rbp+cbData], 0
0x140008261  mov     [rbp+var_18], ax
0x140008265  mov     rsi, rcx
0x140008268  test    rdx, rdx
0x14000826b  jnz     short loc_140008277
0x14000826d  mov     eax, 80070057h
0x140008272  jmp     loc_1400084D8
0x140008277  mov     rax, [rcx+48h]
0x14000827b  cmp     [rcx+40h], rax
0x14000827f  jnz     short loc_14000828B
0x140008281  mov     eax, 801B8003h
0x140008286  jmp     loc_1400084D8
0x14000828b  cmp     byte ptr [rcx+1], 0
0x14000828f  jz      loc_1400084AC
0x140008295  cmp     byte ptr [rcx], 0
0x140008298  jnz     loc_1400084AC
0x14000829e  mov     rax, [rcx+28h]
0x1400082a2  cmp     [rcx+20h], rax
0x1400082a6  jz      short loc_1400082E1
0x1400082a8  lea     rcx, [rbp+hKey]
0x1400082ac  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400082b1  mov     rdx, [rsi+20h]; lpSubKey
0x1400082b5  or      ebx, 20019h
0x1400082bb  mov     r9d, ebx; samDesired
0x1400082be  mov     [rsp+60h+phkResult], rax; phkResult
0x1400082c3  xor     r8d, r8d; ulOptions
0x1400082c6  mov     rcx, r14; hKey
0x1400082c9  call    cs:__imp_RegOpenKeyExW
0x1400082cf  test    eax, eax
0x1400082d1  jz      short loc_1400082DD
0x1400082d3  mov     ebx, 80004005h
0x1400082d8  jmp     loc_1400084AE
0x1400082dd  mov     r14, [rbp+hKey]
0x1400082e1  mov     rdx, [rsi+40h]; lpValueName
0x1400082e5  lea     rax, [rbp+cbData]
0x1400082e9  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1400082ee  lea     r9, [rbp+Type]; lpType
0x1400082f2  xor     r8d, r8d; lpReserved
0x1400082f5  mov     [rsp+60h+phkResult], 0; lpData
0x1400082fe  mov     rcx, r14; hKey
0x140008301  call    cs:__imp_RegQueryValueExW
0x140008307  test    eax, eax
0x140008309  jnz     short loc_1400082D3
0x14000830b  mov     edx, [rbp+Type]
0x14000830e  lea     eax, [rdx-1]
0x140008311  cmp     eax, 1
0x140008314  mov     eax, [rbp+cbData]
0x140008317  jbe     short loc_140008323
0x140008319  cmp     edx, 7
0x14000831c  jnz     short loc_140008328
0x14000831e  add     eax, 2
0x140008321  jmp     short loc_140008325
0x140008323  inc     eax
0x140008325  mov     [rbp+cbData], eax
0x140008328  xor     ecx, ecx
0x14000832a  lea     r9, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x140008331  cmp     [r9+rcx*8+4], edx
0x140008336  jz      short loc_140008346
0x140008338  inc     ecx
0x14000833a  cmp     ecx, 0Bh
0x14000833d  jb      short loc_140008331
0x14000833f  mov     ecx, 9
0x140008344  jmp     short loc_14000834A
0x140008346  mov     ecx, [r9+rcx*8]
0x14000834a  mov     edx, [rsi+4]
0x14000834d  cmp     edx, ecx
0x14000834f  jz      short loc_14000837B
0x140008351  cmp     edx, 9
0x140008354  jz      short loc_14000837B
0x140008356  cmp     edx, 5
0x140008359  jnz     short loc_140008360
0x14000835b  cmp     ecx, 1
0x14000835e  jz      short loc_14000837B
0x140008360  cmp     edx, 1
0x140008363  jnz     short loc_14000836A
0x140008365  cmp     ecx, 5
0x140008368  jz      short loc_14000837B
0x14000836a  test    edx, edx
0x14000836c  jnz     loc_1400082D3
0x140008372  cmp     ecx, 1
0x140008375  jnz     loc_1400082D3
0x14000837b  lea     rdi, [rsi+8]
0x14000837f  mov     [rsi+4], ecx
0x140008382  mov     rbx, [rdi+8]
0x140008386  mov     r15d, eax
0x140008389  mov     rax, [rdi]
0x14000838c  sub     rbx, rax
0x14000838f  cmp     r15, rbx
0x140008392  jbe     short loc_1400083C1
0x140008394  mov     edx, r15d
0x140008397  mov     rcx, rdi
0x14000839a  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x14000839f  test    al, al
0x1400083a1  jnz     short loc_1400083AD
0x1400083a3  mov     ebx, 8007000Eh
0x1400083a8  jmp     loc_1400084AE
0x1400083ad  mov     rcx, [rdi+8]; void *
0x1400083b1  mov     r8, r15
0x1400083b4  sub     r8, rbx; Size
0x1400083b7  xor     edx, edx; Val
0x1400083b9  call    memset_0
0x1400083be  mov     rax, [rdi]
0x1400083c1  add     rax, r15
0x1400083c4  lea     r9, [rbp+Type]; lpType
0x1400083c8  mov     [rdi+8], rax
0x1400083cc  xor     r8d, r8d; lpReserved
0x1400083cf  mov     rdx, [rsi+40h]; lpValueName
0x1400083d3  lea     rax, [rbp+cbData]
0x1400083d7  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1400083dc  mov     rcx, r14; hKey
0x1400083df  mov     rax, [rdi]
0x1400083e2  mov     [rsp+60h+phkResult], rax; lpData
0x1400083e7  call    cs:__imp_RegQueryValueExW
0x1400083ed  test    eax, eax
0x1400083ef  mov     rax, [rdi]
0x1400083f2  jz      short loc_140008402
0x1400083f4  mov     ebx, 80004005h
0x1400083f9  mov     [rdi+8], rax
0x1400083fd  jmp     loc_1400084AE
0x140008402  mov     r14, [rdi+8]
0x140008406  mov     ebx, [rbp+cbData]
0x140008409  sub     r14, rax
0x14000840c  cmp     rbx, r14
0x14000840f  ja      short loc_14000841A
0x140008411  add     rax, rbx
0x140008414  mov     [rdi+8], rax
0x140008418  jmp     short loc_140008444
0x14000841a  mov     rdx, rbx
0x14000841d  mov     rcx, rdi
0x140008420  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x140008425  test    al, al
0x140008427  jz      short loc_140008444
0x140008429  mov     rcx, [rdi+8]; void *
0x14000842d  mov     r8, rbx
0x140008430  sub     r8, r14; Size
0x140008433  xor     edx, edx; Val
0x140008435  call    memset_0
0x14000843a  mov     rcx, [rdi]
0x14000843d  add     rcx, rbx
0x140008440  mov     [rdi+8], rcx
0x140008444  cmp     dword ptr [rsi+4], 5
0x140008448  jnz     short loc_1400084A9
0x14000844a  mov     rcx, [rdi]; lpSrc
0x14000844d  lea     rdx, [rbp+Src]
0x140008451  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140008456  mov     ebx, eax
0x140008458  test    eax, eax
0x14000845a  js      short loc_1400084AE
0x14000845c  mov     r14, [rbp+Src]
0x140008460  mov     rax, [rbp+var_20]
0x140008464  sub     rax, r14
0x140008467  sar     rax, 1
0x14000846a  lea     ecx, ds:2[rax*2]
0x140008471  mov     rax, [rdi]
0x140008474  mov     ebx, ecx
0x140008476  mov     [rbp+cbData], ecx
0x140008479  sub     rbx, r14
0x14000847c  add     rbx, r14
0x14000847f  mov     [rdi+8], rax
0x140008483  mov     rdx, rbx
0x140008486  mov     rcx, rdi
0x140008489  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x14000848e  test    al, al
0x140008490  jz      loc_1400083A3
0x140008496  mov     rcx, [rdi+8]; void *
0x14000849a  mov     r8, rbx; Size
0x14000849d  mov     rdx, r14; Src
0x1400084a0  call    memcpy_0
0x1400084a5  add     [rdi+8], rbx
0x1400084a9  mov     byte ptr [rsi], 1
0x1400084ac  xor     ebx, ebx
0x1400084ae  mov     rcx, [rbp+Src]; void *
0x1400084b2  lea     rax, [rbp+var_18]
0x1400084b6  cmp     rcx, rax
0x1400084b9  jz      short loc_1400084C7
0x1400084bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400084c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400084c7  mov     rcx, [rbp+hKey]; hKey
0x1400084cb  test    rcx, rcx
0x1400084ce  jz      short loc_1400084D6
0x1400084d0  call    cs:__imp_RegCloseKey
0x1400084d6  mov     eax, ebx
0x1400084d8  mov     rbx, [rsp+60h+arg_0]
0x1400084e0  add     rsp, 60h
0x1400084e4  pop     r15
0x1400084e6  pop     r14
0x1400084e8  pop     rdi
0x1400084e9  pop     rsi
0x1400084ea  pop     rbp
0x1400084eb  retn
```
