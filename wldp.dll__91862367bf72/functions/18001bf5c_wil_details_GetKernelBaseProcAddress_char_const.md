# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001bf5c`
- end: `0x18001bfad`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001fc30`
- `0x180026d30`

## callees

- `0x18001bf5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bf7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bf7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bf96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bf96`

## string_xrefs

- `0x18001bf77`: `kernelbase.dll`

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
0x18001bf5c  mov     [rsp+arg_0], rbx
0x18001bf61  push    rdi
0x18001bf62  sub     rsp, 20h
0x18001bf66  mov     rdi, rcx
0x18001bf69  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001bf70  test    rax, rax
0x18001bf73  jnz     short loc_18001BF90
0x18001bf75  xor     ebx, ebx
0x18001bf77  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001bf7e  call    cs:__imp_GetModuleHandleW
0x18001bf84  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001bf8b  test    rax, rax
0x18001bf8e  jz      short loc_18001BF9F
0x18001bf90  mov     rdx, rdi; lpProcName
0x18001bf93  mov     rcx, rax; hModule
0x18001bf96  call    cs:__imp_GetProcAddress
0x18001bf9c  mov     rbx, rax
0x18001bf9f  mov     rax, rbx
0x18001bfa2  mov     rbx, [rsp+28h+arg_0]
0x18001bfa7  add     rsp, 20h
0x18001bfab  pop     rdi
0x18001bfac  retn
```
