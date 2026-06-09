# ProcessorManager::Restore(VmRepository *)

- ea: `0x14011e470`
- end: `0x14011e9e6`
- name: `?Restore@ProcessorManager@@UEAAXPEAVVmRepository@@@Z`
- size: `1398`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct VmRepository *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140042260`
- `0x140054a90`
- `0x14005600c`
- `0x14005b648`
- `0x14006af58`
- `0x1400996d8`
- `0x1400c5a3c`
- `0x14011e470`
- `0x14011fbbc`
- `0x14011fd54`
- `0x140127990`
- `0x140132960`
- `0x14013361c`
- `0x1401356c0`
- `0x140299850`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14011e7cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14011e88d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14011e7cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x14011e88d`
- `vid!VidSetPartitionProperty` at `0x14011e5c8`
- `vid!VidSetPartitionProperty` at `0x14011e999`
- `vid!VidSetPartitionProperty` at `0x14011e5c8`
- `vid!VidSetPartitionProperty` at `0x14011e999`
- `vid!VidGetPartitionPropertyEx` at `0x14011e618`
- `vid!VidGetPartitionPropertyEx` at `0x14011e618`
- `vid!VidGetPartitionProperty` at `0x14011e53d`
- `vid!VidGetPartitionProperty` at `0x14011e563`
- `vid!VidGetPartitionProperty` at `0x14011e6b2`
- `vid!VidGetPartitionProperty` at `0x14011e6e7`
- `vid!VidGetPartitionProperty` at `0x14011e70d`
- `vid!VidGetPartitionProperty` at `0x14011e53d`
- `vid!VidGetPartitionProperty` at `0x14011e563`
- `vid!VidGetPartitionProperty` at `0x14011e6b2`
- `vid!VidGetPartitionProperty` at `0x14011e6e7`
- `vid!VidGetPartitionProperty` at `0x14011e70d`

## string_xrefs

