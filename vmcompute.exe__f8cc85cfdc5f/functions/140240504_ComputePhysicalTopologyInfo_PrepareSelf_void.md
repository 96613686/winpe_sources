# ComputePhysicalTopologyInfo::PrepareSelf(void)

- ea: `0x140240504`
- end: `0x140240aed`
- name: `?PrepareSelf@ComputePhysicalTopologyInfo@@EEAAXXZ`
- size: `1513`
- prototype: `void __fastcall(ComputePhysicalTopologyInfo *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1402404f0`

## callees

- `0x1400286f0`
- `0x14003b540`
- `0x14005bac8`
- `0x14005bb24`
- `0x1400a02f8`
- `0x140102440`
- `0x1401332f0`
- `0x1401fc104`
- `0x14021d0b8`
- `0x140233e00`
- `0x14023c350`
- `0x14023f5c8`
- `0x14023f85c`
- `0x1402401c0`
- `0x140240440`
- `0x140240504`
- `0x140240af4`
- `0x14024160c`
- `0x1402416a4`
- `0x140241a0c`

## import_xrefs

- `vid!VidGetSystemInformation` at `0x140240896`
- `vid!VidGetSystemInformation` at `0x140240896`
- `vid!VidOpenStatisticsHandle` at `0x140240565`
- `vid!VidOpenStatisticsHandle` at `0x140240565`
- `vid!VidGetSystemTopology` at `0x1402405f1`
- `vid!VidGetSystemTopology` at `0x1402405f1`
- `vid!VidGetProcessorTopology` at `0x1402407c9`
- `vid!VidGetProcessorTopology` at `0x1402407c9`

## string_xrefs

