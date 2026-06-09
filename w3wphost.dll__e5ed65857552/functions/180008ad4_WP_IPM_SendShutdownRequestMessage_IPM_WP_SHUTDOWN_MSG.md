# WP_IPM::SendShutdownRequestMessage(IPM_WP_SHUTDOWN_MSG)

- ea: `0x180008ad4`
- end: `0x180008b48`
- name: `?SendShutdownRequestMessage@WP_IPM@@QEAAJW4IPM_WP_SHUTDOWN_MSG@@@Z`
- size: `116`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006a30`
- `0x1800089f4`
- `0x180008b50`
- `0x180008e1c`
- `0x180009a78`

## callees

- `0x180001890`
- `0x180008ad4`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008b1f`
- `iisutil!PuDbgPrint` at `0x180008b1f`

## string_xrefs

- `0x180008b18`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
0x180008ad4  mov     [rsp+arg_8], edx
0x180008ad8  push    rbx
0x180008ad9  sub     rsp, 30h
0x180008add  mov     eax, cs:g_dwDebugFlags
0x180008ae3  mov     rbx, rcx
0x180008ae6  test    al, 3
0x180008ae8  setnz   r8b
0x180008aec  bt      eax, 13h
0x180008af0  setb    al
0x180008af3  test    al, r8b
0x180008af6  jz      short loc_180008B2B
0x180008af8  mov     rcx, cs:g_pDebug
0x180008aff  lea     rax, aRequestingShut_0; "Requesting shutdown\n"
0x180008b06  lea     r9, aWpIpmSendshutd; "WP_IPM::SendShutdownRequestMessage"
0x180008b0d  mov     [rsp+38h+var_18], rax
0x180008b12  mov     r8d, 477h
0x180008b18  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008b1f  call    cs:__imp_PuDbgPrint
0x180008b26  nop     dword ptr [rax+rax+00h]
0x180008b2b  mov     edx, 3
0x180008b30  lea     r9, [rsp+38h+arg_8]
0x180008b35  mov     rcx, rbx
0x180008b38  lea     r8d, [rdx+1]
0x180008b3c  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180008b41  add     rsp, 30h
0x180008b45  pop     rbx
0x180008b46  retn
```
