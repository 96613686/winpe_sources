# HTTP_LOG_SITE_TABLE::OnLogFileModeChange(HTTP_LOG_FILE_MODE,HTTP_LOG_FILE_MODE)

- ea: `0x180008730`
- end: `0x1800087e8`
- name: `?OnLogFileModeChange@HTTP_LOG_SITE_TABLE@@AEAAJW4HTTP_LOG_FILE_MODE@@0@Z`
- size: `184`
- prototype: `__int64 __fastcall(struct MULTI_WORK_DISPATCH *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008858`

## callees

- `0x180008730`
- `0x18000e4c4`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x1800087da`
- `iisutil!PuDbgPrintError` at `0x1800087da`

## string_xrefs

- `0x1800087cf`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsitetable.cpp`
- `0x18000876c`: `Couldn't queue HttpLogSiteTableFromSiteToCentralLogModeWorkItem\n`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::OnLogFileModeChange(struct MULTI_WORK_DISPATCH *a1, int a2, int a3)
{
  int v3; // ebx

  if ( a2 || a3 != 2 )
  {
    v3 = 0;
    if ( a2 == 2 && !a3 )
    {
      v3 = MULTI_WORK_QUEUE::GetAndQueueWorkItem((MULTI_WORK_QUEUE *)((char *)g_pLogSvcAdmin + 1584), a1, 2);
      if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsitetable.cpp",
          787,
          "HTTP_LOG_SITE_TABLE::OnLogFileModeChange",
          v3,
          "Couldn't queue HttpLogSiteTableFromCentralToSiteLogModeWorkItem\n");
    }
  }
  else
  {
    v3 = MULTI_WORK_QUEUE::GetAndQueueWorkItem((MULTI_WORK_QUEUE *)((char *)g_pLogSvcAdmin + 1584), a1, 3);
    if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsitetable.cpp",
        768,
        "HTTP_LOG_SITE_TABLE::OnLogFileModeChange",
        v3,
        "Couldn't queue HttpLogSiteTableFromSiteToCentralLogModeWorkItem\n");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008730  push    rbx
0x180008732  sub     rsp, 30h
0x180008736  mov     rax, rcx
0x180008739  test    edx, edx
0x18000873b  jnz     short loc_18000877B
0x18000873d  cmp     r8d, 2
0x180008741  jnz     short loc_18000877B
0x180008743  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000874a  lea     r8d, [rdx+3]; unsigned __int64
0x18000874e  add     rcx, 630h; this
0x180008755  mov     rdx, rax; struct MULTI_WORK_DISPATCH *
0x180008758  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x18000875d  mov     ebx, eax
0x18000875f  test    eax, eax
0x180008761  jns     short loc_1800087E0
0x180008763  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000876a  jz      short loc_1800087E0
0x18000876c  lea     rax, aCouldnTQueueHt_0; "Couldn't queue HttpLogSiteTableFromSite"...
0x180008773  mov     r8d, 300h
0x180008779  jmp     short loc_1800087BC
0x18000877b  xor     ebx, ebx
0x18000877d  cmp     edx, 2
0x180008780  jnz     short loc_1800087E0
0x180008782  test    r8d, r8d
0x180008785  jnz     short loc_1800087E0
0x180008787  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000878e  mov     r8d, edx; unsigned __int64
0x180008791  add     rcx, 630h; this
0x180008798  mov     rdx, rax; struct MULTI_WORK_DISPATCH *
0x18000879b  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x1800087a0  mov     ebx, eax
0x1800087a2  test    eax, eax
0x1800087a4  jns     short loc_1800087E0
0x1800087a6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800087ad  jz      short loc_1800087E0
0x1800087af  lea     rax, aCouldnTQueueHt; "Couldn't queue HttpLogSiteTableFromCent"...
0x1800087b6  mov     r8d, 313h
0x1800087bc  mov     rcx, cs:g_pDebug
0x1800087c3  lea     r9, aHttpLogSiteTab_2; "HTTP_LOG_SITE_TABLE::OnLogFileModeChang"...
0x1800087ca  mov     [rsp+38h+var_10], rax
0x1800087cf  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800087d6  mov     [rsp+38h+var_18], ebx
0x1800087da  call    cs:__imp_PuDbgPrintError
0x1800087e0  mov     eax, ebx
0x1800087e2  add     rsp, 30h
0x1800087e6  pop     rbx
0x1800087e7  retn
```
