# AppHostInitialize(APPHOST_CONFIG *,WP_COUNTERS_MANAGER_INFO *,int)

- ea: `0x180003340`
- end: `0x18000354a`
- name: `?AppHostInitialize@@YAJPEAUAPPHOST_CONFIG@@PEAUWP_COUNTERS_MANAGER_INFO@@H@Z`
- size: `522`
- prototype: `__int64 __fastcall(struct APPHOST_CONFIG *, struct WP_COUNTERS_MANAGER_INFO *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001830`
- `0x180001f68`
- `0x180002a00`
- `0x180002fb0`
- `0x180003340`
- `0x1800051dc`
- `0x180006cd8`
- `0x180006fa4`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000337d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000337d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003429`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003429`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003364`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003364`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000338f`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000338f`
- `iisutil!IISGetPlatformType` at `0x18000339b`
- `iisutil!IISGetPlatformType` at `0x18000339b`
- `iisutil!PuDbgPrint` at `0x18000345f`
- `iisutil!PuDbgPrint` at `0x1800034bd`
- `iisutil!PuDbgPrint` at `0x18000345f`
- `iisutil!PuDbgPrint` at `0x1800034bd`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800034e2`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800034e2`

## string_xrefs

- `0x180003376`: `Unable to Create Debug Print Object \n`
- `0x180003388`: `System\CurrentControlSet\Services\WAS\Parameters\apphost`
- `0x180003496`: `Failed to create the W3WP_HOST  hr = %x\n`
- `0x1800034b1`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003458`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall AppHostInitialize(struct APPHOST_CONFIG *a1, struct WP_COUNTERS_MANAGER_INFO *a2, int a3)
{
  W3WP_HOST *v6; // rax
  W3WP_HOST *v7; // rax
  unsigned int v8; // edx
  signed int v9; // edi
  __int64 v10; // r8
  const char *v11; // rax
  W3WP_HOST *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rcx
  signed int v16; // [rsp+58h] [rbp+20h] BYREF

  g_pDebug = PuCreateDebugPrintsObject("w3wphost", 1);
  if ( !g_pDebug )
    OutputDebugStringA("Unable to Create Debug Print Object \n");
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\WAS\\Parameters\\apphost", 8);
  IISGetPlatformType();
  v6 = (W3WP_HOST *)operator new(0x648u);
  if ( v6 )
  {
    v7 = W3WP_HOST::W3WP_HOST(v6, a1);
    g_pW3WPHost = v7;
    if ( v7 )
    {
      v9 = W3WP_HOST::InitializeInstance(v7, a2);
      if ( v9 >= 0 )
      {
        if ( !a3 )
          return 0;
        v13 = g_pW3WPHost;
        v14 = *((_QWORD *)g_pW3WPHost + 11);
        if ( !v14 )
          goto LABEL_23;
        WaitForSingleObject(*(HANDLE *)(v14 + 16), 0xFFFFFFFF);
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
            1592,
            "WP_IPM::WaitForShutdown",
            "Shutdown event signalled\n");
        W3WP_HOST::ShutdownProcess(v13, *(_DWORD *)(*((_QWORD *)v13 + 11) + 40LL));
        goto LABEL_22;
      }
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v10 = 534;
        v11 = "Failed to initialize the W3WP_HOST  hr = %x\n";
LABEL_17:
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
          v10,
          "AppHostInitialize",
          v11);
        goto LABEL_18;
      }
      goto LABEL_18;
    }
  }
  else
  {
    g_pW3WPHost = 0;
  }
  v9 = -2147024882;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v11 = "Failed to create the W3WP_HOST  hr = %x\n";
    v10 = 522;
    goto LABEL_17;
  }
LABEL_18:
  if ( !g_pW3WPHost )
    goto LABEL_25;
  EVENT_LOG::LogEvent((W3WP_HOST *)((char *)g_pW3WPHost + 80), 0xC00008E4, 0, 0, v9);
  v13 = g_pW3WPHost;
  if ( !g_pW3WPHost )
    goto LABEL_25;
  v15 = *((_QWORD *)g_pW3WPHost + 11);
  if ( v15 )
  {
    v16 = v9;
    WP_IPM::WriteMessage(v15, 11, 4, &v16);
LABEL_22:
    v13 = g_pW3WPHost;
  }
LABEL_23:
  if ( v13 )
  {
    W3WP_HOST::`scalar deleting destructor'(v13, v8);
    g_pW3WPHost = 0;
  }
LABEL_25:
  CLR_HOSTING::Terminate();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003340  mov     [rsp+arg_0], rbx
