# Microsoft::Diagnostics::SettingsManager::CopyDefinedInboxSettingsToMutableDirectory(void)

- ea: `0x18018ea94`
- end: `0x18018ed72`
- name: `?CopyDefinedInboxSettingsToMutableDirectory@SettingsManager@Diagnostics@Microsoft@@AEAAXXZ`
- size: `734`
- prototype: `void __fastcall(Microsoft::Diagnostics::SettingsManager *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18018be10`

## callees

- `0x180001bf4`
- `0x18001d160`
- `0x180020fbc`
- `0x180030a50`
- `0x180035698`
- `0x180048ff4`
- `0x18005d050`
- `0x180099fb4`
- `0x1800aac70`
- `0x18012de40`
- `0x180161298`
- `0x18018ea94`
- `0x18018ed78`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018eb95`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018ec1f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018eb95`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018ec1f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18018ec56`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18018ecd2`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18018ec56`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18018ecd2`

## string_xrefs

- `0x18018eceb`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18018eb77`: `.json`
- `0x18018ec01`: `.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::Diagnostics::SettingsManager::CopyDefinedInboxSettingsToMutableDirectory(
        Microsoft::Diagnostics::SettingsManager *this)
{
  __int128 *v1; // rbx
  __int64 v2; // rax
  const WCHAR *v3; // rcx
  __int64 v4; // rax
  const WCHAR *v5; // rcx
  const WCHAR *v6; // rdx
  const WCHAR *v7; // rcx
  const char *v8; // r9
  __int64 v9; // rdx
  wil::details::in1diag3 *v10; // rcx
  const WCHAR *v11; // rdx
  const WCHAR *v12; // rcx
  BOOL v13; // eax
  __int128 v14; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v15[6]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v16; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[16]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpNewFileName[3]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v19; // [rsp+98h] [rbp-68h]
  LPCWSTR lpFileName[3]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v21; // [rsp+B8h] [rbp-48h]
  _QWORD v22[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD Src[4]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+18h]

  v15[0] = L"utc.app";
  v15[1] = 7;
  v15[2] = L"telemetry.ASM-WindowsDefault";
  v15[3] = 28;
  v15[4] = L"utc.tracing";
  v15[5] = 11;
  v1 = (__int128 *)v15;
  do
  {
    v14 = *v1;
    Microsoft::Diagnostics::SettingsManager::CopyInboxSettingsForNamespaceToMutableDirectory(this, &v14);
    ++v1;
  }
  while ( v1 != &v16 );
  std::wstring::wstring((__int64)Src, &off_18035F290);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src, 1, 0);
  v2 = std::wstring::_Append<wchar_t>(Src);
  std::wstring::wstring(lpFileName, v2);
  std::wstring::_Append<wchar_t>(lpFileName);
  std::wstring::_Append<wchar_t>(lpFileName);
  v3 = (const WCHAR *)lpFileName;
  if ( v21 > 7 )
    v3 = lpFileName[0];
  if ( GetFileAttributesW(v3) != -1 )
  {
    std::wstring::wstring((__int64)v22, &off_18035F280);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v22, 1, 0);
    v4 = std::wstring::_Append<wchar_t>(v22);
    std::wstring::wstring(lpNewFileName, v4);
    std::wstring::_Append<wchar_t>(lpNewFileName);
    std::wstring::_Append<wchar_t>(lpNewFileName);
    v5 = (const WCHAR *)lpNewFileName;
    if ( v19 > 7 )
      v5 = lpNewFileName[0];
    if ( GetFileAttributesW(v5) == -1 )
    {
      v6 = (const WCHAR *)lpNewFileName;
      if ( v19 > 7 )
        v6 = lpNewFileName[0];
      v7 = (const WCHAR *)lpFileName;
      if ( v21 > 7 )
        v7 = lpFileName[0];
      if ( !CopyFileW(v7, v6, 1) )
      {
        v9 = 285;
        v10 = retaddr;
LABEL_23:
        wil::details::in1diag3::_Log_GetLastError(
          v10,
          (void *)v9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
          v8);
LABEL_27:
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpNewFileName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v22);
        goto LABEL_28;
      }
    }
    else
    {
      *(_QWORD *)&v14 = 0;
      v16 = *(_OWORD *)std::wstring::operator std::wstring_view(lpNewFileName, v17);
      if ( (int)Microsoft::Diagnostics::Utils::FileSystem::ReadFileSize(&v16, &v14) < 0 || (__int64)v14 >= 100 )
        goto LABEL_27;
      v11 = (const WCHAR *)lpNewFileName;
      if ( v19 > 7 )
        v11 = lpNewFileName[0];
      v12 = (const WCHAR *)lpFileName;
      if ( v21 > 7 )
        v12 = lpFileName[0];
      v13 = CopyFileW(v12, v11, 0);
      v10 = retaddr;
      if ( !v13 )
      {
        v9 = 294;
        goto LABEL_23;
      }
    }
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18042D328,
        &unk_1803C4380);
    goto LABEL_27;
  }
LABEL_28:
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
}

