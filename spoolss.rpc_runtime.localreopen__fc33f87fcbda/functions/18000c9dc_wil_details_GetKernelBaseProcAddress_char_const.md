# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000c9dc`
- end: `0x18000ca3a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c260`
- `0x180010550`

## callees

- `0x18000c9dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ca1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ca1c`

## string_xrefs

- `0x18000c9f5`: `kernelbase.dll`

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
0x18000c9dc  mov     [rsp+arg_0], rbx
0x18000c9e1  push    rdi
0x18000c9e2  sub     rsp, 20h
0x18000c9e6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000c9ed  mov     rdi, rcx
0x18000c9f0  test    rax, rax
0x18000c9f3  jnz     short loc_18000CA16
0x18000c9f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c9fc  xor     ebx, ebx
0x18000c9fe  call    cs:__imp_GetModuleHandleW
0x18000ca05  nop     dword ptr [rax+rax+00h]
0x18000ca0a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ca11  test    rax, rax
0x18000ca14  jz      short loc_18000CA2B
0x18000ca16  mov     rdx, rdi; lpProcName
0x18000ca19  mov     rcx, rax; hModule
0x18000ca1c  call    cs:__imp_GetProcAddress
0x18000ca23  nop     dword ptr [rax+rax+00h]
0x18000ca28  mov     rbx, rax
0x18000ca2b  mov     rax, rbx
0x18000ca2e  mov     rbx, [rsp+28h+arg_0]
0x18000ca33  add     rsp, 20h
0x18000ca37  pop     rdi
0x18000ca38  retn
```
