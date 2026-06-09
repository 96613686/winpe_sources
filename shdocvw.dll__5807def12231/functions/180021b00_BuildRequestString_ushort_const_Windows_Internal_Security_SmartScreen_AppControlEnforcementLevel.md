# BuildRequestString(ushort const *,Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel)

- ea: `0x180021b00`
- end: `0x180021e7c`
- name: `?BuildRequestString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGW4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@@Z`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005b0c`

## callees

- `0x1800066d0`
- `0x180008320`
- `0x18001a610`
- `0x180020850`
- `0x180021384`
- `0x180021590`
- `0x18002188c`
- `0x1800218e0`
- `0x180021978`
- `0x180021b00`
- `0x1800224ac`
- `0x180022750`
- `0x1800227b8`
- `0x180022cd8`
- `0x180023198`
- `0x180023220`
- `0x180023438`
- `0x180023658`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180021b43`
- `SHLWAPI!PathFindFileNameW` at `0x180021b43`
- `Wldp!__imp_?WldpQueryWindowsLockdownMode@@YAJPEAW4WLDP_WINDOWS_LOCKDOWN_MODE@@@Z` at `0x180021c5a`
- `Wldp!__imp_?WldpQueryWindowsLockdownMode@@YAJPEAW4WLDP_WINDOWS_LOCKDOWN_MODE@@@Z` at `0x180021c5a`

## string_xrefs

