# ComputeService::Resource::CpuResourceAllocator::GetProcessorTopology(void)

- ea: `0x14010f0cc`
- end: `0x14010f351`
- name: `?GetProcessorTopology@CpuResourceAllocator@Resource@ComputeService@@AEAA?AUProcessorTopology@Processor@Resources@Schema@@XZ`
- size: `645`
- prototype: `struct Schema::Resources::Processor::ProcessorTopology __high(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140110300`

## callees

- `0x14002d888`
- `0x140037618`
- `0x14005bb24`
- `0x140080180`
- `0x1400a02f8`
- `0x1400c40e0`
- `0x14010f0cc`
- `0x14010f358`
- `0x14010f380`
- `0x14010f3c4`
- `0x1401332f0`
- `0x14028e430`
- `0x14028e7ac`

## import_xrefs

- `vid!VidGetSystemInformation` at `0x14010f273`
- `vid!VidGetSystemInformation` at `0x14010f273`
- `vid!VidOpenStatisticsHandle` at `0x14010f13c`
- `vid!VidOpenStatisticsHandle` at `0x14010f13c`
- `vid!VidGetSystemTopology` at `0x14010f1af`
- `vid!VidGetSystemTopology` at `0x14010f1af`
- `vid!VidGetProcessorTopology` at `0x14010f225`
- `vid!VidGetProcessorTopology` at `0x14010f225`

## string_xrefs

