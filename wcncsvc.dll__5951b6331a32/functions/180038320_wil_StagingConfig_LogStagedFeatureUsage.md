# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180038320`
- end: `0x180038398`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180038320`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003836b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003836b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003834f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003834f`

## string_xrefs

- `0x180038348`: `kernelbase.dll`

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
0x180038320  push    rbx
0x180038322  push    rbp
0x180038323  push    rsi
0x180038324  push    rdi
0x180038325  sub     rsp, 28h
0x180038329  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180038330  mov     dil, r8b
0x180038333  mov     esi, edx
0x180038335  mov     ebp, ecx
0x180038337  test    rbx, rbx
0x18003833a  jnz     short loc_180038380
0x18003833c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180038343  test    rax, rax
0x180038346  jnz     short loc_180038361
0x180038348  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003834f  call    cs:__imp_GetModuleHandleW
0x180038355  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003835c  test    rax, rax
0x18003835f  jz      short loc_180038374
0x180038361  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180038368  mov     rcx, rax; hModule
0x18003836b  call    cs:__imp_GetProcAddress
0x180038371  mov     rbx, rax
0x180038374  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18003837b  test    rbx, rbx
0x18003837e  jz      short loc_18003838F
0x180038380  mov     r8b, dil
0x180038383  mov     edx, esi
0x180038385  mov     ecx, ebp
0x180038387  mov     rax, rbx
0x18003838a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003838f  add     rsp, 28h
0x180038393  pop     rdi
0x180038394  pop     rsi
0x180038395  pop     rbp
0x180038396  pop     rbx
0x180038397  retn
```
