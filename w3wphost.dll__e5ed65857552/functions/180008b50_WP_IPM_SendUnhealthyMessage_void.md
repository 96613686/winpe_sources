# WP_IPM::SendUnhealthyMessage(void)

- ea: `0x180008b50`
- end: `0x180008c03`
- name: `?SendUnhealthyMessage@WP_IPM@@AEAAXXZ`
- size: `179`
- prototype: `void __fastcall(WP_IPM *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001720`
- `0x180004050`
- `0x180008514`
- `0x1800086a0`
- `0x180008818`

## callees

- `0x180008ad4`
- `0x180008b50`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008b96`
- `iisutil!PuDbgPrint` at `0x180008bf0`
- `iisutil!PuDbgPrint` at `0x180008b96`
- `iisutil!PuDbgPrint` at `0x180008bf0`

## string_xrefs

- `0x180008b8f`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180008be9`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
0x180008b50  push    rbx
0x180008b52  sub     rsp, 30h
0x180008b56  mov     eax, cs:g_dwDebugFlags
0x180008b5c  mov     rbx, rcx
0x180008b5f  test    al, 3
0x180008b61  setnz   dl
0x180008b64  bt      eax, 13h
0x180008b68  setb    al
0x180008b6b  test    al, dl
0x180008b6d  jz      short loc_180008BA2
0x180008b6f  mov     rcx, cs:g_pDebug
0x180008b76  lea     rax, aRequestingShut; "Requesting shutdown due to reported unh"...
0x180008b7d  lea     r9, aWpIpmSendunhea; "WP_IPM::SendUnhealthyMessage"
0x180008b84  mov     [rsp+38h+var_18], rax
0x180008b89  mov     r8d, 497h
0x180008b8f  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008b96  call    cs:__imp_PuDbgPrint
0x180008b9d  nop     dword ptr [rax+rax+00h]
0x180008ba2  mov     edx, 6
0x180008ba7  mov     rcx, rbx
0x180008baa  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x180008baf  test    eax, eax
0x180008bb1  jns     short loc_180008BFC
0x180008bb3  mov     eax, cs:g_dwDebugFlags
0x180008bb9  test    al, 3
0x180008bbb  setnz   cl
0x180008bbe  bt      eax, 13h
0x180008bc2  setb    al
0x180008bc5  test    al, cl
0x180008bc7  jz      short loc_180008BFC
0x180008bc9  mov     rcx, cs:g_pDebug
0x180008bd0  lea     rax, aFailedTellingW; "Failed telling WAS to shut us down\n\n"
0x180008bd7  lea     r9, aWpIpmSendunhea; "WP_IPM::SendUnhealthyMessage"
0x180008bde  mov     [rsp+38h+var_18], rax
0x180008be3  mov     r8d, 4A1h
0x180008be9  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008bf0  call    cs:__imp_PuDbgPrint
0x180008bf7  nop     dword ptr [rax+rax+00h]
0x180008bfc  add     rsp, 30h
0x180008c00  pop     rbx
0x180008c01  retn
```
