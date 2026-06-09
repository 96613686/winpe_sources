# ComputeService::ContainerDefinition::GetImcDataFromHive(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x1400a2114`
- end: `0x1400a247c`
- name: `?GetImcDataFromHive@ContainerDefinition@ComputeService@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `872`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14006615c`

## callees

- `0x1400162e8`
- `0x14001d490`
- `0x1400421f0`
- `0x1400451a0`
- `0x140080180`
- `0x140081d80`
- `0x1400a1b94`
- `0x1400a1dcc`
- `0x1400a2114`
- `0x1400a2490`
- `0x1400a2570`
- `0x1400a2894`
- `0x1400a28c0`
- `0x1400a851c`
- `0x1400a867c`
- `0x1400a97c8`
- `0x1400c4154`
- `0x1401332f0`
- `0x14013624c`
- `0x140247e50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400a2269`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400a2269`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400a239b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400a239b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400a23fa`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400a23fa`

## string_xrefs

- `0x1400a2184`: `onecore\base\gendrv\silos\registry\offlinehivelib\offlinehive.cpp`
- `0x1400a21e9`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x1400a228a`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x1400a229f`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x1400a2358`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x1400a237e`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x1400a23b2`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x1400a2411`: `onecore\vm\compute\shared\container\registrychanges.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ComputeService::ContainerDefinition::GetImcDataFromHive(__int64 a1, HANDLE *a2)
{
  HANDLE v4; // rbx
  __int64 v5; // r8
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // esi
  void *v9; // r15
  unsigned int i; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rdx
  const char *v16; // r9
  const char *v17; // r9
  unsigned int lpOverlapped; // [rsp+20h] [rbp-E0h]
  unsigned int lpOverlappeda; // [rsp+20h] [rbp-E0h]
  unsigned int lpOverlappedb; // [rsp+20h] [rbp-E0h]
  unsigned int lpOverlappedc; // [rsp+20h] [rbp-E0h]
  _BYTE *v23; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v24[4]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[32]; // [rsp+78h] [rbp-88h] BYREF
  char v26[32]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR v27[16]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+D8h] [rbp-28h] BYREF
  char v29; // [rsp+E0h] [rbp-20h]
  DWORD NumberOfBytesRead; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v31; // [rsp+F0h] [rbp-10h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID lpBuffer[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v34; // [rsp+110h] [rbp+10h]
  _BYTE v35[176]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v31 = a1;
  v4 = *a2;
  std::wstring::wstring(v27);
  v28 = 0;
  v29 = 0;
  v6 = OROpenHiveInternal(v4, 0, v5, &v28);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x81C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\registry\\offlinehivelib\\offlinehive.cpp",
      (const char *)v6,
      lpOverlapped);
  LODWORD(v23) = 0;
  v24[0] = 0;
  v7 = ORQueryInfoKey(v28, 0, 0, (unsigned int)&v23, (__int64)v24, 0, 0, 0, 0, 0, 0);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
      (const char *)v7,
      lpOverlappeda);
  v8 = v24[0] + 1;
  v9 = operator new[](saturated_mul(v24[0] + 1, 2u));
  v31 = (__int64)v9;
  for ( i = 0; i < (unsigned int)v23; ++i )
  {
    v24[0] = v8;
    v11 = OREnumKey(v28, i, (_DWORD)v9, (unsigned int)v24, 0, 0, 0);
    if ( v11 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x149,
        (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
        (const char *)v11,
        lpOverlappedb);
    if ( (unsigned int)_o__wcsicmp(v9, L"SYSTEM") )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
        (const char *)0xD,
        lpOverlappedb);
  }
  LODWORD(v23) = 0;
  v12 = ORGetValue(v28, 0, (unsigned int)L"Sequence", (unsigned int)&v23, 0, 0);
  if ( v12 == 2 )
  {
    v23 = v25;
    v13 = std::wstring::wstring(v25, L"Sequence");
    v14 = std::wstring::wstring(v26, &szPassword);
    ComputeService::ContainerDefinition::make_registry_value(v35, v15, v14, v13, 2);
    ComputeService::ContainerDefinition::Details::ApplyValueToOfflineHive(v27, v35, 0);
    ComputeService::ContainerDefinition::Details::ConvertOfflineHiveToBytes(a1, v27);
    Schema::Registry::RegistryValue::~RegistryValue((Schema::Registry::RegistryValue *)v35);
  }
  else
  {
    if ( v12 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
        (const char *)v12,
        lpOverlappedc);
    if ( (_DWORD)v23 != 4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
        (const char *)0xD,
        lpOverlappedc);
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(*a2, &FileSize) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x16A,
        (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
        v16);
    *(_OWORD *)lpBuffer = 0;
    v34 = 0;
    ((void (__fastcall *)(_QWORD, _QWORD))std::vector<unsigned char>::vector<unsigned char>)(
      lpBuffer,
      (union _LARGE_INTEGER)FileSize.QuadPart);
    NumberOfBytesRead = 0;
    if ( !ReadFile(*a2, lpBuffer[0], LODWORD(lpBuffer[1]) - LODWORD(lpBuffer[0]), &NumberOfBytesRead, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
        v17);
    std::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor>::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor>(
      a1,
      lpBuffer);
    std::vector<unsigned char>::_Tidy(lpBuffer);
  }
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v31);
  OfflineHiveLib::OfflineHive::~OfflineHive((OfflineHiveLib::OfflineHive *)v27);
  return a1;
}

