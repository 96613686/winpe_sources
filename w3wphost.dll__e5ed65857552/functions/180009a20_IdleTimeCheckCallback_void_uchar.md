# IdleTimeCheckCallback(void *,uchar)

- ea: `0x180009a20`
- end: `0x180009a72`
- name: `?IdleTimeCheckCallback@@YAXPEAXE@Z`
- size: `82`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009a20`
- `0x180009a78`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180009a59`
- `iisutil!PuDbgPrint` at `0x180009a59`

## string_xrefs

- `0x180009a52`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpidletimer.cxx`

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
0x180009a20  push    rbx
0x180009a22  sub     rsp, 30h
0x180009a26  test    byte ptr cs:g_dwDebugFlags, 3
0x180009a2d  mov     rbx, rcx
0x180009a30  jz      short loc_180009A65
0x180009a32  mov     rcx, cs:g_pDebug
0x180009a39  lea     rax, aCheckIdleTimeC; "Check Idle Time Callback.\n"
0x180009a40  lea     r9, aIdletimecheckc; "IdleTimeCheckCallback"
0x180009a47  mov     [rsp+38h+var_18], rax
0x180009a4c  mov     r8d, 31h ; '1'
0x180009a52  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009a59  call    cs:__imp_PuDbgPrint
0x180009a60  nop     dword ptr [rax+rax+00h]
0x180009a65  mov     rcx, rbx; this
0x180009a68  add     rsp, 30h
0x180009a6c  pop     rbx
0x180009a6d  jmp     ?IncrementTick@WP_IDLE_TIMER@@QEAAXXZ; WP_IDLE_TIMER::IncrementTick(void)
```
