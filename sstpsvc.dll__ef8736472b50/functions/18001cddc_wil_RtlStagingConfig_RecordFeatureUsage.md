# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18001cddc`
- end: `0x18001ce37`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c3c0`

## callees

- `0x18001cb50`
- `0x18001cddc`
- `0x18001e010`

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
0x18001cddc  mov     rax, rsp
0x18001cddf  sub     rsp, 28h
0x18001cde3  mov     qword ptr [rax+20h], 0
0x18001cdeb  mov     [rax+20h], ecx
0x18001cdee  mov     [rax+24h], dx
0x18001cdf2  test    r8d, r8d
0x18001cdf5  jz      short loc_18001CDFC
0x18001cdf7  or      word ptr [rax+26h], 1
0x18001cdfc  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001ce03  test    rax, rax
0x18001ce06  jnz     short loc_18001CE27
0x18001ce08  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001ce0f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001ce14  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001ce1b  test    rax, rax
0x18001ce1e  jnz     short loc_18001CE27
0x18001ce20  mov     eax, 0C0000139h
0x18001ce25  jmp     short loc_18001CE31
0x18001ce27  lea     rcx, [rsp+28h+arg_18]
0x18001ce2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce31  add     rsp, 28h
0x18001ce35  retn
```
