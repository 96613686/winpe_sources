# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18001a250`
- end: `0x18001a2a6`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180019bb8`
- `0x18001a250`
- `0x18001b010`

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
0x18001a250  mov     [rsp+arg_0], rbx
0x18001a255  mov     [rsp+arg_8], rsi
0x18001a25a  push    rdi
0x18001a25b  sub     rsp, 20h
0x18001a25f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18001a266  mov     bl, r8b
0x18001a269  mov     edi, edx
0x18001a26b  mov     esi, ecx
0x18001a26d  test    rax, rax
0x18001a270  jnz     short loc_18001A28A
0x18001a272  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18001a279  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18001a27e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x18001a285  test    rax, rax
0x18001a288  jz      short loc_18001A296
0x18001a28a  mov     r8b, bl
0x18001a28d  mov     edx, edi
0x18001a28f  mov     ecx, esi
0x18001a291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a296  mov     rbx, [rsp+28h+arg_0]
0x18001a29b  mov     rsi, [rsp+28h+arg_8]
0x18001a2a0  add     rsp, 20h
0x18001a2a4  pop     rdi
0x18001a2a5  retn
```
