# ComputeService::Management::ServiceCapabilities::Helpers::GetProcessorCapabilities(void)

- ea: `0x14011b428`
- end: `0x14011b888`
- name: `?GetProcessorCapabilities@Helpers@ServiceCapabilities@Management@ComputeService@@YA?AUProcessorCapabilitiesInfo@Service@Responses@Schema@@XZ`
- size: `1120`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400b2160`

## callees

- `0x140080180`
- `0x1400a02f8`
- `0x1400c40e0`
- `0x140108624`
- `0x14011b428`
- `0x14011b890`
- `0x14011bb28`
- `0x1401332f0`
- `0x140134048`
- `0x1402a0df0`

## import_xrefs

- `vid!VidGetPartitionPropertyEx` at `0x14011b5c7`
- `vid!VidGetPartitionPropertyEx` at `0x14011b5fc`
- `vid!VidGetPartitionPropertyEx` at `0x14011b5c7`
- `vid!VidGetPartitionPropertyEx` at `0x14011b5fc`
- `vid!VidGetSystemInformation` at `0x14011b796`
- `vid!VidGetSystemInformation` at `0x14011b7f6`
- `vid!VidGetSystemInformation` at `0x14011b796`
- `vid!VidGetSystemInformation` at `0x14011b7f6`
- `vid!VidGetPartitionProperty` at `0x14011b492`
- `vid!VidGetPartitionProperty` at `0x14011b4c7`
- `vid!VidGetPartitionProperty` at `0x14011b4fc`
- `vid!VidGetPartitionProperty` at `0x14011b531`
- `vid!VidGetPartitionProperty` at `0x14011b566`
- `vid!VidGetPartitionProperty` at `0x14011b626`
- `vid!VidGetPartitionProperty` at `0x14011b662`
- `vid!VidGetPartitionProperty` at `0x14011b6f3`
- `vid!VidGetPartitionProperty` at `0x14011b492`
- `vid!VidGetPartitionProperty` at `0x14011b4c7`
- `vid!VidGetPartitionProperty` at `0x14011b4fc`
- `vid!VidGetPartitionProperty` at `0x14011b531`
- `vid!VidGetPartitionProperty` at `0x14011b566`
- `vid!VidGetPartitionProperty` at `0x14011b626`
- `vid!VidGetPartitionProperty` at `0x14011b662`
- `vid!VidGetPartitionProperty` at `0x14011b6f3`
- `vid!VidOpenStatisticsHandle` at `0x14011b71c`
- `vid!VidOpenStatisticsHandle` at `0x14011b71c`

## string_xrefs

- `0x14011b4a9`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b4de`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b513`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b548`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b57d`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b63d`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b672`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b70a`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b747`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b7ad`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b80d`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`
- `0x14011b837`: `onecore\vm\compute\management\shared\compute\capabilityhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ComputeService::Management::ServiceCapabilities::Helpers::GetProcessorCapabilities(__int64 a1)
{
  const char *v2; // r9
  const char *v3; // r9
  const char *v4; // r9
  const char *v5; // r9
  __int64 v6; // rdx
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  __int64 v11; // rbx
  const char *v12; // r9
  const char *v13; // r9
  const char *v14; // r9
  _QWORD v16[3]; // [rsp+48h] [rbp-B8h] BYREF
  __m256i v17; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v18; // [rsp+80h] [rbp-80h]
  __int128 v19; // [rsp+90h] [rbp-70h]
  __int128 v20; // [rsp+A0h] [rbp-60h]
  __int128 v21; // [rsp+B0h] [rbp-50h]
  __int64 v22; // [rsp+C0h] [rbp-40h]
  int v23; // [rsp+D0h] [rbp-30h] BYREF
  int v24; // [rsp+D4h] [rbp-2Ch]
  int v25; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-18h]
  __m256i v28; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v29; // [rsp+110h] [rbp+10h] BYREF
  __int128 v30; // [rsp+120h] [rbp+20h] BYREF
  __int128 v31; // [rsp+130h] [rbp+30h]
  __int128 v32; // [rsp+140h] [rbp+40h] BYREF
  __int64 v33; // [rsp+150h] [rbp+50h] BYREF
  __int16 v34; // [rsp+160h] [rbp+60h] BYREF
  __int64 v35; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1168h] [rbp+1068h]

  v16[1] = a1;
  memset_0(&v28, 0, 0x68u);
  GetHostProcessorFeaturesNBank((unsigned __int64 (*)[3])&v28);
  if ( !(unsigned int)VidGetPartitionProperty(-1, 393219, &v29) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v2);
  if ( !(unsigned int)VidGetPartitionProperty(-1, 393218, &v28.m256i_u64[3]) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v3);
  if ( !(unsigned int)VidGetPartitionProperty(-1, 327696, (char *)&v29 + 8) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v4);
  if ( !(unsigned int)VidGetPartitionProperty(-1, 327697, &v30) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v5);
  if ( !(unsigned int)VidGetPartitionProperty(-1, 65537, (char *)&v30 + 8) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v7);
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl'::`2'::impl,
    v6);
  memset_0(&v34, 0, 0xFE8u);
  *(_QWORD *)&v31 = 0;
  if ( (unsigned int)VidGetPartitionPropertyEx(-1, 589833, 0, &v34, 4072) && v34 )
    *(_QWORD *)&v31 = v35;
  *((_QWORD *)&v31 + 1) = 0;
  if ( (unsigned int)VidGetPartitionPropertyEx(-1, 589831, 0, &v34, 4072) && v34 )
    *((_QWORD *)&v31 + 1) = v35;
  if ( !(unsigned int)VidGetPartitionProperty(-1, 393222, &v32) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v8);
  if ( !(unsigned int)VidGetPartitionProperty(-1, 393220, &v33) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v9);
  *((_QWORD *)&v32 + 1) = 0x7FFF;
  v17 = v28;
  v18 = v29;
  v19 = v30;
  v20 = v31;
  v21 = v32;
  v22 = v33;
  ComputeService::Resource::ProcessorCapabilitiesUtils::TranslateProcessorCapabilities(a1, &v17);
  v24 = 0;
  v26 = 0;
  if ( !(unsigned int)VidGetPartitionProperty(-1, 393216, &v26) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v10);
  v11 = VidOpenStatisticsHandle(retaddr);
  v16[0] = v11;
  if ( ((v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v12);
  if ( v26 == 1 )
  {
    v27 = 0;
    v25 = 13;
    if ( !(unsigned int)VidGetSystemInformation(v11, 10, &v25) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x16C,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
        v13);
    if ( v27 )
      *(_BYTE *)(a1 + 81) = 1;
  }
  LOWORD(v23) = 0;
  if ( !(unsigned int)VidGetSystemInformation(v11, 2, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      v14);
  if ( v24 != 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\capabilityhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v23);
  if ( BYTE1(v23) )
    *(_BYTE *)(a1 + 80) = 1;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(v16);
  return a1;
}

```

## disassembly

```asm
0x14011b428  mov     [rsp-8+arg_8], rbx
0x14011b42d  mov     [rsp-8+arg_10], rsi
0x14011b432  push    rbp
0x14011b433  push    rdi
0x14011b434  push    r14
0x14011b436  lea     rbp, [rsp-1050h]
0x14011b43e  mov     eax, 1150h
0x14011b443  call    _alloca_probe
0x14011b448  sub     rsp, rax
0x14011b44b  mov     rax, cs:__security_cookie
0x14011b452  xor     rax, rsp
0x14011b455  mov     [rbp+1060h+var_18], rax
0x14011b45c  mov     rdi, rcx
0x14011b45f  mov     [rsp+1160h+var_1110], rcx
0x14011b464  xor     esi, esi
0x14011b466  mov     [rsp+1160h+var_1120], esi
0x14011b46a  xor     edx, edx; Val
0x14011b46c  lea     r8d, [rsi+68h]; Size
0x14011b470  lea     rcx, [rbp+1060h+var_1070]; void *
0x14011b474  call    memset_0
0x14011b479  lea     rcx, [rbp+1060h+var_1070]; unsigned __int64 (*)[3]
0x14011b47d  call    ?GetHostProcessorFeaturesNBank@@YAXAEAY02_K@Z; GetHostProcessorFeaturesNBank(unsigned __int64 (&)[3])
0x14011b482  lea     r8, [rbp+1060h+var_1050]
0x14011b486  mov     edx, 60003h
0x14011b48b  or      r14, 0FFFFFFFFFFFFFFFFh
0x14011b48f  mov     rcx, r14
0x14011b492  call    cs:__imp_VidGetPartitionProperty
0x14011b499  nop     dword ptr [rax+rax+00h]
0x14011b49e  mov     rcx, [rbp+1068h]; this
0x14011b4a5  test    eax, eax
0x14011b4a7  jnz     short loc_14011B4BB
0x14011b4a9  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b4b0  mov     edx, 106h; void *
0x14011b4b5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b4bb  lea     r8, [rbp+1060h+var_1058]
0x14011b4bf  mov     edx, 60002h
0x14011b4c4  mov     rcx, r14
0x14011b4c7  call    cs:__imp_VidGetPartitionProperty
0x14011b4ce  nop     dword ptr [rax+rax+00h]
0x14011b4d3  mov     rcx, [rbp+1068h]; this
0x14011b4da  test    eax, eax
0x14011b4dc  jnz     short loc_14011B4F0
0x14011b4de  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b4e5  mov     edx, 10Dh; void *
0x14011b4ea  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b4f0  lea     r8, [rbp+1060h+var_1050+8]
0x14011b4f4  mov     edx, 50010h
0x14011b4f9  mov     rcx, r14
0x14011b4fc  call    cs:__imp_VidGetPartitionProperty
0x14011b503  nop     dword ptr [rax+rax+00h]
0x14011b508  mov     rcx, [rbp+1068h]; this
0x14011b50f  test    eax, eax
0x14011b511  jnz     short loc_14011B525
0x14011b513  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b51a  mov     edx, 112h; void *
0x14011b51f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b525  lea     r8, [rbp+1060h+var_1040]
0x14011b529  mov     edx, 50011h
0x14011b52e  mov     rcx, r14
0x14011b531  call    cs:__imp_VidGetPartitionProperty
0x14011b538  nop     dword ptr [rax+rax+00h]
0x14011b53d  mov     rcx, [rbp+1068h]; this
0x14011b544  test    eax, eax
0x14011b546  jnz     short loc_14011B55A
0x14011b548  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b54f  mov     edx, 117h; void *
0x14011b554  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b55a  lea     r8, [rbp+1060h+var_1040+8]
0x14011b55e  mov     edx, 10001h
0x14011b563  mov     rcx, r14
0x14011b566  call    cs:__imp_VidGetPartitionProperty
0x14011b56d  nop     dword ptr [rax+rax+00h]
0x14011b572  mov     rcx, [rbp+1068h]; this
0x14011b579  test    eax, eax
0x14011b57b  jnz     short loc_14011B58F
0x14011b57d  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b584  mov     edx, 11Eh; void *
0x14011b589  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b58f  mov     dl, 1
0x14011b591  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures> `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl(void)'::`2'::impl
0x14011b598  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14011b59d  mov     ebx, 0FE8h
0x14011b5a2  mov     r8d, ebx; Size
0x14011b5a5  xor     edx, edx; Val
0x14011b5a7  lea     rcx, [rbp+1060h+var_1000]; void *
0x14011b5ab  call    memset_0
0x14011b5b0  mov     qword ptr [rbp+1060h+var_1030], rsi
0x14011b5b4  mov     [rsp+1160h+var_1140], ebx
0x14011b5b8  lea     r9, [rbp+1060h+var_1000]
0x14011b5bc  xor     r8d, r8d
0x14011b5bf  mov     edx, 90009h
0x14011b5c4  mov     rcx, r14
0x14011b5c7  call    cs:__imp_VidGetPartitionPropertyEx
0x14011b5ce  nop     dword ptr [rax+rax+00h]
0x14011b5d3  test    eax, eax
0x14011b5d5  jz      short loc_14011B5E5
0x14011b5d7  cmp     [rbp+1060h+var_1000], si
0x14011b5db  jz      short loc_14011B5E5
0x14011b5dd  mov     rax, [rbp+1060h+var_FF8]
0x14011b5e1  mov     qword ptr [rbp+1060h+var_1030], rax
0x14011b5e5  mov     qword ptr [rbp+1060h+var_1030+8], rsi
0x14011b5e9  mov     [rsp+1160h+var_1140], ebx
0x14011b5ed  lea     r9, [rbp+1060h+var_1000]
0x14011b5f1  xor     r8d, r8d
0x14011b5f4  mov     edx, 90007h
0x14011b5f9  mov     rcx, r14
0x14011b5fc  call    cs:__imp_VidGetPartitionPropertyEx
0x14011b603  nop     dword ptr [rax+rax+00h]
0x14011b608  test    eax, eax
0x14011b60a  jz      short loc_14011B61A
0x14011b60c  cmp     [rbp+1060h+var_1000], si
0x14011b610  jz      short loc_14011B61A
0x14011b612  mov     rax, [rbp+1060h+var_FF8]
0x14011b616  mov     qword ptr [rbp+1060h+var_1030+8], rax
0x14011b61a  lea     r8, [rbp+1060h+var_1020]
0x14011b61e  mov     edx, 60006h
0x14011b623  mov     rcx, r14
0x14011b626  call    cs:__imp_VidGetPartitionProperty
0x14011b62d  nop     dword ptr [rax+rax+00h]
0x14011b632  mov     rcx, [rbp+1068h]; this
0x14011b639  test    eax, eax
0x14011b63b  jnz     short loc_14011B64F
0x14011b63d  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b644  mov     edx, 13Fh; void *
0x14011b649  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b64f  mov     rbx, [rbp+1068h]
0x14011b656  lea     r8, [rbp+1060h+var_1010]
0x14011b65a  mov     edx, 60004h
0x14011b65f  mov     rcx, r14
0x14011b662  call    cs:__imp_VidGetPartitionProperty
0x14011b669  nop     dword ptr [rax+rax+00h]
0x14011b66e  test    eax, eax
0x14011b670  jnz     short loc_14011B687
0x14011b672  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b679  mov     edx, 144h; void *
0x14011b67e  mov     rcx, rbx; this
0x14011b681  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b687  mov     qword ptr [rbp+1060h+var_1020+8], 7FFFh
0x14011b68f  movaps  xmm0, xmmword ptr [rbp+1060h+var_1070]
0x14011b693  movaps  [rsp+1160h+var_1100], xmm0
0x14011b698  movaps  xmm1, xmmword ptr [rbp+0]
0x14011b69c  movaps  [rsp+1160h+var_10F0], xmm1
0x14011b6a1  movaps  xmm0, [rbp+1060h+var_1050]
0x14011b6a5  movaps  [rbp+1060h+var_10E0], xmm0
0x14011b6a9  movaps  xmm1, [rbp+1060h+var_1040]
0x14011b6ad  movaps  [rbp+1060h+var_10D0], xmm1
0x14011b6b1  movaps  xmm0, [rbp+1060h+var_1030]
0x14011b6b5  movaps  [rbp+1060h+var_10C0], xmm0
0x14011b6b9  movaps  xmm1, [rbp+1060h+var_1020]
0x14011b6bd  movaps  [rbp+1060h+var_10B0], xmm1
0x14011b6c1  movsd   xmm0, [rbp+1060h+var_1010]
0x14011b6c6  movsd   [rbp+1060h+var_10A0], xmm0
0x14011b6cb  lea     rdx, [rsp+1160h+var_1100]
0x14011b6d0  mov     rcx, rdi
0x14011b6d3  call    ?TranslateProcessorCapabilities@ProcessorCapabilitiesUtils@Resource@ComputeService@@YA?AUProcessorCapabilitiesInfo@Service@Responses@Schema@@U_PROCESSOR_FEATURES@@@Z; ComputeService::Resource::ProcessorCapabilitiesUtils::TranslateProcessorCapabilities(_PROCESSOR_FEATURES)
0x14011b6d8  mov     [rsp+1160h+var_1120], 1
0x14011b6e0  mov     [rbp+1060h+var_108C], esi
0x14011b6e3  mov     [rbp+1060h+var_1080], rsi
0x14011b6e7  lea     r8, [rbp+1060h+var_1080]
0x14011b6eb  mov     edx, 60000h
0x14011b6f0  mov     rcx, r14
0x14011b6f3  call    cs:__imp_VidGetPartitionProperty
0x14011b6fa  nop     dword ptr [rax+rax+00h]
0x14011b6ff  mov     rcx, [rbp+1068h]; this
0x14011b706  test    eax, eax
0x14011b708  jnz     short loc_14011B71C
0x14011b70a  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b711  mov     edx, 15Ah; void *
0x14011b716  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b71c  call    cs:__imp_VidOpenStatisticsHandle
0x14011b723  nop     dword ptr [rax+rax+00h]
0x14011b728  mov     rbx, rax
0x14011b72b  mov     [rsp+1160h+var_1118], rax
0x14011b730  inc     rax
0x14011b733  test    rax, 0FFFFFFFFFFFFFFFEh
0x14011b739  setz    al
0x14011b73c  mov     rcx, [rbp+1068h]; this
0x14011b743  test    al, al
0x14011b745  jz      short loc_14011B759
0x14011b747  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b74e  mov     edx, 15Dh; void *
0x14011b753  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b759  cmp     [rbp+1060h+var_1080], 1
0x14011b75e  jnz     short loc_14011B7C9
0x14011b760  mov     [rbp+1060h+var_1078], rsi
0x14011b764  mov     [rbp+1060h+var_1088], 0Dh
0x14011b76b  lea     rax, [rbp+1060h+var_108C]
0x14011b76f  mov     [rsp+1160h+var_1130], rax
0x14011b774  mov     [rsp+1160h+var_1138], 8
0x14011b77c  lea     rax, [rbp+1060h+var_1078]
0x14011b780  mov     qword ptr [rsp+1160h+var_1140], rax
0x14011b785  mov     r9d, 4
0x14011b78b  lea     r8, [rbp+1060h+var_1088]
0x14011b78f  lea     edx, [r9+6]
0x14011b793  mov     rcx, rbx
0x14011b796  call    cs:__imp_VidGetSystemInformation
0x14011b79d  nop     dword ptr [rax+rax+00h]
0x14011b7a2  mov     rcx, [rbp+1068h]; this
0x14011b7a9  test    eax, eax
0x14011b7ab  jnz     short loc_14011B7BF
0x14011b7ad  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b7b4  mov     edx, 16Ch; void *
0x14011b7b9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b7bf  cmp     [rbp+1060h+var_1078], rsi
0x14011b7c3  jbe     short loc_14011B7C9
0x14011b7c5  mov     byte ptr [rdi+51h], 1
0x14011b7c9  mov     word ptr [rbp+1060h+var_1090], si
0x14011b7cd  lea     rax, [rbp+1060h+var_108C]
0x14011b7d1  mov     [rsp+1160h+var_1130], rax
0x14011b7d6  mov     r14d, 2
0x14011b7dc  mov     [rsp+1160h+var_1138], r14d
0x14011b7e1  lea     rax, [rbp+1060h+var_1090]
0x14011b7e5  mov     qword ptr [rsp+1160h+var_1140], rax; int
0x14011b7ea  xor     r9d, r9d
0x14011b7ed  xor     r8d, r8d
0x14011b7f0  mov     edx, r14d
0x14011b7f3  mov     rcx, rbx
0x14011b7f6  call    cs:__imp_VidGetSystemInformation
0x14011b7fd  nop     dword ptr [rax+rax+00h]
0x14011b802  mov     rcx, [rbp+1068h]; this
0x14011b809  test    eax, eax
0x14011b80b  jnz     short loc_14011B81F
0x14011b80d  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b814  mov     edx, 17Dh; void *
0x14011b819  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011b81f  cmp     [rbp+1060h+var_108C], r14d
0x14011b823  setnz   al
0x14011b826  mov     rcx, [rbp+1068h]; this
0x14011b82d  test    al, al
0x14011b82f  jz      short loc_14011B849
0x14011b831  mov     r9d, 8000FFFFh; char *
0x14011b837  lea     r8, aOnecoreVmCompu_99; "onecore\\vm\\compute\\management\\share"...
0x14011b83e  mov     edx, 17Fh; void *
0x14011b843  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14011b849  cmp     byte ptr [rbp+1060h+var_1090+1], sil
0x14011b84d  jz      short loc_14011B853
0x14011b84f  mov     byte ptr [rdi+50h], 1
0x14011b853  lea     rcx, [rsp+1160h+var_1118]
0x14011b858  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x14011b85d  mov     rax, rdi
0x14011b860  mov     rcx, [rbp+1060h+var_18]
0x14011b867  xor     rcx, rsp; StackCookie
0x14011b86a  call    __security_check_cookie
0x14011b86f  lea     r11, [rsp+1160h+var_10]
0x14011b877  mov     rbx, [r11+28h]
0x14011b87b  mov     rsi, [r11+30h]
0x14011b87f  mov     rsp, r11
0x14011b882  pop     r14
0x14011b884  pop     rdi
0x14011b885  pop     rbp
0x14011b886  retn
```
