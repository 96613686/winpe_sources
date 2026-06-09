# WP_RECYCLER::TimerCallbackForScheduleBased(void *,uchar)

- ea: `0x180009920`
- end: `0x180009986`
- name: `?TimerCallbackForScheduleBased@WP_RECYCLER@@SAXPEAXE@Z`
- size: `102`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008e1c`
- `0x180009920`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180009961`
- `iisutil!PuDbgPrint` at `0x180009961`

## string_xrefs

- `0x18000995a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

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
0x180009920  sub     rsp, 38h
0x180009924  mov     eax, cs:g_dwDebugFlags
0x18000992a  test    al, 3
0x18000992c  setnz   cl
0x18000992f  bt      eax, 14h
0x180009933  setb    al
0x180009936  test    al, cl
0x180009938  jz      short loc_18000996D
0x18000993a  mov     rcx, cs:g_pDebug
0x180009941  lea     rax, aWpRecyclerTime_0; "WP_RECYCLER::TimerCallbackForScheduleBa"...
0x180009948  lea     r9, aWpRecyclerTime_3; "WP_RECYCLER::TimerCallbackForScheduleBa"...
0x18000994f  mov     [rsp+38h+var_18], rax
0x180009954  mov     r8d, 22Bh
0x18000995a  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009961  call    cs:__imp_PuDbgPrint
0x180009968  nop     dword ptr [rax+rax+00h]
0x18000996d  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180009974  mov     edx, 3
0x180009979  mov     rcx, [rcx+68h]
0x18000997d  add     rsp, 38h
0x180009981  jmp     ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
```
