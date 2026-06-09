# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180019bb8`
- end: `0x180019c09`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800184e0`
- `0x18001a250`

## callees

- `0x180019bb8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019bf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019bf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019bda`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019bda`

## string_xrefs

- `0x180019bd3`: `kernelbase.dll`

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
0x180019bb8  mov     [rsp+arg_0], rbx
0x180019bbd  push    rdi
0x180019bbe  sub     rsp, 20h
0x180019bc2  mov     rdi, rcx
0x180019bc5  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180019bcc  test    rax, rax
0x180019bcf  jnz     short loc_180019BEC
0x180019bd1  xor     ebx, ebx
0x180019bd3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180019bda  call    cs:__imp_GetModuleHandleW
0x180019be0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180019be7  test    rax, rax
0x180019bea  jz      short loc_180019BFB
0x180019bec  mov     rdx, rdi; lpProcName
0x180019bef  mov     rcx, rax; hModule
0x180019bf2  call    cs:__imp_GetProcAddress
0x180019bf8  mov     rbx, rax
0x180019bfb  mov     rax, rbx
0x180019bfe  mov     rbx, [rsp+28h+arg_0]
0x180019c03  add     rsp, 20h
0x180019c07  pop     rdi
0x180019c08  retn
```
