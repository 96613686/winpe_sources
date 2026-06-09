# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000a3dc`
- end: `0x18000a42d`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009820`

## callees

- `0x18000a3dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a416`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a416`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a3fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a3fe`

## string_xrefs

- `0x18000a3f5`: `kernelbase.dll`

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
0x18000a3dc  mov     [rsp+arg_0], rbx
0x18000a3e1  push    rdi
0x18000a3e2  sub     rsp, 20h
0x18000a3e6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a3ed  mov     rdi, rcx
0x18000a3f0  test    rax, rax
0x18000a3f3  jnz     short loc_18000A410
0x18000a3f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a3fc  xor     ebx, ebx
0x18000a3fe  call    cs:__imp_GetModuleHandleW
0x18000a404  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a40b  test    rax, rax
0x18000a40e  jz      short loc_18000A41F
0x18000a410  mov     rdx, rdi; lpProcName
0x18000a413  mov     rcx, rax; hModule
0x18000a416  call    cs:__imp_GetProcAddress
0x18000a41c  mov     rbx, rax
0x18000a41f  mov     rax, rbx
0x18000a422  mov     rbx, [rsp+28h+arg_0]
0x18000a427  add     rsp, 20h
0x18000a42b  pop     rdi
0x18000a42c  retn
```
