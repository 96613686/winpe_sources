# CThemeManager2::_LoadThemeFiles(bool,bool)

- ea: `0x1800311a0`
- end: `0x1800313df`
- name: `?_LoadThemeFiles@CThemeManager2@@AEAAJ_N0@Z`
- size: `575`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this, bool, bool)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800141b0`
- `0x180017a10`
- `0x180057070`

## callees

- `0x18000bb40`
- `0x18000d490`
- `0x18000dd60`
- `0x18000ed70`
- `0x180017b70`
- `0x180019398`
- `0x18001e1ec`
- `0x1800311a0`
- `0x1800358c0`
- `0x18003633c`
- `0x1800427dc`
- `0x180055704`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x1800311f1`
- `SHELL32!SHGetFolderPathEx` at `0x1800312ba`
- `SHELL32!SHGetFolderPathEx` at `0x1800311f1`
- `SHELL32!SHGetFolderPathEx` at `0x1800312ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031284`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003139c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003139c`

## pseudocode

```c
__int64 __fastcall CThemeManager2::_LoadThemeFiles(CThemeManager2 *this, char a2, char a3)
{
  char v5; // di
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // r8d
  int v10; // r9d
  void *v11; // rdi
  _DWORD *v12; // rcx
  __int64 result; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+28h] [rbp-D8h]
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String1[22]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[484]; // [rsp+7Ch] [rbp-84h] BYREF
  WCHAR String2[264]; // [rsp+260h] [rbp+160h] BYREF

  if ( !a2 )
  {
    v5 = 0;
    if ( (int)SHGetFolderPathEx(&FOLDERID_ResourceDir, 0, 0, String2, 260) >= 0 )
    {
      v5 = 1;
      CThemeManager2::_AddThemesFromDir(this, String2, 1);
    }
    LOBYTE(v6) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl'::`2'::impl,
      v6);
    wcscpy(String1, L"%MasterThemelector%");
    memset_0(v18, 0, 0x1DCu);
    if ( ExpandThemeTokens(0, String1) >= 0 && (!v5 || CompareStringOrdinal(String1, -1, String2, -1, 1) != 2) )
      CThemeManager2::_AddThemesFromDir(this, String1, 1);
    if ( (int)SHGetFolderPathEx(&FOLDERID_LocalAppData, 0, 0, String2, 260) >= 0
      && (int)StringCchCatW(String2, 0x104u, L"\\Microsoft\\Windows\\Themes") >= 0 )
    {
      CThemeManager2::_AddThemesFromDir(this, String2, 1);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids, String2);
  }
  if ( !*((_BYTE *)this + 2145)
    && (int)CThemeManager2::_GetCurrentThemeFromRegistry(this) >= 0
    && (!*((_DWORD *)this + 552) || a3 || (*(int (__fastcall **)(CThemeManager2 *))(*(_QWORD *)this + 208LL))(this) >= 0) )
  {
    pv[0] = 0;
    if ( (int)_AllocString<CTCoAllocPolicy>(v8, v7, (char *)this + 12, pv) >= 0 )
    {
      v11 = pv[0];
      if ( (unsigned int)CDPA<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::SortedInsertPtr(
                           (int)this + 2112,
                           (int)pv[0],
                           v9,
                           v10,
                           bIgnoreCase,
                           v15,
                           pv[0]) == -1 )
        CoTaskMemFree(v11);
    }
  }
  CThemeManager2::_RemoveDuplicates(this);
  v12 = (_DWORD *)*((_QWORD *)this + 264);
  if ( v12 )
    LODWORD(v12) = *v12;
  result = 0;
  if ( (int)v12 <= 0 )
    return 2147500037LL;
  return result;
}

