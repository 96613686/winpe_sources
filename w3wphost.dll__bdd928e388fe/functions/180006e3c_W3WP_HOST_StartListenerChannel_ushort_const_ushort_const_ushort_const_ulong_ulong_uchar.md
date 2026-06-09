# W3WP_HOST::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)

- ea: `0x180006e3c`
- end: `0x180006efd`
- name: `?StartListenerChannel@W3WP_HOST@@QEAAXPEBG00KKPEAE@Z`
- size: `193`
- prototype: `void __fastcall(W3WP_HOST *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004750`
- `0x1800077a0`

## callees

- `0x180003150`
- `0x180006e3c`
- `0x18000abd0`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006ed4`
- `iisutil!PuDbgPrint` at `0x180006ed4`

## string_xrefs

- `0x180006ea7`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180006eb3`: `StartListenerChannel call dll:%S entry:%S protocolId:%S listenerChannelId:%d failed with error 0x%x \n`

## pseudocode

```c
void __fastcall W3WP_HOST::StartListenerChannel(
        W3WP_HOST *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int8 *a7)
{
  volatile signed __int32 *v8; // rbx

  v8 = (volatile signed __int32 *)g_pW3WPHost;
  if ( (int)LISTENER_CHANNEL_LIST_MANAGER::StartListenerChannel(
              (W3WP_HOST *)((char *)g_pW3WPHost + 368),
              a2,
              a3,
              a4,
              a5,
              a6,
              a7) >= 0 )
  {
    if ( W3WP_HOST::AddToActiveProtocolsList((W3WP_HOST *)v8, a4) )
      _InterlockedIncrement(v8 + 90);
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      3367,
      "W3WP_HOST::StartListenerChannel",
      "StartListenerChannel call dll:%S entry:%S protocolId:%S listenerChannelId:%d failed with error 0x%x \n");
  }
}

```

## disassembly

```asm
0x180006e3c  push    rbx
0x180006e3e  push    rbp
0x180006e3f  push    rsi
0x180006e40  push    rdi
0x180006e41  push    r14
0x180006e43  sub     rsp, 50h
0x180006e47  mov     rax, [rsp+78h+arg_30]
0x180006e4f  mov     rdi, r9
0x180006e52  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180006e59  mov     rsi, r8
0x180006e5c  mov     r14d, [rsp+78h+arg_20]
0x180006e64  mov     rbp, rdx
0x180006e67  mov     [rsp+78h+var_48], rax; unsigned __int8 *
0x180006e6c  mov     eax, [rsp+78h+arg_28]
0x180006e73  mov     [rsp+78h+var_50], eax; unsigned int
0x180006e77  lea     rcx, [rbx+170h]; this
0x180006e7e  mov     [rsp+78h+var_58], r14d; unsigned int
0x180006e83  call    ?StartListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBG00KKPEAE@Z; LISTENER_CHANNEL_LIST_MANAGER::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)
0x180006e88  test    eax, eax
0x180006e8a  jns     short loc_180006EDC
0x180006e8c  test    byte ptr cs:g_dwDebugFlags, 3
0x180006e93  jz      short loc_180006EF2
0x180006e95  mov     rcx, cs:g_pDebug
0x180006e9c  lea     r9, aW3wpHostStartl; "W3WP_HOST::StartListenerChannel"
0x180006ea3  mov     [rsp+78h+var_30], eax
0x180006ea7  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006eae  mov     [rsp+78h+var_38], r14d
0x180006eb3  lea     rax, aStartlistenerc; "StartListenerChannel call dll:%S entry:"...
0x180006eba  mov     [rsp+78h+var_40], rdi
0x180006ebf  mov     r8d, 0D27h
0x180006ec5  mov     [rsp+78h+var_48], rsi
0x180006eca  mov     qword ptr [rsp+78h+var_50], rbp
0x180006ecf  mov     qword ptr [rsp+78h+var_58], rax
0x180006ed4  call    cs:__imp_PuDbgPrint
0x180006eda  jmp     short loc_180006EF2
0x180006edc  mov     rdx, rdi; unsigned __int16 *
0x180006edf  mov     rcx, rbx; this
0x180006ee2  call    ?AddToActiveProtocolsList@W3WP_HOST@@AEAAHPEBG@Z; W3WP_HOST::AddToActiveProtocolsList(ushort const *)
0x180006ee7  test    eax, eax
0x180006ee9  jz      short loc_180006EF2
0x180006eeb  lock inc dword ptr [rbx+168h]
0x180006ef2  add     rsp, 50h
0x180006ef6  pop     r14
0x180006ef8  pop     rdi
0x180006ef9  pop     rsi
0x180006efa  pop     rbp
0x180006efb  pop     rbx
0x180006efc  retn
```
