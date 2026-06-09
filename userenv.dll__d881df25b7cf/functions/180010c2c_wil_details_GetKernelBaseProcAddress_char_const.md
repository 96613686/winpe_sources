# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180010c2c`
- end: `0x180010c8a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009538`
- `0x180019cf0`

## callees

- `0x180010c2c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010c4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010c4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010c6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010c6c`

## string_xrefs

- `0x180010c45`: `kernelbase.dll`

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
0x180010c2c  mov     [rsp+arg_0], rbx
0x180010c31  push    rdi
0x180010c32  sub     rsp, 20h
0x180010c36  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010c3d  mov     rdi, rcx
0x180010c40  test    rax, rax
0x180010c43  jnz     short loc_180010C66
0x180010c45  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180010c4c  xor     ebx, ebx
0x180010c4e  call    cs:__imp_GetModuleHandleW
0x180010c55  nop     dword ptr [rax+rax+00h]
0x180010c5a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010c61  test    rax, rax
0x180010c64  jz      short loc_180010C7B
0x180010c66  mov     rdx, rdi; lpProcName
0x180010c69  mov     rcx, rax; hModule
0x180010c6c  call    cs:__imp_GetProcAddress
0x180010c73  nop     dword ptr [rax+rax+00h]
0x180010c78  mov     rbx, rax
0x180010c7b  mov     rax, rbx
0x180010c7e  mov     rbx, [rsp+28h+arg_0]
0x180010c83  add     rsp, 20h
0x180010c87  pop     rdi
0x180010c88  retn
```
