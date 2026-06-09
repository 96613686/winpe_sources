# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000e360`
- end: `0x18000e3d8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e360`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e38f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e38f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3ab`

## string_xrefs

- `0x18000e388`: `kernelbase.dll`

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
0x18000e360  push    rbx
0x18000e362  push    rbp
0x18000e363  push    rsi
0x18000e364  push    rdi
0x18000e365  sub     rsp, 28h
0x18000e369  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000e370  mov     dil, r8b
0x18000e373  mov     esi, edx
0x18000e375  mov     ebp, ecx
0x18000e377  test    rbx, rbx
0x18000e37a  jnz     short loc_18000E3C0
0x18000e37c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e383  test    rax, rax
0x18000e386  jnz     short loc_18000E3A1
0x18000e388  lea     rcx, LibFileName; "kernelbase.dll"
0x18000e38f  call    cs:__imp_GetModuleHandleW
0x18000e395  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e39c  test    rax, rax
0x18000e39f  jz      short loc_18000E3B4
0x18000e3a1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000e3a8  mov     rcx, rax; hModule
0x18000e3ab  call    cs:__imp_GetProcAddress
0x18000e3b1  mov     rbx, rax
0x18000e3b4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000e3bb  test    rbx, rbx
0x18000e3be  jz      short loc_18000E3CF
0x18000e3c0  mov     r8b, dil
0x18000e3c3  mov     edx, esi
0x18000e3c5  mov     ecx, ebp
0x18000e3c7  mov     rax, rbx
0x18000e3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3cf  add     rsp, 28h
0x18000e3d3  pop     rdi
0x18000e3d4  pop     rsi
0x18000e3d5  pop     rbp
0x18000e3d6  pop     rbx
0x18000e3d7  retn
```
