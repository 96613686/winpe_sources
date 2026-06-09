# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180036b98`
- end: `0x180036bf6`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180036090`
- `0x18003fb60`

## callees

- `0x180036b98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036bd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036bd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036bba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036bba`

## string_xrefs

- `0x180036bb1`: `kernelbase.dll`

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
0x180036b98  mov     [rsp+arg_0], rbx
0x180036b9d  push    rdi
0x180036b9e  sub     rsp, 20h
0x180036ba2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180036ba9  mov     rdi, rcx
0x180036bac  test    rax, rax
0x180036baf  jnz     short loc_180036BD2
0x180036bb1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180036bb8  xor     ebx, ebx
0x180036bba  call    cs:__imp_GetModuleHandleW
0x180036bc1  nop     dword ptr [rax+rax+00h]
0x180036bc6  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180036bcd  test    rax, rax
0x180036bd0  jz      short loc_180036BE7
0x180036bd2  mov     rdx, rdi; lpProcName
0x180036bd5  mov     rcx, rax; hModule
0x180036bd8  call    cs:__imp_GetProcAddress
0x180036bdf  nop     dword ptr [rax+rax+00h]
0x180036be4  mov     rbx, rax
0x180036be7  mov     rax, rbx
0x180036bea  mov     rbx, [rsp+28h+arg_0]
0x180036bef  add     rsp, 20h
0x180036bf3  pop     rdi
0x180036bf4  retn
```
