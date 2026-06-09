# ComputeService::Resource::ProcessorCacheUtils::QuerySystemMemoryBwAllocationInfo(void)

- ea: `0x14029231c`
- end: `0x140292525`
- name: `?QuerySystemMemoryBwAllocationInfo@ProcessorCacheUtils@Resource@ComputeService@@YA?AUMemoryBwAllocationSystemInfo@ProcessorCache@Resources@Schema@@XZ`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140129708`

## callees

- `0x14001bce0`
- `0x14002d818`
- `0x140080180`
- `0x1400a02f8`
- `0x1400c40e0`
- `0x1401332f0`
- `0x140134048`
- `0x14021d1b8`
- `0x140291f6c`
- `0x14029231c`

## import_xrefs

- `vid!VidGetSystemInformation` at `0x1402923c7`
- `vid!VidGetSystemInformation` at `0x14029244e`
- `vid!VidGetSystemInformation` at `0x1402923c7`
- `vid!VidGetSystemInformation` at `0x14029244e`
- `vid!VidOpenStatisticsHandle` at `0x14029236c`
- `vid!VidOpenStatisticsHandle` at `0x14029236c`

## string_xrefs

- `0x1402923de`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`
- `0x140292465`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`
- `0x14029248e`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ComputeService::Resource::ProcessorCacheUtils::QuerySystemMemoryBwAllocationInfo(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  const char *v4; // r9
  const char *v5; // r9
  __int64 i; // rbx
  int v7; // ecx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v14[8]; // [rsp+68h] [rbp-98h] BYREF
  _DWORD *v15; // [rsp+70h] [rbp-90h]
  _DWORD *v16; // [rsp+78h] [rbp-88h]
  __int128 v17; // [rsp+80h] [rbp-80h]
  __int128 v18; // [rsp+90h] [rbp-70h]
  __int128 v19; // [rsp+A0h] [rbp-60h] BYREF
  int v20[2]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v21[258]; // [rsp+B8h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v13 = 0u;
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v14);
  v3 = VidOpenStatisticsHandle(v2);
  v12 = v3;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  memset_0(v20, 0, 0x408u);
  if ( !(unsigned int)VidGetSystemInformation(v3, 3, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
      v4);
  LOBYTE(v13) = (v17 & 0x20) != 0;
  BYTE1(v13) = BYTE12(v18) & 1;
  *(_QWORD *)((char *)&v13 + 4) = *(_QWORD *)((char *)&v18 + 4);
  if ( (v17 & 0x20) != 0 )
  {
    LODWORD(v19) = 1;
    if ( !(unsigned int)VidGetSystemInformation(v3, 4, &v19) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
        v5);
    if ( v20[0] != DWORD1(v13) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x181,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
        (const char *)0x8000FFFFLL,
        (int)v20);
    for ( i = 0; (unsigned int)i < v20[0]; i = (unsigned int)(i + 1) )
    {
      v7 = v21[2 * i];
      v11 = v7;
      if ( v15 == v16 )
        std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(v14, v15, &v11);
      else
        *v15++ = v7;
    }
  }
  Schema::Resources::ProcessorCache::MemoryBwAllocationSystemInfo::MemoryBwAllocationSystemInfo(a1, &v13);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(&v12);
  std::vector<enum Schema::Requests::System::NetworkProperty>::_Tidy(v14, v8, v9);
  return a1;
}

```

## disassembly

