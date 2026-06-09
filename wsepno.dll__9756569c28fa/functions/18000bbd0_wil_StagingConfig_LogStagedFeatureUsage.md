# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000bbd0`
- end: `0x18000bc48`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000bbd0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bc1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bc1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bbff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bbff`

## string_xrefs

- `0x18000bbf8`: `kernelbase.dll`

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
0x18000bbd0  push    rbx
0x18000bbd2  push    rbp
0x18000bbd3  push    rsi
0x18000bbd4  push    rdi
0x18000bbd5  sub     rsp, 28h
0x18000bbd9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000bbe0  mov     dil, r8b
0x18000bbe3  mov     esi, edx
0x18000bbe5  mov     ebp, ecx
0x18000bbe7  test    rbx, rbx
0x18000bbea  jnz     short loc_18000BC30
0x18000bbec  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000bbf3  test    rax, rax
0x18000bbf6  jnz     short loc_18000BC11
0x18000bbf8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000bbff  call    cs:__imp_GetModuleHandleW
0x18000bc05  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000bc0c  test    rax, rax
0x18000bc0f  jz      short loc_18000BC24
0x18000bc11  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000bc18  mov     rcx, rax; hModule
0x18000bc1b  call    cs:__imp_GetProcAddress
0x18000bc21  mov     rbx, rax
0x18000bc24  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000bc2b  test    rbx, rbx
0x18000bc2e  jz      short loc_18000BC3F
0x18000bc30  mov     r8b, dil
0x18000bc33  mov     edx, esi
0x18000bc35  mov     ecx, ebp
0x18000bc37  mov     rax, rbx
0x18000bc3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc3f  add     rsp, 28h
0x18000bc43  pop     rdi
0x18000bc44  pop     rsi
0x18000bc45  pop     rbp
0x18000bc46  pop     rbx
0x18000bc47  retn
```
