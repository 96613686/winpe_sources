# VmUtilities::ReadRamMemoryBlockInformationInternal(VmRepository *,uint)

- ea: `0x1400a4238`
- end: `0x1400a4afe`
- name: `?ReadRamMemoryBlockInformationInternal@VmUtilities@@YA?AV?$optional@URamMemoryBlockInformation@VmUtilities@@@std@@PEAVVmRepository@@I@Z`
- size: `2246`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1401d54a4`

## callees

- `0x14003d828`
- `0x14004b838`
- `0x14005def8`
- `0x14005df20`
- `0x14005dfdc`
- `0x14005e07c`
- `0x140069058`
- `0x1400690dc`
- `0x140078628`
- `0x1400a3664`
- `0x1400a368c`
- `0x1400a3718`
- `0x1400a3cb0`
- `0x1400a4238`
- `0x1400a5d70`
- `0x1400a5dbc`
- `0x1400a606c`
- `0x1400ba144`
- `0x14011ea40`
- `0x14011f6fc`
- `0x1402cb010`

## import_xrefs

- `ntdll!RtlInitializeBitMapEx` at `0x1400a482c`
- `ntdll!RtlInitializeBitMapEx` at `0x1400a482c`
- `ntdll!RtlNumberOfSetBitsEx` at `0x1400a483c`
- `ntdll!RtlNumberOfSetBitsEx` at `0x1400a483c`

## string_xrefs

- `0x1400a42c4`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a43b0`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a43df`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4423`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a44cf`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4502`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a45c7`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4664`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a46ad`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4802`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a485e`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4918`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4937`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4960`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a49b9`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a49df`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4a7c`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4acd`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x1400a4aec`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall VmUtilities::ReadRamMemoryBlockInformationInternal(__int64 a1, __int64 a2, unsigned int a3)
{
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  __int128 *v8; // rdx
  int v9; // eax
  __int128 *v11; // rdx
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
  __int128 *v27; // rdx
  int v28; // eax
  unsigned __int64 v29; // rax
  __int128 *v30; // rdx
  int v31; // eax
  const unsigned __int16 *v32; // rdx
  __int128 *v33; // rdx
  int v34; // eax
  unsigned int v35; // r9d
  __int64 (__fastcall *v36)(__int64, __int128 *, _QWORD, _QWORD); // rdi
  unsigned int v37; // ebx
  __m128i v38; // xmm6
  __int64 v39; // rax
  __int128 *v40; // rdx
  int v41; // eax
  unsigned __int64 v42; // rax
  __int128 *v43; // rdx
  int v44; // eax
  __int128 *v45; // rdx
  int v46; // eax
  __int128 *v47; // rdx
  int v48; // eax
  __int64 (__fastcall *v49)(__int64, __int128 *, _QWORD, _QWORD); // rdi
  unsigned int v50; // ebx
  __int64 v51; // rax
  __int128 *v52; // rdx
  int v53; // eax
  unsigned int v54; // [rsp+20h] [rbp-E0h]
  _QWORD v55[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v56; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v57; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v58; // [rsp+50h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A0h]
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
  _OWORD v71[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v72; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v55[0] = a1;
  memset_0(&v66, 0, 0x40u);
  memset(v71, 0, sizeof(v71));
  v72 = 0;
  v56 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 288LL))(a2, &v56);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
      (const char *)(unsigned int)v6,
      v54);
  v58 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v58) = 0;
  v61 = 0;
  v7 = L"RamMemoryBlock%d";
  if ( v56 < 0x600 )
    v7 = L"RamMemoryBlock/%d/";
  Vml::FormatString(&v58, v7, a3);
  v8 = &v58;
  if ( si128.m128i_i64[1] > 7uLL )
    v8 = (__int128 *)v58;
  v9 = (*(__int64 (__fastcall **)(__int64, __int128 *, int *))(*(_QWORD *)a2 + 80LL))(a2, v8, &v61);
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
    v11 = &v58;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (__int128 *)v58;
    v12 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)a2 + 88LL))(a2, v11, &v66);
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
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v63);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(v55);
      AzureFeatureSetEnabled = VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v60);
      if ( v56 < !AzureFeatureSetEnabled + 2048 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x115,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x80048007LL,
          v54);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v60.m128i_u64[1]);
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
        std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v63);
        std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(v55);
        v25 = VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v60);
        std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v60.m128i_u64[1]);
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
    Vml::FormatString(&v58, v26, a3);
    v27 = &v58;
    if ( si128.m128i_i64[1] > 7uLL )
      v27 = (__int128 *)v58;
    v28 = (*(__int64 (__fastcall **)(__int64, __int128 *, int *))(*(_QWORD *)a2 + 80LL))(a2, v27, &v61);
    if ( (unsigned int)RepositoryKeyFound(v28) )
    {
      v30 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v30 = (__int128 *)v58;
      v31 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *))(*(_QWORD *)a2 + 120LL))(a2, v30, v70);
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
    Vml::FormatString(&v58, v32, a3);
    v62 = 0;
    v33 = &v58;
    if ( si128.m128i_i64[1] > 7uLL )
      v33 = (__int128 *)v58;
    v34 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, v33, &v62);
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
      v64 = 0;
      v65 = 0;
      v55[0] = 0;
      std::vector<unsigned __int64>::vector<unsigned __int64>(&v64, ((unsigned __int64)v62 + 7) >> 3, v55);
      v60 = 0;
      gsl::span<unsigned __int64,-1>::span<unsigned __int64,-1>(&v60, &v64);
      v36 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL);
      v37 = v62;
      v38 = v60;
      v39 = gsl::as_writable_bytes<unsigned __int64,-1,0>(v55, &v60);
      v40 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v40 = (__int128 *)v58;
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
      std::vector<__int64>::operator=(v71, &v64);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>(&v64);
    }
    Vml::FormatString(&v58, L"RamMemoryBlockFaultClusterSizeShift%d", a3);
    v57 = 0;
    v43 = &v58;
    if ( si128.m128i_i64[1] > 7uLL )
      v43 = (__int128 *)v58;
    v44 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, v43, &v57);
    if ( (unsigned int)RepositoryKeyFound(v44) )
    {
      *(_QWORD *)&v63 = 0;
      v45 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v45 = (__int128 *)v58;
      v46 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)a2 + 120LL))(a2, v45, &v63);
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
      Vml::FormatString(&v58, L"RamMemoryBlockFaultClusterBitmap%d", a3);
      v47 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v47 = (__int128 *)v58;
      v48 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, v47, &v57);
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
      v49 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL);
      v50 = v57;
      v51 = gsl::as_writable_bytes<unsigned __int64,-1,0>(v55, &v60);
      v52 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v52 = (__int128 *)v58;
      v53 = v49(a2, v52, *(_QWORD *)(v51 + 8), v50);
      if ( v53 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D9,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v53,
          v54);
      std::vector<__int64>::operator=((char *)&v71[1] + 8, &v64);
      LOBYTE(v72) = v63;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>(&v64);
    }
    VmUtilities::RamMemoryBlockInformation::RamMemoryBlockInformation(a1, &v66);
    *(_BYTE *)(a1 + 120) = 1;
  }
  else
  {
    *(_BYTE *)(a1 + 120) = 0;
  }
  std::wstring::_Tidy_deallocate(&v58);
  VmUtilities::RamMemoryBlockInformation::~RamMemoryBlockInformation((VmUtilities::RamMemoryBlockInformation *)&v66);
  return a1;
}

```

