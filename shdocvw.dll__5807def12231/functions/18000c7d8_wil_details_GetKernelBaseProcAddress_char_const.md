# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000c7d8`
- end: `0x18000c829`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b470`
- `0x180011bb0`

## callees

- `0x18000c7d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c812`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c812`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7fa`

## string_xrefs

- `0x18000c7f1`: `kernelbase.dll`

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
0x18000c7d8  mov     [rsp+arg_0], rbx
0x18000c7dd  push    rdi
0x18000c7de  sub     rsp, 20h
0x18000c7e2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000c7e9  mov     rdi, rcx
0x18000c7ec  test    rax, rax
0x18000c7ef  jnz     short loc_18000C80C
0x18000c7f1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c7f8  xor     ebx, ebx
0x18000c7fa  call    cs:__imp_GetModuleHandleW
0x18000c800  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000c807  test    rax, rax
0x18000c80a  jz      short loc_18000C81B
0x18000c80c  mov     rdx, rdi; lpProcName
0x18000c80f  mov     rcx, rax; hModule
0x18000c812  call    cs:__imp_GetProcAddress
0x18000c818  mov     rbx, rax
0x18000c81b  mov     rax, rbx
0x18000c81e  mov     rbx, [rsp+28h+arg_0]
0x18000c823  add     rsp, 20h
0x18000c827  pop     rdi
0x18000c828  retn
```
