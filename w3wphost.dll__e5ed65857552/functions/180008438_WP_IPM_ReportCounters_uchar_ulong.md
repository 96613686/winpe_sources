# WP_IPM::ReportCounters(uchar *,ulong)

- ea: `0x180008438`
- end: `0x18000850c`
- name: `?ReportCounters@WP_IPM@@QEAAXPEAEK@Z`
- size: `212`
- prototype: `void __fastcall(WP_IPM *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006cd0`
- `0x180006d24`

## callees

- `0x180001890`
- `0x180008438`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000848f`
- `iisutil!PuDbgPrint` at `0x1800084ef`
- `iisutil!PuDbgPrint` at `0x18000848f`
- `iisutil!PuDbgPrint` at `0x1800084ef`

## string_xrefs

- `0x180008488`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x1800084e8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
0x180008438  mov     [rsp+arg_0], rbx
0x18000843d  mov     [rsp+arg_8], rsi
0x180008442  push    rdi
0x180008443  sub     rsp, 30h
0x180008447  mov     eax, cs:g_dwDebugFlags
0x18000844d  mov     ebx, r8d
0x180008450  test    al, 3
0x180008452  mov     rdi, rdx
0x180008455  mov     rsi, rcx
0x180008458  setnz   r9b
0x18000845c  bt      eax, 13h
0x180008460  setb    al
0x180008463  test    al, r9b
0x180008466  jz      short loc_18000849B
0x180008468  mov     rcx, cs:g_pDebug
0x18000846f  lea     rax, aSendingCounter; "Sending counters to WAS\n\n"
0x180008476  lea     r9, aWpIpmReportcou; "WP_IPM::ReportCounters"
0x18000847d  mov     [rsp+38h+var_18], rax
0x180008482  mov     r8d, 5AEh
0x180008488  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000848f  call    cs:__imp_PuDbgPrint
0x180008496  nop     dword ptr [rax+rax+00h]
0x18000849b  mov     r9, rdi
0x18000849e  mov     r8d, ebx
0x1800084a1  mov     edx, 6
0x1800084a6  mov     rcx, rsi
0x1800084a9  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x1800084ae  test    eax, eax
0x1800084b0  jns     short loc_1800084FB
0x1800084b2  mov     eax, cs:g_dwDebugFlags
0x1800084b8  test    al, 3
0x1800084ba  setnz   cl
0x1800084bd  bt      eax, 13h
0x1800084c1  setb    al
0x1800084c4  test    al, cl
0x1800084c6  jz      short loc_1800084FB
0x1800084c8  mov     rcx, cs:g_pDebug
0x1800084cf  lea     rax, aFailedReportin; "Failed reporting counters to WAS\n\n"
0x1800084d6  lea     r9, aWpIpmReportcou; "WP_IPM::ReportCounters"
0x1800084dd  mov     [rsp+38h+var_18], rax
0x1800084e2  mov     r8d, 5BFh
0x1800084e8  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800084ef  call    cs:__imp_PuDbgPrint
0x1800084f6  nop     dword ptr [rax+rax+00h]
0x1800084fb  mov     rbx, [rsp+38h+arg_0]
0x180008500  mov     rsi, [rsp+38h+arg_8]
0x180008505  add     rsp, 30h
0x180008509  pop     rdi
0x18000850a  retn
```
