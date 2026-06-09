# WP_IPM::HandleStopListenerChannel(IPM_MESSAGE const *)

- ea: `0x1800078bc`
- end: `0x18000794f`
- name: `?HandleStopListenerChannel@WP_IPM@@QEAAJPEBVIPM_MESSAGE@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, const struct IPM_MESSAGE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001170`

## callees

- `0x180006f04`
- `0x1800078bc`
- `0x18000d010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007929`
- `iisutil!PuDbgPrint` at `0x180007929`

## string_xrefs

- `0x180007917`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandleStopListenerChannel(WP_IPM *this, const struct IPM_MESSAGE *a2)
{
  int *v2; // rax
  int v3; // esi
  const unsigned __int16 *v4; // rdi
  unsigned int v5; // ebx
  W3WP_HOST *v6; // rcx

  v2 = (int *)(*(__int64 (__fastcall **)(const struct IPM_MESSAGE *))(*(_QWORD *)a2 + 16LL))(a2);
  v3 = *v2;
  v4 = (const unsigned __int16 *)(v2 + 2);
  v5 = v2[1];
  LOBYTE(v6) = (g_dwDebugFlags & 3) != 0;
  if ( ((unsigned __int8)v6 & ((g_dwDebugFlags & 0x80000) != 0)) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      839,
      "WP_IPM::HandleStopListenerChannel",
      "Stop ListenerChannel Requested for: %S, ListenerChannelId:%d\n");
  W3WP_HOST::StopListenerChannel(v6, v4, v5, v3);
  return 0;
}

```

## disassembly

```asm
0x1800078bc  mov     [rsp+arg_0], rbx
0x1800078c1  mov     [rsp+arg_8], rsi
0x1800078c6  push    rdi
0x1800078c7  sub     rsp, 40h
0x1800078cb  mov     rax, [rdx]
0x1800078ce  mov     rcx, rdx
0x1800078d1  mov     rax, [rax+10h]
0x1800078d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078da  mov     esi, [rax]
0x1800078dc  lea     rdi, [rax+8]
0x1800078e0  mov     ebx, [rax+4]
0x1800078e3  mov     eax, cs:g_dwDebugFlags
0x1800078e9  test    al, 3
0x1800078eb  setnz   cl
0x1800078ee  bt      eax, 13h
0x1800078f2  setb    al
0x1800078f5  test    al, cl
0x1800078f7  jz      short loc_18000792F
0x1800078f9  mov     rcx, cs:g_pDebug
0x180007900  lea     rax, aStopListenerch; "Stop ListenerChannel Requested for: %S,"...
0x180007907  mov     [rsp+48h+var_18], ebx
0x18000790b  lea     r9, aWpIpmHandlesto; "WP_IPM::HandleStopListenerChannel"
0x180007912  mov     [rsp+48h+var_20], rdi
0x180007917  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000791e  mov     r8d, 347h
0x180007924  mov     [rsp+48h+var_28], rax
0x180007929  call    cs:__imp_PuDbgPrint
0x18000792f  mov     r9d, esi; int
0x180007932  mov     r8d, ebx; unsigned int
0x180007935  mov     rdx, rdi; unsigned __int16 *
0x180007938  call    ?StopListenerChannel@W3WP_HOST@@QEAAXPEBGKH@Z; W3WP_HOST::StopListenerChannel(ushort const *,ulong,int)
0x18000793d  mov     rbx, [rsp+48h+arg_0]
0x180007942  xor     eax, eax
0x180007944  mov     rsi, [rsp+48h+arg_8]
0x180007949  add     rsp, 40h
0x18000794d  pop     rdi
0x18000794e  retn
```
