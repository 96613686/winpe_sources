# Microsoft::Diagnostics::RADARActionDef::LaunchRADARProcess(Microsoft::Diagnostics::ScenarioInst const &,Microsoft::Diagnostics::EscalationWorkItemState &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::optional<unsigned __int64>)

- ea: `0x1802fafb0`
- end: `0x1802fb3fd`
- name: `?LaunchRADARProcess@RADARActionDef@Diagnostics@Microsoft@@SAXAEBVScenarioInst@23@AEAVEscalationWorkItemState@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2V?$optional@_K@7@@Z`
- size: `1101`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802f4bb0`
- `0x1802fae70`
- `0x1802fe120`

## callees

- `0x180002058`
- `0x1800035ec`
- `0x18001d160`
- `0x18001d200`
- `0x18001d5ac`
- `0x18001e638`
- `0x18001ee94`
- `0x18001f1fc`
- `0x180020fbc`
- `0x180030a50`
- `0x180032718`
- `0x180034d94`
- `0x180048ff4`
- `0x1800495cc`
- `0x18005d050`
- `0x180086f40`
- `0x18008a284`
- `0x1800a1e24`
- `0x1800b10c8`
- `0x1800b1a08`
- `0x1800bc2e0`
- `0x1800e296c`
- `0x18012de40`
- `0x18012eb08`
- `0x1802fafb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802fb366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802fb366`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1802fb2bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1802fb2bb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802fb079`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802fb079`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1802fb106`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1802fb106`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1802fb0ee`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1802fb0ee`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1802fb0ab`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1802fb0ab`

## string_xrefs

- `0x1802fb33f`: `onecore\base\telemetry\utc\service\scenarios\actions\radaraction.cpp`
- `0x1802fb351`: `onecore\base\telemetry\utc\service\scenarios\actions\radaraction.cpp`
- `0x1802fb3d3`: `onecore\base\telemetry\utc\service\scenarios\actions\radaraction.cpp`
- `0x1802fb3eb`: `onecore\base\telemetry\utc\service\scenarios\actions\radaraction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Diagnostics::RADARActionDef::LaunchRADARProcess(
        __int64 a1,
        __int64 a2,
        __m128i *a3,
        _OWORD *a4,
        __int64 a5)
{
  DWORD v7; // edi
  void *v8; // rbx
  __int64 v9; // rax
  void *v10; // rax
  HANDLE v11; // rcx
  const char *v12; // r9
  WCHAR *v13; // rcx
  UINT SystemWow64Directory2W; // eax
  UINT v15; // ecx
  __int64 v16; // rdx
  LPWSTR *v17; // rax
  char v18; // al
  void *appended; // rax
  __int64 v20; // rax
  void *v21; // rax
  void *v22; // rax
  _QWORD *v23; // rax
  int v24; // r8d
  int v25; // r9d
  WCHAR *v26; // rdx
  const char *v27; // r9
  signed int LastError; // eax
  unsigned int v30; // ebx
  int v31; // r8d
  int v32; // r9d
  unsigned int v33; // eax
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  __int16 v35; // [rsp+50h] [rbp-B0h] BYREF
  int v36[6]; // [rsp+58h] [rbp-A8h] BYREF
  __m128i v37; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+110h] [rbp+10h] BYREF
  UINT uSize[2]; // [rsp+120h] [rbp+20h]
  unsigned __int64 v42; // [rsp+128h] [rbp+28h]
  _OWORD v43[2]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR Src[16]; // [rsp+150h] [rbp+50h] BYREF
  LPWSTR lpCommandLine[6]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  if ( a3->m128i_i64[1] )
  {
    v37 = *a3;
    Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a1, v43, &v37);
    v7 = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v43);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v43);
  }
  else
  {
    v7 = 0;
  }
  v8 = (void *)(a2 + 168);
  v9 = Microsoft::Diagnostics::WideStringStream::operator<<(v8);
  Microsoft::Diagnostics::WideStringStream::operator<<(v9, v7);
  if ( *(_BYTE *)(a5 + 8) )
  {
    v10 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v8);
    Microsoft::Diagnostics::WideStringStream::operator<<(v10);
  }
  Microsoft::Diagnostics::WideStringStream::operator<<(v8);
  v11 = OpenProcess(0x400u, 0, v7);
  if ( !v11 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\radaraction.cpp",
      v12);
  v37.m128i_i64[0] = (__int64)v11;
  v35 = 0;
  if ( !(unsigned int)IsWow64Process2(v11, &v35, 0) )
  {
    LastError = GetLastError();
    v30 = LastError;
    if ( LastError > 0 )
      v30 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 262148) )
    {
      v36[0] = v30;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803DF881,
        v31,
        v32,
        (__int64)v36);
    }
    v33 = wil::verify_hresult<long>(v30);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\radaraction.cpp",
      (const char *)v33,
      bInheritHandles);
  }
  std::wstring::wstring(lpBuffer, 260, 0);
  v13 = (WCHAR *)lpBuffer;
  if ( v35 )
  {
    if ( v42 > 7 )
      v13 = lpBuffer[0];
    SystemWow64Directory2W = GetSystemWow64Directory2W(v13, uSize[0]);
  }
  else
  {
    if ( v42 > 7 )
      v13 = lpBuffer[0];
    SystemWow64Directory2W = GetSystemDirectoryW(v13, uSize[0]);
  }
  v15 = SystemWow64Directory2W;
  if ( !SystemWow64Directory2W )
    goto LABEL_21;
  v16 = SystemWow64Directory2W;
  if ( (unsigned __int64)SystemWow64Directory2W >= *(_QWORD *)uSize )
    goto LABEL_21;
  v17 = lpBuffer;
  if ( v42 > 7 )
    v17 = (LPWSTR *)lpBuffer[0];
  if ( *(_WORD *)v17 )
  {
    v18 = 0;
  }
  else
  {
LABEL_21:
    v18 = 1;
    v16 = v15;
  }
  if ( v18 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\radaraction.cpp",
      (const char *)0x800700A1LL,
      bInheritHandles);
  std::wstring::resize(lpBuffer, v16);
  std::wstring::wstring(Src, lpBuffer);
  *(_QWORD *)&v43[0] = L"RdrLeakDiag.exe";
  *((_QWORD *)&v43[0] + 1) = 15;
  Microsoft::Diagnostics::Utils::String::AppendPath(Src);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)lpCommandLine);
  v43[0] = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v36);
  appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpCommandLine);
  v20 = Microsoft::Diagnostics::WideStringStream::operator<<(appended);
  v21 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v20, v7);
  v22 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v21);
  v43[0] = *a4;
  Microsoft::Diagnostics::WideStringStream::AppendString(v22);
  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 262148) )
  {
    v23 = (_QWORD *)Microsoft::Diagnostics::WideStringStream::str(lpCommandLine, v43);
    if ( v23[3] > 7u )
      v23 = (_QWORD *)*v23;
    *(_QWORD *)v36 = v23;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_18042D328,
      (unsigned int)&unk_1803DF84D,
      v24,
      v25,
      (__int64)v36);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v43);
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v26 = (WCHAR *)lpCommandLine;
  if ( lpCommandLine[3] > (LPWSTR)7 )
    v26 = lpCommandLine[0];
  if ( !CreateProcessW(0, v26, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\radaraction.cpp",
      v27);
  *(_QWORD *)&v43[0] = ProcessInformation.hProcess;
  *(_QWORD *)v36 = ProcessInformation.hThread;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v36);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v43);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpCommandLine);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v37);
}

