# WP_IPM::HandleNotifyOfPendingShutdown(void)

- ea: `0x180007e20`
- end: `0x180007e83`
- name: `?HandleNotifyOfPendingShutdown@WP_IPM@@AEAAJXZ`
- size: `99`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001180`

## callees

- `0x180007e20`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007e66`
- `iisutil!PuDbgPrint` at `0x180007e66`

## string_xrefs

- `0x180007e5f`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
0x180007e20  push    rbx
0x180007e22  sub     rsp, 30h
0x180007e26  mov     eax, cs:g_dwDebugFlags
0x180007e2c  mov     rbx, rcx
0x180007e2f  test    al, 3
0x180007e31  setnz   dl
0x180007e34  bt      eax, 13h
0x180007e38  setb    al
0x180007e3b  test    al, dl
0x180007e3d  jz      short loc_180007E72
0x180007e3f  mov     rcx, cs:g_pDebug
0x180007e46  lea     rax, aHandleShutdown; "Handle ******************** Shutdown **"...
0x180007e4d  lea     r9, aWpIpmHandlenot; "WP_IPM::HandleNotifyOfPendingShutdown"
0x180007e54  mov     [rsp+38h+var_18], rax
0x180007e59  mov     r8d, 43Ch
0x180007e5f  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007e66  call    cs:__imp_PuDbgPrint
0x180007e6d  nop     dword ptr [rax+rax+00h]
0x180007e72  mov     eax, 1
0x180007e77  xchg    eax, [rbx+2Ch]
0x180007e7a  xor     eax, eax
0x180007e7c  add     rsp, 30h
0x180007e80  pop     rbx
0x180007e81  retn
```
