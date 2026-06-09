# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x1800121f0`
- end: `0x180012268`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1800121f0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001221f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001221f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001223b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001223b`

## string_xrefs

- `0x180012218`: `kernelbase.dll`

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
0x1800121f0  push    rbx
0x1800121f2  push    rbp
0x1800121f3  push    rsi
0x1800121f4  push    rdi
0x1800121f5  sub     rsp, 28h
0x1800121f9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180012200  mov     dil, r8b
0x180012203  mov     esi, edx
0x180012205  mov     ebp, ecx
0x180012207  test    rbx, rbx
0x18001220a  jnz     short loc_180012250
0x18001220c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012213  test    rax, rax
0x180012216  jnz     short loc_180012231
0x180012218  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001221f  call    cs:__imp_GetModuleHandleW
0x180012225  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001222c  test    rax, rax
0x18001222f  jz      short loc_180012244
0x180012231  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180012238  mov     rcx, rax; hModule
0x18001223b  call    cs:__imp_GetProcAddress
0x180012241  mov     rbx, rax
0x180012244  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001224b  test    rbx, rbx
0x18001224e  jz      short loc_18001225F
0x180012250  mov     r8b, dil
0x180012253  mov     edx, esi
0x180012255  mov     ecx, ebp
0x180012257  mov     rax, rbx
0x18001225a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001225f  add     rsp, 28h
0x180012263  pop     rdi
0x180012264  pop     rsi
0x180012265  pop     rbp
0x180012266  pop     rbx
0x180012267  retn
```
