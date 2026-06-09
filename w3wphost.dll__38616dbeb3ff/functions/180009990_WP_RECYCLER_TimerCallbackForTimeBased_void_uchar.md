# WP_RECYCLER::TimerCallbackForTimeBased(void *,uchar)

- ea: `0x180009990`
- end: `0x1800099f4`
- name: `?TimerCallbackForTimeBased@WP_RECYCLER@@SAXPEAXE@Z`
- size: `100`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008e1c`
- `0x180009990`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800099d6`
- `iisutil!PuDbgPrint` at `0x1800099d6`

## string_xrefs

- `0x1800099cf`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

## pseudocode

```c
void __fastcall WP_RECYCLER::TimerCallbackForTimeBased(__int64 a1)
{
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
      1239,
      "WP_RECYCLER::TimerCallbackForTimeBased",
      "WP_RECYCLER::TimerCallbackForTimeBased - tell WAS to recycle\n");
  WP_RECYCLER::SendRecyclingMsg(a1, 4);
}

```

## disassembly

```asm
0x180009990  push    rbx
0x180009992  sub     rsp, 30h
0x180009996  mov     eax, cs:g_dwDebugFlags
0x18000999c  mov     rbx, rcx
0x18000999f  test    al, 3
0x1800099a1  setnz   dl
0x1800099a4  bt      eax, 14h
0x1800099a8  setb    al
0x1800099ab  test    al, dl
0x1800099ad  jz      short loc_1800099E2
0x1800099af  mov     rcx, cs:g_pDebug
0x1800099b6  lea     rax, aWpRecyclerTime_1; "WP_RECYCLER::TimerCallbackForTimeBased "...
0x1800099bd  lea     r9, aWpRecyclerTime_5; "WP_RECYCLER::TimerCallbackForTimeBased"
0x1800099c4  mov     [rsp+38h+var_18], rax
0x1800099c9  mov     r8d, 4D7h
0x1800099cf  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800099d6  call    cs:__imp_PuDbgPrint
0x1800099dd  nop     dword ptr [rax+rax+00h]
0x1800099e2  mov     edx, 4
0x1800099e7  mov     rcx, rbx
0x1800099ea  add     rsp, 30h
0x1800099ee  pop     rbx
0x1800099ef  jmp     ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
```
