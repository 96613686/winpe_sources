# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000f418`
- end: `0x18000f472`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b5b0`

## callees

- `0x18000c070`
- `0x18000f418`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_RecordFeatureUsage(int a1, __int16 a2, int a3)
{
  FARPROC NtDllProcedureAddress; // rax
  int v5; // [rsp+48h] [rbp+20h] BYREF
  __int16 v6; // [rsp+4Ch] [rbp+24h]
  __int16 v7; // [rsp+4Eh] [rbp+26h]

  v7 = 0;
  v5 = a1;
  v6 = a2;
  if ( a3 )
    v7 |= 1u;
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
  if ( g_wil_details_pfnRtlNotifyFeatureUsage )
    return ((__int64 (__fastcall *)(int *))NtDllProcedureAddress)(&v5);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage");
  g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(int *))NtDllProcedureAddress)(&v5);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000f418  mov     rax, rsp
0x18000f41b  sub     rsp, 28h
0x18000f41f  mov     qword ptr [rax+20h], 0
0x18000f427  mov     [rax+20h], ecx
0x18000f42a  mov     [rax+24h], dx
0x18000f42e  test    r8d, r8d
0x18000f431  jz      short loc_18000F438
0x18000f433  or      word ptr [rax+26h], 1
0x18000f438  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000f43f  test    rax, rax
0x18000f442  jnz     short loc_18000F463
0x18000f444  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000f44b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f450  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000f457  test    rax, rax
0x18000f45a  jnz     short loc_18000F463
0x18000f45c  mov     eax, 0C0000139h
0x18000f461  jmp     short loc_18000F46D
0x18000f463  lea     rcx, [rsp+28h+arg_18]
0x18000f468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f46d  add     rsp, 28h
0x18000f471  retn
```
