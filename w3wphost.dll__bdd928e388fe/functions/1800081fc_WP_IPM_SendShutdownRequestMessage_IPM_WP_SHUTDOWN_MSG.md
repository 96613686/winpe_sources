# WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)

- ea: `0x1800081fc`
- end: `0x180008269`
- name: `?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z`
- size: `109`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800063f0`
- `0x18000812c`
- `0x180008270`
- `0x18000850c`
- `0x180009044`

## callees

- `0x180001830`
- `0x1800081fc`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008247`
- `iisutil!PuDbgPrint` at `0x180008247`

## string_xrefs

- `0x180008240`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::SendShutdownRequestMessage(__int64 a1, int a2)
{
  int v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = a2;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1143,
      "WP_IPM::SendShutdownRequestMessage",
      "Requesting shutdown\n");
  return WP_IPM::WriteMessage(a1, 3, 4u, (__int64)&v4);
}

```

## disassembly

```asm
0x1800081fc  mov     [rsp+arg_8], edx
0x180008200  push    rbx
0x180008201  sub     rsp, 30h
0x180008205  mov     eax, cs:g_dwDebugFlags
0x18000820b  mov     rbx, rcx
0x18000820e  test    al, 3
0x180008210  setnz   r8b
0x180008214  bt      eax, 13h
0x180008218  setb    al
0x18000821b  test    al, r8b
0x18000821e  jz      short loc_18000824D
0x180008220  mov     rcx, cs:g_pDebug
0x180008227  lea     rax, aRequestingShut_0; "Requesting shutdown\n"
0x18000822e  lea     r9, aWpIpmSendshutd; "WP_IPM::SendShutdownRequestMessage"
0x180008235  mov     [rsp+38h+var_18], rax
0x18000823a  mov     r8d, 477h
0x180008240  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008247  call    cs:__imp_PuDbgPrint
0x18000824d  mov     edx, 3
0x180008252  lea     r9, [rsp+38h+arg_8]
0x180008257  mov     rcx, rbx
0x18000825a  lea     r8d, [rdx+1]
0x18000825e  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180008263  add     rsp, 30h
0x180008267  pop     rbx
0x180008268  retn
```