```asm
0x14029231c  mov     [rsp-8+arg_8], rbx
0x140292321  mov     [rsp-8+arg_10], rdi
0x140292326  push    rbp
0x140292327  lea     rbp, [rsp-3D0h]
0x14029232f  sub     rsp, 4D0h
0x140292336  mov     rax, cs:__security_cookie
0x14029233d  xor     rax, rsp
0x140292340  mov     [rbp+3D0h+var_10], rax
0x140292347  mov     rdi, rcx
0x14029234a  mov     [rsp+4D0h+var_488], rcx
0x14029234f  mov     [rsp+4D0h+var_478], 0
0x140292358  mov     [rsp+4D0h+var_470], 0
0x140292361  lea     rcx, [rsp+4D0h+var_468]
0x140292366  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x14029236b  nop
0x14029236c  call    cs:__imp_VidOpenStatisticsHandle
0x140292373  nop     dword ptr [rax+rax+00h]
0x140292378  mov     rbx, rax
0x14029237b  mov     [rsp+4D0h+var_488], rax
0x140292380  xorps   xmm0, xmm0
0x140292383  movups  [rbp+3D0h+var_450], xmm0
0x140292387  movups  [rbp+3D0h+var_440], xmm0
0x14029238b  movups  [rbp+3D0h+var_430], xmm0
0x14029238f  xor     edx, edx; Val
0x140292391  mov     r8d, 408h; Size
0x140292397  lea     rcx, [rbp+3D0h+var_420]; void *
0x14029239b  call    memset_0
0x1402923a0  mov     [rsp+4D0h+var_4A0], 0
0x1402923a9  mov     [rsp+4D0h+var_4A8], 20h ; ' '
0x1402923b1  lea     rax, [rbp+3D0h+var_450]
0x1402923b5  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x1402923ba  xor     r9d, r9d
0x1402923bd  xor     r8d, r8d
0x1402923c0  lea     edx, [r9+3]
0x1402923c4  mov     rcx, rbx
0x1402923c7  call    cs:__imp_VidGetSystemInformation
0x1402923ce  nop     dword ptr [rax+rax+00h]
0x1402923d3  mov     rcx, [rbp+3D8h]; this
0x1402923da  test    eax, eax
0x1402923dc  jnz     short loc_1402923F0
0x1402923de  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x1402923e5  mov     edx, 16Ah; void *
0x1402923ea  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1402923f0  mov     ecx, dword ptr [rbp+3D0h+var_450]
0x1402923f3  shr     ecx, 5
0x1402923f6  and     cl, 1
0x1402923f9  mov     byte ptr [rsp+4D0h+var_478], cl
0x1402923fd  mov     al, byte ptr [rbp+3D0h+var_440+0Ch]
0x140292400  and     al, 1
0x140292402  mov     byte ptr [rsp+4D0h+var_478+1], al
0x140292406  mov     eax, dword ptr [rbp+3D0h+var_440+4]
0x140292409  mov     dword ptr [rsp+4D0h+var_478+4], eax
0x14029240d  mov     eax, dword ptr [rbp+3D0h+var_440+8]
0x140292410  mov     dword ptr [rsp+4D0h+var_470], eax
0x140292414  test    cl, cl
0x140292416  jz      loc_1402924DA
0x14029241c  mov     dword ptr [rbp+3D0h+var_430], 1
0x140292423  mov     [rsp+4D0h+var_4A0], 0
0x14029242c  mov     [rsp+4D0h+var_4A8], 408h
0x140292434  lea     rax, [rbp+3D0h+var_420]
0x140292438  mov     qword ptr [rsp+4D0h+var_4B0], rax; int
0x14029243d  mov     r9d, 10h
0x140292443  lea     r8, [rbp+3D0h+var_430]
0x140292447  lea     edx, [r9-0Ch]
0x14029244b  mov     rcx, rbx
0x14029244e  call    cs:__imp_VidGetSystemInformation
0x140292455  nop     dword ptr [rax+rax+00h]
0x14029245a  mov     rcx, [rbp+3D8h]; this
0x140292461  test    eax, eax
0x140292463  jnz     short loc_140292477
0x140292465  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x14029246c  mov     edx, 17Dh; void *
0x140292471  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140292477  mov     rax, qword ptr [rbp+3D0h+var_420]
0x14029247b  cmp     eax, dword ptr [rsp+4D0h+var_478+4]
0x14029247f  jz      short loc_1402924A0
0x140292481  mov     rcx, [rbp+3D8h]; this
0x140292488  mov     r9d, 8000FFFFh; char *
0x14029248e  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x140292495  mov     edx, 181h; void *
0x14029249a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402924a0  xor     ebx, ebx
0x1402924a2  test    eax, eax
0x1402924a4  jz      short loc_1402924DA
0x1402924a6  mov     ecx, [rbp+rbx*8+3D0h+var_418]
0x1402924aa  mov     [rsp+4D0h+var_490], ecx
0x1402924ae  mov     rdx, [rsp+4D0h+var_460]
0x1402924b3  cmp     rdx, [rsp+4D0h+var_458]
0x1402924b8  jz      short loc_1402924C4
0x1402924ba  mov     [rdx], ecx
0x1402924bc  add     [rsp+4D0h+var_460], 4
0x1402924c2  jmp     short loc_1402924D3
0x1402924c4  lea     r8, [rsp+4D0h+var_490]
0x1402924c9  lea     rcx, [rsp+4D0h+var_468]
0x1402924ce  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1402924d3  inc     ebx
0x1402924d5  cmp     ebx, [rbp+3D0h+var_420]
0x1402924d8  jb      short loc_1402924A6
0x1402924da  lea     rdx, [rsp+4D0h+var_478]
0x1402924df  mov     rcx, rdi
0x1402924e2  call    ??0MemoryBwAllocationSystemInfo@ProcessorCache@Resources@Schema@@QEAA@$$QEAU0123@@Z; Schema::Resources::ProcessorCache::MemoryBwAllocationSystemInfo::MemoryBwAllocationSystemInfo(Schema::Resources::ProcessorCache::MemoryBwAllocationSystemInfo &&)
0x1402924e7  nop
0x1402924e8  lea     rcx, [rsp+4D0h+var_488]
0x1402924ed  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x1402924f2  nop
0x1402924f3  lea     rcx, [rsp+4D0h+var_468]
0x1402924f8  call    ?_Tidy@?$vector@W4NetworkProperty@System@Requests@Schema@@V?$allocator@W4NetworkProperty@System@Requests@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Requests::System::NetworkProperty>::_Tidy(void)
0x1402924fd  mov     rax, rdi
0x140292500  mov     rcx, [rbp+3D0h+var_10]
0x140292507  xor     rcx, rsp; StackCookie
0x14029250a  call    __security_check_cookie
0x14029250f  lea     r11, [rsp+4D0h+var_s0]
0x140292517  mov     rbx, [r11+18h]
0x14029251b  mov     rdi, [r11+20h]
0x14029251f  mov     rsp, r11
0x140292522  pop     rbp
0x140292523  retn
```
