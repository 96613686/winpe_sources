# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000c8b0`
- end: `0x18000c90a`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180009a70`

## callees

- `0x18000ba00`
- `0x18000c8b0`
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
0x18000c8b0  mov     rax, rsp
0x18000c8b3  sub     rsp, 28h
0x18000c8b7  mov     qword ptr [rax+20h], 0
0x18000c8bf  mov     [rax+20h], ecx
0x18000c8c2  mov     [rax+24h], dx
0x18000c8c6  test    r8d, r8d
0x18000c8c9  jz      short loc_18000C8D0
0x18000c8cb  or      word ptr [rax+26h], 1
0x18000c8d0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c8d7  test    rax, rax
0x18000c8da  jnz     short loc_18000C8FB
0x18000c8dc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c8e3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000c8e8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c8ef  test    rax, rax
0x18000c8f2  jnz     short loc_18000C8FB
0x18000c8f4  mov     eax, 0C0000139h
0x18000c8f9  jmp     short loc_18000C905
0x18000c8fb  lea     rcx, [rsp+28h+arg_18]
0x18000c900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c905  add     rsp, 28h
0x18000c909  retn
```
