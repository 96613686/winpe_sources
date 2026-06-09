# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000b92c`
- end: `0x18000b97d`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ac28`

## callees

- `0x18000b92c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b966`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b966`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b94e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b94e`

## string_xrefs

- `0x18000b945`: `kernelbase.dll`

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
0x18000b92c  mov     [rsp+arg_0], rbx
0x18000b931  push    rdi
0x18000b932  sub     rsp, 20h
0x18000b936  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b93d  mov     rdi, rcx
0x18000b940  test    rax, rax
0x18000b943  jnz     short loc_18000B960
0x18000b945  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b94c  xor     ebx, ebx
0x18000b94e  call    cs:__imp_GetModuleHandleW
0x18000b954  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b95b  test    rax, rax
0x18000b95e  jz      short loc_18000B96F
0x18000b960  mov     rdx, rdi; lpProcName
0x18000b963  mov     rcx, rax; hModule
0x18000b966  call    cs:__imp_GetProcAddress
0x18000b96c  mov     rbx, rax
0x18000b96f  mov     rax, rbx
0x18000b972  mov     rbx, [rsp+28h+arg_0]
0x18000b977  add     rsp, 20h
0x18000b97b  pop     rdi
0x18000b97c  retn
```
