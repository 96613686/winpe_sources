# W3WP_HOST::RecycleWorkerProcess(ushort const *)

- ea: `0x1800063f0`
- end: `0x180006445`
- name: `?RecycleWorkerProcess@W3WP_HOST@@UEAAXPEBG@Z`
- size: `85`
- prototype: `void __fastcall(W3WP_HOST *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800063f0`
- `0x1800081fc`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000643a`
- `iisutil!PuDbgPrint` at `0x18000643a`

## string_xrefs

- `0x180006421`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
void __fastcall W3WP_HOST::RecycleWorkerProcess(W3WP_HOST *this, const unsigned __int16 *a2)
{
  if ( (int)WP_IPM::SendShutdownRequestMessage(*((_QWORD *)this + 8), 6) < 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      4750,
      "W3WP_HOST::RecycleWorkerProcess",
      "failed to send recycling request message to WAS: hr=0x%x\n");
}

```

## disassembly

```asm
0x1800063f0  sub     rsp, 38h
0x1800063f4  mov     rcx, [rcx+40h]
0x1800063f8  mov     edx, 6
0x1800063fd  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x180006402  test    eax, eax
0x180006404  jns     short loc_180006440
0x180006406  test    byte ptr cs:g_dwDebugFlags, 3
0x18000640d  jz      short loc_180006440
0x18000640f  mov     rcx, cs:g_pDebug
0x180006416  lea     r9, aW3wpHostRecycl; "W3WP_HOST::RecycleWorkerProcess"
0x18000641d  mov     [rsp+38h+var_10], eax
0x180006421  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006428  lea     rax, aFailedToSendRe; "failed to send recycling request messag"...
0x18000642f  mov     r8d, 128Eh
0x180006435  mov     [rsp+38h+var_18], rax
0x18000643a  call    cs:__imp_PuDbgPrint
0x180006440  add     rsp, 38h
0x180006444  retn
```
