# CanLoadVisualStyle(ushort const *)

- ea: `0x18005fb24`
- end: `0x18005fcad`
- name: `?CanLoadVisualStyle@@YAJPEBG@Z`
- size: `393`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004fb2c`

## callees

- `0x18000bb40`
- `0x18000d490`
- `0x1800358c0`
- `0x18003633c`
- `0x18005fb24`
- `0x18006a174`
- `0x18006a5e8`
- `0x18006a67c`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x18005fb70`
- `SHELL32!SHGetFolderPathEx` at `0x18005fb70`
- `SHLWAPI!PathCommonPrefixW` at `0x18005fbba`
- `SHLWAPI!PathCommonPrefixW` at `0x18005fc39`
- `SHLWAPI!PathCommonPrefixW` at `0x18005fbba`
- `SHLWAPI!PathCommonPrefixW` at `0x18005fc39`
- `SHLWAPI!PathAppendW` at `0x18005fb8f`
- `SHLWAPI!PathAppendW` at `0x18005fb8f`

## pseudocode

```c
__int64 __fastcall CanLoadVisualStyle(LPCWSTR lpFileName)
{
  const unsigned __int8 *v2; // rdx
  __int64 v3; // rbx
  __int64 v4; // rdi
  unsigned int v5; // r8d
  unsigned int v6; // edi
  _QWORD v8[6]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszFile1[22]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v10[484]; // [rsp+8Ch] [rbp-74h] BYREF
  WCHAR pszPath[264]; // [rsp+270h] [rbp+170h] BYREF

  v3 = -1;
  if ( (int)SHGetFolderPathEx(&FOLDERID_ResourceDir, 0, 0, pszPath, 260) >= 0 )
  {
    if ( PathAppendW(pszPath, L"Themes") )
    {
      v4 = -1;
      do
        ++v4;
      while ( pszPath[v4] );
      if ( v4 == PathCommonPrefixW(pszPath, lpFileName, 0) )
        goto LABEL_9;
    }
  }
  v6 = -2147024891;
  LOBYTE(v2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl'::`2'::impl,
    v2);
  wcscpy(pszFile1, L"%MasterThemelector%");
  memset_0(v10, 0, 0x1DCu);
  if ( ExpandThemeTokens(0, pszFile1) >= 0 )
  {
    do
      ++v3;
    while ( pszFile1[v3] );
    if ( v3 == PathCommonPrefixW(pszFile1, lpFileName, 0) )
    {
LABEL_9:
      memset(&v8[1], 0, 24);
      v8[0] = &CThemeSignature::`vftable';
      CThemeSignature::_Init((CThemeSignature *)v8, v2, v5);
      v6 = CThemeSignature::Verify((CThemeSignature *)v8, lpFileName);
      CThemeSignature::~CThemeSignature((CThemeSignature *)v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18005fb24  mov     [rsp-8+arg_8], rbx
0x18005fb29  mov     [rsp-8+arg_10], rsi
0x18005fb2e  push    rbp
0x18005fb2f  push    rdi
0x18005fb30  push    r14
0x18005fb32  lea     rbp, [rsp-390h]
0x18005fb3a  sub     rsp, 490h
0x18005fb41  mov     rax, cs:__security_cookie
0x18005fb48  xor     rax, rsp
0x18005fb4b  mov     [rbp+3A0h+var_20], rax
0x18005fb52  mov     rsi, rcx
0x18005fb55  mov     [rsp+4A0h+var_480], 104h
0x18005fb5d  lea     rcx, FOLDERID_ResourceDir
0x18005fb64  xor     r8d, r8d
0x18005fb67  lea     r9, [rbp+3A0h+pszPath]
0x18005fb6e  xor     edx, edx
0x18005fb70  call    cs:__imp_SHGetFolderPathEx
0x18005fb76  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005fb7a  xor     r14d, r14d
0x18005fb7d  test    eax, eax
0x18005fb7f  js      short loc_18005FBC7
0x18005fb81  lea     rdx, aThemes; "Themes"
0x18005fb88  lea     rcx, [rbp+3A0h+pszPath]; pszPath
0x18005fb8f  call    cs:__imp_PathAppendW
0x18005fb95  test    eax, eax
0x18005fb97  jz      short loc_18005FBC7
0x18005fb99  lea     rax, [rbp+3A0h+pszPath]
0x18005fba0  mov     rdi, rbx
0x18005fba3  inc     rdi
0x18005fba6  cmp     [rax+rdi*2], r14w
0x18005fbab  jnz     short loc_18005FBA3
0x18005fbad  xor     r8d, r8d; achPath
0x18005fbb0  lea     rcx, [rbp+3A0h+pszPath]; pszFile1
0x18005fbb7  mov     rdx, rsi; pszFile2
0x18005fbba  call    cs:__imp_PathCommonPrefixW
0x18005fbc0  mov     eax, eax
0x18005fbc2  cmp     rdi, rax
0x18005fbc5  jz      short loc_18005FC46
0x18005fbc7  mov     edi, 80070005h
0x18005fbcc  mov     dl, 1
0x18005fbce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AUTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest> `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl(void)'::`2'::impl
0x18005fbd5  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18005fbda  movups  xmm0, xmmword ptr cs:aMasterthemesel_0; "%MasterThemeSelector%"
0x18005fbe1  xor     edx, edx; Val
0x18005fbe3  mov     r8d, 1DCh; Size
0x18005fbe9  movups  xmm1, xmmword ptr cs:aMasterthemesel_0+10h; "hemeSelector%"
0x18005fbf0  lea     rcx, [rbp+3A0h+var_414]; void *
0x18005fbf4  movaps  xmmword ptr [rsp+4A0h+pszFile1], xmm0
0x18005fbf9  movups  xmm0, xmmword ptr cs:aMasterthemesel_0+1Ch; "lector%"
0x18005fc00  movaps  [rsp+4A0h+var_430], xmm1
0x18005fc05  movups  [rsp+4A0h+var_430+0Ch], xmm0
0x18005fc0a  call    memset_0
0x18005fc0f  lea     rdx, [rsp+4A0h+pszFile1]; unsigned __int16 *
0x18005fc14  xor     ecx, ecx; unsigned __int16 *
0x18005fc16  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x18005fc1b  test    eax, eax
0x18005fc1d  js      short loc_18005FC84
0x18005fc1f  lea     rax, [rsp+4A0h+pszFile1]
0x18005fc24  inc     rbx
0x18005fc27  cmp     [rax+rbx*2], r14w
0x18005fc2c  jnz     short loc_18005FC24
0x18005fc2e  xor     r8d, r8d; achPath
0x18005fc31  lea     rcx, [rsp+4A0h+pszFile1]; pszFile1
0x18005fc36  mov     rdx, rsi; pszFile2
0x18005fc39  call    cs:__imp_PathCommonPrefixW
0x18005fc3f  mov     eax, eax
0x18005fc41  cmp     rbx, rax
0x18005fc44  jnz     short loc_18005FC84
0x18005fc46  lea     rax, ??_7CThemeSignature@@6B@; const CThemeSignature::`vftable'
0x18005fc4d  mov     [rsp+4A0h+var_468], r14
0x18005fc52  lea     rcx, [rsp+4A0h+var_470]; this
0x18005fc57  mov     [rsp+4A0h+var_470], rax
0x18005fc5c  mov     [rsp+4A0h+var_460], r14
0x18005fc61  mov     [rsp+4A0h+var_458], r14
0x18005fc66  call    ?_Init@CThemeSignature@@IEAAXPEBEK@Z; CThemeSignature::_Init(uchar const *,ulong)
0x18005fc6b  mov     rdx, rsi; lpFileName
0x18005fc6e  lea     rcx, [rsp+4A0h+var_470]; this
0x18005fc73  call    ?Verify@CThemeSignature@@QEAAJPEBG@Z; CThemeSignature::Verify(ushort const *)
0x18005fc78  lea     rcx, [rsp+4A0h+var_470]; this
0x18005fc7d  mov     edi, eax
0x18005fc7f  call    ??1CThemeSignature@@UEAA@XZ; CThemeSignature::~CThemeSignature(void)
0x18005fc84  mov     eax, edi
0x18005fc86  mov     rcx, [rbp+3A0h+var_20]
0x18005fc8d  xor     rcx, rsp; StackCookie
0x18005fc90  call    __security_check_cookie
0x18005fc95  lea     r11, [rsp+4A0h+var_10]
0x18005fc9d  mov     rbx, [r11+28h]
0x18005fca1  mov     rsi, [r11+30h]
0x18005fca5  mov     rsp, r11
0x18005fca8  pop     r14
0x18005fcaa  pop     rdi
0x18005fcab  pop     rbp
0x18005fcac  retn
```
