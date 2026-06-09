# W3WP_HOST::StopListenerChannel(ushort const *,ulong,int)

- ea: `0x1800075dc`
- end: `0x18000767a`
- name: `?StopListenerChannel@W3WP_HOST@@QEAAXPEBGKH@Z`
- size: `158`
- prototype: `void(W3WP_HOST *__hidden this, const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008088`

## callees

- `0x180006bb0`
- `0x1800075dc`
- `0x18000bdc4`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007645`
- `iisutil!PuDbgPrint` at `0x180007645`

## string_xrefs

- `0x180007623`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x18000762e`: `StopListenerChannel call for protocolId:%S listenerChannelId:%d failed with error 0x%x \n`

## pseudocode

```c
void __fastcall W3WP_HOST::StopListenerChannel(W3WP_HOST *this, const unsigned __int16 *a2, unsigned int a3, int a4)
{
  volatile signed __int32 *v4; // rbx
  int v7; // eax

  v4 = (volatile signed __int32 *)g_pW3WPHost;
  v7 = LISTENER_CHANNEL_LIST_MANAGER::StopListenerChannel((W3WP_HOST *)((char *)g_pW3WPHost + 368), a2, a3, a4);
  if ( v7 >= 0 )
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
      "StopListenerChannel call for protocolId:%S listenerChannelId:%d failed with error 0x%x \n",
      a2,
      a3,
      v7);
  }
}

```

## disassembly

```asm
0x1800075dc  mov     [rsp+arg_0], rbx
0x1800075e1  mov     [rsp+arg_8], rsi
0x1800075e6  push    rdi
0x1800075e7  sub     rsp, 40h
0x1800075eb  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800075f2  mov     esi, r8d
0x1800075f5  mov     rdi, rdx
0x1800075f8  lea     rcx, [rbx+170h]; this
0x1800075ff  call    ?StopListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKH@Z; LISTENER_CHANNEL_LIST_MANAGER::StopListenerChannel(ushort const *,ulong,int)
0x180007604  test    eax, eax
0x180007606  jns     short loc_180007653
0x180007608  test    byte ptr cs:g_dwDebugFlags, 3
0x18000760f  jz      short loc_180007669
0x180007611  mov     rcx, cs:g_pDebug
0x180007618  lea     r9, aW3wpHostStopli; "W3WP_HOST::StopListenerChannel"
0x18000761f  mov     [rsp+48h+var_10], eax
0x180007623  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000762a  mov     [rsp+48h+var_18], esi
0x18000762e  lea     rax, aStoplistenerch; "StopListenerChannel call for protocolId"...
0x180007635  mov     [rsp+48h+var_20], rdi
0x18000763a  mov     r8d, 0D62h
0x180007640  mov     [rsp+48h+var_28], rax
0x180007645  call    cs:__imp_PuDbgPrint
0x18000764c  nop     dword ptr [rax+rax+00h]
0x180007651  jmp     short loc_180007669
0x180007653  mov     rdx, rdi; unsigned __int16 *
0x180007656  mov     rcx, rbx; this
0x180007659  call    ?RemoveFromActiveProtocolsList@W3WP_HOST@@AEAAHPEBG@Z; W3WP_HOST::RemoveFromActiveProtocolsList(ushort const *)
0x18000765e  test    eax, eax
0x180007660  jz      short loc_180007669
0x180007662  lock dec dword ptr [rbx+168h]
0x180007669  mov     rbx, [rsp+48h+arg_0]
0x18000766e  mov     rsi, [rsp+48h+arg_8]
0x180007673  add     rsp, 40h
0x180007677  pop     rdi
0x180007678  retn
```