- `0x14024058b`: `Failed to open VID statistics handle`
- `0x1402405a1`: `onecore\vm\common\compute\computephysicaltopologyinfo.cpp`
- `0x140240614`: `onecore\vm\common\compute\computephysicaltopologyinfo.cpp`
- `0x1402407ec`: `onecore\vm\common\compute\computephysicaltopologyinfo.cpp`
- `0x140240a99`: `onecore\vm\common\compute\computephysicaltopologyinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ComputePhysicalTopologyInfo::PrepareSelf(ComputePhysicalTopologyInfo *this)
{
  ComputePhysicalTopologyInfo *v1; // r15
  char v2; // r13
  unsigned int SystemTopology; // eax
  unsigned __int8 v4; // si
  unsigned __int8 *v5; // rbx
  __int64 v6; // rbx
  ComputePhysicalTopologyInfo *v7; // r14
  __int64 *v8; // r15
  unsigned int v9; // eax
  unsigned int ProcessorTopology; // eax
  __int64 v11; // rsi
  unsigned int v12; // eax
  int v13; // ecx
  char v14; // dl
  int v15; // ecx
  struct Node *v16; // rax
  char *v17; // rcx
  struct Node **v18; // rdx
  struct Node **v19; // rsi
  struct Node **v20; // rbx
  ComputePhysicalTopologyInfo *v21; // r15
  _QWORD *v22; // rsi
  __int64 v23; // r8
  unsigned __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 v26; // r14
  __int64 i; // rbx
  __int64 v28; // rcx
  __int64 v29; // rcx
  char v30; // al
  _BYTE *v31; // rdx
  const char *v32; // [rsp+20h] [rbp-1C8h]
  char *v33; // [rsp+28h] [rbp-1C0h]
  char *v34; // [rsp+28h] [rbp-1C0h]
  char *v35; // [rsp+28h] [rbp-1C0h]
  const char *v36; // [rsp+30h] [rbp-1B8h]
  char v37; // [rsp+40h] [rbp-1A8h]
  char v38[7]; // [rsp+41h] [rbp-1A7h] BYREF
  ComputePhysicalTopologyInfo *v39; // [rsp+48h] [rbp-1A0h]
  struct Node *v40; // [rsp+50h] [rbp-198h] BYREF
  ComputePhysicalTopologyInfo *v41; // [rsp+58h] [rbp-190h]
  __int64 *v42; // [rsp+60h] [rbp-188h]
  _QWORD v43[3]; // [rsp+68h] [rbp-180h] BYREF
  _BYTE v44[4]; // [rsp+80h] [rbp-168h] BYREF
  unsigned int v45; // [rsp+84h] [rbp-164h] BYREF
  unsigned int v46; // [rsp+88h] [rbp-160h] BYREF
  ComputePhysicalTopologyInfo *v47; // [rsp+90h] [rbp-158h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp-150h] BYREF
  unsigned __int8 *v49; // [rsp+A0h] [rbp-148h] BYREF
  unsigned int v50; // [rsp+A8h] [rbp-140h] BYREF
  char v51; // [rsp+B0h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v47 = this;
  v39 = this;
  v1 = this;
  v41 = this;
  v37 = 1;
  v2 = 0;
  v44[0] = 0;
  v43[0] = VidOpenStatisticsHandle(this);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x17C,
    (unsigned int)"onecore\\vm\\common\\compute\\computephysicaltopologyinfo.cpp",
    (const char *)0x8000FFFFLL,
    (unsigned __int64)(v43[0] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL,
    (bool)"Failed to open VID statistics handle",
    v36);
  v46 = 0;
  v50 = 0;
  v49 = (unsigned __int8 *)v1 - 44;
  SystemTopology = VidGetSystemTopology(v43[0], &v46, &v50, 0, (char *)v1 - 44, 0, 0);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x189,
    (unsigned int)"onecore\\vm\\common\\compute\\computephysicaltopologyinfo.cpp",
    (const char *)SystemTopology,
    (int)"Failed to get LP count and NUMA node count.",
    v33);
  try
  {
    phkResult = 0;
    if ( (unsigned int)Vml::VmRegistryKey::Open(
                         &phkResult,
                         HKEY_LOCAL_MACHINE,
                         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
                         0x20019u) )
    {
      v45 = 0;
      if ( (unsigned int)Vml::VmRegistryKey::QueryValue(
                           (Vml::VmRegistryKey *)&phkResult,
                           L"BalancerIncludeMinroot",
                           &v45) )
      {
        v2 = v45 != 0;
        v44[0] = v45 != 0;
      }
    }
    Vml::VmRegistryKey::~VmRegistryKey((Vml::VmRegistryKey *)&phkResult);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecore\\vm\\common\\compute\\computephysicaltopologyinfo.cpp",
      "Failed to read the minroot included registry key. Will not include minroot LPs.",
      v32);
    v37 = 1;
    v2 = v44[0];
    v1 = v41;
    v47 = v41;
  }
  v4 = 0;
  v44[0] = 0;
  v42 = (__int64 *)((char *)v1 - 160);
  v5 = v49;
  do
  {
    if ( *((_QWORD *)v1 - 19) == *((_QWORD *)v1 - 18) )
    {
      std::vector<Compute::Topology::Tree>::_Emplace_reallocate<unsigned char &>(
        (char *)v1 - 160,
        *((_QWORD *)v1 - 19),
        v44);
      v4 = v44[0];
    }
    else
    {
      Compute::Topology::Tree::Tree(*((Compute::Topology::Tree **)v1 - 19), v4);
      *((_QWORD *)v1 - 19) += 160LL;
    }
    v44[0] = ++v4;
  }
  while ( v4 <= *v5 );
  v41 = (ComputePhysicalTopologyInfo *)((char *)v47 - 184);
  *((_DWORD *)v47 - 12) = v46 / v50;
  v45 = 0;
  LODWORD(v47) = 0;
  v6 = v43[0];
  v7 = v39;
  v8 = v42;
  if ( !v46 )
  {
LABEL_37:
    if ( v2 )
    {
      v19 = (struct Node **)*((_QWORD *)v7 - 16);
      v20 = (struct Node **)*((_QWORD *)v7 - 17);
      if ( v20 != v19 )
      {
        v21 = v41;
        do
          ComputePhysicalTopologyInfo::FreeLp(v21, *v20++);
        while ( v20 != v19 );
        v8 = v42;
      }
    }
    goto LABEL_42;
  }
  LOBYTE(v39) = 0;
  v9 = 0;
  while ( 1 )
  {
    v44[0] = 0;
    LODWORD(v49) = 0;
    LODWORD(phkResult) = 0;
    ProcessorTopology = VidGetProcessorTopology(v6, v9, v44, &v49, 0, &phkResult);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\vm\\common\\compute\\computephysicaltopologyinfo.cpp",
      (const char *)ProcessorTopology,
      (int)"Failed to get LP count, NUMA node number, and package ID.",
      v35);
    v11 = *v8 + 160LL * v44[0];
    v12 = (unsigned int)v49;
    v13 = *(_DWORD *)(v11 + 152);
    if ( v13 == 0xFFFF )
    {
      *(_DWORD *)(v11 + 152) = (_DWORD)v49;
      v13 = v12;
    }
    else
    {
      if ( v13 == (_DWORD)v49 )
        goto LABEL_18;
      *(_DWORD *)(v11 + 152) = 65534;
      v13 = 65534;
    }
    v12 = (unsigned int)v49;
LABEL_18:
    if ( v45 <= v12 )
      v45 = v12 + 1;
    if ( v13 == 65534 )
      *((_BYTE *)v7 - 15) = 1;
    LODWORD(v34) = 256;
    v14 = (unsigned int)VidGetSystemInformation(v6, 9, &v47) != 0 ? v37 : 0;
    v37 = v14;
    v15 = (unsigned __int8)v39;
    if ( (_DWORD)phkResult == -1 )
      v15 = 1;
    LODWORD(v39) = v15;
    if ( v14 )
    {
      v43[1] = 16;
      v43[2] = &v51;
      v16 = (struct Node *)Compute::Topology::Tree::Insert((struct Node *)v11);
      v40 = v16;
      if ( v16 )
      {
        v17 = (char *)v7 - 136;
        v18 = (struct Node **)*((_QWORD *)v7 - 16);
        if ( v18 == *((struct Node ***)v7 - 15) )
        {
          std::vector<_VID_SUBNODE_METADATA>::_Emplace_reallocate<_VID_SUBNODE_METADATA>(v17, v18, &v40);
          v16 = v40;
        }
        else
        {
          *v18 = v16;
          *((_QWORD *)v17 + 1) += 8LL;
        }
        if ( (_DWORD)phkResult != -1 && v2 )
          Compute::Topology::Tree::AllocateLp((Compute::Topology::Tree *)v11, v16);
        *((_BYTE *)v7 - 16) = 0;
      }
      v14 = v37;
      LOBYTE(v15) = (_BYTE)v39;
    }
    v9 = (_DWORD)v47 + 1;
    LODWORD(v47) = v9;
    if ( v9 >= v46 )
      break;
    v37 = v14;
  }
  if ( !(_BYTE)v15 )
    goto LABEL_37;
LABEL_42:
  v22 = (_QWORD *)((char *)v7 - 40);
  v23 = *((_QWORD *)v7 - 5);
  v24 = 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)v7 - 4) - v23) >> 3);
  if ( v45 >= v24 )
  {
    if ( v45 > v24 )
    {
      if ( v45 <= 0xAAAAAAAAAAAAAAABuLL * ((v22[2] - v23) >> 3) )
        v22[1] = std::_Uninitialized_value_construct_n<std::allocator<std::vector<unsigned char>>>(v22[1], v45 - v24);
      else
        std::vector<std::vector<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>((char *)v7 - 40);
    }
  }
  else
  {
    v25 = v23 + 24LL * v45;
    std::_Destroy_range<std::allocator<Schema::Responses::Service::SecureNestedPagingCpuId>>(v25, v22[1]);
    v22[1] = v25;
  }
  v26 = v8[1];
  for ( i = *v8; i != v26; i += 160 )
  {
    v28 = *(unsigned int *)(i + 152);
    if ( (unsigned int)(v28 - 65534) > 1 )
    {
      v29 = *v22 + 24 * v28;
      v30 = *(_BYTE *)(i + 144);
      v38[0] = v30;
      v31 = *(_BYTE **)(v29 + 8);
      if ( v31 == *(_BYTE **)(v29 + 16) )
      {
        std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(v29, v31, v38);
      }
      else
      {
        *v31 = v30;
        ++*(_QWORD *)(v29 + 8);
      }
    }
  }
  if ( !v37 )
  {
    wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecore\\vm\\common\\compute\\computephysicaltopologyinfo.cpp",
      0,
      (int)"No subnode information fetched",
      v34);
    ComputePhysicalTopologyInfo::Reset(v41);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(v43);
}

```

