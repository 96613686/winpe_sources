# VmUtilities::ReadRamMemoryBlockInformationInternal(VmRepository *,uint)

- ea: `0x140093290`
- end: `0x140093b47`
- name: `?ReadRamMemoryBlockInformationInternal@VmUtilities@@YA?AV?$optional@URamMemoryBlockInformation@VmUtilities@@@std@@PEAVVmRepository@@I@Z`
- size: `2231`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14023e540`

## callees

- `0x140017040`
- `0x14001bce0`
- `0x14002f8dc`
- `0x1400421f0`
- `0x14005a7a8`
- `0x14007864c`
- `0x1400857b4`
- `0x140093110`
- `0x140093138`
- `0x14009319c`
- `0x140093230`
- `0x140093290`
- `0x140093cac`
- `0x140093d04`
- `0x140094ba8`
- `0x1400c40e0`
- `0x1400c4154`
- `0x14010ddb4`
- `0x1401332f0`
- `0x140134048`
- `0x140189f38`
- `0x140190b40`
- `0x1402c4010`

## import_xrefs

- `ntdll!RtlInitializeBitMapEx` at `0x140093875`
- `ntdll!RtlInitializeBitMapEx` at `0x140093875`
- `ntdll!RtlNumberOfSetBitsEx` at `0x140093885`
- `ntdll!RtlNumberOfSetBitsEx` at `0x140093885`

## string_xrefs

- `0x14009331a`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400933f8`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x140093427`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14009346b`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x140093517`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14009354a`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14009360f`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400936ac`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400936f5`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14009384b`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400938a7`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x140093961`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x140093980`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400939a9`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x140093a02`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x140093a28`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x140093ac5`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x140093b16`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x140093b35`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall VmUtilities::ReadRamMemoryBlockInformationInternal(__int64 a1, __int64 a2, unsigned int a3)
{
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  _QWORD *v8; // rdx
  int v9; // eax
  _QWORD *v11; // rdx
  int v12; // eax
  unsigned __int64 v13; // r14
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  bool AzureFeatureSetEnabled; // al
  unsigned int v19; // eax
  unsigned __int64 v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  bool v25; // bl
  const unsigned __int16 *v26; // rdx
  _QWORD *v27; // rdx
  int v28; // eax
  unsigned __int64 v29; // rax
  _QWORD *v30; // rdx
  int v31; // eax
  const unsigned __int16 *v32; // rdx
  _QWORD *v33; // rdx
  int v34; // eax
  unsigned int v35; // r9d
  __int64 (__fastcall *v36)(__int64, _QWORD *, _QWORD, _QWORD); // rdi
  unsigned int v37; // ebx
  __m128i v38; // xmm6
  __int64 v39; // rax
  _QWORD *v40; // rdx
  int v41; // eax
  unsigned __int64 v42; // rax
  _QWORD *v43; // rdx
  int v44; // eax
  _QWORD *v45; // rdx
  int v46; // eax
  _QWORD *v47; // rdx
  int v48; // eax
  __int64 (__fastcall *v49)(__int64, _QWORD *, _QWORD, _QWORD); // rdi
  unsigned int v50; // ebx
  __int64 v51; // rax
  _QWORD *v52; // rdx
  int v53; // eax
  int v54; // [rsp+20h] [rbp-E0h]
  _QWORD v55[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v56; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v57; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v58[3]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v59; // [rsp+68h] [rbp-98h]
  __m128i v60; // [rsp+70h] [rbp-90h] BYREF
  int v61; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v62; // [rsp+84h] [rbp-7Ch] BYREF
  __int128 v63; // [rsp+88h] [rbp-78h] BYREF
  __int128 v64; // [rsp+98h] [rbp-68h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h]
  unsigned int v66; // [rsp+B0h] [rbp-50h] BYREF
  int v67; // [rsp+B4h] [rbp-4Ch]
  unsigned __int64 v68; // [rsp+B8h] [rbp-48h]
  unsigned __int8 v69; // [rsp+D0h] [rbp-30h]
  _QWORD v70[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v71[24]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v72[24]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v73; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v55[0] = a1;
  memset_0(&v66, 0, 0x40u);
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v71);
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v72);
  v73 = 0;
  v56 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 288LL))(a2, &v56);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
      (const char *)(unsigned int)v6,
      v54);
  std::wstring::wstring(v58);
  v61 = 0;
  v7 = L"RamMemoryBlock%d";
  if ( v56 < 0x600 )
    v7 = L"RamMemoryBlock/%d/";
  Vml::FormatString(v58, v7, a3);
  v8 = v58;
  if ( v59 > 7 )
    v8 = (_QWORD *)v58[0];
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD *, int *))(*(_QWORD *)a2 + 80LL))(a2, v8, &v61);
  if ( (unsigned int)RepositoryKeyFound(v9) )
  {
    if ( v56 == 1024 )
    {
      if ( v61 != 40 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x80048007LL,
          v54);
    }
    else if ( v56 >= 0x500 && v61 != 48 )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x80048007LL,
        v54);
    }
    v11 = v58;
    if ( v59 > 7 )
      v11 = (_QWORD *)v58[0];
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned int *))(*(_QWORD *)a2 + 88LL))(a2, v11, &v66);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)(unsigned int)v12,
        v54);
    v13 = v68;
    if ( !v68 || v66 > 3 || (v67 & 0xFFFFFFF0) != 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x80048007LL,
        v54);
    if ( (v67 & 2) != 0 )
    {
      v60 = 0;
      v14 = (__int64 *)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(v55);
      v15 = *v14;
      *v14 = 0;
      *(_QWORD *)&v63 = v15;
      VirtualizationSettings::VirtualizationSettings(&v60, v16, v17, &v63);
      std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&v63);
      std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(v55);
      AzureFeatureSetEnabled = VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v60);
      if ( v56 < !AzureFeatureSetEnabled + 2048 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x115,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x80048007LL,
          v54);
      std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&v60.m128i_u64[1]);
      v13 = v68;
    }
    if ( v69 >= 0x40u )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x8007000DLL,
        v54);
    v19 = v56;
    if ( v56 >= 0x901 )
    {
      if ( v56 == 2305 )
      {
        v60 = 0;
        v21 = (__int64 *)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(v55);
        v22 = *v21;
        *v21 = 0;
        *(_QWORD *)&v63 = v22;
        VirtualizationSettings::VirtualizationSettings(&v60, v23, v24, &v63);
        std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&v63);
        std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(v55);
        v25 = VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v60);
        std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(&v60.m128i_u64[1]);
        v20 = (-(__int64)v25 & 0xFF00000008LL) + 4294967288LL;
        v13 = v68;
        v19 = v56;
      }
      else
      {
        v20 = 0x10000000000LL;
      }
    }
    else
    {
      v20 = 4294967288LL;
    }
    if ( v13 > v20 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x8007000DLL,
        v54);
    v26 = L"RamMemoryBlockPageCountValid%d";
    if ( v19 < 0x600 )
      v26 = L"RamMemoryBlockPageCountValid/%d/";
    Vml::FormatString(v58, v26, a3);
    v27 = v58;
    if ( v59 > 7 )
      v27 = (_QWORD *)v58[0];
    v28 = (*(__int64 (__fastcall **)(__int64, _QWORD *, int *))(*(_QWORD *)a2 + 80LL))(a2, v27, &v61);
    if ( (unsigned int)RepositoryKeyFound(v28) )
    {
      v30 = v58;
      if ( v59 > 7 )
        v30 = (_QWORD *)v58[0];
      v31 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *))(*(_QWORD *)a2 + 120LL))(a2, v30, v70);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v31,
          v54);
      v29 = v70[0];
    }
    else
    {
      v29 = v13;
      v70[0] = v13;
    }
    if ( !v13 || v29 > v13 || !v29 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x8007000DLL,
        v54);
    if ( v29 != v13 && (v67 & 1) == 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x169,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x8007000DLL,
        v54);
    v32 = L"RamMemoryBlockBackingBitmap%d";
    if ( v56 < 0x600 )
      v32 = L"RamMemoryBlockBackingBitmap/%d/";
    Vml::FormatString(v58, v32, a3);
    v62 = 0;
    v33 = v58;
    if ( v59 > 7 )
      v33 = (_QWORD *)v58[0];
    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, v33, &v62);
    if ( (unsigned int)RepositoryKeyFound(v34) )
    {
      v35 = 8;
      if ( v56 <= 0x900 )
        v35 = 4;
      if ( v62 % v35 || v62 / v35 != (v13 + 8 * v35 - 1) / (8 * v35) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x80004005LL,
          v54);
      v55[0] = 0;
      v64 = 0;
      v65 = 0;
      std::vector<unsigned __int64>::_Construct_n<unsigned __int64 const &>(&v64, ((unsigned __int64)v62 + 7) >> 3, v55);
      v60 = 0;
      gsl::span<unsigned __int64,-1>::span<unsigned __int64,-1>(&v60, &v64);
      v36 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL);
      v37 = v62;
      v38 = v60;
      v39 = gsl::as_writable_bytes<unsigned __int64,-1,0>(v55, &v60);
      v40 = v58;
      if ( v59 > 7 )
        v40 = (_QWORD *)v58[0];
      v41 = v36(a2, v40, *(_QWORD *)(v39 + 8), v37);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v41,
          v54);
      v63 = 0;
      RtlInitializeBitMapEx(&v63, _mm_srli_si128(v38, 8).m128i_u64[0], v13);
      v42 = RtlNumberOfSetBitsEx(&v63);
      if ( v42 > v70[0] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x19F,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x8007000DLL,
          v54);
      v70[1] = v70[0] - v42;
      std::vector<Config::VirtualMachine::VpSubnodeMetadata>::operator=(v71, &v64);
      std::vector<Schema::Resources::Processor::NumaNodeProcessor>::_Tidy(&v64);
    }
    Vml::FormatString(v58, L"RamMemoryBlockFaultClusterSizeShift%d", a3);
    v57 = 0;
    v43 = v58;
    if ( v59 > 7 )
      v43 = (_QWORD *)v58[0];
    v44 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, v43, &v57);
    if ( (unsigned int)RepositoryKeyFound(v44) )
    {
      *(_QWORD *)&v63 = 0;
      v45 = v58;
      if ( v59 > 7 )
        v45 = (_QWORD *)v58[0];
      v46 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *))(*(_QWORD *)a2 + 120LL))(a2, v45, &v63);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v46,
          v54);
      if ( (unsigned __int64)v63 > 0xFF )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1BE,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x570,
          v54);
      Vml::FormatString(v58, L"RamMemoryBlockFaultClusterBitmap%d", a3);
      v47 = v58;
      if ( v59 > 7 )
        v47 = (_QWORD *)v58[0];
      v48 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, v47, &v57);
      if ( v48 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CC,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v48,
          v54);
      if ( (v57 & 7) != 0 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1D0,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x570,
          v54);
      v64 = 0;
      v65 = 0;
      std::vector<unsigned __int64>::vector<unsigned __int64>(&v64, (unsigned __int64)v57 >> 3);
      v60 = 0;
      gsl::span<unsigned __int64,-1>::span<unsigned __int64,-1>(&v60, &v64);
      v49 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL);
      v50 = v57;
      v51 = gsl::as_writable_bytes<unsigned __int64,-1,0>(v55, &v60);
      v52 = v58;
      if ( v59 > 7 )
        v52 = (_QWORD *)v58[0];
      v53 = v49(a2, v52, *(_QWORD *)(v51 + 8), v50);
      if ( v53 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D9,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v53,
          v54);
      std::vector<Config::VirtualMachine::VpSubnodeMetadata>::operator=(v72, &v64);
      LOBYTE(v73) = v63;
      std::vector<Schema::Resources::Processor::NumaNodeProcessor>::_Tidy(&v64);
    }
    VmUtilities::RamMemoryBlockInformation::RamMemoryBlockInformation(a1, &v66);
    *(_BYTE *)(a1 + 120) = 1;
  }
  else
  {
    *(_BYTE *)(a1 + 120) = 0;
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v58);
  VmUtilities::RamMemoryBlockInformation::~RamMemoryBlockInformation((VmUtilities::RamMemoryBlockInformation *)&v66);
  return a1;
}

```

