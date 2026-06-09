# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18003c810`
- end: `0x18003c861`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800398e0`

## callees

- `0x18003c810`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18003c832`
- `KERNEL32!GetModuleHandleW` at `0x18003c832`
- `KERNEL32!GetProcAddress` at `0x18003c84a`
- `KERNEL32!GetProcAddress` at `0x18003c84a`

## string_xrefs

- `0x18003c829`: `kernelbase.dll`

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
0x18003c810  mov     [rsp+arg_0], rbx
0x18003c815  push    rdi
0x18003c816  sub     rsp, 20h
0x18003c81a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003c821  mov     rdi, rcx
0x18003c824  test    rax, rax
0x18003c827  jnz     short loc_18003C844
0x18003c829  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003c830  xor     ebx, ebx
0x18003c832  call    cs:__imp_GetModuleHandleW
0x18003c838  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18003c83f  test    rax, rax
0x18003c842  jz      short loc_18003C853
0x18003c844  mov     rdx, rdi; lpProcName
0x18003c847  mov     rcx, rax; hModule
0x18003c84a  call    cs:__imp_GetProcAddress
0x18003c850  mov     rbx, rax
0x18003c853  mov     rax, rbx
0x18003c856  mov     rbx, [rsp+28h+arg_0]
0x18003c85b  add     rsp, 20h
0x18003c85f  pop     rdi
0x18003c860  retn
```
