# WP_IPM::SendUnhealthyMessage(void)

- ea: `0x180008270`
- end: `0x180008316`
- name: `?SendUnhealthyMessage@WP_IPM@@AEAAXXZ`
- size: `166`
- prototype: `void __fastcall(WP_IPM *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800016e0`
- `0x180003d50`
- `0x180007ce8`
- `0x180007e48`
- `0x180007f8c`

## callees

- `0x1800081fc`
- `0x180008270`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800082b6`
- `iisutil!PuDbgPrint` at `0x18000830a`
- `iisutil!PuDbgPrint` at `0x1800082b6`
- `iisutil!PuDbgPrint` at `0x18000830a`

## string_xrefs

- `0x1800082af`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180008303`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
void __fastcall WP_IPM::SendUnhealthyMessage(WP_IPM *this)
{
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1175,
      "WP_IPM::SendUnhealthyMessage",
      "Requesting shutdown due to reported unhealthiness\n\n");
  if ( (int)WP_IPM::SendShutdownRequestMessage(this, 6) < 0
    && (g_dwDebugFlags & 3) != 0
    && (g_dwDebugFlags & 0x80000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1185,
      "WP_IPM::SendUnhealthyMessage",
      "Failed telling WAS to shut us down\n\n");
  }
}

```

## disassembly

```asm
0x180008270  push    rbx
0x180008272  sub     rsp, 30h
0x180008276  mov     eax, cs:g_dwDebugFlags
0x18000827c  mov     rbx, rcx
0x18000827f  test    al, 3
0x180008281  setnz   dl
0x180008284  bt      eax, 13h
0x180008288  setb    al
0x18000828b  test    al, dl
0x18000828d  jz      short loc_1800082BC
0x18000828f  mov     rcx, cs:g_pDebug
0x180008296  lea     rax, aRequestingShut; "Requesting shutdown due to reported unh"...
0x18000829d  lea     r9, aWpIpmSendunhea; "WP_IPM::SendUnhealthyMessage"
0x1800082a4  mov     [rsp+38h+var_18], rax
0x1800082a9  mov     r8d, 497h
0x1800082af  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800082b6  call    cs:__imp_PuDbgPrint
0x1800082bc  mov     edx, 6
0x1800082c1  mov     rcx, rbx
0x1800082c4  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x1800082c9  test    eax, eax
0x1800082cb  jns     short loc_180008310
0x1800082cd  mov     eax, cs:g_dwDebugFlags
0x1800082d3  test    al, 3
0x1800082d5  setnz   cl
0x1800082d8  bt      eax, 13h
0x1800082dc  setb    al
0x1800082df  test    al, cl
0x1800082e1  jz      short loc_180008310
0x1800082e3  mov     rcx, cs:g_pDebug
0x1800082ea  lea     rax, aFailedTellingW; "Failed telling WAS to shut us down\n\n"
0x1800082f1  lea     r9, aWpIpmSendunhea; "WP_IPM::SendUnhealthyMessage"
0x1800082f8  mov     [rsp+38h+var_18], rax
0x1800082fd  mov     r8d, 4A1h
0x180008303  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000830a  call    cs:__imp_PuDbgPrint
0x180008310  add     rsp, 30h
0x180008314  pop     rbx
0x180008315  retn
```
