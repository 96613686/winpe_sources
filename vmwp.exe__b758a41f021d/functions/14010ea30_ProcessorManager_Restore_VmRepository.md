# ProcessorManager::Restore(VmRepository *)

- ea: `0x14010ea30`
- end: `0x14010efa6`
- name: `?Restore@ProcessorManager@@UEAAXPEAVVmRepository@@@Z`
- size: `1398`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct VmRepository *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400364a0`
- `0x1400545bc`
- `0x140055e18`
- `0x14005e524`
- `0x140066eec`
- `0x140078628`
- `0x140083990`
- `0x14010ea30`
- `0x14011017c`
- `0x140110314`
- `0x140118280`
- `0x14011ea40`
- `0x14011f6fc`
- `0x1401217a0`
- `0x1402a28f0`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14010ed8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14010ee4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14010ed8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14010ee4d`
- `vid!VidSetPartitionProperty` at `0x14010eb88`
- `vid!VidSetPartitionProperty` at `0x14010ef59`
- `vid!VidSetPartitionProperty` at `0x14010eb88`
- `vid!VidSetPartitionProperty` at `0x14010ef59`
- `vid!VidGetPartitionPropertyEx` at `0x14010ebd8`
- `vid!VidGetPartitionPropertyEx` at `0x14010ebd8`
- `vid!VidGetPartitionProperty` at `0x14010eafd`
- `vid!VidGetPartitionProperty` at `0x14010eb23`
- `vid!VidGetPartitionProperty` at `0x14010ec72`
- `vid!VidGetPartitionProperty` at `0x14010eca7`
- `vid!VidGetPartitionProperty` at `0x14010eccd`
- `vid!VidGetPartitionProperty` at `0x14010eafd`
- `vid!VidGetPartitionProperty` at `0x14010eb23`
- `vid!VidGetPartitionProperty` at `0x14010ec72`
- `vid!VidGetPartitionProperty` at `0x14010eca7`
- `vid!VidGetPartitionProperty` at `0x14010eccd`

## string_xrefs

