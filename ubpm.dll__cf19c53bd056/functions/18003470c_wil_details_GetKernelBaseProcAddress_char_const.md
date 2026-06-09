# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18003470c`
- end: `0x18003475d`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180033c60`
- `0x18003d130`

## callees

- `0x18003470c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034746`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034746`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003472e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003472e`

## string_xrefs

- `0x180034725`: `kernelbase.dll`

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
0x18003470c  mov     [rsp+arg_0], rbx
0x180034711  push    rdi
0x180034712  sub     rsp, 20h
0x180034716  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003471d  mov     rdi, rcx
0x180034720  test    rax, rax
0x180034723  jnz     short loc_180034740
0x180034725  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003472c  xor     ebx, ebx
0x18003472e  call    cs:__imp_GetModuleHandleW
0x180034734  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003473b  test    rax, rax
0x18003473e  jz      short loc_18003474F
0x180034740  mov     rdx, rdi; lpProcName
0x180034743  mov     rcx, rax; hModule
0x180034746  call    cs:__imp_GetProcAddress
0x18003474c  mov     rbx, rax
0x18003474f  mov     rax, rbx
0x180034752  mov     rbx, [rsp+28h+arg_0]
0x180034757  add     rsp, 20h
0x18003475b  pop     rdi
0x18003475c  retn
```
