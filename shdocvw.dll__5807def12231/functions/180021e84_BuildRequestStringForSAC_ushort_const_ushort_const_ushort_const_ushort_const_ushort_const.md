# BuildRequestStringForSAC(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180021e84`
- end: `0x1800222db`
- name: `?BuildRequestStringForSAC@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0000@Z`
- size: `1111`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800060a8`

## callees

- `0x1800066d0`
- `0x180006a4c`
- `0x180008320`
- `0x18001a610`
- `0x180020850`
- `0x180021384`
- `0x180021590`
- `0x18002188c`
- `0x1800218e0`
- `0x180021978`
- `0x180021e84`
- `0x1800222e4`
- `0x1800224ac`
- `0x180022750`
- `0x1800227b8`
- `0x180022cd8`
- `0x180023198`
- `0x180023220`
- `0x180023438`
- `0x180023658`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180021ede`
- `SHLWAPI!PathFindFileNameW` at `0x180021ede`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180021fd7`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180021fd7`
- `Wldp!__imp_?WldpQueryWindowsLockdownMode@@YAJPEAW4WLDP_WINDOWS_LOCKDOWN_MODE@@@Z` at `0x180021fe4`
- `Wldp!__imp_?WldpQueryWindowsLockdownMode@@YAJPEAW4WLDP_WINDOWS_LOCKDOWN_MODE@@@Z` at `0x180021fe4`

## string_xrefs

