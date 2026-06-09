# LOG_SVC_ADMIN::ExecuteWorkItem(MULTI_WORK_ITEM *)

- ea: `0x18000b560`
- end: `0x18000b5d3`
- name: `?ExecuteWorkItem@LOG_SVC_ADMIN@@UEAAJPEAVMULTI_WORK_ITEM@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *__hidden this, struct MULTI_WORK_ITEM *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b560`
- `0x18000cf98`
- `0x18000d088`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18000b5c5`
- `iisutil!PuDbgPrintError` at `0x18000b5c5`

## string_xrefs

- `0x18000b5be`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::ExecuteWorkItem(LOG_SVC_ADMIN *this, struct MULTI_WORK_ITEM *a2)
{
  unsigned int started; // ebx

  if ( *((_QWORD *)a2 + 2) == 1 )
  {
    started = LOG_SVC_ADMIN::StartServiceWorkItem(this);
    if ( (started & 0x80000000) == 0 )
      return started;
  }
  else
  {
    if ( *((_QWORD *)a2 + 2) == 2 )
    {
      started = 0;
      LOG_SVC_ADMIN::StopServiceWorkItem(this);
      return started;
    }
    started = -2147024809;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
      522,
      "LOG_SVC_ADMIN::ExecuteWorkItem",
      started,
      "Executing work item on LOG_SVC_ADMIN failed\n");
  return started;
}

```

## disassembly

```asm
0x18000b560  push    rbx
0x18000b562  sub     rsp, 30h
0x18000b566  mov     rax, [rdx+10h]
0x18000b56a  sub     rax, 1
0x18000b56e  jz      short loc_18000B586
0x18000b570  cmp     rax, 1
0x18000b574  jz      short loc_18000B57D
0x18000b576  mov     ebx, 80070057h
0x18000b57b  jmp     short loc_18000B591
0x18000b57d  xor     ebx, ebx
0x18000b57f  call    ?StopServiceWorkItem@LOG_SVC_ADMIN@@AEAAXXZ; LOG_SVC_ADMIN::StopServiceWorkItem(void)
0x18000b584  jmp     short loc_18000B5CB
0x18000b586  call    ?StartServiceWorkItem@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::StartServiceWorkItem(void)
0x18000b58b  mov     ebx, eax
0x18000b58d  test    eax, eax
0x18000b58f  jns     short loc_18000B5CB
0x18000b591  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b598  jz      short loc_18000B5CB
0x18000b59a  mov     rcx, cs:g_pDebug
0x18000b5a1  lea     rax, aExecutingWorkI; "Executing work item on LOG_SVC_ADMIN fa"...
0x18000b5a8  mov     [rsp+38h+var_10], rax
0x18000b5ad  lea     r9, aLogSvcAdminExe_0; "LOG_SVC_ADMIN::ExecuteWorkItem"
0x18000b5b4  mov     r8d, 20Ah
0x18000b5ba  mov     [rsp+38h+var_18], ebx
0x18000b5be  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000b5c5  call    cs:__imp_PuDbgPrintError
0x18000b5cb  mov     eax, ebx
0x18000b5cd  add     rsp, 30h
0x18000b5d1  pop     rbx
0x18000b5d2  retn
```
