# HTTP_LOG_CONTEXT::ExecuteWorkItem(MULTI_WORK_ITEM *)

- ea: `0x18000a290`
- end: `0x18000a2f1`
- name: `?ExecuteWorkItem@HTTP_LOG_CONTEXT@@UEAAJPEAVMULTI_WORK_ITEM@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(HTTP_LOG_CONTEXT *__hidden this, struct MULTI_WORK_ITEM *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a290`
- `0x18000a57c`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18000a2da`
- `iisutil!PuDbgPrintError` at `0x18000a2da`

## string_xrefs

- `0x18000a2d3`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logcontext.cpp`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_CONTEXT::ExecuteWorkItem(HTTP_LOG_CONTEXT *this, struct MULTI_WORK_ITEM *a2)
{
  unsigned int v2; // ebx

  if ( *((_QWORD *)a2 + 2) == 1 )
  {
    v2 = 0;
    HTTP_LOG_CONTEXT::ProcessETW(this);
  }
  else
  {
    v2 = -2147024809;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logcontext.cpp",
        391,
        "HTTP_LOG_CONTEXT::ExecuteWorkItem",
        -2147024809,
        "Executing work item on HTTP_LOG_CONTEXT failed\n");
  }
  return v2;
}

```

## disassembly

```asm
0x18000a290  push    rbx
0x18000a292  sub     rsp, 30h
0x18000a296  cmp     qword ptr [rdx+10h], 1
0x18000a29b  jz      short loc_18000A2E2
0x18000a29d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000a2a4  mov     ebx, 80070057h
0x18000a2a9  jz      short loc_18000A2E9
0x18000a2ab  mov     rcx, cs:g_pDebug
0x18000a2b2  lea     rax, aExecutingWorkI_0; "Executing work item on HTTP_LOG_CONTEXT"...
0x18000a2b9  mov     [rsp+38h+var_10], rax
0x18000a2be  lea     r9, aHttpLogContext; "HTTP_LOG_CONTEXT::ExecuteWorkItem"
0x18000a2c5  mov     r8d, 187h
0x18000a2cb  mov     [rsp+38h+var_18], 80070057h
0x18000a2d3  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000a2da  call    cs:__imp_PuDbgPrintError
0x18000a2e0  jmp     short loc_18000A2E9
0x18000a2e2  xor     ebx, ebx
0x18000a2e4  call    ?ProcessETW@HTTP_LOG_CONTEXT@@QEAAJXZ; HTTP_LOG_CONTEXT::ProcessETW(void)
0x18000a2e9  mov     eax, ebx
0x18000a2eb  add     rsp, 30h
0x18000a2ef  pop     rbx
0x18000a2f0  retn
```