- `0x180022224`: `{"data":"{\"apphelpBlock\":false,\"authenticode\":{\"hash\":\"%s\",\"hashAlgo\":\"%s\",\"issuer\":{\"hash\":\"\",\"subjectName\":\"\"},\"signer\":{\"hash\":\"\",\"subjectName\":\"\"},\"signing\":{\"message\":\"\",\"time\":\"\"},\"valid\":%s},\"binaryType\":332,\"config\":{\"device\":{\"appReputation\":{\"enforcedByPolicy\":false,\"level\":\"warn\"}},\"user\":{\"uriReputation\":{\"enforcedByPolicy\":false,\"level\":\"warn\"}}},\"correlationId\":\"%s\",\"fileId\":\"%s\",\"hash\":null,\"identity\":`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall BuildRequestStringForSAC(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v7; // rax
  const WCHAR *v8; // rax
  int WindowsLockdownMode; // eax
  bool v10; // r13
  _QWORD *v11; // rax
  _QWORD *v12; // rax
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
  int v26; // [rsp+20h] [rbp-130h]
  int v27; // [rsp+D0h] [rbp-80h] BYREF
  _QWORD *v28; // [rsp+D8h] [rbp-78h]
  __int64 v29; // [rsp+E0h] [rbp-70h]
  __int64 v30; // [rsp+E8h] [rbp-68h]
  __int64 v31; // [rsp+F0h] [rbp-60h]
  __int64 *v32; // [rsp+F8h] [rbp-58h] BYREF
  LPWSTR FileNameW; // [rsp+100h] [rbp-50h]
  __int64 v34; // [rsp+110h] [rbp-40h]
  __int64 v35; // [rsp+118h] [rbp-38h]
  __int64 v36; // [rsp+120h] [rbp-30h]
  _QWORD *v37; // [rsp+128h] [rbp-28h]
  __int64 v38; // [rsp+130h] [rbp-20h]
  _SYSTEM_INFO SystemInfo; // [rsp+138h] [rbp-18h] BYREF
  _BYTE Src[32]; // [rsp+168h] [rbp+18h] BYREF
  __int64 v41; // [rsp+188h] [rbp+38h] BYREF
  _QWORD v42[4]; // [rsp+190h] [rbp+40h] BYREF
  _QWORD v43[4]; // [rsp+1B0h] [rbp+60h] BYREF
  _QWORD v44[4]; // [rsp+1D0h] [rbp+80h] BYREF
  _QWORD v45[4]; // [rsp+1F0h] [rbp+A0h] BYREF
  _QWORD v46[4]; // [rsp+210h] [rbp+C0h] BYREF
  _QWORD v47[4]; // [rsp+230h] [rbp+E0h] BYREF
  _BYTE v48[32]; // [rsp+250h] [rbp+100h] BYREF
  _BYTE v49[32]; // [rsp+270h] [rbp+120h] BYREF
  _BYTE v50[8]; // [rsp+290h] [rbp+140h] BYREF
  _QWORD v51[4]; // [rsp+298h] [rbp+148h] BYREF
  _QWORD v52[4]; // [rsp+2B8h] [rbp+168h] BYREF
  _QWORD v53[5]; // [rsp+2D8h] [rbp+188h] BYREF
  _QWORD v54[4]; // [rsp+300h] [rbp+1B0h] BYREF
  _QWORD v55[8]; // [rsp+320h] [rbp+1D0h] BYREF
  _QWORD v56[4]; // [rsp+360h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+278h]

  v36 = a4;
  v38 = a1;
  v35 = a5;
  v34 = a6;
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
  GetAppFileVersionInfo(&v41, a2);
  GetAppFileCertInfo(v50, a2);
  GetOSRegion((__int64)v47);
  GetOSVersion(v46);
  GetLocale(v45);
  v7 = std::wstring::wstring(v49, a2);
  v8 = (const WCHAR *)std::operator+<unsigned short>(v48, v7, L":Zone.Identifier");
  GetMarkOfTheWebFromFile((__int64)v54, v8);
  std::wstring::_Tidy_deallocate(v48);
  std::wstring::_Tidy_deallocate(v49);
  GetCorrelationId(v44);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetNativeSystemInfo(&SystemInfo);
  v27 = 0;
  WindowsLockdownMode = WldpQueryWindowsLockdownMode((enum WLDP_WINDOWS_LOCKDOWN_MODE *)&v27);
  if ( WindowsLockdownMode < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2BA,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)WindowsLockdownMode,
      v26);
  v10 = v27 != 0;
  std::wstring::wstring(v48, a2);
  std::wstring::wstring(v49, v48);
  EscapeFilePathForJson(Src);
  EscapeFilePathForJson(v43);
  v11 = v51;
  if ( v51[3] > 7u )
    v11 = (_QWORD *)v51[0];
  v37 = v11;
  v12 = v43;
  if ( v43[3] > 7u )
    v12 = (_QWORD *)v43[0];
  v28 = v12;
  v13 = v42;
  if ( v42[3] > 7u )
    v13 = (_QWORD *)v42[0];
  v14 = v56;
  if ( v56[3] > 7u )
    v14 = (_QWORD *)v56[0];
  v15 = v54;
  if ( v54[3] > 7u )
    v15 = (_QWORD *)v54[0];
  v16 = v55;
  if ( v55[3] > 7u )
    v16 = (_QWORD *)v55[0];
  v17 = v47;
  if ( v47[3] > 7u )
    v17 = (_QWORD *)v47[0];
  v18 = v45;
  if ( v45[3] > 7u )
    v18 = (_QWORD *)v45[0];
  v19 = v46;
  if ( v46[3] > 7u )
    v19 = (_QWORD *)v46[0];
  v20 = L"true";
  v21 = L"true";
  if ( !v10 )
    v21 = L"false";
  v22 = v44;
  if ( v44[3] > 7u )
    v22 = (_QWORD *)v44[0];
  if ( !v50[0] )
    v20 = L"false";
  v23 = v52;
  if ( v52[3] > 7u )
    v23 = (_QWORD *)v52[0];
  v24 = v53;
  if ( v53[3] > 7u )
    v24 = (_QWORD *)v53[0];
  wil::str_printf<std::wstring>(
    v38,
    L"{\"data\":\"{\\\"apphelpBlock\\\":false,\\\"authenticode\\\":{\\\"hash\\\":\\\"%s\\\",\\\"hashAlgo\\\":\\\"%s\\\",\\"
     "\"issuer\\\":{\\\"hash\\\":\\\"\\\",\\\"subjectName\\\":\\\"\\\"},\\\"signer\\\":{\\\"hash\\\":\\\"\\\",\\\"subject"
     "Name\\\":\\\"\\\"},\\\"signing\\\":{\\\"message\\\":\\\"\\\",\\\"time\\\":\\\"\\\"},\\\"valid\\\":%s},\\\"binaryTyp"
     "e\\\":332,\\\"config\\\":{\\\"device\\\":{\\\"appReputation\\\":{\\\"enforcedByPolicy\\\":false,\\\"level\\\":\\\"w"
     "arn\\\"}},\\\"user\\\":{\\\"uriReputation\\\":{\\\"enforcedByPolicy\\\":false,\\\"level\\\":\\\"warn\\\"}}},\\\"cor"
     "relationId\\\":\\\"%s\\\",\\\"fileId\\\":\\\"%s\\\",\\\"hash\\\":null,\\\"identity\\\":{\\\"caller\\\":{\\\"locales"
     "\\\":[\\\"\\\",\\\"\\\"],\\\"process\\\":{\\\"application\\\":{\\\"$type\\\":\\\"\\\",\\\"path\\\":\\\"\\\"},\\\"cr"
     "eationTime\\\":\\\"\\\",\\\"id\\\":0}},\\\"client\\\":{\\\"data\\\":{\\\"offlineExperience\\\":\\\"\\\",\\\"script\\"
     "\":\\\"\\\"},\\\"version\\\":\\\"1\\\"},\\\"device\\\":{\\\"architecture\\\":%d,\\\"browser\\\":{\\\"edge\\\":\\\"\\"
     "\",\\\"internetExplorer\\\":\\\"\\\"},\\\"cloudSku\\\":%s,\\\"containerGuest\\\":false,\\\"enterprise\\\":null,\\\""
     "family\\\":3,\\\"locale\\\":\\\"\\\",\\\"netJoinStatus\\\":3,\\\"onlineIdTicket\\\":\\\"\\\",\\\"osVersion\\\":\\\""
     "%s\\\"},\\\"user\\\":{\\\"locale\\\":\\\"%s\\\",\\\"geo\\\":\\\"%s\\\"}},\\\"motw\\\":{\\\"hostUrl\\\":\\\"%s\\\",\\"
     "\"zoneId\\\":\\\"%s\\\",\\\"referrerUrl\\\":\\\"%s\\\"},\\\"path\\\":{\\\"driveType\\\":3,\\\"fileName\\\":\\\"%s\\"
     "\",\\\"originalFileName\\\":\\\"%s\\\",\\\"filePath\\\":\\\"%s\\\"},\\\"productName\\\":\\\"%s\\\",\\\"programId\\\""
     ":\\\"%s\\\",\\\"publisher\\\":\\\"%s\\\",\\\"ErrorCode\\\":\\\"%s\\\",\\\"FeedbackHubUri\\\":\\\"%s\\\",\\\"LearnMo"
     "reUri\\\":\\\"%s\\\",\\\"size\\\":0,\\\"uxEnabled\\\":true,\\\"verb\\\":\\\"open\\\",\\\"version\\\":\\\"%lld\\\"}\"}",
    v24,
    v23,
    v20,
    v22,
    v31,
    SystemInfo.wProcessorArchitecture,
    v21,
    v19,
    v18,
    v17,
    v16,
    v15,
    v14,
    FileNameW,
    v13,
    v28,
    v30,
    v29,
    v37,
    v36,
    v35,
    v34,
    v41);
  std::wstring::_Tidy_deallocate(v43);
  std::wstring::_Tidy_deallocate(v48);
  std::wstring::_Tidy_deallocate(v44);
  MarkOfTheWeb::~MarkOfTheWeb((MarkOfTheWeb *)v54);
  std::wstring::_Tidy_deallocate(v45);
  std::wstring::_Tidy_deallocate(v46);
  std::wstring::_Tidy_deallocate(v47);
  AUTHENTICODE_INFO::~AUTHENTICODE_INFO((AUTHENTICODE_INFO *)v50);
  std::wstring::_Tidy_deallocate(v42);
  wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&long PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&long PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>(&v32);
  return v38;
}

