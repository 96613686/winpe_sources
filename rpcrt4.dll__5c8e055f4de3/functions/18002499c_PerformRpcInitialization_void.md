# PerformRpcInitialization(void)

- ea: `0x18002499c`
- end: `0x180024e03`
- name: `?PerformRpcInitialization@@YAJXZ`
- size: `1127`
- prototype: `__int64(void)`
- caller_count: `142`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800030f0`
- `0x1800122f0`
- `0x18001e860`
- `0x180024270`
- `0x180024800`
- `0x180024e10`
- `0x1800252a0`
- `0x18002c000`
- `0x18002d000`
- `0x18002d1c0`
- `0x1800329a8`
- `0x180032d50`
- `0x1800466f0`
- `0x18004dac0`
- `0x18005ca40`
- `0x18005e9d0`
- `0x18005faa0`
- `0x180064c90`
- `0x180065260`
- `0x180066038`
- `0x180066290`
- `0x180066718`
- `0x180066c80`
- `0x1800674d0`
- `0x180067e00`
- `0x1800682a0`
- `0x180068320`
- `0x180068390`
- `0x180069b70`
- `0x180069c10`
- `0x180069d90`
- `0x18006aa80`
- `0x18006afb4`
- `0x18006b340`
- `0x18006b420`
- `0x18006b720`
- `0x18006b990`
- `0x18006bc50`
- `0x18006bd90`
- `0x18006bee0`
- `0x18006cda0`
- `0x18006d140`
- `0x18006da20`
- `0x18006e090`
- `0x18006e120`
- `0x18006e1e0`
- `0x18006e270`
- `0x18006e310`
- `0x18006e400`
- `0x180075b00`

## callees

- `0x180021e70`
- `0x18002499c`
- `0x180048db4`
- `0x180048eac`
- `0x180048f58`
- `0x180048ffc`
- `0x18004962c`
- `0x18008ddcc`
- `0x180091010`
- `0x180091480`
- `0x180093f3c`
- `0x1800947d0`
- `0x180094810`
- `0x180094ea8`
- `0x180094efc`
- `0x18009fa24`
- `0x1800a2acc`
- `0x1800d2010`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x180024d69`
- `ntdll!wcsncpy_s` at `0x180024d69`
- `ntdll!SbSelectProcedure` at `0x180024d19`
- `ntdll!SbSelectProcedure` at `0x180024d19`
- `ntdll!WinSqmIsOptedIn` at `0x180024c47`
- `ntdll!WinSqmIsOptedIn` at `0x180024c47`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180024af5`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180024af5`
- `ntdll!EtwEventRegister` at `0x180024cb6`
- `ntdll!EtwEventRegister` at `0x180024cb6`
- `ntdll!RtlLeaveCriticalSection` at `0x180024cea`
- `ntdll!RtlLeaveCriticalSection` at `0x180024cea`
- `ntdll!RtlEnterCriticalSection` at `0x1800249c6`
- `ntdll!RtlEnterCriticalSection` at `0x1800249c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d34`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800249f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800249f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024a8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024a8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180024b47`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180024b47`

## string_xrefs

