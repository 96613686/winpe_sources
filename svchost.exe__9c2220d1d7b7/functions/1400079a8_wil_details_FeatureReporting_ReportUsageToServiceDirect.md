# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1400079a8`
- end: `0x140007a4e`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x14000792c`

## callees

- `0x1400077a8`
- `0x1400079a8`
- `0x140007d00`
- `0x140009010`

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
         (volatile signed __int32 *)&Feature_ResourceManagerLimits__private_reporting,
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v8 = 31261443;
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
0x1400079a8  mov     [rsp+arg_0], rbx
0x1400079ad  mov     [rsp+arg_18], rsi
0x1400079b2  push    rdi
0x1400079b3  sub     rsp, 50h
0x1400079b7  mov     r9, rdx
0x1400079ba  lea     rcx, [rsp+58h+var_20]
0x1400079bf  mov     rbx, rdx
0x1400079c2  shr     r9, 20h
0x1400079c6  mov     rdx, cs:off_14000CB00
0x1400079cd  mov     edi, r8d
0x1400079d0  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400079d5  mov     esi, [rax+10h]
0x1400079d8  bt      ebx, 0Ah
0x1400079dc  jnb     short loc_140007A36
0x1400079de  cmp     edi, 0FEh
0x1400079e4  jz      short loc_140007A36
0x1400079e6  mov     [rsp+58h+var_28], 0
0x1400079ef  mov     dword ptr [rsp+58h+var_28], 1DD0303h
0x1400079f7  mov     word ptr [rsp+58h+var_28+4], di
0x1400079fc  bt      ebx, 0Bh
0x140007a00  jnb     short loc_140007A08
0x140007a02  or      word ptr [rsp+58h+var_28+6], 1
0x140007a08  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140007a0f  test    rax, rax
0x140007a12  jnz     short loc_140007A2C
0x140007a14  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140007a1b  call    wil_details_GetNtDllProcedureAddress
0x140007a20  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140007a27  test    rax, rax
0x140007a2a  jz      short loc_140007A36
0x140007a2c  lea     rcx, [rsp+58h+var_28]
0x140007a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a36  mov     rbx, [rsp+58h+arg_0]
0x140007a3b  xor     eax, eax
0x140007a3d  test    esi, esi
0x140007a3f  mov     rsi, [rsp+58h+arg_18]
0x140007a44  setz    al
0x140007a47  add     rsp, 50h
0x140007a4b  pop     rdi
0x140007a4c  retn
```