## disassembly

```asm
0x1400a4238  mov     rax, rsp
0x1400a423b  push    rbp
0x1400a423c  push    rbx
0x1400a423d  push    rsi
0x1400a423e  push    rdi
0x1400a423f  push    r12
0x1400a4241  push    r14
0x1400a4243  push    r15
0x1400a4245  lea     rbp, [rsp-50h]
0x1400a424a  sub     rsp, 150h
0x1400a4251  movaps  xmmword ptr [rax-48h], xmm6
0x1400a4255  mov     rax, cs:__security_cookie
0x1400a425c  xor     rax, rsp
0x1400a425f  mov     [rbp+80h+var_50], rax
0x1400a4263  mov     r12d, r8d
0x1400a4266  mov     rsi, rdx
0x1400a4269  mov     r15, rcx
0x1400a426c  mov     [rsp+180h+var_150], rcx
0x1400a4271  xor     edx, edx; Val
0x1400a4273  lea     r8d, [rdx+40h]; Size
0x1400a4277  lea     rcx, [rbp+80h+var_D0]; void *
0x1400a427b  call    memset_0
0x1400a4280  xorps   xmm0, xmm0
0x1400a4283  movdqa  [rbp+80h+var_90], xmm0
0x1400a4288  xorps   xmm1, xmm1
0x1400a428b  movdqa  [rbp+80h+var_80], xmm1
0x1400a4290  movdqa  [rbp+80h+var_70], xmm0
0x1400a4295  xor     eax, eax
0x1400a4297  mov     [rbp+80h+var_60], rax
0x1400a429b  mov     [rsp+180h+var_13C], eax
0x1400a429f  mov     rax, [rsi]
0x1400a42a2  lea     rdx, [rsp+180h+var_13C]
0x1400a42a7  mov     rcx, rsi
0x1400a42aa  mov     rax, [rax+120h]
0x1400a42b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a42b6  mov     rcx, [rbp+88h]; this
0x1400a42bd  test    eax, eax
0x1400a42bf  jns     short loc_1400A42D6
0x1400a42c1  mov     r9d, eax; char *
0x1400a42c4  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400a42cb  mov     edx, 0DEh; void *
0x1400a42d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a42d6  xorps   xmm0, xmm0
0x1400a42d9  movups  [rsp+180h+var_130], xmm0
0x1400a42de  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400a42e6  movdqu  [rsp+180h+var_120], xmm1
0x1400a42ec  xor     eax, eax
0x1400a42ee  mov     word ptr [rsp+180h+var_130], ax
0x1400a42f3  mov     [rbp+80h+var_100], eax
0x1400a42f6  lea     rdx, ?MEMORY_BLOCK_KEY_FORMAT_V2@@3QBGB; "RamMemoryBlock%d"
0x1400a42fd  lea     rax, ?MEMORY_BLOCK_KEY_FORMAT@@3QBGB; "RamMemoryBlock/%d/"
0x1400a4304  mov     edi, 600h
0x1400a4309  cmp     [rsp+180h+var_13C], edi
0x1400a430d  cmovb   rdx, rax
0x1400a4311  mov     r8d, r12d
0x1400a4314  lea     rcx, [rsp+180h+var_130]
0x1400a4319  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x1400a431e  mov     rax, [rsi]
0x1400a4321  lea     rdx, [rsp+180h+var_130]
0x1400a4326  cmp     qword ptr [rsp+180h+var_120+8], 7
0x1400a432c  cmova   rdx, qword ptr [rsp+180h+var_130]
0x1400a4332  lea     r8, [rbp+80h+var_100]
0x1400a4336  mov     rcx, rsi
0x1400a4339  mov     rax, [rax+50h]
0x1400a433d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4342  mov     ecx, eax; int
0x1400a4344  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400a4349  test    eax, eax
0x1400a434b  jnz     short loc_1400A438F
0x1400a434d  mov     [r15+78h], al
0x1400a4351  lea     rcx, [rsp+180h+var_130]
0x1400a4356  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400a435b  nop
0x1400a435c  lea     rcx, [rbp+80h+var_D0]; this
0x1400a4360  call    ??1RamMemoryBlockInformation@VmUtilities@@QEAA@XZ; VmUtilities::RamMemoryBlockInformation::~RamMemoryBlockInformation(void)
0x1400a4365  mov     rax, r15
0x1400a4368  mov     rcx, [rbp+80h+var_50]
0x1400a436c  xor     rcx, rsp; StackCookie
0x1400a436f  call    __security_check_cookie
0x1400a4374  movaps  xmm6, [rsp+180h+var_40]
0x1400a437c  add     rsp, 150h
0x1400a4383  pop     r15
0x1400a4385  pop     r14
0x1400a4387  pop     r12
0x1400a4389  pop     rdi
0x1400a438a  pop     rsi
0x1400a438b  pop     rbx
0x1400a438c  pop     rbp
0x1400a438d  retn
0x1400a438f  mov     r9d, [rbp+80h+var_100]
0x1400a4393  cmp     [rsp+180h+var_13C], 400h
0x1400a439b  jnz     short loc_1400A43C2
0x1400a439d  cmp     r9d, 28h ; '('
0x1400a43a1  jz      short loc_1400A43F1
0x1400a43a3  mov     rcx, [rbp+88h]; this
0x1400a43aa  mov     r9d, 80048007h; char *
0x1400a43b0  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400a43b7  mov     edx, 0F5h; void *
0x1400a43bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a43c2  cmp     [rsp+180h+var_13C], 500h
0x1400a43ca  jb      short loc_1400A43F1
0x1400a43cc  cmp     r9d, 30h ; '0'
0x1400a43d0  jz      short loc_1400A43F1
0x1400a43d2  mov     rcx, [rbp+88h]; this
0x1400a43d9  mov     r9d, 80048007h; char *
0x1400a43df  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400a43e6  mov     edx, 0FCh; void *
0x1400a43eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a43f1  mov     rax, [rsi]
0x1400a43f4  lea     rdx, [rsp+180h+var_130]
0x1400a43f9  cmp     qword ptr [rsp+180h+var_120+8], 7
0x1400a43ff  cmova   rdx, qword ptr [rsp+180h+var_130]
0x1400a4405  lea     r8, [rbp+80h+var_D0]
0x1400a4409  mov     rcx, rsi
0x1400a440c  mov     rax, [rax+58h]
0x1400a4410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4415  mov     rcx, [rbp+88h]; this
0x1400a441c  test    eax, eax
0x1400a441e  jns     short loc_1400A4435
0x1400a4420  mov     r9d, eax; char *
0x1400a4423  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400a442a  mov     edx, 106h; void *
0x1400a442f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a4435  mov     r14, [rbp+80h+var_C8]
0x1400a4439  test    r14, r14
0x1400a443c  jz      loc_1400A4ADF
0x1400a4442  cmp     [rbp+80h+var_D0], 3
0x1400a4446  ja      loc_1400A4ADF
0x1400a444c  test    [rbp+80h+var_CC], 0FFFFFFF0h
0x1400a4453  jnz     loc_1400A4ADF
0x1400a4459  test    byte ptr [rbp+80h+var_CC], 2
0x1400a445d  jz      loc_1400A44EF
0x1400a4463  xorps   xmm0, xmm0
0x1400a4466  movups  [rsp+180h+var_110], xmm0
0x1400a446b  lea     rcx, [rsp+180h+var_150]
0x1400a4470  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x1400a4475  nop
0x1400a4476  mov     rcx, [rax]
0x1400a4479  mov     qword ptr [rax], 0
0x1400a4480  mov     qword ptr [rbp+80h+var_F8], rcx
0x1400a4484  lea     r9, [rbp+80h+var_F8]
0x1400a4488  lea     rcx, [rsp+180h+var_110]
0x1400a448d  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x1400a4492  nop
0x1400a4493  lea     rcx, [rbp+80h+var_F8]
0x1400a4497  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x1400a449c  nop
0x1400a449d  lea     rcx, [rsp+180h+var_150]
0x1400a44a2  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x1400a44a7  lea     rcx, [rsp+180h+var_110]; this
0x1400a44ac  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x1400a44b1  movzx   eax, al
0x1400a44b4  xor     eax, 1
0x1400a44b7  add     eax, 800h
0x1400a44bc  cmp     [rsp+180h+var_13C], eax
0x1400a44c0  jnb     short loc_1400A44E1
0x1400a44c2  mov     rcx, [rbp+88h]; this
0x1400a44c9  mov     r9d, 80048007h; char *
0x1400a44cf  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400a44d6  mov     edx, 115h; void *
0x1400a44db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a44e1  lea     rcx, [rsp+180h+var_110+8]
0x1400a44e6  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x1400a44eb  mov     r14, [rbp+80h+var_C8]
0x1400a44ef  cmp     [rbp+80h+var_B0], 40h ; '@'
0x1400a44f3  jb      short loc_1400A4514
0x1400a44f5  mov     rcx, [rbp+88h]; this
0x1400a44fc  mov     r9d, 8007000Dh; char *
0x1400a4502  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400a4509  mov     edx, 11Fh; void *
0x1400a450e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a4514  mov     eax, [rsp+180h+var_13C]
0x1400a4518  mov     ecx, 901h
0x1400a451d  cmp     eax, ecx
0x1400a451f  jnb     short loc_1400A452B
0x1400a4521  mov     ecx, 0FFFFFFF8h
0x1400a4526  jmp     loc_1400A45B5
0x1400a452b  jnz     short loc_1400A45AB
0x1400a452d  xorps   xmm0, xmm0
0x1400a4530  movups  [rsp+180h+var_110], xmm0
0x1400a4535  lea     rcx, [rsp+180h+var_150]
0x1400a453a  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x1400a453f  nop
0x1400a4540  mov     rcx, [rax]
0x1400a4543  mov     qword ptr [rax], 0
0x1400a454a  mov     qword ptr [rbp+80h+var_F8], rcx
0x1400a454e  lea     r9, [rbp+80h+var_F8]
0x1400a4552  lea     rcx, [rsp+180h+var_110]
0x1400a4557  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x1400a455c  nop
0x1400a455d  lea     rcx, [rbp+80h+var_F8]
0x1400a4561  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x1400a4566  nop
0x1400a4567  lea     rcx, [rsp+180h+var_150]
0x1400a456c  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x1400a4571  lea     rcx, [rsp+180h+var_110]; this
0x1400a4576  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x1400a457b  mov     bl, al
0x1400a457d  lea     rcx, [rsp+180h+var_110+8]
0x1400a4582  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x1400a4587  neg     bl
0x1400a4589  sbb     rax, rax
0x1400a458c  mov     rcx, 0FF00000008h
0x1400a4596  and     rax, rcx
0x1400a4599  mov     ecx, 0FFFFFFF8h
0x1400a459e  add     rcx, rax
0x1400a45a1  mov     r14, [rbp+80h+var_C8]
0x1400a45a5  mov     eax, [rsp+180h+var_13C]
0x1400a45a9  jmp     short loc_1400A45B5
0x1400a45ab  mov     rcx, 10000000000h
0x1400a45b5  cmp     r14, rcx
0x1400a45b8  jbe     short loc_1400A45D9
0x1400a45ba  mov     rcx, [rbp+88h]; this
0x1400a45c1  mov     r9d, 8007000Dh; char *
0x1400a45c7  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400a45ce  mov     edx, 13Ch; void *
0x1400a45d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a45d9  lea     rdx, ?MEMORY_BLOCK_PAGE_COUNT_VALID_FORMAT_V2@@3QBGB; "RamMemoryBlockPageCountValid%d"
0x1400a45e0  lea     rcx, ?MEMORY_BLOCK_PAGE_COUNT_VALID_FORMAT@@3QBGB; "RamMemoryBlockPageCountValid/%d/"
0x1400a45e7  cmp     eax, edi
0x1400a45e9  cmovb   rdx, rcx
0x1400a45ed  mov     r8d, r12d
0x1400a45f0  lea     rcx, [rsp+180h+var_130]
0x1400a45f5  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x1400a45fa  mov     rax, [rsi]
0x1400a45fd  lea     rdx, [rsp+180h+var_130]
0x1400a4602  cmp     qword ptr [rsp+180h+var_120+8], 7
0x1400a4608  cmova   rdx, qword ptr [rsp+180h+var_130]
0x1400a460e  lea     r8, [rbp+80h+var_100]
0x1400a4612  mov     rcx, rsi
0x1400a4615  mov     rax, [rax+50h]
0x1400a4619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a461e  mov     ecx, eax; int
0x1400a4620  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400a4625  test    eax, eax
0x1400a4627  jnz     short loc_1400A4632
0x1400a4629  mov     rax, r14
0x1400a462c  mov     [rbp+80h+var_A0], rax
0x1400a4630  jmp     short loc_1400A467A
0x1400a4632  mov     rax, [rsi]
0x1400a4635  lea     rdx, [rsp+180h+var_130]
0x1400a463a  cmp     qword ptr [rsp+180h+var_120+8], 7
0x1400a4640  cmova   rdx, qword ptr [rsp+180h+var_130]
0x1400a4646  lea     r8, [rbp+80h+var_A0]
0x1400a464a  mov     rcx, rsi
0x1400a464d  mov     rax, [rax+78h]
0x1400a4651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4656  mov     rcx, [rbp+88h]; this
0x1400a465d  test    eax, eax
0x1400a465f  jns     short loc_1400A4676
0x1400a4661  mov     r9d, eax; char *
0x1400a4664  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400a466b  mov     edx, 155h; void *
0x1400a4670  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a4676  mov     rax, [rbp+80h+var_A0]
0x1400a467a  test    r14, r14
0x1400a467d  jz      loc_1400A4AC0
0x1400a4683  cmp     rax, r14
0x1400a4686  ja      loc_1400A4AC0
0x1400a468c  test    rax, rax
0x1400a468f  jz      loc_1400A4AC0
0x1400a4695  cmp     rax, r14
0x1400a4698  jz      short loc_1400A46BF
0x1400a469a  test    byte ptr [rbp+80h+var_CC], 1
0x1400a469e  jnz     short loc_1400A46BF
0x1400a46a0  mov     rcx, [rbp+88h]; this
0x1400a46a7  mov     r9d, 8007000Dh; char *
0x1400a46ad  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x1400a46b4  mov     edx, 169h; void *
0x1400a46b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a46bf  lea     rdx, ?MEMORY_BLOCK_BACKING_BITMAP_FORMAT_V2@@3QBGB; "RamMemoryBlockBackingBitmap%d"
0x1400a46c6  lea     rax, ?MEMORY_BLOCK_BACKING_BITMAP_FORMAT@@3QBGB; "RamMemoryBlockBackingBitmap/%d/"
0x1400a46cd  cmp     [rsp+180h+var_13C], edi
0x1400a46d1  cmovb   rdx, rax
0x1400a46d5  mov     r8d, r12d
0x1400a46d8  lea     rcx, [rsp+180h+var_130]
0x1400a46dd  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x1400a46e2  mov     [rbp+80h+var_FC], 0
0x1400a46e9  mov     rax, [rsi]
0x1400a46ec  lea     rdx, [rsp+180h+var_130]
0x1400a46f1  cmp     qword ptr [rsp+180h+var_120+8], 7
0x1400a46f7  cmova   rdx, qword ptr [rsp+180h+var_130]
0x1400a46fd  lea     r8, [rbp+80h+var_FC]
0x1400a4701  mov     rcx, rsi
0x1400a4704  mov     rax, [rax+50h]
0x1400a4708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a470d  mov     ecx, eax; int
0x1400a470f  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400a4714  test    eax, eax
0x1400a4716  jz      loc_1400A488E
0x1400a471c  mov     eax, 4
0x1400a4721  lea     r9d, [rax+4]
0x1400a4725  cmp     [rsp+180h+var_13C], 900h
0x1400a472d  cmovbe  r9d, eax
0x1400a4731  xor     edx, edx
0x1400a4733  mov     r10d, [rbp+80h+var_FC]
0x1400a4737  mov     eax, r10d
0x1400a473a  div     r9d
0x1400a473d  test    edx, edx
0x1400a473f  jnz     loc_1400A492A
  ... truncated ...
```
