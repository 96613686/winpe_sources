# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000c9e0`
- end: `0x18000ca36`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: `FARPROC __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000c0a4`
- `0x18000c9e0`
- `0x18000e010`

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
0x18000c9e0  mov     [rsp+arg_0], rbx
0x18000c9e5  mov     [rsp+arg_8], rsi
0x18000c9ea  push    rdi
0x18000c9eb  sub     rsp, 20h
0x18000c9ef  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000c9f6  mov     bl, r8b
0x18000c9f9  mov     edi, edx
0x18000c9fb  mov     esi, ecx
0x18000c9fd  test    rax, rax
0x18000ca00  jnz     short loc_18000CA1A
0x18000ca02  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000ca09  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18000ca0e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18000ca15  test    rax, rax
0x18000ca18  jz      short loc_18000CA26
0x18000ca1a  mov     r8b, bl
0x18000ca1d  mov     edx, edi
0x18000ca1f  mov     ecx, esi
0x18000ca21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca26  mov     rbx, [rsp+28h+arg_0]
0x18000ca2b  mov     rsi, [rsp+28h+arg_8]
0x18000ca30  add     rsp, 20h
0x18000ca34  pop     rdi
0x18000ca35  retn
```