```

## disassembly

```asm
0x1400a2114  mov     [rsp-8+arg_10], rbx
0x1400a2119  mov     [rsp-8+arg_18], rsi
0x1400a211e  push    rbp
0x1400a211f  push    rdi
0x1400a2120  push    r12
0x1400a2122  push    r14
0x1400a2124  push    r15
0x1400a2126  lea     rbp, [rsp-0E0h]
0x1400a212e  sub     rsp, 1E0h
0x1400a2135  mov     rax, cs:__security_cookie
0x1400a213c  xor     rax, rsp
0x1400a213f  mov     [rbp+100h+var_30], rax
0x1400a2146  mov     r14, rdx
0x1400a2149  mov     rdi, rcx
0x1400a214c  mov     [rbp+100h+var_110], rcx
0x1400a2150  xor     r12d, r12d
0x1400a2153  mov     rbx, [rdx]
0x1400a2156  lea     rcx, [rbp+100h+var_148]; void *
0x1400a215a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400a215f  nop
0x1400a2160  mov     [rbp+100h+var_128], r12
0x1400a2164  mov     [rbp+100h+var_120], r12b
0x1400a2168  lea     r9, [rbp+100h+var_128]
0x1400a216c  xor     edx, edx
0x1400a216e  mov     rcx, rbx
0x1400a2171  call    OROpenHiveInternal
0x1400a2176  mov     rcx, [rbp+108h]; this
0x1400a217d  test    eax, eax
0x1400a217f  jz      short loc_1400A2196
0x1400a2181  mov     r9d, eax; char *
0x1400a2184  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\registry"...
0x1400a218b  mov     edx, 81Ch; void *
0x1400a2190  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a2196  mov     dword ptr [rsp+200h+var_1A0], r12d
0x1400a219b  mov     [rsp+200h+var_198], r12d
0x1400a21a0  mov     [rsp+200h+var_1B0], r12
0x1400a21a5  mov     [rsp+200h+var_1B8], r12
0x1400a21aa  mov     [rsp+200h+var_1C0], r12
0x1400a21af  mov     [rsp+200h+var_1C8], r12
0x1400a21b4  mov     [rsp+200h+var_1D0], r12
0x1400a21b9  mov     [rsp+200h+var_1D8], r12
0x1400a21be  lea     rax, [rsp+200h+var_198]
0x1400a21c3  mov     [rsp+200h+lpOverlapped], rax; unsigned int
0x1400a21c8  lea     r9, [rsp+200h+var_1A0]
0x1400a21cd  xor     r8d, r8d
0x1400a21d0  xor     edx, edx
0x1400a21d2  mov     rcx, [rbp+100h+var_128]
0x1400a21d6  call    ORQueryInfoKey
0x1400a21db  mov     rcx, [rbp+108h]; this
0x1400a21e2  test    eax, eax
0x1400a21e4  jz      short loc_1400A21FB
0x1400a21e6  mov     r9d, eax; char *
0x1400a21e9  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a21f0  mov     edx, 136h; void *
0x1400a21f5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a21fb  mov     esi, [rsp+200h+var_198]
0x1400a21ff  inc     esi
0x1400a2201  mov     ecx, esi
0x1400a2203  mov     eax, 2
0x1400a2208  mul     rcx
0x1400a220b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400a2212  cmovb   rax, rcx
0x1400a2216  mov     rcx, rax; unsigned __int64
0x1400a2219  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400a221e  mov     r15, rax
0x1400a2221  mov     [rbp+100h+var_110], rax
0x1400a2225  mov     ebx, r12d
0x1400a2228  mov     rcx, [rbp+100h+var_128]
0x1400a222c  cmp     ebx, dword ptr [rsp+200h+var_1A0]
0x1400a2230  jnb     short loc_1400A22B1
0x1400a2232  mov     [rsp+200h+var_198], esi
0x1400a2236  mov     [rsp+200h+var_1D0], r12
0x1400a223b  mov     [rsp+200h+var_1D8], r12
0x1400a2240  mov     [rsp+200h+lpOverlapped], r12; unsigned int
0x1400a2245  lea     r9, [rsp+200h+var_198]
0x1400a224a  mov     r8, r15
0x1400a224d  mov     edx, ebx
0x1400a224f  call    OREnumKey
0x1400a2254  mov     rcx, [rbp+108h]; this
0x1400a225b  test    eax, eax
0x1400a225d  jnz     short loc_1400A229C
0x1400a225f  lea     rdx, aSystem_0; "SYSTEM"
0x1400a2266  mov     rcx, r15
0x1400a2269  call    cs:__imp__o__wcsicmp
0x1400a2270  nop     dword ptr [rax+rax+00h]
0x1400a2275  test    eax, eax
0x1400a2277  jnz     short loc_1400A227D
0x1400a2279  inc     ebx
0x1400a227b  jmp     short loc_1400A2228
0x1400a227d  mov     rcx, [rbp+108h]; this
0x1400a2284  mov     r9d, 0Dh; char *
0x1400a228a  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a2291  mov     edx, 14Dh; void *
0x1400a2296  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a229c  mov     r9d, eax; char *
0x1400a229f  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a22a6  mov     edx, 149h; void *
0x1400a22ab  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a22b1  mov     dword ptr [rsp+200h+var_1A0], r12d
0x1400a22b6  mov     [rsp+200h+var_1D8], r12
0x1400a22bb  mov     [rsp+200h+lpOverlapped], r12; unsigned int
0x1400a22c0  lea     r9, [rsp+200h+var_1A0]
0x1400a22c5  lea     r8, aSequence; "Sequence"
0x1400a22cc  xor     edx, edx
0x1400a22ce  call    ORGetValue
0x1400a22d3  cmp     eax, 2
0x1400a22d6  jnz     short loc_1400A234A
0x1400a22d8  lea     rax, [rsp+200h+var_188]
0x1400a22dd  mov     [rsp+200h+var_1A0], rax
0x1400a22e2  lea     rdx, aSequence; "Sequence"
0x1400a22e9  lea     rcx, [rsp+200h+var_188]
0x1400a22ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400a22f3  mov     rbx, rax
0x1400a22f6  lea     rdx, szPassword
0x1400a22fd  lea     rcx, [rbp+100h+var_168]
0x1400a2301  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400a2306  nop
0x1400a2307  mov     dword ptr [rsp+200h+lpOverlapped], 2
0x1400a230f  mov     r9, rbx
0x1400a2312  mov     r8, rax
0x1400a2315  lea     rcx, [rbp+100h+var_E0]
0x1400a2319  call    ?make_registry_value@ContainerDefinition@ComputeService@@YA?AURegistryValue@Registry@Schema@@W4RegistryHive@45@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z; ComputeService::ContainerDefinition::make_registry_value(Schema::Registry::RegistryHive,std::wstring,std::wstring,ulong)
0x1400a231e  nop
0x1400a231f  xor     r8d, r8d
0x1400a2322  lea     rdx, [rbp+100h+var_E0]
0x1400a2326  lea     rcx, [rbp+100h+var_148]
0x1400a232a  call    ComputeService__ContainerDefinition__Details__ApplyValueToOfflineHive
0x1400a232f  lea     rdx, [rbp+100h+var_148]
0x1400a2333  mov     rcx, rdi
0x1400a2336  call    ?ConvertOfflineHiveToBytes@Details@ContainerDefinition@ComputeService@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEAUOfflineHive@OfflineHiveLib@@@Z; ComputeService::ContainerDefinition::Details::ConvertOfflineHiveToBytes(OfflineHiveLib::OfflineHive &)
0x1400a233b  nop
0x1400a233c  lea     rcx, [rbp+100h+var_E0]; this
0x1400a2340  call    ??1RegistryValue@Registry@Schema@@QEAA@XZ; Schema::Registry::RegistryValue::~RegistryValue(void)
0x1400a2345  jmp     loc_1400A243A
0x1400a234a  mov     rcx, [rbp+108h]; this
0x1400a2351  test    eax, eax
0x1400a2353  jz      short loc_1400A236A
0x1400a2355  mov     r9d, eax; char *
0x1400a2358  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a235f  mov     edx, 160h; void *
0x1400a2364  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a236a  cmp     dword ptr [rsp+200h+var_1A0], 4
0x1400a236f  jz      short loc_1400A2390
0x1400a2371  mov     rcx, [rbp+108h]; this
0x1400a2378  mov     r9d, 0Dh; char *
0x1400a237e  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a2385  mov     edx, 165h; void *
0x1400a238a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a2390  mov     qword ptr [rbp+100h+FileSize], r12
0x1400a2394  lea     rdx, [rbp+100h+FileSize]; lpFileSize
0x1400a2398  mov     rcx, [r14]; hFile
0x1400a239b  call    cs:__imp_GetFileSizeEx
0x1400a23a2  nop     dword ptr [rax+rax+00h]
0x1400a23a7  mov     rcx, [rbp+108h]; this
0x1400a23ae  test    eax, eax
0x1400a23b0  jnz     short loc_1400A23C4
0x1400a23b2  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a23b9  mov     edx, 16Ah; void *
0x1400a23be  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400a23c4  xorps   xmm0, xmm0
0x1400a23c7  xor     eax, eax
0x1400a23c9  movups  xmmword ptr [rbp+100h+lpBuffer], xmm0
0x1400a23cd  mov     [rbp+100h+var_F0], rax
0x1400a23d1  mov     rdx, qword ptr [rbp+100h+FileSize]
0x1400a23d5  lea     rcx, [rbp+100h+lpBuffer]
0x1400a23d9  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1400a23de  nop
0x1400a23df  mov     [rbp+100h+NumberOfBytesRead], r12d
0x1400a23e3  mov     rdx, [rbp+100h+lpBuffer]; lpBuffer
0x1400a23e7  mov     r8d, dword ptr [rbp+100h+lpBuffer+8]
0x1400a23eb  sub     r8d, edx; nNumberOfBytesToRead
0x1400a23ee  mov     [rsp+200h+lpOverlapped], r12; lpOverlapped
0x1400a23f3  lea     r9, [rbp+100h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400a23f7  mov     rcx, [r14]; hFile
0x1400a23fa  call    cs:__imp_ReadFile
0x1400a2401  nop     dword ptr [rax+rax+00h]
0x1400a2406  mov     rcx, [rbp+108h]; this
0x1400a240d  test    eax, eax
0x1400a240f  jnz     short loc_1400A2423
0x1400a2411  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a2418  mov     edx, 16Eh; void *
0x1400a241d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400a2423  lea     rdx, [rbp+100h+lpBuffer]
0x1400a2427  mov     rcx, rdi
0x1400a242a  call    ??0?$vector@UProcessorCacheMonitor@ProcessorCache@Resources@Schema@@V?$allocator@UProcessorCacheMonitor@ProcessorCache@Resources@Schema@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor>::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor>(std::vector<Schema::Resources::ProcessorCache::ProcessorCacheMonitor> &&)
0x1400a242f  nop
0x1400a2430  lea     rcx, [rbp+100h+lpBuffer]
0x1400a2434  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400a2439  nop
0x1400a243a  lea     rcx, [rbp+100h+var_110]
0x1400a243e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1400a2443  nop
0x1400a2444  lea     rcx, [rbp+100h+var_148]; this
0x1400a2448  call    ??1OfflineHive@OfflineHiveLib@@QEAA@XZ; OfflineHiveLib::OfflineHive::~OfflineHive(void)
0x1400a244d  mov     rax, rdi
0x1400a2450  mov     rcx, [rbp+100h+var_30]
0x1400a2457  xor     rcx, rsp; StackCookie
0x1400a245a  call    __security_check_cookie
0x1400a245f  lea     r11, [rsp+200h+var_20]
0x1400a2467  mov     rbx, [r11+40h]
0x1400a246b  mov     rsi, [r11+48h]
0x1400a246f  mov     rsp, r11
0x1400a2472  pop     r15
0x1400a2474  pop     r14
0x1400a2476  pop     r12
0x1400a2478  pop     rdi
0x1400a2479  pop     rbp
0x1400a247a  retn
```
