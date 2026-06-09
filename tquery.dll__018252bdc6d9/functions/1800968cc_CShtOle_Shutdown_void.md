# CShtOle::Shutdown(void)

- ea: `0x1800968cc`
- end: `0x180096ba4`
- name: `?Shutdown@CShtOle@@QEAAXXZ`
- size: `728`
- prototype: `void __fastcall(CShtOle *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180096870`

## callees

- `0x18002f914`
- `0x180038f08`
- `0x18008b084`
- `0x1800968cc`
- `0x1800f7b50`
- `0x1801177d8`
- `0x18013effc`
- `0x18017504c`
- `0x180188d90`
- `0x180189cce`
- `0x18018a0ed`
- `0x1801fe2e8`
- `0x1801fe760`
- `0x1801fe784`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096913`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096913`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096b5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096b5f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18009697f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x180096ab5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18009697f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x180096ab5`

## string_xrefs

- `0x1800969dd`: `CLSID\%ws\InProcServer32`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CShtOle::Shutdown(CShtOle *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rdi
  _QWORD *v5; // rdx
  __int64 v6; // r8
  WCHAR *v7; // rcx
  int v8; // eax
  int Value; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  __int64 v12; // r8
  WCHAR *v13; // rcx
  char IsEnabled; // al
  const wchar_t *v15; // r8
  unsigned int v16; // r9d
  unsigned int v17; // edx
  int v18; // [rsp+20h] [rbp-538h]
  int v19; // [rsp+20h] [rbp-538h]
  unsigned int v20; // [rsp+28h] [rbp-530h]
  DWORD v21; // [rsp+40h] [rbp-518h] BYREF
  DWORD v22[3]; // [rsp+44h] [rbp-514h] BYREF
  struct _GUID v23; // [rsp+50h] [rbp-508h] BYREF
  char *v24; // [rsp+60h] [rbp-4F8h]
  CShtOle *v25; // [rsp+68h] [rbp-4F0h]
  char *v26; // [rsp+70h] [rbp-4E8h]
  LPWSTR pszPath[3]; // [rsp+78h] [rbp-4E0h] BYREF
  unsigned __int64 v28; // [rsp+90h] [rbp-4C8h]
  OLECHAR sz[56]; // [rsp+A0h] [rbp-4B8h] BYREF
  wchar_t v30[264]; // [rsp+110h] [rbp-448h] BYREF
  wchar_t SubKey[264]; // [rsp+320h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+558h] [rbp+0h]

  v25 = this;
  if ( *((_DWORD *)this + 4) )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
    v24 = (char *)this + 24;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    while ( 1 )
    {
      v26 = (char *)this + 8;
      v4 = *((_QWORD *)this + 1);
      *(_QWORD *)&v23.Data1 = v4;
      if ( !v4 )
        break;
      std::wstring::wstring(pszPath, v3);
      v5 = (_QWORD *)(v4 + 176);
      if ( *(_QWORD *)(v4 + 200) > 7u )
        v5 = (_QWORD *)*v5;
      v6 = -1;
      do
        ++v6;
      while ( *((_WORD *)v5 + v6) );
      try
      {
        std::wstring::_Assign<wchar_t>(pszPath, v5, v6);
        v7 = (WCHAR *)pszPath;
        if ( v28 > 7 )
          v7 = pszPath[0];
        PathStripPathW(v7);
        if ( !pszPath[2] )
        {
          memset_0(sz, 0, 0x64u);
          StringFromGUID2_0((const GUID *const)(v4 + 156), sz, 39);
          memset_0(SubKey, 0, 0x208u);
          v8 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ws\\InProcServer32", sz);
          if ( v8 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x51,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\shtole.cxx",
              (const char *)(unsigned int)v8,
              v18);
          memset_0(v30, 0, 0x208u);
          v21 = 520;
          v22[0] = 0;
          Value = WSearchRegGetValue(HKEY_CLASSES_ROOT, SubKey, 0, 4u, v22, v30, &v21);
          if ( Value < 0 )
            wil::details::in1diag3::_Log_NtStatus(retaddr, v10, v11, (const char *)(unsigned int)Value, v19);
          v12 = -1;
          do
            ++v12;
          while ( v30[v12] );
          std::wstring::_Assign<wchar_t>(pszPath, v30, v12);
          v13 = (WCHAR *)pszPath;
          if ( v28 > 7 )
            v13 = pszPath[0];
          PathStripPathW(v13);
        }
      }
      catch ( ... )
      {
        indexer::result::details::result_from_caught_exception<1>(
          retaddr,
          99,
          "onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\shtole.cxx");
      }
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58386382>::GetImpl'::`2'::impl);
      v15 = (const wchar_t *)pszPath;
      v16 = *(_DWORD *)(v4 + 224);
      v23 = *(struct _GUID *)(v4 + 156);
      if ( IsEnabled )
        v20 = *(_DWORD *)(v4 + 232);
      else
        v20 = 0;
      if ( v28 > 7 )
        v15 = pszPath[0];
      SearchIndexerTelemetryAggregatedMedium::IFilterUsage(
        (const wchar_t *)(v4 + 8),
        &v23,
        v15,
        v16,
        *(_DWORD *)(v4 + 228),
        v20);
      *((_QWORD *)this + 1) = *(_QWORD *)v4;
      CShtOle::CClassNode::`scalar deleting destructor'((CShtOle::CClassNode *)v4, v17);
      std::wstring::_Tidy_deallocate(pszPath);
    }
    LeaveCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x1800968cc  mov     [rsp+arg_8], rbx
0x1800968d1  mov     [rsp+arg_10], rsi
0x1800968d6  push    rdi
0x1800968d7  push    r14
0x1800968d9  push    r15
0x1800968db  sub     rsp, 540h
0x1800968e2  mov     rax, cs:__security_cookie
0x1800968e9  xor     rax, rsp
0x1800968ec  mov     [rsp+558h+var_28], rax
0x1800968f4  mov     r14, rcx
0x1800968f7  mov     [rsp+558h+var_4F0], rcx
0x1800968fc  xor     esi, esi
0x1800968fe  cmp     [rcx+10h], esi
0x180096901  jz      loc_180096B65
0x180096907  lea     rbx, [rcx+18h]
0x18009690b  mov     [rsp+558h+var_4F8], rbx
0x180096910  mov     rcx, rbx; lpCriticalSection
0x180096913  call    cs:__imp_EnterCriticalSection
0x180096919  nop
0x18009691a  lea     r15, [r14+8]
0x18009691e  mov     [rsp+558h+var_4E8], r15
0x180096923  mov     rdi, [r15]
0x180096926  mov     qword ptr [rsp+558h+var_508.Data1], rdi
0x18009692b  test    rdi, rdi
0x18009692e  jz      loc_180096B5C
0x180096934  lea     rcx, [rsp+558h+pszPath]
0x180096939  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009693e  nop
0x18009693f  lea     rdx, [rdi+0B0h]
0x180096946  cmp     qword ptr [rdi+0C8h], 7
0x18009694e  jbe     short loc_180096953
0x180096950  mov     rdx, [rdx]
0x180096953  or      r8, 0FFFFFFFFFFFFFFFFh
0x180096957  inc     r8
0x18009695a  cmp     [rdx+r8*2], si
0x18009695f  jnz     short loc_180096957
0x180096961  lea     rcx, [rsp+558h+pszPath]
0x180096966  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18009696b  lea     rcx, [rsp+558h+pszPath]
0x180096970  cmp     [rsp+558h+var_4C8], 7
0x180096979  cmova   rcx, [rsp+558h+pszPath]; pszPath
0x18009697f  call    cs:__imp_PathStripPathW
0x180096985  cmp     [rsp+558h+var_4D0], rsi
0x18009698d  jnz     loc_180096ABC
0x180096993  xor     edx, edx; Val
0x180096995  lea     r8d, [rdx+64h]; Size
0x180096999  lea     rcx, [rsp+558h+sz]; void *
0x1800969a1  call    memset_0
0x1800969a6  lea     rcx, [rdi+9Ch]; rguid
0x1800969ad  mov     r8d, 27h ; '''; cchMax
0x1800969b3  lea     rdx, [rsp+558h+sz]; lpsz
0x1800969bb  call    StringFromGUID2_0
0x1800969c0  xor     edx, edx; Val
0x1800969c2  mov     r8d, 208h; Size
0x1800969c8  lea     rcx, [rsp+558h+SubKey]; void *
0x1800969d0  call    memset_0
0x1800969d5  lea     r9, [rsp+558h+sz]
0x1800969dd  lea     r8, aClsidWsInprocs; "CLSID\\%ws\\InProcServer32"
0x1800969e4  mov     edx, 104h; unsigned __int64
0x1800969e9  lea     rcx, [rsp+558h+SubKey]; wchar_t *
0x1800969f1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800969f6  mov     rcx, [rsp+558h]; this
0x1800969fe  test    eax, eax
0x180096a00  js      loc_180096B8E
0x180096a06  xor     edx, edx; Val
0x180096a08  mov     r8d, 208h; Size
0x180096a0e  lea     rcx, [rsp+558h+var_448]; void *
0x180096a16  call    memset_0
0x180096a1b  mov     [rsp+558h+var_518], 208h
0x180096a23  mov     [rsp+558h+var_514], esi
0x180096a27  lea     rax, [rsp+558h+var_518]
0x180096a2c  mov     [rsp+558h+var_528], rax; LPDWORD
0x180096a31  lea     rax, [rsp+558h+var_448]
0x180096a39  mov     [rsp+558h+var_530], rax; PVOID
0x180096a3e  lea     rax, [rsp+558h+var_514]
0x180096a43  mov     [rsp+558h+var_538], rax; int
0x180096a48  mov     r9d, 4; dwFlags
0x180096a4e  xor     r8d, r8d; lpValue
0x180096a51  lea     rdx, [rsp+558h+SubKey]; lpSubKey
0x180096a59  mov     rcx, 0FFFFFFFF80000000h; hkey
0x180096a60  call    ?WSearchRegGetValue@@YAJPEAUHKEY__@@PEB_W1KPEAKPEAX2@Z; WSearchRegGetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong *,void *,ulong *)
0x180096a65  mov     rcx, [rsp+558h]; this
0x180096a6d  test    eax, eax
0x180096a6f  jns     short loc_180096A79
0x180096a71  mov     r9d, eax; char *
0x180096a74  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180096a79  lea     rax, [rsp+558h+var_448]
0x180096a81  or      r8, 0FFFFFFFFFFFFFFFFh
0x180096a85  inc     r8
0x180096a88  cmp     [rax+r8*2], si
0x180096a8d  jnz     short loc_180096A85
0x180096a8f  lea     rdx, [rsp+558h+var_448]
0x180096a97  lea     rcx, [rsp+558h+pszPath]
0x180096a9c  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180096aa1  lea     rcx, [rsp+558h+pszPath]
0x180096aa6  cmp     [rsp+558h+var_4C8], 7
0x180096aaf  cmova   rcx, [rsp+558h+pszPath]; pszPath
0x180096ab5  call    cs:__imp_PathStripPathW
0x180096abb  nop
0x180096abc  jmp     short loc_180096AD4
0x180096abe  xor     esi, esi
0x180096ac0  mov     rbx, [rsp+558h+var_4F8]
0x180096ac5  mov     r14, [rsp+558h+var_4F0]
0x180096aca  mov     r15, [rsp+558h+var_4E8]
0x180096acf  mov     rdi, qword ptr [rsp+558h+var_508.Data1]
0x180096ad4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58386382@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58386382@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382> `wil::Feature<__WilFeatureTraits_Feature_58386382>::GetImpl(void)'::`2'::impl
0x180096adb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58386382@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382>::__private_IsEnabled(void)
0x180096ae0  lea     r8, [rsp+558h+pszPath]
0x180096ae5  movups  xmm0, xmmword ptr [rdi+9Ch]
0x180096aec  lea     rcx, [rdi+8]; wchar_t *
0x180096af0  mov     r9d, [rdi+0E0h]; unsigned int
0x180096af7  movdqu  xmmword ptr [rsp+558h+var_508.Data1], xmm0
0x180096afd  test    al, al
0x180096aff  jz      short loc_180096B17
0x180096b01  mov     eax, [rdi+0E8h]
0x180096b07  mov     edx, [rdi+0E4h]
0x180096b0d  mov     dword ptr [rsp+558h+var_530], eax
0x180096b11  mov     dword ptr [rsp+558h+var_538], edx
0x180096b15  jmp     short loc_180096B25
0x180096b17  mov     eax, [rdi+0E4h]
0x180096b1d  mov     dword ptr [rsp+558h+var_530], esi; unsigned int
0x180096b21  mov     dword ptr [rsp+558h+var_538], eax; unsigned int
0x180096b25  cmp     [rsp+558h+var_4C8], 7
0x180096b2e  cmova   r8, [rsp+558h+pszPath]; wchar_t *
0x180096b34  lea     rdx, [rsp+558h+var_508]; struct _GUID *
0x180096b39  call    ?IFilterUsage@SearchIndexerTelemetryAggregatedMedium@@SAXPEB_WU_GUID@@0KKK@Z; SearchIndexerTelemetryAggregatedMedium::IFilterUsage(wchar_t const *,_GUID,wchar_t const *,ulong,ulong,ulong)
0x180096b3e  mov     rax, [rdi]
0x180096b41  mov     [r15], rax
0x180096b44  mov     rcx, rdi; this
0x180096b47  call    ??_GCClassNode@CShtOle@@QEAAPEAXI@Z; CShtOle::CClassNode::`scalar deleting destructor'(uint)
0x180096b4c  nop
0x180096b4d  lea     rcx, [rsp+558h+pszPath]
0x180096b52  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180096b57  jmp     loc_18009691A
0x180096b5c  mov     rcx, rbx; lpCriticalSection
0x180096b5f  call    cs:__imp_LeaveCriticalSection
0x180096b65  mov     rcx, [rsp+558h+var_28]
0x180096b6d  xor     rcx, rsp; StackCookie
0x180096b70  call    __security_check_cookie
0x180096b75  lea     r11, [rsp+558h+var_18]
0x180096b7d  mov     rbx, [r11+28h]
0x180096b81  mov     rsi, [r11+30h]
0x180096b85  mov     rsp, r11
0x180096b88  pop     r15
0x180096b8a  pop     r14
0x180096b8c  pop     rdi
0x180096b8d  retn
0x180096b8e  mov     r9d, eax; char *
0x180096b91  lea     r8, aOnecoreuapBase_229; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180096b98  mov     edx, 51h ; 'Q'; void *
0x180096b9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