- `0x14010f117`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14010f177`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14010f1c6`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14010f33f`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14010f161`: `Failed to open VID statistics handle`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Schema::Resources::Processor::ProcessorTopology *__fastcall ComputeService::Resource::CpuResourceAllocator::GetProcessorTopology(
        ComputeService *a1,
        Schema::Resources::Processor::ProcessorTopology *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  const char *v5; // r9
  const char *v6; // r9
  __int64 v7; // rcx
  unsigned int j; // esi
  __int64 v9; // rdx
  int v11; // [rsp+20h] [rbp-E0h]
  const char *v12; // [rsp+30h] [rbp-D0h]
  __int128 v13; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v14[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int i; // [rsp+68h] [rbp-98h] BYREF
  int v16; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[4]; // [rsp+74h] [rbp-8Ch] BYREF
  _BYTE v19[4]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v20[4]; // [rsp+7Ch] [rbp-84h] BYREF
  int v21; // [rsp+80h] [rbp-80h]
  _BYTE v22[8]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD *v23; // [rsp+90h] [rbp-70h]
  _OWORD *v24; // [rsp+98h] [rbp-68h]
  _QWORD v25[32]; // [rsp+A0h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v14[1] = a2;
  if ( !ComputeService::AreVirtualMachinesEnabled(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25D,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
      (const char *)0x80370102LL,
      v11);
  Schema::Resources::Processor::ProcessorTopology::ProcessorTopology(a2);
  v4 = VidOpenStatisticsHandle(v3);
  v14[0] = v4;
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x265,
    (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
    (const char *)0x8000FFFFLL,
    (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL,
    (bool)"Failed to open VID statistics handle",
    v12);
  if ( !(unsigned int)VidGetSystemTopology(v4, a2, 0, 0, 0, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
      v5);
  for ( i = 0; i < *(_DWORD *)a2; ++i )
  {
    Schema::Resources::Processor::LogicalProcessor::LogicalProcessor((Schema::Resources::Processor::LogicalProcessor *)&v17);
    v17 = i;
    v16 = 0;
    if ( !(unsigned int)VidGetProcessorTopology(v4, i, v18, v19, v20, &v16) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x27F,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
        v6);
    v21 = v16;
    if ( (unsigned int)VidGetSystemInformation(v4, 9, &i) )
    {
      for ( j = 0; j < 0x10; ++j )
      {
        v7 = LODWORD(v25[2 * j + 1]);
        if ( (_DWORD)v7 == -1 )
          break;
        *(_QWORD *)&v13 = (unsigned int)v7;
        v7 = 0;
        *((_QWORD *)&v13 + 1) = v25[2 * j];
        if ( v23 == v24 )
          std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(
            v22,
            v23,
            &v13);
        else
          *v23++ = v13;
      }
    }
    v9 = *((_QWORD *)a2 + 2);
    if ( v9 == *((_QWORD *)a2 + 3) )
    {
      std::vector<Schema::Resources::Processor::LogicalProcessor>::_Emplace_reallocate<Schema::Resources::Processor::LogicalProcessor const &>(
        (char *)a2 + 8,
        v9,
        &v17);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<Schema::Resources::Processor::LogicalProcessor>>::construct<Schema::Resources::Processor::LogicalProcessor,Schema::Resources::Processor::LogicalProcessor const &>(
        v7,
        v9,
        &v17);
      *((_QWORD *)a2 + 2) += 48LL;
    }
    std::vector<_HV_SUBNODE>::_Tidy(v22);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(v14);
  return a2;
}

```

## disassembly

```asm
0x14010f0cc  push    rbp
0x14010f0ce  push    rbx
0x14010f0cf  push    rsi
0x14010f0d0  push    rdi
0x14010f0d1  lea     rbp, [rsp-0B8h]
0x14010f0d9  sub     rsp, 1B8h
0x14010f0e0  mov     rax, cs:__security_cookie
0x14010f0e7  xor     rax, rsp
0x14010f0ea  mov     [rbp+0D0h+var_30], rax
0x14010f0f1  mov     rdi, rdx
0x14010f0f4  mov     [rsp+1D0h+var_170], rdx
0x14010f0f9  mov     [rsp+1D0h+var_190], 0
0x14010f101  mov     rbx, [rbp+0D8h]
0x14010f108  call    ?AreVirtualMachinesEnabled@ComputeService@@YA_NXZ; ComputeService::AreVirtualMachinesEnabled(void)
0x14010f10d  test    al, al
0x14010f10f  jnz     short loc_14010F12C
0x14010f111  mov     r9d, 80370102h; char *
0x14010f117  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14010f11e  mov     edx, 25Dh; void *
0x14010f123  mov     rcx, rbx; this
0x14010f126  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14010f12c  mov     rcx, rdi; this
0x14010f12f  call    ??0ProcessorTopology@Processor@Resources@Schema@@QEAA@XZ; Schema::Resources::Processor::ProcessorTopology::ProcessorTopology(void)
0x14010f134  mov     [rsp+1D0h+var_190], 1
0x14010f13c  call    cs:__imp_VidOpenStatisticsHandle
0x14010f143  nop     dword ptr [rax+rax+00h]
0x14010f148  mov     rbx, rax
0x14010f14b  mov     [rsp+1D0h+var_178], rax
0x14010f150  dec     rax
0x14010f153  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14010f157  setbe   al
0x14010f15a  mov     rcx, [rbp+0D8h]; this
0x14010f161  lea     rdx, aFailedToOpenVi; "Failed to open VID statistics handle"
0x14010f168  mov     qword ptr [rsp+1D0h+var_1A8], rdx; bool
0x14010f16d  mov     [rsp+1D0h+var_1B0], al; char
0x14010f171  mov     r9d, 8000FFFFh; char *
0x14010f177  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14010f17e  mov     edx, 265h; void *
0x14010f183  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x14010f188  mov     [rsp+1D0h+var_1A0], 0
0x14010f191  mov     qword ptr [rsp+1D0h+var_1A8], 0
0x14010f19a  mov     qword ptr [rsp+1D0h+var_1B0], 0
0x14010f1a3  xor     r9d, r9d
0x14010f1a6  xor     r8d, r8d
0x14010f1a9  mov     rdx, rdi
0x14010f1ac  mov     rcx, rbx
0x14010f1af  call    cs:__imp_VidGetSystemTopology
0x14010f1b6  nop     dword ptr [rax+rax+00h]
0x14010f1bb  mov     rcx, [rbp+0D8h]; this
0x14010f1c2  test    eax, eax
0x14010f1c4  jnz     short loc_14010F1D8
0x14010f1c6  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14010f1cd  mov     edx, 270h; void *
0x14010f1d2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14010f1d8  mov     [rsp+1D0h+var_168], 0
0x14010f1e0  cmp     dword ptr [rdi], 0
0x14010f1e3  jbe     loc_14010F316
0x14010f1e9  lea     rcx, [rsp+1D0h+var_160]; this
0x14010f1ee  call    ??0LogicalProcessor@Processor@Resources@Schema@@QEAA@XZ; Schema::Resources::Processor::LogicalProcessor::LogicalProcessor(void)
0x14010f1f3  nop
0x14010f1f4  mov     edx, [rsp+1D0h+var_168]
0x14010f1f8  mov     [rsp+1D0h+var_160], edx
0x14010f1fc  mov     [rsp+1D0h+var_164], 0
0x14010f204  lea     rax, [rsp+1D0h+var_164]
0x14010f209  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x14010f20e  lea     rax, [rsp+1D0h+var_154]
0x14010f213  mov     qword ptr [rsp+1D0h+var_1B0], rax
0x14010f218  lea     r9, [rsp+1D0h+var_158]
0x14010f21d  lea     r8, [rsp+1D0h+var_15C]
0x14010f222  mov     rcx, rbx
0x14010f225  call    cs:__imp_VidGetProcessorTopology
0x14010f22c  nop     dword ptr [rax+rax+00h]
0x14010f231  mov     rcx, [rbp+0D8h]; this
0x14010f238  test    eax, eax
0x14010f23a  jz      loc_14010F33F
0x14010f240  mov     eax, [rsp+1D0h+var_164]
0x14010f244  mov     [rbp+0D0h+var_150], eax
0x14010f247  mov     [rsp+1D0h+var_1A0], 0
0x14010f250  mov     dword ptr [rsp+1D0h+var_1A8], 100h
0x14010f258  lea     rax, [rbp+0D0h+var_130]
0x14010f25c  mov     qword ptr [rsp+1D0h+var_1B0], rax
0x14010f261  mov     r9d, 4
0x14010f267  lea     r8, [rsp+1D0h+var_168]
0x14010f26c  lea     edx, [r9+5]
0x14010f270  mov     rcx, rbx
0x14010f273  call    cs:__imp_VidGetSystemInformation
0x14010f27a  nop     dword ptr [rax+rax+00h]
0x14010f27f  test    eax, eax
0x14010f281  jz      short loc_14010F2D6
0x14010f283  xor     esi, esi
0x14010f285  mov     eax, esi
0x14010f287  add     rax, rax
0x14010f28a  mov     ecx, [rbp+rax*8+0D0h+var_128]
0x14010f28e  cmp     ecx, 0FFFFFFFFh
0x14010f291  jz      short loc_14010F2D6
0x14010f293  mov     dword ptr [rsp+1D0h+var_188], ecx
0x14010f297  xor     ecx, ecx
0x14010f299  mov     dword ptr [rsp+1D0h+var_188+4], ecx
0x14010f29d  mov     rax, [rbp+rax*8+0D0h+var_130]
0x14010f2a2  mov     qword ptr [rsp+1D0h+var_188+8], rax
0x14010f2a7  mov     rdx, [rbp+0D0h+var_140]
0x14010f2ab  cmp     rdx, [rbp+0D0h+var_138]
0x14010f2af  jz      short loc_14010F2C1
0x14010f2b1  movups  xmm0, [rsp+1D0h+var_188]
0x14010f2b6  movdqu  xmmword ptr [rdx], xmm0
0x14010f2ba  add     [rbp+0D0h+var_140], 10h
0x14010f2bf  jmp     short loc_14010F2CF
0x14010f2c1  lea     r8, [rsp+1D0h+var_188]
0x14010f2c6  lea     rcx, [rbp+0D0h+var_148]
0x14010f2ca  call    ??$_Emplace_reallocate@AEBUCpuGroupProperty@Processor@Resources@Schema@@@?$vector@UCpuGroupProperty@Processor@Resources@Schema@@V?$allocator@UCpuGroupProperty@Processor@Resources@Schema@@@std@@@std@@AEAAPEAUCpuGroupProperty@Processor@Resources@Schema@@QEAU2345@AEBU2345@@Z; std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(Schema::Resources::Processor::CpuGroupProperty * const,Schema::Resources::Processor::CpuGroupProperty const &)
0x14010f2cf  inc     esi
0x14010f2d1  cmp     esi, 10h
0x14010f2d4  jb      short loc_14010F285
0x14010f2d6  mov     rdx, [rdi+10h]
0x14010f2da  lea     r8, [rsp+1D0h+var_160]
0x14010f2df  cmp     rdx, [rdi+18h]
0x14010f2e3  jz      short loc_14010F2F1
0x14010f2e5  call    ??$construct@ULogicalProcessor@Processor@Resources@Schema@@AEBU1234@@?$_Default_allocator_traits@V?$allocator@ULogicalProcessor@Processor@Resources@Schema@@@std@@@std@@SAXAEAV?$allocator@ULogicalProcessor@Processor@Resources@Schema@@@1@QEAULogicalProcessor@Processor@Resources@Schema@@AEBU3456@@Z; std::_Default_allocator_traits<std::allocator<Schema::Resources::Processor::LogicalProcessor>>::construct<Schema::Resources::Processor::LogicalProcessor,Schema::Resources::Processor::LogicalProcessor const &>(std::allocator<Schema::Resources::Processor::LogicalProcessor> &,Schema::Resources::Processor::LogicalProcessor * const,Schema::Resources::Processor::LogicalProcessor const &)
0x14010f2ea  add     qword ptr [rdi+10h], 30h ; '0'
0x14010f2ef  jmp     short loc_14010F2FB
0x14010f2f1  lea     rcx, [rdi+8]
0x14010f2f5  call    ??$_Emplace_reallocate@AEBULogicalProcessor@Processor@Resources@Schema@@@?$vector@ULogicalProcessor@Processor@Resources@Schema@@V?$allocator@ULogicalProcessor@Processor@Resources@Schema@@@std@@@std@@AEAAPEAULogicalProcessor@Processor@Resources@Schema@@QEAU2345@AEBU2345@@Z; std::vector<Schema::Resources::Processor::LogicalProcessor>::_Emplace_reallocate<Schema::Resources::Processor::LogicalProcessor const &>(Schema::Resources::Processor::LogicalProcessor * const,Schema::Resources::Processor::LogicalProcessor const &)
0x14010f2fa  nop
0x14010f2fb  lea     rcx, [rbp+0D0h+var_148]
0x14010f2ff  call    ?_Tidy@?$vector@U_HV_SUBNODE@@V?$allocator@U_HV_SUBNODE@@@std@@@std@@AEAAXXZ; std::vector<_HV_SUBNODE>::_Tidy(void)
0x14010f304  mov     eax, [rsp+1D0h+var_168]
0x14010f308  inc     eax
0x14010f30a  mov     [rsp+1D0h+var_168], eax
0x14010f30e  cmp     eax, [rdi]
0x14010f310  jb      loc_14010F1E9
0x14010f316  lea     rcx, [rsp+1D0h+var_178]
0x14010f31b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x14010f320  mov     rax, rdi
0x14010f323  mov     rcx, [rbp+0D0h+var_30]
0x14010f32a  xor     rcx, rsp; StackCookie
0x14010f32d  call    __security_check_cookie
0x14010f332  add     rsp, 1B8h
0x14010f339  pop     rdi
0x14010f33a  pop     rsi
0x14010f33b  pop     rbx
0x14010f33c  pop     rbp
0x14010f33d  retn
0x14010f33f  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14010f346  mov     edx, 27Fh; void *
0x14010f34b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
