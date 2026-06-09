# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18001a1f0`
- end: `0x18001a24a`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a330`

## callees

- `0x18000ae00`
- `0x18001a1f0`
- `0x18001b010`

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
0x18001a1f0  mov     rax, rsp
0x18001a1f3  sub     rsp, 28h
0x18001a1f7  mov     qword ptr [rax+20h], 0
0x18001a1ff  mov     [rax+20h], ecx
0x18001a202  mov     [rax+24h], dx
0x18001a206  test    r8d, r8d
0x18001a209  jz      short loc_18001A210
0x18001a20b  or      word ptr [rax+26h], 1
0x18001a210  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001a217  test    rax, rax
0x18001a21a  jnz     short loc_18001A23B
0x18001a21c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001a223  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001a228  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001a22f  test    rax, rax
0x18001a232  jnz     short loc_18001A23B
0x18001a234  mov     eax, 0C0000139h
0x18001a239  jmp     short loc_18001A245
0x18001a23b  lea     rcx, [rsp+28h+arg_18]
0x18001a240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a245  add     rsp, 28h
0x18001a249  retn
```
