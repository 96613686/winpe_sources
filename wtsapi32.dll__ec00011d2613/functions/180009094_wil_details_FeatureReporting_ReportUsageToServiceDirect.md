# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180009094`
- end: `0x180009139`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180009018`

## callees

- `0x180008e94`
- `0x180009094`
- `0x1800093ac`
- `0x180016010`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  int v5; // esi
  FARPROC NtDllProcedureAddress; // rax
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v9,
         (volatile signed __int32 *)&Feature_RailV2ServerBuildSupported__private_reporting,
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v8 = 59083637;
    WORD2(v8) = a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v8) |= 1u;
    NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage"),
          (g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress) != 0) )
    {
      ((void (__fastcall *)(__int64 *))NtDllProcedureAddress)(&v8);
    }
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x180009094  mov     [rsp+arg_0], rbx
0x180009099  mov     [rsp+arg_18], rsi
0x18000909e  push    rdi
0x18000909f  sub     rsp, 50h
0x1800090a3  mov     r9, rdx
0x1800090a6  lea     rcx, [rsp+58h+var_20]
0x1800090ab  mov     rbx, rdx
0x1800090ae  shr     r9, 20h
0x1800090b2  mov     rdx, cs:off_18001C330
0x1800090b9  mov     edi, r8d
0x1800090bc  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800090c1  mov     esi, [rax+10h]
0x1800090c4  bt      ebx, 0Ah
0x1800090c8  jnb     short loc_180009122
0x1800090ca  cmp     edi, 0FEh
0x1800090d0  jz      short loc_180009122
0x1800090d2  mov     [rsp+58h+var_28], 0
0x1800090db  mov     dword ptr [rsp+58h+var_28], 3858B75h
0x1800090e3  mov     word ptr [rsp+58h+var_28+4], di
0x1800090e8  bt      ebx, 0Bh
0x1800090ec  jnb     short loc_1800090F4
0x1800090ee  or      word ptr [rsp+58h+var_28+6], 1
0x1800090f4  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800090fb  test    rax, rax
0x1800090fe  jnz     short loc_180009118
0x180009100  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009107  call    wil_details_GetNtDllProcedureAddress
0x18000910c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009113  test    rax, rax
0x180009116  jz      short loc_180009122
0x180009118  lea     rcx, [rsp+58h+var_28]
0x18000911d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009122  mov     rbx, [rsp+58h+arg_0]
0x180009127  xor     eax, eax
0x180009129  test    esi, esi
0x18000912b  mov     rsi, [rsp+58h+arg_18]
0x180009130  setz    al
0x180009133  add     rsp, 50h
0x180009137  pop     rdi
0x180009138  retn
```
