# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180040d90`
- end: `0x180040de1`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003eb00`

## callees

- `0x180040d90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040db2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040db2`

## string_xrefs

- `0x180040da9`: `kernelbase.dll`

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
0x180040d90  mov     [rsp+arg_0], rbx
0x180040d95  push    rdi
0x180040d96  sub     rsp, 20h
0x180040d9a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180040da1  mov     rdi, rcx
0x180040da4  test    rax, rax
0x180040da7  jnz     short loc_180040DC4
0x180040da9  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180040db0  xor     ebx, ebx
0x180040db2  call    cs:__imp_GetModuleHandleW
0x180040db8  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180040dbf  test    rax, rax
0x180040dc2  jz      short loc_180040DD3
0x180040dc4  mov     rdx, rdi; lpProcName
0x180040dc7  mov     rcx, rax; hModule
0x180040dca  call    cs:__imp_GetProcAddress
0x180040dd0  mov     rbx, rax
0x180040dd3  mov     rax, rbx
0x180040dd6  mov     rbx, [rsp+28h+arg_0]
0x180040ddb  add     rsp, 20h
0x180040ddf  pop     rdi
0x180040de0  retn
```
