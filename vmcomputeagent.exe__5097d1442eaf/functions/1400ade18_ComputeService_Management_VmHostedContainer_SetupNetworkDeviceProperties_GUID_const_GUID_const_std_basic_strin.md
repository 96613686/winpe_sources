# ComputeService::Management::VmHostedContainer::SetupNetworkDeviceProperties(_GUID const &,_GUID const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Config::Containers::HNS::HNSInterfaceConstraint)

- ea: `0x1400ade18`
- end: `0x1400ae22d`
- name: `?SetupNetworkDeviceProperties@VmHostedContainer@Management@ComputeService@@YAXAEBU_GUID@@0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHNSInterfaceConstraint@HNS@Containers@Config@@@Z`
- size: `1045`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400ae234`

## callees

- `0x140005360`
- `0x140008760`
- `0x14000ea60`
- `0x14008ae64`
- `0x1400ad794`
- `0x1400ade18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ae140`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ae140`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400adee7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400adee7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400adf2d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400adf99`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae00e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae053`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae08b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae0da`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae129`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400adf2d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400adf99`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae00e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae053`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae08b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae0da`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae129`

## string_xrefs

- `0x1400adf8c`: `Compartment`
- `0x1400ae188`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae19d`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae1b2`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae1c7`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae1dc`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae1f1`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae206`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae21b`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ade84`: `System\CurrentControlSet\Services\Netvsc\InterfaceMap`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::Management::VmHostedContainer::SetupNetworkDeviceProperties(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  _QWORD *v5; // rdi
  const WCHAR *v7; // rdx
  LSTATUS v8; // eax
  __int64 v9; // r8
  DWORD v10; // eax
  LSTATUS v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  LPCVOID *v14; // rcx
  LSTATUS v15; // eax
  LPCVOID *v16; // rcx
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  const void *v20; // rax
  LSTATUS v21; // eax
  const void *v22; // rax
  LSTATUS v23; // eax
  int dwOptions; // [rsp+20h] [rbp-79h]
  int dwOptionsa; // [rsp+20h] [rbp-79h]
  int dwOptionsb; // [rsp+20h] [rbp-79h]
  int dwOptionsc; // [rsp+20h] [rbp-79h]
  int dwOptionsd; // [rsp+20h] [rbp-79h]
  int dwOptionse; // [rsp+20h] [rbp-79h]
  int dwOptionsf; // [rsp+20h] [rbp-79h]
  int dwOptionsg; // [rsp+20h] [rbp-79h]
  HKEY hKey; // [rsp+58h] [rbp-41h] BYREF
  LPCVOID lpData[2]; // [rsp+60h] [rbp-39h] BYREF
  int v34; // [rsp+70h] [rbp-29h]
  unsigned __int64 v35; // [rsp+78h] [rbp-21h]
  LPCWSTR lpSubKey[2]; // [rsp+80h] [rbp-19h] BYREF
  __m128i si128; // [rsp+90h] [rbp-9h]
  _QWORD v38[3]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v5 = a3;
  LOBYTE(a3) = 1;
  Vml::GuidToString(v38, a1, a3);
  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  Vml::FormatString(lpSubKey, (wchar_t *)L"%ls\\%ls");
  hKey = 0;
  v7 = (const WCHAR *)lpSubKey;
  if ( si128.m128i_i64[1] > 7uLL )
    v7 = lpSubKey[0];
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 1u, 0x20006u, 0, &hKey, 0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
      (const char *)(unsigned int)v8,
      dwOptions);
  if ( v5[2] )
  {
    v10 = 2 * *((_DWORD *)v5 + 4) + 2;
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    v11 = RegSetKeyValueW(hKey, 0, L"PnPId", 1u, v5, v10);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
        (const char *)(unsigned int)v11,
        dwOptionsa);
  }
  v12 = *(_QWORD *)&GUID_NULL.Data1;
  if ( *a2 != *(_QWORD *)&GUID_NULL.Data1 || (v13 = *(_QWORD *)GUID_NULL.Data4, a2[1] != *(_QWORD *)GUID_NULL.Data4) )
  {
    LOBYTE(v9) = 1;
    Vml::GuidToString(lpData, a2, v9);
    v14 = lpData;
    if ( v35 > 7 )
      v14 = (LPCVOID *)lpData[0];
    v15 = RegSetKeyValueW(hKey, 0, L"Compartment", 1u, v14, 2 * v34 + 2);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x123,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
        (const char *)(unsigned int)v15,
        dwOptionsb);
    std::wstring::~wstring(lpData);
    v13 = *(_QWORD *)GUID_NULL.Data4;
    v12 = *(_QWORD *)&GUID_NULL.Data1;
  }
  if ( *(_QWORD *)a4 != v12 || *(_QWORD *)(a4 + 8) != v13 )
  {
    LOBYTE(v9) = 1;
    Vml::GuidToString(lpData, a4, v9);
    v16 = lpData;
    if ( v35 > 7 )
      v16 = (LPCVOID *)lpData[0];
    v17 = RegSetKeyValueW(hKey, 0, L"Guid", 1u, v16, 2 * v34 + 2);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
        (const char *)(unsigned int)v17,
        dwOptionsc);
    std::wstring::~wstring(lpData);
  }
  if ( *(_QWORD *)(a4 + 16) )
  {
    v18 = RegSetKeyValueW(hKey, 0, L"Luid", 0xBu, (LPCVOID)(a4 + 16), 8u);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
        (const char *)(unsigned int)v18,
        dwOptionsd);
  }
  if ( *(_DWORD *)(a4 + 24) )
  {
    v19 = RegSetKeyValueW(hKey, 0, L"Index", 4u, (LPCVOID)(a4 + 24), 4u);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
        (const char *)(unsigned int)v19,
        dwOptionse);
  }
  if ( *(_QWORD *)(a4 + 48) )
  {
    v20 = *(_QWORD *)(a4 + 56) <= 7u ? (const void *)(a4 + 32) : *(const void **)(a4 + 32);
    v21 = RegSetKeyValueW(hKey, 0, L"Alias", 1u, v20, 2 * *(_DWORD *)(a4 + 48) + 2);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
        (const char *)(unsigned int)v21,
        dwOptionsf);
  }
  if ( *(_QWORD *)(a4 + 80) )
  {
    v22 = *(_QWORD *)(a4 + 88) <= 7u ? (const void *)(a4 + 64) : *(const void **)(a4 + 64);
    v23 = RegSetKeyValueW(hKey, 0, L"Description", 1u, v22, 2 * *(_DWORD *)(a4 + 80) + 2);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
        (const char *)(unsigned int)v23,
        dwOptionsg);
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
  std::wstring::~wstring(v38);
  std::wstring::~wstring((void *)(a4 + 64));
  std::wstring::~wstring((void *)(a4 + 32));
}

