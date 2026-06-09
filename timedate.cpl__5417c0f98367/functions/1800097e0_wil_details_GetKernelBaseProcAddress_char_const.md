# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800097e0`
- end: `0x180009831`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800090a8`

## callees

- `0x1800097e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000981a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000981a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009802`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009802`

## string_xrefs

- `0x1800097f9`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(LPCSTR lpProcName)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, lpProcName);
  v3 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, lpProcName);
  return (FARPROC)v3;
}

```

## disassembly

```asm
0x1800097e0  mov     [rsp+arg_0], rbx
0x1800097e5  push    rdi
0x1800097e6  sub     rsp, 20h
0x1800097ea  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800097f1  mov     rdi, rcx
0x1800097f4  test    rax, rax
0x1800097f7  jnz     short loc_180009814
0x1800097f9  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009800  xor     ebx, ebx
0x180009802  call    cs:__imp_GetModuleHandleW
0x180009808  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000980f  test    rax, rax
0x180009812  jz      short loc_180009823
0x180009814  mov     rdx, rdi; lpProcName
0x180009817  mov     rcx, rax; hModule
0x18000981a  call    cs:__imp_GetProcAddress
0x180009820  mov     rbx, rax
0x180009823  mov     rax, rbx
0x180009826  mov     rbx, [rsp+28h+arg_0]
0x18000982b  add     rsp, 20h
0x18000982f  pop     rdi
0x180009830  retn
```