- `0x14011e7e6`: `onecore\vm\common\vml\VmComputerName.h`
- `0x14011e8a4`: `onecore\vm\common\vml\VmComputerName.h`
- `0x14011e775`: `IgnoreNonArchitecturalCoreSharingCompatibility`
- `0x14011e975`: `Warning: Failed to read %s from saved state repository.\n`

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
0x14011e470  mov     [rsp-8+arg_10], rbx
0x14011e475  mov     [rsp-8+arg_18], rsi
0x14011e47a  push    rbp
0x14011e47b  push    rdi
0x14011e47c  push    r15
0x14011e47e  lea     rbp, [rsp-0F90h]
0x14011e486  mov     eax, 1090h
0x14011e48b  call    _alloca_probe
0x14011e490  sub     rsp, rax
0x14011e493  mov     rax, cs:__security_cookie
0x14011e49a  xor     rax, rsp
0x14011e49d  mov     [rbp+0FA0h+var_20], rax
0x14011e4a4  mov     rsi, rdx
0x14011e4a7  mov     rbx, rcx
0x14011e4aa  mov     [rsp+10A0h+phkResult], 0
0x14011e4b3  mov     rax, [rdx]
0x14011e4b6  mov     r9d, 8
0x14011e4bc  lea     r8, [rsp+10A0h+phkResult]
0x14011e4c1  lea     rdx, ?SAVED_VM_PROCESSOR_INFO_XPATH@@3QBGB; "/savedVM/processor_attribute"
0x14011e4c8  mov     rcx, rsi
0x14011e4cb  mov     rax, [rax+58h]
0x14011e4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e4d4  mov     rcx, [rbp+0FA8h]; this
0x14011e4db  test    eax, eax
0x14011e4dd  jns     short loc_14011E4F4
0x14011e4df  mov     r9d, eax; char *
0x14011e4e2  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
0x14011e4e9  mov     edx, 0F51h; void *
0x14011e4ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14011e4f4  mov     rax, [rbx+298h]
0x14011e4fb  mov     ecx, [rax]
0x14011e4fd  mov     rax, [rsp+10A0h+phkResult]
0x14011e502  shr     rax, 20h
0x14011e506  cmp     rcx, rax
0x14011e509  jnb     short loc_14011E52A
0x14011e50b  mov     rcx, [rbp+0FA8h]; this
0x14011e512  mov     r9d, 80004005h; char *
0x14011e518  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
0x14011e51f  mov     edx, 0F56h; void *
0x14011e524  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14011e52a  lea     r8, [rbx+260h]
0x14011e531  mov     edx, 60003h
0x14011e536  mov     rcx, [rbx+2D8h]
0x14011e53d  call    cs:__imp_VidGetPartitionProperty
0x14011e544  nop     dword ptr [rax+rax+00h]
0x14011e549  lea     rdi, [rbx+258h]
0x14011e550  mov     r8, rdi
0x14011e553  mov     r15d, 60004h
0x14011e559  mov     edx, r15d
0x14011e55c  mov     rcx, [rbx+2D8h]
0x14011e563  call    cs:__imp_VidGetPartitionProperty
0x14011e56a  nop     dword ptr [rax+rax+00h]
0x14011e56f  mov     [rbp+0FA0h+var_1010], 0
0x14011e576  mov     rax, [rsi]
0x14011e579  lea     rdx, [rbp+0FA0h+var_1010]
0x14011e57d  mov     rcx, rsi
0x14011e580  mov     rax, [rax+120h]
0x14011e587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e58c  mov     rcx, [rbp+0FA8h]; this
0x14011e593  test    eax, eax
0x14011e595  jns     short loc_14011E5AC
0x14011e597  mov     r9d, eax; char *
0x14011e59a  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
0x14011e5a1  mov     edx, 0F68h; void *
0x14011e5a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14011e5ac  cmp     [rbp+0FA0h+var_1010], 0B01h
0x14011e5b3  jnb     short loc_14011E5DB
0x14011e5b5  cmp     qword ptr [rdi], 1
0x14011e5b9  jbe     short loc_14011E5DB
0x14011e5bb  xor     r8d, r8d
0x14011e5be  mov     rdx, r15
0x14011e5c1  mov     rcx, [rbx+2D8h]
0x14011e5c8  call    cs:__imp_VidSetPartitionProperty
0x14011e5cf  nop     dword ptr [rax+rax+00h]
0x14011e5d4  mov     qword ptr [rdi], 0
0x14011e5db  xorps   xmm0, xmm0
0x14011e5de  xor     eax, eax
0x14011e5e0  movups  xmmword ptr [rbx+208h], xmm0
0x14011e5e7  mov     [rbx+218h], rax
0x14011e5ee  mov     edi, 0FE8h
0x14011e5f3  mov     r8d, edi; Size
0x14011e5f6  xor     edx, edx; Val
0x14011e5f8  lea     rcx, [rbp+0FA0h+var_1008]; void *
0x14011e5fc  call    memset_0
0x14011e601  mov     dword ptr [rsp+10A0h+var_1080], edi
0x14011e605  lea     r9, [rbp+0FA0h+var_1008]
0x14011e609  xor     r8d, r8d
0x14011e60c  mov     edx, 90010h
0x14011e611  mov     rcx, [rbx+2D8h]
0x14011e618  call    cs:__imp_VidGetPartitionPropertyEx
0x14011e61f  nop     dword ptr [rax+rax+00h]
0x14011e624  test    eax, eax
0x14011e626  jz      short loc_14011E695
0x14011e628  cmp     [rbp+0FA0h+var_1008], 0
0x14011e62c  jz      short loc_14011E695
0x14011e62e  mov     eax, [rbx+380h]
0x14011e634  mov     dword ptr [rsp+10A0h+phkResult], eax
0x14011e638  mov     byte ptr [rsp+10A0h+phkResult+4], 1
0x14011e63d  mov     rcx, [rsp+10A0h+phkResult]
0x14011e642  call    ?GetVmProcessorFeaturesBankCount@@YAGV?$optional@I@std@@@Z; GetVmProcessorFeaturesBankCount(std::optional<uint>)
0x14011e647  movzx   eax, ax
0x14011e64a  mov     [rsp+10A0h+var_1040], rax
0x14011e64f  mov     [rsp+10A0h+var_1038], 3
0x14011e658  movzx   eax, [rbp+0FA0h+var_1008]
0x14011e65c  mov     [rsp+10A0h+var_1030], rax
0x14011e661  lea     rdx, [rsp+10A0h+phkResult]
0x14011e666  lea     rcx, [rsp+10A0h+var_1040]
0x14011e66b  call    __std_min_8u
0x14011e670  xor     r8d, r8d
0x14011e673  test    rax, rax
0x14011e676  jz      short loc_14011E6D4
0x14011e678  movsxd  rdx, r8d
0x14011e67b  mov     rcx, [rbp+rdx*8+0FA0h+var_1000]
0x14011e680  mov     [rbx+rdx*8+208h], rcx
0x14011e688  inc     r8d
0x14011e68b  movsxd  rcx, r8d
0x14011e68e  cmp     rcx, rax
0x14011e691  jb      short loc_14011E678
0x14011e693  jmp     short loc_14011E6D4
0x14011e695  xor     edi, edi
0x14011e697  movsxd  r8, edi
0x14011e69a  add     r8, 41h ; 'A'
0x14011e69e  lea     r8, [rbx+r8*8]
0x14011e6a2  lea     eax, [rdi+6000Ah]
0x14011e6a8  movsxd  rdx, eax
0x14011e6ab  mov     rcx, [rbx+2D8h]
0x14011e6b2  call    cs:__imp_VidGetPartitionProperty
0x14011e6b9  nop     dword ptr [rax+rax+00h]
0x14011e6be  mov     rcx, [rbp+0FA8h]; this
0x14011e6c5  test    eax, eax
0x14011e6c7  jz      loc_14011E9D4
0x14011e6cd  inc     edi
0x14011e6cf  cmp     edi, 2
0x14011e6d2  jl      short loc_14011E697
0x14011e6d4  lea     r8, [rbx+268h]
0x14011e6db  mov     edx, 50010h
0x14011e6e0  mov     rcx, [rbx+2D8h]
0x14011e6e7  call    cs:__imp_VidGetPartitionProperty
0x14011e6ee  nop     dword ptr [rax+rax+00h]
0x14011e6f3  lea     rdi, [rbx+278h]
0x14011e6fa  mov     r8, rdi
0x14011e6fd  mov     r15d, 50011h
0x14011e703  mov     edx, r15d
0x14011e706  mov     rcx, [rbx+2D8h]
0x14011e70d  call    cs:__imp_VidGetPartitionProperty
0x14011e714  nop     dword ptr [rax+rax+00h]
0x14011e719  mov     [rbp+0FA0h+var_1018], 0
0x14011e721  mov     rax, [rsi]
0x14011e724  lea     r8, [rbp+0FA0h+var_1018]
0x14011e728  lea     rdx, ?SAVED_VM_NON_ARCHITECURAL_CORE_SHARING_XPATH@@3QBGB; "/savedVM/non_architectural_core_sharing"
0x14011e72f  mov     rcx, rsi
0x14011e732  mov     rax, [rax+78h]
0x14011e736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e73b  test    eax, eax
0x14011e73d  js      loc_14011E95E
0x14011e743  mov     [rsp+10A0h+phkResult], 0
0x14011e74c  mov     r9d, 20019h; unsigned int
0x14011e752  lea     r8, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14011e759  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14011e760  lea     rcx, [rsp+10A0h+phkResult]; phkResult
0x14011e765  call    ?Open@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGK@Z; Vml::VmRegistryKey::Open(HKEY__ *,ushort const *,ulong)
0x14011e76a  mov     [rbp+0FA0h+var_100C], 0
0x14011e771  lea     r8, [rbp+0FA0h+var_100C]; unsigned int *
0x14011e775  lea     rdx, ?IGNORE_NON_ARCHITECURAL_CORE_SHARING_COMPATIBILITY@@3QBGB; "IgnoreNonArchitecturalCoreSharingCompat"...
0x14011e77c  lea     rcx, [rsp+10A0h+phkResult]; this
0x14011e781  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x14011e786  test    eax, eax
0x14011e788  jz      short loc_14011E794
0x14011e78a  cmp     [rbp+0FA0h+var_100C], 0
0x14011e78e  jnz     loc_14011E94E
0x14011e794  cmp     [rbp+0FA0h+var_1018], 1
0x14011e799  jnz     loc_14011E94E
0x14011e79f  cmp     qword ptr [rdi], 1
0x14011e7a3  jz      loc_14011E94E
0x14011e7a9  mov     r15d, 10h
0x14011e7af  lea     rsi, ?g_ComputerName@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ComputerName
0x14011e7b6  mov     rax, cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ComputerNameResolved
0x14011e7bd  test    rax, rax
0x14011e7c0  jnz     short loc_14011E800
0x14011e7c2  mov     [rbp+0FA0h+nSize], r15d
0x14011e7c6  lea     r8, [rbp+0FA0h+nSize]; nSize
0x14011e7ca  mov     rdx, rsi; lpBuffer
0x14011e7cd  xor     ecx, ecx; NameType
0x14011e7cf  call    cs:__imp_GetComputerNameExW
0x14011e7d6  nop     dword ptr [rax+rax+00h]
0x14011e7db  test    eax, eax
0x14011e7dd  jnz     short loc_14011E7F6
0x14011e7df  mov     rcx, [rbp+0FA8h]; this
0x14011e7e6  lea     r8, aOnecoreVmCommo_76; "onecore\\vm\\common\\vml\\VmComputerNam"...
0x14011e7ed  lea     edx, [rax+44h]; void *
0x14011e7f0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011e7f6  mov     rax, rsi
0x14011e7f9  mov     cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ComputerNameResolved
0x14011e800  mov     [rsp+10A0h+var_1058], rax
0x14011e805  mov     rcx, [rbx+2C8h]
0x14011e80c  add     rcx, r15
0x14011e80f  mov     rax, [rcx]
0x14011e812  mov     rax, [rax+8]
0x14011e816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e81b  mov     [rsp+10A0h+var_1060], rax
0x14011e820  mov     rcx, [rbx+2C8h]
0x14011e827  add     rcx, r15
0x14011e82a  mov     rax, [rcx]
0x14011e82d  mov     rax, [rax]
0x14011e830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e835  mov     qword ptr [rbp+0FA0h+nSize], rax
0x14011e839  lea     rax, [rsp+10A0h+var_1058]
0x14011e83e  mov     [rsp+10A0h+var_1070], rax; __int64
0x14011e843  lea     rax, [rsp+10A0h+var_1060]
0x14011e848  mov     [rsp+10A0h+var_1078], rax; __int64
0x14011e84d  lea     rax, [rbp+0FA0h+nSize]
0x14011e851  mov     [rsp+10A0h+var_1080], rax; __int64
0x14011e856  mov     edx, 4; unsigned int
0x14011e85b  lea     rcx, VMWP_VM_GENERIC_PROCESSOR_FEATURES_NOT_SUPPORTED_ERROR; struct _EVENT_DESCRIPTOR *
0x14011e862  call    ??$VmEventWriteAndReport@PEBGPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG33@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort const * &&)
0x14011e867  mov     eax, [rdi]
0x14011e869  mov     dword ptr [rsp+10A0h+var_1060], eax
0x14011e86d  mov     eax, dword ptr [rbp+0FA0h+var_1018]
0x14011e870  mov     dword ptr [rsp+10A0h+var_1058], eax
0x14011e874  mov     rax, cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ComputerNameResolved
0x14011e87b  test    rax, rax
0x14011e87e  jnz     short loc_14011E8BE
0x14011e880  mov     [rbp+0FA0h+nSize], r15d
0x14011e884  lea     r8, [rbp+0FA0h+nSize]; nSize
0x14011e888  mov     rdx, rsi; lpBuffer
0x14011e88b  xor     ecx, ecx; NameType
0x14011e88d  call    cs:__imp_GetComputerNameExW
0x14011e894  nop     dword ptr [rax+rax+00h]
0x14011e899  test    eax, eax
0x14011e89b  jnz     short loc_14011E8B4
0x14011e89d  mov     rcx, [rbp+0FA8h]; this
0x14011e8a4  lea     r8, aOnecoreVmCommo_76; "onecore\\vm\\common\\vml\\VmComputerNam"...
0x14011e8ab  lea     edx, [rax+44h]; void *
0x14011e8ae  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14011e8b4  mov     rax, rsi
0x14011e8b7  mov     cs:?g_ComputerNameResolved@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ComputerNameResolved
0x14011e8be  mov     qword ptr [rbp+0FA0h+nSize], rax
0x14011e8c2  mov     rcx, [rbx+2C8h]
0x14011e8c9  add     rcx, r15
0x14011e8cc  mov     rax, [rcx]
0x14011e8cf  mov     rax, [rax+8]
0x14011e8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e8d8  mov     [rsp+10A0h+var_1050], rax
0x14011e8dd  mov     rcx, [rbx+2C8h]
0x14011e8e4  add     rcx, r15
0x14011e8e7  mov     rax, [rcx]
0x14011e8ea  mov     rax, [rax]
0x14011e8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011e8f2  mov     [rsp+10A0h+var_1048], rax
0x14011e8f7  lea     rax, [rsp+10A0h+var_1060]
0x14011e8fc  mov     [rsp+10A0h+var_1068], rax; __int64
0x14011e901  lea     rax, [rsp+10A0h+var_1058]
0x14011e906  mov     [rsp+10A0h+var_1070], rax; __int64
0x14011e90b  lea     rax, [rbp+0FA0h+nSize]
0x14011e90f  mov     [rsp+10A0h+var_1078], rax; __int64
0x14011e914  lea     rax, [rsp+10A0h+var_1050]
0x14011e919  mov     [rsp+10A0h+var_1080], rax; int
0x14011e91e  lea     r9, [rsp+10A0h+var_1048]
0x14011e923  lea     rcx, VMWP_VM_PROCESSOR_CORE_SHARING_NOT_SUPPORTED_ERROR; EventDescriptor
0x14011e92a  call    ??$VmEventWrite@PEBGPEBGPEBGII@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG22$$QEAI3@Z; VmEventWrite<ushort const *,ushort const *,ushort const *,uint,uint>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&,ushort const * &&,uint &&,uint &&)
0x14011e92f  mov     rcx, [rbp+0FA8h]; this
0x14011e936  mov     r9d, 80004005h; char *
0x14011e93c  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
0x14011e943  mov     edx, 0FDDh; void *
0x14011e948  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14011e94e  lea     rcx, [rsp+10A0h+phkResult]; this
0x14011e953  call    ?Close@VmRegistryKey@Vml@@QEAAXXZ; Vml::VmRegistryKey::Close(void)
0x14011e958  mov     r8, [rbp+0FA0h+var_1018]
0x14011e95c  jmp     short loc_14011E98A
0x14011e95e  mov     esi, 8020h
0x14011e963  mov     ecx, esi
0x14011e965  call    VmlIsDebugTraceEnabled
0x14011e96a  test    eax, eax
0x14011e96c  jz      short loc_14011E983
0x14011e96e  lea     r8, ?SAVED_VM_NON_ARCHITECURAL_CORE_SHARING_XPATH@@3QBGB; "/savedVM/non_architectural_core_sharing"
0x14011e975  lea     rdx, aWarningFailedT; "Warning: Failed to read %s from saved s"...
0x14011e97c  mov     ecx, esi
0x14011e97e  call    VmlDebugTrace
0x14011e983  xor     r8d, r8d
0x14011e986  mov     [rbp+0FA0h+var_1018], r8
0x14011e98a  cmp     r8, [rdi]
0x14011e98d  jz      short loc_14011E9AC
0x14011e98f  mov     rdx, r15
0x14011e992  mov     rcx, [rbx+2D8h]
0x14011e999  call    cs:__imp_VidSetPartitionProperty
0x14011e9a0  nop     dword ptr [rax+rax+00h]
0x14011e9a5  mov     rax, [rbp+0FA0h+var_1018]
0x14011e9a9  mov     [rdi], rax
0x14011e9ac  mov     rcx, [rbp+0FA0h+var_20]
0x14011e9b3  xor     rcx, rsp; StackCookie
0x14011e9b6  call    __security_check_cookie
0x14011e9bb  lea     r11, [rsp+10A0h+var_10]
0x14011e9c3  mov     rbx, [r11+30h]
0x14011e9c7  mov     rsi, [r11+38h]
0x14011e9cb  mov     rsp, r11
0x14011e9ce  pop     r15
0x14011e9d0  pop     rdi
0x14011e9d1  pop     rbp
0x14011e9d2  retn
0x14011e9d4  lea     r8, aOnecoreVmWorke_101; "onecore\\vm\\worker\\processor\\process"...
  ... truncated ...
```