0x180003345  mov     [rsp+arg_8], rsi
0x18000334a  push    rdi
0x18000334b  sub     rsp, 30h
0x18000334f  mov     rsi, rdx
0x180003352  mov     rdi, rcx
0x180003355  mov     edx, 1
0x18000335a  lea     rcx, aW3wphost; "w3wphost"
0x180003361  mov     ebx, r8d
0x180003364  call    cs:__imp_PuCreateDebugPrintsObject
0x18000336a  mov     cs:g_pDebug, rax
0x180003371  test    rax, rax
0x180003374  jnz     short loc_180003383
0x180003376  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x18000337d  call    cs:__imp_OutputDebugStringA
0x180003383  mov     edx, 8
0x180003388  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WA"...
0x18000338f  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180003395  mov     cs:g_dwDebugFlags, eax
0x18000339b  call    cs:__imp_IISGetPlatformType
0x1800033a1  mov     ecx, 648h; Size
0x1800033a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800033ab  test    rax, rax
0x1800033ae  jz      loc_180003479
0x1800033b4  mov     rdx, rdi; struct APPHOST_CONFIG *
0x1800033b7  mov     rcx, rax; this
0x1800033ba  call    ??0W3WP_HOST@@QEAA@PEAUAPPHOST_CONFIG@@@Z; W3WP_HOST::W3WP_HOST(APPHOST_CONFIG *)
0x1800033bf  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, rax; W3WP_HOST * g_pW3WPHost
0x1800033c6  test    rax, rax
0x1800033c9  jz      loc_180003484
0x1800033cf  mov     rdx, rsi; struct WP_COUNTERS_MANAGER_INFO *
0x1800033d2  mov     rcx, rax; this
0x1800033d5  call    ?InitializeInstance@W3WP_HOST@@QEAAJPEAUWP_COUNTERS_MANAGER_INFO@@@Z; W3WP_HOST::InitializeInstance(WP_COUNTERS_MANAGER_INFO *)
0x1800033da  mov     edi, eax
0x1800033dc  test    eax, eax
0x1800033de  jns     short loc_180003403
0x1800033e0  test    byte ptr cs:g_dwDebugFlags, 3
0x1800033e7  jz      loc_1800034C3
0x1800033ed  mov     [rsp+38h+var_10], eax
0x1800033f1  mov     r8d, 216h
0x1800033f7  lea     rax, aFailedToInitia_4; "Failed to initialize the W3WP_HOST  hr "...
0x1800033fe  jmp     loc_1800034A3
0x180003403  test    ebx, ebx
0x180003405  jnz     short loc_18000340E
0x180003407  xor     eax, eax
0x180003409  jmp     loc_18000353A
0x18000340e  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180003415  mov     rcx, [rbx+58h]
0x180003419  test    rcx, rcx
0x18000341c  jz      loc_18000351B
0x180003422  mov     rcx, [rcx+10h]; hHandle
0x180003426  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003429  call    cs:__imp_WaitForSingleObject
0x18000342f  test    byte ptr cs:g_dwDebugFlags, 3
0x180003436  jz      short loc_180003465
0x180003438  mov     rcx, cs:g_pDebug
0x18000343f  lea     rax, aShutdownEventS; "Shutdown event signalled\n"
0x180003446  lea     r9, aWpIpmWaitforsh; "WP_IPM::WaitForShutdown"
0x18000344d  mov     [rsp+38h+var_18], rax
0x180003452  mov     r8d, 638h
0x180003458  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000345f  call    cs:__imp_PuDbgPrint
0x180003465  mov     rdx, [rbx+58h]
0x180003469  mov     rcx, rbx; this
0x18000346c  mov     edx, [rdx+28h]; int
0x18000346f  call    ?ShutdownProcess@W3WP_HOST@@QEAAXH@Z; W3WP_HOST::ShutdownProcess(int)
0x180003474  jmp     loc_180003514
0x180003479  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, 0; W3WP_HOST * g_pW3WPHost
0x180003484  test    byte ptr cs:g_dwDebugFlags, 3
0x18000348b  mov     edi, 8007000Eh
0x180003490  jz      short loc_1800034C3
0x180003492  mov     [rsp+38h+var_10], edi
0x180003496  lea     rax, aFailedToCreate; "Failed to create the W3WP_HOST  hr = %x"...
0x18000349d  mov     r8d, 20Ah
0x1800034a3  mov     rcx, cs:g_pDebug
0x1800034aa  lea     r9, aApphostinitial_0; "AppHostInitialize"
0x1800034b1  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800034b8  mov     [rsp+38h+var_18], rax
0x1800034bd  call    cs:__imp_PuDbgPrint
0x1800034c3  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800034ca  test    rcx, rcx
0x1800034cd  jz      short loc_180003533
0x1800034cf  xor     r8d, r8d
0x1800034d2  mov     dword ptr [rsp+38h+var_18], edi
0x1800034d6  add     rcx, 50h ; 'P'
0x1800034da  xor     r9d, r9d
0x1800034dd  mov     edx, 0C00008E4h
0x1800034e2  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800034e8  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800034ef  test    rbx, rbx
0x1800034f2  jz      short loc_180003533
0x1800034f4  mov     rcx, [rbx+58h]
0x1800034f8  test    rcx, rcx
0x1800034fb  jz      short loc_18000351B
0x1800034fd  mov     edx, 0Bh
0x180003502  mov     [rsp+38h+arg_18], edi
0x180003506  lea     r9, [rsp+38h+arg_18]
0x18000350b  lea     r8d, [rdx-7]
0x18000350f  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180003514  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000351b  test    rbx, rbx
0x18000351e  jz      short loc_180003533
0x180003520  mov     rcx, rbx; this
0x180003523  call    ??_GW3WP_HOST@@QEAAPEAXI@Z; W3WP_HOST::`scalar deleting destructor'(uint)
0x180003528  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, 0; W3WP_HOST * g_pW3WPHost
0x180003533  call    ?Terminate@CLR_HOSTING@@SAXXZ; CLR_HOSTING::Terminate(void)
0x180003538  mov     eax, edi
0x18000353a  mov     rbx, [rsp+38h+arg_0]
0x18000353f  mov     rsi, [rsp+38h+arg_8]
0x180003544  add     rsp, 30h
0x180003548  pop     rdi
0x180003549  retn
```
