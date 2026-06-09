# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000f4b0`
- end: `0x18000f54c`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000f4b0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000f4ea`
- `KERNEL32!GetModuleHandleW` at `0x18000f4ea`
- `KERNEL32!GetProcAddress` at `0x18000f50c`
- `KERNEL32!GetProcAddress` at `0x18000f50c`

## string_xrefs

- `0x18000f4e3`: `kernelbase.dll`

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
0x18000f4b0  mov     [rsp+arg_0], rbx
0x18000f4b5  mov     [rsp+arg_8], rbp
0x18000f4ba  mov     [rsp+arg_10], rsi
0x18000f4bf  push    rdi
0x18000f4c0  sub     rsp, 20h
0x18000f4c4  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000f4cb  mov     dil, r8b
0x18000f4ce  mov     esi, edx
0x18000f4d0  mov     ebp, ecx
0x18000f4d2  test    rbx, rbx
0x18000f4d5  jnz     short loc_18000F527
0x18000f4d7  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000f4de  test    rax, rax
0x18000f4e1  jnz     short loc_18000F502
0x18000f4e3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000f4ea  call    cs:__imp_GetModuleHandleW
0x18000f4f1  nop     dword ptr [rax+rax+00h]
0x18000f4f6  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000f4fd  test    rax, rax
0x18000f500  jz      short loc_18000F51B
0x18000f502  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000f509  mov     rcx, rax; hModule
0x18000f50c  call    cs:__imp_GetProcAddress
0x18000f513  nop     dword ptr [rax+rax+00h]
0x18000f518  mov     rbx, rax
0x18000f51b  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000f522  test    rbx, rbx
0x18000f525  jz      short loc_18000F536
0x18000f527  mov     r8b, dil
0x18000f52a  mov     edx, esi
0x18000f52c  mov     ecx, ebp
0x18000f52e  mov     rax, rbx
0x18000f531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f536  mov     rbx, [rsp+28h+arg_0]
0x18000f53b  mov     rbp, [rsp+28h+arg_8]
0x18000f540  mov     rsi, [rsp+28h+arg_10]
0x18000f545  add     rsp, 20h
0x18000f549  pop     rdi
0x18000f54a  retn
```
