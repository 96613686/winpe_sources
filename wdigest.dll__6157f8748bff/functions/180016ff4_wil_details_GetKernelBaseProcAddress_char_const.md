# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180016ff4`
- end: `0x180017045`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015b50`
- `0x180018c50`

## callees

- `0x180016ff4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017016`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017016`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001702e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001702e`

## string_xrefs

- `0x18001700d`: `kernelbase.dll`

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
0x180016ff4  mov     [rsp+arg_0], rbx
0x180016ff9  push    rdi
0x180016ffa  sub     rsp, 20h
0x180016ffe  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180017005  mov     rdi, rcx
0x180017008  test    rax, rax
0x18001700b  jnz     short loc_180017028
0x18001700d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180017014  xor     ebx, ebx
0x180017016  call    cs:__imp_GetModuleHandleW
0x18001701c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180017023  test    rax, rax
0x180017026  jz      short loc_180017037
0x180017028  mov     rdx, rdi; lpProcName
0x18001702b  mov     rcx, rax; hModule
0x18001702e  call    cs:__imp_GetProcAddress
0x180017034  mov     rbx, rax
0x180017037  mov     rax, rbx
0x18001703a  mov     rbx, [rsp+28h+arg_0]
0x18001703f  add     rsp, 20h
0x180017043  pop     rdi
0x180017044  retn
```