```

## disassembly

```asm
0x1800311a0  push    rbp
0x1800311a2  push    rbx
0x1800311a3  push    rsi
0x1800311a4  push    rdi
0x1800311a5  lea     rbp, [rsp-388h]
0x1800311ad  sub     rsp, 488h
0x1800311b4  mov     rax, cs:__security_cookie
0x1800311bb  xor     rax, rsp
0x1800311be  mov     [rbp+3A0h+var_30], rax
0x1800311c5  mov     sil, r8b
0x1800311c8  mov     rbx, rcx
0x1800311cb  test    dl, dl
0x1800311cd  jnz     loc_180031327
0x1800311d3  lea     r9, [rbp+3A0h+String2]
0x1800311da  mov     [rsp+4A0h+bIgnoreCase], 104h
0x1800311e2  xor     r8d, r8d
0x1800311e5  lea     rcx, FOLDERID_ResourceDir
0x1800311ec  xor     edx, edx
0x1800311ee  xor     dil, dil
0x1800311f1  call    cs:__imp_SHGetFolderPathEx
0x1800311f7  test    eax, eax
0x1800311f9  js      short loc_180031210
0x1800311fb  mov     dil, 1
0x1800311fe  lea     rdx, [rbp+3A0h+String2]; unsigned __int16 *
0x180031205  mov     r8b, dil; bool
0x180031208  mov     rcx, rbx; this
0x18003120b  call    ?_AddThemesFromDir@CThemeManager2@@AEAAJPEBG_N@Z; CThemeManager2::_AddThemesFromDir(ushort const *,bool)
0x180031210  mov     dl, 1
0x180031212  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AUTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest> `wil::Feature<__WilFeatureTraits_Feature_AUTest>::GetImpl(void)'::`2'::impl
0x180031219  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AUTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AUTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003121e  movups  xmm0, xmmword ptr cs:aMasterthemesel_0; "%MasterThemeSelector%"
0x180031225  xor     edx, edx; Val
0x180031227  mov     r8d, 1DCh; Size
0x18003122d  movups  xmm1, xmmword ptr cs:aMasterthemesel_0+10h; "hemeSelector%"
0x180031234  lea     rcx, [rsp+4A0h+var_424]; void *
0x180031239  movaps  xmmword ptr [rsp+4A0h+String1], xmm0
0x18003123e  movups  xmm0, xmmword ptr cs:aMasterthemesel_0+1Ch; "lector%"
0x180031245  movaps  [rsp+4A0h+var_440], xmm1
0x18003124a  movups  [rsp+4A0h+var_440+0Ch], xmm0
0x18003124f  call    memset_0
0x180031254  lea     rdx, [rsp+4A0h+String1]; unsigned __int16 *
0x180031259  xor     ecx, ecx; unsigned __int16 *
0x18003125b  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x180031260  test    eax, eax
0x180031262  js      short loc_18003129F
0x180031264  test    dil, dil
0x180031267  jz      short loc_18003128F
0x180031269  or      r9d, 0FFFFFFFFh; cchCount2
0x18003126d  mov     [rsp+4A0h+bIgnoreCase], 1; bIgnoreCase
0x180031275  or      edx, r9d; cchCount1
0x180031278  lea     r8, [rbp+3A0h+String2]; lpString2
0x18003127f  lea     rcx, [rsp+4A0h+String1]; lpString1
0x180031284  call    cs:__imp_CompareStringOrdinal
0x18003128a  cmp     eax, 2
0x18003128d  jz      short loc_18003129F
0x18003128f  mov     r8b, 1; bool
0x180031292  lea     rdx, [rsp+4A0h+String1]; unsigned __int16 *
0x180031297  mov     rcx, rbx; this
0x18003129a  call    ?_AddThemesFromDir@CThemeManager2@@AEAAJPEBG_N@Z; CThemeManager2::_AddThemesFromDir(ushort const *,bool)
0x18003129f  lea     r9, [rbp+3A0h+String2]
0x1800312a6  mov     [rsp+4A0h+bIgnoreCase], 104h; int
0x1800312ae  xor     r8d, r8d
0x1800312b1  lea     rcx, FOLDERID_LocalAppData
0x1800312b8  xor     edx, edx
0x1800312ba  call    cs:__imp_SHGetFolderPathEx
0x1800312c0  test    eax, eax
0x1800312c2  js      short loc_1800312F2
0x1800312c4  lea     r8, aMicrosoftWindo_2; "\\Microsoft\\Windows\\Themes"
0x1800312cb  mov     edx, 104h; unsigned __int64
0x1800312d0  lea     rcx, [rbp+3A0h+String2]; unsigned __int16 *
0x1800312d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800312dc  test    eax, eax
0x1800312de  js      short loc_1800312F2
0x1800312e0  mov     r8b, 1; bool
0x1800312e3  lea     rdx, [rbp+3A0h+String2]; unsigned __int16 *
0x1800312ea  mov     rcx, rbx; this
0x1800312ed  call    ?_AddThemesFromDir@CThemeManager2@@AEAAJPEBG_N@Z; CThemeManager2::_AddThemesFromDir(ushort const *,bool)
0x1800312f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312f9  lea     rax, WPP_GLOBAL_Control
0x180031300  cmp     rcx, rax
0x180031303  jz      short loc_180031327
0x180031305  test    byte ptr [rcx+1Ch], 8
0x180031309  jz      short loc_180031327
0x18003130b  mov     rcx, [rcx+10h]
0x18003130f  lea     r9, [rbp+3A0h+String2]
0x180031316  mov     edx, 20h ; ' '
0x18003131b  lea     r8, WPP_6bdbcbb7e6e739505c4fb97354cda1d8_Traceguids
0x180031322  call    WPP_SF_S
0x180031327  cmp     byte ptr [rbx+861h], 0
0x18003132e  jnz     short loc_1800313A2
0x180031330  mov     rcx, rbx; this
0x180031333  call    ?_GetCurrentThemeFromRegistry@CThemeManager2@@AEAAJXZ; CThemeManager2::_GetCurrentThemeFromRegistry(void)
0x180031338  test    eax, eax
0x18003133a  js      short loc_1800313A2
0x18003133c  cmp     dword ptr [rbx+8A0h], 0
0x180031343  jz      short loc_180031360
0x180031345  test    sil, sil
0x180031348  jnz     short loc_180031360
0x18003134a  mov     rax, [rbx]
0x18003134d  mov     rcx, rbx
0x180031350  mov     rax, [rax+0D0h]
0x180031357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003135c  test    eax, eax
0x18003135e  js      short loc_1800313A2
0x180031360  lea     r8, [rbx+0Ch]
0x180031364  mov     [rsp+4A0h+pv], 0
0x18003136d  lea     r9, [rsp+4A0h+pv]
0x180031372  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180031377  test    eax, eax
0x180031379  js      short loc_1800313A2
0x18003137b  mov     rdi, [rsp+4A0h+pv]
0x180031380  lea     rcx, [rbx+840h]; int
0x180031387  mov     rdx, rdi; int
0x18003138a  mov     [rsp+4A0h+p], rdi; p
0x18003138f  call    ?SortedInsertPtr@?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAHPEBGHP6AH00_J@Z1I0@Z; CDPA<ushort,CTContainer_PolicyUnOwned<ushort>>::SortedInsertPtr(ushort const *,int,int (*)(ushort const *,ushort const *,__int64),__int64,uint,ushort const *)
0x180031394  cmp     eax, 0FFFFFFFFh
0x180031397  jnz     short loc_1800313A2
0x180031399  mov     rcx, rdi; pv
0x18003139c  call    cs:__imp_CoTaskMemFree
0x1800313a2  mov     rcx, rbx; this
0x1800313a5  call    ?_RemoveDuplicates@CThemeManager2@@AEAAXXZ; CThemeManager2::_RemoveDuplicates(void)
0x1800313aa  mov     rcx, [rbx+840h]
0x1800313b1  test    rcx, rcx
0x1800313b4  jz      short loc_1800313B8
0x1800313b6  mov     ecx, [rcx]
0x1800313b8  xor     eax, eax
0x1800313ba  mov     edx, 80004005h
0x1800313bf  test    ecx, ecx
0x1800313c1  cmovle  eax, edx
0x1800313c4  mov     rcx, [rbp+3A0h+var_30]
0x1800313cb  xor     rcx, rsp; StackCookie
0x1800313ce  call    __security_check_cookie
0x1800313d3  add     rsp, 488h
0x1800313da  pop     rdi
0x1800313db  pop     rsi
0x1800313dc  pop     rbx
0x1800313dd  pop     rbp
0x1800313de  retn
```