- `0x180021bd0`: `recommendations`
- `0x180021deb`: `{"data":"{\"apphelpBlock\":false,\"authenticode\":{\"hash\":\"%s\",\"hashAlgo\":\"%s\",\"issuer\":{\"hash\":\"\",\"subjectName\":\"\"},\"signer\":{\"hash\":\"\",\"subjectName\":\"\"},\"signing\":{\"message\":\"\",\"time\":\"\"},\"valid\":%s},\"binaryType\":332,\"config\":{\"device\":{\"appControl\":{\"level\":\"%s\"},\"appReputation\":{\"enforcedByPolicy\":false,\"level\":\"warn\"}},\"user\":{\"uriReputation\":{\"enforcedByPolicy\":false,\"level\":\"warn\"}}},\"correlationId\":\"%s\",\"fileId\":`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall BuildRequestString(__int64 a1, const WCHAR *a2, int a3)
{
  int v5; // ebx
  int v6; // ebx
  bool v7; // zf
  const wchar_t *v8; // rbx
  __int64 v9; // rax
  const WCHAR *v10; // rax
  int WindowsLockdownMode; // eax
  _QWORD *v12; // r13
  _QWORD *v13; // r12
  _QWORD *v14; // r15
  _QWORD *v15; // r14
  _QWORD *v16; // rsi
  _QWORD *v17; // rdi
  _QWORD *v18; // rbx
  _QWORD *v19; // r11
  const wchar_t *v20; // r10
  const wchar_t *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // r9
  _QWORD *v24; // r8
  int v26; // [rsp+20h] [rbp-110h]
  int v27; // [rsp+B0h] [rbp-80h] BYREF
  const wchar_t *v28; // [rsp+B8h] [rbp-78h]
  __int64 v29; // [rsp+C0h] [rbp-70h]
  __int64 v30; // [rsp+C8h] [rbp-68h]
  __int64 v31; // [rsp+D0h] [rbp-60h]
  __int64 *v32; // [rsp+D8h] [rbp-58h] BYREF
  LPWSTR FileNameW; // [rsp+E0h] [rbp-50h]
  __int64 v34; // [rsp+F0h] [rbp-40h]
  __int64 v35; // [rsp+F8h] [rbp-38h] BYREF
  _QWORD v36[4]; // [rsp+100h] [rbp-30h] BYREF
  _QWORD v37[4]; // [rsp+120h] [rbp-10h] BYREF
  _QWORD v38[4]; // [rsp+140h] [rbp+10h] BYREF
  _QWORD v39[4]; // [rsp+160h] [rbp+30h] BYREF
  _QWORD v40[4]; // [rsp+180h] [rbp+50h] BYREF
  _BYTE v41[8]; // [rsp+1A0h] [rbp+70h] BYREF
  _QWORD v42[4]; // [rsp+1A8h] [rbp+78h] BYREF
  _QWORD v43[4]; // [rsp+1C8h] [rbp+98h] BYREF
  _QWORD v44[5]; // [rsp+1E8h] [rbp+B8h] BYREF
  _QWORD v45[4]; // [rsp+210h] [rbp+E0h] BYREF
  _QWORD v46[8]; // [rsp+230h] [rbp+100h] BYREF
  _QWORD v47[4]; // [rsp+270h] [rbp+140h] BYREF
  _BYTE v48[32]; // [rsp+290h] [rbp+160h] BYREF
  _BYTE v49[32]; // [rsp+2B0h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+1E8h]

  v34 = a1;
  FileNameW = PathFindFileNameW(a2);
  GetAppFileInfo(&v32, a2);
  if ( v32 )
  {
    v31 = *v32;
    v30 = v32[6];
    v29 = v32[1];
  }
  else
  {
    v31 = 0;
    v29 = 0;
    v30 = 0;
  }
  GetAppFileVersionInfo(&v35, a2);
  GetAppFileCertInfo(v41, a2);
  v5 = a3 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 == 1;
      v8 = L"anywhere";
      if ( v7 )
        v8 = L"store";
    }
    else
    {
      v8 = L"preferStore";
    }
    v28 = v8;
  }
  else
  {
    v28 = L"recommendations";
  }
  GetOSRegion((__int64)v40);
  GetOSVersion(v39);
  GetLocale(v38);
  v9 = std::wstring::wstring(v49, a2);
  v10 = (const WCHAR *)std::operator+<unsigned short>(v48, v9, L":Zone.Identifier");
  GetMarkOfTheWebFromFile((__int64)v45, v10);
  std::wstring::_Tidy_deallocate(v48);
  std::wstring::_Tidy_deallocate(v49);
  GetCorrelationId(v37);
  v27 = 0;
  WindowsLockdownMode = WldpQueryWindowsLockdownMode((enum WLDP_WINDOWS_LOCKDOWN_MODE *)&v27);
  if ( WindowsLockdownMode < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x266,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)WindowsLockdownMode,
      v26);
  v12 = v42;
  if ( v42[3] > 7u )
    v12 = (_QWORD *)v42[0];
  v13 = v36;
  if ( v36[3] > 7u )
    v13 = (_QWORD *)v36[0];
  v14 = v47;
  if ( v47[3] > 7u )
    v14 = (_QWORD *)v47[0];
  v15 = v45;
  if ( v45[3] > 7u )
    v15 = (_QWORD *)v45[0];
  v16 = v46;
  if ( v46[3] > 7u )
    v16 = (_QWORD *)v46[0];
  v17 = v40;
  if ( v40[3] > 7u )
    v17 = (_QWORD *)v40[0];
  v18 = v38;
  if ( v38[3] > 7u )
    v18 = (_QWORD *)v38[0];
  v19 = v39;
  if ( v39[3] > 7u )
    v19 = (_QWORD *)v39[0];
  v20 = L"true";
  v21 = L"true";
  if ( !v27 )
    v21 = L"false";
  v22 = v37;
  if ( v37[3] > 7u )
    v22 = (_QWORD *)v37[0];
  if ( !v41[0] )
    v20 = L"false";
  v23 = v43;
  if ( v43[3] > 7u )
    v23 = (_QWORD *)v43[0];
  v24 = v44;
  if ( v44[3] > 7u )
    v24 = (_QWORD *)v44[0];
  wil::str_printf<std::wstring>(
    v34,
    L"{\"data\":\"{\\\"apphelpBlock\\\":false,\\\"authenticode\\\":{\\\"hash\\\":\\\"%s\\\",\\\"hashAlgo\\\":\\\"%s\\\",\\"
     "\"issuer\\\":{\\\"hash\\\":\\\"\\\",\\\"subjectName\\\":\\\"\\\"},\\\"signer\\\":{\\\"hash\\\":\\\"\\\",\\\"subject"
     "Name\\\":\\\"\\\"},\\\"signing\\\":{\\\"message\\\":\\\"\\\",\\\"time\\\":\\\"\\\"},\\\"valid\\\":%s},\\\"binaryTyp"
     "e\\\":332,\\\"config\\\":{\\\"device\\\":{\\\"appControl\\\":{\\\"level\\\":\\\"%s\\\"},\\\"appReputation\\\":{\\\""
     "enforcedByPolicy\\\":false,\\\"level\\\":\\\"warn\\\"}},\\\"user\\\":{\\\"uriReputation\\\":{\\\"enforcedByPolicy\\"
     "\":false,\\\"level\\\":\\\"warn\\\"}}},\\\"correlationId\\\":\\\"%s\\\",\\\"fileId\\\":\\\"%s\\\",\\\"hash\\\":null"
     ",\\\"identity\\\":{\\\"caller\\\":{\\\"locales\\\":[\\\"\\\",\\\"\\\"],\\\"process\\\":{\\\"application\\\":{\\\"$t"
     "ype\\\":\\\"\\\",\\\"path\\\":\\\"\\\"},\\\"creationTime\\\":\\\"\\\",\\\"id\\\":0}},\\\"client\\\":{\\\"data\\\":{"
     "\\\"offlineExperience\\\":\\\"\\\",\\\"script\\\":\\\"\\\"},\\\"version\\\":\\\"1\\\"},\\\"device\\\":{\\\"architec"
     "ture\\\":9,\\\"browser\\\":{\\\"edge\\\":\\\"\\\",\\\"internetExplorer\\\":\\\"\\\"},\\\"cloudSku\\\":%s,\\\"contai"
     "nerGuest\\\":false,\\\"enterprise\\\":null,\\\"family\\\":3,\\\"locale\\\":\\\"\\\",\\\"netJoinStatus\\\":3,\\\"onl"
     "ineIdTicket\\\":\\\"\\\",\\\"osVersion\\\":\\\"%s\\\"},\\\"user\\\":{\\\"locale\\\":\\\"%s\\\",\\\"geo\\\":\\\"%s\\"
     "\"}},\\\"motw\\\":{\\\"hostUrl\\\":\\\"%s\\\",\\\"zoneId\\\":\\\"%s\\\",\\\"referrerUrl\\\":\\\"%s\\\"},\\\"path\\\""
     ":{\\\"driveType\\\":3,\\\"fileName\\\":\\\"%s\\\",\\\"originalFileName\\\":\\\"%s\\\"},\\\"productName\\\":\\\"%s\\"
     "\",\\\"programId\\\":\\\"%s\\\",\\\"publisher\\\":\\\"%s\\\",\\\"size\\\":0,\\\"uxEnabled\\\":true,\\\"verb\\\":\\\""
     "open\\\",\\\"version\\\":\\\"%lld\\\"}\"}",
    v24,
    v23,
    v20,
    v28,
    v22,
    v31,
    v21,
    v19,
    v18,
    v17,
    v16,
    v15,
    v14,
    FileNameW,
    v13,
    v30,
    v29,
    v12,
    v35);
  std::wstring::_Tidy_deallocate(v37);
  MarkOfTheWeb::~MarkOfTheWeb((MarkOfTheWeb *)v45);
  std::wstring::_Tidy_deallocate(v38);
  std::wstring::_Tidy_deallocate(v39);
  std::wstring::_Tidy_deallocate(v40);
  AUTHENTICODE_INFO::~AUTHENTICODE_INFO((AUTHENTICODE_INFO *)v41);
  std::wstring::_Tidy_deallocate(v36);
  wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&long PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&long PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>(&v32);
  return v34;
}

