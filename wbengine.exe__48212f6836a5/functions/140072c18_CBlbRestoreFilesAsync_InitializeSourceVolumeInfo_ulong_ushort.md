# CBlbRestoreFilesAsync::InitializeSourceVolumeInfo(ulong,ushort * *)

- ea: `0x140072c18`
- end: `0x140073062`
- name: `?InitializeSourceVolumeInfo@CBlbRestoreFilesAsync@@AEAAJKPEAPEAG@Z`
- size: `1098`
- prototype: `__int64 __fastcall(CBlbRestoreFilesAsync *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140071b24`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x140014200`
- `0x1400142d8`
- `0x140072c18`
- `0x1400889f0`
- `0x14008ba2c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140072d1f`
- `msvcrt!_wcsnicmp` at `0x140072ea7`
- `msvcrt!_wcsnicmp` at `0x140072f86`
- `msvcrt!_wcsnicmp` at `0x140072d1f`
- `msvcrt!_wcsnicmp` at `0x140072ea7`
- `msvcrt!_wcsnicmp` at `0x140072f86`
- `ole32!CoTaskMemFree` at `0x140072d94`
- `ole32!CoTaskMemFree` at `0x140072e22`
- `ole32!CoTaskMemFree` at `0x140072fff`
- `ole32!CoTaskMemFree` at `0x14007300d`
- `ole32!CoTaskMemFree` at `0x140072d94`
- `ole32!CoTaskMemFree` at `0x140072e22`
- `ole32!CoTaskMemFree` at `0x140072fff`
- `ole32!CoTaskMemFree` at `0x14007300d`

## string_xrefs

- `0x140072c47`: `base\stor\blb\engine\service\restorefiles.cpp`
- `0x140072d4a`: `base\stor\blb\engine\service\restorefiles.cpp`
- `0x140072e83`: `base\stor\blb\engine\service\restorefiles.cpp`
- `0x140072ed7`: `base\stor\blb\engine\service\restorefiles.cpp`
- `0x140072f54`: `base\stor\blb\engine\service\restorefiles.cpp`
- `0x140072c3b`: `rgwszSourcePath != NULL`
- `0x140072d3e`: `wszVolumePath != NULL`
- `0x140072ecb`: `wszVolumePath == NULL`
- `0x140072f48`: `wszVolumePath`

## pseudocode

```c
__int64 __fastcall CBlbRestoreFilesAsync::InitializeSourceVolumeInfo(
        CBlbRestoreFilesAsync *this,
        unsigned int a2,
        const wchar_t **a3)
{
  PVOID *v5; // rcx
  unsigned int v6; // r12d
  const wchar_t *v7; // r13
  void *v8; // rbx
  int v9; // r14d
  wchar_t *v10; // rdi
  unsigned int i; // r15d
  __int64 v12; // rsi
  const wchar_t *v13; // rdx
  size_t v14; // r8
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // r8
  unsigned int v21; // r15d
  unsigned int j; // esi
  size_t v23; // r8
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v26; // [rsp+78h] [rbp+10h]
  wchar_t *String2; // [rsp+80h] [rbp+18h] BYREF

  v26 = a2;
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x160u, "rgwszSourcePath != NULL");
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = *((_DWORD *)this + 96);
  v7 = *a3;
  v8 = 0;
  pv = 0;
  v9 = 0;
  v10 = 0;
  String2 = 0;
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
  {
    WPP_SF_S(v5[2], 23, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids, v7);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  for ( i = 0; i < *((_DWORD *)this + 96); ++i )
  {
    v12 = *((_QWORD *)this + 49) + 120LL * i;
    v13 = *(const wchar_t **)(v12 + 24);
    if ( !v13 )
      goto LABEL_32;
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    if ( _wcsnicmp(v7, v13, v14) )
    {
LABEL_32:
      if ( v10 )
      {
        CoTaskMemFree(v10);
        String2 = 0;
      }
      v18 = BlbutilQueryVolumeName((struct _GUID *)v12, *(_DWORD *)(v12 + 16), &String2, 0);
      v10 = String2;
      v9 = v18;
      if ( v18 < 0 )
        goto LABEL_65;
      v19 = -1;
      do
        ++v19;
      while ( String2[v19] );
      if ( String2[v19 - 1] != 92 )
        BlbAssert(
          "base\\stor\\blb\\engine\\service\\restorefiles.cpp",
          0x1B0u,
          "wszCatalogVolumeName[wcslen(wszCatalogVolumeName) - 1] == '\\\\'");
      v20 = -1;
      do
        ++v20;
      while ( v10[v20] );
      if ( !_wcsnicmp(v7, v10, v20 - 1) )
      {
        v6 = i;
        if ( v8 )
          BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x1B6u, "wszVolumePath == NULL");
        v5 = (PVOID *)WPP_GLOBAL_Control;
        v8 = v10;
        v10 = 0;
        break;
      }
      goto LABEL_42;
    }
    if ( v6 == *((_DWORD *)this + 96) )
      goto LABEL_26;
    if ( !v8 )
      BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x186u, "wszVolumePath != NULL");
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(*(_QWORD *)(120LL * v6 + *((_QWORD *)this + 49) + 24) + 2 * v15) );
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(*(_QWORD *)(v12 + 24) + 2 * v16) );
    if ( v16 > v15 )
    {
      CoTaskMemFree(v8);
      pv = 0;
LABEL_26:
      v17 = BlbutilDuplicateString(*(const unsigned __int16 **)(v12 + 24), (unsigned __int16 **)&pv, 0);
      v8 = pv;
      v9 = v17;
      if ( v17 < 0 )
        goto LABEL_65;
      v6 = i;
LABEL_42:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      continue;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids, v8);
      goto LABEL_42;
    }
  }
  if ( v6 == *((_DWORD *)this + 96) )
  {
    v9 = -2139619263;
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 2u )
      WPP_SF_S(v5[2], 25, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids, v7);
  }
  else
  {
    if ( !v8 )
      BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x1C7u, "wszVolumePath");
    v21 = v26;
    for ( j = 1; j < v21; ++j )
    {
      v23 = -1;
      do
        ++v23;
      while ( *((_WORD *)v8 + v23) );
      if ( _wcsnicmp(v7, (const wchar_t *)v8, v23) )
      {
        v9 = -2139619240;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids,
            (_DWORD)v7,
            (__int64)v8);
        }
        goto LABEL_65;
      }
    }
    *((_QWORD *)this + 34) = v8;
    *((_QWORD *)this + 66) = *((_QWORD *)this + 49) + 120LL * v6;
    if ( v9 >= 0 )
      goto LABEL_66;
  }