## disassembly

```asm
0x140240504  mov     [rsp+arg_8], rbx
0x140240509  mov     [rsp+arg_10], rsi
0x14024050e  push    rdi
0x14024050f  push    r12
0x140240511  push    r13
0x140240513  push    r14
0x140240515  push    r15
0x140240517  sub     rsp, 1C0h
0x14024051e  mov     rax, cs:__security_cookie
0x140240525  xor     rax, rsp
0x140240528  mov     [rsp+1E8h+var_38], rax
0x140240530  mov     rax, rcx
0x140240533  mov     [rsp+1E8h+var_158], rcx
0x14024053b  mov     r14, rcx
0x14024053e  mov     [rsp+1E8h+var_1A0], rcx
0x140240543  mov     r15, rcx
0x140240546  mov     [rsp+1E8h+var_190], rcx
0x14024054b  mov     r12d, 1
0x140240551  mov     al, r12b
0x140240554  mov     [rsp+1E8h+var_1A8], al
0x140240558  xor     edi, edi
0x14024055a  mov     r13b, dil
0x14024055d  mov     [rsp+1E8h+var_168], dil
0x140240565  call    cs:__imp_VidOpenStatisticsHandle
0x14024056c  nop     dword ptr [rax+rax+00h]
0x140240571  mov     rbx, rax
0x140240574  mov     [rsp+1E8h+var_180], rax
0x140240579  dec     rax
0x14024057c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140240580  setbe   al
0x140240583  mov     rcx, [rsp+1E8h]; this
0x14024058b  lea     rdx, aFailedToOpenVi; "Failed to open VID statistics handle"
0x140240592  mov     [rsp+1E8h+var_1C0], rdx; bool
0x140240597  mov     [rsp+1E8h+var_1C8], al; char
0x14024059b  mov     r9d, 8000FFFFh; char *
0x1402405a1  lea     r8, aOnecoreVmCommo_39; "onecore\\vm\\common\\compute\\computeph"...
0x1402405a8  mov     edx, 17Ch; void *
0x1402405ad  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x1402405b2  mov     [rsp+1E8h+var_160], edi
0x1402405b9  mov     [rsp+1E8h+var_140], edi
0x1402405c0  lea     rax, [r15-2Ch]
0x1402405c4  mov     [rsp+1E8h+var_148], rax
0x1402405cc  mov     [rsp+1E8h+var_1B8], rdi
0x1402405d1  mov     [rsp+1E8h+var_1C0], rdi; char *
0x1402405d6  mov     qword ptr [rsp+1E8h+var_1C8], rax
0x1402405db  xor     r9d, r9d
0x1402405de  lea     r8, [rsp+1E8h+var_140]
0x1402405e6  lea     rdx, [rsp+1E8h+var_160]
0x1402405ee  mov     rcx, rbx
0x1402405f1  call    cs:__imp_VidGetSystemTopology
0x1402405f8  nop     dword ptr [rax+rax+00h]
0x1402405fd  mov     rcx, [rsp+1E8h]; this
0x140240605  lea     rdx, aFailedToGetLpC; "Failed to get LP count and NUMA node co"...
0x14024060c  mov     qword ptr [rsp+1E8h+var_1C8], rdx; int
0x140240611  mov     r9d, eax; char *
0x140240614  lea     r8, aOnecoreVmCommo_39; "onecore\\vm\\common\\compute\\computeph"...
0x14024061b  mov     edx, 189h; void *
0x140240620  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x140240625  nop
0x140240626  mov     [rsp+1E8h+phkResult], rdi
0x14024062e  mov     r9d, 20019h; unsigned int
0x140240634  lea     r8, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14024063b  mov     rdx, 0FFFFFFFF80000002h; hKey
0x140240642  lea     rcx, [rsp+1E8h+phkResult]; phkResult
0x14024064a  call    ?Open@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGK@Z; Vml::VmRegistryKey::Open(HKEY__ *,ushort const *,ulong)
0x14024064f  test    eax, eax
0x140240651  jz      short loc_14024068D
0x140240653  mov     [rsp+1E8h+var_164], edi
0x14024065a  lea     r8, [rsp+1E8h+var_164]; unsigned int *
0x140240662  lea     rdx, aBalancerinclud; "BalancerIncludeMinroot"
0x140240669  lea     rcx, [rsp+1E8h+phkResult]; this
0x140240671  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x140240676  test    eax, eax
0x140240678  jz      short loc_14024068D
0x14024067a  cmp     [rsp+1E8h+var_164], edi
0x140240681  setnz   r13b
0x140240685  mov     [rsp+1E8h+var_168], r13b
0x14024068d  lea     rcx, [rsp+1E8h+phkResult]; this
0x140240695  call    ??1VmRegistryKey@Vml@@QEAA@XZ; Vml::VmRegistryKey::~VmRegistryKey(void)
0x14024069a  nop
0x14024069b  jmp     short loc_1402406C2
0x14024069d  xor     edi, edi
0x14024069f  lea     r12d, [rdi+1]
0x1402406a3  mov     al, r12b
0x1402406a6  mov     [rsp+1E8h+var_1A8], al
0x1402406aa  mov     r13b, [rsp+1E8h+var_168]
0x1402406b2  mov     r15, [rsp+1E8h+var_190]
0x1402406b7  mov     rax, r15
0x1402406ba  mov     [rsp+1E8h+var_158], rax
0x1402406c2  mov     sil, dil
0x1402406c5  mov     [rsp+1E8h+var_168], dil
0x1402406cd  lea     r14, [r15-0A0h]
0x1402406d4  mov     [rsp+1E8h+var_188], r14
0x1402406d9  mov     rbx, [rsp+1E8h+var_148]
0x1402406e1  mov     rax, [r15-98h]
0x1402406e8  cmp     rax, [r15-90h]
0x1402406ef  jz      short loc_140240706
0x1402406f1  mov     dl, sil; unsigned __int8
0x1402406f4  mov     rcx, rax; this
0x1402406f7  call    ??0Tree@Topology@Compute@@QEAA@E@Z; Compute::Topology::Tree::Tree(uchar)
0x1402406fc  add     qword ptr [r14+8], 0A0h
0x140240704  jmp     short loc_140240721
0x140240706  lea     r8, [rsp+1E8h+var_168]
0x14024070e  mov     rdx, rax
0x140240711  mov     rcx, r14
0x140240714  call    ??$_Emplace_reallocate@AEAE@?$vector@VTree@Topology@Compute@@V?$allocator@VTree@Topology@Compute@@@std@@@std@@AEAAPEAVTree@Topology@Compute@@QEAV234@AEAE@Z; std::vector<Compute::Topology::Tree>::_Emplace_reallocate<uchar &>(Compute::Topology::Tree * const,uchar &)
0x140240719  mov     sil, [rsp+1E8h+var_168]
0x140240721  add     sil, r12b
0x140240724  mov     [rsp+1E8h+var_168], sil
0x14024072c  cmp     sil, [rbx]
0x14024072f  jbe     short loc_1402406E1
0x140240731  mov     rcx, [rsp+1E8h+var_158]
0x140240739  add     rcx, 0FFFFFFFFFFFFFF48h
0x140240740  mov     [rsp+1E8h+var_190], rcx
0x140240745  xor     edx, edx
0x140240747  mov     eax, [rsp+1E8h+var_160]
0x14024074e  div     [rsp+1E8h+var_140]
0x140240755  mov     [rcx+88h], eax
0x14024075b  mov     [rsp+1E8h+var_164], edi
0x140240762  mov     dword ptr [rsp+1E8h+var_158], edi
0x140240769  cmp     [rsp+1E8h+var_160], edi
0x140240770  mov     rbx, [rsp+1E8h+var_180]
0x140240775  mov     r14, [rsp+1E8h+var_1A0]
0x14024077a  mov     r15, [rsp+1E8h+var_188]
0x14024077f  jbe     loc_14024097B
0x140240785  mov     byte ptr [rsp+1E8h+var_1A0], dil
0x14024078a  mov     eax, edi
0x14024078c  mov     [rsp+1E8h+var_168], dil
0x140240794  mov     dword ptr [rsp+1E8h+var_148], edi
0x14024079b  mov     dword ptr [rsp+1E8h+phkResult], edi
0x1402407a2  lea     rcx, [rsp+1E8h+phkResult]
0x1402407aa  mov     [rsp+1E8h+var_1C0], rcx; char *
0x1402407af  mov     qword ptr [rsp+1E8h+var_1C8], rdi
0x1402407b4  lea     r9, [rsp+1E8h+var_148]
0x1402407bc  lea     r8, [rsp+1E8h+var_168]
0x1402407c4  mov     edx, eax
0x1402407c6  mov     rcx, rbx
0x1402407c9  call    cs:__imp_VidGetProcessorTopology
0x1402407d0  nop     dword ptr [rax+rax+00h]
0x1402407d5  mov     rcx, [rsp+1E8h]; this
0x1402407dd  lea     rdx, aFailedToGetLpC_0; "Failed to get LP count, NUMA node numbe"...
0x1402407e4  mov     qword ptr [rsp+1E8h+var_1C8], rdx; int
0x1402407e9  mov     r9d, eax; char *
0x1402407ec  lea     r8, aOnecoreVmCommo_39; "onecore\\vm\\common\\compute\\computeph"...
0x1402407f3  mov     edx, 1B6h; void *
0x1402407f8  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1402407fd  movzx   eax, [rsp+1E8h+var_168]
0x140240805  lea     rsi, [rax+rax*4]
0x140240809  shl     rsi, 5
0x14024080d  add     rsi, [r15]
0x140240810  mov     eax, dword ptr [rsp+1E8h+var_148]
0x140240817  mov     ecx, [rsi+98h]
0x14024081d  cmp     ecx, 0FFFFh
0x140240823  jnz     short loc_14024082F
0x140240825  mov     [rsi+98h], eax
0x14024082b  mov     ecx, eax
0x14024082d  jmp     short loc_140240842
0x14024082f  cmp     ecx, eax
0x140240831  jz      short loc_140240849
0x140240833  mov     dword ptr [rsi+98h], 0FFFEh
0x14024083d  mov     ecx, 0FFFEh
0x140240842  mov     eax, dword ptr [rsp+1E8h+var_148]
0x140240849  cmp     [rsp+1E8h+var_164], eax
0x140240850  ja      short loc_14024085B
0x140240852  inc     eax
0x140240854  mov     [rsp+1E8h+var_164], eax
0x14024085b  cmp     ecx, 0FFFEh
0x140240861  jnz     short loc_140240867
0x140240863  mov     [r14-0Fh], r12b
0x140240867  mov     [rsp+1E8h+var_1B8], rdi
0x14024086c  mov     dword ptr [rsp+1E8h+var_1C0], 100h
0x140240874  lea     rax, [rsp+1E8h+var_138]
0x14024087c  mov     qword ptr [rsp+1E8h+var_1C8], rax
0x140240881  mov     r9d, 4
0x140240887  lea     r8, [rsp+1E8h+var_158]
0x14024088f  lea     edx, [r9+5]
0x140240893  mov     rcx, rbx
0x140240896  call    cs:__imp_VidGetSystemInformation
0x14024089d  nop     dword ptr [rax+rax+00h]
0x1402408a2  neg     eax
0x1402408a4  sbb     cl, cl
0x1402408a6  and     cl, [rsp+1E8h+var_1A8]
0x1402408aa  mov     dl, cl
0x1402408ac  mov     [rsp+1E8h+var_1A8], cl
0x1402408b0  mov     ecx, dword ptr [rsp+1E8h+var_1A0]
0x1402408b4  movzx   ecx, cl
0x1402408b7  cmp     dword ptr [rsp+1E8h+phkResult], 0FFFFFFFFh
0x1402408bf  cmovz   ecx, r12d
0x1402408c3  mov     dword ptr [rsp+1E8h+var_1A0], ecx
0x1402408c7  test    dl, dl
0x1402408c9  jz      loc_140240954
0x1402408cf  mov     [rsp+1E8h+var_178], 10h
0x1402408d8  lea     rax, [rsp+1E8h+var_138]
0x1402408e0  mov     [rsp+1E8h+var_170], rax
0x1402408e5  mov     r8d, dword ptr [rsp+1E8h+var_158]
0x1402408ed  lea     rdx, [rsp+1E8h+var_178]
0x1402408f2  mov     rcx, rsi
0x1402408f5  call    ?Insert@Tree@Topology@Compute@@QEAAPEAVNode@23@V?$span@$$CBU_HV_SUBNODE@@$0?0@gsl@@I@Z; Compute::Topology::Tree::Insert(gsl::span<_HV_SUBNODE const,-1>,uint)
0x1402408fa  mov     [rsp+1E8h+var_198], rax
0x1402408ff  test    rax, rax
0x140240902  jz      short loc_14024094C
0x140240904  lea     rcx, [r14-88h]
0x14024090b  mov     rdx, [r14-80h]
0x14024090f  cmp     rdx, [r14-78h]
0x140240913  jz      short loc_14024091F
0x140240915  mov     [rdx], rax
0x140240918  add     qword ptr [rcx+8], 8
0x14024091d  jmp     short loc_14024092E
0x14024091f  lea     r8, [rsp+1E8h+var_198]
0x140240924  call    ??$_Emplace_reallocate@U_VID_SUBNODE_METADATA@@@?$vector@U_VID_SUBNODE_METADATA@@V?$allocator@U_VID_SUBNODE_METADATA@@@std@@@std@@AEAAPEAU_VID_SUBNODE_METADATA@@QEAU2@$$QEAU2@@Z; std::vector<_VID_SUBNODE_METADATA>::_Emplace_reallocate<_VID_SUBNODE_METADATA>(_VID_SUBNODE_METADATA * const,_VID_SUBNODE_METADATA &&)
0x140240929  mov     rax, [rsp+1E8h+var_198]
0x14024092e  cmp     dword ptr [rsp+1E8h+phkResult], 0FFFFFFFFh
0x140240936  jz      short loc_140240948
0x140240938  test    r13b, r13b
0x14024093b  jz      short loc_140240948
0x14024093d  mov     rdx, rax; struct Node *
0x140240940  mov     rcx, rsi; this
0x140240943  call    ?AllocateLp@Tree@Topology@Compute@@QEAAXPEAVNode@23@@Z; Compute::Topology::Tree::AllocateLp(Compute::Topology::Node *)
0x140240948  mov     [r14-10h], dil
0x14024094c  mov     dl, [rsp+1E8h+var_1A8]
0x140240950  mov     ecx, dword ptr [rsp+1E8h+var_1A0]
0x140240954  mov     eax, dword ptr [rsp+1E8h+var_158]
0x14024095b  add     eax, r12d
0x14024095e  mov     dword ptr [rsp+1E8h+var_158], eax
0x140240965  cmp     eax, [rsp+1E8h+var_160]
0x14024096c  jnb     short loc_140240977
0x14024096e  mov     [rsp+1E8h+var_1A8], dl
0x140240972  jmp     loc_14024078C
0x140240977  test    cl, cl
0x140240979  jnz     short loc_1402409AE
0x14024097b  test    r13b, r13b
0x14024097e  jz      short loc_1402409AE
0x140240980  mov     rsi, [r14-80h]
0x140240984  mov     rbx, [r14-88h]
0x14024098b  cmp     rbx, rsi
0x14024098e  jz      short loc_1402409AE
0x140240990  mov     r15, [rsp+1E8h+var_190]
0x140240995  mov     rdx, [rbx]; struct Node *
0x140240998  mov     rcx, r15; this
0x14024099b  call    ?FreeLp@ComputePhysicalTopologyInfo@@UEAAXPEAVNode@Topology@Compute@@@Z; ComputePhysicalTopologyInfo::FreeLp(Compute::Topology::Node *)
0x1402409a0  add     rbx, 8
0x1402409a4  cmp     rbx, rsi
0x1402409a7  jnz     short loc_140240995
0x1402409a9  mov     r15, [rsp+1E8h+var_188]
0x1402409ae  lea     rsi, [r14-28h]
0x1402409b2  mov     edx, [rsp+1E8h+var_164]
0x1402409b9  mov     r8, [rsi]
0x1402409bc  mov     rcx, [rsi+8]
0x1402409c0  sub     rcx, r8
0x1402409c3  sar     rcx, 3
0x1402409c7  mov     r9, 0AAAAAAAAAAAAAAABh
0x1402409d1  imul    rcx, r9
0x1402409d5  cmp     rdx, rcx
0x1402409d8  jnb     short loc_1402409F4
0x1402409da  lea     rax, [rdx+rdx*2]
0x1402409de  lea     rbx, [r8+rax*8]
0x1402409e2  mov     rdx, [rsi+8]
0x1402409e6  mov     rcx, rbx
0x1402409e9  call    ??$_Destroy_range@V?$allocator@USecureNestedPagingCpuId@Service@Responses@Schema@@@std@@@std@@YAXPEAUSecureNestedPagingCpuId@Service@Responses@Schema@@QEAU1234@AEAV?$allocator@USecureNestedPagingCpuId@Service@Responses@Schema@@@0@@Z; std::_Destroy_range<std::allocator<Schema::Responses::Service::SecureNestedPagingCpuId>>(Schema::Responses::Service::SecureNestedPagingCpuId *,Schema::Responses::Service::SecureNestedPagingCpuId * const,std::allocator<Schema::Responses::Service::SecureNestedPagingCpuId> &)
0x1402409ee  mov     [rsi+8], rbx
0x1402409f2  jmp     short loc_140240A24
0x1402409f4  jbe     short loc_140240A24
0x1402409f6  mov     rax, [rsi+10h]
0x1402409fa  sub     rax, r8
0x1402409fd  sar     rax, 3
0x140240a01  imul    rax, r9
0x140240a05  cmp     rdx, rax
0x140240a08  jbe     short loc_140240A14
0x140240a0a  mov     rcx, rsi
0x140240a0d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<std::vector<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140240a12  jmp     short loc_140240A24
0x140240a14  sub     rdx, rcx
0x140240a17  mov     rcx, [rsi+8]
0x140240a1b  call    ??$_Uninitialized_value_construct_n@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@std@@@std@@YAPEAV?$vector@EV?$allocator@E@std@@@0@PEAV10@_KAEAV?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<std::vector<uchar>>>(std::vector<uchar> *,unsigned __int64,std::allocator<std::vector<uchar>> &)
0x140240a20  mov     [rsi+8], rax
0x140240a24  mov     r14, [r15+8]
0x140240a28  mov     rbx, [r15]
0x140240a2b  jmp     short loc_140240A76
0x140240a2d  mov     ecx, [rbx+98h]
0x140240a33  lea     eax, [rcx-0FFFEh]
0x140240a39  cmp     eax, r12d
0x140240a3c  jbe     short loc_140240A6F
0x140240a3e  lea     rcx, [rcx+rcx*2]
0x140240a42  mov     rax, [rsi]
0x140240a45  lea     rcx, [rax+rcx*8]
0x140240a49  mov     al, [rbx+90h]
0x140240a4f  mov     [rsp+1E8h+var_1A7], al
0x140240a53  mov     rdx, [rcx+8]
0x140240a57  cmp     rdx, [rcx+10h]
0x140240a5b  jz      short loc_140240A65
0x140240a5d  mov     [rdx], al
0x140240a5f  add     [rcx+8], r12
0x140240a63  jmp     short loc_140240A6F
0x140240a65  lea     r8, [rsp+1E8h+var_1A7]
0x140240a6a  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x140240a6f  add     rbx, 0A0h
0x140240a76  cmp     rbx, r14
0x140240a79  jnz     short loc_140240A2D
0x140240a7b  cmp     [rsp+1E8h+var_1A8], dil
0x140240a80  jnz     short loc_140240AB5
  ... truncated ...
```
