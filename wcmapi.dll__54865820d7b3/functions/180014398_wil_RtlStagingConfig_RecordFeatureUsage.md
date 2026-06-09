# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180014398`
- end: `0x180014410`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800108f0`

## callees

- `0x180008a90`
- `0x18000aac8`
- `0x180014398`
- `0x18001e010`

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
0x180014398  sub     rsp, 38h
0x18001439c  mov     rax, cs:__security_cookie
0x1800143a3  xor     rax, rsp
0x1800143a6  mov     [rsp+38h+var_10], rax
0x1800143ab  mov     [rsp+38h+var_18], 0
0x1800143b4  mov     dword ptr [rsp+38h+var_18], ecx
0x1800143b8  mov     word ptr [rsp+38h+var_18+4], dx
0x1800143bd  test    r8d, r8d
0x1800143c0  jz      short loc_1800143C8
0x1800143c2  or      word ptr [rsp+38h+var_18+6], 1
0x1800143c8  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800143cf  test    rax, rax
0x1800143d2  jnz     short loc_1800143F3
0x1800143d4  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800143db  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800143e0  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800143e7  test    rax, rax
0x1800143ea  jnz     short loc_1800143F3
0x1800143ec  mov     eax, 0C0000139h
0x1800143f1  jmp     short loc_1800143FD
0x1800143f3  lea     rcx, [rsp+38h+var_18]
0x1800143f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143fd  mov     rcx, [rsp+38h+var_10]
0x180014402  xor     rcx, rsp; StackCookie
0x180014405  call    __security_check_cookie
0x18001440a  add     rsp, 38h
0x18001440e  retn
```
