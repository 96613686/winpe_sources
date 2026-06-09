# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18002f418`
- end: `0x18002f469`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002e828`
- `0x18002f850`

## callees

- `0x18002f418`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f43a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f43a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f452`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f452`

## string_xrefs

- `0x18002f431`: `kernelbase.dll`

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
0x18002f418  mov     [rsp+arg_0], rbx
0x18002f41d  push    rdi
0x18002f41e  sub     rsp, 20h
0x18002f422  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002f429  mov     rdi, rcx
0x18002f42c  test    rax, rax
0x18002f42f  jnz     short loc_18002F44C
0x18002f431  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002f438  xor     ebx, ebx
0x18002f43a  call    cs:__imp_GetModuleHandleW
0x18002f440  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002f447  test    rax, rax
0x18002f44a  jz      short loc_18002F45B
0x18002f44c  mov     rdx, rdi; lpProcName
0x18002f44f  mov     rcx, rax; hModule
0x18002f452  call    cs:__imp_GetProcAddress
0x18002f458  mov     rbx, rax
0x18002f45b  mov     rax, rbx
0x18002f45e  mov     rbx, [rsp+28h+arg_0]
0x18002f463  add     rsp, 20h
0x18002f467  pop     rdi
0x18002f468  retn
```
