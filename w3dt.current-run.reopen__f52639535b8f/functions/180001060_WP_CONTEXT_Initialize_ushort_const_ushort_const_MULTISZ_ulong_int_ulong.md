# WP_CONTEXT::Initialize(ushort const *,ushort const *,MULTISZ *,ulong,int,ulong)

- ea: `0x180001060`
- end: `0x180001767`
- name: `?Initialize@WP_CONTEXT@@QEAAJPEBG0PEAVMULTISZ@@KHK@Z`
- size: `1799`
- prototype: `int(WP_CONTEXT *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct MULTISZ *, unsigned int, int, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015660`

## callees

- `0x180001060`
- `0x180001770`
- `0x18000fad0`
- `0x180012050`
- `0x180012180`
- `0x180012530`
- `0x1800131f0`
- `0x1800143dc`
- `0x180014a4c`
- `0x180014a90`
- `0x180014af8`
- `0x1800153c8`
- `0x180015b2c`
- `0x180015bc0`
- `0x180015e08`
- `0x1800160a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180001127`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180001127`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180001145`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180001145`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1800011b5`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1800011c5`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1800011b5`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1800011c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800013d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800013d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001429`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000175a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001429`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000175a`
- `ntdll!NtSetInformationFile` at `0x18000165b`
- `ntdll!NtSetInformationFile` at `0x18000165b`
- `HTTPAPI!HttpCreateRequestQueue` at `0x1800012e8`
- `HTTPAPI!HttpCreateRequestQueue` at `0x1800015d6`
- `HTTPAPI!HttpCreateRequestQueue` at `0x1800012e8`
- `HTTPAPI!HttpCreateRequestQueue` at `0x1800015d6`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x180001748`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x180001748`
- `iisutil!PuDbgPrintError` at `0x1800014b4`
- `iisutil!PuDbgPrintError` at `0x1800014b4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000116a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000116a`
- `iisutil!PuDbgPrint` at `0x18000128b`
- `iisutil!PuDbgPrint` at `0x180001339`
- `iisutil!PuDbgPrint` at `0x18000141f`
- `iisutil!PuDbgPrint` at `0x180001561`
- `iisutil!PuDbgPrint` at `0x1800015a1`
- `iisutil!PuDbgPrint` at `0x180001627`
- `iisutil!PuDbgPrint` at `0x18000169b`
- `iisutil!PuDbgPrint` at `0x1800016e9`
- `iisutil!PuDbgPrint` at `0x180001729`
- `iisutil!PuDbgPrint` at `0x18000128b`
- `iisutil!PuDbgPrint` at `0x180001339`
- `iisutil!PuDbgPrint` at `0x18000141f`
- `iisutil!PuDbgPrint` at `0x180001561`
- `iisutil!PuDbgPrint` at `0x1800015a1`
- `iisutil!PuDbgPrint` at `0x180001627`
- `iisutil!PuDbgPrint` at `0x18000169b`
- `iisutil!PuDbgPrint` at `0x1800016e9`
- `iisutil!PuDbgPrint` at `0x180001729`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000129d`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000129d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800010b0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800010ca`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001113`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001152`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800010b0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800010ca`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001113`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001152`

## string_xrefs

- `0x1800011be`: `APP_POOL_CONFIG`
- `0x180001284`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\wpcontext.cxx`
- `0x180001418`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\wpcontext.cxx`
- `0x180001682`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\wpcontext.cxx`
- `0x1800016d0`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\wpcontext.cxx`
- `0x180001722`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\wpcontext.cxx`
- `0x1800014a9`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180001199`: `Failed to create control channel\n`
- `0x180001489`: `Failed to create request queue!\n`
- `0x1800013fb`: `Failed to associate handle with thread pool.  hr = %x\n`
- `0x180001541`: `AppPool already open!\n`
- `0x180001581`: `AppPool already open!\n`
- `0x180001327`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\apppool.cxx`
- `0x18000155a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\apppool.cxx`
- `0x18000159a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\apppool.cxx`
- `0x180001615`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\apppool.cxx`
- `0x180001310`: `Failed to open AppPool '%ws'.  rc = %d\n`
- `0x1800015fe`: `Failed to open AppPool '%ws'.  rc = %d\n`

