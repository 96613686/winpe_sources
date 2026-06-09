# HostedW3SVCStart(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180004750`
- end: `0x180004a31`
- name: `?HostedW3SVCStart@@YAJPEBG00K@Z`
- size: `737`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t *, wchar_t *Source)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001f68`
- `0x180001fa8`
- `0x180002a00`
- `0x180002fb0`
- `0x1800032a8`
- `0x180004750`
- `0x180004ad4`
- `0x1800051dc`
- `0x1800061dc`
- `0x180006cd8`
- `0x180006e3c`
- `0x180006fa4`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004790`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004790`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800047b8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800047b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004a16`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004a16`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800048e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800048e6`
- `iisutil!PuCreateDebugPrintsObject` at `0x180004777`
- `iisutil!PuCreateDebugPrintsObject` at `0x180004777`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x1800047a2`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x1800047a2`
- `iisutil!IISGetPlatformType` at `0x1800047ae`
- `iisutil!IISGetPlatformType` at `0x1800047ae`
- `iisutil!PuDbgPrint` at `0x18000491c`
- `iisutil!PuDbgPrint` at `0x180004973`
- `iisutil!PuDbgPrint` at `0x18000491c`
- `iisutil!PuDbgPrint` at `0x180004973`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180004998`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180004998`

## string_xrefs

- `0x180004789`: `Unable to Create Debug Print Object \n`
- `0x18000479b`: `System\CurrentControlSet\Services\WAS\Parameters\apphost`
- `0x18000494c`: `Failed to create the W3WP_HOST  hr = %x\n`
- `0x180004967`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180004915`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x1800048fc`: `InitComplete event signalled\n`
- `0x180004903`: `WP_IPM::WaitForInitComplete`

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
  W3WP_HOST *v12; // rcx
  __int64 v13; // r8
  const char *v14; // rax
  W3WP_HOST *v15; // rcx
  __int64 v16; // rbx
  unsigned int v17; // edx
  void *v18; // rcx
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
      goto LABEL_22;
    v8 = 0;
  }
  g_fComInitialized = v8;
  v9 = (W3WP_HOST *)operator new(0x648u);
  if ( !v9 )
  {
    g_pW3WPHost = 0;
    goto LABEL_19;
  }
  v10 = W3WP_HOST::W3WP_HOST(v9, 0);
  g_pW3WPHost = v10;
  if ( !v10 )
  {
LABEL_19:
    v7 = -2147024882;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_22;
    v14 = "Failed to create the W3WP_HOST  hr = %x\n";
    v13 = 314;
LABEL_21:
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      v13,
      "HostedW3SVCStart",
      v14);
