# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14004b658`
- end: `0x14004b6a9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140048390`
- `0x14004bb90`

## callees

- `0x14004b658`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b692`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b692`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14004b67a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14004b67a`

## string_xrefs

- `0x14004b671`: `kernelbase.dll`

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
0x14004b658  mov     [rsp+arg_0], rbx
0x14004b65d  push    rdi
0x14004b65e  sub     rsp, 20h
0x14004b662  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14004b669  mov     rdi, rcx
0x14004b66c  test    rax, rax
0x14004b66f  jnz     short loc_14004B68C
0x14004b671  lea     rcx, ModuleName; "kernelbase.dll"
0x14004b678  xor     ebx, ebx
0x14004b67a  call    cs:__imp_GetModuleHandleW
0x14004b680  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14004b687  test    rax, rax
0x14004b68a  jz      short loc_14004B69B
0x14004b68c  mov     rdx, rdi; lpProcName
0x14004b68f  mov     rcx, rax; hModule
0x14004b692  call    cs:__imp_GetProcAddress
0x14004b698  mov     rbx, rax
0x14004b69b  mov     rax, rbx
0x14004b69e  mov     rbx, [rsp+28h+arg_0]
0x14004b6a3  add     rsp, 20h
0x14004b6a7  pop     rdi
0x14004b6a8  retn
```