```

## disassembly

```asm
0x1400ade18  push    rbp
0x1400ade1a  push    rbx
0x1400ade1b  push    rsi
0x1400ade1c  push    rdi
0x1400ade1d  push    r15
0x1400ade1f  lea     rbp, [rsp-37h]
0x1400ade24  sub     rsp, 0D0h
0x1400ade2b  mov     rax, cs:__security_cookie
0x1400ade32  xor     rax, rsp
0x1400ade35  mov     [rbp+57h+var_30], rax
0x1400ade39  mov     rbx, r9
0x1400ade3c  mov     rdi, r8
0x1400ade3f  mov     rsi, rdx
0x1400ade42  mov     [rbp+57h+var_A0], rbx
0x1400ade46  mov     r15d, 1
0x1400ade4c  mov     r8b, r15b
0x1400ade4f  mov     rdx, rcx
0x1400ade52  lea     rcx, [rbp+57h+var_50]
0x1400ade56  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400ade5b  nop
0x1400ade5c  xorps   xmm0, xmm0
0x1400ade5f  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x1400ade63  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400ade6b  movdqu  [rbp+57h+var_60], xmm1
0x1400ade70  xor     eax, eax
0x1400ade72  mov     word ptr [rbp+57h+lpSubKey], ax
0x1400ade76  lea     r9, [rbp+57h+var_50]
0x1400ade7a  cmp     [rbp+57h+var_38], 7
0x1400ade7f  cmova   r9, [rbp+57h+var_50]
0x1400ade84  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ne"...
0x1400ade8b  lea     rdx, aLsLs; "%ls\\%ls"
0x1400ade92  lea     rcx, [rbp+57h+lpSubKey]; Src
0x1400ade96  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x1400ade9b  nop
0x1400ade9c  mov     [rbp+57h+hKey], 0
0x1400adea4  lea     rdx, [rbp+57h+lpSubKey]
0x1400adea8  cmp     qword ptr [rbp+57h+var_60+8], 7
0x1400adead  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1400adeb2  mov     [rsp+0F0h+lpdwDisposition], 0; lpdwDisposition
0x1400adebb  lea     rax, [rbp+57h+hKey]
0x1400adebf  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1400adec4  mov     [rsp+0F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400adecd  mov     [rsp+0F0h+samDesired], 20006h; samDesired
0x1400aded5  mov     [rsp+0F0h+dwOptions], r15d; int
0x1400adeda  xor     r9d, r9d; lpClass
0x1400adedd  xor     r8d, r8d; Reserved
0x1400adee0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400adee7  call    cs:__imp_RegCreateKeyExW
0x1400adeed  mov     rcx, [rbp+5Fh]; this
0x1400adef1  test    eax, eax
0x1400adef3  js      loc_1400AE19A
0x1400adef9  cmp     qword ptr [rdi+10h], 0
0x1400adefe  jz      short loc_1400ADF3F
0x1400adf00  mov     eax, [rdi+10h]
0x1400adf03  lea     eax, ds:2[rax*2]
0x1400adf0a  cmp     qword ptr [rdi+18h], 7
0x1400adf0f  jbe     short loc_1400ADF14
0x1400adf11  mov     rdi, [rdi]
0x1400adf14  mov     [rsp+0F0h+samDesired], eax; cbData
0x1400adf18  mov     qword ptr [rsp+0F0h+dwOptions], rdi; int
0x1400adf1d  mov     r9d, r15d; dwType
0x1400adf20  lea     r8, aPnpid; "PnPId"
0x1400adf27  xor     edx, edx; lpSubKey
0x1400adf29  mov     rcx, [rbp+57h+hKey]; hKey
0x1400adf2d  call    cs:__imp_RegSetKeyValueW
0x1400adf33  mov     rcx, [rbp+5Fh]; this
0x1400adf37  test    eax, eax
0x1400adf39  js      loc_1400AE1AF
0x1400adf3f  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1400adf46  cmp     [rsi], rax
0x1400adf49  jnz     short loc_1400ADF58
0x1400adf4b  mov     rcx, qword ptr cs:GUID_NULL.Data4
0x1400adf52  cmp     [rsi+8], rcx
0x1400adf56  jz      short loc_1400ADFC2
0x1400adf58  mov     r8b, r15b
0x1400adf5b  mov     rdx, rsi
0x1400adf5e  lea     rcx, [rbp+57h+lpData]
0x1400adf62  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400adf67  nop
0x1400adf68  mov     eax, [rbp+57h+var_80]
0x1400adf6b  lea     rcx, [rbp+57h+lpData]
0x1400adf6f  cmp     [rbp+57h+var_78], 7
0x1400adf74  cmova   rcx, [rbp+57h+lpData]
0x1400adf79  lea     eax, ds:2[rax*2]
0x1400adf80  mov     [rsp+0F0h+samDesired], eax; cbData
0x1400adf84  mov     qword ptr [rsp+0F0h+dwOptions], rcx; int
0x1400adf89  mov     r9d, r15d; dwType
0x1400adf8c  lea     r8, aCompartment; "Compartment"
0x1400adf93  xor     edx, edx; lpSubKey
0x1400adf95  mov     rcx, [rbp+57h+hKey]; hKey
0x1400adf99  call    cs:__imp_RegSetKeyValueW
0x1400adf9f  mov     rcx, [rbp+5Fh]; this
0x1400adfa3  test    eax, eax
0x1400adfa5  js      loc_1400AE1C4
0x1400adfab  lea     rcx, [rbp+57h+lpData]; void *
0x1400adfaf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400adfb4  mov     rcx, qword ptr cs:GUID_NULL.Data4
0x1400adfbb  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1400adfc2  cmp     [rbx], rax
0x1400adfc5  jnz     short loc_1400ADFCD
0x1400adfc7  cmp     [rbx+8], rcx
0x1400adfcb  jz      short loc_1400AE029
0x1400adfcd  mov     r8b, r15b
0x1400adfd0  mov     rdx, rbx
0x1400adfd3  lea     rcx, [rbp+57h+lpData]
0x1400adfd7  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400adfdc  nop
0x1400adfdd  mov     eax, [rbp+57h+var_80]
0x1400adfe0  lea     rcx, [rbp+57h+lpData]
0x1400adfe4  cmp     [rbp+57h+var_78], 7
0x1400adfe9  cmova   rcx, [rbp+57h+lpData]
0x1400adfee  lea     eax, ds:2[rax*2]
0x1400adff5  mov     [rsp+0F0h+samDesired], eax; cbData
0x1400adff9  mov     qword ptr [rsp+0F0h+dwOptions], rcx; int
0x1400adffe  mov     r9d, r15d; dwType
0x1400ae001  lea     r8, aGuid; "Guid"
0x1400ae008  xor     edx, edx; lpSubKey
0x1400ae00a  mov     rcx, [rbp+57h+hKey]; hKey
0x1400ae00e  call    cs:__imp_RegSetKeyValueW
0x1400ae014  mov     rcx, [rbp+5Fh]; this
0x1400ae018  test    eax, eax
0x1400ae01a  js      loc_1400AE1D9
0x1400ae020  lea     rcx, [rbp+57h+lpData]; void *
0x1400ae024  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae029  lea     rax, [rbx+10h]
0x1400ae02d  cmp     qword ptr [rax], 0
0x1400ae031  jz      short loc_1400AE065
0x1400ae033  mov     [rsp+0F0h+samDesired], 8; cbData
0x1400ae03b  mov     qword ptr [rsp+0F0h+dwOptions], rax; int
0x1400ae040  mov     r9d, 0Bh; dwType
0x1400ae046  lea     r8, aLuid; "Luid"
0x1400ae04d  xor     edx, edx; lpSubKey
0x1400ae04f  mov     rcx, [rbp+57h+hKey]; hKey
0x1400ae053  call    cs:__imp_RegSetKeyValueW
0x1400ae059  mov     rcx, [rbp+5Fh]; this
0x1400ae05d  test    eax, eax
0x1400ae05f  js      loc_1400AE1EE
0x1400ae065  lea     rax, [rbx+18h]
0x1400ae069  cmp     dword ptr [rax], 0
0x1400ae06c  jz      short loc_1400AE09D
0x1400ae06e  mov     r9d, 4; dwType
0x1400ae074  mov     [rsp+0F0h+samDesired], r9d; cbData
0x1400ae079  mov     qword ptr [rsp+0F0h+dwOptions], rax; int
0x1400ae07e  lea     r8, aIndex; "Index"
0x1400ae085  xor     edx, edx; lpSubKey
0x1400ae087  mov     rcx, [rbp+57h+hKey]; hKey
0x1400ae08b  call    cs:__imp_RegSetKeyValueW
0x1400ae091  mov     rcx, [rbp+5Fh]; this
0x1400ae095  test    eax, eax
0x1400ae097  js      loc_1400AE203
0x1400ae09d  lea     rsi, [rbx+20h]
0x1400ae0a1  cmp     qword ptr [rsi+10h], 0
0x1400ae0a6  jz      short loc_1400AE0EC
0x1400ae0a8  mov     eax, [rbx+30h]
0x1400ae0ab  lea     ecx, ds:2[rax*2]
0x1400ae0b2  cmp     qword ptr [rsi+18h], 7
0x1400ae0b7  jbe     short loc_1400AE0BE
0x1400ae0b9  mov     rax, [rsi]
0x1400ae0bc  jmp     short loc_1400AE0C1
0x1400ae0be  mov     rax, rsi
0x1400ae0c1  mov     [rsp+0F0h+samDesired], ecx; cbData
0x1400ae0c5  mov     qword ptr [rsp+0F0h+dwOptions], rax; int
0x1400ae0ca  mov     r9d, r15d; dwType
0x1400ae0cd  lea     r8, aAlias; "Alias"
0x1400ae0d4  xor     edx, edx; lpSubKey
0x1400ae0d6  mov     rcx, [rbp+57h+hKey]; hKey
0x1400ae0da  call    cs:__imp_RegSetKeyValueW
0x1400ae0e0  mov     rcx, [rbp+5Fh]; this
0x1400ae0e4  test    eax, eax
0x1400ae0e6  js      loc_1400AE218
0x1400ae0ec  lea     rdi, [rbx+40h]
0x1400ae0f0  cmp     qword ptr [rdi+10h], 0
0x1400ae0f5  jz      short loc_1400AE137
0x1400ae0f7  mov     eax, [rbx+50h]
0x1400ae0fa  lea     ecx, ds:2[rax*2]
0x1400ae101  cmp     qword ptr [rdi+18h], 7
0x1400ae106  jbe     short loc_1400AE10D
0x1400ae108  mov     rax, [rdi]
0x1400ae10b  jmp     short loc_1400AE110
0x1400ae10d  mov     rax, rdi
0x1400ae110  mov     [rsp+0F0h+samDesired], ecx; cbData
0x1400ae114  mov     qword ptr [rsp+0F0h+dwOptions], rax; int
0x1400ae119  mov     r9d, r15d; dwType
0x1400ae11c  lea     r8, aDescription; "Description"
0x1400ae123  xor     edx, edx; lpSubKey
0x1400ae125  mov     rcx, [rbp+57h+hKey]; hKey
0x1400ae129  call    cs:__imp_RegSetKeyValueW
0x1400ae12f  mov     rcx, [rbp+5Fh]; this
0x1400ae133  test    eax, eax
0x1400ae135  js      short loc_1400AE185
0x1400ae137  mov     rcx, [rbp+57h+hKey]; hKey
0x1400ae13b  test    rcx, rcx
0x1400ae13e  jz      short loc_1400AE147
0x1400ae140  call    cs:__imp_RegCloseKey
0x1400ae146  nop
0x1400ae147  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1400ae14b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae150  nop
0x1400ae151  lea     rcx, [rbp+57h+var_50]; void *
0x1400ae155  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae15a  nop
0x1400ae15b  mov     rcx, rdi; void *
0x1400ae15e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae163  mov     rcx, rsi; void *
0x1400ae166  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae16b  mov     rcx, [rbp+57h+var_30]
0x1400ae16f  xor     rcx, rsp; StackCookie
0x1400ae172  call    __security_check_cookie
0x1400ae177  add     rsp, 0D0h
0x1400ae17e  pop     r15
0x1400ae180  pop     rdi
0x1400ae181  pop     rsi
0x1400ae182  pop     rbx
0x1400ae183  pop     rbp
0x1400ae184  retn
0x1400ae185  mov     r9d, eax; char *
0x1400ae188  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae18f  mov     edx, 160h; void *
0x1400ae194  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ae19a  mov     r9d, eax; char *
0x1400ae19d  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae1a4  mov     edx, 10Ah; void *
0x1400ae1a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ae1af  mov     r9d, eax; char *
0x1400ae1b2  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae1b9  mov     edx, 115h; void *
0x1400ae1be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ae1c4  mov     r9d, eax; char *
0x1400ae1c7  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae1ce  mov     edx, 123h; void *
0x1400ae1d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ae1d9  mov     r9d, eax; char *
0x1400ae1dc  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae1e3  mov     edx, 130h; void *
0x1400ae1e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ae1ee  mov     r9d, eax; char *
0x1400ae1f1  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae1f8  mov     edx, 13Ch; void *
0x1400ae1fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ae203  mov     r9d, eax; char *
0x1400ae206  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae20d  mov     edx, 148h; void *
0x1400ae212  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ae218  mov     r9d, eax; char *
0x1400ae21b  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae222  mov     edx, 154h; void *
0x1400ae227  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
