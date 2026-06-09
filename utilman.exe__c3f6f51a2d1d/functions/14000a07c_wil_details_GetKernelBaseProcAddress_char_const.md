# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000a07c`
- end: `0x14000a0da`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400094a0`
- `0x14000a5e0`

## callees

- `0x14000a07c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000a0bc`
- `KERNEL32!GetProcAddress` at `0x14000a0bc`
- `KERNEL32!GetModuleHandleW` at `0x14000a09e`
- `KERNEL32!GetModuleHandleW` at `0x14000a09e`

## string_xrefs

- `0x14000a095`: `kernelbase.dll`

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
0x14000a07c  mov     [rsp+arg_0], rbx
0x14000a081  push    rdi
0x14000a082  sub     rsp, 20h
0x14000a086  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000a08d  mov     rdi, rcx
0x14000a090  test    rax, rax
0x14000a093  jnz     short loc_14000A0B6
0x14000a095  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000a09c  xor     ebx, ebx
0x14000a09e  call    cs:__imp_GetModuleHandleW
0x14000a0a5  nop     dword ptr [rax+rax+00h]
0x14000a0aa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000a0b1  test    rax, rax
0x14000a0b4  jz      short loc_14000A0CB
0x14000a0b6  mov     rdx, rdi; lpProcName
0x14000a0b9  mov     rcx, rax; hModule
0x14000a0bc  call    cs:__imp_GetProcAddress
0x14000a0c3  nop     dword ptr [rax+rax+00h]
0x14000a0c8  mov     rbx, rax
0x14000a0cb  mov     rax, rbx
0x14000a0ce  mov     rbx, [rsp+28h+arg_0]
0x14000a0d3  add     rsp, 20h
0x14000a0d7  pop     rdi
0x14000a0d8  retn
```
