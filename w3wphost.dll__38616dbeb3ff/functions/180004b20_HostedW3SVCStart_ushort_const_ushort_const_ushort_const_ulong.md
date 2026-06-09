# HostedW3SVCStart(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180004b20`
- end: `0x180004e3e`
- name: `?HostedW3SVCStart@@YAJPEBG00K@Z`
- size: `798`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t *, wchar_t *Source)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002090`
- `0x1800020d0`
- `0x180002b68`
- `0x180003188`
- `0x1800034ac`
- `0x180004b20`
- `0x180004ee4`
- `0x18000561c`
- `0x1800067f4`
- `0x180007398`
- `0x18000750c`
- `0x180007680`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004b66`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004b66`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004ba0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004ba0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004e1c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004e1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004cd4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004cd4`
- `iisutil!PuCreateDebugPrintsObject` at `0x180004b47`
- `iisutil!PuCreateDebugPrintsObject` at `0x180004b47`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180004b7e`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180004b7e`
- `iisutil!IISGetPlatformType` at `0x180004b90`
- `iisutil!IISGetPlatformType` at `0x180004b90`
- `iisutil!PuDbgPrint` at `0x180004d10`
- `iisutil!PuDbgPrint` at `0x180004d6d`
- `iisutil!PuDbgPrint` at `0x180004d10`
- `iisutil!PuDbgPrint` at `0x180004d6d`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180004d98`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180004d98`

## string_xrefs

- `0x180004b5f`: `Unable to Create Debug Print Object \n`
- `0x180004b77`: `System\CurrentControlSet\Services\WAS\Parameters\apphost`
- `0x180004d46`: `Failed to create the W3WP_HOST  hr = %x\n`
- `0x180004d61`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180004d09`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180004cf0`: `InitComplete event signalled\n`
- `0x180004cf7`: `WP_IPM::WaitForInitComplete`

## pseudocode

```c
__int64 __fastcall HostedW3SVCStart(wchar_t *a1, wchar_t *a2, wchar_t *Source)
{
  HRESULT v6; // eax
  signed int v7; // ebx
  int v8; // eax
  W3WP_HOST *v9; // rax
  W3WP_HOST *v10; // rax
  W3WP_HOST *v11; // rcx
  int v12; // eax
  W3WP_HOST *v13; // rcx
  W3WP_HOST *v14; // rcx
  __int64 v15; // rbx
  unsigned int v16; // edx
  void *v17; // rcx
  void *Block; // [rsp+40h] [rbp-38h] BYREF

  Block = 0;
  g_pDebug = PuCreateDebugPrintsObject("w3wphost", 1);
  if ( !g_pDebug )
    OutputDebugStringA("Unable to Create Debug Print Object \n");
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\WAS\\Parameters\\apphost", 8);
  IISGetPlatformType();
  v6 = CoInitializeEx(0, 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = 1;
  }
  else
  {
    if ( v6 != -2147417850 )
    {
LABEL_21:
      if ( g_pW3WPHost )
      {
        EVENT_LOG::LogEvent((W3WP_HOST *)((char *)g_pW3WPHost + 80), 0xC00008E4, 0, 0, v7);
        if ( g_pW3WPHost )
        {
          W3WP_HOST::ShutdownProcess(g_pW3WPHost, 0);
          if ( g_pW3WPHost )
            W3WP_HOST::`scalar deleting destructor'(g_pW3WPHost, v16);
          g_pW3WPHost = 0;
        }
      }
      v17 = Block;
      if ( Block )
      {
        if ( *((_QWORD *)Block + 10) )
        {
          operator delete(*((void **)Block + 10));
          *((_QWORD *)Block + 10) = 0;
          v17 = Block;
        }
        operator delete(v17);
        Block = 0;
      }
      CLR_HOSTING::Terminate();
      if ( g_fComInitialized )
      {
        CoUninitialize();
        g_fComInitialized = 0;
      }
      return (unsigned int)v7;
    }
    v8 = 0;
  }
  g_fComInitialized = v8;
  v9 = (W3WP_HOST *)operator new(0x648u);
  if ( !v9 )
  {
    g_pW3WPHost = 0;
LABEL_19:
    v7 = -2147024882;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        314,
        "HostedW3SVCStart",
        "Failed to create the W3WP_HOST  hr = %x\n",
        -2147024882);
    goto LABEL_21;
  }
  v10 = W3WP_HOST::W3WP_HOST(v9, 0);
  g_pW3WPHost = v10;
  if ( !v10 )
    goto LABEL_19;
  v7 = W3WP_HOST::InitializeHostedConfig(v10, a1, a2, (unsigned __int16 ***)&Block);
  if ( v7 < 0 )
    goto LABEL_21;
  v7 = AllocAndCopyString(Source, (unsigned __int16 **)Block + 10);
  if ( v7 < 0 )
    goto LABEL_21;
  v11 = g_pW3WPHost;
  *((_DWORD *)Block + 22) = 1;
  *((_QWORD *)v11 + 39) = Block;
  Block = 0;
  v12 = W3WP_HOST::InitializeInstance(v11, 0);
  v7 = v12;
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        349,
        "HostedW3SVCStart",
        "Failed to initalize the W3WP_HOST  hr = %x\n",
        v12);
    goto LABEL_21;
  }
  W3WP_HOST::ProcessPreloadApplications(v13, 1);
  W3WP_HOST::StartListenerChannel(v14, &dword_18000FB84, &dword_18000FB84, L"http", 0, 0, 0);
  v15 = *((_QWORD *)g_pW3WPHost + 11);
  WaitForSingleObject(*(HANDLE *)(v15 + 24), 0xFFFFFFFF);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1620,
      "WP_IPM::WaitForInitComplete",
      "InitComplete event signalled\n");
  v7 = *(_DWORD *)(v15 + 32);
  if ( v7 < 0 )
    goto LABEL_21;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004b20  push    rbx
