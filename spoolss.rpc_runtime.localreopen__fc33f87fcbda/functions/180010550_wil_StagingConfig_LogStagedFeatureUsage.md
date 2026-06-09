# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180010550`
- end: `0x1800105a7`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000c9dc`
- `0x180010550`
- `0x180017010`

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
0x180010550  mov     [rsp+arg_0], rbx
0x180010555  mov     [rsp+arg_8], rsi
0x18001055a  push    rdi
0x18001055b  sub     rsp, 20h
0x18001055f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180010566  mov     bl, r8b
0x180010569  mov     edi, edx
0x18001056b  mov     esi, ecx
0x18001056d  test    rax, rax
0x180010570  jnz     short loc_18001058A
0x180010572  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180010579  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18001057e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x180010585  test    rax, rax
0x180010588  jz      short loc_180010596
0x18001058a  mov     r8b, bl
0x18001058d  mov     edx, edi
0x18001058f  mov     ecx, esi
0x180010591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010596  mov     rbx, [rsp+28h+arg_0]
0x18001059b  mov     rsi, [rsp+28h+arg_8]
0x1800105a0  add     rsp, 20h
0x1800105a4  pop     rdi
0x1800105a5  retn
```
