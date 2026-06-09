# AppHostInitialize(APPHOST_CONFIG *,WP_COUNTERS_MANAGER_INFO *,int)

- ea: `0x180003540`
- end: `0x18000377b`
- name: `?AppHostInitialize@@YAJPEAUAPPHOST_CONFIG@@PEAUWP_COUNTERS_MANAGER_INFO@@H@Z`
- size: `571`
- prototype: `__int64 __fastcall(struct APPHOST_CONFIG *, struct WP_COUNTERS_MANAGER_INFO *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001890`
- `0x180002090`
- `0x180002b68`
- `0x180003188`
- `0x180003540`
- `0x18000561c`
- `0x180007398`
- `0x180007680`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003583`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003583`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003641`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003641`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003564`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003564`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000359b`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x18000359b`
- `iisutil!IISGetPlatformType` at `0x1800035ad`
- `iisutil!IISGetPlatformType` at `0x1800035ad`
- `iisutil!PuDbgPrint` at `0x18000367d`
- `iisutil!PuDbgPrint` at `0x1800036e1`
- `iisutil!PuDbgPrint` at `0x18000367d`
- `iisutil!PuDbgPrint` at `0x1800036e1`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000370c`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000370c`

## string_xrefs

- `0x18000357c`: `Unable to Create Debug Print Object \n`
- `0x180003594`: `System\CurrentControlSet\Services\WAS\Parameters\apphost`
- `0x1800036ba`: `Failed to create the W3WP_HOST  hr = %x\n`
- `0x1800036d5`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003676`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall AppHostInitialize(struct APPHOST_CONFIG *a1, struct WP_COUNTERS_MANAGER_INFO *a2, int a3)
{
  W3WP_HOST *v6; // rax
  W3WP_HOST *v7; // rax
  int v8; // eax
  unsigned int v9; // edx
  unsigned int v10; // edi
  W3WP_HOST *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // [rsp+58h] [rbp+20h] BYREF

  g_pDebug = PuCreateDebugPrintsObject("w3wphost", 1);
  if ( !g_pDebug )
    OutputDebugStringA("Unable to Create Debug Print Object \n");
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\WAS\\Parameters\\apphost", 8);
  IISGetPlatformType();
  v6 = (W3WP_HOST *)operator new(0x648u);
  if ( !v6 )
  {
    g_pW3WPHost = 0;
LABEL_15:
    v10 = -2147024882;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        522,
        "AppHostInitialize",
        "Failed to create the W3WP_HOST  hr = %x\n",
        -2147024882);
    goto LABEL_17;
  }
  v7 = W3WP_HOST::W3WP_HOST(v6, a1);
  g_pW3WPHost = v7;
  if ( !v7 )
    goto LABEL_15;
  v8 = W3WP_HOST::InitializeInstance(v7, a2);
  v10 = v8;
  if ( v8 >= 0 )
  {
    if ( !a3 )
      return 0;
    v12 = g_pW3WPHost;
    v13 = *((_QWORD *)g_pW3WPHost + 11);
    if ( !v13 )
      goto LABEL_22;
    WaitForSingleObject(*(HANDLE *)(v13 + 16), 0xFFFFFFFF);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
        1592,
        "WP_IPM::WaitForShutdown",
        "Shutdown event signalled\n");
    W3WP_HOST::ShutdownProcess(v12, *(_DWORD *)(*((_QWORD *)v12 + 11) + 40LL));
    goto LABEL_21;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      534,
      "AppHostInitialize",
      "Failed to initialize the W3WP_HOST  hr = %x\n",
      v8);
LABEL_17:
  if ( !g_pW3WPHost )
    goto LABEL_24;
  EVENT_LOG::LogEvent((W3WP_HOST *)((char *)g_pW3WPHost + 80), 0xC00008E4, 0, 0, v10);
  v12 = g_pW3WPHost;
  if ( !g_pW3WPHost )
    goto LABEL_24;
  v14 = *((_QWORD *)g_pW3WPHost + 11);
  if ( v14 )
  {
    v15 = v10;
    WP_IPM::WriteMessage(v14, 11, 4, &v15);
LABEL_21:
    v12 = g_pW3WPHost;
  }
LABEL_22:
  if ( v12 )
  {
    W3WP_HOST::`scalar deleting destructor'(v12, v9);
    g_pW3WPHost = 0;
  }
LABEL_24:
  CLR_HOSTING::Terminate();
  return v10;
}

