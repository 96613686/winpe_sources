# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000a9b0`
- end: `0x18000aa28`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a9b0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a9df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a9df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a9fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a9fb`

## string_xrefs

- `0x18000a9d8`: `kernelbase.dll`

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
0x18000a9b0  push    rbx
0x18000a9b2  push    rbp
0x18000a9b3  push    rsi
0x18000a9b4  push    rdi
0x18000a9b5  sub     rsp, 28h
0x18000a9b9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000a9c0  mov     dil, r8b
0x18000a9c3  mov     esi, edx
0x18000a9c5  mov     ebp, ecx
0x18000a9c7  test    rbx, rbx
0x18000a9ca  jnz     short loc_18000AA10
0x18000a9cc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a9d3  test    rax, rax
0x18000a9d6  jnz     short loc_18000A9F1
0x18000a9d8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a9df  call    cs:__imp_GetModuleHandleW
0x18000a9e5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a9ec  test    rax, rax
0x18000a9ef  jz      short loc_18000AA04
0x18000a9f1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000a9f8  mov     rcx, rax; hModule
0x18000a9fb  call    cs:__imp_GetProcAddress
0x18000aa01  mov     rbx, rax
0x18000aa04  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000aa0b  test    rbx, rbx
0x18000aa0e  jz      short loc_18000AA1F
0x18000aa10  mov     r8b, dil
0x18000aa13  mov     edx, esi
0x18000aa15  mov     ecx, ebp
0x18000aa17  mov     rax, rbx
0x18000aa1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa1f  add     rsp, 28h
0x18000aa23  pop     rdi
0x18000aa24  pop     rsi
0x18000aa25  pop     rbp
0x18000aa26  pop     rbx
0x18000aa27  retn
```
