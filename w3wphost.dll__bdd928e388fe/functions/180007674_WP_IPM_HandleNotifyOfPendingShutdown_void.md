# WP_IPM::HandleNotifyOfPendingShutdown(void)

- ea: `0x180007674`
- end: `0x1800076d0`
- name: `?HandleNotifyOfPendingShutdown@WP_IPM@@AEAAJXZ`
- size: `92`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001170`

## callees

- `0x180007674`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800076ba`
- `iisutil!PuDbgPrint` at `0x1800076ba`

## string_xrefs

- `0x1800076b3`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandleNotifyOfPendingShutdown(WP_IPM *this)
{
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1084,
      "WP_IPM::HandleNotifyOfPendingShutdown",
      "Handle ******************** Shutdown ***** Notification\n\n");
  _InterlockedExchange((volatile __int32 *)this + 11, 1);
  return 0;
}

```

## disassembly

```asm
0x180007674  push    rbx
0x180007676  sub     rsp, 30h
0x18000767a  mov     eax, cs:g_dwDebugFlags
0x180007680  mov     rbx, rcx
0x180007683  test    al, 3
0x180007685  setnz   dl
0x180007688  bt      eax, 13h
0x18000768c  setb    al
0x18000768f  test    al, dl
0x180007691  jz      short loc_1800076C0
0x180007693  mov     rcx, cs:g_pDebug
0x18000769a  lea     rax, aHandleShutdown; "Handle ******************** Shutdown **"...
0x1800076a1  lea     r9, aWpIpmHandlenot; "WP_IPM::HandleNotifyOfPendingShutdown"
0x1800076a8  mov     [rsp+38h+var_18], rax
0x1800076ad  mov     r8d, 43Ch
0x1800076b3  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800076ba  call    cs:__imp_PuDbgPrint
0x1800076c0  mov     eax, 1
0x1800076c5  xchg    eax, [rbx+2Ch]
0x1800076c8  xor     eax, eax
0x1800076ca  add     rsp, 30h
0x1800076ce  pop     rbx
0x1800076cf  retn
```
