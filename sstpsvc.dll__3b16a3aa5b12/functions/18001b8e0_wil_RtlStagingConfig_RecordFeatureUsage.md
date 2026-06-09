# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18001b8e0`
- end: `0x18001b93a`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001aeb0`

## callees

- `0x18001b67c`
- `0x18001b8e0`
- `0x18001d010`

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
0x18001b8e0  mov     rax, rsp
0x18001b8e3  sub     rsp, 28h
0x18001b8e7  mov     qword ptr [rax+20h], 0
0x18001b8ef  mov     [rax+20h], ecx
0x18001b8f2  mov     [rax+24h], dx
0x18001b8f6  test    r8d, r8d
0x18001b8f9  jz      short loc_18001B900
0x18001b8fb  or      word ptr [rax+26h], 1
0x18001b900  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001b907  test    rax, rax
0x18001b90a  jnz     short loc_18001B92B
0x18001b90c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001b913  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b918  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001b91f  test    rax, rax
0x18001b922  jnz     short loc_18001B92B
0x18001b924  mov     eax, 0C0000139h
0x18001b929  jmp     short loc_18001B935
0x18001b92b  lea     rcx, [rsp+28h+arg_18]
0x18001b930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b935  add     rsp, 28h
0x18001b939  retn
```