LABEL_65:
  CoTaskMemFree(v8);
LABEL_66:
  if ( v10 )
    CoTaskMemFree(v10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140072c18  mov     [rsp+arg_18], rbx
0x140072c1d  mov     [rsp+arg_8], edx
0x140072c21  push    rbp
0x140072c22  push    rsi
0x140072c23  push    rdi
0x140072c24  push    r12
0x140072c26  push    r13
0x140072c28  push    r14
0x140072c2a  push    r15
0x140072c2c  sub     rsp, 30h
0x140072c30  mov     rsi, r8
0x140072c33  mov     rbp, rcx
0x140072c36  test    r8, r8
0x140072c39  jnz     short loc_140072C53
0x140072c3b  lea     r8, aRgwszsourcepat; "rgwszSourcePath != NULL"
0x140072c42  mov     edx, 160h; unsigned int
0x140072c47  lea     rcx, aBaseStorBlbEng_38; "base\\stor\\blb\\engine\\service\\resto"...
0x140072c4e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140072c53  mov     rcx, cs:WPP_GLOBAL_Control
0x140072c5a  lea     r15, WPP_GLOBAL_Control
0x140072c61  cmp     rcx, r15
0x140072c64  jz      short loc_140072C8E
0x140072c66  test    byte ptr [rcx+1Ch], 1
0x140072c6a  jz      short loc_140072C8E
0x140072c6c  cmp     byte ptr [rcx+19h], 4
0x140072c70  jb      short loc_140072C8E
0x140072c72  mov     rcx, [rcx+10h]
0x140072c76  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140072c7d  mov     edx, 16h
0x140072c82  call    WPP_SF_
0x140072c87  mov     rcx, cs:WPP_GLOBAL_Control
0x140072c8e  mov     r12d, [rbp+180h]
0x140072c95  xor     r9d, r9d
0x140072c98  mov     r13, [rsi]
0x140072c9b  mov     ebx, r9d
0x140072c9e  mov     [rsp+68h+pv], rbx
0x140072ca3  mov     r14d, r9d
0x140072ca6  mov     edi, r9d
0x140072ca9  mov     [rsp+68h+String2], r9
0x140072cb1  cmp     rcx, r15
0x140072cb4  jz      short loc_140072CE3
0x140072cb6  test    byte ptr [rcx+1Ch], 1
0x140072cba  jz      short loc_140072CE3
0x140072cbc  cmp     byte ptr [rcx+19h], 4
0x140072cc0  jb      short loc_140072CE3
0x140072cc2  mov     rcx, [rcx+10h]
0x140072cc6  lea     edx, [r9+17h]
0x140072cca  mov     r9, r13
0x140072ccd  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140072cd4  call    WPP_SF_S
0x140072cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140072ce0  xor     r9d, r9d
0x140072ce3  mov     r15d, r9d
0x140072ce6  cmp     r15d, [rbp+180h]
0x140072ced  jnb     loc_140072EF3
0x140072cf3  mov     eax, r15d
0x140072cf6  imul    rsi, rax, 78h ; 'x'
0x140072cfa  add     rsi, [rbp+188h]
0x140072d01  mov     rdx, [rsi+18h]; String2
0x140072d05  test    rdx, rdx
0x140072d08  jz      loc_140072E1A
0x140072d0e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140072d12  inc     r8; MaxCount
0x140072d15  cmp     [rdx+r8*2], r9w
0x140072d1a  jnz     short loc_140072D12
0x140072d1c  mov     rcx, r13; String1
0x140072d1f  call    cs:__imp__wcsnicmp
0x140072d25  xor     r9d, r9d
0x140072d28  test    eax, eax
0x140072d2a  jnz     loc_140072E1A
0x140072d30  cmp     r12d, [rbp+180h]
0x140072d37  jz      short loc_140072DA3
0x140072d39  test    rbx, rbx
0x140072d3c  jnz     short loc_140072D59
0x140072d3e  lea     r8, aWszvolumepathN; "wszVolumePath != NULL"
0x140072d45  mov     edx, 186h; unsigned int
0x140072d4a  lea     rcx, aBaseStorBlbEng_38; "base\\stor\\blb\\engine\\service\\resto"...
0x140072d51  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140072d56  xor     r9d, r9d
0x140072d59  mov     eax, r12d
0x140072d5c  imul    rcx, rax, 78h ; 'x'
0x140072d60  mov     rax, [rbp+188h]
0x140072d67  mov     rdx, [rcx+rax+18h]
0x140072d6c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140072d70  inc     rcx
0x140072d73  cmp     [rdx+rcx*2], r9w
0x140072d78  jnz     short loc_140072D70
0x140072d7a  mov     rdx, [rsi+18h]
0x140072d7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140072d82  inc     rax
0x140072d85  cmp     [rdx+rax*2], r9w
0x140072d8a  jnz     short loc_140072D82
0x140072d8c  cmp     rax, rcx
0x140072d8f  jbe     short loc_140072DCF
0x140072d91  mov     rcx, rbx; pv
0x140072d94  call    cs:__imp_CoTaskMemFree
0x140072d9a  mov     [rsp+68h+pv], 0
0x140072da3  mov     rcx, [rsi+18h]; unsigned __int16 *
0x140072da7  lea     rdx, [rsp+68h+pv]; unsigned __int16 **
0x140072dac  xor     r8d, r8d; unsigned __int64
0x140072daf  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140072db4  mov     rbx, [rsp+68h+pv]
0x140072db9  xor     r9d, r9d
0x140072dbc  mov     r14d, eax
0x140072dbf  test    eax, eax
0x140072dc1  js      loc_140072FFC
0x140072dc7  mov     r12d, r15d
0x140072dca  jmp     loc_140072EB4
0x140072dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140072dd6  lea     rax, WPP_GLOBAL_Control
0x140072ddd  cmp     rcx, rax
0x140072de0  jz      loc_140072EBB
0x140072de6  test    byte ptr [rcx+1Ch], 1
0x140072dea  jz      loc_140072EBB
0x140072df0  cmp     byte ptr [rcx+19h], 4
0x140072df4  jb      loc_140072EBB
0x140072dfa  mov     rcx, [rcx+10h]
0x140072dfe  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140072e05  mov     edx, 18h
0x140072e0a  mov     r9, rbx
0x140072e0d  call    WPP_SF_S
0x140072e12  xor     r9d, r9d
0x140072e15  jmp     loc_140072EB4
0x140072e1a  test    rdi, rdi
0x140072e1d  jz      short loc_140072E34
0x140072e1f  mov     rcx, rdi; pv
0x140072e22  call    cs:__imp_CoTaskMemFree
0x140072e28  mov     [rsp+68h+String2], 0
0x140072e34  mov     edx, [rsi+10h]; unsigned int
0x140072e37  lea     r8, [rsp+68h+String2]; unsigned __int16 **
0x140072e3f  xor     r9d, r9d; unsigned __int8
0x140072e42  mov     rcx, rsi; struct _GUID *
0x140072e45  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x140072e4a  mov     rdi, [rsp+68h+String2]
0x140072e52  xor     ecx, ecx
0x140072e54  mov     r14d, eax
0x140072e57  test    eax, eax
0x140072e59  js      loc_140072FFC
0x140072e5f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140072e63  mov     rax, rsi
0x140072e66  inc     rax
0x140072e69  cmp     [rdi+rax*2], cx
0x140072e6d  jnz     short loc_140072E66
0x140072e6f  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x140072e75  jz      short loc_140072E91
0x140072e77  lea     r8, aWszcatalogvolu; "wszCatalogVolumeName[wcslen(wszCatalogV"...
0x140072e7e  mov     edx, 1B0h; unsigned int
0x140072e83  lea     rcx, aBaseStorBlbEng_38; "base\\stor\\blb\\engine\\service\\resto"...
0x140072e8a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140072e8f  xor     ecx, ecx
0x140072e91  mov     r8, rsi
0x140072e94  inc     r8
0x140072e97  cmp     [rdi+r8*2], cx
0x140072e9c  jnz     short loc_140072E94
0x140072e9e  dec     r8; MaxCount
0x140072ea1  mov     rdx, rdi; String2
0x140072ea4  mov     rcx, r13; String1
0x140072ea7  call    cs:__imp__wcsnicmp
0x140072ead  xor     r9d, r9d
0x140072eb0  test    eax, eax
0x140072eb2  jz      short loc_140072EC3
0x140072eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140072ebb  inc     r15d
0x140072ebe  jmp     loc_140072CE6
0x140072ec3  mov     r12d, r15d
0x140072ec6  test    rbx, rbx
0x140072ec9  jz      short loc_140072EE6
0x140072ecb  lea     r8, aWszvolumepathN_0; "wszVolumePath == NULL"
0x140072ed2  mov     edx, 1B6h; unsigned int
0x140072ed7  lea     rcx, aBaseStorBlbEng_38; "base\\stor\\blb\\engine\\service\\resto"...
0x140072ede  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140072ee3  xor     r9d, r9d
0x140072ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x140072eed  mov     rbx, rdi
0x140072ef0  mov     rdi, r9
0x140072ef3  cmp     r12d, [rbp+180h]
0x140072efa  jnz     short loc_140072F43
0x140072efc  mov     r14d, 80780041h
0x140072f02  lea     rax, WPP_GLOBAL_Control
0x140072f09  cmp     rcx, rax
0x140072f0c  jz      loc_140072FFC
0x140072f12  test    byte ptr [rcx+1Ch], 1
0x140072f16  jz      loc_140072FFC
0x140072f1c  cmp     byte ptr [rcx+19h], 2
0x140072f20  jb      loc_140072FFC
0x140072f26  mov     rcx, [rcx+10h]
0x140072f2a  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140072f31  mov     edx, 19h
0x140072f36  mov     r9, r13
0x140072f39  call    WPP_SF_S
0x140072f3e  jmp     loc_140072FFC
0x140072f43  test    rbx, rbx
0x140072f46  jnz     short loc_140072F63
0x140072f48  lea     r8, aWszvolumepath; "wszVolumePath"
0x140072f4f  mov     edx, 1C7h; unsigned int
0x140072f54  lea     rcx, aBaseStorBlbEng_38; "base\\stor\\blb\\engine\\service\\resto"...
0x140072f5b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140072f60  xor     r9d, r9d
0x140072f63  mov     r15d, [rsp+68h+arg_8]
0x140072f68  mov     esi, 1
0x140072f6d  cmp     esi, r15d
0x140072f70  jnb     short loc_140072FDB
0x140072f72  or      r8, 0FFFFFFFFFFFFFFFFh
0x140072f76  inc     r8; MaxCount
0x140072f79  cmp     [rbx+r8*2], r9w
0x140072f7e  jnz     short loc_140072F76
0x140072f80  mov     rdx, rbx; String2
0x140072f83  mov     rcx, r13; String1
0x140072f86  call    cs:__imp__wcsnicmp
0x140072f8c  xor     r9d, r9d
0x140072f8f  test    eax, eax
0x140072f91  jnz     short loc_140072F97
0x140072f93  inc     esi
0x140072f95  jmp     short loc_140072F6D
0x140072f97  mov     r14d, 80780058h
0x140072f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140072fa4  lea     rax, WPP_GLOBAL_Control
0x140072fab  cmp     rcx, rax
0x140072fae  jz      short loc_140072FFC
0x140072fb0  test    byte ptr [rcx+1Ch], 1
0x140072fb4  jz      short loc_140072FFC
0x140072fb6  cmp     byte ptr [rcx+19h], 2
0x140072fba  jb      short loc_140072FFC
0x140072fbc  mov     rcx, [rcx+10h]
0x140072fc0  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140072fc7  mov     edx, 1Ah
0x140072fcc  mov     [rsp+68h+var_48], rbx
0x140072fd1  mov     r9, r13
0x140072fd4  call    WPP_SF_SS
0x140072fd9  jmp     short loc_140072FFC
0x140072fdb  mov     eax, r12d
0x140072fde  imul    rcx, rax, 78h ; 'x'
0x140072fe2  mov     [rbp+110h], rbx
0x140072fe9  add     rcx, [rbp+188h]
0x140072ff0  mov     [rbp+210h], rcx
0x140072ff7  test    r14d, r14d
0x140072ffa  jns     short loc_140073005
0x140072ffc  mov     rcx, rbx; pv
0x140072fff  call    cs:__imp_CoTaskMemFree
0x140073005  test    rdi, rdi
0x140073008  jz      short loc_140073013
0x14007300a  mov     rcx, rdi; pv
0x14007300d  call    cs:__imp_CoTaskMemFree
0x140073013  mov     rcx, cs:WPP_GLOBAL_Control
0x14007301a  lea     rax, WPP_GLOBAL_Control
0x140073021  cmp     rcx, rax
0x140073024  jz      short loc_140073047
0x140073026  test    byte ptr [rcx+1Ch], 1
0x14007302a  jz      short loc_140073047
0x14007302c  cmp     byte ptr [rcx+19h], 4
0x140073030  jb      short loc_140073047
0x140073032  mov     rcx, [rcx+10h]
0x140073036  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x14007303d  mov     edx, 1Bh
0x140073042  call    WPP_SF_
0x140073047  mov     rbx, [rsp+68h+arg_18]
0x14007304f  mov     eax, r14d
0x140073052  add     rsp, 30h
0x140073056  pop     r15
0x140073058  pop     r14
0x14007305a  pop     r13
0x14007305c  pop     r12
0x14007305e  pop     rdi
0x14007305f  pop     rsi
0x140073060  pop     rbp
0x140073061  retn
```
