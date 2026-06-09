# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000c97c`
- end: `0x18000c9d6`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: `__int64 __fastcall(int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b8c0`

## callees

- `0x18000c12c`
- `0x18000c97c`
- `0x18000e010`

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
0x18000c97c  mov     rax, rsp
0x18000c97f  sub     rsp, 28h
0x18000c983  mov     qword ptr [rax+20h], 0
0x18000c98b  mov     [rax+20h], ecx
0x18000c98e  mov     [rax+24h], dx
0x18000c992  test    r8d, r8d
0x18000c995  jz      short loc_18000C99C
0x18000c997  or      word ptr [rax+26h], 1
0x18000c99c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c9a3  test    rax, rax
0x18000c9a6  jnz     short loc_18000C9C7
0x18000c9a8  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c9af  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000c9b4  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c9bb  test    rax, rax
0x18000c9be  jnz     short loc_18000C9C7
0x18000c9c0  mov     eax, 0C0000139h
0x18000c9c5  jmp     short loc_18000C9D1
0x18000c9c7  lea     rcx, [rsp+28h+arg_18]
0x18000c9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9d1  add     rsp, 28h
0x18000c9d5  retn
```
