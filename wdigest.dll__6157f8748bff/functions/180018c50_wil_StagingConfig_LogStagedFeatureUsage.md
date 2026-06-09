# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180018c50`
- end: `0x180018ca6`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180016ff4`
- `0x180018c50`
- `0x180038010`

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
0x180018c50  mov     [rsp+arg_0], rbx
0x180018c55  mov     [rsp+arg_8], rsi
0x180018c5a  push    rdi
0x180018c5b  sub     rsp, 20h
0x180018c5f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180018c66  mov     bl, r8b
0x180018c69  mov     edi, edx
0x180018c6b  mov     esi, ecx
0x180018c6d  test    rax, rax
0x180018c70  jnz     short loc_180018C8A
0x180018c72  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180018c79  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x180018c7e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x180018c85  test    rax, rax
0x180018c88  jz      short loc_180018C96
0x180018c8a  mov     r8b, bl
0x180018c8d  mov     edx, edi
0x180018c8f  mov     ecx, esi
0x180018c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c96  mov     rbx, [rsp+28h+arg_0]
0x180018c9b  mov     rsi, [rsp+28h+arg_8]
0x180018ca0  add     rsp, 20h
0x180018ca4  pop     rdi
0x180018ca5  retn
```