0x180004b22  push    rbp
0x180004b23  push    rsi
0x180004b24  push    rdi
0x180004b25  sub     rsp, 58h
0x180004b29  mov     rsi, rdx
0x180004b2c  mov     [rsp+78h+Block], 0
0x180004b35  mov     rbp, rcx
0x180004b38  mov     edx, 1
0x180004b3d  lea     rcx, aW3wphost; "w3wphost"
0x180004b44  mov     rdi, r8
0x180004b47  call    cs:__imp_PuCreateDebugPrintsObject
0x180004b4e  nop     dword ptr [rax+rax+00h]
0x180004b53  mov     cs:g_pDebug, rax
0x180004b5a  test    rax, rax
0x180004b5d  jnz     short loc_180004B72
0x180004b5f  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x180004b66  call    cs:__imp_OutputDebugStringA
0x180004b6d  nop     dword ptr [rax+rax+00h]
0x180004b72  mov     edx, 8
0x180004b77  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WA"...
0x180004b7e  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180004b85  nop     dword ptr [rax+rax+00h]
0x180004b8a  mov     cs:g_dwDebugFlags, eax
0x180004b90  call    cs:__imp_IISGetPlatformType
0x180004b97  nop     dword ptr [rax+rax+00h]
0x180004b9c  xor     edx, edx; dwCoInit
0x180004b9e  xor     ecx, ecx; pvReserved
0x180004ba0  call    cs:__imp_CoInitializeEx
0x180004ba7  nop     dword ptr [rax+rax+00h]
0x180004bac  mov     ebx, eax
0x180004bae  test    eax, eax
0x180004bb0  jns     short loc_180004BC1
0x180004bb2  cmp     eax, 80010106h
0x180004bb7  jnz     loc_180004D79
0x180004bbd  xor     eax, eax
0x180004bbf  jmp     short loc_180004BC6
0x180004bc1  mov     eax, 1
0x180004bc6  mov     ecx, 648h; Size
0x180004bcb  mov     cs:?g_fComInitialized@@3HA, eax; int g_fComInitialized
0x180004bd1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004bd6  test    rax, rax
0x180004bd9  jz      loc_180004D29
0x180004bdf  xor     edx, edx; struct APPHOST_CONFIG *
0x180004be1  mov     rcx, rax; this
0x180004be4  call    ??0W3WP_HOST@@QEAA@PEAUAPPHOST_CONFIG@@@Z; W3WP_HOST::W3WP_HOST(APPHOST_CONFIG *)
0x180004be9  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, rax; W3WP_HOST * g_pW3WPHost
0x180004bf0  test    rax, rax
0x180004bf3  jz      loc_180004D34
0x180004bf9  lea     r9, [rsp+78h+Block]; struct APPHOST_CONFIG **
0x180004bfe  mov     r8, rsi; unsigned __int16 *
0x180004c01  mov     rdx, rbp; unsigned __int16 *
0x180004c04  mov     rcx, rax; this
0x180004c07  call    ?InitializeHostedConfig@W3WP_HOST@@QEAAJPEBG0PEAPEAUAPPHOST_CONFIG@@@Z; W3WP_HOST::InitializeHostedConfig(ushort const *,ushort const *,APPHOST_CONFIG * *)
0x180004c0c  mov     ebx, eax
0x180004c0e  test    eax, eax
0x180004c10  js      loc_180004D79
0x180004c16  mov     rdx, [rsp+78h+Block]
0x180004c1b  mov     rcx, rdi; Source
0x180004c1e  add     rdx, 50h ; 'P'; unsigned __int16 **
0x180004c22  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x180004c27  mov     ebx, eax
0x180004c29  test    eax, eax
0x180004c2b  js      loc_180004D79
0x180004c31  mov     rax, [rsp+78h+Block]
0x180004c36  xor     edx, edx; struct WP_COUNTERS_MANAGER_INFO *
0x180004c38  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; this
0x180004c3f  mov     dword ptr [rax+58h], 1
0x180004c46  mov     rax, [rsp+78h+Block]
0x180004c4b  mov     [rcx+138h], rax
0x180004c52  mov     [rsp+78h+Block], 0
0x180004c5b  call    ?InitializeInstance@W3WP_HOST@@QEAAJPEAUWP_COUNTERS_MANAGER_INFO@@@Z; W3WP_HOST::InitializeInstance(WP_COUNTERS_MANAGER_INFO *)
0x180004c60  mov     ebx, eax
0x180004c62  test    eax, eax
0x180004c64  jns     short loc_180004C89
0x180004c66  test    byte ptr cs:g_dwDebugFlags, 3
0x180004c6d  jz      loc_180004D79
0x180004c73  mov     [rsp+78h+var_50], eax
0x180004c77  mov     r8d, 15Dh
0x180004c7d  lea     rax, aFailedToInital; "Failed to initalize the W3WP_HOST  hr ="...
0x180004c84  jmp     loc_180004D53
0x180004c89  mov     edx, 1; unsigned int
0x180004c8e  call    ?ProcessPreloadApplications@W3WP_HOST@@QEAAJK@Z; W3WP_HOST::ProcessPreloadApplications(ulong)
0x180004c93  lea     rdx, dword_18000FB84; unsigned __int16 *
0x180004c9a  mov     [rsp+78h+var_48], 0; unsigned __int8 *
0x180004ca3  mov     r8, rdx; unsigned __int16 *
0x180004ca6  mov     [rsp+78h+var_50], 0; unsigned int
0x180004cae  lea     r9, aHttp; "http"
0x180004cb5  mov     [rsp+78h+var_58], 0; unsigned int
0x180004cbd  call    ?StartListenerChannel@W3WP_HOST@@QEAAXPEBG00KKPEAE@Z; W3WP_HOST::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)
0x180004cc2  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180004cc9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004ccc  mov     rbx, [rax+58h]
0x180004cd0  mov     rcx, [rbx+18h]; hHandle
0x180004cd4  call    cs:__imp_WaitForSingleObject
0x180004cdb  nop     dword ptr [rax+rax+00h]
0x180004ce0  test    byte ptr cs:g_dwDebugFlags, 3
0x180004ce7  jz      short loc_180004D1C
0x180004ce9  mov     rcx, cs:g_pDebug
0x180004cf0  lea     rax, aInitcompleteEv; "InitComplete event signalled\n"
0x180004cf7  lea     r9, aWpIpmWaitforin; "WP_IPM::WaitForInitComplete"
0x180004cfe  mov     qword ptr [rsp+78h+var_58], rax
0x180004d03  mov     r8d, 654h
0x180004d09  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004d10  call    cs:__imp_PuDbgPrint
0x180004d17  nop     dword ptr [rax+rax+00h]
0x180004d1c  mov     ebx, [rbx+20h]
0x180004d1f  test    ebx, ebx
0x180004d21  jns     loc_180004E32
0x180004d27  jmp     short loc_180004D79
0x180004d29  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, 0; W3WP_HOST * g_pW3WPHost
0x180004d34  test    byte ptr cs:g_dwDebugFlags, 3
0x180004d3b  mov     ebx, 8007000Eh
0x180004d40  jz      short loc_180004D79
0x180004d42  mov     [rsp+78h+var_50], ebx
0x180004d46  lea     rax, aFailedToCreate; "Failed to create the W3WP_HOST  hr = %x"...
0x180004d4d  mov     r8d, 13Ah
0x180004d53  mov     rcx, cs:g_pDebug
0x180004d5a  lea     r9, aHostedw3svcsta_0; "HostedW3SVCStart"
0x180004d61  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004d68  mov     qword ptr [rsp+78h+var_58], rax
0x180004d6d  call    cs:__imp_PuDbgPrint
0x180004d74  nop     dword ptr [rax+rax+00h]
0x180004d79  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180004d80  test    rcx, rcx
0x180004d83  jz      short loc_180004DD3
0x180004d85  xor     r8d, r8d
0x180004d88  mov     [rsp+78h+var_58], ebx
0x180004d8c  add     rcx, 50h ; 'P'
0x180004d90  xor     r9d, r9d
0x180004d93  mov     edx, 0C00008E4h
0x180004d98  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180004d9f  nop     dword ptr [rax+rax+00h]
0x180004da4  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; this
0x180004dab  test    rcx, rcx
0x180004dae  jz      short loc_180004DD3
0x180004db0  xor     edx, edx; int
0x180004db2  call    ?ShutdownProcess@W3WP_HOST@@QEAAXH@Z; W3WP_HOST::ShutdownProcess(int)
0x180004db7  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; this
0x180004dbe  test    rcx, rcx
0x180004dc1  jz      short loc_180004DC8
0x180004dc3  call    ??_GW3WP_HOST@@QEAAPEAXI@Z; W3WP_HOST::`scalar deleting destructor'(uint)
0x180004dc8  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, 0; W3WP_HOST * g_pW3WPHost
0x180004dd3  mov     rcx, [rsp+78h+Block]
0x180004dd8  test    rcx, rcx
0x180004ddb  jz      short loc_180004E0E
0x180004ddd  mov     rax, [rcx+50h]
0x180004de1  test    rax, rax
0x180004de4  jz      short loc_180004E00
0x180004de6  mov     rcx, rax; Block
0x180004de9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004dee  mov     rax, [rsp+78h+Block]
0x180004df3  mov     qword ptr [rax+50h], 0
0x180004dfb  mov     rcx, [rsp+78h+Block]; Block
0x180004e00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004e05  mov     [rsp+78h+Block], 0
0x180004e0e  call    ?Terminate@CLR_HOSTING@@SAXXZ; CLR_HOSTING::Terminate(void)
0x180004e13  cmp     cs:?g_fComInitialized@@3HA, 0; int g_fComInitialized
0x180004e1a  jz      short loc_180004E32
0x180004e1c  call    cs:__imp_CoUninitialize
0x180004e23  nop     dword ptr [rax+rax+00h]
0x180004e28  mov     cs:?g_fComInitialized@@3HA, 0; int g_fComInitialized
0x180004e32  mov     eax, ebx
0x180004e34  add     rsp, 58h
0x180004e38  pop     rdi
0x180004e39  pop     rsi
0x180004e3a  pop     rbp
0x180004e3b  pop     rbx
0x180004e3c  retn
```
