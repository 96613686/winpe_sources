# W3WP_HOST::RecycleWorkerProcess(ushort const *)

- ea: `0x180006a30`
- end: `0x180006a8c`
- name: `?RecycleWorkerProcess@W3WP_HOST@@UEAAXPEBG@Z`
- size: `92`
- prototype: `void __fastcall(W3WP_HOST *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006a30`
- `0x180008ad4`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006a7a`
- `iisutil!PuDbgPrint` at `0x180006a7a`

## string_xrefs

- `0x180006a61`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
void __fastcall W3WP_HOST::RecycleWorkerProcess(W3WP_HOST *this, const unsigned __int16 *a2)
{
  int v2; // eax

  v2 = WP_IPM::SendShutdownRequestMessage(*((_QWORD *)this + 8), 6);
  if ( v2 < 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      4750,
      "W3WP_HOST::RecycleWorkerProcess",
      "failed to send recycling request message to WAS: hr=0x%x\n",
      v2);
}

```

## disassembly

```asm
0x180006a30  sub     rsp, 38h
0x180006a34  mov     rcx, [rcx+40h]
0x180006a38  mov     edx, 6
0x180006a3d  call    ?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)
0x180006a42  test    eax, eax
0x180006a44  jns     short loc_180006A86
0x180006a46  test    byte ptr cs:g_dwDebugFlags, 3
0x180006a4d  jz      short loc_180006A86
0x180006a4f  mov     rcx, cs:g_pDebug
0x180006a56  lea     r9, aW3wpHostRecycl; "W3WP_HOST::RecycleWorkerProcess"
0x180006a5d  mov     [rsp+38h+var_10], eax
0x180006a61  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006a68  lea     rax, aFailedToSendRe; "failed to send recycling request messag"...
0x180006a6f  mov     r8d, 128Eh
0x180006a75  mov     [rsp+38h+var_18], rax
0x180006a7a  call    cs:__imp_PuDbgPrint
0x180006a81  nop     dword ptr [rax+rax+00h]
0x180006a86  add     rsp, 38h
0x180006a8a  retn
```
