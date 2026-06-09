# LOG_SVC_ADMIN::CancelPendingServiceStatusTimer(void)

- ea: `0x18000b290`
- end: `0x18000b31b`
- name: `?CancelPendingServiceStatusTimer@LOG_SVC_ADMIN@@AEAAJXZ`
- size: `139`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b5dc`
- `0x18000d180`

## callees

- `0x18000b290`

## import_xrefs

- `ntdll!RtlDeleteTimer` at `0x18000b2bb`
- `ntdll!RtlDeleteTimer` at `0x18000b2bb`
- `iisutil!PuDbgPrintError` at `0x18000b2ff`
- `iisutil!PuDbgPrintError` at `0x18000b2ff`

## string_xrefs

- `0x18000b2f8`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000b2e7`: `LOG_SVC_ADMIN::CancelPendingServiceStatusTimer`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::CancelPendingServiceStatusTimer(LOG_SVC_ADMIN *this)
{
  unsigned int v2; // ebx
  void *v3; // rcx
  void *v4; // rdx
  NTSTATUS v5; // eax

  v2 = 0;
  v3 = (void *)*((_QWORD *)this + 264);
  if ( v3 )
  {
    v4 = (void *)*((_QWORD *)this + 263);
    if ( v4 )
    {
      v5 = RtlDeleteTimer(v3, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      if ( v5 >= 0 )
      {
        *((_QWORD *)this + 263) = 0;
      }
      else
      {
        v2 = v5 | 0x10000000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
            1533,
            "LOG_SVC_ADMIN::CancelPendingServiceStatusTimer",
            v2,
            "Could not cancel timer\n");
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000b290  mov     [rsp+arg_0], rbx
0x18000b295  push    rdi
0x18000b296  sub     rsp, 30h
0x18000b29a  mov     rdi, rcx
0x18000b29d  xor     ebx, ebx
0x18000b29f  mov     rcx, [rcx+840h]; TimerQueue
0x18000b2a6  test    rcx, rcx
0x18000b2a9  jz      short loc_18000B30E
0x18000b2ab  mov     rdx, [rdi+838h]; Timer
0x18000b2b2  test    rdx, rdx
0x18000b2b5  jz      short loc_18000B30E
0x18000b2b7  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000b2bb  call    cs:__imp_RtlDeleteTimer
0x18000b2c1  test    eax, eax
0x18000b2c3  jns     short loc_18000B307
0x18000b2c5  mov     ebx, eax
0x18000b2c7  bts     ebx, 1Ch
0x18000b2cb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b2d2  jz      short loc_18000B30E
0x18000b2d4  mov     rcx, cs:g_pDebug
0x18000b2db  lea     rax, aCouldNotCancel_0; "Could not cancel timer\n"
0x18000b2e2  mov     [rsp+38h+var_10], rax
0x18000b2e7  lea     r9, aLogSvcAdminCan; "LOG_SVC_ADMIN::CancelPendingServiceStat"...
0x18000b2ee  mov     r8d, 5FDh
0x18000b2f4  mov     [rsp+38h+var_18], ebx
0x18000b2f8  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000b2ff  call    cs:__imp_PuDbgPrintError
0x18000b305  jmp     short loc_18000B30E
0x18000b307  mov     [rdi+838h], rbx
0x18000b30e  mov     eax, ebx
0x18000b310  mov     rbx, [rsp+38h+arg_0]
0x18000b315  add     rsp, 30h
0x18000b319  pop     rdi
0x18000b31a  retn
```
