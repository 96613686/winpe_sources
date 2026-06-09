# WP_IPM::HandleStopListenerChannel(IPM_MESSAGE const *)

- ea: `0x180008088`
- end: `0x180008122`
- name: `?HandleStopListenerChannel@WP_IPM@@QEAAJPEBVIPM_MESSAGE@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, const struct IPM_MESSAGE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001180`

## callees

- `0x1800075dc`
- `0x180008088`
- `0x18000e010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800080f5`
- `iisutil!PuDbgPrint` at `0x1800080f5`

## string_xrefs

- `0x1800080e3`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandleStopListenerChannel(WP_IPM *this, const struct IPM_MESSAGE *a2)
{
  int *v2; // rax
  int v3; // esi
  const wchar_t *v4; // rdi
  unsigned int v5; // ebx
  W3WP_HOST *v6; // rcx

  v2 = (int *)(*(__int64 (__fastcall **)(const struct IPM_MESSAGE *))(*(_QWORD *)a2 + 16LL))(a2);
  v3 = *v2;
  v4 = (const wchar_t *)(v2 + 2);
  v5 = v2[1];
  LOBYTE(v6) = (g_dwDebugFlags & 3) != 0;
  if ( ((unsigned __int8)v6 & ((g_dwDebugFlags & 0x80000) != 0)) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      839,
      "WP_IPM::HandleStopListenerChannel",
      "Stop ListenerChannel Requested for: %S, ListenerChannelId:%d\n",
      v4,
      v5);
  W3WP_HOST::StopListenerChannel(v6, v4, v5, v3);
  return 0;
}

```

## disassembly

```asm
0x180008088  mov     [rsp+arg_0], rbx
0x18000808d  mov     [rsp+arg_8], rsi
0x180008092  push    rdi
0x180008093  sub     rsp, 40h
0x180008097  mov     rax, [rdx]
0x18000809a  mov     rcx, rdx
0x18000809d  mov     rax, [rax+10h]
0x1800080a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a6  mov     esi, [rax]
0x1800080a8  lea     rdi, [rax+8]
0x1800080ac  mov     ebx, [rax+4]
0x1800080af  mov     eax, cs:g_dwDebugFlags
0x1800080b5  test    al, 3
0x1800080b7  setnz   cl
0x1800080ba  bt      eax, 13h
0x1800080be  setb    al
0x1800080c1  test    al, cl
0x1800080c3  jz      short loc_180008101
0x1800080c5  mov     rcx, cs:g_pDebug
0x1800080cc  lea     rax, aStopListenerch; "Stop ListenerChannel Requested for: %S,"...
0x1800080d3  mov     [rsp+48h+var_18], ebx
0x1800080d7  lea     r9, aWpIpmHandlesto; "WP_IPM::HandleStopListenerChannel"
0x1800080de  mov     [rsp+48h+var_20], rdi
0x1800080e3  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800080ea  mov     r8d, 347h
0x1800080f0  mov     [rsp+48h+var_28], rax
0x1800080f5  call    cs:__imp_PuDbgPrint
0x1800080fc  nop     dword ptr [rax+rax+00h]
0x180008101  mov     r9d, esi; int
0x180008104  mov     r8d, ebx; unsigned int
0x180008107  mov     rdx, rdi; unsigned __int16 *
0x18000810a  call    ?StopListenerChannel@W3WP_HOST@@QEAAXPEBGKH@Z; W3WP_HOST::StopListenerChannel(ushort const *,ulong,int)
0x18000810f  mov     rbx, [rsp+48h+arg_0]
0x180008114  xor     eax, eax
0x180008116  mov     rsi, [rsp+48h+arg_8]
0x18000811b  add     rsp, 40h
0x18000811f  pop     rdi
0x180008120  retn
```
