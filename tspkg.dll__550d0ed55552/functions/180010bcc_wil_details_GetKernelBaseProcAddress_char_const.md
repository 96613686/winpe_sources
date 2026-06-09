# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180010bcc`
- end: `0x180010c1d`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010758`

## callees

- `0x180010bcc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010bee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010bee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010c06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010c06`

## string_xrefs

- `0x180010be5`: `kernelbase.dll`

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
0x180010bcc  mov     [rsp+arg_0], rbx
0x180010bd1  push    rdi
0x180010bd2  sub     rsp, 20h
0x180010bd6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010bdd  mov     rdi, rcx
0x180010be0  test    rax, rax
0x180010be3  jnz     short loc_180010C00
0x180010be5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180010bec  xor     ebx, ebx
0x180010bee  call    cs:__imp_GetModuleHandleW
0x180010bf4  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010bfb  test    rax, rax
0x180010bfe  jz      short loc_180010C0F
0x180010c00  mov     rdx, rdi; lpProcName
0x180010c03  mov     rcx, rax; hModule
0x180010c06  call    cs:__imp_GetProcAddress
0x180010c0c  mov     rbx, rax
0x180010c0f  mov     rax, rbx
0x180010c12  mov     rbx, [rsp+28h+arg_0]
0x180010c17  add     rsp, 20h
0x180010c1b  pop     rdi
0x180010c1c  retn
```
