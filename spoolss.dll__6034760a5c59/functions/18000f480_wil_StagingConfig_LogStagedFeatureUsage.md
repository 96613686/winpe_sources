# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000f480`
- end: `0x18000f4d6`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000c018`
- `0x18000f480`
- `0x180016010`

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
0x18000f480  mov     [rsp+arg_0], rbx
0x18000f485  mov     [rsp+arg_8], rsi
0x18000f48a  push    rdi
0x18000f48b  sub     rsp, 20h
0x18000f48f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000f496  mov     bl, r8b
0x18000f499  mov     edi, edx
0x18000f49b  mov     esi, ecx
0x18000f49d  test    rax, rax
0x18000f4a0  jnz     short loc_18000F4BA
0x18000f4a2  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000f4a9  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18000f4ae  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18000f4b5  test    rax, rax
0x18000f4b8  jz      short loc_18000F4C6
0x18000f4ba  mov     r8b, bl
0x18000f4bd  mov     edx, edi
0x18000f4bf  mov     ecx, esi
0x18000f4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4c6  mov     rbx, [rsp+28h+arg_0]
0x18000f4cb  mov     rsi, [rsp+28h+arg_8]
0x18000f4d0  add     rsp, 20h
0x18000f4d4  pop     rdi
0x18000f4d5  retn
```
