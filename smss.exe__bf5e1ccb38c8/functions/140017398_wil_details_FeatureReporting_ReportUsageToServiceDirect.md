# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140017398`
- end: `0x1400173fd`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14001726c`

## callees

- `0x140016e3c`
- `0x1400170e8`
- `0x140017398`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  int v6; // esi
  _BYTE v8[56]; // [rsp+30h] [rbp-38h] BYREF

  v3 = a2;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && a3 != 254 )
    wil_RtlStagingConfig_RecordFeatureUsage(*(unsigned int *)(a1 + 24), a3, (v3 >> 11) & 1);
  return v6 == 0;
}

```

## disassembly

```asm
0x140017398  mov     [rsp+arg_18], rbx
0x14001739d  push    rbp
0x14001739e  push    rsi
0x14001739f  push    rdi
0x1400173a0  sub     rsp, 50h
0x1400173a4  mov     r9, rdx
0x1400173a7  mov     rbx, rdx
0x1400173aa  mov     rdx, [rcx+8]
0x1400173ae  mov     rbp, rcx
0x1400173b1  shr     r9, 20h
0x1400173b5  lea     rcx, [rsp+68h+var_38]
0x1400173ba  mov     edi, r8d
0x1400173bd  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400173c2  mov     esi, [rax+10h]
0x1400173c5  bt      ebx, 0Ah
0x1400173c9  jnb     short loc_1400173E6
0x1400173cb  cmp     edi, 0FEh
0x1400173d1  jz      short loc_1400173E6
0x1400173d3  mov     ecx, [rbp+18h]
0x1400173d6  mov     edx, edi
0x1400173d8  shr     ebx, 0Bh
0x1400173db  and     ebx, 1
0x1400173de  mov     r8d, ebx
0x1400173e1  call    wil_RtlStagingConfig_RecordFeatureUsage
0x1400173e6  mov     rbx, [rsp+68h+arg_18]
0x1400173ee  xor     eax, eax
0x1400173f0  test    esi, esi
0x1400173f2  setz    al
0x1400173f5  add     rsp, 50h
0x1400173f9  pop     rdi
0x1400173fa  pop     rsi
0x1400173fb  pop     rbp
0x1400173fc  retn
```