- `0x1800249db`: `rpcrt4.dll`

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
  qword_1800FA170 = (__int64)&ThreadListHead;
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
      v11 = (void (*)(void))qword_1800F9E88;
      if ( qword_1800F9E88
        || (v11 = (void (*)(void))SbSelectProcedure(2880154539LL, 0, "kLsE", 0), (qword_1800F9E88 = (__int64)v11) != 0) )
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
0x18002499c  mov     [rsp+arg_0], rbx
0x1800249a1  push    rdi
0x1800249a2  sub     rsp, 50h
0x1800249a6  xor     edi, edi
0x1800249a8  cmp     cs:?RpcHasBeenInitialized@@3HA, edi; int RpcHasBeenInitialized
0x1800249ae  jz      short loc_1800249BD
0x1800249b0  xor     eax, eax
0x1800249b2  mov     rbx, [rsp+58h+arg_0]
0x1800249b7  add     rsp, 50h
0x1800249bb  pop     rdi
0x1800249bc  retn
0x1800249bd  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x1800249c4  mov     ebx, edi
0x1800249c6  call    cs:__imp_RtlEnterCriticalSection
0x1800249cc  cmp     cs:?RpcHasBeenInitialized@@3HA, edi; int RpcHasBeenInitialized
0x1800249d2  jnz     loc_180024CE3
0x1800249d8  xorps   xmm0, xmm0
0x1800249db  lea     rcx, aRpcrt4Dll_0; "rpcrt4.dll"
0x1800249e2  xor     eax, eax
0x1800249e4  xor     r8d, r8d; dwFlags
0x1800249e7  xor     edx, edx; hFile
0x1800249e9  mov     [rsp+58h+var_18], rax
0x1800249ee  movups  [rsp+58h+var_38], xmm0
0x1800249f3  movups  [rsp+58h+var_28], xmm0
0x1800249f8  call    cs:__imp_LoadLibraryExW
0x1800249fe  test    rax, rax
0x180024a01  jz      loc_180024CDE
0x180024a07  lea     rcx, [rsp+58h+var_38]; struct tagBasicSystemInfo *
0x180024a0c  call    ?GetBasicSystemInfo@@YAHPEAUtagBasicSystemInfo@@@Z; GetBasicSystemInfo(tagBasicSystemInfo *)
0x180024a11  test    eax, eax
0x180024a13  jz      loc_180024CDE
0x180024a19  mov     rdx, qword ptr [rsp+58h+var_38+8]
0x180024a1e  mov     rcx, qword ptr [rsp+58h+var_28]
0x180024a23  mov     eax, dword ptr [rsp+58h+var_28+8]
0x180024a27  cmp     rdx, rcx
0x180024a2a  mov     r8, [rsp+58h+var_18]
0x180024a2f  mov     cs:?gNumberOfProcessors@@3IA, eax; uint gNumberOfProcessors
0x180024a35  mov     eax, dword ptr [rsp+58h+var_38]
0x180024a39  mov     cs:?gPageSize@@3KA, eax; ulong gPageSize
0x180024a3f  mov     rax, rcx
0x180024a42  cmovb   rax, rdx
0x180024a46  mov     cs:?gfServerPlatform@@3HA, r8d; int gfServerPlatform
0x180024a4d  shl     rax, 14h
0x180024a51  shr     rax, 1
0x180024a54  mov     cs:?gPartialReceiveQuotaKeepaliveThreshold@@3_KA, rax; unsigned __int64 gPartialReceiveQuotaKeepaliveThreshold
0x180024a5b  cmp     rdx, rcx
0x180024a5e  mov     cs:?gPhysicalMemorySize@@3_KA, rdx; unsigned __int64 gPhysicalMemorySize
0x180024a65  cmovb   rcx, rdx
0x180024a69  lea     rax, [rcx+rcx*2]
0x180024a6d  shl     rax, 14h
0x180024a71  shr     rax, 2
0x180024a75  mov     cs:?gPartialReceiveQuotaDenyThreshold@@3_KA, rax; unsigned __int64 gPartialReceiveQuotaDenyThreshold
0x180024a7c  test    r8d, r8d
0x180024a7f  mov     eax, edi
0x180024a81  setz    al
0x180024a84  mov     cs:?g_fRestrictRemoteClients@@3IA, eax; uint g_fRestrictRemoteClients
0x180024a8a  call    cs:__imp_GetTickCount
0x180024a90  mov     cs:?gProcessStartTime@@3KA, eax; ulong gProcessStartTime
0x180024a96  call    ?InitializeRpcAllocator@@YAHXZ; InitializeRpcAllocator(void)
0x180024a9b  test    eax, eax
0x180024a9d  jnz     loc_180024CDE
0x180024aa3  call    ?GetMaxRpcSize@@YAXXZ; GetMaxRpcSize(void)
0x180024aa8  call    ?InitializeRpcProtocolOfsClient@@YAHXZ; InitializeRpcProtocolOfsClient(void)
0x180024aad  test    eax, eax
0x180024aaf  jnz     loc_180024CDE
0x180024ab5  call    ?InitializeObjectDictionary@@YAHXZ; InitializeObjectDictionary(void)
0x180024aba  test    eax, eax
0x180024abc  jnz     loc_180024CDE
0x180024ac2  call    ?InitializeRpcServer@@YAHXZ; InitializeRpcServer(void)
0x180024ac7  test    eax, eax
0x180024ac9  jnz     loc_180024CDE
0x180024acf  call    ?InitializeRpcProtocolLrpc@@YAJXZ; InitializeRpcProtocolLrpc(void)
0x180024ad4  test    eax, eax
0x180024ad6  jnz     loc_180024CDE
0x180024adc  lea     ecx, [rax+28h]; dwBytes
0x180024adf  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180024ae4  mov     rbx, rax
0x180024ae7  test    rax, rax
0x180024aea  jz      loc_180024CD7
0x180024af0  xor     edx, edx; SpinCount
0x180024af2  mov     rcx, rax; CriticalSection
0x180024af5  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180024afb  lea     rax, ?ThreadListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY ThreadListHead
0x180024b02  mov     cs:?ThreadListMutex@@3PEAVMUTEX@@EA, rbx; MUTEX * ThreadListMutex
0x180024b09  mov     ecx, 20h ; ' '; dwBytes
0x180024b0e  mov     cs:qword_1800FA170, rax
0x180024b15  mov     cs:?ThreadListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ThreadListHead
0x180024b1c  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180024b21  mov     cs:?gLocalComputerName@@3PEAGEA, rax; ushort * gLocalComputerName
0x180024b28  test    rax, rax
0x180024b2b  jz      loc_180024CDE
0x180024b31  lea     r8, ?gLocalComputerNameLength@@3KA; nSize
0x180024b38  mov     cs:?gLocalComputerNameLength@@3KA, 10h; ulong gLocalComputerNameLength
0x180024b42  mov     rdx, rax; lpBuffer
0x180024b45  xor     ecx, ecx; NameType
0x180024b47  call    cs:__imp_GetComputerNameExW
0x180024b4d  cmp     eax, 1
0x180024b50  jnz     loc_180024D34
0x180024b56  mov     ebx, cs:?gLocalComputerNameLength@@3KA; ulong gLocalComputerNameLength
0x180024b5c  inc     ebx
0x180024b5e  mov     cs:?gLocalComputerNameLength@@3KA, ebx; ulong gLocalComputerNameLength
0x180024b64  mov     rax, gs:60h
0x180024b6d  mov     ecx, [rax+0BCh]
0x180024b73  mov     rax, gs:60h
0x180024b7c  shr     ecx, 8
0x180024b7f  and     ecx, 1
0x180024b82  mov     cs:?gfAppVerifierEnabled@@3HA, ecx; int gfAppVerifierEnabled
0x180024b88  mov     ecx, [rax+0BCh]
0x180024b8e  mov     rax, gs:60h
0x180024b97  shr     ecx, 19h
0x180024b9a  and     ecx, 1
0x180024b9d  mov     cs:?gfPagedHeapEnabled@@3HA, ecx; int gfPagedHeapEnabled
0x180024ba3  mov     rcx, [rax+18h]
0x180024ba7  mov     rax, [rcx+10h]
0x180024bab  add     rax, 58h ; 'X'
0x180024baf  mov     cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA, rax; _UNICODE_STRING * pBaseNameUnicodeString
0x180024bb6  call    ?RpcpApplyIFEOConfigurations@@YAXXZ; RpcpApplyIFEOConfigurations(void)
0x180024bbb  cmp     cs:?gfAppVerifierEnabled@@3HA, edi; int gfAppVerifierEnabled
0x180024bc1  jnz     loc_180024DCB
0x180024bc7  cmp     cs:?gfPagedHeapEnabled@@3HA, edi; int gfPagedHeapEnabled
0x180024bcd  jnz     loc_180024DCB
0x180024bd3  call    ?InitializeDefaultSecurityDescriptor@@YAJXZ; InitializeDefaultSecurityDescriptor(void)
0x180024bd8  test    eax, eax
0x180024bda  jnz     loc_180024CDE
0x180024be0  call    InitializeEPMapperClient
0x180024be5  mov     ebx, eax
0x180024be7  test    eax, eax
0x180024be9  jnz     loc_180024CE3
0x180024bef  call    ?ReadPolicySettings@@YAJXZ; ReadPolicySettings(void)
0x180024bf4  mov     ebx, eax
0x180024bf6  test    eax, eax
0x180024bf8  jnz     loc_180024CE3
0x180024bfe  mov     rax, cs:qword_1800F9E88
0x180024c05  test    rax, rax
0x180024c08  jz      loc_180024D08
0x180024c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c13  mov     eax, cs:?gfServerPlatform@@3HA; int gfServerPlatform
0x180024c19  neg     eax
0x180024c1b  sbb     ecx, ecx
0x180024c1d  and     ecx, 0EA60h
0x180024c23  add     ecx, 7530h
0x180024c29  cmp     cs:?g_fServerSideDebugInfoEnabled@@3HA, edi; int g_fServerSideDebugInfoEnabled
0x180024c2f  mov     cs:?gThreadTimeout@@3KA, ecx; ulong gThreadTimeout
0x180024c35  jnz     loc_180024DD5
0x180024c3b  cmp     cs:?g_fClientSideDebugInfoEnabled@@3HA, edi; int g_fClientSideDebugInfoEnabled
0x180024c41  jnz     loc_180024DD5
0x180024c47  call    cs:__imp_WinSqmIsOptedIn
0x180024c4d  lea     r8, RpcEtwGuid_Context
0x180024c54  mov     cs:?g_SqmEnabled@@3HA, eax; int g_SqmEnabled
0x180024c5a  mov     r9, r8
0x180024c5d  lea     rcx, RpcEtwGuid
0x180024c64  call    McGenEventRegister_EtwEventRegister
0x180024c69  lea     r8, RpcLegacyEvents_Context
0x180024c70  mov     r9, r8
0x180024c73  lea     rcx, RpcLegacyEvents
0x180024c7a  call    McGenEventRegister_EtwEventRegister
0x180024c7f  lea     r8, RpcAuditEtwGuid_Context
0x180024c86  mov     r9, r8
0x180024c89  lea     rcx, RpcAuditEtwGuid
0x180024c90  call    McGenEventRegister_EtwEventRegister
0x180024c95  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, rdi
0x180024c9c  jnz     short loc_180024CF7
0x180024c9e  lea     r9, Microsoft_Windows_Networking_CorrelationHandle
0x180024ca5  xor     r8d, r8d
0x180024ca8  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback
0x180024caf  lea     rcx, Microsoft_Windows_Networking_CorrelationId
0x180024cb6  call    cs:__imp_EtwEventRegister
0x180024cbc  test    eax, eax
0x180024cbe  jz      short loc_180024CF7
0x180024cc0  call    ?GetRpcIdleTimerWindow@@YAKXZ; GetRpcIdleTimerWindow(void)
0x180024cc5  mov     cs:?g_dwIdleTimerWindow@@3KA, eax; ulong g_dwIdleTimerWindow
0x180024ccb  mov     cs:?RpcHasBeenInitialized@@3HA, 1; int RpcHasBeenInitialized
0x180024cd5  jmp     short loc_180024CE3
0x180024cd7  mov     cs:?ThreadListMutex@@3PEAVMUTEX@@EA, rdi; MUTEX * ThreadListMutex
0x180024cde  mov     ebx, 0Eh
0x180024ce3  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x180024cea  call    cs:__imp_RtlLeaveCriticalSection
0x180024cf0  mov     eax, ebx
0x180024cf2  jmp     loc_1800249B2
0x180024cf7  movups  xmm0, cs:RpcEtwGuid
0x180024cfe  movdqu  cs:Microsoft_Windows_Networking_ProviderId, xmm0
0x180024d06  jmp     short loc_180024CC0
0x180024d08  xor     r9d, r9d
0x180024d0b  lea     r8, g_SbModuleTable_AeNamespace; "kLsE"
0x180024d12  xor     edx, edx
0x180024d14  mov     ecx, 0ABABABABh
0x180024d19  call    cs:__imp_SbSelectProcedure
0x180024d1f  mov     cs:qword_1800F9E88, rax
0x180024d26  test    rax, rax
0x180024d29  jz      loc_180024C13
0x180024d2f  jmp     loc_180024C0E
0x180024d34  call    cs:__imp_GetLastError
0x180024d3a  cmp     eax, 2
0x180024d3d  jnz     short loc_180024D84
0x180024d3f  mov     rax, gs:60h
0x180024d48  mov     rcx, [rax+20h]
0x180024d4c  cmp     [rcx+8], edi
0x180024d4f  jge     short loc_180024CDE
0x180024d51  mov     rcx, cs:?gLocalComputerName@@3PEAGEA; Destination
0x180024d58  lea     r8, aLocalhost_0; "LocalHost"
0x180024d5f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180024d63  mov     r9, rbx; MaxCount
0x180024d66  lea     edx, [rbx+11h]; SizeInWords
0x180024d69  call    cs:__imp_wcsncpy_s
0x180024d6f  mov     rax, cs:?gLocalComputerName@@3PEAGEA; ushort * gLocalComputerName
0x180024d76  inc     rbx
0x180024d79  cmp     [rax+rbx*2], di
0x180024d7d  jnz     short loc_180024D76
0x180024d7f  jmp     loc_180024B5C
0x180024d84  cmp     eax, 8
0x180024d87  jz      loc_180024CDE
0x180024d8d  cmp     eax, 718h
0x180024d92  jz      short loc_180024DC1
0x180024d94  cmp     eax, 5AAh
0x180024d99  jz      short loc_180024DC1
0x180024d9b  mov     ebx, 5
0x180024da0  cmp     eax, 13h
0x180024da3  jz      loc_180024CE3
0x180024da9  cmp     eax, 281h
0x180024dae  jz      loc_180024CE3
0x180024db4  cmp     eax, ebx
0x180024db6  jz      loc_180024CE3
0x180024dbc  jmp     loc_180024CDE
0x180024dc1  mov     ebx, 6B9h
0x180024dc6  jmp     loc_180024CE3
0x180024dcb  call    ?InitializeRpcVerifier@@YAXXZ; InitializeRpcVerifier(void)
0x180024dd0  jmp     loc_180024BD3
0x180024dd5  call    ?InitializeCellHeap@@YAJXZ; InitializeCellHeap(void)
0x180024dda  mov     ebx, eax
0x180024ddc  cmp     eax, 6E4h
0x180024de1  jnz     short loc_180024DF6
0x180024de3  mov     cs:?g_fServerSideDebugInfoEnabled@@3HA, edi; int g_fServerSideDebugInfoEnabled
0x180024de9  mov     ebx, edi
0x180024deb  mov     cs:?g_fClientSideDebugInfoEnabled@@3HA, edi; int g_fClientSideDebugInfoEnabled
0x180024df1  jmp     loc_180024C47
0x180024df6  test    eax, eax
0x180024df8  jnz     loc_180024CE3
0x180024dfe  jmp     loc_180024C47
```