```

## disassembly

```asm
0x180003540  mov     [rsp+arg_0], rbx
0x180003545  mov     [rsp+arg_8], rsi
0x18000354a  push    rdi
0x18000354b  sub     rsp, 30h
0x18000354f  mov     rsi, rdx
0x180003552  mov     rdi, rcx
0x180003555  mov     edx, 1
0x18000355a  lea     rcx, aW3wphost; "w3wphost"
0x180003561  mov     ebx, r8d
0x180003564  call    cs:__imp_PuCreateDebugPrintsObject
0x18000356b  nop     dword ptr [rax+rax+00h]
0x180003570  mov     cs:g_pDebug, rax
0x180003577  test    rax, rax
0x18000357a  jnz     short loc_18000358F
0x18000357c  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x180003583  call    cs:__imp_OutputDebugStringA
0x18000358a  nop     dword ptr [rax+rax+00h]
0x18000358f  mov     edx, 8
0x180003594  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WA"...
0x18000359b  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x1800035a2  nop     dword ptr [rax+rax+00h]
0x1800035a7  mov     cs:g_dwDebugFlags, eax
0x1800035ad  call    cs:__imp_IISGetPlatformType
0x1800035b4  nop     dword ptr [rax+rax+00h]
0x1800035b9  mov     ecx, 648h; Size
0x1800035be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800035c3  test    rax, rax
0x1800035c6  jz      loc_18000369D
0x1800035cc  mov     rdx, rdi; struct APPHOST_CONFIG *
0x1800035cf  mov     rcx, rax; this
0x1800035d2  call    ??0W3WP_HOST@@QEAA@PEAUAPPHOST_CONFIG@@@Z; W3WP_HOST::W3WP_HOST(APPHOST_CONFIG *)
0x1800035d7  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, rax; W3WP_HOST * g_pW3WPHost
0x1800035de  test    rax, rax
0x1800035e1  jz      loc_1800036A8
0x1800035e7  mov     rdx, rsi; struct WP_COUNTERS_MANAGER_INFO *
0x1800035ea  mov     rcx, rax; this
0x1800035ed  call    ?InitializeInstance@W3WP_HOST@@QEAAJPEAUWP_COUNTERS_MANAGER_INFO@@@Z; W3WP_HOST::InitializeInstance(WP_COUNTERS_MANAGER_INFO *)
0x1800035f2  mov     edi, eax
0x1800035f4  test    eax, eax
0x1800035f6  jns     short loc_18000361B
0x1800035f8  test    byte ptr cs:g_dwDebugFlags, 3
0x1800035ff  jz      loc_1800036ED
0x180003605  mov     [rsp+38h+var_10], eax
0x180003609  mov     r8d, 216h
0x18000360f  lea     rax, aFailedToInitia_4; "Failed to initialize the W3WP_HOST  hr "...
0x180003616  jmp     loc_1800036C7
0x18000361b  test    ebx, ebx
0x18000361d  jnz     short loc_180003626
0x18000361f  xor     eax, eax
0x180003621  jmp     loc_18000376A
0x180003626  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000362d  mov     rcx, [rbx+58h]
0x180003631  test    rcx, rcx
0x180003634  jz      loc_18000374B
0x18000363a  mov     rcx, [rcx+10h]; hHandle
0x18000363e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003641  call    cs:__imp_WaitForSingleObject
0x180003648  nop     dword ptr [rax+rax+00h]
0x18000364d  test    byte ptr cs:g_dwDebugFlags, 3
0x180003654  jz      short loc_180003689
0x180003656  mov     rcx, cs:g_pDebug
0x18000365d  lea     rax, aShutdownEventS; "Shutdown event signalled\n"
0x180003664  lea     r9, aWpIpmWaitforsh; "WP_IPM::WaitForShutdown"
0x18000366b  mov     [rsp+38h+var_18], rax
0x180003670  mov     r8d, 638h
0x180003676  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000367d  call    cs:__imp_PuDbgPrint
0x180003684  nop     dword ptr [rax+rax+00h]
0x180003689  mov     rdx, [rbx+58h]
0x18000368d  mov     rcx, rbx; this
0x180003690  mov     edx, [rdx+28h]; int
0x180003693  call    ?ShutdownProcess@W3WP_HOST@@QEAAXH@Z; W3WP_HOST::ShutdownProcess(int)
0x180003698  jmp     loc_180003744
0x18000369d  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, 0; W3WP_HOST * g_pW3WPHost
0x1800036a8  test    byte ptr cs:g_dwDebugFlags, 3
0x1800036af  mov     edi, 8007000Eh
0x1800036b4  jz      short loc_1800036ED
0x1800036b6  mov     [rsp+38h+var_10], edi
0x1800036ba  lea     rax, aFailedToCreate; "Failed to create the W3WP_HOST  hr = %x"...
0x1800036c1  mov     r8d, 20Ah
0x1800036c7  mov     rcx, cs:g_pDebug
0x1800036ce  lea     r9, aApphostinitial_0; "AppHostInitialize"
0x1800036d5  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800036dc  mov     [rsp+38h+var_18], rax
0x1800036e1  call    cs:__imp_PuDbgPrint
0x1800036e8  nop     dword ptr [rax+rax+00h]
0x1800036ed  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800036f4  test    rcx, rcx
0x1800036f7  jz      short loc_180003763
0x1800036f9  xor     r8d, r8d
0x1800036fc  mov     dword ptr [rsp+38h+var_18], edi
0x180003700  add     rcx, 50h ; 'P'
0x180003704  xor     r9d, r9d
0x180003707  mov     edx, 0C00008E4h
0x18000370c  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180003713  nop     dword ptr [rax+rax+00h]
0x180003718  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000371f  test    rbx, rbx
0x180003722  jz      short loc_180003763
0x180003724  mov     rcx, [rbx+58h]
0x180003728  test    rcx, rcx
0x18000372b  jz      short loc_18000374B
0x18000372d  mov     edx, 0Bh
0x180003732  mov     [rsp+38h+arg_18], edi
0x180003736  lea     r9, [rsp+38h+arg_18]
0x18000373b  lea     r8d, [rdx-7]
0x18000373f  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180003744  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000374b  test    rbx, rbx
0x18000374e  jz      short loc_180003763
0x180003750  mov     rcx, rbx; this
0x180003753  call    ??_GW3WP_HOST@@QEAAPEAXI@Z; W3WP_HOST::`scalar deleting destructor'(uint)
0x180003758  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, 0; W3WP_HOST * g_pW3WPHost
0x180003763  call    ?Terminate@CLR_HOSTING@@SAXXZ; CLR_HOSTING::Terminate(void)
0x180003768  mov     eax, edi
0x18000376a  mov     rbx, [rsp+38h+arg_0]
0x18000376f  mov     rsi, [rsp+38h+arg_8]
0x180003774  add     rsp, 30h
0x180003778  pop     rdi
0x180003779  retn
```
