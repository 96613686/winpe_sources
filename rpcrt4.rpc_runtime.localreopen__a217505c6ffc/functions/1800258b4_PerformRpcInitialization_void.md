# PerformRpcInitialization(void)

- ea: `0x1800258b4`
- end: `0x180025d62`
- name: `?PerformRpcInitialization@@YAJXZ`
- size: `1198`
- prototype: `__int64(void)`
- caller_count: `142`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003140`
- `0x180004f40`
- `0x180005510`
- `0x1800062f8`
- `0x180006550`
- `0x180006a18`
- `0x180006fb4`
- `0x180007820`
- `0x180008190`
- `0x180008630`
- `0x1800086b0`
- `0x180008720`
- `0x180009e10`
- `0x180009eb0`
- `0x18000a040`
- `0x18000ad30`
- `0x18000b298`
- `0x18000b630`
- `0x18000b680`
- `0x18000b760`
- `0x18000bab0`
- `0x18000bd30`
- `0x18000bfd0`
- `0x18000c110`
- `0x18000c260`
- `0x18000c4b0`
- `0x18000c540`
- `0x18000c610`
- `0x18000dbf0`
- `0x18001f910`
- `0x180025180`
- `0x180025710`
- `0x180026080`
- `0x18002d310`
- `0x18002e330`
- `0x18002e4f0`
- `0x180033e58`
- `0x180034230`
- `0x180044870`
- `0x180058520`
- `0x180066200`
- `0x18006cff0`
- `0x18006f4a0`
- `0x180075750`
- `0x180079940`
- `0x1800799e0`
- `0x18007d1b0`
- `0x18007d5c0`
- `0x180082e00`
- `0x1800830a0`

## callees

- `0x180023020`
- `0x1800258b4`
- `0x18005bbfc`
- `0x18005bcf8`
- `0x18005bdac`
- `0x18005be64`
- `0x18005c028`
- `0x1800919e0`
- `0x1800955b0`
- `0x180095a30`
- `0x180096910`
- `0x1800971f0`
- `0x1800972fc`
- `0x18009798c`
- `0x180097c58`
- `0x1800a306c`
- `0x1800a6048`
- `0x1800d7010`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x180025cc2`
- `ntdll!wcsncpy_s` at `0x180025cc2`
- `ntdll!SbSelectProcedure` at `0x180025c62`
- `ntdll!SbSelectProcedure` at `0x180025c62`
- `ntdll!WinSqmIsOptedIn` at `0x180025b7e`
- `ntdll!WinSqmIsOptedIn` at `0x180025b7e`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180025a20`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180025a20`
- `ntdll!EtwEventRegister` at `0x180025bf3`
- `ntdll!EtwEventRegister` at `0x180025bf3`
- `ntdll!RtlLeaveCriticalSection` at `0x180025c2d`
- `ntdll!RtlLeaveCriticalSection` at `0x180025c2d`
- `ntdll!RtlEnterCriticalSection` at `0x1800258df`
- `ntdll!RtlEnterCriticalSection` at `0x1800258df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c83`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025917`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025917`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800259af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800259af`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180025a78`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180025a78`

## string_xrefs

- `0x1800258fa`: `rpcrt4.dll`

## pseudocode

```c
__int64 PerformRpcInitialization(void)
{
  unsigned int PolicySettings; // ebx
  __int64 v2; // rcx
  __int64 v3; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  WCHAR *v6; // rax
  __int64 v7; // rbx
  struct _PEB *v8; // rax
  ULONG NtGlobalFlag; // ecx
  struct _PEB *v10; // rax
  void (*v11)(void); // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  DWORD LastError; // eax
  unsigned int v16; // eax
  __int128 v17; // [rsp+20h] [rbp-38h] BYREF
  __int128 v18; // [rsp+30h] [rbp-28h]
  __int64 v19; // [rsp+40h] [rbp-18h]

  if ( RpcHasBeenInitialized )
    return 0;
  PolicySettings = 0;
  RtlEnterCriticalSection(&GlobalMutex);
  if ( RpcHasBeenInitialized )
    goto LABEL_33;
  v19 = 0;
  v17 = 0;
  v18 = 0;
  if ( !LoadLibraryExW(L"rpcrt4.dll", 0, 0) || !(unsigned int)GetBasicSystemInfo((struct tagBasicSystemInfo *)&v17) )
    goto LABEL_32;
  v2 = v18;
  gNumberOfProcessors = DWORD2(v18);
  gPageSize = v17;
  v3 = v18;
  if ( *((_QWORD *)&v17 + 1) < (unsigned __int64)v18 )
    v3 = *((_QWORD *)&v17 + 1);
  gfServerPlatform = v19;
  gPartialReceiveQuotaKeepaliveThreshold = (unsigned __int64)(v3 << 20) >> 1;
  gPhysicalMemorySize = *((_QWORD *)&v17 + 1);
  if ( *((_QWORD *)&v17 + 1) < (unsigned __int64)v18 )
    v2 = *((_QWORD *)&v17 + 1);
  gPartialReceiveQuotaDenyThreshold = (unsigned __int64)(3145728 * v2) >> 2;
  g_fRestrictRemoteClients = v19 == 0;
  gProcessStartTime = GetTickCount();
  if ( (unsigned int)InitializeRpcAllocator() )
    goto LABEL_32;
  GetMaxRpcSize();
  if ( (unsigned int)InitializeRpcProtocolOfsClient()
    || (unsigned int)InitializeObjectDictionary()
    || (unsigned int)InitializeRpcServer()
    || (unsigned int)InitializeRpcProtocolLrpc() )
  {
    goto LABEL_32;
  }
  v4 = (struct _RTL_CRITICAL_SECTION *)AllocWrapper(0x28u);
  v5 = v4;
  if ( !v4 )
  {
    ThreadListMutex = 0;
    goto LABEL_32;
  }
  RtlInitializeCriticalSectionAndSpinCount(v4, 0);
  ThreadListMutex = v5;
  qword_1800FF170 = (__int64)&ThreadListHead;
  ThreadListHead.Flink = &ThreadListHead;
  v6 = (WCHAR *)AllocWrapper(0x20u);
  gLocalComputerName = v6;
  if ( !v6 )
    goto LABEL_32;
  gLocalComputerNameLength = 16;
  if ( GetComputerNameExW(ComputerNameNetBIOS, v6, &gLocalComputerNameLength) )
  {
    LODWORD(v7) = gLocalComputerNameLength;
    goto LABEL_19;
  }
  LastError = GetLastError();
  if ( LastError != 2 )
  {
    if ( LastError != 8 )
    {
      if ( LastError == 1816 || LastError == 1450 )
      {
        PolicySettings = 1721;
        goto LABEL_33;
      }
      PolicySettings = 5;
      if ( LastError == 19 || LastError == 641 || LastError == 5 )
        goto LABEL_33;
    }
    goto LABEL_32;
  }
  if ( (NtCurrentPeb()->ProcessParameters->Flags & 0x80000000) == 0 )
  {
LABEL_32:
    PolicySettings = 14;
    goto LABEL_33;
  }
  v7 = -1;
  wcsncpy_s((wchar_t *)gLocalComputerName, 0x10u, L"LocalHost", 0xFFFFFFFFFFFFFFFFuLL);
  do
    ++v7;
  while ( gLocalComputerName[v7] );
LABEL_19:
  gLocalComputerNameLength = v7 + 1;
  v8 = NtCurrentPeb();
  gfAppVerifierEnabled = (v8->NtGlobalFlag >> 8) & 1;
  NtGlobalFlag = v8->NtGlobalFlag;
  v10 = NtCurrentPeb();
  gfPagedHeapEnabled = (NtGlobalFlag >> 25) & 1;
  pBaseNameUnicodeString = (PUNICODE_STRING)&v10->Ldr->InLoadOrderModuleList.Flink[5].Blink;
  RpcpApplyIFEOConfigurations();
  if ( gfAppVerifierEnabled || gfPagedHeapEnabled )
    InitializeRpcVerifier();
  if ( (unsigned int)InitializeDefaultSecurityDescriptor() )
    goto LABEL_32;
  PolicySettings = InitializeEPMapperClient();
  if ( !PolicySettings )
  {
    PolicySettings = ReadPolicySettings();
    if ( !PolicySettings )
    {
      v11 = (void (*)(void))qword_1800FEE88;
      if ( qword_1800FEE88
        || (v11 = (void (*)(void))SbSelectProcedure(2880154539LL, 0, "kLsE", 0), (qword_1800FEE88 = (__int64)v11) != 0) )
      {
        v11();
      }
      gThreadTimeout = gfServerPlatform != 0 ? 90000 : 30000;
      if ( !g_fServerSideDebugInfoEnabled && !g_fClientSideDebugInfoEnabled )
        goto LABEL_28;
      v16 = InitializeCellHeap();
      PolicySettings = v16;
      if ( v16 == 1764 )
      {
        g_fServerSideDebugInfoEnabled = 0;
        PolicySettings = 0;
        g_fClientSideDebugInfoEnabled = 0;
        goto LABEL_28;
      }
      if ( !v16 )
      {
LABEL_28:
        g_SqmEnabled = WinSqmIsOptedIn();
        McGenEventRegister_EtwEventRegister(&RpcEtwGuid, v12, &RpcEtwGuid_Context, &RpcEtwGuid_Context);
        McGenEventRegister_EtwEventRegister(RpcLegacyEvents, v13, RpcLegacyEvents_Context, RpcLegacyEvents_Context);
        McGenEventRegister_EtwEventRegister(RpcAuditEtwGuid, v14, &RpcAuditEtwGuid_Context, &RpcAuditEtwGuid_Context);
        if ( Microsoft_Windows_Networking_CorrelationHandle
          || !(unsigned int)EtwEventRegister(
                              Microsoft_Windows_Networking_CorrelationId,
                              Microsoft_Windows_Networking_Correlation_EtwEnableCallback,
                              0,
                              &Microsoft_Windows_Networking_CorrelationHandle) )
        {
          Microsoft_Windows_Networking_ProviderId = RpcEtwGuid;
        }
        g_dwIdleTimerWindow = GetRpcIdleTimerWindow();
        RpcHasBeenInitialized = 1;
      }
    }
  }
LABEL_33:
  RtlLeaveCriticalSection(&GlobalMutex);
  return PolicySettings;
}

