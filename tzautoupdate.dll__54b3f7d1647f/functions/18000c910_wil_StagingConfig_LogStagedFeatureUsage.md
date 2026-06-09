# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000c910`
- end: `0x18000c966`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000b978`
- `0x18000c910`
- `0x18001d010`

## pseudocode

```c
FARPROC __fastcall wil_StagingConfig_LogStagedFeatureUsage(unsigned int a1, unsigned int a2, __int64 a3)
{
  FARPROC result; // rax
  char v4; // bl

  result = (FARPROC)g_wil_details_pfnLogStagedFeatureUsage;
  v4 = a3;
  if ( g_wil_details_pfnLogStagedFeatureUsage
    || (result = wil_details_GetKernelBaseProcAddress("LogStagedFeatureUsage"),
        (g_wil_details_pfnLogStagedFeatureUsage = (__int64)result) != 0) )
  {
    LOBYTE(a3) = v4;
    return (FARPROC)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))result)(a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x18000c910  mov     [rsp+arg_0], rbx
0x18000c915  mov     [rsp+arg_8], rsi
0x18000c91a  push    rdi
0x18000c91b  sub     rsp, 20h
0x18000c91f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000c926  mov     bl, r8b
0x18000c929  mov     edi, edx
0x18000c92b  mov     esi, ecx
0x18000c92d  test    rax, rax
0x18000c930  jnz     short loc_18000C94A
0x18000c932  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000c939  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18000c93e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18000c945  test    rax, rax
0x18000c948  jz      short loc_18000C956
0x18000c94a  mov     r8b, bl
0x18000c94d  mov     edx, edi
0x18000c94f  mov     ecx, esi
0x18000c951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c956  mov     rbx, [rsp+28h+arg_0]
0x18000c95b  mov     rsi, [rsp+28h+arg_8]
0x18000c960  add     rsp, 20h
0x18000c964  pop     rdi
0x18000c965  retn
```