```

## disassembly

```asm
0x180021b00  mov     [rsp-8+arg_10], rbx
0x180021b05  push    rbp
0x180021b06  push    rsi
0x180021b07  push    rdi
0x180021b08  push    r12
0x180021b0a  push    r13
0x180021b0c  push    r14
0x180021b0e  push    r15
0x180021b10  lea     rbp, [rsp-1B0h]
0x180021b18  sub     rsp, 2E0h
0x180021b1f  mov     rax, cs:__security_cookie
0x180021b26  xor     rax, rsp
0x180021b29  mov     [rbp+1E0h+var_40], rax
0x180021b30  mov     ebx, r8d
0x180021b33  mov     rdi, rdx
0x180021b36  mov     [rbp+1E0h+var_220], rcx
0x180021b3a  mov     [rbp+1E0h+var_230], rcx
0x180021b3e  xor     esi, esi
0x180021b40  mov     rcx, rdx; pszPath
0x180021b43  call    cs:__imp_PathFindFileNameW
0x180021b49  mov     [rbp+1E0h+var_230], rax
0x180021b4d  mov     rdx, rdi
0x180021b50  lea     rcx, [rbp+1E0h+var_238]
0x180021b54  call    ?GetAppFileInfo@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_INFO@@P6AJPEAU1@@Z$1?PicFreeFileInfo@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; GetAppFileInfo(ushort const *)
0x180021b59  nop
0x180021b5a  mov     rax, [rbp+1E0h+var_238]
0x180021b5e  test    rax, rax
0x180021b61  jz      short loc_180021B7E
0x180021b63  mov     rsi, [rax]
0x180021b66  mov     [rbp+1E0h+var_240], rsi
0x180021b6a  mov     rsi, [rax+30h]
0x180021b6e  mov     [rbp+1E0h+var_248], rsi
0x180021b72  mov     rsi, [rax+8]
0x180021b76  mov     [rbp+1E0h+var_250], rsi
0x180021b7a  xor     esi, esi
0x180021b7c  jmp     short loc_180021B8A
0x180021b7e  mov     [rbp+1E0h+var_240], rsi
0x180021b82  mov     [rbp+1E0h+var_250], rsi
0x180021b86  mov     [rbp+1E0h+var_248], rsi
0x180021b8a  mov     rdx, rdi
0x180021b8d  lea     rcx, [rbp+1E0h+var_218]
0x180021b91  call    ?GetAppFileVersionInfo@@YA?AUFILE_VERSION_INFO@@PEBG@Z; GetAppFileVersionInfo(ushort const *)
0x180021b96  nop
0x180021b97  mov     rdx, rdi
0x180021b9a  lea     rcx, [rbp+1E0h+var_170]
0x180021b9e  call    ?GetAppFileCertInfo@@YA?AUAUTHENTICODE_INFO@@PEBG@Z; GetAppFileCertInfo(ushort const *)
0x180021ba3  nop
0x180021ba4  sub     ebx, 1
0x180021ba7  jz      short loc_180021BD0
0x180021ba9  sub     ebx, 1
0x180021bac  jz      short loc_180021BC7
0x180021bae  cmp     ebx, 1
0x180021bb1  lea     rbx, aAnywhere; "anywhere"
0x180021bb8  jnz     short loc_180021BC1
0x180021bba  lea     rbx, aStore; "store"
0x180021bc1  mov     [rbp+1E0h+var_258], rbx
0x180021bc5  jmp     short loc_180021BDB
0x180021bc7  lea     rbx, aPreferstore; "preferStore"
0x180021bce  jmp     short loc_180021BC1
0x180021bd0  lea     rax, aRecommendation; "recommendations"
0x180021bd7  mov     [rbp+1E0h+var_258], rax
0x180021bdb  lea     rcx, [rbp+1E0h+var_190]
0x180021bdf  call    ?GetOSRegion@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4RegionLookupFallbackOptions@@@Z; GetOSRegion(RegionLookupFallbackOptions)
0x180021be4  nop
0x180021be5  lea     rcx, [rbp+1E0h+var_1B0]
0x180021be9  call    ?GetOSVersion@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetOSVersion(void)
0x180021bee  nop
0x180021bef  lea     rcx, [rbp+1E0h+var_1D0]
0x180021bf3  call    ?GetLocale@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetLocale(void)
0x180021bf8  nop
0x180021bf9  mov     rdx, rdi
0x180021bfc  lea     rcx, [rbp+1E0h+var_60]
0x180021c03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021c08  nop
0x180021c09  lea     r8, aZoneIdentifier; ":Zone.Identifier"
0x180021c10  mov     rdx, rax
0x180021c13  lea     rcx, [rbp+1E0h+var_80]
0x180021c1a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180021c1f  nop
0x180021c20  mov     rdx, rax
0x180021c23  lea     rcx, [rbp+1E0h+var_100]
0x180021c2a  call    ?GetMarkOfTheWebFromFile@@YA?AUMarkOfTheWeb@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetMarkOfTheWebFromFile(std::wstring const &)
0x180021c2f  nop
0x180021c30  lea     rcx, [rbp+1E0h+var_80]
0x180021c37  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021c3c  nop
0x180021c3d  lea     rcx, [rbp+1E0h+var_60]
0x180021c44  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021c49  lea     rcx, [rbp+1E0h+var_1F0]
0x180021c4d  call    ?GetCorrelationId@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetCorrelationId(void)
0x180021c52  nop
0x180021c53  mov     [rbp+1E0h+var_260], esi
0x180021c56  lea     rcx, [rbp+1E0h+var_260]
0x180021c5a  call    cs:__imp_?WldpQueryWindowsLockdownMode@@YAJPEAW4WLDP_WINDOWS_LOCKDOWN_MODE@@@Z; WldpQueryWindowsLockdownMode(WLDP_WINDOWS_LOCKDOWN_MODE *)
0x180021c60  mov     rcx, [rbp+1E8h]; this
0x180021c67  test    eax, eax
0x180021c69  jns     short loc_180021C80
0x180021c6b  mov     r9d, eax; char *
0x180021c6e  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180021c75  mov     edx, 266h; void *
0x180021c7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021c80  cmp     [rbp+1E0h+var_260], esi
0x180021c83  setnz   al
0x180021c86  lea     r13, [rbp+1E0h+var_168]
0x180021c8a  cmp     [rbp+1E0h+var_150], 7
0x180021c92  cmova   r13, [rbp+1E0h+var_168]
0x180021c97  lea     r12, [rbp+1E0h+var_210]
0x180021c9b  cmp     [rbp+1E0h+var_1F8], 7
0x180021ca0  cmova   r12, [rbp+1E0h+var_210]
0x180021ca5  lea     r15, [rbp+1E0h+var_A0]
0x180021cac  cmp     [rbp+1E0h+var_88], 7
0x180021cb4  cmova   r15, [rbp+1E0h+var_A0]
0x180021cbc  lea     r14, [rbp+1E0h+var_100]
0x180021cc3  cmp     [rbp+1E0h+var_E8], 7
0x180021ccb  cmova   r14, [rbp+1E0h+var_100]
0x180021cd3  lea     rsi, [rbp+1E0h+var_E0]
0x180021cda  cmp     [rbp+1E0h+var_C8], 7
0x180021ce2  cmova   rsi, [rbp+1E0h+var_E0]
0x180021cea  lea     rdi, [rbp+1E0h+var_190]
0x180021cee  cmp     [rbp+1E0h+var_178], 7
0x180021cf3  cmova   rdi, [rbp+1E0h+var_190]
0x180021cf8  lea     rbx, [rbp+1E0h+var_1D0]
0x180021cfc  cmp     [rbp+1E0h+var_1B8], 7
0x180021d01  cmova   rbx, [rbp+1E0h+var_1D0]
0x180021d06  lea     r11, [rbp+1E0h+var_1B0]
0x180021d0a  cmp     [rbp+1E0h+var_198], 7
0x180021d0f  cmova   r11, [rbp+1E0h+var_1B0]
0x180021d14  lea     r8, aFalse; "false"
0x180021d1b  lea     r10, aTrue; "true"
0x180021d22  mov     rdx, r10
0x180021d25  test    al, al
0x180021d27  cmovz   rdx, r8
0x180021d2b  lea     rcx, [rbp+1E0h+var_1F0]
0x180021d2f  cmp     [rbp+1E0h+var_1D8], 7
0x180021d34  cmova   rcx, [rbp+1E0h+var_1F0]
0x180021d39  cmp     [rbp+1E0h+var_170], 0
0x180021d3d  cmovz   r10, r8
0x180021d41  lea     r9, [rbp+1E0h+var_148]
0x180021d48  cmp     [rbp+1E0h+var_130], 7
0x180021d50  cmova   r9, [rbp+1E0h+var_148]
0x180021d58  lea     r8, [rbp+1E0h+var_128]
0x180021d5f  cmp     [rbp+1E0h+var_110], 7
0x180021d67  cmova   r8, [rbp+1E0h+var_128]
0x180021d6f  mov     rax, [rbp+1E0h+var_218]
0x180021d73  mov     [rsp+310h+var_270], rax
0x180021d7b  mov     [rsp+310h+var_278], r13
0x180021d83  mov     rax, [rbp+1E0h+var_250]
0x180021d87  mov     [rsp+310h+var_280], rax
0x180021d8f  mov     rax, [rbp+1E0h+var_248]
0x180021d93  mov     [rsp+310h+var_288], rax
0x180021d9b  mov     [rsp+310h+var_290], r12
0x180021da3  mov     rax, [rbp+1E0h+var_230]
0x180021da7  mov     [rsp+310h+var_298], rax
0x180021dac  mov     [rsp+310h+var_2A0], r15
0x180021db1  mov     [rsp+310h+var_2A8], r14
0x180021db6  mov     [rsp+310h+var_2B0], rsi
0x180021dbb  mov     [rsp+310h+var_2B8], rdi
0x180021dc0  mov     [rsp+310h+var_2C0], rbx
0x180021dc5  mov     [rsp+310h+var_2C8], r11
0x180021dca  mov     [rsp+310h+var_2D0], rdx
0x180021dcf  mov     rax, [rbp+1E0h+var_240]
0x180021dd3  mov     [rsp+310h+var_2D8], rax
0x180021dd8  mov     [rsp+310h+var_2E0], rcx
0x180021ddd  mov     rax, [rbp+1E0h+var_258]
0x180021de1  mov     [rsp+310h+var_2E8], rax
0x180021de6  mov     [rsp+310h+var_2F0], r10
0x180021deb  lea     rdx, aDataApphelpblo_0; "{\"data\":\"{\\\"apphelpBlock\\\":false"...
0x180021df2  mov     rcx, [rbp+1E0h+var_220]
0x180021df6  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180021dfb  nop
0x180021dfc  lea     rcx, [rbp+1E0h+var_1F0]
0x180021e00  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021e05  nop
0x180021e06  lea     rcx, [rbp+1E0h+var_100]; this
0x180021e0d  call    ??1MarkOfTheWeb@@QEAA@XZ; MarkOfTheWeb::~MarkOfTheWeb(void)
0x180021e12  nop
0x180021e13  lea     rcx, [rbp+1E0h+var_1D0]
0x180021e17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021e1c  nop
0x180021e1d  lea     rcx, [rbp+1E0h+var_1B0]
0x180021e21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021e26  nop
0x180021e27  lea     rcx, [rbp+1E0h+var_190]
0x180021e2b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021e30  nop
0x180021e31  lea     rcx, [rbp+1E0h+var_170]; this
0x180021e35  call    ??1AUTHENTICODE_INFO@@QEAA@XZ; AUTHENTICODE_INFO::~AUTHENTICODE_INFO(void)
0x180021e3a  nop
0x180021e3b  lea     rcx, [rbp+1E0h+var_210]
0x180021e3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021e44  nop
0x180021e45  lea     rcx, [rbp+1E0h+var_238]
0x180021e49  call    ??1?$unique_storage@U?$resource_policy@PEAU_FILE_INFO@@P6AJPEAU1@@Z$1?PicFreeFileInfo@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>(void)
0x180021e4e  mov     rax, [rbp+1E0h+var_220]
0x180021e52  mov     rcx, [rbp+1E0h+var_40]
0x180021e59  xor     rcx, rsp; StackCookie
0x180021e5c  call    __security_check_cookie
0x180021e61  mov     rbx, [rsp+310h+arg_10]
0x180021e69  add     rsp, 2E0h
0x180021e70  pop     r15
0x180021e72  pop     r14
0x180021e74  pop     r13
0x180021e76  pop     r12
0x180021e78  pop     rdi
0x180021e79  pop     rsi
0x180021e7a  pop     rbp
0x180021e7b  retn
```
