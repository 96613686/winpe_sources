# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x140016e3c`
- end: `0x140016e96`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140017398`

## callees

- `0x140016e3c`
- `0x140017684`
- `0x14001e010`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_RecordFeatureUsage(int a1, __int16 a2, int a3)
{
  __int64 (__fastcall *NtDllProcedureAddress)(int *); // rax
  int v5; // [rsp+48h] [rbp+20h] BYREF
  __int16 v6; // [rsp+4Ch] [rbp+24h]
  __int16 v7; // [rsp+4Eh] [rbp+26h]

  v7 = 0;
  v5 = a1;
  v6 = a2;
  if ( a3 )
    v7 |= 1u;
  NtDllProcedureAddress = (__int64 (__fastcall *)(int *))g_wil_details_pfnRtlNotifyFeatureUsage;
  if ( g_wil_details_pfnRtlNotifyFeatureUsage )
    return NtDllProcedureAddress(&v5);
  NtDllProcedureAddress = (__int64 (__fastcall *)(int *))wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage");
  g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return NtDllProcedureAddress(&v5);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x140016e3c  mov     rax, rsp
0x140016e3f  sub     rsp, 28h
0x140016e43  mov     qword ptr [rax+20h], 0
0x140016e4b  mov     [rax+20h], ecx
0x140016e4e  mov     [rax+24h], dx
0x140016e52  test    r8d, r8d
0x140016e55  jz      short loc_140016E5C
0x140016e57  or      word ptr [rax+26h], 1
0x140016e5c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140016e63  test    rax, rax
0x140016e66  jnz     short loc_140016E87
0x140016e68  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140016e6f  call    wil_details_GetNtDllProcedureAddress
0x140016e74  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140016e7b  test    rax, rax
0x140016e7e  jnz     short loc_140016E87
0x140016e80  mov     eax, 0C0000139h
0x140016e85  jmp     short loc_140016E91
0x140016e87  lea     rcx, [rsp+28h+arg_18]
0x140016e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016e91  add     rsp, 28h
0x140016e95  retn
```
