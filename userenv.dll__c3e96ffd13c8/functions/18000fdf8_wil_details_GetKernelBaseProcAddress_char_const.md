# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000fdf8`
- end: `0x18000fe49`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008c98`
- `0x180018350`

## callees

- `0x18000fdf8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fe1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fe1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe32`

## string_xrefs

- `0x18000fe11`: `kernelbase.dll`

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
0x18000fdf8  mov     [rsp+arg_0], rbx
0x18000fdfd  push    rdi
0x18000fdfe  sub     rsp, 20h
0x18000fe02  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000fe09  mov     rdi, rcx
0x18000fe0c  test    rax, rax
0x18000fe0f  jnz     short loc_18000FE2C
0x18000fe11  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000fe18  xor     ebx, ebx
0x18000fe1a  call    cs:__imp_GetModuleHandleW
0x18000fe20  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000fe27  test    rax, rax
0x18000fe2a  jz      short loc_18000FE3B
0x18000fe2c  mov     rdx, rdi; lpProcName
0x18000fe2f  mov     rcx, rax; hModule
0x18000fe32  call    cs:__imp_GetProcAddress
0x18000fe38  mov     rbx, rax
0x18000fe3b  mov     rax, rbx
0x18000fe3e  mov     rbx, [rsp+28h+arg_0]
0x18000fe43  add     rsp, 20h
0x18000fe47  pop     rdi
0x18000fe48  retn
```
