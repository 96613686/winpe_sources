# ComputeService::Management::VmHostedContainer::CleanupNetworkDevices(std::vector<Config::Containers::VmHosted::NetworkAdapter,std::allocator<Config::Containers::VmHosted::NetworkAdapter>> const &,uint)

- ea: `0x1400ad0e0`
- end: `0x1400ad397`
- name: `?CleanupNetworkDevices@VmHostedContainer@Management@ComputeService@@YAXAEBV?$vector@UNetworkAdapter@VmHosted@Containers@Config@@V?$allocator@UNetworkAdapter@VmHosted@Containers@Config@@@std@@@std@@I@Z`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14009be50`

## callees

- `0x140005360`
- `0x140006074`
- `0x140008760`
- `0x14000ea60`
- `0x1400341ac`
- `0x140052aac`
- `0x14008ae64`
- `0x1400ad0e0`
- `0x1400ad794`
- `0x1400b22cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ad26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ad26b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400ad1c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400ad1c8`
- `IPHLPAPI!ConvertCompartmentIdToGuid` at `0x1400ad123`
- `IPHLPAPI!ConvertCompartmentIdToGuid` at `0x1400ad123`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1400ad2d7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1400ad2d7`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1400ad1ee`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1400ad1ee`

## string_xrefs

- `0x1400ad238`: `Registry cleanup on compartment [%ws] failed for [%ws]`
- `0x1400ad2fb`: `Registry cleanup of interface property map failed for [%ws]`
- `0x1400ad247`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ad30a`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ad370`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ad385`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ad1ba`: `System\CurrentControlSet\Services\Netvsc\CompartmentMap`
- `0x1400ad2ab`: `System\CurrentControlSet\Services\Netvsc\InterfaceMap`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::Management::VmHostedContainer::CleanupNetworkDevices(
        __int64 *a1,
        NET_IF_COMPARTMENT_ID a2)
{
  unsigned int v3; // eax
  __int64 v4; // rbx
  __int64 v5; // rsi
  __m128i si128; // xmm6
  __int64 v7; // r8
  LSTATUS v8; // eax
  const WCHAR *v9; // r8
  LSTATUS v10; // eax
  __int64 v11; // r8
  unsigned int v12; // edi
  char **v13; // rdx
  const char *v14; // rax
  const WCHAR *v15; // rdx
  unsigned int v16; // eax
  const char *v17; // rdx
  unsigned int phkResult; // [rsp+28h] [rbp-89h]
  int phkResulta; // [rsp+28h] [rbp-89h]
  HKEY hKey; // [rsp+48h] [rbp-69h] BYREF
  char *v21[3]; // [rsp+50h] [rbp-61h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp-49h]
  GUID CompartmentGuid; // [rsp+70h] [rbp-41h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+80h] [rbp-31h] BYREF
  __m128i v25; // [rsp+90h] [rbp-21h]
  LPCWSTR lpValueName[2]; // [rsp+A0h] [rbp-11h] BYREF
  __m128i v27; // [rsp+B0h] [rbp-1h]
  char *v28[4]; // [rsp+C0h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]

  CompartmentGuid = GUID_NULL;
  if ( a2 >= 2 )
  {
    v3 = ConvertCompartmentIdToGuid(a2, &CompartmentGuid);
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x177,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
        (const char *)v3,
        phkResult);
  }
  v4 = *a1;
  v5 = a1[1];
  if ( *a1 != v5 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      *(_OWORD *)lpValueName = 0;
      v27 = si128;
      LOWORD(lpValueName[0]) = 0;
      ComputeService::Net::GetPnpInstanceId(v4, *(unsigned int *)(v4 + 196), lpValueName);
      if ( memcmp_0(&CompartmentGuid, &GUID_NULL, 0x10u) )
      {
        LOBYTE(v7) = 1;
        Vml::GuidToString(v28, &CompartmentGuid, v7);
        hKey = 0;
        v8 = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Services\\Netvsc\\CompartmentMap",
               0,
               0xF003Fu,
               &hKey);
        if ( v8 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1A3,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
            (const char *)(unsigned int)v8,
            phkResulta);
        v9 = (const WCHAR *)lpValueName;
        if ( v27.m128i_i64[1] > 7uLL )
          v9 = lpValueName[0];
        v10 = RegDeleteKeyValueW(hKey, 0, v9);
        v12 = v10;
        if ( v10 != 2 && v10 )
        {
          LOBYTE(v11) = 1;
          Vml::GuidToString(v21, v4, v11);
          v13 = v21;
          if ( v22 > 7 )
            v13 = (char **)v21[0];
          v14 = (const char *)v28;
          if ( v28[3] > (char *)7 )
            v14 = v28[0];
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x1B0,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
            (const char *)v12,
            (int)"Registry cleanup on compartment [%ws] failed for [%ws]",
            v14,
            v13);
          std::wstring::~wstring(v21);
        }
        if ( hKey )
          RegCloseKey(hKey);
        std::wstring::~wstring(v28);
      }
      LOBYTE(v7) = 1;
      Vml::GuidToString(v21, v4, v7);
      *(_OWORD *)lpSubKey = 0;
      v25 = si128;
      LOWORD(lpSubKey[0]) = 0;
      Vml::FormatString(lpSubKey, (wchar_t *)L"%ls\\%ls");
      v15 = (const WCHAR *)lpSubKey;
      if ( v25.m128i_i64[1] > 7uLL )
        v15 = lpSubKey[0];
      v16 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v15);
      if ( (v16 & 0xFFFFFFFD) != 0 )
      {
        v17 = (const char *)v21;
        if ( v22 > 7 )
          v17 = v21[0];
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x1CF,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
          (const char *)v16,
          (int)"Registry cleanup of interface property map failed for [%ws]",
          v17);
      }
      std::wstring::~wstring(lpSubKey);
      std::wstring::~wstring(v21);
      std::wstring::~wstring(lpValueName);
      v4 += 296;
    }
    while ( v4 != v5 );
  }
}