```

## disassembly

```asm
0x1800258b4  mov     [rsp+arg_0], rbx
0x1800258b9  push    rdi
0x1800258ba  sub     rsp, 50h
0x1800258be  xor     edi, edi
0x1800258c0  cmp     cs:?RpcHasBeenInitialized@@3HA, edi; int RpcHasBeenInitialized
0x1800258c6  jz      short loc_1800258D6
0x1800258c8  xor     eax, eax
0x1800258ca  mov     rbx, [rsp+58h+arg_0]
0x1800258cf  add     rsp, 50h
0x1800258d3  pop     rdi
0x1800258d4  retn
0x1800258d6  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x1800258dd  mov     ebx, edi
0x1800258df  call    cs:__imp_RtlEnterCriticalSection
0x1800258e6  nop     dword ptr [rax+rax+00h]
0x1800258eb  cmp     cs:?RpcHasBeenInitialized@@3HA, edi; int RpcHasBeenInitialized
0x1800258f1  jnz     loc_180025C26
0x1800258f7  xorps   xmm0, xmm0
0x1800258fa  lea     rcx, aRpcrt4Dll_0; "rpcrt4.dll"
0x180025901  xor     eax, eax
0x180025903  xor     r8d, r8d; dwFlags
0x180025906  xor     edx, edx; hFile
0x180025908  mov     [rsp+58h+var_18], rax
0x18002590d  movups  [rsp+58h+var_38], xmm0
0x180025912  movups  [rsp+58h+var_28], xmm0
0x180025917  call    cs:__imp_LoadLibraryExW
0x18002591e  nop     dword ptr [rax+rax+00h]
0x180025923  test    rax, rax
0x180025926  jz      loc_180025C21
0x18002592c  lea     rcx, [rsp+58h+var_38]; struct tagBasicSystemInfo *
0x180025931  call    ?GetBasicSystemInfo@@YAHPEAUtagBasicSystemInfo@@@Z; GetBasicSystemInfo(tagBasicSystemInfo *)
0x180025936  test    eax, eax
0x180025938  jz      loc_180025C21
0x18002593e  mov     rdx, qword ptr [rsp+58h+var_38+8]
0x180025943  mov     rcx, qword ptr [rsp+58h+var_28]
0x180025948  mov     eax, dword ptr [rsp+58h+var_28+8]
0x18002594c  cmp     rdx, rcx
0x18002594f  mov     r8, [rsp+58h+var_18]
0x180025954  mov     cs:?gNumberOfProcessors@@3IA, eax; uint gNumberOfProcessors
0x18002595a  mov     eax, dword ptr [rsp+58h+var_38]
0x18002595e  mov     cs:?gPageSize@@3KA, eax; ulong gPageSize
0x180025964  mov     rax, rcx
0x180025967  cmovb   rax, rdx
0x18002596b  mov     cs:?gfServerPlatform@@3HA, r8d; int gfServerPlatform
0x180025972  shl     rax, 14h
0x180025976  shr     rax, 1
0x180025979  mov     cs:?gPartialReceiveQuotaKeepaliveThreshold@@3_KA, rax; unsigned __int64 gPartialReceiveQuotaKeepaliveThreshold
0x180025980  cmp     rdx, rcx
0x180025983  mov     cs:?gPhysicalMemorySize@@3_KA, rdx; unsigned __int64 gPhysicalMemorySize
0x18002598a  cmovb   rcx, rdx
0x18002598e  lea     rax, [rcx+rcx*2]
0x180025992  shl     rax, 14h
0x180025996  shr     rax, 2
0x18002599a  mov     cs:?gPartialReceiveQuotaDenyThreshold@@3_KA, rax; unsigned __int64 gPartialReceiveQuotaDenyThreshold
0x1800259a1  test    r8d, r8d
0x1800259a4  mov     eax, edi
0x1800259a6  setz    al
0x1800259a9  mov     cs:?g_fRestrictRemoteClients@@3IA, eax; uint g_fRestrictRemoteClients
0x1800259af  call    cs:__imp_GetTickCount
0x1800259b6  nop     dword ptr [rax+rax+00h]
0x1800259bb  mov     cs:?gProcessStartTime@@3KA, eax; ulong gProcessStartTime
0x1800259c1  call    ?InitializeRpcAllocator@@YAHXZ; InitializeRpcAllocator(void)
0x1800259c6  test    eax, eax
0x1800259c8  jnz     loc_180025C21
0x1800259ce  call    ?GetMaxRpcSize@@YAXXZ; GetMaxRpcSize(void)
0x1800259d3  call    ?InitializeRpcProtocolOfsClient@@YAHXZ; InitializeRpcProtocolOfsClient(void)
0x1800259d8  test    eax, eax
0x1800259da  jnz     loc_180025C21
0x1800259e0  call    ?InitializeObjectDictionary@@YAHXZ; InitializeObjectDictionary(void)
0x1800259e5  test    eax, eax
0x1800259e7  jnz     loc_180025C21
0x1800259ed  call    ?InitializeRpcServer@@YAHXZ; InitializeRpcServer(void)
0x1800259f2  test    eax, eax
0x1800259f4  jnz     loc_180025C21
0x1800259fa  call    ?InitializeRpcProtocolLrpc@@YAJXZ; InitializeRpcProtocolLrpc(void)
0x1800259ff  test    eax, eax
0x180025a01  jnz     loc_180025C21
0x180025a07  lea     ecx, [rax+28h]; dwBytes
0x180025a0a  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180025a0f  mov     rbx, rax
0x180025a12  test    rax, rax
0x180025a15  jz      loc_180025C1A
0x180025a1b  xor     edx, edx; SpinCount
0x180025a1d  mov     rcx, rax; CriticalSection
0x180025a20  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180025a27  nop     dword ptr [rax+rax+00h]
0x180025a2c  lea     rax, ?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x180025a33  mov     cs:?ThreadListMutex@@3PEAVMUTEX@@EA, rbx; MUTEX * ThreadListMutex
0x180025a3a  mov     ecx, 20h ; ' '; dwBytes
0x180025a3f  mov     cs:qword_1800FF170, rax
0x180025a46  mov     cs:?ThreadListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ThreadListHead
0x180025a4d  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180025a52  mov     cs:?gLocalComputerName@@3PEAGEA, rax; ushort * gLocalComputerName
0x180025a59  test    rax, rax
0x180025a5c  jz      loc_180025C21
0x180025a62  lea     r8, ?gLocalComputerNameLength@@3KA; nSize
0x180025a69  mov     cs:?gLocalComputerNameLength@@3KA, 10h; ulong gLocalComputerNameLength
0x180025a73  mov     rdx, rax; lpBuffer
0x180025a76  xor     ecx, ecx; NameType
0x180025a78  call    cs:__imp_GetComputerNameExW
0x180025a7f  nop     dword ptr [rax+rax+00h]
0x180025a84  cmp     eax, 1
0x180025a87  jnz     loc_180025C83
0x180025a8d  mov     ebx, cs:?gLocalComputerNameLength@@3KA; ulong gLocalComputerNameLength
0x180025a93  inc     ebx
0x180025a95  mov     cs:?gLocalComputerNameLength@@3KA, ebx; ulong gLocalComputerNameLength
0x180025a9b  mov     rax, gs:60h
0x180025aa4  mov     ecx, [rax+0BCh]
0x180025aaa  mov     rax, gs:60h
0x180025ab3  shr     ecx, 8
0x180025ab6  and     ecx, 1
0x180025ab9  mov     cs:?gfAppVerifierEnabled@@3HA, ecx; int gfAppVerifierEnabled
0x180025abf  mov     ecx, [rax+0BCh]
0x180025ac5  mov     rax, gs:60h
0x180025ace  shr     ecx, 19h
0x180025ad1  and     ecx, 1
0x180025ad4  mov     cs:?gfPagedHeapEnabled@@3HA, ecx; int gfPagedHeapEnabled
0x180025ada  mov     rcx, [rax+18h]
0x180025ade  mov     rax, [rcx+10h]
0x180025ae2  add     rax, 58h ; 'X'
0x180025ae6  mov     cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA, rax; _UNICODE_STRING * pBaseNameUnicodeString
0x180025aed  call    ?RpcpApplyIFEOConfigurations@@YAXXZ; RpcpApplyIFEOConfigurations(void)
0x180025af2  cmp     cs:?gfAppVerifierEnabled@@3HA, edi; int gfAppVerifierEnabled
0x180025af8  jnz     loc_180025D2A
0x180025afe  cmp     cs:?gfPagedHeapEnabled@@3HA, edi; int gfPagedHeapEnabled
0x180025b04  jnz     loc_180025D2A
0x180025b0a  call    ?InitializeDefaultSecurityDescriptor@@YAJXZ; InitializeDefaultSecurityDescriptor(void)
0x180025b0f  test    eax, eax
0x180025b11  jnz     loc_180025C21
0x180025b17  call    InitializeEPMapperClient
0x180025b1c  mov     ebx, eax
0x180025b1e  test    eax, eax
0x180025b20  jnz     loc_180025C26
0x180025b26  call    ?ReadPolicySettings@@YAJXZ; ReadPolicySettings(void)
0x180025b2b  mov     ebx, eax
0x180025b2d  test    eax, eax
0x180025b2f  jnz     loc_180025C26
0x180025b35  mov     rax, cs:qword_1800FEE88
0x180025b3c  test    rax, rax
0x180025b3f  jz      loc_180025C51
0x180025b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b4a  mov     eax, cs:?gfServerPlatform@@3HA; int gfServerPlatform
0x180025b50  neg     eax
0x180025b52  sbb     ecx, ecx
0x180025b54  and     ecx, 0EA60h
0x180025b5a  add     ecx, 7530h
0x180025b60  cmp     cs:?g_fServerSideDebugInfoEnabled@@3HA, edi; int g_fServerSideDebugInfoEnabled
0x180025b66  mov     cs:?gThreadTimeout@@3KA, ecx; ulong gThreadTimeout
0x180025b6c  jnz     loc_180025D34
0x180025b72  cmp     cs:?g_fClientSideDebugInfoEnabled@@3HA, edi; int g_fClientSideDebugInfoEnabled
0x180025b78  jnz     loc_180025D34
0x180025b7e  call    cs:__imp_WinSqmIsOptedIn
0x180025b85  nop     dword ptr [rax+rax+00h]
0x180025b8a  lea     r8, RpcEtwGuid_Context
0x180025b91  mov     cs:?g_SqmEnabled@@3HA, eax; int g_SqmEnabled
0x180025b97  mov     r9, r8
0x180025b9a  lea     rcx, RpcEtwGuid
0x180025ba1  call    McGenEventRegister_EtwEventRegister
0x180025ba6  lea     r8, RpcLegacyEvents_Context
0x180025bad  mov     r9, r8
0x180025bb0  lea     rcx, RpcLegacyEvents
0x180025bb7  call    McGenEventRegister_EtwEventRegister
0x180025bbc  lea     r8, RpcAuditEtwGuid_Context
0x180025bc3  mov     r9, r8
0x180025bc6  lea     rcx, RpcAuditEtwGuid
0x180025bcd  call    McGenEventRegister_EtwEventRegister
0x180025bd2  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, rdi
0x180025bd9  jnz     short loc_180025C40
0x180025bdb  lea     r9, Microsoft_Windows_Networking_CorrelationHandle
0x180025be2  xor     r8d, r8d
0x180025be5  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback
0x180025bec  lea     rcx, Microsoft_Windows_Networking_CorrelationId
0x180025bf3  call    cs:__imp_EtwEventRegister
0x180025bfa  nop     dword ptr [rax+rax+00h]
0x180025bff  test    eax, eax
0x180025c01  jz      short loc_180025C40
0x180025c03  call    ?GetRpcIdleTimerWindow@@YAKXZ; GetRpcIdleTimerWindow(void)
0x180025c08  mov     cs:?g_dwIdleTimerWindow@@3KA, eax; ulong g_dwIdleTimerWindow
0x180025c0e  mov     cs:?RpcHasBeenInitialized@@3HA, 1; int RpcHasBeenInitialized
0x180025c18  jmp     short loc_180025C26
0x180025c1a  mov     cs:?ThreadListMutex@@3PEAVMUTEX@@EA, rdi; MUTEX * ThreadListMutex
0x180025c21  mov     ebx, 0Eh
0x180025c26  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x180025c2d  call    cs:__imp_RtlLeaveCriticalSection
0x180025c34  nop     dword ptr [rax+rax+00h]
0x180025c39  mov     eax, ebx
0x180025c3b  jmp     loc_1800258CA
0x180025c40  movups  xmm0, cs:RpcEtwGuid
0x180025c47  movdqu  cs:Microsoft_Windows_Networking_ProviderId, xmm0
0x180025c4f  jmp     short loc_180025C03
0x180025c51  xor     r9d, r9d
0x180025c54  lea     r8, g_SbModuleTable_AeNamespace; "kLsE"
0x180025c5b  xor     edx, edx
0x180025c5d  mov     ecx, 0ABABABABh
0x180025c62  call    cs:__imp_SbSelectProcedure
0x180025c69  nop     dword ptr [rax+rax+00h]
0x180025c6e  mov     cs:qword_1800FEE88, rax
0x180025c75  test    rax, rax
0x180025c78  jz      loc_180025B4A
0x180025c7e  jmp     loc_180025B45
0x180025c83  call    cs:__imp_GetLastError
0x180025c8a  nop     dword ptr [rax+rax+00h]
0x180025c8f  cmp     eax, 2
0x180025c92  jnz     short loc_180025CE3
0x180025c94  mov     rax, gs:60h
0x180025c9d  mov     rcx, [rax+20h]
0x180025ca1  cmp     [rcx+8], edi
0x180025ca4  jge     loc_180025C21
0x180025caa  mov     rcx, cs:?gLocalComputerName@@3PEAGEA; Destination
0x180025cb1  lea     r8, aLocalhost_0; "LocalHost"
0x180025cb8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025cbc  mov     r9, rbx; MaxCount
0x180025cbf  lea     edx, [rbx+11h]; SizeInWords
0x180025cc2  call    cs:__imp_wcsncpy_s
0x180025cc9  nop     dword ptr [rax+rax+00h]
0x180025cce  mov     rax, cs:?gLocalComputerName@@3PEAGEA; ushort * gLocalComputerName
0x180025cd5  inc     rbx
0x180025cd8  cmp     [rax+rbx*2], di
0x180025cdc  jnz     short loc_180025CD5
0x180025cde  jmp     loc_180025A93
0x180025ce3  cmp     eax, 8
0x180025ce6  jz      loc_180025C21
0x180025cec  cmp     eax, 718h
0x180025cf1  jz      short loc_180025D20
0x180025cf3  cmp     eax, 5AAh
0x180025cf8  jz      short loc_180025D20
0x180025cfa  mov     ebx, 5
0x180025cff  cmp     eax, 13h
0x180025d02  jz      loc_180025C26
0x180025d08  cmp     eax, 281h
0x180025d0d  jz      loc_180025C26
0x180025d13  cmp     eax, ebx
0x180025d15  jz      loc_180025C26
0x180025d1b  jmp     loc_180025C21
0x180025d20  mov     ebx, 6B9h
0x180025d25  jmp     loc_180025C26
0x180025d2a  call    ?InitializeRpcVerifier@@YAXXZ; InitializeRpcVerifier(void)
0x180025d2f  jmp     loc_180025B0A
0x180025d34  call    ?InitializeCellHeap@@YAJXZ; InitializeCellHeap(void)
0x180025d39  mov     ebx, eax
0x180025d3b  cmp     eax, 6E4h
0x180025d40  jnz     short loc_180025D55
0x180025d42  mov     cs:?g_fServerSideDebugInfoEnabled@@3HA, edi; int g_fServerSideDebugInfoEnabled
0x180025d48  mov     ebx, edi
0x180025d4a  mov     cs:?g_fClientSideDebugInfoEnabled@@3HA, edi; int g_fClientSideDebugInfoEnabled
0x180025d50  jmp     loc_180025B7E
0x180025d55  test    eax, eax
0x180025d57  jnz     loc_180025C26
0x180025d5d  jmp     loc_180025B7E
```
