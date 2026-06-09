# LISTENER_CHANNEL::HandleStopListenerChannel(int)

- ea: `0x18000af4c`
- end: `0x18000affa`
- name: `?HandleStopListenerChannel@LISTENER_CHANNEL@@QEAAJH@Z`
- size: `174`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bec0`

## callees

- `0x18000af4c`
- `0x18000e010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000af6d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000afce`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000af6d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000afce`
- `iisutil!PuDbgPrint` at `0x18000afa9`
- `iisutil!PuDbgPrint` at `0x18000afa9`

## string_xrefs

- `0x18000af8b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel.cxx`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL::HandleStopListenerChannel(LISTENER_CHANNEL *this, unsigned int a2)
{
  int v4; // ebx
  const wchar_t *Str; // rax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, unsigned __int16 *, LISTENER_CHANNEL *, _QWORD); // rbx
  unsigned __int16 *v8; // rax

  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v4 = *((_DWORD *)this + 18);
    Str = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 16));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\listener_channel.cxx",
      959,
      "LISTENER_CHANNEL::HandleStopListenerChannel",
      "Stop listenerChannel %S:%d\n",
      Str,
      v4);
  }
  v6 = *(_QWORD *)(*((_QWORD *)this + 34) + 280LL);
  v7 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, LISTENER_CHANNEL *, _QWORD))(*(_QWORD *)v6 + 24LL);
  v8 = STRU::QueryStr((LISTENER_CHANNEL *)((char *)this + 16));
  return v7(v6, v8, this, a2);
}

```

## disassembly

```asm
0x18000af4c  push    rbx
0x18000af4e  push    rbp
0x18000af4f  push    rsi
0x18000af50  push    rdi
0x18000af51  push    r14
0x18000af53  sub     rsp, 40h
0x18000af57  test    byte ptr cs:g_dwDebugFlags, 3
0x18000af5e  mov     r14d, edx
0x18000af61  mov     rsi, rcx
0x18000af64  jz      short loc_18000AFB5
0x18000af66  mov     ebx, [rcx+48h]
0x18000af69  add     rcx, 10h
0x18000af6d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000af74  nop     dword ptr [rax+rax+00h]
0x18000af79  mov     rcx, cs:g_pDebug
0x18000af80  lea     r9, aListenerChanne_1; "LISTENER_CHANNEL::HandleStopListenerCha"...
0x18000af87  mov     [rsp+68h+var_38], ebx
0x18000af8b  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000af92  mov     [rsp+68h+var_40], rax
0x18000af97  mov     r8d, 3BFh
0x18000af9d  lea     rax, aStopListenerch_0; "Stop listenerChannel %S:%d\n"
0x18000afa4  mov     [rsp+68h+var_48], rax
0x18000afa9  call    cs:__imp_PuDbgPrint
0x18000afb0  nop     dword ptr [rax+rax+00h]
0x18000afb5  mov     rax, [rsi+110h]
0x18000afbc  lea     rcx, [rsi+10h]
0x18000afc0  mov     rdi, [rax+118h]
0x18000afc7  mov     rax, [rdi]
0x18000afca  mov     rbx, [rax+18h]
0x18000afce  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000afd5  nop     dword ptr [rax+rax+00h]
0x18000afda  mov     r9d, r14d
0x18000afdd  mov     r8, rsi
0x18000afe0  mov     rdx, rax
0x18000afe3  mov     rcx, rdi
0x18000afe6  mov     rax, rbx
0x18000afe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afee  add     rsp, 40h
0x18000aff2  pop     r14
0x18000aff4  pop     rdi
0x18000aff5  pop     rsi
0x18000aff6  pop     rbp
0x18000aff7  pop     rbx
0x18000aff8  retn
```