```

## disassembly

```asm
0x1802fafb0  push    rbp
0x1802fafb2  push    rbx
0x1802fafb3  push    rsi
0x1802fafb4  push    rdi
0x1802fafb5  push    r14
0x1802fafb7  push    r15
0x1802fafb9  lea     rbp, [rsp-0B8h]
0x1802fafc1  sub     rsp, 1B8h
0x1802fafc8  mov     rax, cs:__security_cookie
0x1802fafcf  xor     rax, rsp
0x1802fafd2  mov     [rbp+0E0h+var_40], rax
0x1802fafd9  mov     r14, r9
0x1802fafdc  mov     rbx, rdx
0x1802fafdf  mov     rsi, [rbp+0E0h+arg_20]
0x1802fafe6  xor     r15d, r15d
0x1802fafe9  cmp     [r8+8], r15
0x1802fafed  jnz     short loc_1802FAFF4
0x1802fafef  mov     edi, r15d
0x1802faff2  jmp     short loc_1802FB020
0x1802faff4  movups  xmm0, xmmword ptr [r8]
0x1802faff8  movdqu  [rsp+1E0h+var_170], xmm0
0x1802faffe  lea     r8, [rsp+1E0h+var_170]
0x1802fb003  lea     rdx, [rbp+0E0h+var_B0]
0x1802fb007  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x1802fb00c  lea     rcx, [rbp+0E0h+var_B0]
0x1802fb010  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x1802fb015  mov     edi, eax
0x1802fb017  lea     rcx, [rbp+0E0h+var_B0]; this
0x1802fb01b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802fb020  add     rbx, 0A8h
0x1802fb027  lea     rdx, aPid_4; "PID: "
0x1802fb02e  mov     rcx, rbx; Src
0x1802fb031  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802fb036  mov     edx, edi
0x1802fb038  mov     rcx, rax
0x1802fb03b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1802fb040  cmp     [rsi+8], r15b
0x1802fb044  jz      short loc_1802FB060
0x1802fb046  lea     rdx, aWaitTimeMin; "; Wait Time (min): "
0x1802fb04d  mov     rcx, rbx; Src
0x1802fb050  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802fb055  mov     rdx, [rsi]
0x1802fb058  mov     rcx, rax; Src
0x1802fb05b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x1802fb060  lea     rdx, asc_1803721B4; "\r\n"
0x1802fb067  mov     rcx, rbx; Src
0x1802fb06a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802fb06f  mov     r8d, edi; dwProcessId
0x1802fb072  xor     edx, edx; bInheritHandle
0x1802fb074  mov     ecx, 400h; dwDesiredAccess
0x1802fb079  call    cs:__imp_OpenProcess
0x1802fb080  nop     dword ptr [rax+rax+00h]
0x1802fb085  mov     rcx, rax
0x1802fb088  mov     rax, [rbp+0E8h]
0x1802fb08f  test    rcx, rcx
0x1802fb092  jz      loc_1802FB351
0x1802fb098  mov     qword ptr [rsp+1E0h+var_170], rcx
0x1802fb09d  mov     [rsp+1E0h+var_190], r15w
0x1802fb0a3  xor     r8d, r8d
0x1802fb0a6  lea     rdx, [rsp+1E0h+var_190]
0x1802fb0ab  call    cs:__imp_IsWow64Process2
0x1802fb0b2  nop     dword ptr [rax+rax+00h]
0x1802fb0b7  test    eax, eax
0x1802fb0b9  jz      loc_1802FB366
0x1802fb0bf  xor     r8d, r8d
0x1802fb0c2  mov     edx, 104h
0x1802fb0c7  lea     rcx, [rbp+0E0h+lpBuffer]
0x1802fb0cb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1802fb0d0  nop
0x1802fb0d1  movzx   r8d, [rsp+1E0h+var_190]
0x1802fb0d7  lea     rcx, [rbp+0E0h+lpBuffer]
0x1802fb0db  mov     edx, [rbp+0E0h+uSize]; uSize
0x1802fb0de  test    r8w, r8w
0x1802fb0e2  jz      short loc_1802FB0FC
0x1802fb0e4  cmp     [rbp+0E0h+var_B8], 7
0x1802fb0e9  cmova   rcx, [rbp+0E0h+lpBuffer]
0x1802fb0ee  call    cs:__imp_GetSystemWow64Directory2W
0x1802fb0f5  nop     dword ptr [rax+rax+00h]
0x1802fb0fa  jmp     short loc_1802FB112
0x1802fb0fc  cmp     [rbp+0E0h+var_B8], 7
0x1802fb101  cmova   rcx, [rbp+0E0h+lpBuffer]; lpBuffer
0x1802fb106  call    cs:__imp_GetSystemDirectoryW
0x1802fb10d  nop     dword ptr [rax+rax+00h]
0x1802fb112  mov     ecx, eax
0x1802fb114  test    eax, eax
0x1802fb116  jz      short loc_1802FB139
0x1802fb118  mov     edx, eax
0x1802fb11a  cmp     rdx, qword ptr [rbp+0E0h+uSize]
0x1802fb11e  jnb     short loc_1802FB139
0x1802fb120  lea     rax, [rbp+0E0h+lpBuffer]
0x1802fb124  cmp     [rbp+0E0h+var_B8], 7
0x1802fb129  cmova   rax, [rbp+0E0h+lpBuffer]
0x1802fb12e  cmp     [rax], r15w
0x1802fb132  jz      short loc_1802FB139
0x1802fb134  mov     al, r15b
0x1802fb137  jmp     short loc_1802FB13D
0x1802fb139  mov     al, 1
0x1802fb13b  mov     edx, ecx
0x1802fb13d  mov     rcx, [rbp+0E8h]; this
0x1802fb144  test    al, al
0x1802fb146  jnz     loc_1802FB3E5
0x1802fb14c  lea     rcx, [rbp+0E0h+lpBuffer]
0x1802fb150  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1802fb155  lea     rdx, [rbp+0E0h+lpBuffer]
0x1802fb159  lea     rcx, [rbp+0E0h+Src]
0x1802fb15d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1802fb162  nop
0x1802fb163  lea     rax, aRdrleakdiagExe; "RdrLeakDiag.exe"
0x1802fb16a  mov     qword ptr [rbp+0E0h+var_B0], rax
0x1802fb16e  mov     qword ptr [rbp+0E0h+var_B0+8], 0Fh
0x1802fb176  lea     rdx, [rbp+0E0h+var_B0]
0x1802fb17a  lea     rcx, [rbp+0E0h+Src]; pszPath
0x1802fb17e  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1802fb183  xor     r8d, r8d
0x1802fb186  mov     dl, 1
0x1802fb188  lea     rcx, [rbp+0E0h+Src]; lpSrc
0x1802fb18c  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1802fb191  lea     rcx, [rbp+0E0h+lpCommandLine]; this
0x1802fb195  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x1802fb19a  nop
0x1802fb19b  lea     rdx, [rsp+1E0h+var_188]
0x1802fb1a0  lea     rcx, [rbp+0E0h+Src]
0x1802fb1a4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802fb1a9  movups  xmm0, xmmword ptr [rax]
0x1802fb1ac  movdqu  [rbp+0E0h+var_B0], xmm0
0x1802fb1b1  lea     rdx, [rbp+0E0h+var_B0]
0x1802fb1b5  lea     rcx, [rbp+0E0h+lpCommandLine]; Src
0x1802fb1b9  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1802fb1be  lea     rdx, aP; " -p "
0x1802fb1c5  mov     rcx, rax; Src
0x1802fb1c8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802fb1cd  mov     edx, edi
0x1802fb1cf  mov     rcx, rax
0x1802fb1d2  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1802fb1d7  lea     rdx, asc_18039A33C; " "
0x1802fb1de  mov     rcx, rax; Src
0x1802fb1e1  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1802fb1e6  movups  xmm0, xmmword ptr [r14]
0x1802fb1ea  movdqu  [rbp+0E0h+var_B0], xmm0
0x1802fb1ef  lea     rdx, [rbp+0E0h+var_B0]
0x1802fb1f3  mov     rcx, rax; Src
0x1802fb1f6  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1802fb1fb  mov     eax, cs:dword_18042D328
0x1802fb201  cmp     eax, 4
0x1802fb204  jbe     short loc_1802FB25D
0x1802fb206  mov     edx, 40004h
0x1802fb20b  lea     rcx, dword_18042D328
0x1802fb212  call    _tlgKeywordOn
0x1802fb217  test    al, al
0x1802fb219  jz      short loc_1802FB25D
0x1802fb21b  lea     rdx, [rbp+0E0h+var_B0]
0x1802fb21f  lea     rcx, [rbp+0E0h+lpCommandLine]
0x1802fb223  call    ?str@WideStringStream@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::WideStringStream::str(void)
0x1802fb228  cmp     qword ptr [rax+18h], 7
0x1802fb22d  jbe     short loc_1802FB232
0x1802fb22f  mov     rax, [rax]
0x1802fb232  mov     qword ptr [rsp+1E0h+var_188], rax
0x1802fb237  lea     rax, [rsp+1E0h+var_188]
0x1802fb23c  mov     qword ptr [rsp+1E0h+bInheritHandles], rax
0x1802fb241  lea     rdx, unk_1803DF84D
0x1802fb248  lea     rcx, dword_18042D328
0x1802fb24f  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1802fb254  lea     rcx, [rbp+0E0h+var_B0]; this
0x1802fb258  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802fb25d  xor     edx, edx; Val
0x1802fb25f  lea     r8d, [rdx+68h]; Size
0x1802fb263  lea     rcx, [rbp+0E0h+StartupInfo]; void *
0x1802fb267  call    memset_0
0x1802fb26c  xorps   xmm0, xmm0
0x1802fb26f  xor     eax, eax
0x1802fb271  movups  xmmword ptr [rbp+0E0h+ProcessInformation.hProcess], xmm0
0x1802fb275  mov     qword ptr [rbp+0E0h+ProcessInformation.dwProcessId], rax
0x1802fb279  lea     rdx, [rbp+0E0h+lpCommandLine]
0x1802fb27d  cmp     [rbp+0E0h+var_58], 7
0x1802fb285  cmova   rdx, [rbp+0E0h+lpCommandLine]; lpCommandLine
0x1802fb28a  lea     rax, [rbp+0E0h+ProcessInformation]
0x1802fb28e  mov     [rsp+1E0h+lpProcessInformation], rax; lpProcessInformation
0x1802fb293  lea     rax, [rbp+0E0h+StartupInfo]
0x1802fb297  mov     [rsp+1E0h+lpStartupInfo], rax; lpStartupInfo
0x1802fb29c  mov     [rsp+1E0h+lpCurrentDirectory], r15; lpCurrentDirectory
0x1802fb2a1  mov     [rsp+1E0h+lpEnvironment], r15; lpEnvironment
0x1802fb2a6  mov     [rsp+1E0h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x1802fb2ae  mov     [rsp+1E0h+bInheritHandles], r15d; bInheritHandles
0x1802fb2b3  xor     r9d, r9d; lpThreadAttributes
0x1802fb2b6  xor     r8d, r8d; lpProcessAttributes
0x1802fb2b9  xor     ecx, ecx; lpApplicationName
0x1802fb2bb  call    cs:__imp_CreateProcessW
0x1802fb2c2  nop     dword ptr [rax+rax+00h]
0x1802fb2c7  mov     rcx, [rbp+0E8h]; this
0x1802fb2ce  test    eax, eax
0x1802fb2d0  jz      short loc_1802FB33F
0x1802fb2d2  mov     rax, [rbp+0E0h+ProcessInformation.hProcess]
0x1802fb2d6  mov     qword ptr [rbp+0E0h+var_B0], rax
0x1802fb2da  mov     rax, [rbp+0E0h+ProcessInformation.hThread]
0x1802fb2de  mov     qword ptr [rsp+1E0h+var_188], rax
0x1802fb2e3  lea     rcx, [rsp+1E0h+var_188]
0x1802fb2e8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802fb2ed  lea     rcx, [rbp+0E0h+var_B0]
0x1802fb2f1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802fb2f6  nop
0x1802fb2f7  lea     rcx, [rbp+0E0h+lpCommandLine]; this
0x1802fb2fb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802fb300  nop
0x1802fb301  lea     rcx, [rbp+0E0h+Src]; this
0x1802fb305  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802fb30a  nop
0x1802fb30b  lea     rcx, [rbp+0E0h+lpBuffer]; this
0x1802fb30f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802fb314  nop
0x1802fb315  lea     rcx, [rsp+1E0h+var_170]
0x1802fb31a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802fb31f  mov     rcx, [rbp+0E0h+var_40]
0x1802fb326  xor     rcx, rsp; StackCookie
0x1802fb329  call    __security_check_cookie
0x1802fb32e  add     rsp, 1B8h
0x1802fb335  pop     r15
0x1802fb337  pop     r14
0x1802fb339  pop     rdi
0x1802fb33a  pop     rsi
0x1802fb33b  pop     rbx
0x1802fb33c  pop     rbp
0x1802fb33d  retn
0x1802fb33f  lea     r8, aOnecoreBaseTel_273; "onecore\\base\\telemetry\\utc\\service"...
0x1802fb346  mov     edx, 13Ah; void *
0x1802fb34b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802fb351  lea     r8, aOnecoreBaseTel_273; "onecore\\base\\telemetry\\utc\\service"...
0x1802fb358  mov     edx, 0FCh; void *
0x1802fb35d  mov     rcx, rax; this
0x1802fb360  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802fb366  call    cs:__imp_GetLastError
0x1802fb36d  nop     dword ptr [rax+rax+00h]
0x1802fb372  mov     ebx, eax
0x1802fb374  test    eax, eax
0x1802fb376  jle     short loc_1802FB381
0x1802fb378  movzx   ebx, ax
0x1802fb37b  or      ebx, 80070000h
0x1802fb381  mov     eax, cs:dword_18042D328
0x1802fb387  cmp     eax, 2
0x1802fb38a  jbe     short loc_1802FB3C2
0x1802fb38c  mov     edx, 40004h
0x1802fb391  lea     rcx, dword_18042D328
0x1802fb398  call    _tlgKeywordOn
0x1802fb39d  test    al, al
0x1802fb39f  jz      short loc_1802FB3C2
0x1802fb3a1  mov     [rsp+1E0h+var_188], ebx
0x1802fb3a5  lea     rax, [rsp+1E0h+var_188]
0x1802fb3aa  mov     qword ptr [rsp+1E0h+bInheritHandles], rax; int
0x1802fb3af  lea     rdx, unk_1803DF881
0x1802fb3b6  lea     rcx, dword_18042D328
0x1802fb3bd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1802fb3c2  mov     ecx, ebx
0x1802fb3c4  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1802fb3c9  mov     r9d, eax; char *
0x1802fb3cc  mov     rcx, [rbp+0E8h]; this
0x1802fb3d3  lea     r8, aOnecoreBaseTel_273; "onecore\\base\\telemetry\\utc\\service"...
0x1802fb3da  mov     edx, 10Fh; void *
0x1802fb3df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802fb3e5  mov     r9d, 800700A1h; char *
0x1802fb3eb  lea     r8, aOnecoreBaseTel_273; "onecore\\base\\telemetry\\utc\\service"...
0x1802fb3f2  mov     edx, 11Eh; void *
0x1802fb3f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