- `0x14010eda6`: `onecore\vm\common\vml\VmComputerName.h`
- `0x14010ee64`: `onecore\vm\common\vml\VmComputerName.h`
- `0x14010ed35`: `IgnoreNonArchitecturalCoreSharingCompatibility`
- `0x14010ef35`: `Warning: Failed to read %s from saved state repository.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ProcessorManager::Restore(ProcessorManager *this, struct VmRepository *a2)
{
  int v4; // eax
  _QWORD *v5; // rdi
  int v6; // eax
  unsigned __int64 v7; // rax
  int i; // r8d
  int j; // edi
  const char *v10; // r9
  _DWORD *v11; // rdi
  WCHAR *v12; // rax
  const char *v13; // r9
  WCHAR *v14; // rax
  const char *v15; // r9
  __int64 v16; // r8
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v22[3]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  DWORD nSize[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v26; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v27; // [rsp+94h] [rbp-6Ch] BYREF
  _BYTE v28[4072]; // [rsp+98h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10A8h] [rbp+FA8h]

  phkResult = 0;
  v4 = (*(__int64 (__fastcall **)(struct VmRepository *, const unsigned __int16 *, HKEY *, __int64))(*(_QWORD *)a2 + 88LL))(
         a2,
         L"/savedVM/processor_attribute",
         &phkResult,
         8);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF51,
      (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
      (const char *)(unsigned int)v4,
      v17);
  if ( **((unsigned int **)this + 83) < (unsigned __int64)phkResult >> 32 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF56,
      (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
      (const char *)0x80004005LL,
      v17);
  VidGetPartitionProperty(*((_QWORD *)this + 91), 393219, (char *)this + 608);
  v5 = (_QWORD *)((char *)this + 600);
  VidGetPartitionProperty(*((_QWORD *)this + 91), 393220, (char *)this + 600);
  v26 = 0;
  v6 = (*(__int64 (__fastcall **)(struct VmRepository *, unsigned int *))(*(_QWORD *)a2 + 288LL))(a2, &v26);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF68,
      (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
      (const char *)(unsigned int)v6,
      v17);
  if ( v26 < 0xB01 && *v5 > 1u )
  {
    VidSetPartitionProperty(*((_QWORD *)this + 91), 393220, 0);
    *v5 = 0;
  }
  *(_OWORD *)((char *)this + 520) = 0;
  *((_QWORD *)this + 67) = 0;
  memset_0(v28, 0, sizeof(v28));
  if ( (unsigned int)VidGetPartitionPropertyEx(*((_QWORD *)this + 91), 589840, 0, v28) && v28[0] )
  {
    LODWORD(phkResult) = *((_DWORD *)this + 224);
    BYTE4(phkResult) = 1;
    v22[0] = (unsigned __int16)GetVmProcessorFeaturesBankCount(phkResult);
    v22[1] = 3;
    v22[2] = v28[0];
    v7 = _std_min_8u(v22, &phkResult);
    for ( i = 0; i < v7; ++i )
      *((_QWORD *)this + i + 65) = *(_QWORD *)&v28[8 * i + 8];
  }
  else
  {
    for ( j = 0; j < 2; ++j )
    {
      if ( !(unsigned int)VidGetPartitionProperty(*((_QWORD *)this + 91), j + 393226, (char *)this + 8 * j + 520) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xFA2,
          (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
          v10);
    }
  }
  VidGetPartitionProperty(*((_QWORD *)this + 91), 327696, (char *)this + 616);
  v11 = (_DWORD *)((char *)this + 632);
  VidGetPartitionProperty(*((_QWORD *)this + 91), 327697, (char *)this + 632);
  v25 = 0;
  if ( (*(int (__fastcall **)(struct VmRepository *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 120LL))(
         a2,
         L"/savedVM/non_architectural_core_sharing",
         &v25) < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(32800) )
      VmlDebugTrace(
        32800,
        L"Warning: Failed to read %s from saved state repository.\n",
        L"/savedVM/non_architectural_core_sharing");
    v16 = 0;
    v25 = 0;
  }
  else
  {
    phkResult = 0;
    Vml::VmRegistryKey::Open(
      &phkResult,
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
      0x20019u);
    v27 = 0;
    if ( (!Vml::VmRegistryKey::QueryValue(
             (Vml::VmRegistryKey *)&phkResult,
             L"IgnoreNonArchitecturalCoreSharingCompatibility",
             &v27)
       || !v27)
      && v25 == 1
      && *(_QWORD *)v11 != 1 )
    {
      v12 = (WCHAR *)Vml::Details::g_ComputerNameResolved;
      if ( !Vml::Details::g_ComputerNameResolved )
      {
        nSize[0] = 16;
        if ( !GetComputerNameExW(ComputerNameNetBIOS, &Vml::Details::g_ComputerName, nSize) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecore\\vm\\common\\vml\\VmComputerName.h",
            v13);
        v12 = &Vml::Details::g_ComputerName;
        Vml::Details::g_ComputerNameResolved = &Vml::Details::g_ComputerName;
      }
      v20 = (__int64)v12;
      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 89) + 16LL) + 8LL))(*((_QWORD *)this + 89) + 16LL);
      *(_QWORD *)nSize = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)this + 89) + 16LL))(*((_QWORD *)this + 89) + 16LL);
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short const *>(
        (struct _EVENT_DESCRIPTOR *)&VMWP_VM_GENERIC_PROCESSOR_FEATURES_NOT_SUPPORTED_ERROR,
        4u,
        (__int64)nSize,
        (__int64)&v19,
        (__int64)&v20);
      LODWORD(v19) = *v11;
      LODWORD(v20) = v25;
      v14 = (WCHAR *)Vml::Details::g_ComputerNameResolved;
      if ( !Vml::Details::g_ComputerNameResolved )
      {
        nSize[0] = 16;
        if ( !GetComputerNameExW(ComputerNameNetBIOS, &Vml::Details::g_ComputerName, nSize) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecore\\vm\\common\\vml\\VmComputerName.h",
            v15);
        v14 = &Vml::Details::g_ComputerName;
        Vml::Details::g_ComputerNameResolved = &Vml::Details::g_ComputerName;
      }
      *(_QWORD *)nSize = v14;
      v21[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 89) + 16LL) + 8LL))(*((_QWORD *)this + 89) + 16LL);
      v21[1] = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)this + 89) + 16LL))(*((_QWORD *)this + 89) + 16LL);
      VmEventWrite<unsigned short const *,unsigned short const *,unsigned short const *,unsigned int,unsigned int>(
        &VMWP_VM_PROCESSOR_CORE_SHARING_NOT_SUPPORTED_ERROR,
        (__int64)v21,
        (__int64)nSize,
        (__int64)&v20,
        (__int64)&v19);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFDD,
        (unsigned int)"onecore\\vm\\worker\\processor\\processormanager.cpp",
        (const char *)0x80004005LL,
        v18);
    }
    Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
    v16 = v25;
  }
  if ( v16 != *(_QWORD *)v11 )
  {
    VidSetPartitionProperty(*((_QWORD *)this + 91), 327697, v16);
    *(_QWORD *)v11 = v25;
  }
}

```

