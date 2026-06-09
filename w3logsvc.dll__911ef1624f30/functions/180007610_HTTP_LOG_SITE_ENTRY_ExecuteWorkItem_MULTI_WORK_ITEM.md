# HTTP_LOG_SITE_ENTRY::ExecuteWorkItem(MULTI_WORK_ITEM *)

- ea: `0x180007610`
- end: `0x18000766a`
- name: `?ExecuteWorkItem@HTTP_LOG_SITE_ENTRY@@UEAAJPEAVMULTI_WORK_ITEM@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(HTTP_LOG_SITE_ENTRY *__hidden this, struct MULTI_WORK_ITEM *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007610`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18000765c`
- `iisutil!PuDbgPrintError` at `0x18000765c`

## string_xrefs

- `0x180007655`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsite.cpp`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_ENTRY::ExecuteWorkItem(HTTP_LOG_SITE_ENTRY *this, struct MULTI_WORK_ITEM *a2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( *((_QWORD *)a2 + 2) != 1 )
  {
    v2 = -2147024809;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsite.cpp",
        1147,
        "HTTP_LOG_SITE_ENTRY::ExecuteWorkItem",
        -2147024809,
        "Executing work item on HTTP_LOG_SITE_ENTRY failed\n");
  }
  return v2;
}

```

## disassembly

```asm
0x180007610  push    rbx
0x180007612  sub     rsp, 30h
0x180007616  xor     ebx, ebx
0x180007618  cmp     qword ptr [rdx+10h], 1
0x18000761d  jz      short loc_180007662
0x18000761f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007626  mov     ebx, 80070057h
0x18000762b  jz      short loc_180007662
0x18000762d  mov     rcx, cs:g_pDebug
0x180007634  lea     rax, aExecutingWorkI_2; "Executing work item on HTTP_LOG_SITE_EN"...
0x18000763b  mov     [rsp+38h+var_10], rax
0x180007640  lea     r9, aHttpLogSiteEnt; "HTTP_LOG_SITE_ENTRY::ExecuteWorkItem"
0x180007647  mov     r8d, 47Bh
0x18000764d  mov     [rsp+38h+var_18], 80070057h
0x180007655  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000765c  call    cs:__imp_PuDbgPrintError
0x180007662  mov     eax, ebx
0x180007664  add     rsp, 30h
0x180007668  pop     rbx
0x180007669  retn
```
