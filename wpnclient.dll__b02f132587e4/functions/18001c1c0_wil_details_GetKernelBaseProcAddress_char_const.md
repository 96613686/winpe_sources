# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001c1c0`
- end: `0x18001c211`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015400`
- `0x18002c730`

## callees

- `0x18001c1c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c1e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c1e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c1fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c1fa`

## string_xrefs

- `0x18001c1d9`: `kernelbase.dll`

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
0x18001c1c0  mov     [rsp+arg_0], rbx
0x18001c1c5  push    rdi
0x18001c1c6  sub     rsp, 20h
0x18001c1ca  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001c1d1  mov     rdi, rcx
0x18001c1d4  test    rax, rax
0x18001c1d7  jnz     short loc_18001C1F4
0x18001c1d9  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001c1e0  xor     ebx, ebx
0x18001c1e2  call    cs:__imp_GetModuleHandleW
0x18001c1e8  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001c1ef  test    rax, rax
0x18001c1f2  jz      short loc_18001C203
0x18001c1f4  mov     rdx, rdi; lpProcName
0x18001c1f7  mov     rcx, rax; hModule
0x18001c1fa  call    cs:__imp_GetProcAddress
0x18001c200  mov     rbx, rax
0x18001c203  mov     rax, rbx
0x18001c206  mov     rbx, [rsp+28h+arg_0]
0x18001c20b  add     rsp, 20h
0x18001c20f  pop     rdi
0x18001c210  retn
```
