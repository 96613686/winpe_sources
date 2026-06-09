# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000b354`
- end: `0x18000b3ae`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b800`
- `0x180011c90`

## callees

- `0x18000b354`
- `0x18000bae4`
- `0x18003d010`

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
0x18000b354  mov     rax, rsp
0x18000b357  sub     rsp, 28h
0x18000b35b  mov     qword ptr [rax+20h], 0
0x18000b363  mov     [rax+20h], ecx
0x18000b366  mov     [rax+24h], dx
0x18000b36a  test    r8d, r8d
0x18000b36d  jz      short loc_18000B374
0x18000b36f  or      word ptr [rax+26h], 1
0x18000b374  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b37b  test    rax, rax
0x18000b37e  jnz     short loc_18000B39F
0x18000b380  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b387  call    wil_details_GetNtDllProcedureAddress
0x18000b38c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b393  test    rax, rax
0x18000b396  jnz     short loc_18000B39F
0x18000b398  mov     eax, 0C0000139h
0x18000b39d  jmp     short loc_18000B3A9
0x18000b39f  lea     rcx, [rsp+28h+arg_18]
0x18000b3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3a9  add     rsp, 28h
0x18000b3ad  retn
```