```

## disassembly

```asm
0x18018ea94  mov     [rsp-8+arg_0], rbx
0x18018ea99  push    rbp
0x18018ea9a  lea     rbp, [rsp-10h]
0x18018ea9f  sub     rsp, 110h
0x18018eaa6  mov     rax, cs:__security_cookie
0x18018eaad  xor     rax, rsp
0x18018eab0  mov     [rbp+10h+var_10], rax
0x18018eab4  lea     rax, aUtcApp; "utc.app"
0x18018eabb  mov     [rsp+110h+var_E0], rax
0x18018eac0  mov     [rsp+110h+var_D8], 7
0x18018eac9  lea     rax, aTelemetryAsmWi; "telemetry.ASM-WindowsDefault"
0x18018ead0  mov     [rsp+110h+var_D0], rax
0x18018ead5  mov     [rsp+110h+var_C8], 1Ch
0x18018eade  lea     rax, aUtcTracing; "utc.tracing"
0x18018eae5  mov     [rsp+110h+var_C0], rax
0x18018eaea  mov     [rsp+110h+var_B8], 0Bh
0x18018eaf3  lea     rbx, [rsp+110h+var_E0]
0x18018eaf8  movups  xmm0, xmmword ptr [rbx]
0x18018eafb  movdqu  [rsp+110h+var_F0], xmm0
0x18018eb01  lea     rdx, [rsp+110h+var_F0]
0x18018eb06  call    ?CopyInboxSettingsForNamespaceToMutableDirectory@SettingsManager@Diagnostics@Microsoft@@AEAA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::SettingsManager::CopyInboxSettingsForNamespaceToMutableDirectory(std::wstring_view)
0x18018eb0b  add     rbx, 10h
0x18018eb0f  lea     rax, [rsp+110h+var_B0]
0x18018eb14  cmp     rbx, rax
0x18018eb17  jnz     short loc_18018EAF8
0x18018eb19  lea     rdx, off_18035F290; "%WinDir%\\DiagTrack\\Settings"
0x18018eb20  lea     rcx, [rbp+10h+Src]
0x18018eb24  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18018eb29  nop
0x18018eb2a  xor     r8d, r8d
0x18018eb2d  mov     dl, 1
0x18018eb2f  lea     rcx, [rbp+10h+Src]; lpSrc
0x18018eb33  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18018eb38  mov     r8d, 1
0x18018eb3e  lea     rdx, asc_1803772C8; "\\"
0x18018eb45  lea     rcx, [rbp+10h+Src]; Src
0x18018eb49  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18018eb4e  mov     rdx, rax
0x18018eb51  lea     rcx, [rbp+10h+lpFileName]
0x18018eb55  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18018eb5a  nop
0x18018eb5b  mov     ebx, 9
0x18018eb60  mov     r8d, ebx
0x18018eb63  lea     rdx, aUtcAllow; "utc.allow"
0x18018eb6a  lea     rcx, [rbp+10h+lpFileName]; Src
0x18018eb6e  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18018eb73  lea     r8d, [rbx-4]
0x18018eb77  lea     rdx, aJson_0; ".json"
0x18018eb7e  lea     rcx, [rbp+10h+lpFileName]; Src
0x18018eb82  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18018eb87  lea     rcx, [rbp+10h+lpFileName]
0x18018eb8b  cmp     [rbp+10h+var_58], 7
0x18018eb90  cmova   rcx, [rbp+10h+lpFileName]; lpFileName
0x18018eb95  call    cs:__imp_GetFileAttributesW
0x18018eb9c  nop     dword ptr [rax+rax+00h]
0x18018eba1  cmp     eax, 0FFFFFFFFh
0x18018eba4  jz      loc_18018ED41
0x18018ebaa  lea     rdx, off_18035F280; "%DiagtrackStorageRoot%\\DownloadedSetti"...
0x18018ebb1  lea     rcx, [rbp+10h+var_50]
0x18018ebb5  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18018ebba  nop
0x18018ebbb  xor     r8d, r8d
0x18018ebbe  mov     dl, 1
0x18018ebc0  lea     rcx, [rbp+10h+var_50]; lpSrc
0x18018ebc4  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18018ebc9  lea     r8d, [rbx-8]
0x18018ebcd  lea     rdx, asc_1803772C8; "\\"
0x18018ebd4  lea     rcx, [rbp+10h+var_50]; Src
0x18018ebd8  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18018ebdd  mov     rdx, rax
0x18018ebe0  lea     rcx, [rbp+10h+lpNewFileName]
0x18018ebe4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18018ebe9  nop
0x18018ebea  mov     r8d, ebx
0x18018ebed  lea     rdx, aUtcAllow; "utc.allow"
0x18018ebf4  lea     rcx, [rbp+10h+lpNewFileName]; Src
0x18018ebf8  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18018ebfd  lea     r8d, [rbx-4]
0x18018ec01  lea     rdx, aJson_0; ".json"
0x18018ec08  lea     rcx, [rbp+10h+lpNewFileName]; Src
0x18018ec0c  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18018ec11  lea     rcx, [rbp+10h+lpNewFileName]
0x18018ec15  cmp     [rbp+10h+var_78], 7
0x18018ec1a  cmova   rcx, [rbp+10h+lpNewFileName]; lpFileName
0x18018ec1f  call    cs:__imp_GetFileAttributesW
0x18018ec26  nop     dword ptr [rax+rax+00h]
0x18018ec2b  cmp     eax, 0FFFFFFFFh
0x18018ec2e  jnz     short loc_18018EC74
0x18018ec30  lea     rdx, [rbp+10h+lpNewFileName]
0x18018ec34  cmp     [rbp+10h+var_78], 7
0x18018ec39  cmova   rdx, [rbp+10h+lpNewFileName]; lpNewFileName
0x18018ec3e  lea     rcx, [rbp+10h+lpFileName]
0x18018ec42  cmp     [rbp+10h+var_58], 7
0x18018ec47  cmova   rcx, [rbp+10h+lpFileName]; lpExistingFileName
0x18018ec4c  mov     rbx, [rbp+18h]
0x18018ec50  mov     r8d, 1; bFailIfExists
0x18018ec56  call    cs:__imp_CopyFileW
0x18018ec5d  nop     dword ptr [rax+rax+00h]
0x18018ec62  test    eax, eax
0x18018ec64  jnz     loc_18018ECF9
0x18018ec6a  mov     edx, 11Dh
0x18018ec6f  mov     rcx, rbx
0x18018ec72  jmp     short loc_18018ECEB
0x18018ec74  mov     qword ptr [rsp+110h+var_F0], 0
0x18018ec7d  lea     rdx, [rsp+110h+var_A0]
0x18018ec82  lea     rcx, [rbp+10h+lpNewFileName]
0x18018ec86  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018ec8b  movups  xmm0, xmmword ptr [rax]
0x18018ec8e  movdqu  [rsp+110h+var_B0], xmm0
0x18018ec94  lea     rdx, [rsp+110h+var_F0]
0x18018ec99  lea     rcx, [rsp+110h+var_B0]
0x18018ec9e  call    ?ReadFileSize@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEA_J@Z; Microsoft::Diagnostics::Utils::FileSystem::ReadFileSize(std::wstring_view,__int64 &)
0x18018eca3  test    eax, eax
0x18018eca5  js      loc_18018ED2D
0x18018ecab  cmp     qword ptr [rsp+110h+var_F0], 64h ; 'd'
0x18018ecb1  jge     short loc_18018ED2D
0x18018ecb3  lea     rdx, [rbp+10h+lpNewFileName]
0x18018ecb7  cmp     [rbp+10h+var_78], 7
0x18018ecbc  cmova   rdx, [rbp+10h+lpNewFileName]; lpNewFileName
0x18018ecc1  lea     rcx, [rbp+10h+lpFileName]
0x18018ecc5  cmp     [rbp+10h+var_58], 7
0x18018ecca  cmova   rcx, [rbp+10h+lpFileName]; lpExistingFileName
0x18018eccf  xor     r8d, r8d; bFailIfExists
0x18018ecd2  call    cs:__imp_CopyFileW
0x18018ecd9  nop     dword ptr [rax+rax+00h]
0x18018ecde  mov     rcx, [rbp+18h]; this
0x18018ece2  test    eax, eax
0x18018ece4  jnz     short loc_18018ECF9
0x18018ece6  mov     edx, 126h; void *
0x18018eceb  lea     r8, aOnecoreBaseTel_84; "onecore\\base\\telemetry\\utc\\service"...
0x18018ecf2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18018ecf7  jmp     short loc_18018ED2D
0x18018ecf9  mov     eax, cs:dword_18042D328
0x18018ecff  cmp     eax, 4
0x18018ed02  jbe     short loc_18018ED2D
0x18018ed04  mov     edx, 200h
0x18018ed09  lea     rcx, dword_18042D328
0x18018ed10  call    _tlgKeywordOn
0x18018ed15  test    al, al
0x18018ed17  jz      short loc_18018ED2D
0x18018ed19  lea     rdx, unk_1803C4380
0x18018ed20  lea     rcx, dword_18042D328
0x18018ed27  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18018ed2c  nop
0x18018ed2d  lea     rcx, [rbp+10h+lpNewFileName]; this
0x18018ed31  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18018ed36  nop
0x18018ed37  lea     rcx, [rbp+10h+var_50]; this
0x18018ed3b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18018ed40  nop
0x18018ed41  lea     rcx, [rbp+10h+lpFileName]; this
0x18018ed45  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18018ed4a  nop
0x18018ed4b  lea     rcx, [rbp+10h+Src]; this
0x18018ed4f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18018ed54  mov     rcx, [rbp+10h+var_10]
0x18018ed58  xor     rcx, rsp; StackCookie
0x18018ed5b  call    __security_check_cookie
0x18018ed60  mov     rbx, [rsp+110h+arg_0]
0x18018ed68  add     rsp, 110h
0x18018ed6f  pop     rbp
0x18018ed70  retn
```
