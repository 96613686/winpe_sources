# IdleTimeCheckCallback(void *,uchar)

- ea: `0x180008ff0`
- end: `0x18000903c`
- name: `?IdleTimeCheckCallback@@YAXPEAXE@Z`
- size: `76`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008ff0`
- `0x180009044`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180009029`
- `iisutil!PuDbgPrint` at `0x180009029`

## string_xrefs

- `0x180009022`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`

## pseudocode

```c
void __fastcall IdleTimeCheckCallback(WP_IDLE_TIMER *a1)
{
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpidletimer.cxx",
      49,
      "IdleTimeCheckCallback",
      "Check Idle Time Callback.\n");
  WP_IDLE_TIMER::IncrementTick(a1);
}

```

## disassembly

```asm
0x180008ff0  push    rbx
0x180008ff2  sub     rsp, 30h
0x180008ff6  test    byte ptr cs:g_dwDebugFlags, 3
0x180008ffd  mov     rbx, rcx
0x180009000  jz      short loc_18000902F
0x180009002  mov     rcx, cs:g_pDebug
0x180009009  lea     rax, aCheckIdleTimeC; "Check Idle Time Callback.\n"
0x180009010  lea     r9, aIdletimecheckc; "IdleTimeCheckCallback"
0x180009017  mov     [rsp+38h+var_18], rax
0x18000901c  mov     r8d, 31h ; '1'
0x180009022  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009029  call    cs:__imp_PuDbgPrint
0x18000902f  mov     rcx, rbx; this
0x180009032  add     rsp, 30h
0x180009036  pop     rbx
0x180009037  jmp     ?IncrementTick@WP_IDLE_TIMER@@QEAAXXZ; WP_IDLE_TIMER::IncrementTick(void)
```
