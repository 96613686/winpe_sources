# LISTENER_CHANNEL::HandleStartListenerChannel(void)

- ea: `0x18000ae4c`
- end: `0x18000af45`
- name: `?HandleStartListenerChannel@LISTENER_CHANNEL@@QEAAJXZ`
- size: `249`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000be80`

## callees

- `0x18000a0f4`
- `0x18000ae4c`
- `0x18000e010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ae6a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000aec0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000aed3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000af1c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ae6a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000aec0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000aed3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000af1c`
- `iisutil!PuDbgPrint` at `0x18000aea6`
- `iisutil!PuDbgPrint` at `0x18000aea6`

## string_xrefs

- `0x18000ae88`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel.cxx`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::HandleStartListenerChannel(LISTENER_CHANNEL *this)
{
  int v2; // ebx
  const wchar_t *Str; // rax
  W3WP_HOST *v4; // rdi
  const unsigned __int16 *v5; // rbx
  const unsigned __int16 *v6; // rax
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, unsigned __int16 *, LISTENER_CHANNEL *); // rbx
  unsigned __int16 *v10; // rax

  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v2 = *((_DWORD *)this + 18);
    Str = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 16));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\listener_channel.cxx",
      909,
      "LISTENER_CHANNEL::HandleStartListenerChannel",
      "Start listenerChannel %S:%d\n",
      Str,
      v2);
  }
  v4 = g_pW3WPHost;
  v5 = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 136));
  v6 = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 80));
  result = PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(
             (W3WP_HOST *)((char *)v4 + 320),
             v6,
             v5,
             (struct PROTOCOL_MANAGER_ENTRY **)this + 34,
             1);
  if ( (int)result >= 0 )
  {
    v8 = *(_QWORD *)(*((_QWORD *)this + 34) + 280LL);
    v9 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, LISTENER_CHANNEL *))(*(_QWORD *)v8 + 16LL);
    v10 = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 16));
    return v9(v8, v10, this);
  }
  return result;
}

```

## disassembly

```asm
0x18000ae4c  push    rbx
0x18000ae4e  push    rbp
0x18000ae4f  push    rsi
0x18000ae50  push    rdi
0x18000ae51  push    r14
0x18000ae53  sub     rsp, 40h
0x18000ae57  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ae5e  mov     rsi, rcx
0x18000ae61  jz      short loc_18000AEB2
0x18000ae63  mov     ebx, [rcx+48h]
0x18000ae66  add     rcx, 10h
0x18000ae6a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000ae71  nop     dword ptr [rax+rax+00h]
0x18000ae76  mov     rcx, cs:g_pDebug
0x18000ae7d  lea     r9, aListenerChanne_0; "LISTENER_CHANNEL::HandleStartListenerCh"...
0x18000ae84  mov     [rsp+68h+var_38], ebx
0x18000ae88  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000ae8f  mov     [rsp+68h+var_40], rax
0x18000ae94  mov     r8d, 38Dh
0x18000ae9a  lea     rax, aStartListenerc_0; "Start listenerChannel %S:%d\n"
0x18000aea1  mov     qword ptr [rsp+68h+var_48], rax
0x18000aea6  call    cs:__imp_PuDbgPrint
0x18000aead  nop     dword ptr [rax+rax+00h]
0x18000aeb2  mov     rdi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x18000aeb9  lea     rcx, [rsi+88h]
0x18000aec0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000aec7  nop     dword ptr [rax+rax+00h]
0x18000aecc  lea     rcx, [rsi+50h]
0x18000aed0  mov     rbx, rax
0x18000aed3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000aeda  nop     dword ptr [rax+rax+00h]
0x18000aedf  lea     r14, [rsi+110h]
0x18000aee6  mov     [rsp+68h+var_48], 1; int
0x18000aeee  mov     r9, r14; struct PROTOCOL_MANAGER_ENTRY **
0x18000aef1  lea     rcx, [rdi+140h]; this
0x18000aef8  mov     rdx, rax; unsigned __int16 *
0x18000aefb  mov     r8, rbx; unsigned __int16 *
0x18000aefe  call    ?GetProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAJPEBG0PEAPEAVPROTOCOL_MANAGER_ENTRY@@H@Z; PROTOCOL_MANAGER_LIST::GetProtocolManagerEntry(ushort const *,ushort const *,PROTOCOL_MANAGER_ENTRY * *,int)
0x18000af03  test    eax, eax
0x18000af05  js      short loc_18000AF39
0x18000af07  mov     rax, [r14]
0x18000af0a  lea     rcx, [rsi+10h]
0x18000af0e  mov     rdi, [rax+118h]
0x18000af15  mov     rax, [rdi]
0x18000af18  mov     rbx, [rax+10h]
0x18000af1c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000af23  nop     dword ptr [rax+rax+00h]
0x18000af28  mov     r8, rsi
0x18000af2b  mov     rcx, rdi
0x18000af2e  mov     rdx, rax
0x18000af31  mov     rax, rbx
0x18000af34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af39  add     rsp, 40h
0x18000af3d  pop     r14
0x18000af3f  pop     rdi
0x18000af40  pop     rsi
0x18000af41  pop     rbp
0x18000af42  pop     rbx
0x18000af43  retn
```
