# WP_IPM::ReportCounters(uchar *,ulong)

- ea: `0x180007c18`
- end: `0x180007cdf`
- name: `?ReportCounters@WP_IPM@@QEAAXPEAEK@Z`
- size: `199`
- prototype: `void __fastcall(WP_IPM *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006670`
- `0x1800066c4`

## callees

- `0x180001830`
- `0x180007c18`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007c6f`
- `iisutil!PuDbgPrint` at `0x180007cc9`
- `iisutil!PuDbgPrint` at `0x180007c6f`
- `iisutil!PuDbgPrint` at `0x180007cc9`

## string_xrefs

- `0x180007c68`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180007cc2`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
void __fastcall WP_IPM::ReportCounters(WP_IPM *this, unsigned __int8 *a2, unsigned int a3)
{
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1454,
      "WP_IPM::ReportCounters",
      "Sending counters to WAS\n\n");
  if ( (int)WP_IPM::WriteMessage((__int64)this, 6, a3, (__int64)a2) < 0
    && (g_dwDebugFlags & 3) != 0
    && (g_dwDebugFlags & 0x80000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1471,
      "WP_IPM::ReportCounters",
      "Failed reporting counters to WAS\n\n");
  }
}

```

## disassembly

```asm
0x180007c18  mov     [rsp+arg_0], rbx
0x180007c1d  mov     [rsp+arg_8], rsi
0x180007c22  push    rdi
0x180007c23  sub     rsp, 30h
0x180007c27  mov     eax, cs:g_dwDebugFlags
0x180007c2d  mov     ebx, r8d
0x180007c30  test    al, 3
0x180007c32  mov     rdi, rdx
0x180007c35  mov     rsi, rcx
0x180007c38  setnz   r9b
0x180007c3c  bt      eax, 13h
0x180007c40  setb    al
0x180007c43  test    al, r9b
0x180007c46  jz      short loc_180007C75
0x180007c48  mov     rcx, cs:g_pDebug
0x180007c4f  lea     rax, aSendingCounter; "Sending counters to WAS\n\n"
0x180007c56  lea     r9, aWpIpmReportcou; "WP_IPM::ReportCounters"
0x180007c5d  mov     [rsp+38h+var_18], rax
0x180007c62  mov     r8d, 5AEh
0x180007c68  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007c6f  call    cs:__imp_PuDbgPrint
0x180007c75  mov     r9, rdi
0x180007c78  mov     r8d, ebx
0x180007c7b  mov     edx, 6
0x180007c80  mov     rcx, rsi
0x180007c83  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180007c88  test    eax, eax
0x180007c8a  jns     short loc_180007CCF
0x180007c8c  mov     eax, cs:g_dwDebugFlags
0x180007c92  test    al, 3
0x180007c94  setnz   cl
0x180007c97  bt      eax, 13h
0x180007c9b  setb    al
0x180007c9e  test    al, cl
0x180007ca0  jz      short loc_180007CCF
0x180007ca2  mov     rcx, cs:g_pDebug
0x180007ca9  lea     rax, aFailedReportin; "Failed reporting counters to WAS\n\n"
0x180007cb0  lea     r9, aWpIpmReportcou; "WP_IPM::ReportCounters"
0x180007cb7  mov     [rsp+38h+var_18], rax
0x180007cbc  mov     r8d, 5BFh
0x180007cc2  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007cc9  call    cs:__imp_PuDbgPrint
0x180007ccf  mov     rbx, [rsp+38h+arg_0]
0x180007cd4  mov     rsi, [rsp+38h+arg_8]
0x180007cd9  add     rsp, 30h
0x180007cdd  pop     rdi
0x180007cde  retn
```
