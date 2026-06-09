# LISTENER_CHANNEL::HandleStopListenerChannel(int)

- ea: `0x18000a30c`
- end: `0x18000a3a7`
- name: `?HandleStopListenerChannel@LISTENER_CHANNEL@@QEAAJH@Z`
- size: `155`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b0f0`

## callees

- `0x18000a30c`
- `0x18000d010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a32d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a382`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a32d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a382`
- `iisutil!PuDbgPrint` at `0x18000a363`
- `iisutil!PuDbgPrint` at `0x18000a363`

## string_xrefs

- `0x18000a345`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel.cxx`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::HandleStopListenerChannel(LISTENER_CHANNEL *this, unsigned int a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, unsigned __int16 *, LISTENER_CHANNEL *, _QWORD); // rbx
  unsigned __int16 *Str; // rax

  if ( (g_dwDebugFlags & 3) != 0 )
  {
    STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 16));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\listener_channel.cxx",
      959,
      "LISTENER_CHANNEL::HandleStopListenerChannel",
      "Stop listenerChannel %S:%d\n");
  }
  v4 = *(_QWORD *)(*((_QWORD *)this + 34) + 280LL);
  v5 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, LISTENER_CHANNEL *, _QWORD))(*(_QWORD *)v4 + 24LL);
  Str = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 16));
  return v5(v4, Str, this, a2);
}

```

## disassembly

```asm
0x18000a30c  push    rbx
0x18000a30e  push    rbp
0x18000a30f  push    rsi
0x18000a310  push    rdi
0x18000a311  push    r14
0x18000a313  sub     rsp, 40h
0x18000a317  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a31e  mov     r14d, edx
0x18000a321  mov     rsi, rcx
0x18000a324  jz      short loc_18000A369
0x18000a326  mov     ebx, [rcx+48h]
0x18000a329  add     rcx, 10h
0x18000a32d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a333  mov     rcx, cs:g_pDebug
0x18000a33a  lea     r9, aListenerChanne_1; "LISTENER_CHANNEL::HandleStopListenerCha"...
0x18000a341  mov     [rsp+68h+var_38], ebx
0x18000a345  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a34c  mov     [rsp+68h+var_40], rax
0x18000a351  mov     r8d, 3BFh
0x18000a357  lea     rax, aStopListenerch_0; "Stop listenerChannel %S:%d\n"
0x18000a35e  mov     [rsp+68h+var_48], rax
0x18000a363  call    cs:__imp_PuDbgPrint
0x18000a369  mov     rax, [rsi+110h]
0x18000a370  lea     rcx, [rsi+10h]
0x18000a374  mov     rdi, [rax+118h]
0x18000a37b  mov     rax, [rdi]
0x18000a37e  mov     rbx, [rax+18h]
0x18000a382  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000a388  mov     r9d, r14d
0x18000a38b  mov     r8, rsi
0x18000a38e  mov     rdx, rax
0x18000a391  mov     rcx, rdi
0x18000a394  mov     rax, rbx
0x18000a397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a39c  add     rsp, 40h
0x18000a3a0  pop     r14
0x18000a3a2  pop     rdi
0x18000a3a3  pop     rsi
0x18000a3a4  pop     rbp
0x18000a3a5  pop     rbx
0x18000a3a6  retn
```
