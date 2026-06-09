# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18002e560`
- end: `0x18002e5be`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c4f0`
- `0x18002f1f0`

## callees

- `0x18002e560`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e582`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e582`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e5a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e5a0`

## string_xrefs

- `0x18002e579`: `kernelbase.dll`

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
0x18002e560  mov     [rsp+arg_0], rbx
0x18002e565  push    rdi
0x18002e566  sub     rsp, 20h
0x18002e56a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002e571  mov     rdi, rcx
0x18002e574  test    rax, rax
0x18002e577  jnz     short loc_18002E59A
0x18002e579  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002e580  xor     ebx, ebx
0x18002e582  call    cs:__imp_GetModuleHandleW
0x18002e589  nop     dword ptr [rax+rax+00h]
0x18002e58e  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002e595  test    rax, rax
0x18002e598  jz      short loc_18002E5AF
0x18002e59a  mov     rdx, rdi; lpProcName
0x18002e59d  mov     rcx, rax; hModule
0x18002e5a0  call    cs:__imp_GetProcAddress
0x18002e5a7  nop     dword ptr [rax+rax+00h]
0x18002e5ac  mov     rbx, rax
0x18002e5af  mov     rax, rbx
0x18002e5b2  mov     rbx, [rsp+28h+arg_0]
0x18002e5b7  add     rsp, 20h
0x18002e5bb  pop     rdi
0x18002e5bc  retn
```
