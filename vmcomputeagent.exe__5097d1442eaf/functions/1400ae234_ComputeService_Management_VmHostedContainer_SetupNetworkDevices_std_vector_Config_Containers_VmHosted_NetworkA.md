# ComputeService::Management::VmHostedContainer::SetupNetworkDevices(std::vector<Config::Containers::VmHosted::NetworkAdapter,std::allocator<Config::Containers::VmHosted::NetworkAdapter>> const &,uint)

- ea: `0x1400ae234`
- end: `0x1400ae54b`
- name: `?SetupNetworkDevices@VmHostedContainer@Management@ComputeService@@YAXAEBV?$vector@UNetworkAdapter@VmHosted@Containers@Config@@V?$allocator@UNetworkAdapter@VmHosted@Containers@Config@@@std@@@std@@I@Z`
- size: `791`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14009a630`
- `0x14009be50`

## callees

- `0x140005360`
- `0x140006074`
- `0x140008760`
- `0x14000ea60`
- `0x14001bfa4`
- `0x140027858`
- `0x1400341ac`
- `0x14008ae64`
- `0x1400ade18`
- `0x1400ae234`
- `0x1400b22cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ae3af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ae3af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400ae343`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400ae343`
- `IPHLPAPI!ConvertCompartmentIdToGuid` at `0x1400ae27c`
- `IPHLPAPI!ConvertCompartmentIdToGuid` at `0x1400ae27c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae391`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ae391`

## string_xrefs

- `0x1400ae50f`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae524`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae539`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainernetwork.cpp`
- `0x1400ae335`: `System\CurrentControlSet\Services\Netvsc\CompartmentMap`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::Management::VmHostedContainer::SetupNetworkDevices(
        __int64 *a1,
        NET_IF_COMPARTMENT_ID a2)
{
  unsigned int v3; // eax
  __int64 v4; // rbx
  __int64 v5; // rdi
  __m128i si128; // xmm6
  __int64 v7; // r8
  LSTATUS v8; // eax
  LPCVOID *v9; // rcx
  const WCHAR *v10; // r8
  LSTATUS v11; // eax
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  DWORD dwOptions; // [rsp+28h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+28h] [rbp-E0h]
  DWORD dwOptionsb; // [rsp+28h] [rbp-E0h]
  _QWORD v17[4]; // [rsp+58h] [rbp-B0h] BYREF
  int v18; // [rsp+78h] [rbp-90h]
  int v19; // [rsp+7Ch] [rbp-8Ch]
  _BYTE v20[32]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v21[32]; // [rsp+A0h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp-48h] BYREF
  GUID CompartmentGuid; // [rsp+C8h] [rbp-40h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+D8h] [rbp-30h] BYREF
  __m128i v25; // [rsp+E8h] [rbp-20h]
  __int128 v26; // [rsp+F8h] [rbp-10h]
  __int64 v27; // [rsp+108h] [rbp+0h]
  int v28; // [rsp+110h] [rbp+8h]
  int v29; // [rsp+114h] [rbp+Ch]
  _OWORD v30[2]; // [rsp+118h] [rbp+10h] BYREF
  _OWORD v31[2]; // [rsp+138h] [rbp+30h] BYREF
  LPCVOID lpData[2]; // [rsp+158h] [rbp+50h] BYREF
  int v33; // [rsp+168h] [rbp+60h]
  unsigned __int64 v34; // [rsp+170h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1A0h] [rbp+98h]

  CompartmentGuid = GUID_NULL;
  if ( a2 >= 2 )
  {
    v3 = ConvertCompartmentIdToGuid(a2, &CompartmentGuid);
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
        (const char *)v3,
        dwOptions);
  }
  v4 = *a1;
  v5 = a1[1];
  if ( v4 != v5 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      *(_OWORD *)lpValueName = 0;
      v25 = si128;
      LOWORD(lpValueName[0]) = 0;
      ComputeService::Net::GetPnpInstanceId(v4, *(unsigned int *)(v4 + 196), lpValueName);
      if ( memcmp_0(&CompartmentGuid, &GUID_NULL, 0x10u) )
      {
        LOBYTE(v7) = 1;
        Vml::GuidToString(lpData, &CompartmentGuid, v7);
        hKey = 0;
        v8 = RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Services\\Netvsc\\CompartmentMap",
               0,
               0,
               1u,
               0x20006u,
               0,
               &hKey,
               0);
        if ( v8 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD3,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
            (const char *)(unsigned int)v8,
            dwOptionsa);
        v9 = lpData;
        if ( v34 > 7 )
          v9 = (LPCVOID *)lpData[0];
        v10 = (const WCHAR *)lpValueName;
        if ( v25.m128i_i64[1] > 7uLL )
          v10 = lpValueName[0];
        v11 = RegSetKeyValueW(hKey, 0, v10, 1u, v9, 2 * v33 + 2);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDD,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainernetwork.cpp",
            (const char *)(unsigned int)v11,
            dwOptionsb);
        if ( hKey )
          RegCloseKey(hKey);
        std::wstring::~wstring(lpData);
      }
      v29 = 0;
      v30[0] = 0;
      v30[1] = si128;
      LOWORD(v30[0]) = 0;
      v31[0] = 0;
      v31[1] = si128;
      LOWORD(v31[0]) = 0;
      v26 = *(_OWORD *)(v4 + 200);
      v27 = *(_QWORD *)(v4 + 216);
      v28 = *(_DWORD *)(v4 + 224);
      v12 = (_QWORD *)(v4 + 232);
      if ( v30 != (_OWORD *)(v4 + 232) )
      {
        if ( *(_QWORD *)(v4 + 256) > 7u )
          v12 = (_QWORD *)*v12;
        std::wstring::_Assign<unsigned short>((void **)v30, v12, *(_QWORD *)(v4 + 248));
      }
      v13 = (_QWORD *)(v4 + 264);
      if ( v31 != (_OWORD *)(v4 + 264) )
      {
        if ( *(_QWORD *)(v4 + 288) > 7u )
          v13 = (_QWORD *)*v13;
        std::wstring::_Assign<unsigned short>((void **)v31, v13, *(_QWORD *)(v4 + 280));
      }
      *(_OWORD *)&v17[1] = v26;
      v17[3] = v27;
      v18 = v28;
      v19 = v29;
      std::wstring::wstring(v20, v30);
      std::wstring::wstring(v21, v31);
      ComputeService::Management::VmHostedContainer::SetupNetworkDeviceProperties(
        v4,
        &CompartmentGuid,
        lpValueName,
        (__int64)&v17[1]);
      std::wstring::~wstring(v31);
      std::wstring::~wstring(v30);
      std::wstring::~wstring(lpValueName);
      v4 += 296;
    }
    while ( v4 != v5 );
  }
}

