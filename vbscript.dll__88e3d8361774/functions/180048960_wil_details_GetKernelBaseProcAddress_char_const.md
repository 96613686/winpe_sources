# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180048960`
- end: `0x1800489b1`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180047e40`
- `0x180048bf0`

## callees

- `0x180048960`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180048982`
- `KERNEL32!GetModuleHandleW` at `0x180048982`
- `KERNEL32!GetProcAddress` at `0x18004899a`
- `KERNEL32!GetProcAddress` at `0x18004899a`

## string_xrefs

- `0x180048979`: `kernelbase.dll`

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
0x180048960  mov     [rsp+arg_0], rbx
0x180048965  push    rdi
0x180048966  sub     rsp, 20h
0x18004896a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180048971  mov     rdi, rcx
0x180048974  test    rax, rax
0x180048977  jnz     short loc_180048994
0x180048979  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180048980  xor     ebx, ebx
0x180048982  call    cs:__imp_GetModuleHandleW
0x180048988  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18004898f  test    rax, rax
0x180048992  jz      short loc_1800489A3
0x180048994  mov     rdx, rdi; lpProcName
0x180048997  mov     rcx, rax; hModule
0x18004899a  call    cs:__imp_GetProcAddress
0x1800489a0  mov     rbx, rax
0x1800489a3  mov     rax, rbx
0x1800489a6  mov     rbx, [rsp+28h+arg_0]
0x1800489ab  add     rsp, 20h
0x1800489af  pop     rdi
0x1800489b0  retn
```