## pseudocode

```c
__int64 __fastcall WP_CONTEXT::Initialize(
        WP_CONTEXT *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct MULTISZ *a4,
        unsigned int a5,
        int a6,
        unsigned int a7)
{
  WP_CONTEXT *v7; // rdi
  STRU *v9; // rcx
  int ControlChannel; // ebx
  const char *v13; // rax
  __int64 v14; // r8
  int v15; // eax
  UL_APP_POOL *RequestQueueHandle; // rsi
  bool v18; // sf
  const WCHAR *Str; // rdi
  signed int LastError; // eax
  UL_CONTROL_CHANNEL *v21; // rcx
  int v22; // eax
  int v23; // eax
  void *v24; // rcx
  int v25; // eax
  void *v26; // rax
  __int64 v27; // [rsp+28h] [rbp-99h]
  HTTPAPI_VERSION Version; // [rsp+40h] [rbp-81h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-79h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-71h] BYREF
  GUID pguid; // [rsp+60h] [rbp-61h] BYREF
  OLECHAR sz[8]; // [rsp+70h] [rbp-51h] BYREF
  __int128 v33; // [rsp+80h] [rbp-41h]
  __int128 v34; // [rsp+90h] [rbp-31h]
  __int128 v35; // [rsp+A0h] [rbp-21h]
  __int128 v36; // [rsp+B0h] [rbp-11h]

  v7 = g_pwpContext;
  v9 = g_pwpContext;
  SRWLock = 0;
  *((_DWORD *)g_pwpContext + 312) = a6;
  ControlChannel = STRU::Copy(v9, a2);
  if ( ControlChannel < 0 )
    return (unsigned int)ControlChannel;
  ControlChannel = STRU::Copy((WP_CONTEXT *)((char *)v7 + 184), a3);
  if ( ControlChannel < 0 )
    return (unsigned int)ControlChannel;
  if ( *((_DWORD *)v7 + 312) )
  {
    pguid = 0;
    *(_OWORD *)sz = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    ControlChannel = STRU::Copy((WP_CONTEXT *)((char *)v7 + 848), a2);
    if ( ControlChannel < 0 )
      goto LABEL_53;
    ControlChannel = CoCreateGuid(&pguid);
    if ( ControlChannel < 0 )
      goto LABEL_53;
    StringFromGUID2(&pguid, sz, 40);
    ControlChannel = STRU::Copy((WP_CONTEXT *)((char *)v7 + 904), a2);
    if ( ControlChannel < 0 )
      goto LABEL_53;
    ControlChannel = STRU::Append((WP_CONTEXT *)((char *)v7 + 904), sz);
    if ( ControlChannel < 0 )
      goto LABEL_53;
    ControlChannel = BINDING_TABLE::CreateControlChannel((WP_CONTEXT *)((char *)v7 + 832));
    if ( ControlChannel < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_53;
      v13 = "Failed to create control channel\n";
      v14 = 600;
      goto LABEL_52;
    }
    *((_DWORD *)v7 + 310) = 1;
    ControlChannel = BINDING_TABLE::ProcessSiteBindings((WP_CONTEXT *)((char *)v7 + 832));
    if ( ControlChannel < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_53;
      v13 = "Failed to process sites\n";
      v14 = 615;
      goto LABEL_52;
    }
    ControlChannel = BINDING_TABLE::CreateRequestQueue((WP_CONTEXT *)((char *)v7 + 832));
    if ( ControlChannel < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_53;
      v13 = "Failed to create request queue!\n";
      v14 = 630;
LABEL_52:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        v14,
        "BINDING_TABLE::Initialize",
        ControlChannel,
        v13);
LABEL_53:
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v27) = ControlChannel;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
          111,
          "WP_CONTEXT::Initialize",
          "Failed to initialize site bindings\n",
          v27);
      }
      return (unsigned int)ControlChannel;
    }
  }
  else
  {
    v21 = (WP_CONTEXT *)((char *)v7 + 784);
    if ( a4 )
    {
      v22 = UL_CONTROL_CHANNEL::Initialize(v21, a4, a2, a5);
      ControlChannel = v22;
      if ( v22 )
      {
        if ( v22 > 0 )
          ControlChannel = (unsigned __int16)v22 | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
            129,
            "WP_CONTEXT::Initialize",
            "SetupControlChannel failed with 0x%8x\n",
            ControlChannel);
        return (unsigned int)ControlChannel;
      }
    }
    else if ( *((_DWORD *)v7 + 199) != 1 )
    {
      v23 = HTTP_WRAPPER::Initialize(v21);
      ControlChannel = v23;
      if ( v23 )
      {
        if ( v23 > 0 )
          ControlChannel = (unsigned __int16)v23 | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
            147,
            "WP_CONTEXT::Initialize",
            "Initialize failed with 0x%08x\n",
            ControlChannel);
        return (unsigned int)ControlChannel;
      }
    }
  }
  RequestQueueHandle = (WP_CONTEXT *)((char *)v7 + 760);
  if ( *((_DWORD *)v7 + 312) )
  {
    Str = STRU::QueryStr((WP_CONTEXT *)((char *)v7 + 904));
    if ( !*(_QWORD *)RequestQueueHandle )
    {
      ControlChannel = PER_CPU__RTL_SRWLOCK_::Create__lambda_9f7522036324b4ca4a740e78e50c103c___lambda_ad80fcf7fe795745df7e5df01a45fa63___(
                         0,
                         0,
                         (char *)RequestQueueHandle + 8);
      if ( ControlChannel < 0 )
        goto LABEL_19;
      UL_APP_POOL::AcquireLockExclusive(RequestQueueHandle);
      Version = (HTTPAPI_VERSION)2;
      ControlChannel = HttpCreateRequestQueue((HTTPAPI_VERSION)2, Str, 0, 1u, (PHANDLE)RequestQueueHandle);
      if ( ControlChannel )
      {
        UL_APP_POOL::ReleaseLockExclusive(RequestQueueHandle);
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\apppool.cxx",
            114,
            "UL_APP_POOL::Initialize",
            "Failed to open AppPool '%ws'.  rc = %d\n",
            Str,
            ControlChannel);
        v18 = ControlChannel < 0;
        if ( ControlChannel > 0 )
          goto LABEL_29;
        goto LABEL_20;
      }
LABEL_69:
      v24 = *(void **)RequestQueueHandle;
      Version = (HTTPAPI_VERSION)3;
      IoStatusBlock = 0;
      NtSetInformationFile(v24, &IoStatusBlock, &Version, 4u, FileIoCompletionNotificationInformation);
      UL_APP_POOL::ReleaseLockExclusive(RequestQueueHandle);
      ControlChannel = 0;
      goto LABEL_19;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\apppool.cxx",
        70,
        "UL_APP_POOL::Initialize",
        "AppPool already open!\n");
      ControlChannel = -2147024844;
      goto LABEL_19;
    }
LABEL_65:
    ControlChannel = -2147024844;
    goto LABEL_19;
  }
  if ( *(_QWORD *)RequestQueueHandle )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\apppool.cxx",
        70,
        "UL_APP_POOL::Initialize",
        "AppPool already open!\n");
    goto LABEL_65;
  }
  ControlChannel = PER_CPU__RTL_SRWLOCK_::Create__lambda_9f7522036324b4ca4a740e78e50c103c___lambda_ad80fcf7fe795745df7e5df01a45fa63___(
                     0,
                     0,
                     (char *)v7 + 768);
  if ( ControlChannel < 0 )
  {
LABEL_19:
    v18 = ControlChannel < 0;
    goto LABEL_20;
  }
  UL_APP_POOL::AcquireLockExclusive((WP_CONTEXT *)((char *)v7 + 760));
  Version = (HTTPAPI_VERSION)2;
  ControlChannel = HttpCreateRequestQueue((HTTPAPI_VERSION)2, a2, 0, 1u, (PHANDLE)v7 + 95);
  if ( !ControlChannel )
    goto LABEL_69;
  UL_APP_POOL::ReleaseLockExclusive((WP_CONTEXT *)((char *)v7 + 760));
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\apppool.cxx",
      114,
      "UL_APP_POOL::Initialize",
      "Failed to open AppPool '%ws'.  rc = %d\n",
      a2,
      ControlChannel);
  v18 = ControlChannel < 0;
  if ( ControlChannel > 0 )
  {
LABEL_29:
    ControlChannel = (unsigned __int16)ControlChannel | 0x80070000;
    goto LABEL_19;
  }
LABEL_20:
  if ( v18 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v27) = ControlChannel;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
        171,
        "WP_CONTEXT::Initialize",
        "Failed to initialize AppPool.  hr = %x\n",
        v27);
    }
    return (unsigned int)ControlChannel;
  }
  SetEnvironmentVariableW(L"APP_POOL_ID", a2);
  SetEnvironmentVariableW(L"APP_POOL_CONFIG", a3);
  v15 = UL_NATIVE_REQUEST::Initialize(a6, a7);
  ControlChannel = v15;
  if ( v15 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
        192,
        "WP_CONTEXT::Initialize",
        "Failed to initialize UL_NATIVE_REQUEST globals.  hr = %x\n",
        v15);
    goto LABEL_14;
  }
  v25 = UL_DISCONNECT_CONTEXT::Initialize();
  ControlChannel = v25;
  if ( v25 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
        206,
        "WP_CONTEXT::Initialize",
        "Failed to initialize UL_DISCONNECT_CONTEXT globals.  hr = %x\n",
        v25);
LABEL_45:
    UL_NATIVE_REQUEST::Terminate();
LABEL_14:
    UL_APP_POOL::Cleanup(RequestQueueHandle);
    return (unsigned int)ControlChannel;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
      213,
      "WP_CONTEXT::Initialize",
      "AppPool '%ws' initialized\n",
      a2);
  v26 = UL_APP_POOL::QueryAndLockHandle(RequestQueueHandle, (void **)&SRWLock);
  if ( !ThreadPoolBindIoCompletionCallback(
          v26,
          (void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))WP_CONTEXT::OnCompletion,
          0) )
  {
    LastError = GetLastError();
    ControlChannel = LastError;
    if ( LastError > 0 )
      ControlChannel = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\wpcontext.cxx",
        226,
        "WP_CONTEXT::Initialize",
        "Failed to associate handle with thread pool.  hr = %x\n",
        ControlChannel);
    ReleaseSRWLockShared(SRWLock);
    UL_DISCONNECT_CONTEXT::Terminate();
    goto LABEL_45;
  }
  ReleaseSRWLockShared(SRWLock);
  return 0;
}

```

