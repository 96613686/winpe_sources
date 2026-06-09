# TooMuchContextSwitchingLoad(ulong,ulong,ulong,ulong)

- ea: `0x1800035c0`
- end: `0x1800036ff`
- name: `?TooMuchContextSwitchingLoad@@YAHKKKK@Z`
- size: `319`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001450`

## callees

- `0x180002d54`
- `0x1800035c0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035fe`
- `iisutil!PuDbgPrint` at `0x1800036a4`
- `iisutil!PuDbgPrint` at `0x1800036e2`
- `iisutil!PuDbgPrint` at `0x1800036a4`
- `iisutil!PuDbgPrint` at `0x1800036e2`

## string_xrefs

- `0x18000369d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x1800036db`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x18000367e`: `W3TP: Not creating thread, ContextSwitch rate is: %g\n`
- `0x1800036bc`: `W3TP: OK to create thread, ContextSwitch rate is: %g\n`

## pseudocode

```c
__int64 __fastcall TooMuchContextSwitchingLoad(unsigned int a1, unsigned int a2, int a3)
{
  int v3; // ebp
  unsigned int ContextSwitchCount; // ebx
  DWORD TickCount; // eax
  int v9; // ecx
  signed int v10; // eax
  double v11; // xmm2_8
  int v12; // eax
  double v13; // xmm2_8
  unsigned int v15; // [rsp+68h] [rbp+20h] BYREF

  v3 = g_dwNumProcs;
  v15 = 0;
  ContextSwitchCount = GetContextSwitchCount(&v15);
  if ( ContextSwitchCount )
  {
    TickCount = GetTickCount();
    ContextSwitchCount = 1;
    v9 = TickCount - a2 - 1;
    if ( TickCount > a2 )
      v9 = TickCount - a2;
    if ( v15 > a1 )
      v10 = v15 - a1;
    else
      v10 = v15 - a1 - 1;
    v11 = (double)v10;
    v12 = 2 * a3;
    if ( (unsigned int)v3 <= 1 )
      v12 = a3;
    v13 = v11 / ((double)v9 / 1000.0);
    if ( v13 / (double)v3 <= (double)v12 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
          1913,
          "TooMuchContextSwitchingLoad",
          "W3TP: OK to create thread, ContextSwitch rate is: %g\n",
          v13);
      return 0;
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
        1908,
        "TooMuchContextSwitchingLoad",
        "W3TP: Not creating thread, ContextSwitch rate is: %g\n",
        v13);
    }
  }
  return ContextSwitchCount;
}

```

## disassembly

```asm
0x1800035c0  mov     rax, rsp
0x1800035c3  mov     [rax+8], rbx
0x1800035c7  mov     [rax+10h], rbp
0x1800035cb  mov     [rax+20h], r9d
0x1800035cf  push    rsi
0x1800035d0  push    rdi
0x1800035d1  push    r14
0x1800035d3  sub     rsp, 30h
0x1800035d7  mov     ebp, cs:?g_dwNumProcs@@3KA; ulong g_dwNumProcs
0x1800035dd  mov     edi, ecx
0x1800035df  lea     rcx, [rax+20h]; unsigned int *
0x1800035e3  mov     dword ptr [rax+20h], 0
0x1800035ea  mov     r14d, r8d
0x1800035ed  mov     esi, edx
0x1800035ef  call    ?GetContextSwitchCount@@YAHPEAK@Z; GetContextSwitchCount(ulong *)
0x1800035f4  mov     ebx, eax
0x1800035f6  test    eax, eax
0x1800035f8  jz      loc_1800036EA
0x1800035fe  call    cs:__imp_GetTickCount
0x180003604  mov     r8d, eax
0x180003607  mov     ebx, 1
0x18000360c  sub     r8d, esi
0x18000360f  cmp     eax, esi
0x180003611  mov     eax, [rsp+48h+arg_18]
0x180003615  lea     ecx, [r8-1]
0x180003619  cmova   ecx, r8d
0x18000361d  cmp     eax, edi
0x18000361f  ja      short loc_180003627
0x180003621  sub     eax, edi
0x180003623  sub     eax, ebx
0x180003625  jmp     short loc_180003629
0x180003627  sub     eax, edi
0x180003629  xorps   xmm0, xmm0
0x18000362c  xorps   xmm2, xmm2
0x18000362f  cvtsi2sd xmm2, rax
0x180003634  mov     eax, ecx
0x180003636  cmp     ebp, ebx
0x180003638  cvtsi2sd xmm0, rax
0x18000363d  lea     eax, [r14+r14]
0x180003641  cmovbe  eax, r14d
0x180003645  divsd   xmm0, cs:__real@408f400000000000
0x18000364d  divsd   xmm2, xmm0
0x180003651  xorps   xmm0, xmm0
0x180003654  cvtsi2sd xmm0, rbp
0x180003659  movaps  xmm1, xmm2
0x18000365c  divsd   xmm1, xmm0
0x180003660  xorps   xmm0, xmm0
0x180003663  cvtsi2sd xmm0, rax
0x180003668  comisd  xmm1, xmm0
0x18000366c  jbe     short loc_1800036AC
0x18000366e  test    cs:g_dwDebugFlags, 3
0x180003675  jz      short loc_1800036EA
0x180003677  mov     rcx, cs:g_pDebug
0x18000367e  lea     rax, aW3tpNotCreatin; "W3TP: Not creating thread, ContextSwitc"...
0x180003685  movsd   [rsp+48h+var_20], xmm2
0x18000368b  lea     r9, aToomuchcontext; "TooMuchContextSwitchingLoad"
0x180003692  mov     r8d, 774h
0x180003698  mov     [rsp+48h+var_28], rax
0x18000369d  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800036a4  call    cs:__imp_PuDbgPrint
0x1800036aa  jmp     short loc_1800036EA
0x1800036ac  test    cs:g_dwDebugFlags, 3
0x1800036b3  jz      short loc_1800036E8
0x1800036b5  mov     rcx, cs:g_pDebug
0x1800036bc  lea     rax, aW3tpOkToCreate; "W3TP: OK to create thread, ContextSwitc"...
0x1800036c3  movsd   [rsp+48h+var_20], xmm2
0x1800036c9  lea     r9, aToomuchcontext; "TooMuchContextSwitchingLoad"
0x1800036d0  mov     r8d, 779h
0x1800036d6  mov     [rsp+48h+var_28], rax
0x1800036db  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800036e2  call    cs:__imp_PuDbgPrint
0x1800036e8  xor     ebx, ebx
0x1800036ea  mov     rbp, [rsp+48h+arg_8]
0x1800036ef  mov     eax, ebx
0x1800036f1  mov     rbx, [rsp+48h+arg_0]
0x1800036f6  add     rsp, 30h
0x1800036fa  pop     r14
0x1800036fc  pop     rdi
0x1800036fd  pop     rsi
0x1800036fe  retn
```
