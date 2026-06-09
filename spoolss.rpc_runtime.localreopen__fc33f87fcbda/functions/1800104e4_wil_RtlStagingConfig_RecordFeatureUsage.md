# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1800104e4`
- end: `0x18001053f`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bee0`

## callees

- `0x18000ca40`
- `0x1800104e4`
- `0x180017010`

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
0x1800104e4  mov     rax, rsp
0x1800104e7  sub     rsp, 28h
0x1800104eb  mov     qword ptr [rax+20h], 0
0x1800104f3  mov     [rax+20h], ecx
0x1800104f6  mov     [rax+24h], dx
0x1800104fa  test    r8d, r8d
0x1800104fd  jz      short loc_180010504
0x1800104ff  or      word ptr [rax+26h], 1
0x180010504  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001050b  test    rax, rax
0x18001050e  jnz     short loc_18001052F
0x180010510  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180010517  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001051c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180010523  test    rax, rax
0x180010526  jnz     short loc_18001052F
0x180010528  mov     eax, 0C0000139h
0x18001052d  jmp     short loc_180010539
0x18001052f  lea     rcx, [rsp+28h+arg_18]
0x180010534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010539  add     rsp, 28h
0x18001053d  retn
```
