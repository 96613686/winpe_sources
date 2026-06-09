# W3WP_HOST::StopListenerChannel(ushort const *,ulong,int)

- ea: `0x180006f04`
- end: `0x180006f9b`
- name: `?StopListenerChannel@W3WP_HOST@@QEAAXPEBGKH@Z`
- size: `151`
- prototype: `void(W3WP_HOST *__hidden this, const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800078bc`

## callees

- `0x180006560`
- `0x180006f04`
- `0x18000affc`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006f6d`
- `iisutil!PuDbgPrint` at `0x180006f6d`

## string_xrefs

- `0x180006f4b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180006f56`: `StopListenerChannel call for protocolId:%S listenerChannelId:%d failed with error 0x%x \n`

## pseudocode

```c
void __fastcall W3WP_HOST::StopListenerChannel(W3WP_HOST *this, const unsigned __int16 *a2, unsigned int a3, int a4)
{
  volatile signed __int32 *v4; // rbx

  v4 = (volatile signed __int32 *)g_pW3WPHost;
  if ( (int)LISTENER_CHANNEL_LIST_MANAGER::StopListenerChannel((W3WP_HOST *)((char *)g_pW3WPHost + 368), a2, a3, a4) >= 0 )
  {
    if ( W3WP_HOST::RemoveFromActiveProtocolsList((W3WP_HOST *)v4, a2) )
      _InterlockedDecrement(v4 + 90);
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      3426,
      "W3WP_HOST::StopListenerChannel",
      "StopListenerChannel call for protocolId:%S listenerChannelId:%d failed with error 0x%x \n");
  }
}

```

## disassembly

```asm
0x180006f04  mov     [rsp+arg_0], rbx
0x180006f09  mov     [rsp+arg_8], rsi
0x180006f0e  push    rdi
0x180006f0f  sub     rsp, 40h
0x180006f13  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180006f1a  mov     esi, r8d
0x180006f1d  mov     rdi, rdx
0x180006f20  lea     rcx, [rbx+170h]; this
0x180006f27  call    ?StopListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKH@Z; LISTENER_CHANNEL_LIST_MANAGER::StopListenerChannel(ushort const *,ulong,int)
0x180006f2c  test    eax, eax
0x180006f2e  jns     short loc_180006F75
0x180006f30  test    byte ptr cs:g_dwDebugFlags, 3
0x180006f37  jz      short loc_180006F8B
0x180006f39  mov     rcx, cs:g_pDebug
0x180006f40  lea     r9, aW3wpHostStopli; "W3WP_HOST::StopListenerChannel"
0x180006f47  mov     [rsp+48h+var_10], eax
0x180006f4b  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006f52  mov     [rsp+48h+var_18], esi
0x180006f56  lea     rax, aStoplistenerch; "StopListenerChannel call for protocolId"...
0x180006f5d  mov     [rsp+48h+var_20], rdi
0x180006f62  mov     r8d, 0D62h
0x180006f68  mov     [rsp+48h+var_28], rax
0x180006f6d  call    cs:__imp_PuDbgPrint
0x180006f73  jmp     short loc_180006F8B
0x180006f75  mov     rdx, rdi; unsigned __int16 *
0x180006f78  mov     rcx, rbx; this
0x180006f7b  call    ?RemoveFromActiveProtocolsList@W3WP_HOST@@AEAAHPEBG@Z; W3WP_HOST::RemoveFromActiveProtocolsList(ushort const *)
0x180006f80  test    eax, eax
0x180006f82  jz      short loc_180006F8B
0x180006f84  lock dec dword ptr [rbx+168h]
0x180006f8b  mov     rbx, [rsp+48h+arg_0]
0x180006f90  mov     rsi, [rsp+48h+arg_8]
0x180006f95  add     rsp, 40h
0x180006f99  pop     rdi
0x180006f9a  retn
```