```

## disassembly

```asm
0x180021e84  mov     [rsp-8+arg_10], rbx
0x180021e89  push    rbp
0x180021e8a  push    rsi
0x180021e8b  push    rdi
0x180021e8c  push    r12
0x180021e8e  push    r13
0x180021e90  push    r14
0x180021e92  push    r15
0x180021e94  lea     rbp, [rsp-240h]
0x180021e9c  sub     rsp, 390h
0x180021ea3  mov     rax, cs:__security_cookie
0x180021eaa  xor     rax, rsp
0x180021ead  mov     [rbp+270h+var_40], rax
0x180021eb4  mov     [rbp+270h+var_2A0], r9
0x180021eb8  mov     rbx, rdx
0x180021ebb  mov     [rbp+270h+var_290], rcx
0x180021ebf  mov     [rbp+270h+var_2C0], rcx
0x180021ec3  mov     rax, [rbp+270h+arg_20]
0x180021eca  mov     [rbp+270h+var_2A8], rax
0x180021ece  mov     rax, [rbp+270h+arg_28]
0x180021ed5  mov     [rbp+270h+var_2B0], rax
0x180021ed9  xor     esi, esi
0x180021edb  mov     rcx, rdx; pszPath
0x180021ede  call    cs:__imp_PathFindFileNameW
0x180021ee4  mov     [rbp+270h+var_2C0], rax
0x180021ee8  mov     rdx, rbx
0x180021eeb  lea     rcx, [rbp+270h+var_2C8]
0x180021eef  call    ?GetAppFileInfo@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_INFO@@P6AJPEAU1@@Z$1?PicFreeFileInfo@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; GetAppFileInfo(ushort const *)
0x180021ef4  nop
0x180021ef5  mov     rax, [rbp+270h+var_2C8]
0x180021ef9  test    rax, rax
0x180021efc  jz      short loc_180021F17
0x180021efe  mov     rdi, [rax]
0x180021f01  mov     [rbp+270h+var_2D0], rdi
0x180021f05  mov     rdi, [rax+30h]
0x180021f09  mov     [rbp+270h+var_2D8], rdi
0x180021f0d  mov     rdi, [rax+8]
0x180021f11  mov     [rbp+270h+var_2E0], rdi
0x180021f15  jmp     short loc_180021F23
0x180021f17  mov     [rbp+270h+var_2D0], rsi
0x180021f1b  mov     [rbp+270h+var_2E0], rsi
0x180021f1f  mov     [rbp+270h+var_2D8], rsi
0x180021f23  mov     rdx, rbx
0x180021f26  lea     rcx, [rbp+270h+var_238]
0x180021f2a  call    ?GetAppFileVersionInfo@@YA?AUFILE_VERSION_INFO@@PEBG@Z; GetAppFileVersionInfo(ushort const *)
0x180021f2f  nop
0x180021f30  mov     rdx, rbx
0x180021f33  lea     rcx, [rbp+270h+var_130]
0x180021f3a  call    ?GetAppFileCertInfo@@YA?AUAUTHENTICODE_INFO@@PEBG@Z; GetAppFileCertInfo(ushort const *)
0x180021f3f  nop
0x180021f40  lea     rcx, [rbp+270h+var_190]
0x180021f47  call    ?GetOSRegion@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4RegionLookupFallbackOptions@@@Z; GetOSRegion(RegionLookupFallbackOptions)
0x180021f4c  nop
0x180021f4d  lea     rcx, [rbp+270h+var_1B0]
0x180021f54  call    ?GetOSVersion@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetOSVersion(void)
0x180021f59  nop
0x180021f5a  lea     rcx, [rbp+270h+var_1D0]
0x180021f61  call    ?GetLocale@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetLocale(void)
0x180021f66  nop
0x180021f67  mov     rdx, rbx
0x180021f6a  lea     rcx, [rbp+270h+var_150]
0x180021f71  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021f76  nop
0x180021f77  lea     r8, aZoneIdentifier; ":Zone.Identifier"
0x180021f7e  mov     rdx, rax
0x180021f81  lea     rcx, [rbp+270h+var_170]
0x180021f88  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180021f8d  nop
0x180021f8e  mov     rdx, rax
0x180021f91  lea     rcx, [rbp+270h+var_C0]
0x180021f98  call    ?GetMarkOfTheWebFromFile@@YA?AUMarkOfTheWeb@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetMarkOfTheWebFromFile(std::wstring const &)
0x180021f9d  nop
0x180021f9e  lea     rcx, [rbp+270h+var_170]
0x180021fa5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021faa  nop
0x180021fab  lea     rcx, [rbp+270h+var_150]
0x180021fb2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021fb7  lea     rcx, [rbp+270h+var_1F0]
0x180021fbe  call    ?GetCorrelationId@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetCorrelationId(void)
0x180021fc3  nop
0x180021fc4  xorps   xmm0, xmm0
0x180021fc7  movups  xmmword ptr [rbp+270h+SystemInfo], xmm0
0x180021fcb  movups  xmmword ptr [rbp+270h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180021fcf  movups  xmmword ptr [rbp+270h+SystemInfo.dwNumberOfProcessors], xmm0
0x180021fd3  lea     rcx, [rbp+270h+SystemInfo]; lpSystemInfo
0x180021fd7  call    cs:__imp_GetNativeSystemInfo
0x180021fdd  mov     [rbp+270h+var_2F0], esi
0x180021fe0  lea     rcx, [rbp+270h+var_2F0]
0x180021fe4  call    cs:__imp_?WldpQueryWindowsLockdownMode@@YAJPEAW4WLDP_WINDOWS_LOCKDOWN_MODE@@@Z; WldpQueryWindowsLockdownMode(WLDP_WINDOWS_LOCKDOWN_MODE *)
0x180021fea  mov     rcx, [rbp+278h]; this
0x180021ff1  test    eax, eax
0x180021ff3  jns     short loc_18002200A
0x180021ff5  mov     r9d, eax; char *
0x180021ff8  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180021fff  mov     edx, 2BAh; void *
0x180022004  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002200a  cmp     [rbp+270h+var_2F0], esi
0x18002200d  setnz   r13b
0x180022011  mov     rdx, rbx
0x180022014  lea     rcx, [rbp+270h+var_170]
0x18002201b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022020  nop
0x180022021  lea     rdx, [rbp+270h+var_170]
0x180022028  lea     rcx, [rbp+270h+var_150]
0x18002202f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022034  mov     rdx, rax
0x180022037  lea     rcx, [rbp+270h+Src]; Src
0x18002203b  call    ?EscapeFilePathForJson@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; EscapeFilePathForJson(std::wstring)
0x180022040  mov     rdx, rax
0x180022043  lea     rcx, [rbp+270h+var_210]; Src
0x180022047  call    ?EscapeFilePathForJson@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; EscapeFilePathForJson(std::wstring)
0x18002204c  nop
0x18002204d  lea     rax, [rbp+270h+var_128]
0x180022054  mov     r8d, 7
0x18002205a  cmp     [rbp+270h+var_110], r8
0x180022061  cmova   rax, [rbp+270h+var_128]
0x180022069  mov     [rbp+270h+var_298], rax
0x18002206d  lea     rax, [rbp+270h+var_210]
0x180022071  cmp     [rbp+270h+var_1F8], r8
0x180022075  cmova   rax, [rbp+270h+var_210]
0x18002207a  mov     [rbp+270h+var_2E8], rax
0x18002207e  lea     r12, [rbp+270h+var_230]
0x180022082  cmp     [rbp+270h+var_218], r8
0x180022086  cmova   r12, [rbp+270h+var_230]
0x18002208b  lea     r15, [rbp+270h+var_60]
0x180022092  cmp     [rbp+270h+var_48], r8
0x180022099  cmova   r15, [rbp+270h+var_60]
0x1800220a1  lea     r14, [rbp+270h+var_C0]
0x1800220a8  cmp     [rbp+270h+var_A8], r8
0x1800220af  cmova   r14, [rbp+270h+var_C0]
0x1800220b7  lea     rsi, [rbp+270h+var_A0]
0x1800220be  cmp     [rbp+270h+var_88], r8
0x1800220c5  cmova   rsi, [rbp+270h+var_A0]
0x1800220cd  lea     rdi, [rbp+270h+var_190]
0x1800220d4  cmp     [rbp+270h+var_178], r8
0x1800220db  cmova   rdi, [rbp+270h+var_190]
0x1800220e3  lea     rbx, [rbp+270h+var_1D0]
0x1800220ea  cmp     [rbp+270h+var_1B8], r8
0x1800220f1  cmova   rbx, [rbp+270h+var_1D0]
0x1800220f9  lea     r11, [rbp+270h+var_1B0]
0x180022100  cmp     [rbp+270h+var_198], r8
0x180022107  cmova   r11, [rbp+270h+var_1B0]
0x18002210f  lea     rax, aFalse; "false"
0x180022116  lea     r10, aTrue; "true"
0x18002211d  mov     rdx, r10
0x180022120  test    r13b, r13b
0x180022123  cmovz   rdx, rax
0x180022127  lea     rcx, [rbp+270h+var_1F0]
0x18002212e  cmp     [rbp+270h+var_1D8], r8
0x180022135  cmova   rcx, [rbp+270h+var_1F0]
0x18002213d  cmp     [rbp+270h+var_130], 0
0x180022144  cmovz   r10, rax
0x180022148  lea     r9, [rbp+270h+var_108]
0x18002214f  cmp     [rbp+270h+var_F0], r8
0x180022156  cmova   r9, [rbp+270h+var_108]
0x18002215e  lea     r8, [rbp+270h+var_E8]
0x180022165  cmp     [rbp+270h+var_D0], 7
0x18002216d  cmova   r8, [rbp+270h+var_E8]
0x180022175  mov     rax, [rbp+270h+var_238]
0x180022179  mov     [rsp+3C0h+var_300], rax
0x180022181  mov     rax, [rbp+270h+var_2B0]
0x180022185  mov     [rsp+3C0h+var_308], rax
0x18002218d  mov     rax, [rbp+270h+var_2A8]
0x180022191  mov     [rsp+3C0h+var_310], rax
0x180022199  mov     rax, [rbp+270h+var_2A0]
0x18002219d  mov     [rsp+3C0h+var_318], rax
0x1800221a5  mov     rax, [rbp+270h+var_298]
0x1800221a9  mov     [rsp+3C0h+var_320], rax
0x1800221b1  mov     rax, [rbp+270h+var_2E0]
0x1800221b5  mov     [rsp+3C0h+var_328], rax
0x1800221bd  mov     rax, [rbp+270h+var_2D8]
0x1800221c1  mov     [rsp+3C0h+var_330], rax
0x1800221c9  mov     rax, [rbp+270h+var_2E8]
0x1800221cd  mov     [rsp+3C0h+var_338], rax
0x1800221d5  mov     [rsp+3C0h+var_340], r12
0x1800221dd  mov     rax, [rbp+270h+var_2C0]
0x1800221e1  mov     [rsp+3C0h+var_348], rax
0x1800221e6  mov     [rsp+3C0h+var_350], r15
0x1800221eb  mov     [rsp+3C0h+var_358], r14
0x1800221f0  mov     [rsp+3C0h+var_360], rsi
0x1800221f5  mov     [rsp+3C0h+var_368], rdi
0x1800221fa  mov     [rsp+3C0h+var_370], rbx
0x1800221ff  mov     [rsp+3C0h+var_378], r11
0x180022204  mov     [rsp+3C0h+var_380], rdx
0x180022209  movzx   eax, word ptr [rbp+270h+SystemInfo]
0x18002220d  mov     [rsp+3C0h+var_388], eax
0x180022211  mov     rax, [rbp+270h+var_2D0]
0x180022215  mov     [rsp+3C0h+var_390], rax
0x18002221a  mov     [rsp+3C0h+var_398], rcx
0x18002221f  mov     [rsp+3C0h+var_3A0], r10
0x180022224  lea     rdx, aDataApphelpblo; "{\"data\":\"{\\\"apphelpBlock\\\":false"...
0x18002222b  mov     rcx, [rbp+270h+var_290]
0x18002222f  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180022234  nop
0x180022235  lea     rcx, [rbp+270h+var_210]
0x180022239  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002223e  nop
0x18002223f  lea     rcx, [rbp+270h+var_170]
0x180022246  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002224b  nop
0x18002224c  lea     rcx, [rbp+270h+var_1F0]
0x180022253  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022258  nop
0x180022259  lea     rcx, [rbp+270h+var_C0]; this
0x180022260  call    ??1MarkOfTheWeb@@QEAA@XZ; MarkOfTheWeb::~MarkOfTheWeb(void)
0x180022265  nop
0x180022266  lea     rcx, [rbp+270h+var_1D0]
0x18002226d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022272  nop
0x180022273  lea     rcx, [rbp+270h+var_1B0]
0x18002227a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002227f  nop
0x180022280  lea     rcx, [rbp+270h+var_190]
0x180022287  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002228c  nop
0x18002228d  lea     rcx, [rbp+270h+var_130]; this
0x180022294  call    ??1AUTHENTICODE_INFO@@QEAA@XZ; AUTHENTICODE_INFO::~AUTHENTICODE_INFO(void)
0x180022299  nop
0x18002229a  lea     rcx, [rbp+270h+var_230]
0x18002229e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800222a3  nop
0x1800222a4  lea     rcx, [rbp+270h+var_2C8]
0x1800222a8  call    ??1?$unique_storage@U?$resource_policy@PEAU_FILE_INFO@@P6AJPEAU1@@Z$1?PicFreeFileInfo@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>(void)
0x1800222ad  mov     rax, [rbp+270h+var_290]
0x1800222b1  mov     rcx, [rbp+270h+var_40]
0x1800222b8  xor     rcx, rsp; StackCookie
0x1800222bb  call    __security_check_cookie
0x1800222c0  mov     rbx, [rsp+3C0h+arg_10]
0x1800222c8  add     rsp, 390h
0x1800222cf  pop     r15
0x1800222d1  pop     r14
0x1800222d3  pop     r13
0x1800222d5  pop     r12
0x1800222d7  pop     rdi
0x1800222d8  pop     rsi
0x1800222d9  pop     rbp
0x1800222da  retn
```
