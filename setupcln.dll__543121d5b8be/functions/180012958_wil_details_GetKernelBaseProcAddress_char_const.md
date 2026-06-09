# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180012958`
- end: `0x1800129a9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000fc90`

## callees

- `0x180012958`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001297a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001297a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012992`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012992`

## string_xrefs

- `0x180012973`: `kernelbase.dll`

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
0x180012958  mov     [rsp+arg_0], rbx
0x18001295d  push    rdi
0x18001295e  sub     rsp, 20h
0x180012962  mov     rdi, rcx
0x180012965  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001296c  test    rax, rax
0x18001296f  jnz     short loc_18001298C
0x180012971  xor     ebx, ebx
0x180012973  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001297a  call    cs:__imp_GetModuleHandleW
0x180012980  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012987  test    rax, rax
0x18001298a  jz      short loc_18001299B
0x18001298c  mov     rdx, rdi; lpProcName
0x18001298f  mov     rcx, rax; hModule
0x180012992  call    cs:__imp_GetProcAddress
0x180012998  mov     rbx, rax
0x18001299b  mov     rax, rbx
0x18001299e  mov     rbx, [rsp+28h+arg_0]
0x1800129a3  add     rsp, 20h
0x1800129a7  pop     rdi
0x1800129a8  retn
```