```

## disassembly

```asm
0x1400ae234  mov     rax, rsp
0x1400ae237  mov     [rax+18h], rbx
0x1400ae23b  mov     [rax+20h], rdi
0x1400ae23f  push    rbp
0x1400ae240  lea     rbp, [rax-98h]
0x1400ae247  sub     rsp, 190h
0x1400ae24e  movaps  xmmword ptr [rax-18h], xmm6
0x1400ae252  mov     rax, cs:__security_cookie
0x1400ae259  xor     rax, rsp
0x1400ae25c  mov     [rbp+90h+var_20], rax
0x1400ae260  mov     eax, edx
0x1400ae262  mov     rdi, rcx
0x1400ae265  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400ae26c  movdqu  xmmword ptr [rbp+90h+CompartmentGuid.Data1], xmm0
0x1400ae271  cmp     edx, 2
0x1400ae274  jb      short loc_1400AE291
0x1400ae276  lea     rdx, [rbp+90h+CompartmentGuid]; CompartmentGuid
0x1400ae27a  mov     ecx, eax; CompartmentId
0x1400ae27c  call    cs:__imp_ConvertCompartmentIdToGuid
0x1400ae282  mov     rcx, [rbp+98h]; this
0x1400ae289  test    eax, eax
0x1400ae28b  jnz     loc_1400AE536
0x1400ae291  mov     rbx, [rdi]
0x1400ae294  mov     rdi, [rdi+8]
0x1400ae298  cmp     rbx, rdi
0x1400ae29b  jz      loc_1400AE4E6
0x1400ae2a1  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1400ae2a9  xorps   xmm0, xmm0
0x1400ae2ac  movups  xmmword ptr [rbp+90h+lpValueName], xmm0
0x1400ae2b0  movdqu  [rbp+90h+var_B0], xmm6
0x1400ae2b5  xor     eax, eax
0x1400ae2b7  mov     word ptr [rbp+90h+lpValueName], ax
0x1400ae2bb  lea     r8, [rbp+90h+lpValueName]
0x1400ae2bf  mov     edx, [rbx+0C4h]
0x1400ae2c5  mov     rcx, rbx
0x1400ae2c8  call    ?GetPnpInstanceId@Net@ComputeService@@YAXAEBU_GUID@@IAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Net::GetPnpInstanceId(_GUID const &,uint,std::wstring &)
0x1400ae2cd  mov     r8d, 10h; Size
0x1400ae2d3  lea     rdx, GUID_NULL; Buf2
0x1400ae2da  lea     rcx, [rbp+90h+CompartmentGuid]; Buf1
0x1400ae2de  call    memcmp_0
0x1400ae2e3  test    eax, eax
0x1400ae2e5  jz      loc_1400AE3BF
0x1400ae2eb  mov     r8b, 1
0x1400ae2ee  lea     rdx, [rbp+90h+CompartmentGuid]
0x1400ae2f2  lea     rcx, [rbp+90h+lpData]
0x1400ae2f6  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400ae2fb  nop
0x1400ae2fc  mov     [rbp+90h+hKey], 0
0x1400ae304  mov     [rsp+190h+lpdwDisposition], 0; lpdwDisposition
0x1400ae30d  lea     rax, [rbp+90h+hKey]
0x1400ae311  mov     [rsp+190h+phkResult], rax; phkResult
0x1400ae316  mov     [rsp+190h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400ae31f  mov     [rsp+190h+samDesired], 20006h; samDesired
0x1400ae327  mov     [rsp+190h+dwOptions], 1; int
0x1400ae32f  xor     r9d, r9d; lpClass
0x1400ae332  xor     r8d, r8d; Reserved
0x1400ae335  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ne"...
0x1400ae33c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400ae343  call    cs:__imp_RegCreateKeyExW
0x1400ae349  mov     rcx, [rbp+98h]; this
0x1400ae350  test    eax, eax
0x1400ae352  js      loc_1400AE521
0x1400ae358  mov     eax, [rbp+90h+var_30]
0x1400ae35b  lea     rcx, [rbp+90h+lpData]
0x1400ae35f  cmp     [rbp+90h+var_28], 7
0x1400ae364  cmova   rcx, [rbp+90h+lpData]
0x1400ae369  lea     r8, [rbp+90h+lpValueName]
0x1400ae36d  cmp     qword ptr [rbp+90h+var_B0+8], 7
0x1400ae372  cmova   r8, [rbp+90h+lpValueName]; lpValueName
0x1400ae377  lea     eax, ds:2[rax*2]
0x1400ae37e  mov     [rsp+190h+samDesired], eax; cbData
0x1400ae382  mov     qword ptr [rsp+190h+dwOptions], rcx; int
0x1400ae387  xor     edx, edx; lpSubKey
0x1400ae389  lea     r9d, [rdx+1]; dwType
0x1400ae38d  mov     rcx, [rbp+90h+hKey]; hKey
0x1400ae391  call    cs:__imp_RegSetKeyValueW
0x1400ae397  mov     rcx, [rbp+98h]; this
0x1400ae39e  test    eax, eax
0x1400ae3a0  js      loc_1400AE50C
0x1400ae3a6  mov     rcx, [rbp+90h+hKey]; hKey
0x1400ae3aa  test    rcx, rcx
0x1400ae3ad  jz      short loc_1400AE3B6
0x1400ae3af  call    cs:__imp_RegCloseKey
0x1400ae3b5  nop
0x1400ae3b6  lea     rcx, [rbp+90h+lpData]; void *
0x1400ae3ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae3bf  xorps   xmm0, xmm0
0x1400ae3c2  mov     [rbp+90h+var_84], 0
0x1400ae3c9  xorps   xmm1, xmm1
0x1400ae3cc  movups  [rbp+90h+var_80], xmm1
0x1400ae3d0  movdqa  [rbp+90h+var_70], xmm6
0x1400ae3d5  xor     eax, eax
0x1400ae3d7  mov     word ptr [rbp+90h+var_80], ax
0x1400ae3db  movups  [rbp+90h+var_60], xmm0
0x1400ae3df  movdqa  [rbp+90h+var_50], xmm6
0x1400ae3e4  mov     word ptr [rbp+90h+var_60], ax
0x1400ae3e8  movups  xmm0, xmmword ptr [rbx+0C8h]
0x1400ae3ef  movdqu  [rbp+90h+var_A0], xmm0
0x1400ae3f4  mov     rax, [rbx+0D8h]
0x1400ae3fb  mov     [rbp+90h+var_90], rax
0x1400ae3ff  mov     eax, [rbx+0E0h]
0x1400ae405  mov     [rbp+90h+var_88], eax
0x1400ae408  lea     rdx, [rbx+0E8h]
0x1400ae40f  lea     rax, [rbp+90h+var_80]
0x1400ae413  cmp     rax, rdx
0x1400ae416  jz      short loc_1400AE432
0x1400ae418  cmp     qword ptr [rdx+18h], 7
0x1400ae41d  jbe     short loc_1400AE422
0x1400ae41f  mov     rdx, [rdx]
0x1400ae422  mov     r8, [rbx+0F8h]
0x1400ae429  lea     rcx, [rbp+90h+var_80]
0x1400ae42d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400ae432  lea     rdx, [rbx+108h]
0x1400ae439  lea     rax, [rbp+90h+var_60]
0x1400ae43d  cmp     rax, rdx
0x1400ae440  jz      short loc_1400AE45C
0x1400ae442  cmp     qword ptr [rdx+18h], 7
0x1400ae447  jbe     short loc_1400AE44C
0x1400ae449  mov     rdx, [rdx]
0x1400ae44c  mov     r8, [rbx+118h]
0x1400ae453  lea     rcx, [rbp+90h+var_60]
0x1400ae457  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400ae45c  lea     rax, [rsp+190h+var_140+8]
0x1400ae461  mov     qword ptr [rsp+190h+var_140], rax
0x1400ae466  movaps  xmm0, [rbp+90h+var_A0]
0x1400ae46a  movdqu  xmmword ptr [rsp+190h+var_140+8], xmm0
0x1400ae470  mov     rax, [rbp+90h+var_90]
0x1400ae474  mov     [rsp+190h+var_128], rax
0x1400ae479  mov     eax, [rbp+90h+var_88]
0x1400ae47c  mov     [rsp+190h+var_120], eax
0x1400ae480  mov     eax, [rbp+90h+var_84]
0x1400ae483  mov     [rsp+190h+var_11C], eax
0x1400ae487  lea     rdx, [rbp+90h+var_80]
0x1400ae48b  lea     rcx, [rsp+190h+var_118]
0x1400ae490  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400ae495  nop
0x1400ae496  lea     rdx, [rbp+90h+var_60]
0x1400ae49a  lea     rcx, [rbp+90h+var_F8]
0x1400ae49e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400ae4a3  nop
0x1400ae4a4  lea     r9, [rsp+190h+var_140+8]
0x1400ae4a9  lea     r8, [rbp+90h+lpValueName]
0x1400ae4ad  lea     rdx, [rbp+90h+CompartmentGuid]
0x1400ae4b1  mov     rcx, rbx
0x1400ae4b4  call    ?SetupNetworkDeviceProperties@VmHostedContainer@Management@ComputeService@@YAXAEBU_GUID@@0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHNSInterfaceConstraint@HNS@Containers@Config@@@Z; ComputeService::Management::VmHostedContainer::SetupNetworkDeviceProperties(_GUID const &,_GUID const &,std::wstring const &,Config::Containers::HNS::HNSInterfaceConstraint)
0x1400ae4b9  nop
0x1400ae4ba  lea     rcx, [rbp+90h+var_60]; void *
0x1400ae4be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae4c3  lea     rcx, [rbp+90h+var_80]; void *
0x1400ae4c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae4cc  nop
0x1400ae4cd  lea     rcx, [rbp+90h+lpValueName]; void *
0x1400ae4d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae4d6  add     rbx, 128h
0x1400ae4dd  cmp     rbx, rdi
0x1400ae4e0  jnz     loc_1400AE2A9
0x1400ae4e6  mov     rcx, [rbp+90h+var_20]
0x1400ae4ea  xor     rcx, rsp; StackCookie
0x1400ae4ed  call    __security_check_cookie
0x1400ae4f2  lea     r11, [rsp+190h+var_s0]
0x1400ae4fa  mov     rbx, [r11+20h]
0x1400ae4fe  mov     rdi, [r11+28h]
0x1400ae502  movaps  xmm6, xmmword ptr [r11-10h]
0x1400ae507  mov     rsp, r11
0x1400ae50a  pop     rbp
0x1400ae50b  retn
0x1400ae50c  mov     r9d, eax; char *
0x1400ae50f  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae516  mov     edx, 0DDh; void *
0x1400ae51b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ae521  mov     r9d, eax; char *
0x1400ae524  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae52b  mov     edx, 0D3h; void *
0x1400ae530  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ae536  mov     r9d, eax; char *
0x1400ae539  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\management\\orche"...
0x1400ae540  mov     edx, 9Ah; void *
0x1400ae545  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
