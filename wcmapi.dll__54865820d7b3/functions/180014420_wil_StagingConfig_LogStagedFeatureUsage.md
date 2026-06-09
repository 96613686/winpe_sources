# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180014420`
- end: `0x180014477`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000aa2c`
- `0x180014420`
- `0x18001e010`

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
0x180014420  mov     [rsp+arg_0], rbx
0x180014425  mov     [rsp+arg_8], rsi
0x18001442a  push    rdi
0x18001442b  sub     rsp, 20h
0x18001442f  mov     rax, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180014436  mov     bl, r8b
0x180014439  mov     edi, edx
0x18001443b  mov     esi, ecx
0x18001443d  test    rax, rax
0x180014440  jnz     short loc_18001445A
0x180014442  lea     rcx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180014449  call    ?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z; wil_details_GetKernelBaseProcAddress(char const *)
0x18001444e  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rax
0x180014455  test    rax, rax
0x180014458  jz      short loc_180014466
0x18001445a  mov     r8b, bl
0x18001445d  mov     edx, edi
0x18001445f  mov     ecx, esi
0x180014461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014466  mov     rbx, [rsp+28h+arg_0]
0x18001446b  mov     rsi, [rsp+28h+arg_8]
0x180014470  add     rsp, 20h
0x180014474  pop     rdi
0x180014475  retn
```
