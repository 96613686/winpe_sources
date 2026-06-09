# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180009220`
- end: `0x180009298`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180009220`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000924f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000924f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000926b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000926b`

## string_xrefs

- `0x180009248`: `kernelbase.dll`

## pseudocode

```c
HMODULE __fastcall wil_StagingConfig_LogStagedFeatureUsage(unsigned int a1, unsigned int a2, __int64 a3)
{
  __int64 (__fastcall *v3)(_QWORD, _QWORD, _QWORD); // rbx
  char v4; // di
  HMODULE result; // rax

  v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))g_wil_details_pfnLogStagedFeatureUsage;
  v4 = a3;
  if ( g_wil_details_pfnLogStagedFeatureUsage )
    goto LABEL_6;
  result = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (result = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = result) != 0) )
  {
    result = (HMODULE)GetProcAddress(result, "LogStagedFeatureUsage");
    v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))result;
  }
  g_wil_details_pfnLogStagedFeatureUsage = (__int64)v3;
  if ( v3 )
  {
LABEL_6:
    LOBYTE(a3) = v4;
    return (HMODULE)v3(a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x180009220  push    rbx
0x180009222  push    rbp
0x180009223  push    rsi
0x180009224  push    rdi
0x180009225  sub     rsp, 28h
0x180009229  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180009230  mov     dil, r8b
0x180009233  mov     esi, edx
0x180009235  mov     ebp, ecx
0x180009237  test    rbx, rbx
0x18000923a  jnz     short loc_180009280
0x18000923c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009243  test    rax, rax
0x180009246  jnz     short loc_180009261
0x180009248  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000924f  call    cs:__imp_GetModuleHandleW
0x180009255  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000925c  test    rax, rax
0x18000925f  jz      short loc_180009274
0x180009261  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180009268  mov     rcx, rax; hModule
0x18000926b  call    cs:__imp_GetProcAddress
0x180009271  mov     rbx, rax
0x180009274  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000927b  test    rbx, rbx
0x18000927e  jz      short loc_18000928F
0x180009280  mov     r8b, dil
0x180009283  mov     edx, esi
0x180009285  mov     ecx, ebp
0x180009287  mov     rax, rbx
0x18000928a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000928f  add     rsp, 28h
0x180009293  pop     rdi
0x180009294  pop     rsi
0x180009295  pop     rbp
0x180009296  pop     rbx
0x180009297  retn
```
