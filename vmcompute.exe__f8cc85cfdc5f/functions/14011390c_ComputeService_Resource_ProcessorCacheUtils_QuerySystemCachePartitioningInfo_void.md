# ComputeService::Resource::ProcessorCacheUtils::QuerySystemCachePartitioningInfo(void)

- ea: `0x14011390c`
- end: `0x140113b49`
- name: `?QuerySystemCachePartitioningInfo@ProcessorCacheUtils@Resource@ComputeService@@YA?AUCacheAllocationSystemInfo@ProcessorCache@Resources@Schema@@XZ`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140129708`

## callees

- `0x14001bce0`
- `0x14002f8dc`
- `0x14004bdb4`
- `0x140080180`
- `0x1400a02f8`
- `0x1400c40e0`
- `0x14011390c`
- `0x140113b50`
- `0x1401332f0`
- `0x140134048`

## import_xrefs

- `vid!VidGetSystemInformation` at `0x1401139d1`
- `vid!VidGetSystemInformation` at `0x140113a50`
- `vid!VidGetSystemInformation` at `0x1401139d1`
- `vid!VidGetSystemInformation` at `0x140113a50`
- `vid!VidGetPartitionProperty` at `0x140113ace`
- `vid!VidGetPartitionProperty` at `0x140113ace`
- `vid!VidOpenStatisticsHandle` at `0x14011396a`
- `vid!VidOpenStatisticsHandle` at `0x14011396a`

## string_xrefs

- `0x1401139e8`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`
- `0x140113a67`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`
- `0x140113a8f`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`
- `0x140113ae5`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ComputeService::Resource::ProcessorCacheUtils::QuerySystemCachePartitioningInfo(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  const char *v4; // r9
  const char *v5; // r9
  __int64 i; // rbx
  const char *v7; // r9
  __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  char v11; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v12; // [rsp+59h] [rbp-A7h]
  char v13; // [rsp+5Bh] [rbp-A5h]
  __int64 v14; // [rsp+5Ch] [rbp-A4h]
  int v15; // [rsp+64h] [rbp-9Ch]
  _BYTE v16[24]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h]
  __int128 v18; // [rsp+88h] [rbp-78h]
  __int128 v19; // [rsp+98h] [rbp-68h]
  __int128 v20; // [rsp+A8h] [rbp-58h] BYREF
  int v21[260]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v16);
  v17 = 0;
  v3 = VidOpenStatisticsHandle(v2);
  v9 = v3;
  v18 = 0;
  v19 = 0;
  memset_0(v21, 0, 0x408u);
  v20 = 0;
  v10 = 0;
  if ( !(unsigned int)VidGetSystemInformation(v3, 3, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
      v4);
  v11 = v18 & 1;
  v14 = *(_QWORD *)((char *)&v18 + 4);
  v15 = HIDWORD(v18);
  if ( (v18 & 1) != 0 )
  {
    LODWORD(v20) = 0;
    if ( !(unsigned int)VidGetSystemInformation(v3, 4, &v20) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
        v5);
    if ( v21[0] != v15 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
        (const char *)0x8000FFFFLL,
        (int)v21);
    for ( i = 0; (unsigned int)i < v21[0]; i = (unsigned int)(i + 1) )
      std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64 const &>(v16, &v21[2 * i + 2]);
    if ( !(unsigned int)VidGetPartitionProperty(-1, 327694, &v10) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
        v7);
    LODWORD(v17) = v10;
  }
  Schema::Resources::ProcessorCache::CacheAllocationSystemInfo::CacheAllocationSystemInfo(a1, &v11);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(&v9);
  std::vector<Schema::Resources::Processor::NumaNodeProcessor>::_Tidy(v16);
  return a1;
}

