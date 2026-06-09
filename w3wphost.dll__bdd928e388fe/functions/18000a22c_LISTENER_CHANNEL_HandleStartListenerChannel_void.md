# LISTENER_CHANNEL::HandleStartListenerChannel(void)

- ea: `0x18000a22c`
- end: `0x18000a306`
- name: `?HandleStartListenerChannel@LISTENER_CHANNEL@@QEAAJXZ`
- size: `218`
- prototype: `__int64 __fastcall(struct PROTOCOL_MANAGER_ENTRY **this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b0b0`

## callees

- `0x180009630`
- `0x18000a22c`
- `0x18000d010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a24a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a294`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a2a1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a2e4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a24a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a294`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a2a1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a2e4`
- `iisutil!PuDbgPrint` at `0x18000a280`
- `iisutil!PuDbgPrint` at `0x18000a280`

## string_xrefs

- `0x18000a262`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel.cxx`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::HandleStartListenerChannel(struct PROTOCOL_MANAGER_ENTRY **this)
{
  W3WP_HOST *v2; // rdi
  const unsigned __int16 *Str; // rbx
  const unsigned __int16 *v4; // rax
  __int64 result; // rax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, unsigned __int16 *, struct PROTOCOL_MANAGER_ENTRY **); // rbx
  unsigned __int16 *v8; // rax

  if ( (g_dwDebugFlags & 3) != 0 )
  {
    STRU::QueryStr((STRU *)(this + 2));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\listener_channel.cxx",
      909,
      "LISTENER_CHANNEL::HandleStartListenerChannel",
      "Start listenerChannel %S:%d\n");
  }
  v2 = g_pW3WPHost;
  Str = STRU::QueryStr((STRU *)(this + 17));
  v4 = STRU::QueryStr((STRU *)(this + 10));
  result = PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry((W3WP_HOST *)((char *)v2 + 320), v4, Str, this + 34, 1);
  if ( (int)result >= 0 )
  {
    v6 = *((_QWORD *)this[34] + 35);
    v7 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct PROTOCOL_MANAGER_ENTRY **))(*(_QWORD *)v6 + 16LL);
    v8 = STRU::QueryStr((STRU *)(this + 2));
    return v7(v6, v8, this);
  }
  return result;
}

```

## disassembly

```asm
0x18000a22c  push    rbx
0x18000a22e  push    rbp
0x18000a22f  push    rsi
0x18000a230  push    rdi
0x18000a231  push    r14
0x18000a233  sub     rsp, 40h
0x18000a237  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a23e  mov     rsi, rcx
0x18000a241  jz      short loc_18000A286
0x18000a243  mov     ebx, [rcx+48h]
0x18000a246  add     rcx, 10h
0x18000a24a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a250  mov     rcx, cs:g_pDebug
0x18000a257  lea     r9, aListenerChanne_0; "LISTENER_CHANNEL::HandleStartListenerCh"...
0x18000a25e  mov     [rsp+68h+var_38], ebx
0x18000a262  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a269  mov     [rsp+68h+var_40], rax
0x18000a26e  mov     r8d, 38Dh
0x18000a274  lea     rax, aStartListenerc_0; "Start listenerChannel %S:%d\n"
0x18000a27b  mov     qword ptr [rsp+68h+var_48], rax
0x18000a280  call    cs:__imp_PuDbgPrint
0x18000a286  mov     rdi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000a28d  lea     rcx, [rsi+88h]
0x18000a294  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a29a  lea     rcx, [rsi+50h]
0x18000a29e  mov     rbx, rax
0x18000a2a1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a2a7  lea     r14, [rsi+110h]
0x18000a2ae  mov     [rsp+68h+var_48], 1; int
0x18000a2b6  mov     r9, r14; struct PROTOCOL_MANAGER_ENTRY **
0x18000a2b9  lea     rcx, [rdi+140h]; this
0x18000a2c0  mov     rdx, rax; unsigned __int16 *
0x18000a2c3  mov     r8, rbx; unsigned __int16 *
0x18000a2c6  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x18000a2cb  test    eax, eax
0x18000a2cd  js      short loc_18000A2FB
0x18000a2cf  mov     rax, [r14]
0x18000a2d2  lea     rcx, [rsi+10h]
0x18000a2d6  mov     rdi, [rax+118h]
0x18000a2dd  mov     rax, [rdi]
0x18000a2e0  mov     rbx, [rax+10h]
0x18000a2e4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a2ea  mov     r8, rsi
0x18000a2ed  mov     rcx, rdi
0x18000a2f0  mov     rdx, rax
0x18000a2f3  mov     rax, rbx
0x18000a2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2fb  add     rsp, 40h
0x18000a2ff  pop     r14
0x18000a301  pop     rdi
0x18000a302  pop     rsi
0x18000a303  pop     rbp
0x18000a304  pop     rbx
0x18000a305  retn
```
