# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18002d6e8`
- end: `0x18002d739`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002b890`
- `0x18002db00`

## callees

- `0x18002d6e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d722`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d722`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d70a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d70a`

## string_xrefs

- `0x18002d701`: `kernelbase.dll`

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
0x18002d6e8  mov     [rsp+arg_0], rbx
0x18002d6ed  push    rdi
0x18002d6ee  sub     rsp, 20h
0x18002d6f2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002d6f9  mov     rdi, rcx
0x18002d6fc  test    rax, rax
0x18002d6ff  jnz     short loc_18002D71C
0x18002d701  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002d708  xor     ebx, ebx
0x18002d70a  call    cs:__imp_GetModuleHandleW
0x18002d710  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002d717  test    rax, rax
0x18002d71a  jz      short loc_18002D72B
0x18002d71c  mov     rdx, rdi; lpProcName
0x18002d71f  mov     rcx, rax; hModule
0x18002d722  call    cs:__imp_GetProcAddress
0x18002d728  mov     rbx, rax
0x18002d72b  mov     rax, rbx
0x18002d72e  mov     rbx, [rsp+28h+arg_0]
0x18002d733  add     rsp, 20h
0x18002d737  pop     rdi
0x18002d738  retn
```
