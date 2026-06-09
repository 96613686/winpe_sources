# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000b978`
- end: `0x18000b9c9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009d68`
- `0x18000c910`

## callees

- `0x18000b978`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b99a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b99a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9b2`

## string_xrefs

- `0x18000b991`: `kernelbase.dll`

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
0x18000b978  mov     [rsp+arg_0], rbx
0x18000b97d  push    rdi
0x18000b97e  sub     rsp, 20h
0x18000b982  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b989  mov     rdi, rcx
0x18000b98c  test    rax, rax
0x18000b98f  jnz     short loc_18000B9AC
0x18000b991  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b998  xor     ebx, ebx
0x18000b99a  call    cs:__imp_GetModuleHandleW
0x18000b9a0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b9a7  test    rax, rax
0x18000b9aa  jz      short loc_18000B9BB
0x18000b9ac  mov     rdx, rdi; lpProcName
0x18000b9af  mov     rcx, rax; hModule
0x18000b9b2  call    cs:__imp_GetProcAddress
0x18000b9b8  mov     rbx, rax
0x18000b9bb  mov     rax, rbx
0x18000b9be  mov     rbx, [rsp+28h+arg_0]
0x18000b9c3  add     rsp, 20h
0x18000b9c7  pop     rdi
0x18000b9c8  retn
```
