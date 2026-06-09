# W3WP_HOST::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)

- ea: `0x18000750c`
- end: `0x1800075d4`
- name: `?StartListenerChannel@W3WP_HOST@@QEAAXPEBG00KKPEAE@Z`
- size: `200`
- prototype: `void __fastcall(W3WP_HOST *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004b20`
- `0x180007f68`

## callees

- `0x180003340`
- `0x18000750c`
- `0x18000b8e8`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800075a4`
- `iisutil!PuDbgPrint` at `0x1800075a4`

## string_xrefs

- `0x180007577`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180007583`: `StartListenerChannel call dll:%S entry:%S protocolId:%S listenerChannelId:%d failed with error 0x%x \n`

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
  int started; // eax

  v8 = (volatile signed __int32 *)g_pW3WPHost;
  started = LISTENER_CHANNEL_LIST_MANAGER::StartListenerChannel(
              (W3WP_HOST *)((char *)g_pW3WPHost + 368),
              a2,
              a3,
              a4,
              a5,
              a6,
              a7);
  if ( started >= 0 )
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
      "StartListenerChannel call dll:%S entry:%S protocolId:%S listenerChannelId:%d failed with error 0x%x \n",
      a2,
      a3,
      a4,
      a5,
      started);
  }
}

```

## disassembly

```asm
0x18000750c  push    rbx
0x18000750e  push    rbp
0x18000750f  push    rsi
0x180007510  push    rdi
0x180007511  push    r14
0x180007513  sub     rsp, 50h
0x180007517  mov     rax, [rsp+78h+arg_30]
0x18000751f  mov     rdi, r9
0x180007522  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180007529  mov     rsi, r8
0x18000752c  mov     r14d, [rsp+78h+arg_20]
0x180007534  mov     rbp, rdx
0x180007537  mov     [rsp+78h+var_48], rax; unsigned __int8 *
0x18000753c  mov     eax, [rsp+78h+arg_28]
0x180007543  mov     [rsp+78h+var_50], eax; unsigned int
0x180007547  lea     rcx, [rbx+170h]; this
0x18000754e  mov     [rsp+78h+var_58], r14d; unsigned int
0x180007553  call    ?StartListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBG00KKPEAE@Z; LISTENER_CHANNEL_LIST_MANAGER::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)
0x180007558  test    eax, eax
0x18000755a  jns     short loc_1800075B2
0x18000755c  test    byte ptr cs:g_dwDebugFlags, 3
0x180007563  jz      short loc_1800075C8
0x180007565  mov     rcx, cs:g_pDebug
0x18000756c  lea     r9, aW3wpHostStartl; "W3WP_HOST::StartListenerChannel"
0x180007573  mov     [rsp+78h+var_30], eax
0x180007577  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000757e  mov     [rsp+78h+var_38], r14d
0x180007583  lea     rax, aStartlistenerc; "StartListenerChannel call dll:%S entry:"...
0x18000758a  mov     [rsp+78h+var_40], rdi
0x18000758f  mov     r8d, 0D27h
0x180007595  mov     [rsp+78h+var_48], rsi
0x18000759a  mov     qword ptr [rsp+78h+var_50], rbp
0x18000759f  mov     qword ptr [rsp+78h+var_58], rax
0x1800075a4  call    cs:__imp_PuDbgPrint
0x1800075ab  nop     dword ptr [rax+rax+00h]
0x1800075b0  jmp     short loc_1800075C8
0x1800075b2  mov     rdx, rdi; unsigned __int16 *
0x1800075b5  mov     rcx, rbx; this
0x1800075b8  call    ?AddToActiveProtocolsList@W3WP_HOST@@AEAAHPEBG@Z; W3WP_HOST::AddToActiveProtocolsList(ushort const *)
0x1800075bd  test    eax, eax
0x1800075bf  jz      short loc_1800075C8
0x1800075c1  lock inc dword ptr [rbx+168h]
0x1800075c8  add     rsp, 50h
0x1800075cc  pop     r14
0x1800075ce  pop     rdi
0x1800075cf  pop     rsi
0x1800075d0  pop     rbp
0x1800075d1  pop     rbx
0x1800075d2  retn
```