## disassembly

```asm
0x14010ea30  mov     [rsp-8+arg_10], rbx
0x14010ea35  mov     [rsp-8+arg_18], rsi
0x14010ea3a  push    rbp
0x14010ea3b  push    rdi
0x14010ea3c  push    r15
0x14010ea3e  lea     rbp, [rsp-0F90h]
0x14010ea46  mov     eax, 1090h
0x14010ea4b  call    _alloca_probe
0x14010ea50  sub     rsp, rax
0x14010ea53  mov     rax, cs:__security_cookie
0x14010ea5a  xor     rax, rsp
0x14010ea5d  mov     [rbp+0FA0h+var_20], rax
0x14010ea64  mov     rsi, rdx
0x14010ea67  mov     rbx, rcx
0x14010ea6a  mov     [rsp+10A0h+phkResult], 0
0x14010ea73  mov     rax, [rdx]
0x14010ea76  mov     r9d, 8
0x14010ea7c  lea     r8, [rsp+10A0h+phkResult]
0x14010ea81  lea     rdx, ?SAVED_VM_PROCESSOR_INFO_XPATH@@3QBGB; "/savedVM/processor_attribute"
0x14010ea88  mov     rcx, rsi
0x14010ea8b  mov     rax, [rax+58h]
0x14010ea8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010ea94  mov     rcx, [rbp+0FA8h]; this
0x14010ea9b  test    eax, eax
0x14010ea9d  jns     short loc_14010EAB4
0x14010ea9f  mov     r9d, eax; char *
0x14010eaa2  lea     r8, aOnecoreVmWorke_102; "onecore\\vm\\worker\\processor\\process"...
0x14010eaa9  mov     edx, 0F51h; void *
0x14010eaae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14010eab4  mov     rax, [rbx+298h]
0x14010eabb  mov     ecx, [rax]
0x14010eabd  mov     rax, [rsp+10A0h+phkResult]
0x14010eac2  shr     rax, 20h
0x14010eac6  cmp     rcx, rax
0x14010eac9  jnb     short loc_14010EAEA
0x14010eacb  mov     rcx, [rbp+0FA8h]; this
0x14010ead2  mov     r9d, 80004005h; char *
0x14010ead8  lea     r8, aOnecoreVmWorke_102; "onecore\\vm\\worker\\processor\\process"...
0x14010eadf  mov     edx, 0F56h; void *
0x14010eae4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14010eaea  lea     r8, [rbx+260h]
0x14010eaf1  mov     edx, 60003h
0x14010eaf6  mov     rcx, [rbx+2D8h]
0x14010eafd  call    cs:__imp_VidGetPartitionProperty
0x14010eb04  nop     dword ptr [rax+rax+00h]
0x14010eb09  lea     rdi, [rbx+258h]
0x14010eb10  mov     r8, rdi
0x14010eb13  mov     r15d, 60004h
0x14010eb19  mov     edx, r15d
0x14010eb1c  mov     rcx, [rbx+2D8h]
0x14010eb23  call    cs:__imp_VidGetPartitionProperty
0x14010eb2a  nop     dword ptr [rax+rax+00h]
0x14010eb2f  mov     [rbp+0FA0h+var_1010], 0
0x14010eb36  mov     rax, [rsi]
0x14010eb39  lea     rdx, [rbp+0FA0h+var_1010]
0x14010eb3d  mov     rcx, rsi
0x14010eb40  mov     rax, [rax+120h]
0x14010eb47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010eb4c  mov     rcx, [rbp+0FA8h]; this
0x14010eb53  test    eax, eax
0x14010eb55  jns     short loc_14010EB6C
0x14010eb57  mov     r9d, eax; char *
0x14010eb5a  lea     r8, aOnecoreVmWorke_102; "onecore\\vm\\worker\\processor\\process"...
0x14010eb61  mov     edx, 0F68h; void *
0x14010eb66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14010eb6c  cmp     [rbp+0FA0h+var_1010], 0B01h
0x14010eb73  jnb     short loc_14010EB9B
0x14010eb75  cmp     qword ptr [rdi], 1
0x14010eb79  jbe     short loc_14010EB9B
0x14010eb7b  xor     r8d, r8d
0x14010eb7e  mov     rdx, r15
0x14010eb81  mov     rcx, [rbx+2D8h]
0x14010eb88  call    cs:__imp_VidSetPartitionProperty
0x14010eb8f  nop     dword ptr [rax+rax+00h]
0x14010eb94  mov     qword ptr [rdi], 0
0x14010eb9b  xorps   xmm0, xmm0
0x14010eb9e  xor     eax, eax
0x14010eba0  movups  xmmword ptr [rbx+208h], xmm0
0x14010eba7  mov     [rbx+218h], rax
0x14010ebae  mov     edi, 0FE8h
0x14010ebb3  mov     r8d, edi; Size
0x14010ebb6  xor     edx, edx; Val
0x14010ebb8  lea     rcx, [rbp+0FA0h+var_1008]; void *
0x14010ebbc  call    memset_0
0x14010ebc1  mov     dword ptr [rsp+10A0h+var_1080], edi
0x14010ebc5  lea     r9, [rbp+0FA0h+var_1008]
0x14010ebc9  xor     r8d, r8d
0x14010ebcc  mov     edx, 90010h
0x14010ebd1  mov     rcx, [rbx+2D8h]
0x14010ebd8  call    cs:__imp_VidGetPartitionPropertyEx
0x14010ebdf  nop     dword ptr [rax+rax+00h]
0x14010ebe4  test    eax, eax
0x14010ebe6  jz      short loc_14010EC55
0x14010ebe8  cmp     [rbp+0FA0h+var_1008], 0
0x14010ebec  jz      short loc_14010EC55
0x14010ebee  mov     eax, [rbx+380h]
0x14010ebf4  mov     dword ptr [rsp+10A0h+phkResult], eax
0x14010ebf8  mov     byte ptr [rsp+10A0h+phkResult+4], 1
0x14010ebfd  mov     rcx, [rsp+10A0h+phkResult]
0x14010ec02  call    ?GetVmProcessorFeaturesBankCount@@YAGV?$optional@I@std@@@Z; GetVmProcessorFeaturesBankCount(std::optional<uint>)
0x14010ec07  movzx   eax, ax
0x14010ec0a  mov     [rsp+10A0h+var_1040], rax
0x14010ec0f  mov     [rsp+10A0h+var_1038], 3
0x14010ec18  movzx   eax, [rbp+0FA0h+var_1008]
0x14010ec1c  mov     [rsp+10A0h+var_1030], rax
0x14010ec21  lea     rdx, [rsp+10A0h+phkResult]
0x14010ec26  lea     rcx, [rsp+10A0h+var_1040]
0x14010ec2b  call    __std_min_8u
0x14010ec30  xor     r8d, r8d
0x14010ec33  test    rax, rax
0x14010ec36  jz      short loc_14010EC94
0x14010ec38  movsxd  rdx, r8d
0x14010ec3b  mov     rcx, [rbp+rdx*8+0FA0h+var_1000]
0x14010ec40  mov     [rbx+rdx*8+208h], rcx
0x14010ec48  inc     r8d
0x14010ec4b  movsxd  rcx, r8d
0x14010ec4e  cmp     rcx, rax
0x14010ec51  jb      short loc_14010EC38
0x14010ec53  jmp     short loc_14010EC94
0x14010ec55  xor     edi, edi
0x14010ec57  movsxd  r8, edi
0x14010ec5a  add     r8, 41h ; 'A'
0x14010ec5e  lea     r8, [rbx+r8*8]
0x14010ec62  lea     eax, [rdi+6000Ah]
0x14010ec68  movsxd  rdx, eax
0x14010ec6b  mov     rcx, [rbx+2D8h]
0x14010ec72  call    cs:__imp_VidGetPartitionProperty
0x14010ec79  nop     dword ptr [rax+rax+00h]
0x14010ec7e  mov     rcx, [rbp+0FA8h]; this
0x14010ec85  test    eax, eax
0x14010ec87  jz      loc_14010EF94
0x14010ec8d  inc     edi
0x14010ec8f  cmp     edi, 2
0x14010ec92  jl      short loc_14010EC57
0x14010ec94  lea     r8, [rbx+268h]
0x14010ec9b  mov     edx, 50010h
0x14010eca0  mov     rcx, [rbx+2D8h]
0x14010eca7  call    cs:__imp_VidGetPartitionProperty
0x14010ecae  nop     dword ptr [rax+rax+00h]
0x14010ecb3  lea     rdi, [rbx+278h]
0x14010ecba  mov     r8, rdi
0x14010ecbd  mov     r15d, 50011h
0x14010ecc3  mov     edx, r15d
0x14010ecc6  mov     rcx, [rbx+2D8h]
0x14010eccd  call    cs:__imp_VidGetPartitionProperty
0x14010ecd4  nop     dword ptr [rax+rax+00h]
0x14010ecd9  mov     [rbp+0FA0h+var_1018], 0
0x14010ece1  mov     rax, [rsi]
0x14010ece4  lea     r8, [rbp+0FA0h+var_1018]
0x14010ece8  lea     rdx, ?SAVED_VM_NON_ARCHITECURAL_CORE_SHARING_XPATH@@3QBGB; "/savedVM/non_architectural_core_sharing"
0x14010ecef  mov     rcx, rsi
0x14010ecf2  mov     rax, [rax+78h]
0x14010ecf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010ecfb  test    eax, eax
0x14010ecfd  js      loc_14010EF1E
0x14010ed03  mov     [rsp+10A0h+phkResult], 0
0x14010ed0c  mov     r9d, 20019h; unsigned int
0x14010ed12  lea     r8, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14010ed19  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14010ed20  lea     rcx, [rsp+10A0h+phkResult]; phkResult
0x14010ed25  call    ?Open@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGK@Z; Vml::VmRegistryKey::Open(HKEY__ *,ushort const *,ulong)
0x14010ed2a  mov     [rbp+0FA0h+var_100C], 0
0x14010ed31  lea     r8, [rbp+0FA0h+var_100C]; unsigned int *
0x14010ed35  lea     rdx, ?IGNORE_NON_ARCHITECURAL_CORE_SHARING_COMPATIBILITY@@3QBGB; "IgnoreNonArchitecturalCoreSharingCompat"...
0x14010ed3c  lea     rcx, [rsp+10A0h+phkResult]; this
0x14010ed41  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x14010ed46  test    eax, eax
0x14010ed48  jz      short loc_14010ED54
0x14010ed4a  cmp     [rbp+0FA0h+var_100C], 0
0x14010ed4e  jnz     loc_14010EF0E
0x14010ed54  cmp     [rbp+0FA0h+var_1018], 1
0x14010ed59  jnz     loc_14010EF0E
0x14010ed5f  cmp     qword ptr [rdi], 1
0x14010ed63  jz      loc_14010EF0E
0x14010ed69  mov     r15d, 10h
0x14010ed6f  lea     rsi, ?g_ComputerName@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ComputerName
0x14010ed76  mov     rax, cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ComputerNameResolved
0x14010ed7d  test    rax, rax
0x14010ed80  jnz     short loc_14010EDC0
0x14010ed82  mov     [rbp+0FA0h+nSize], r15d
0x14010ed86  lea     r8, [rbp+0FA0h+nSize]; nSize
0x14010ed8a  mov     rdx, rsi; lpBuffer
0x14010ed8d  xor     ecx, ecx; NameType
0x14010ed8f  call    cs:__imp_GetComputerNameExW
0x14010ed96  nop     dword ptr [rax+rax+00h]
0x14010ed9b  test    eax, eax
0x14010ed9d  jnz     short loc_14010EDB6
0x14010ed9f  mov     rcx, [rbp+0FA8h]; this
0x14010eda6  lea     r8, aOnecoreVmCommo_76; "onecore\\vm\\common\\vml\\VmComputerNam"...
0x14010edad  lea     edx, [rax+44h]; void *
0x14010edb0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14010edb6  mov     rax, rsi
0x14010edb9  mov     cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ComputerNameResolved
0x14010edc0  mov     [rsp+10A0h+var_1058], rax
0x14010edc5  mov     rcx, [rbx+2C8h]
0x14010edcc  add     rcx, r15
0x14010edcf  mov     rax, [rcx]
0x14010edd2  mov     rax, [rax+8]
0x14010edd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010eddb  mov     [rsp+10A0h+var_1060], rax
0x14010ede0  mov     rcx, [rbx+2C8h]
0x14010ede7  add     rcx, r15
0x14010edea  mov     rax, [rcx]
0x14010eded  mov     rax, [rax]
0x14010edf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010edf5  mov     qword ptr [rbp+0FA0h+nSize], rax
0x14010edf9  lea     rax, [rsp+10A0h+var_1058]
0x14010edfe  mov     [rsp+10A0h+var_1070], rax; __int64
0x14010ee03  lea     rax, [rsp+10A0h+var_1060]
0x14010ee08  mov     [rsp+10A0h+var_1078], rax; __int64
0x14010ee0d  lea     rax, [rbp+0FA0h+nSize]
0x14010ee11  mov     [rsp+10A0h+var_1080], rax; __int64
0x14010ee16  mov     edx, 4; unsigned int
0x14010ee1b  lea     rcx, VMWP_VM_GENERIC_PROCESSOR_FEATURES_NOT_SUPPORTED_ERROR; struct _EVENT_DESCRIPTOR *
0x14010ee22  call    ??$VmEventWriteAndReport@PEBGPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG33@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort const * &&)
0x14010ee27  mov     eax, [rdi]
0x14010ee29  mov     dword ptr [rsp+10A0h+var_1060], eax
0x14010ee2d  mov     eax, dword ptr [rbp+0FA0h+var_1018]
0x14010ee30  mov     dword ptr [rsp+10A0h+var_1058], eax
0x14010ee34  mov     rax, cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ComputerNameResolved
0x14010ee3b  test    rax, rax
0x14010ee3e  jnz     short loc_14010EE7E
0x14010ee40  mov     [rbp+0FA0h+nSize], r15d
0x14010ee44  lea     r8, [rbp+0FA0h+nSize]; nSize
0x14010ee48  mov     rdx, rsi; lpBuffer
0x14010ee4b  xor     ecx, ecx; NameType
0x14010ee4d  call    cs:__imp_GetComputerNameExW
0x14010ee54  nop     dword ptr [rax+rax+00h]
0x14010ee59  test    eax, eax
0x14010ee5b  jnz     short loc_14010EE74
0x14010ee5d  mov     rcx, [rbp+0FA8h]; this
0x14010ee64  lea     r8, aOnecoreVmCommo_76; "onecore\\vm\\common\\vml\\VmComputerNam"...
0x14010ee6b  lea     edx, [rax+44h]; void *
0x14010ee6e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14010ee74  mov     rax, rsi
0x14010ee77  mov     cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ComputerNameResolved
0x14010ee7e  mov     qword ptr [rbp+0FA0h+nSize], rax
0x14010ee82  mov     rcx, [rbx+2C8h]
0x14010ee89  add     rcx, r15
0x14010ee8c  mov     rax, [rcx]
0x14010ee8f  mov     rax, [rax+8]
0x14010ee93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010ee98  mov     [rsp+10A0h+var_1050], rax
0x14010ee9d  mov     rcx, [rbx+2C8h]
0x14010eea4  add     rcx, r15
0x14010eea7  mov     rax, [rcx]
0x14010eeaa  mov     rax, [rax]
0x14010eead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010eeb2  mov     [rsp+10A0h+var_1048], rax
0x14010eeb7  lea     rax, [rsp+10A0h+var_1060]
0x14010eebc  mov     [rsp+10A0h+var_1068], rax; __int64
0x14010eec1  lea     rax, [rsp+10A0h+var_1058]
0x14010eec6  mov     [rsp+10A0h+var_1070], rax; __int64
0x14010eecb  lea     rax, [rbp+0FA0h+nSize]
0x14010eecf  mov     [rsp+10A0h+var_1078], rax; __int64
0x14010eed4  lea     rax, [rsp+10A0h+var_1050]
0x14010eed9  mov     [rsp+10A0h+var_1080], rax; int
0x14010eede  lea     r9, [rsp+10A0h+var_1048]
0x14010eee3  lea     rcx, VMWP_VM_PROCESSOR_CORE_SHARING_NOT_SUPPORTED_ERROR; EventDescriptor
0x14010eeea  call    ??$VmEventWrite@PEBGPEBGPEBGII@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG22$$QEAI3@Z; VmEventWrite<ushort const *,ushort const *,ushort const *,uint,uint>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&,ushort const * &&,uint &&,uint &&)
0x14010eeef  mov     rcx, [rbp+0FA8h]; this
0x14010eef6  mov     r9d, 80004005h; char *
0x14010eefc  lea     r8, aOnecoreVmWorke_102; "onecore\\vm\\worker\\processor\\process"...
0x14010ef03  mov     edx, 0FDDh; void *
0x14010ef08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14010ef0e  lea     rcx, [rsp+10A0h+phkResult]; this
0x14010ef13  call    ?Close@VmRegistryKey@Vml@@QEAAXXZ; Vml::VmRegistryKey::Close(void)
0x14010ef18  mov     r8, [rbp+0FA0h+var_1018]
0x14010ef1c  jmp     short loc_14010EF4A
0x14010ef1e  mov     esi, 8020h
0x14010ef23  mov     ecx, esi
0x14010ef25  call    VmlIsDebugTraceEnabled
0x14010ef2a  test    eax, eax
0x14010ef2c  jz      short loc_14010EF43
0x14010ef2e  lea     r8, ?SAVED_VM_NON_ARCHITECURAL_CORE_SHARING_XPATH@@3QBGB; "/savedVM/non_architectural_core_sharing"
0x14010ef35  lea     rdx, aWarningFailedT; "Warning: Failed to read %s from saved s"...
0x14010ef3c  mov     ecx, esi
0x14010ef3e  call    VmlDebugTrace
0x14010ef43  xor     r8d, r8d
0x14010ef46  mov     [rbp+0FA0h+var_1018], r8
0x14010ef4a  cmp     r8, [rdi]
0x14010ef4d  jz      short loc_14010EF6C
0x14010ef4f  mov     rdx, r15
0x14010ef52  mov     rcx, [rbx+2D8h]
0x14010ef59  call    cs:__imp_VidSetPartitionProperty
0x14010ef60  nop     dword ptr [rax+rax+00h]
0x14010ef65  mov     rax, [rbp+0FA0h+var_1018]
0x14010ef69  mov     [rdi], rax
0x14010ef6c  mov     rcx, [rbp+0FA0h+var_20]
0x14010ef73  xor     rcx, rsp; StackCookie
0x14010ef76  call    __security_check_cookie
0x14010ef7b  lea     r11, [rsp+10A0h+var_10]
0x14010ef83  mov     rbx, [r11+30h]
0x14010ef87  mov     rsi, [r11+38h]
0x14010ef8b  mov     rsp, r11
0x14010ef8e  pop     r15
0x14010ef90  pop     rdi
0x14010ef91  pop     rbp
0x14010ef92  retn
0x14010ef94  lea     r8, aOnecoreVmWorke_102; "onecore\\vm\\worker\\processor\\process"...
  ... truncated ...
```
