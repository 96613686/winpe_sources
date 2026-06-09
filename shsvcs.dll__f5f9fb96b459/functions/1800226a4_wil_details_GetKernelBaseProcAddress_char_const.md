# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800226a4`
- end: `0x1800226f5`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180021ee8`
- `0x180022ac0`

## callees

- `0x1800226a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800226c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800226c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800226de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800226de`

## string_xrefs

- `0x1800226bd`: `kernelbase.dll`

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
0x1800226a4  mov     [rsp+arg_0], rbx
0x1800226a9  push    rdi
0x1800226aa  sub     rsp, 20h
0x1800226ae  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800226b5  mov     rdi, rcx
0x1800226b8  test    rax, rax
0x1800226bb  jnz     short loc_1800226D8
0x1800226bd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800226c4  xor     ebx, ebx
0x1800226c6  call    cs:__imp_GetModuleHandleW
0x1800226cc  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800226d3  test    rax, rax
0x1800226d6  jz      short loc_1800226E7
0x1800226d8  mov     rdx, rdi; lpProcName
0x1800226db  mov     rcx, rax; hModule
0x1800226de  call    cs:__imp_GetProcAddress
0x1800226e4  mov     rbx, rax
0x1800226e7  mov     rax, rbx
0x1800226ea  mov     rbx, [rsp+28h+arg_0]
0x1800226ef  add     rsp, 20h
0x1800226f3  pop     rdi
0x1800226f4  retn
```