## disassembly

```asm
0x180001060  mov     [rsp-8+arg_0], rbx
0x180001065  push    rbp
0x180001066  push    rsi
0x180001067  push    rdi
0x180001068  push    r12
0x18000106a  push    r13
0x18000106c  push    r14
0x18000106e  push    r15
0x180001070  lea     rbp, [rsp-0Fh]
0x180001075  sub     rsp, 0D0h
0x18000107c  mov     rax, cs:__security_cookie
0x180001083  xor     rax, rsp
0x180001086  mov     [rbp+3Fh+var_40], rax
0x18000108a  mov     rdi, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x180001091  mov     rsi, r9
0x180001094  mov     r13d, [rbp+3Fh+arg_28]
0x180001098  mov     rcx, rdi
0x18000109b  mov     r15, r8
0x18000109e  mov     [rbp+3Fh+SRWLock], 0
0x1800010a6  mov     r14, rdx
0x1800010a9  mov     [rdi+4E0h], r13d
0x1800010b0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800010b6  mov     ebx, eax
0x1800010b8  test    eax, eax
0x1800010ba  js      loc_1800011F5
0x1800010c0  lea     rcx, [rdi+0B8h]
0x1800010c7  mov     rdx, r15
0x1800010ca  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800010d0  mov     ebx, eax
0x1800010d2  test    eax, eax
0x1800010d4  js      loc_1800011F5
0x1800010da  cmp     dword ptr [rdi+4E0h], 0
0x1800010e1  jz      loc_1800014E9
0x1800010e7  xorps   xmm1, xmm1
0x1800010ea  lea     rsi, [rdi+340h]
0x1800010f1  xorps   xmm0, xmm0
0x1800010f4  lea     rcx, [rsi+10h]
0x1800010f8  mov     rdx, r14
0x1800010fb  movups  xmmword ptr [rbp+3Fh+pguid.Data1], xmm0
0x1800010ff  movups  xmmword ptr [rbp+3Fh+sz], xmm1
0x180001103  movups  [rbp+3Fh+var_80], xmm1
0x180001107  movups  [rbp+3Fh+var_70], xmm1
0x18000110b  movups  [rbp+3Fh+var_60], xmm1
0x18000110f  movups  [rbp+3Fh+var_50], xmm1
0x180001113  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001119  mov     ebx, eax
0x18000111b  test    eax, eax
0x18000111d  js      loc_1800014BA
0x180001123  lea     rcx, [rbp+3Fh+pguid]; pguid
0x180001127  call    cs:__imp_CoCreateGuid
0x18000112d  mov     ebx, eax
0x18000112f  test    eax, eax
0x180001131  js      loc_1800014BA
0x180001137  mov     r8d, 28h ; '('; cchMax
0x18000113d  lea     rdx, [rbp+3Fh+sz]; lpsz
0x180001141  lea     rcx, [rbp+3Fh+pguid]; rguid
0x180001145  call    cs:__imp_StringFromGUID2
0x18000114b  mov     rdx, r14
0x18000114e  lea     rcx, [rsi+48h]
0x180001152  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001158  mov     ebx, eax
0x18000115a  test    eax, eax
0x18000115c  js      loc_1800014BA
0x180001162  lea     rdx, [rbp+3Fh+sz]
0x180001166  lea     rcx, [rsi+48h]
0x18000116a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180001170  mov     ebx, eax
0x180001172  test    eax, eax
0x180001174  js      loc_1800014BA
0x18000117a  mov     rcx, rsi; this
0x18000117d  call    ?CreateControlChannel@BINDING_TABLE@@AEAAJXZ; BINDING_TABLE::CreateControlChannel(void)
0x180001182  mov     ebx, eax
0x180001184  test    eax, eax
0x180001186  jns     loc_18000143E
0x18000118c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001193  jz      loc_1800014BA
0x180001199  lea     rax, aFailedToCreate_0; "Failed to create control channel\n"
0x1800011a0  mov     r8d, 258h
0x1800011a6  jmp     loc_180001496
0x1800011ab  mov     rdx, r14; lpValue
0x1800011ae  lea     rcx, Name; "APP_POOL_ID"
0x1800011b5  call    cs:__imp_SetEnvironmentVariableW
0x1800011bb  mov     rdx, r15; lpValue
0x1800011be  lea     rcx, aAppPoolConfig; "APP_POOL_CONFIG"
0x1800011c5  call    cs:__imp_SetEnvironmentVariableW
0x1800011cb  mov     edx, [rbp+3Fh+arg_30]; unsigned int
0x1800011ce  mov     ecx, r13d; int
0x1800011d1  call    ?Initialize@UL_NATIVE_REQUEST@@SAJHK@Z; UL_NATIVE_REQUEST::Initialize(int,ulong)
0x1800011d6  mov     ebx, eax
0x1800011d8  test    eax, eax
0x1800011da  jns     loc_1800016A6
0x1800011e0  test    byte ptr cs:g_dwDebugFlags, 3
0x1800011e7  jnz     loc_180001670
0x1800011ed  mov     rcx, rsi; this
0x1800011f0  call    ?Cleanup@UL_APP_POOL@@QEAAJXZ; UL_APP_POOL::Cleanup(void)
0x1800011f5  mov     eax, ebx
0x1800011f7  mov     rcx, [rbp+3Fh+var_40]
0x1800011fb  xor     rcx, rsp; StackCookie
0x1800011fe  call    __security_check_cookie
0x180001203  mov     rbx, [rsp+100h+arg_0]
0x18000120b  add     rsp, 0D0h
0x180001212  pop     r15
0x180001214  pop     r14
0x180001216  pop     r13
0x180001218  pop     r12
0x18000121a  pop     rdi
0x18000121b  pop     rsi
0x18000121c  pop     rbp
0x18000121d  retn
0x18000121e  cmp     dword ptr [rdi+4E0h], 0
0x180001225  lea     rsi, [rdi+2F8h]
0x18000122c  jnz     short loc_180001296
0x18000122e  cmp     qword ptr [rsi], 0
0x180001232  jnz     loc_180001571
0x180001238  lea     r8, [rsi+8]
0x18000123c  xor     edx, edx
0x18000123e  xor     ecx, ecx
0x180001240  call    PER_CPU__RTL_SRWLOCK___Create__lambda_9f7522036324b4ca4a740e78e50c103c___lambda_ad80fcf7fe795745df7e5df01a45fa63___
0x180001245  mov     ebx, eax
0x180001247  test    eax, eax
0x180001249  jns     loc_1800015B1
0x18000124f  test    ebx, ebx
0x180001251  jns     loc_1800011AB
0x180001257  test    byte ptr cs:g_dwDebugFlags, 3
0x18000125e  jz      short loc_1800011F5
0x180001260  lea     rax, aFailedToInitia_2; "Failed to initialize AppPool.  hr = %x"...
0x180001267  mov     dword ptr [rsp+100h+var_D8], ebx
0x18000126b  mov     [rsp+100h+RequestQueueHandle], rax
0x180001270  lea     r9, aWpContextIniti; "WP_CONTEXT::Initialize"
0x180001277  mov     r8d, 0ABh
0x18000127d  mov     rcx, cs:g_pDebug
0x180001284  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000128b  call    cs:__imp_PuDbgPrint
0x180001291  jmp     loc_1800011F5
0x180001296  lea     rcx, [rdi+388h]
0x18000129d  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800012a3  cmp     qword ptr [rsi], 0
0x1800012a7  mov     rdi, rax
0x1800012aa  jnz     loc_180001531
0x1800012b0  lea     r8, [rsi+8]
0x1800012b4  xor     edx, edx
0x1800012b6  xor     ecx, ecx
0x1800012b8  call    PER_CPU__RTL_SRWLOCK___Create__lambda_9f7522036324b4ca4a740e78e50c103c___lambda_ad80fcf7fe795745df7e5df01a45fa63___
0x1800012bd  mov     ebx, eax
0x1800012bf  test    eax, eax
0x1800012c1  js      short loc_18000124F
0x1800012c3  mov     rcx, rsi; this
0x1800012c6  call    ?AcquireLockExclusive@UL_APP_POOL@@AEAAXXZ; UL_APP_POOL::AcquireLockExclusive(void)
0x1800012cb  mov     dword ptr [rsp+100h+Version.HttpApiMajorVersion], 2
0x1800012d3  mov     r9d, 1; Flags
0x1800012d9  mov     ecx, dword ptr [rsp+100h+Version.HttpApiMajorVersion]; Version
0x1800012dd  xor     r8d, r8d; SecurityAttributes
0x1800012e0  mov     rdx, rdi; Name
0x1800012e3  mov     [rsp+100h+RequestQueueHandle], rsi; RequestQueueHandle
0x1800012e8  call    cs:__imp_HttpCreateRequestQueue
0x1800012ee  mov     ebx, eax
0x1800012f0  test    eax, eax
0x1800012f2  jz      loc_180001632
0x1800012f8  mov     rcx, rsi; this
0x1800012fb  call    ?ReleaseLockExclusive@UL_APP_POOL@@AEAAXXZ; UL_APP_POOL::ReleaseLockExclusive(void)
0x180001300  test    byte ptr cs:g_dwDebugFlags, 3
0x180001307  jz      short loc_18000133F
0x180001309  mov     rcx, cs:g_pDebug
0x180001310  lea     rax, aFailedToOpenAp; "Failed to open AppPool '%ws'.  rc = %d"...
0x180001317  mov     [rsp+100h+var_D0], ebx
0x18000131b  lea     r9, aUlAppPoolIniti; "UL_APP_POOL::Initialize"
0x180001322  mov     [rsp+100h+var_D8], rdi
0x180001327  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000132e  mov     r8d, 72h ; 'r'
0x180001334  mov     [rsp+100h+RequestQueueHandle], rax
0x180001339  call    cs:__imp_PuDbgPrint
0x18000133f  test    ebx, ebx
0x180001341  jle     loc_180001251
0x180001347  movzx   ebx, bx
0x18000134a  or      ebx, 80070000h
0x180001350  jmp     loc_18000124F
0x180001355  jle     short loc_180001360
0x180001357  movzx   ebx, ax
0x18000135a  or      ebx, 80070000h
0x180001360  test    byte ptr cs:g_dwDebugFlags, 3
0x180001367  jz      loc_1800011F5
0x18000136d  lea     rax, aSetupcontrolch; "SetupControlChannel failed with 0x%8x\n"
0x180001374  mov     dword ptr [rsp+100h+var_D8], ebx
0x180001378  mov     [rsp+100h+RequestQueueHandle], rax
0x18000137d  lea     r9, aWpContextIniti; "WP_CONTEXT::Initialize"
0x180001384  mov     r8d, 81h
0x18000138a  jmp     loc_18000127D
0x18000138f  jle     short loc_18000139A
0x180001391  movzx   ebx, ax
0x180001394  or      ebx, 80070000h
0x18000139a  test    byte ptr cs:g_dwDebugFlags, 3
0x1800013a1  jz      loc_1800011F5
0x1800013a7  lea     rax, aInitializeFail; "Initialize failed with 0x%08x\n"
0x1800013ae  mov     dword ptr [rsp+100h+var_D8], ebx
0x1800013b2  mov     [rsp+100h+RequestQueueHandle], rax
0x1800013b7  lea     r9, aWpContextIniti; "WP_CONTEXT::Initialize"
0x1800013be  mov     r8d, 93h
0x1800013c4  jmp     loc_18000127D
0x1800013c9  test    ebx, ebx
0x1800013cb  jle     loc_180001251
0x1800013d1  jmp     loc_180001347
0x1800013d6  call    cs:__imp_GetLastError
0x1800013dc  mov     ebx, eax
0x1800013de  test    eax, eax
0x1800013e0  jle     short loc_1800013EB
0x1800013e2  movzx   ebx, ax
0x1800013e5  or      ebx, 80070000h
0x1800013eb  test    byte ptr cs:g_dwDebugFlags, 3
0x1800013f2  jz      short loc_180001425
0x1800013f4  mov     rcx, cs:g_pDebug
0x1800013fb  lea     rax, aFailedToAssoci; "Failed to associate handle with thread "...
0x180001402  mov     dword ptr [rsp+100h+var_D8], ebx
0x180001406  lea     r9, aWpContextIniti; "WP_CONTEXT::Initialize"
0x18000140d  mov     r8d, 0E2h
0x180001413  mov     [rsp+100h+RequestQueueHandle], rax
0x180001418  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000141f  call    cs:__imp_PuDbgPrint
0x180001425  mov     rcx, [rbp+3Fh+SRWLock]; SRWLock
0x180001429  call    cs:__imp_ReleaseSRWLockShared
0x18000142f  call    ?Terminate@UL_DISCONNECT_CONTEXT@@SAXXZ; UL_DISCONNECT_CONTEXT::Terminate(void)
0x180001434  call    ?Terminate@UL_NATIVE_REQUEST@@SAXXZ; UL_NATIVE_REQUEST::Terminate(void)
0x180001439  jmp     loc_1800011ED
0x18000143e  mov     rcx, rsi; this
0x180001441  mov     dword ptr [rsi+198h], 1
0x18000144b  call    ?ProcessSiteBindings@BINDING_TABLE@@AEAAJXZ; BINDING_TABLE::ProcessSiteBindings(void)
0x180001450  mov     ebx, eax
0x180001452  test    eax, eax
0x180001454  jns     short loc_18000146E
0x180001456  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000145d  jz      short loc_1800014BA
0x18000145f  lea     rax, aFailedToProces; "Failed to process sites\n"
0x180001466  mov     r8d, 267h
0x18000146c  jmp     short loc_180001496
0x18000146e  mov     rcx, rsi; this
0x180001471  call    ?CreateRequestQueue@BINDING_TABLE@@AEAAJXZ; BINDING_TABLE::CreateRequestQueue(void)
0x180001476  mov     ebx, eax
0x180001478  test    eax, eax
0x18000147a  jns     loc_18000121E
0x180001480  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001487  jz      short loc_1800014BA
0x180001489  lea     rax, aFailedToCreate; "Failed to create request queue!\n"
0x180001490  mov     r8d, 276h
0x180001496  mov     rcx, cs:g_pDebug
0x18000149d  lea     r9, aBindingTableIn; "BINDING_TABLE::Initialize"
0x1800014a4  mov     [rsp+100h+var_D8], rax
0x1800014a9  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800014b0  mov     dword ptr [rsp+100h+RequestQueueHandle], ebx
0x1800014b4  call    cs:__imp_PuDbgPrintError
0x1800014ba  test    byte ptr cs:g_dwDebugFlags, 3
0x1800014c1  jz      loc_1800011F5
0x1800014c7  lea     rax, aFailedToInitia_0; "Failed to initialize site bindings\n"
0x1800014ce  mov     dword ptr [rsp+100h+var_D8], ebx
0x1800014d2  mov     [rsp+100h+RequestQueueHandle], rax
0x1800014d7  lea     r9, aWpContextIniti; "WP_CONTEXT::Initialize"
0x1800014de  mov     r8d, 6Fh ; 'o'
0x1800014e4  jmp     loc_18000127D
0x1800014e9  lea     rcx, [rdi+310h]; this
0x1800014f0  test    rsi, rsi
0x1800014f3  jz      short loc_180001513
0x1800014f5  mov     r9d, [rbp+3Fh+arg_20]; unsigned int
0x1800014f9  mov     r8, r14; unsigned __int16 *
0x1800014fc  mov     rdx, rsi; struct MULTISZ *
0x1800014ff  call    ?Initialize@UL_CONTROL_CHANNEL@@QEAAKAEBVMULTISZ@@PEBGK@Z; UL_CONTROL_CHANNEL::Initialize(MULTISZ const &,ushort const *,ulong)
0x180001504  mov     ebx, eax
0x180001506  test    eax, eax
0x180001508  jz      loc_18000121E
0x18000150e  jmp     loc_180001355
0x180001513  cmp     dword ptr [rcx+0Ch], 1
0x180001517  jz      loc_18000121E
0x18000151d  call    ?Initialize@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::Initialize(void)
0x180001522  mov     ebx, eax
0x180001524  test    eax, eax
0x180001526  jz      loc_18000121E
0x18000152c  jmp     loc_18000138F
0x180001531  test    byte ptr cs:g_dwDebugFlags, 3
0x180001538  jz      short loc_1800015A7
0x18000153a  mov     rcx, cs:g_pDebug
0x180001541  lea     rax, aApppoolAlready; "AppPool already open!\n"
0x180001548  lea     r9, aUlAppPoolIniti; "UL_APP_POOL::Initialize"
0x18000154f  mov     [rsp+100h+RequestQueueHandle], rax
0x180001554  mov     r8d, 46h ; 'F'
0x18000155a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001561  call    cs:__imp_PuDbgPrint
0x180001567  mov     ebx, 80070034h
0x18000156c  jmp     loc_18000124F
0x180001571  test    byte ptr cs:g_dwDebugFlags, 3
0x180001578  jz      short loc_1800015A7
0x18000157a  mov     rcx, cs:g_pDebug
0x180001581  lea     rax, aApppoolAlready; "AppPool already open!\n"
0x180001588  lea     r9, aUlAppPoolIniti; "UL_APP_POOL::Initialize"
0x18000158f  mov     [rsp+100h+RequestQueueHandle], rax
0x180001594  mov     r8d, 46h ; 'F'
0x18000159a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800015a1  call    cs:__imp_PuDbgPrint
0x1800015a7  mov     ebx, 80070034h
0x1800015ac  jmp     loc_18000124F
0x1800015b1  mov     rcx, rsi; this
0x1800015b4  call    ?AcquireLockExclusive@UL_APP_POOL@@AEAAXXZ; UL_APP_POOL::AcquireLockExclusive(void)
0x1800015b9  mov     dword ptr [rsp+100h+Version.HttpApiMajorVersion], 2
0x1800015c1  mov     r9d, 1; Flags
  ... truncated ...
```
