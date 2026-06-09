# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001c8a8`
- end: `0x18001c8f9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001c050`
- `0x18002bda0`

## callees

- `0x18001c8a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c8ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c8ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c8e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c8e2`

## string_xrefs

- `0x18001c8c1`: `kernelbase.dll`

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
0x18001c8a8  mov     [rsp+arg_0], rbx
0x18001c8ad  push    rdi
0x18001c8ae  sub     rsp, 20h
0x18001c8b2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001c8b9  mov     rdi, rcx
0x18001c8bc  test    rax, rax
0x18001c8bf  jnz     short loc_18001C8DC
0x18001c8c1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001c8c8  xor     ebx, ebx
0x18001c8ca  call    cs:__imp_GetModuleHandleW
0x18001c8d0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001c8d7  test    rax, rax
0x18001c8da  jz      short loc_18001C8EB
0x18001c8dc  mov     rdx, rdi; lpProcName
0x18001c8df  mov     rcx, rax; hModule
0x18001c8e2  call    cs:__imp_GetProcAddress
0x18001c8e8  mov     rbx, rax
0x18001c8eb  mov     rax, rbx
0x18001c8ee  mov     rbx, [rsp+28h+arg_0]
0x18001c8f3  add     rsp, 20h
0x18001c8f7  pop     rdi
0x18001c8f8  retn
```
