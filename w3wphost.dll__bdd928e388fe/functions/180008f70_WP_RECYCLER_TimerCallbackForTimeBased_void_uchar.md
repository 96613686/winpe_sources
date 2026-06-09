# WP_RECYCLER::TimerCallbackForTimeBased(void *,uchar)

- ea: `0x180008f70`
- end: `0x180008fce`
- name: `?TimerCallbackForTimeBased@WP_RECYCLER@@SAXPEAXE@Z`
- size: `94`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000850c`
- `0x180008f70`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008fb6`
- `iisutil!PuDbgPrint` at `0x180008fb6`

## string_xrefs

- `0x180008faf`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

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
0x180008f70  push    rbx
0x180008f72  sub     rsp, 30h
0x180008f76  mov     eax, cs:g_dwDebugFlags
0x180008f7c  mov     rbx, rcx
0x180008f7f  test    al, 3
0x180008f81  setnz   dl
0x180008f84  bt      eax, 14h
0x180008f88  setb    al
0x180008f8b  test    al, dl
0x180008f8d  jz      short loc_180008FBC
0x180008f8f  mov     rcx, cs:g_pDebug
0x180008f96  lea     rax, aWpRecyclerTime_1; "WP_RECYCLER::TimerCallbackForTimeBased "...
0x180008f9d  lea     r9, aWpRecyclerTime_5; "WP_RECYCLER::TimerCallbackForTimeBased"
0x180008fa4  mov     [rsp+38h+var_18], rax
0x180008fa9  mov     r8d, 4D7h
0x180008faf  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008fb6  call    cs:__imp_PuDbgPrint
0x180008fbc  mov     edx, 4
0x180008fc1  mov     rcx, rbx
0x180008fc4  add     rsp, 30h
0x180008fc8  pop     rbx
0x180008fc9  jmp     ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
```
