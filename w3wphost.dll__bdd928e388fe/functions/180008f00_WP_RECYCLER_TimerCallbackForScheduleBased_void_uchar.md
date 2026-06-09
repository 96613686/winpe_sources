# WP_RECYCLER::TimerCallbackForScheduleBased(void *,uchar)

- ea: `0x180008f00`
- end: `0x180008f60`
- name: `?TimerCallbackForScheduleBased@WP_RECYCLER@@SAXPEAXE@Z`
- size: `96`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000850c`
- `0x180008f00`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008f41`
- `iisutil!PuDbgPrint` at `0x180008f41`

## string_xrefs

- `0x180008f3a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

## pseudocode

```c
void __fastcall WP_RECYCLER::TimerCallbackForScheduleBased(PVOID a1)
{
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
      555,
      "WP_RECYCLER::TimerCallbackForScheduleBased",
      "WP_RECYCLER::TimerCallbackForScheduleBased() - tell WAS to recycle\n");
  WP_RECYCLER::SendRecyclingMsg(*((_QWORD *)g_pW3WPHost + 13), 3);
}

```

## disassembly

```asm
0x180008f00  sub     rsp, 38h
0x180008f04  mov     eax, cs:g_dwDebugFlags
0x180008f0a  test    al, 3
0x180008f0c  setnz   cl
0x180008f0f  bt      eax, 14h
0x180008f13  setb    al
0x180008f16  test    al, cl
0x180008f18  jz      short loc_180008F47
0x180008f1a  mov     rcx, cs:g_pDebug
0x180008f21  lea     rax, aWpRecyclerTime_0; "WP_RECYCLER::TimerCallbackForScheduleBa"...
0x180008f28  lea     r9, aWpRecyclerTime_3; "WP_RECYCLER::TimerCallbackForScheduleBa"...
0x180008f2f  mov     [rsp+38h+var_18], rax
0x180008f34  mov     r8d, 22Bh
0x180008f3a  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008f41  call    cs:__imp_PuDbgPrint
0x180008f47  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180008f4e  mov     edx, 3
0x180008f53  mov     rcx, [rcx+68h]
0x180008f57  add     rsp, 38h
0x180008f5b  jmp     ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
```
