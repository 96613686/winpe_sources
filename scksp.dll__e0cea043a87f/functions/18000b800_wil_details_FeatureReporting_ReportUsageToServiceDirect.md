# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000b800`
- end: `0x18000b86a`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000b784`

## callees

- `0x18000b354`
- `0x18000b600`
- `0x18000b800`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  int v5; // esi
  _BYTE v7[40]; // [rsp+30h] [rbp-28h] BYREF

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v7,
         (volatile signed __int32 *)Feature_Servicing_SmartCardKspPqcSupport__private_reporting,
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && a3 != 254 )
    wil_RtlStagingConfig_RecordFeatureUsage(59873727, a3, (v3 >> 11) & 1);
  return v5 == 0;
}

```

## disassembly

```asm
0x18000b800  mov     [rsp+arg_0], rbx
0x18000b805  mov     [rsp+arg_18], rsi
0x18000b80a  push    rdi
0x18000b80b  sub     rsp, 50h
0x18000b80f  mov     r9, rdx
0x18000b812  lea     rcx, [rsp+58h+var_28]
0x18000b817  mov     rbx, rdx
0x18000b81a  shr     r9, 20h
0x18000b81e  mov     rdx, cs:off_1800486C8
0x18000b825  mov     edi, r8d
0x18000b828  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000b82d  mov     esi, [rax+10h]
0x18000b830  bt      ebx, 0Ah
0x18000b834  jnb     short loc_18000B853
0x18000b836  cmp     edi, 0FEh
0x18000b83c  jz      short loc_18000B853
0x18000b83e  shr     ebx, 0Bh
0x18000b841  mov     edx, edi
0x18000b843  and     ebx, 1
0x18000b846  mov     ecx, 39199BFh
0x18000b84b  mov     r8d, ebx
0x18000b84e  call    wil_RtlStagingConfig_RecordFeatureUsage
0x18000b853  mov     rbx, [rsp+58h+arg_0]
0x18000b858  xor     eax, eax
0x18000b85a  test    esi, esi
0x18000b85c  mov     rsi, [rsp+58h+arg_18]
0x18000b861  setz    al
0x18000b864  add     rsp, 50h
0x18000b868  pop     rdi
0x18000b869  retn
```