## disassembly

```asm
0x140093290  mov     rax, rsp
0x140093293  push    rbp
0x140093294  push    rbx
0x140093295  push    rsi
0x140093296  push    rdi
0x140093297  push    r12
0x140093299  push    r14
0x14009329b  push    r15
0x14009329d  lea     rbp, [rsp-50h]
0x1400932a2  sub     rsp, 150h
0x1400932a9  movaps  xmmword ptr [rax-48h], xmm6
0x1400932ad  mov     rax, cs:__security_cookie
0x1400932b4  xor     rax, rsp
0x1400932b7  mov     [rbp+80h+var_50], rax
0x1400932bb  mov     r12d, r8d
0x1400932be  mov     rsi, rdx
0x1400932c1  mov     r15, rcx
0x1400932c4  mov     [rsp+180h+var_150], rcx
0x1400932c9  xor     edx, edx; Val
0x1400932cb  lea     r8d, [rdx+40h]; Size
0x1400932cf  lea     rcx, [rbp+80h+var_D0]; void *
0x1400932d3  call    memset_0
0x1400932d8  lea     rcx, [rbp+80h+var_90]
0x1400932dc  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x1400932e1  lea     rcx, [rbp+80h+var_78]
0x1400932e5  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x1400932ea  nop
0x1400932eb  xor     eax, eax
0x1400932ed  mov     [rbp+80h+var_60], rax
0x1400932f1  mov     [rsp+180h+var_13C], eax
0x1400932f5  mov     rax, [rsi]
0x1400932f8  lea     rdx, [rsp+180h+var_13C]
0x1400932fd  mov     rcx, rsi
0x140093300  mov     rax, [rax+120h]
0x140093307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009330c  mov     rcx, [rbp+88h]; this
0x140093313  test    eax, eax
0x140093315  jns     short loc_14009332C
0x140093317  mov     r9d, eax; char *
0x14009331a  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x140093321  mov     edx, 0DEh; void *
0x140093326  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009332c  lea     rcx, [rsp+180h+var_130]; void *
0x140093331  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140093336  nop
0x140093337  mov     [rbp+80h+var_100], 0
0x14009333e  lea     rdx, ?MEMORY_BLOCK_KEY_FORMAT_V2@@3QBGB; "RamMemoryBlock%d"
0x140093345  lea     rax, ?MEMORY_BLOCK_KEY_FORMAT@@3QBGB; "RamMemoryBlock/%d/"
0x14009334c  mov     edi, 600h
0x140093351  cmp     [rsp+180h+var_13C], edi
0x140093355  cmovb   rdx, rax
0x140093359  mov     r8d, r12d
0x14009335c  lea     rcx, [rsp+180h+var_130]
0x140093361  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x140093366  mov     rax, [rsi]
0x140093369  lea     rdx, [rsp+180h+var_130]
0x14009336e  cmp     [rsp+180h+var_118], 7
0x140093374  cmova   rdx, [rsp+180h+var_130]
0x14009337a  lea     r8, [rbp+80h+var_100]
0x14009337e  mov     rcx, rsi
0x140093381  mov     rax, [rax+50h]
0x140093385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009338a  mov     ecx, eax; int
0x14009338c  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x140093391  test    eax, eax
0x140093393  jnz     short loc_1400933D7
0x140093395  mov     [r15+78h], al
0x140093399  lea     rcx, [rsp+180h+var_130]; this
0x14009339e  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400933a3  nop
0x1400933a4  lea     rcx, [rbp+80h+var_D0]; this
0x1400933a8  call    ??1RamMemoryBlockInformation@VmUtilities@@QEAA@XZ; VmUtilities::RamMemoryBlockInformation::~RamMemoryBlockInformation(void)
0x1400933ad  mov     rax, r15
0x1400933b0  mov     rcx, [rbp+80h+var_50]
0x1400933b4  xor     rcx, rsp; StackCookie
0x1400933b7  call    __security_check_cookie
0x1400933bc  movaps  xmm6, [rsp+180h+var_40]
0x1400933c4  add     rsp, 150h
0x1400933cb  pop     r15
0x1400933cd  pop     r14
0x1400933cf  pop     r12
0x1400933d1  pop     rdi
0x1400933d2  pop     rsi
0x1400933d3  pop     rbx
0x1400933d4  pop     rbp
0x1400933d5  retn
0x1400933d7  mov     r9d, [rbp+80h+var_100]
0x1400933db  cmp     [rsp+180h+var_13C], 400h
0x1400933e3  jnz     short loc_14009340A
0x1400933e5  cmp     r9d, 28h ; '('
0x1400933e9  jz      short loc_140093439
0x1400933eb  mov     rcx, [rbp+88h]; this
0x1400933f2  mov     r9d, 80048007h; char *
0x1400933f8  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400933ff  mov     edx, 0F5h; void *
0x140093404  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009340a  cmp     [rsp+180h+var_13C], 500h
0x140093412  jb      short loc_140093439
0x140093414  cmp     r9d, 30h ; '0'
0x140093418  jz      short loc_140093439
0x14009341a  mov     rcx, [rbp+88h]; this
0x140093421  mov     r9d, 80048007h; char *
0x140093427  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14009342e  mov     edx, 0FCh; void *
0x140093433  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140093439  mov     rax, [rsi]
0x14009343c  lea     rdx, [rsp+180h+var_130]
0x140093441  cmp     [rsp+180h+var_118], 7
0x140093447  cmova   rdx, [rsp+180h+var_130]
0x14009344d  lea     r8, [rbp+80h+var_D0]
0x140093451  mov     rcx, rsi
0x140093454  mov     rax, [rax+58h]
0x140093458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009345d  mov     rcx, [rbp+88h]; this
0x140093464  test    eax, eax
0x140093466  jns     short loc_14009347D
0x140093468  mov     r9d, eax; char *
0x14009346b  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x140093472  mov     edx, 106h; void *
0x140093477  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009347d  mov     r14, [rbp+80h+var_C8]
0x140093481  test    r14, r14
0x140093484  jz      loc_140093B28
0x14009348a  cmp     [rbp+80h+var_D0], 3
0x14009348e  ja      loc_140093B28
0x140093494  test    [rbp+80h+var_CC], 0FFFFFFF0h
0x14009349b  jnz     loc_140093B28
0x1400934a1  test    byte ptr [rbp+80h+var_CC], 2
0x1400934a5  jz      loc_140093537
0x1400934ab  xorps   xmm0, xmm0
0x1400934ae  movups  [rsp+180h+var_110], xmm0
0x1400934b3  lea     rcx, [rsp+180h+var_150]
0x1400934b8  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x1400934bd  nop
0x1400934be  mov     rcx, [rax]
0x1400934c1  mov     qword ptr [rax], 0
0x1400934c8  mov     qword ptr [rbp+80h+var_F8], rcx
0x1400934cc  lea     r9, [rbp+80h+var_F8]
0x1400934d0  lea     rcx, [rsp+180h+var_110]
0x1400934d5  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x1400934da  nop
0x1400934db  lea     rcx, [rbp+80h+var_F8]
0x1400934df  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x1400934e4  nop
0x1400934e5  lea     rcx, [rsp+180h+var_150]
0x1400934ea  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x1400934ef  lea     rcx, [rsp+180h+var_110]; this
0x1400934f4  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x1400934f9  movzx   eax, al
0x1400934fc  xor     eax, 1
0x1400934ff  add     eax, 800h
0x140093504  cmp     [rsp+180h+var_13C], eax
0x140093508  jnb     short loc_140093529
0x14009350a  mov     rcx, [rbp+88h]; this
0x140093511  mov     r9d, 80048007h; char *
0x140093517  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14009351e  mov     edx, 115h; void *
0x140093523  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140093529  lea     rcx, [rsp+180h+var_110+8]
0x14009352e  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x140093533  mov     r14, [rbp+80h+var_C8]
0x140093537  cmp     [rbp+80h+var_B0], 40h ; '@'
0x14009353b  jb      short loc_14009355C
0x14009353d  mov     rcx, [rbp+88h]; this
0x140093544  mov     r9d, 8007000Dh; char *
0x14009354a  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x140093551  mov     edx, 11Fh; void *
0x140093556  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009355c  mov     eax, [rsp+180h+var_13C]
0x140093560  mov     ecx, 901h
0x140093565  cmp     eax, ecx
0x140093567  jnb     short loc_140093573
0x140093569  mov     ecx, 0FFFFFFF8h
0x14009356e  jmp     loc_1400935FD
0x140093573  jnz     short loc_1400935F3
0x140093575  xorps   xmm0, xmm0
0x140093578  movups  [rsp+180h+var_110], xmm0
0x14009357d  lea     rcx, [rsp+180h+var_150]
0x140093582  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x140093587  nop
0x140093588  mov     rcx, [rax]
0x14009358b  mov     qword ptr [rax], 0
0x140093592  mov     qword ptr [rbp+80h+var_F8], rcx
0x140093596  lea     r9, [rbp+80h+var_F8]
0x14009359a  lea     rcx, [rsp+180h+var_110]
0x14009359f  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x1400935a4  nop
0x1400935a5  lea     rcx, [rbp+80h+var_F8]
0x1400935a9  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x1400935ae  nop
0x1400935af  lea     rcx, [rsp+180h+var_150]
0x1400935b4  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x1400935b9  lea     rcx, [rsp+180h+var_110]; this
0x1400935be  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x1400935c3  mov     bl, al
0x1400935c5  lea     rcx, [rsp+180h+var_110+8]
0x1400935ca  call    ??1?$unique_ptr@UComputeSystemConfiguration@Management@ComputeService@@U?$default_delete@UComputeSystemConfiguration@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ComputeSystemConfiguration>::~unique_ptr<ComputeService::Management::ComputeSystemConfiguration>(void)
0x1400935cf  neg     bl
0x1400935d1  sbb     rax, rax
0x1400935d4  mov     rcx, 0FF00000008h
0x1400935de  and     rax, rcx
0x1400935e1  mov     ecx, 0FFFFFFF8h
0x1400935e6  add     rcx, rax
0x1400935e9  mov     r14, [rbp+80h+var_C8]
0x1400935ed  mov     eax, [rsp+180h+var_13C]
0x1400935f1  jmp     short loc_1400935FD
0x1400935f3  mov     rcx, 10000000000h
0x1400935fd  cmp     r14, rcx
0x140093600  jbe     short loc_140093621
0x140093602  mov     rcx, [rbp+88h]; this
0x140093609  mov     r9d, 8007000Dh; char *
0x14009360f  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x140093616  mov     edx, 13Ch; void *
0x14009361b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140093621  lea     rdx, ?MEMORY_BLOCK_PAGE_COUNT_VALID_FORMAT_V2@@3QBGB; "RamMemoryBlockPageCountValid%d"
0x140093628  lea     rcx, ?MEMORY_BLOCK_PAGE_COUNT_VALID_FORMAT@@3QBGB; "RamMemoryBlockPageCountValid/%d/"
0x14009362f  cmp     eax, edi
0x140093631  cmovb   rdx, rcx
0x140093635  mov     r8d, r12d
0x140093638  lea     rcx, [rsp+180h+var_130]
0x14009363d  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x140093642  mov     rax, [rsi]
0x140093645  lea     rdx, [rsp+180h+var_130]
0x14009364a  cmp     [rsp+180h+var_118], 7
0x140093650  cmova   rdx, [rsp+180h+var_130]
0x140093656  lea     r8, [rbp+80h+var_100]
0x14009365a  mov     rcx, rsi
0x14009365d  mov     rax, [rax+50h]
0x140093661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093666  mov     ecx, eax; int
0x140093668  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x14009366d  test    eax, eax
0x14009366f  jnz     short loc_14009367A
0x140093671  mov     rax, r14
0x140093674  mov     [rbp+80h+var_A0], rax
0x140093678  jmp     short loc_1400936C2
0x14009367a  mov     rax, [rsi]
0x14009367d  lea     rdx, [rsp+180h+var_130]
0x140093682  cmp     [rsp+180h+var_118], 7
0x140093688  cmova   rdx, [rsp+180h+var_130]
0x14009368e  lea     r8, [rbp+80h+var_A0]
0x140093692  mov     rcx, rsi
0x140093695  mov     rax, [rax+78h]
0x140093699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009369e  mov     rcx, [rbp+88h]; this
0x1400936a5  test    eax, eax
0x1400936a7  jns     short loc_1400936BE
0x1400936a9  mov     r9d, eax; char *
0x1400936ac  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400936b3  mov     edx, 155h; void *
0x1400936b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400936be  mov     rax, [rbp+80h+var_A0]
0x1400936c2  test    r14, r14
0x1400936c5  jz      loc_140093B09
0x1400936cb  cmp     rax, r14
0x1400936ce  ja      loc_140093B09
0x1400936d4  test    rax, rax
0x1400936d7  jz      loc_140093B09
0x1400936dd  cmp     rax, r14
0x1400936e0  jz      short loc_140093707
0x1400936e2  test    byte ptr [rbp+80h+var_CC], 1
0x1400936e6  jnz     short loc_140093707
0x1400936e8  mov     rcx, [rbp+88h]; this
0x1400936ef  mov     r9d, 8007000Dh; char *
0x1400936f5  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400936fc  mov     edx, 169h; void *
0x140093701  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140093707  lea     rdx, ?MEMORY_BLOCK_BACKING_BITMAP_FORMAT_V2@@3QBGB; "RamMemoryBlockBackingBitmap%d"
0x14009370e  lea     rax, ?MEMORY_BLOCK_BACKING_BITMAP_FORMAT@@3QBGB; "RamMemoryBlockBackingBitmap/%d/"
0x140093715  cmp     [rsp+180h+var_13C], edi
0x140093719  cmovb   rdx, rax
0x14009371d  mov     r8d, r12d
0x140093720  lea     rcx, [rsp+180h+var_130]
0x140093725  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x14009372a  mov     [rbp+80h+var_FC], 0
0x140093731  mov     rax, [rsi]
0x140093734  lea     rdx, [rsp+180h+var_130]
0x140093739  cmp     [rsp+180h+var_118], 7
0x14009373f  cmova   rdx, [rsp+180h+var_130]
0x140093745  lea     r8, [rbp+80h+var_FC]
0x140093749  mov     rcx, rsi
0x14009374c  mov     rax, [rax+50h]
0x140093750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093755  mov     ecx, eax; int
0x140093757  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x14009375c  test    eax, eax
0x14009375e  jz      loc_1400938D7
0x140093764  mov     eax, 4
0x140093769  lea     r9d, [rax+4]
0x14009376d  cmp     [rsp+180h+var_13C], 900h
0x140093775  cmovbe  r9d, eax
0x140093779  xor     edx, edx
0x14009377b  mov     r10d, [rbp+80h+var_FC]
0x14009377f  mov     eax, r10d
0x140093782  div     r9d
0x140093785  test    edx, edx
0x140093787  jnz     loc_140093973
0x14009378d  lea     ecx, ds:0[r9*8]
0x140093795  lea     eax, [rcx-1]
0x140093798  add     rax, r14
  ... truncated ...
```