```

## disassembly

```asm
0x14011390c  mov     [rsp-8+arg_8], rbx
0x140113911  mov     [rsp-8+arg_10], rdi
0x140113916  push    rbp
0x140113917  lea     rbp, [rsp-3E0h]
0x14011391f  sub     rsp, 4E0h
0x140113926  mov     rax, cs:__security_cookie
0x14011392d  xor     rax, rsp
0x140113930  mov     [rbp+3E0h+var_10], rax
0x140113937  mov     rdi, rcx
0x14011393a  mov     [rsp+4E0h+var_4A0], rcx
0x14011393f  mov     [rsp+4E0h+var_488], 0
0x140113944  xor     eax, eax
0x140113946  mov     [rsp+4E0h+var_487], ax
0x14011394b  mov     [rsp+4E0h+var_485], al
0x14011394f  mov     [rsp+4E0h+var_484], rax
0x140113954  mov     [rsp+4E0h+var_47C], eax
0x140113958  lea     rcx, [rsp+4E0h+var_478]
0x14011395d  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x140113962  mov     [rbp+3E0h+var_460], 0
0x14011396a  call    cs:__imp_VidOpenStatisticsHandle
0x140113971  nop     dword ptr [rax+rax+00h]
0x140113976  mov     rbx, rax
0x140113979  mov     [rsp+4E0h+var_4A0], rax
0x14011397e  xorps   xmm0, xmm0
0x140113981  movups  [rbp+3E0h+var_458], xmm0
0x140113985  movups  [rbp+3E0h+var_448], xmm0
0x140113989  xor     edx, edx; Val
0x14011398b  mov     r8d, 408h; Size
0x140113991  lea     rcx, [rbp+3E0h+var_420]; void *
0x140113995  call    memset_0
0x14011399a  xorps   xmm0, xmm0
0x14011399d  movups  [rbp+3E0h+var_438], xmm0
0x1401139a1  mov     [rsp+4E0h+var_490], 0
0x1401139aa  mov     [rsp+4E0h+var_4B0], 0
0x1401139b3  mov     [rsp+4E0h+var_4B8], 20h ; ' '
0x1401139bb  lea     rax, [rbp+3E0h+var_458]
0x1401139bf  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x1401139c4  xor     r9d, r9d
0x1401139c7  xor     r8d, r8d
0x1401139ca  lea     edx, [r9+3]
0x1401139ce  mov     rcx, rbx
0x1401139d1  call    cs:__imp_VidGetSystemInformation
0x1401139d8  nop     dword ptr [rax+rax+00h]
0x1401139dd  mov     rcx, [rbp+3E8h]; this
0x1401139e4  test    eax, eax
0x1401139e6  jnz     short loc_1401139FA
0x1401139e8  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x1401139ef  mov     edx, 0DFh; void *
0x1401139f4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401139fa  mov     al, byte ptr [rbp+3E0h+var_458]
0x1401139fd  and     al, 1
0x1401139ff  mov     [rsp+4E0h+var_488], al
0x140113a03  mov     eax, dword ptr [rbp+3E0h+var_458+8]
0x140113a06  mov     dword ptr [rsp+4E0h+var_484+4], eax
0x140113a0a  mov     eax, dword ptr [rbp+3E0h+var_458+4]
0x140113a0d  mov     dword ptr [rsp+4E0h+var_484], eax
0x140113a11  mov     eax, dword ptr [rbp+3E0h+var_458+0Ch]
0x140113a14  mov     [rsp+4E0h+var_47C], eax
0x140113a18  jz      loc_140113AFE
0x140113a1e  mov     dword ptr [rbp+3E0h+var_438], 0
0x140113a25  mov     [rsp+4E0h+var_4B0], 0
0x140113a2e  mov     [rsp+4E0h+var_4B8], 408h
0x140113a36  lea     rax, [rbp+3E0h+var_420]
0x140113a3a  mov     qword ptr [rsp+4E0h+var_4C0], rax; int
0x140113a3f  mov     r9d, 10h
0x140113a45  lea     r8, [rbp+3E0h+var_438]
0x140113a49  lea     edx, [r9-0Ch]
0x140113a4d  mov     rcx, rbx
0x140113a50  call    cs:__imp_VidGetSystemInformation
0x140113a57  nop     dword ptr [rax+rax+00h]
0x140113a5c  mov     rcx, [rbp+3E8h]; this
0x140113a63  test    eax, eax
0x140113a65  jnz     short loc_140113A79
0x140113a67  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x140113a6e  mov     edx, 0F2h; void *
0x140113a73  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140113a79  mov     eax, [rbp+3E0h+var_420]
0x140113a7c  cmp     eax, [rsp+4E0h+var_47C]
0x140113a80  jz      short loc_140113AA1
0x140113a82  mov     rcx, [rbp+3E8h]; this
0x140113a89  mov     r9d, 8000FFFFh; char *
0x140113a8f  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x140113a96  mov     edx, 0F6h; void *
0x140113a9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140113aa1  xor     ebx, ebx
0x140113aa3  test    eax, eax
0x140113aa5  jz      short loc_140113AC0
0x140113aa7  lea     rdx, [rbp+3E0h+var_418]
0x140113aab  lea     rdx, [rdx+rbx*8]
0x140113aaf  lea     rcx, [rsp+4E0h+var_478]
0x140113ab4  call    ??$_Emplace_one_at_back@AEB_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAAEA_KAEB_K@Z; std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64 const &>(unsigned __int64 const &)
0x140113ab9  inc     ebx
0x140113abb  cmp     ebx, [rbp+3E0h+var_420]
0x140113abe  jb      short loc_140113AA7
0x140113ac0  lea     r8, [rsp+4E0h+var_490]
0x140113ac5  mov     edx, 5000Eh
0x140113aca  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140113ace  call    cs:__imp_VidGetPartitionProperty
0x140113ad5  nop     dword ptr [rax+rax+00h]
0x140113ada  mov     rcx, [rbp+3E8h]; this
0x140113ae1  test    eax, eax
0x140113ae3  jnz     short loc_140113AF7
0x140113ae5  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x140113aec  mov     edx, 101h; void *
0x140113af1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140113af7  mov     ecx, dword ptr [rsp+4E0h+var_490]
0x140113afb  mov     dword ptr [rbp+3E0h+var_460], ecx
0x140113afe  lea     rdx, [rsp+4E0h+var_488]
0x140113b03  mov     rcx, rdi
0x140113b06  call    ??0CacheAllocationSystemInfo@ProcessorCache@Resources@Schema@@QEAA@$$QEAU0123@@Z; Schema::Resources::ProcessorCache::CacheAllocationSystemInfo::CacheAllocationSystemInfo(Schema::Resources::ProcessorCache::CacheAllocationSystemInfo &&)
0x140113b0b  nop
0x140113b0c  lea     rcx, [rsp+4E0h+var_4A0]
0x140113b11  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x140113b16  nop
0x140113b17  lea     rcx, [rsp+4E0h+var_478]
0x140113b1c  call    ?_Tidy@?$vector@UNumaNodeProcessor@Processor@Resources@Schema@@V?$allocator@UNumaNodeProcessor@Processor@Resources@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Resources::Processor::NumaNodeProcessor>::_Tidy(void)
0x140113b21  mov     rax, rdi
0x140113b24  mov     rcx, [rbp+3E0h+var_10]
0x140113b2b  xor     rcx, rsp; StackCookie
0x140113b2e  call    __security_check_cookie
0x140113b33  lea     r11, [rsp+4E0h+var_s0]
0x140113b3b  mov     rbx, [r11+18h]
0x140113b3f  mov     rdi, [r11+20h]
0x140113b43  mov     rsp, r11
0x140113b46  pop     rbp
0x140113b47  retn
```
