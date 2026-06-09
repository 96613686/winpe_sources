# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18002c5a8`
- end: `0x18002c5f9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002a550`
- `0x18002d220`

## callees

- `0x18002c5a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c5ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c5ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c5e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c5e2`

## string_xrefs

- `0x18002c5c1`: `kernelbase.dll`

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
0x18002c5a8  mov     [rsp+arg_0], rbx
0x18002c5ad  push    rdi
0x18002c5ae  sub     rsp, 20h
0x18002c5b2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002c5b9  mov     rdi, rcx
0x18002c5bc  test    rax, rax
0x18002c5bf  jnz     short loc_18002C5DC
0x18002c5c1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002c5c8  xor     ebx, ebx
0x18002c5ca  call    cs:__imp_GetModuleHandleW
0x18002c5d0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002c5d7  test    rax, rax
0x18002c5da  jz      short loc_18002C5EB
0x18002c5dc  mov     rdx, rdi; lpProcName
0x18002c5df  mov     rcx, rax; hModule
0x18002c5e2  call    cs:__imp_GetProcAddress
0x18002c5e8  mov     rbx, rax
0x18002c5eb  mov     rax, rbx
0x18002c5ee  mov     rbx, [rsp+28h+arg_0]
0x18002c5f3  add     rsp, 20h
0x18002c5f7  pop     rdi
0x18002c5f8  retn
```
