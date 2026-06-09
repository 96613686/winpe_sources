# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x14000cb60`
- end: `0x14000cbd8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x14000cb60`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000cbab`
- `KERNEL32!GetProcAddress` at `0x14000cbab`
- `KERNEL32!GetModuleHandleW` at `0x14000cb8f`
- `KERNEL32!GetModuleHandleW` at `0x14000cb8f`

## string_xrefs

- `0x14000cb88`: `kernelbase.dll`

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
0x14000cb60  push    rbx
0x14000cb62  push    rbp
0x14000cb63  push    rsi
0x14000cb64  push    rdi
0x14000cb65  sub     rsp, 28h
0x14000cb69  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x14000cb70  mov     dil, r8b
0x14000cb73  mov     esi, edx
0x14000cb75  mov     ebp, ecx
0x14000cb77  test    rbx, rbx
0x14000cb7a  jnz     short loc_14000CBC0
0x14000cb7c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000cb83  test    rax, rax
0x14000cb86  jnz     short loc_14000CBA1
0x14000cb88  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000cb8f  call    cs:__imp_GetModuleHandleW
0x14000cb95  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000cb9c  test    rax, rax
0x14000cb9f  jz      short loc_14000CBB4
0x14000cba1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x14000cba8  mov     rcx, rax; hModule
0x14000cbab  call    cs:__imp_GetProcAddress
0x14000cbb1  mov     rbx, rax
0x14000cbb4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x14000cbbb  test    rbx, rbx
0x14000cbbe  jz      short loc_14000CBCF
0x14000cbc0  mov     r8b, dil
0x14000cbc3  mov     edx, esi
0x14000cbc5  mov     ecx, ebp
0x14000cbc7  mov     rax, rbx
0x14000cbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbcf  add     rsp, 28h
0x14000cbd3  pop     rdi
0x14000cbd4  pop     rsi
0x14000cbd5  pop     rbp
0x14000cbd6  pop     rbx
0x14000cbd7  retn
```