LABEL_22:
    if ( g_pW3WPHost )
    {
      EVENT_LOG::LogEvent((W3WP_HOST *)((char *)g_pW3WPHost + 80), 0xC00008E4, 0, 0, v7);
      if ( g_pW3WPHost )
      {
        W3WP_HOST::ShutdownProcess(g_pW3WPHost, 0);
        if ( g_pW3WPHost )
          W3WP_HOST::`scalar deleting destructor'(g_pW3WPHost, v17);
        g_pW3WPHost = 0;
      }
    }
    v18 = Block;
    if ( Block )
    {
      if ( *((_QWORD *)Block + 10) )
      {
        operator delete(*((void **)Block + 10));
        *((_QWORD *)Block + 10) = 0;
        v18 = Block;
      }
      operator delete(v18);
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
  v7 = W3WP_HOST::InitializeHostedConfig(v10, a1, a2, (unsigned __int16 ***)&Block);
  if ( v7 < 0 )
    goto LABEL_22;
  v7 = AllocAndCopyString(Source, (unsigned __int16 **)Block + 10);
  if ( v7 < 0 )
    goto LABEL_22;
  v11 = g_pW3WPHost;
  *((_DWORD *)Block + 22) = 1;
  *((_QWORD *)v11 + 39) = Block;
  Block = 0;
  v7 = W3WP_HOST::InitializeInstance(v11, 0);
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_22;
    v13 = 349;
    v14 = "Failed to initalize the W3WP_HOST  hr = %x\n";
    goto LABEL_21;
  }
  W3WP_HOST::ProcessPreloadApplications(v12, 1u);
  W3WP_HOST::StartListenerChannel(v15, &dword_18000EB74, &dword_18000EB74, L"http", 0, 0, 0);
  v16 = *((_QWORD *)g_pW3WPHost + 11);
  WaitForSingleObject(*(HANDLE *)(v16 + 24), 0xFFFFFFFF);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1620,
      "WP_IPM::WaitForInitComplete",
      "InitComplete event signalled\n");
  v7 = *(_DWORD *)(v16 + 32);
  if ( v7 < 0 )
    goto LABEL_22;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004750  push    rbx
0x180004752  push    rbp
0x180004753  push    rsi
0x180004754  push    rdi
0x180004755  sub     rsp, 58h
0x180004759  mov     rsi, rdx
0x18000475c  mov     [rsp+78h+Block], 0
0x180004765  mov     rbp, rcx
0x180004768  mov     edx, 1
0x18000476d  lea     rcx, aW3wphost; "w3wphost"
0x180004774  mov     rdi, r8
0x180004777  call    cs:__imp_PuCreateDebugPrintsObject
0x18000477d  mov     cs:g_pDebug, rax
0x180004784  test    rax, rax
0x180004787  jnz     short loc_180004796
0x180004789  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x180004790  call    cs:__imp_OutputDebugStringA
0x180004796  mov     edx, 8
0x18000479b  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WA"...
0x1800047a2  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x1800047a8  mov     cs:g_dwDebugFlags, eax
0x1800047ae  call    cs:__imp_IISGetPlatformType
0x1800047b4  xor     edx, edx; dwCoInit
0x1800047b6  xor     ecx, ecx; pvReserved
0x1800047b8  call    cs:__imp_CoInitializeEx
0x1800047be  mov     ebx, eax
0x1800047c0  test    eax, eax
0x1800047c2  jns     short loc_1800047D3
0x1800047c4  cmp     eax, 80010106h
0x1800047c9  jnz     loc_180004979
0x1800047cf  xor     eax, eax
0x1800047d1  jmp     short loc_1800047D8
0x1800047d3  mov     eax, 1
0x1800047d8  mov     ecx, 648h; Size
0x1800047dd  mov     cs:?g_fComInitialized@@3HA, eax; int g_fComInitialized
0x1800047e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800047e8  test    rax, rax
0x1800047eb  jz      loc_18000492F
0x1800047f1  xor     edx, edx; struct APPHOST_CONFIG *
0x1800047f3  mov     rcx, rax; this
0x1800047f6  call    ??0W3WP_HOST@@QEAA@PEAUAPPHOST_CONFIG@@@Z; W3WP_HOST::W3WP_HOST(APPHOST_CONFIG *)
0x1800047fb  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, rax; W3WP_HOST * g_pW3WPHost
0x180004802  test    rax, rax
0x180004805  jz      loc_18000493A
0x18000480b  lea     r9, [rsp+78h+Block]; struct APPHOST_CONFIG **
0x180004810  mov     r8, rsi; unsigned __int16 *
0x180004813  mov     rdx, rbp; unsigned __int16 *
0x180004816  mov     rcx, rax; this
0x180004819  call    ?InitializeHostedConfig@W3WP_HOST@@QEAAJPEBG0PEAPEAUAPPHOST_CONFIG@@@Z; W3WP_HOST::InitializeHostedConfig(ushort const *,ushort const *,APPHOST_CONFIG * *)
0x18000481e  mov     ebx, eax
0x180004820  test    eax, eax
0x180004822  js      loc_180004979
0x180004828  mov     rdx, [rsp+78h+Block]
0x18000482d  mov     rcx, rdi; Source
0x180004830  add     rdx, 50h ; 'P'; unsigned __int16 **
0x180004834  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x180004839  mov     ebx, eax
0x18000483b  test    eax, eax
0x18000483d  js      loc_180004979
0x180004843  mov     rax, [rsp+78h+Block]
0x180004848  xor     edx, edx; struct WP_COUNTERS_MANAGER_INFO *
0x18000484a  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; this
0x180004851  mov     dword ptr [rax+58h], 1
0x180004858  mov     rax, [rsp+78h+Block]
0x18000485d  mov     [rcx+138h], rax
0x180004864  mov     [rsp+78h+Block], 0
0x18000486d  call    ?InitializeInstance@W3WP_HOST@@QEAAJPEAUWP_COUNTERS_MANAGER_INFO@@@Z; W3WP_HOST::InitializeInstance(WP_COUNTERS_MANAGER_INFO *)
0x180004872  mov     ebx, eax
0x180004874  test    eax, eax
0x180004876  jns     short loc_18000489B
0x180004878  test    byte ptr cs:g_dwDebugFlags, 3
0x18000487f  jz      loc_180004979
0x180004885  mov     [rsp+78h+var_50], eax
0x180004889  mov     r8d, 15Dh
0x18000488f  lea     rax, aFailedToInital; "Failed to initalize the W3WP_HOST  hr ="...
0x180004896  jmp     loc_180004959
0x18000489b  mov     edx, 1; unsigned int
0x1800048a0  call    ?ProcessPreloadApplications@W3WP_HOST@@QEAAJK@Z; W3WP_HOST::ProcessPreloadApplications(ulong)
0x1800048a5  lea     rdx, dword_18000EB74; unsigned __int16 *
0x1800048ac  mov     [rsp+78h+var_48], 0; unsigned __int8 *
0x1800048b5  mov     r8, rdx; unsigned __int16 *
0x1800048b8  mov     [rsp+78h+var_50], 0; unsigned int
0x1800048c0  lea     r9, aHttp; "http"
0x1800048c7  mov     [rsp+78h+var_58], 0; unsigned int
0x1800048cf  call    ?StartListenerChannel@W3WP_HOST@@QEAAXPEBG00KKPEAE@Z; W3WP_HOST::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)
0x1800048d4  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800048db  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800048de  mov     rbx, [rax+58h]
0x1800048e2  mov     rcx, [rbx+18h]; hHandle
0x1800048e6  call    cs:__imp_WaitForSingleObject
0x1800048ec  test    byte ptr cs:g_dwDebugFlags, 3
0x1800048f3  jz      short loc_180004922
0x1800048f5  mov     rcx, cs:g_pDebug
0x1800048fc  lea     rax, aInitcompleteEv; "InitComplete event signalled\n"
0x180004903  lea     r9, aWpIpmWaitforin; "WP_IPM::WaitForInitComplete"
0x18000490a  mov     qword ptr [rsp+78h+var_58], rax
0x18000490f  mov     r8d, 654h
0x180004915  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000491c  call    cs:__imp_PuDbgPrint
0x180004922  mov     ebx, [rbx+20h]
0x180004925  test    ebx, ebx
0x180004927  jns     loc_180004A26
0x18000492d  jmp     short loc_180004979
0x18000492f  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, 0; W3WP_HOST * g_pW3WPHost
0x18000493a  test    byte ptr cs:g_dwDebugFlags, 3
0x180004941  mov     ebx, 8007000Eh
0x180004946  jz      short loc_180004979
0x180004948  mov     [rsp+78h+var_50], ebx
0x18000494c  lea     rax, aFailedToCreate; "Failed to create the W3WP_HOST  hr = %x"...
0x180004953  mov     r8d, 13Ah
0x180004959  mov     rcx, cs:g_pDebug
0x180004960  lea     r9, aHostedw3svcsta_0; "HostedW3SVCStart"
0x180004967  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000496e  mov     qword ptr [rsp+78h+var_58], rax
0x180004973  call    cs:__imp_PuDbgPrint
0x180004979  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180004980  test    rcx, rcx
0x180004983  jz      short loc_1800049CD
0x180004985  xor     r8d, r8d
0x180004988  mov     [rsp+78h+var_58], ebx
0x18000498c  add     rcx, 50h ; 'P'
0x180004990  xor     r9d, r9d
0x180004993  mov     edx, 0C00008E4h
0x180004998  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000499e  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; this
0x1800049a5  test    rcx, rcx
0x1800049a8  jz      short loc_1800049CD
0x1800049aa  xor     edx, edx; int
0x1800049ac  call    ?ShutdownProcess@W3WP_HOST@@QEAAXH@Z; W3WP_HOST::ShutdownProcess(int)
0x1800049b1  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; this
0x1800049b8  test    rcx, rcx
0x1800049bb  jz      short loc_1800049C2
0x1800049bd  call    ??_GW3WP_HOST@@QEAAPEAXI@Z; W3WP_HOST::`scalar deleting destructor'(uint)
0x1800049c2  mov     cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA, 0; W3WP_HOST * g_pW3WPHost
0x1800049cd  mov     rcx, [rsp+78h+Block]
0x1800049d2  test    rcx, rcx
0x1800049d5  jz      short loc_180004A08
0x1800049d7  mov     rax, [rcx+50h]
0x1800049db  test    rax, rax
0x1800049de  jz      short loc_1800049FA
0x1800049e0  mov     rcx, rax; Block
0x1800049e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800049e8  mov     rax, [rsp+78h+Block]
0x1800049ed  mov     qword ptr [rax+50h], 0
0x1800049f5  mov     rcx, [rsp+78h+Block]; Block
0x1800049fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800049ff  mov     [rsp+78h+Block], 0
0x180004a08  call    ?Terminate@CLR_HOSTING@@SAXXZ; CLR_HOSTING::Terminate(void)
0x180004a0d  cmp     cs:?g_fComInitialized@@3HA, 0; int g_fComInitialized
0x180004a14  jz      short loc_180004A26
0x180004a16  call    cs:__imp_CoUninitialize
0x180004a1c  mov     cs:?g_fComInitialized@@3HA, 0; int g_fComInitialized
0x180004a26  mov     eax, ebx
0x180004a28  add     rsp, 58h
0x180004a2c  pop     rdi
0x180004a2d  pop     rsi
0x180004a2e  pop     rbp
0x180004a2f  pop     rbx
0x180004a30  retn
```
