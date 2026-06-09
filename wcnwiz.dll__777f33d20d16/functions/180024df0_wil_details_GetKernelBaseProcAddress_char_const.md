# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180024df0`
- end: `0x180024e41`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180023a20`

## callees

- `0x180024df0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024e2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024e2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024e12`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024e12`

## string_xrefs

- `0x180024e09`: `kernelbase.dll`

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
0x180024df0  mov     [rsp+arg_0], rbx
0x180024df5  push    rdi
0x180024df6  sub     rsp, 20h
0x180024dfa  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180024e01  mov     rdi, rcx
0x180024e04  test    rax, rax
0x180024e07  jnz     short loc_180024E24
0x180024e09  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180024e10  xor     ebx, ebx
0x180024e12  call    cs:__imp_GetModuleHandleW
0x180024e18  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180024e1f  test    rax, rax
0x180024e22  jz      short loc_180024E33
0x180024e24  mov     rdx, rdi; lpProcName
0x180024e27  mov     rcx, rax; hModule
0x180024e2a  call    cs:__imp_GetProcAddress
0x180024e30  mov     rbx, rax
0x180024e33  mov     rax, rbx
0x180024e36  mov     rbx, [rsp+28h+arg_0]
0x180024e3b  add     rsp, 20h
0x180024e3f  pop     rdi
0x180024e40  retn
```
