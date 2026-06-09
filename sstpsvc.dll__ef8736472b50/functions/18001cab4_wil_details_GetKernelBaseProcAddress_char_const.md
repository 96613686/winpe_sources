# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001cab4`
- end: `0x18001cb12`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001a820`

## callees

- `0x18001cab4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cad6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cad6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001caf4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001caf4`

## string_xrefs

- `0x18001cacd`: `kernelbase.dll`

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
0x18001cab4  mov     [rsp+arg_0], rbx
0x18001cab9  push    rdi
0x18001caba  sub     rsp, 20h
0x18001cabe  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001cac5  mov     rdi, rcx
0x18001cac8  test    rax, rax
0x18001cacb  jnz     short loc_18001CAEE
0x18001cacd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001cad4  xor     ebx, ebx
0x18001cad6  call    cs:__imp_GetModuleHandleW
0x18001cadd  nop     dword ptr [rax+rax+00h]
0x18001cae2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001cae9  test    rax, rax
0x18001caec  jz      short loc_18001CB03
0x18001caee  mov     rdx, rdi; lpProcName
0x18001caf1  mov     rcx, rax; hModule
0x18001caf4  call    cs:__imp_GetProcAddress
0x18001cafb  nop     dword ptr [rax+rax+00h]
0x18001cb00  mov     rbx, rax
0x18001cb03  mov     rax, rbx
0x18001cb06  mov     rbx, [rsp+28h+arg_0]
0x18001cb0b  add     rsp, 20h
0x18001cb0f  pop     rdi
0x18001cb10  retn
```
