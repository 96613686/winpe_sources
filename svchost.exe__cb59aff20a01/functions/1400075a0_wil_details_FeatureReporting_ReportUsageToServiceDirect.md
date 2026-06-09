# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1400075a0`
- end: `0x140007645`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x140007484`

## callees

- `0x140007300`
- `0x1400075a0`
- `0x1400078bc`
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
0x1400075a0  mov     [rsp+arg_0], rbx
0x1400075a5  mov     [rsp+arg_18], rsi
0x1400075aa  push    rdi
0x1400075ab  sub     rsp, 50h
0x1400075af  mov     r9, rdx
0x1400075b2  lea     rcx, [rsp+58h+var_20]
0x1400075b7  mov     rbx, rdx
0x1400075ba  shr     r9, 20h
0x1400075be  mov     rdx, cs:off_14000CAE0
0x1400075c5  mov     edi, r8d
0x1400075c8  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400075cd  mov     esi, [rax+10h]
0x1400075d0  bt      ebx, 0Ah
0x1400075d4  jnb     short loc_14000762E
0x1400075d6  cmp     edi, 0FEh
0x1400075dc  jz      short loc_14000762E
0x1400075de  mov     [rsp+58h+var_28], 0
0x1400075e7  mov     dword ptr [rsp+58h+var_28], 1DD0303h
0x1400075ef  mov     word ptr [rsp+58h+var_28+4], di
0x1400075f4  bt      ebx, 0Bh
0x1400075f8  jnb     short loc_140007600
0x1400075fa  or      word ptr [rsp+58h+var_28+6], 1
0x140007600  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140007607  test    rax, rax
0x14000760a  jnz     short loc_140007624
0x14000760c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140007613  call    wil_details_GetNtDllProcedureAddress
0x140007618  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000761f  test    rax, rax
0x140007622  jz      short loc_14000762E
0x140007624  lea     rcx, [rsp+58h+var_28]
0x140007629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000762e  mov     rbx, [rsp+58h+arg_0]
0x140007633  xor     eax, eax
0x140007635  test    esi, esi
0x140007637  mov     rsi, [rsp+58h+arg_18]
0x14000763c  setz    al
0x14000763f  add     rsp, 50h
0x140007643  pop     rdi
0x140007644  retn
```
