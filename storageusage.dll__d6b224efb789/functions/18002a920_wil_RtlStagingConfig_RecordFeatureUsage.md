# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18002a920`
- end: `0x18002a997`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002a160`

## callees

- `0x1800050f0`
- `0x180016cc0`
- `0x18002a920`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_RecordFeatureUsage(int a1, unsigned __int16 a2, int a3)
{
  FARPROC NtDllProcedureAddress; // rax
  int v5; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+24h] [rbp-14h]

  v5 = a1;
  v6 = a2;
  if ( a3 )
    HIWORD(v6) |= 1u;
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
0x18002a920  sub     rsp, 38h
0x18002a924  mov     rax, cs:__security_cookie
0x18002a92b  xor     rax, rsp
0x18002a92e  mov     [rsp+38h+var_10], rax
0x18002a933  mov     [rsp+38h+var_18], 0
0x18002a93c  mov     dword ptr [rsp+38h+var_18], ecx
0x18002a940  mov     word ptr [rsp+38h+var_18+4], dx
0x18002a945  test    r8d, r8d
0x18002a948  jz      short loc_18002A950
0x18002a94a  or      word ptr [rsp+38h+var_18+6], 1
0x18002a950  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18002a957  test    rax, rax
0x18002a95a  jnz     short loc_18002A97B
0x18002a95c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18002a963  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002a968  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18002a96f  test    rax, rax
0x18002a972  jnz     short loc_18002A97B
0x18002a974  mov     eax, 0C0000139h
0x18002a979  jmp     short loc_18002A985
0x18002a97b  lea     rcx, [rsp+38h+var_18]
0x18002a980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a985  mov     rcx, [rsp+38h+var_10]
0x18002a98a  xor     rcx, rsp; StackCookie
0x18002a98d  call    __security_check_cookie
0x18002a992  add     rsp, 38h
0x18002a996  retn
```