```

## disassembly

```asm
0x1400ad0e0  mov     rax, rsp
0x1400ad0e3  mov     [rax+18h], rbx
0x1400ad0e7  push    rbp
0x1400ad0e8  push    rsi
0x1400ad0e9  push    rdi
0x1400ad0ea  lea     rbp, [rax-5Fh]
0x1400ad0ee  sub     rsp, 0F0h
0x1400ad0f5  movaps  xmmword ptr [rax-28h], xmm6
0x1400ad0f9  mov     rax, cs:__security_cookie
0x1400ad100  xor     rax, rsp
0x1400ad103  mov     [rbp+57h+var_28], rax
0x1400ad107  mov     eax, edx
0x1400ad109  mov     rdi, rcx
0x1400ad10c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400ad113  movdqu  xmmword ptr [rbp+57h+CompartmentGuid.Data1], xmm0
0x1400ad118  cmp     edx, 2
0x1400ad11b  jb      short loc_1400AD135
0x1400ad11d  lea     rdx, [rbp+57h+CompartmentGuid]; CompartmentGuid
0x1400ad121  mov     ecx, eax; CompartmentId
0x1400ad123  call    cs:__imp_ConvertCompartmentIdToGuid
0x1400ad129  mov     rcx, [rbp+5Fh]; this
0x1400ad12d  test    eax, eax
0x1400ad12f  jnz     loc_1400AD36D
0x1400ad135  mov     rbx, [rdi]
0x1400ad138  mov     rsi, [rdi+8]
0x1400ad13c  cmp     rbx, rsi
0x1400ad13f  jz      loc_1400AD349
0x1400ad145  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1400ad14d  xorps   xmm0, xmm0
0x1400ad150  movups  xmmword ptr [rbp+57h+lpValueName], xmm0
0x1400ad154  movdqu  [rbp+57h+var_58], xmm6
0x1400ad159  xor     eax, eax
0x1400ad15b  mov     word ptr [rbp+57h+lpValueName], ax
0x1400ad15f  lea     r8, [rbp+57h+lpValueName]
0x1400ad163  mov     edx, [rbx+0C4h]
0x1400ad169  mov     rcx, rbx
0x1400ad16c  call    ?GetPnpInstanceId@Net@ComputeService@@YAXAEBU_GUID@@IAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Net::GetPnpInstanceId(_GUID const &,uint,std::wstring &)
0x1400ad171  mov     r8d, 10h; Size
0x1400ad177  lea     rdx, GUID_NULL; Buf2
0x1400ad17e  lea     rcx, [rbp+57h+CompartmentGuid]; Buf1
0x1400ad182  call    memcmp_0
0x1400ad187  test    eax, eax
0x1400ad189  jz      loc_1400AD27B
0x1400ad18f  mov     r8b, 1
0x1400ad192  lea     rdx, [rbp+57h+CompartmentGuid]
0x1400ad196  lea     rcx, [rbp+57h+var_48]
0x1400ad19a  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400ad19f  nop
0x1400ad1a0  mov     [rbp+57h+hKey], 0
0x1400ad1a8  lea     rax, [rbp+57h+hKey]
0x1400ad1ac  mov     [rsp+100h+phkResult], rax; int
0x1400ad1b1  mov     r9d, 0F003Fh; samDesired
0x1400ad1b7  xor     r8d, r8d; ulOptions
0x1400ad1ba  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ne"...
0x1400ad1c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400ad1c8  call    cs:__imp_RegOpenKeyExW
0x1400ad1ce  mov     rcx, [rbp+5Fh]; this
0x1400ad1d2  test    eax, eax
0x1400ad1d4  js      loc_1400AD382
0x1400ad1da  lea     r8, [rbp+57h+lpValueName]
0x1400ad1de  cmp     qword ptr [rbp+57h+var_58+8], 7
0x1400ad1e3  cmova   r8, [rbp+57h+lpValueName]; lpValueName
0x1400ad1e8  xor     edx, edx; lpSubKey
0x1400ad1ea  mov     rcx, [rbp+57h+hKey]; hKey
0x1400ad1ee  call    cs:__imp_RegDeleteKeyValueW
0x1400ad1f4  mov     edi, eax
0x1400ad1f6  cmp     eax, 2
0x1400ad1f9  jz      short loc_1400AD262
0x1400ad1fb  test    eax, eax
0x1400ad1fd  jz      short loc_1400AD262
0x1400ad1ff  mov     r8b, 1
0x1400ad202  mov     rdx, rbx
0x1400ad205  lea     rcx, [rbp+57h+var_B8]
0x1400ad209  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400ad20e  lea     rdx, [rbp+57h+var_B8]
0x1400ad212  cmp     [rbp+57h+var_A0], 7
0x1400ad217  cmova   rdx, [rbp+57h+var_B8]
0x1400ad21c  lea     rax, [rbp+57h+var_48]
0x1400ad220  cmp     [rbp+57h+var_30], 7
0x1400ad225  cmova   rax, [rbp+57h+var_48]
0x1400ad22a  mov     rcx, [rbp+5Fh]; this
0x1400ad22e  mov     [rsp+100h+var_D0], rdx
0x1400ad233  mov     [rsp+100h+var_D8], rax; char *
0x1400ad238  lea     rax, aRegistryCleanu_0; "Registry cleanup on compartment [%ws] f"...
0x1400ad23f  mov     [rsp+100h+phkResult], rax; int
0x1400ad244  mov     r9d, edi; char *
0x1400ad247  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ad24e  mov     edx, 1B0h; void *
0x1400ad253  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400ad258  lea     rcx, [rbp+57h+var_B8]; void *
0x1400ad25c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ad261  nop
0x1400ad262  mov     rcx, [rbp+57h+hKey]; hKey
0x1400ad266  test    rcx, rcx
0x1400ad269  jz      short loc_1400AD272
0x1400ad26b  call    cs:__imp_RegCloseKey
0x1400ad271  nop
0x1400ad272  lea     rcx, [rbp+57h+var_48]; void *
0x1400ad276  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ad27b  mov     r8b, 1
0x1400ad27e  mov     rdx, rbx
0x1400ad281  lea     rcx, [rbp+57h+var_B8]
0x1400ad285  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400ad28a  nop
0x1400ad28b  xorps   xmm0, xmm0
0x1400ad28e  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x1400ad292  movdqu  [rbp+57h+var_78], xmm6
0x1400ad297  xor     eax, eax
0x1400ad299  mov     word ptr [rbp+57h+lpSubKey], ax
0x1400ad29d  lea     r9, [rbp+57h+var_B8]
0x1400ad2a1  cmp     [rbp+57h+var_A0], 7
0x1400ad2a6  cmova   r9, [rbp+57h+var_B8]
0x1400ad2ab  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ne"...
0x1400ad2b2  lea     rdx, aLsLs; "%ls\\%ls"
0x1400ad2b9  lea     rcx, [rbp+57h+lpSubKey]; Src
0x1400ad2bd  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x1400ad2c2  lea     rdx, [rbp+57h+lpSubKey]
0x1400ad2c6  cmp     qword ptr [rbp+57h+var_78+8], 7
0x1400ad2cb  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1400ad2d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400ad2d7  call    cs:__imp_RegDeleteKeyW
0x1400ad2dd  test    eax, 0FFFFFFFDh
0x1400ad2e2  jz      short loc_1400AD31C
0x1400ad2e4  lea     rdx, [rbp+57h+var_B8]
0x1400ad2e8  cmp     [rbp+57h+var_A0], 7
0x1400ad2ed  cmova   rdx, [rbp+57h+var_B8]
0x1400ad2f2  mov     rcx, [rbp+5Fh]; this
0x1400ad2f6  mov     [rsp+100h+var_D8], rdx; char *
0x1400ad2fb  lea     rdx, aRegistryCleanu; "Registry cleanup of interface property "...
0x1400ad302  mov     [rsp+100h+phkResult], rdx; int
0x1400ad307  mov     r9d, eax; char *
0x1400ad30a  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ad311  mov     edx, 1CFh; void *
0x1400ad316  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400ad31b  nop
0x1400ad31c  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1400ad320  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ad325  nop
0x1400ad326  lea     rcx, [rbp+57h+var_B8]; void *
0x1400ad32a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ad32f  nop
0x1400ad330  lea     rcx, [rbp+57h+lpValueName]; void *
0x1400ad334  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ad339  add     rbx, 128h
0x1400ad340  cmp     rbx, rsi
0x1400ad343  jnz     loc_1400AD14D
0x1400ad349  mov     rcx, [rbp+57h+var_28]
0x1400ad34d  xor     rcx, rsp; StackCookie
0x1400ad350  call    __security_check_cookie
0x1400ad355  lea     r11, [rsp+100h+var_10]
0x1400ad35d  mov     rbx, [r11+30h]
0x1400ad361  movaps  xmm6, xmmword ptr [r11-10h]
0x1400ad366  mov     rsp, r11
0x1400ad369  pop     rdi
0x1400ad36a  pop     rsi
0x1400ad36b  pop     rbp
0x1400ad36c  retn
0x1400ad36d  mov     r9d, eax; char *
0x1400ad370  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ad377  mov     edx, 177h; void *
0x1400ad37c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ad382  mov     r9d, eax; char *
0x1400ad385  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ad38c  mov     edx, 1A3h; void *
0x1400ad391  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
