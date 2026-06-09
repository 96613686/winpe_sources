# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18001d110`
- end: `0x18001d188`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18001d110`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d15b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d15b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d13f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d13f`

## string_xrefs

- `0x18001d138`: `kernelbase.dll`

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
0x18001d110  push    rbx
0x18001d112  push    rbp
0x18001d113  push    rsi
0x18001d114  push    rdi
0x18001d115  sub     rsp, 28h
0x18001d119  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18001d120  mov     dil, r8b
0x18001d123  mov     esi, edx
0x18001d125  mov     ebp, ecx
0x18001d127  test    rbx, rbx
0x18001d12a  jnz     short loc_18001D170
0x18001d12c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d133  test    rax, rax
0x18001d136  jnz     short loc_18001D151
0x18001d138  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001d13f  call    cs:__imp_GetModuleHandleW
0x18001d145  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d14c  test    rax, rax
0x18001d14f  jz      short loc_18001D164
0x18001d151  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18001d158  mov     rcx, rax; hModule
0x18001d15b  call    cs:__imp_GetProcAddress
0x18001d161  mov     rbx, rax
0x18001d164  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001d16b  test    rbx, rbx
0x18001d16e  jz      short loc_18001D17F
0x18001d170  mov     r8b, dil
0x18001d173  mov     edx, esi
0x18001d175  mov     ecx, ebp
0x18001d177  mov     rax, rbx
0x18001d17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d17f  add     rsp, 28h
0x18001d183  pop     rdi
0x18001d184  pop     rsi
0x18001d185  pop     rbp
0x18001d186  pop     rbx
0x18001d187  retn
```
