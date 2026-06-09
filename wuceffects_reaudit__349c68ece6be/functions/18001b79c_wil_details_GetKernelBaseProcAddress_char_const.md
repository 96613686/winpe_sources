# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001b79c`
- end: `0x18001b7ef`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `83`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001b740`
- `0x180023de0`

## callees

- `0x18001b79c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b7be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b7be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b7e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b7e4`

## string_xrefs

- `0x18001b7b5`: `kernelbase.dll`

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
0x18001b79c  mov     [rsp+arg_0], rbx
0x18001b7a1  push    rdi
0x18001b7a2  sub     rsp, 20h
0x18001b7a6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001b7ad  mov     rdi, rcx
0x18001b7b0  test    rax, rax
0x18001b7b3  jnz     short loc_18001B7DE
0x18001b7b5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001b7bc  xor     ebx, ebx
0x18001b7be  call    cs:__imp_GetModuleHandleW
0x18001b7c4  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001b7cb  test    rax, rax
0x18001b7ce  jnz     short loc_18001B7DE
0x18001b7d0  mov     rax, rbx
0x18001b7d3  mov     rbx, [rsp+28h+arg_0]
0x18001b7d8  add     rsp, 20h
0x18001b7dc  pop     rdi
0x18001b7dd  retn
0x18001b7de  mov     rdx, rdi; lpProcName
0x18001b7e1  mov     rcx, rax; hModule
0x18001b7e4  call    cs:__imp_GetProcAddress
0x18001b7ea  mov     rbx, rax
0x18001b7ed  jmp     short loc_18001B7D0
```
