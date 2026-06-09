# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000aa2c`
- end: `0x18000aa8a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a7b0`
- `0x180014420`

## callees

- `0x18000aa2c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa6c`

## string_xrefs

- `0x18000aa45`: `kernelbase.dll`

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
0x18000aa2c  mov     [rsp+arg_0], rbx
0x18000aa31  push    rdi
0x18000aa32  sub     rsp, 20h
0x18000aa36  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000aa3d  mov     rdi, rcx
0x18000aa40  test    rax, rax
0x18000aa43  jnz     short loc_18000AA66
0x18000aa45  lea     rcx, ModuleName; "kernelbase.dll"
0x18000aa4c  xor     ebx, ebx
0x18000aa4e  call    cs:__imp_GetModuleHandleW
0x18000aa55  nop     dword ptr [rax+rax+00h]
0x18000aa5a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000aa61  test    rax, rax
0x18000aa64  jz      short loc_18000AA7B
0x18000aa66  mov     rdx, rdi; lpProcName
0x18000aa69  mov     rcx, rax; hModule
0x18000aa6c  call    cs:__imp_GetProcAddress
0x18000aa73  nop     dword ptr [rax+rax+00h]
0x18000aa78  mov     rbx, rax
0x18000aa7b  mov     rax, rbx
0x18000aa7e  mov     rbx, [rsp+28h+arg_0]
0x18000aa83  add     rsp, 20h
0x18000aa87  pop     rdi
0x18000aa88  retn
```
