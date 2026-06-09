# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180049ef0`
- end: `0x180049f4e`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180049340`
- `0x18004a190`

## callees

- `0x180049ef0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180049f12`
- `KERNEL32!GetModuleHandleW` at `0x180049f12`
- `KERNEL32!GetProcAddress` at `0x180049f30`
- `KERNEL32!GetProcAddress` at `0x180049f30`

## string_xrefs

- `0x180049f09`: `kernelbase.dll`

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
0x180049ef0  mov     [rsp+arg_0], rbx
0x180049ef5  push    rdi
0x180049ef6  sub     rsp, 20h
0x180049efa  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180049f01  mov     rdi, rcx
0x180049f04  test    rax, rax
0x180049f07  jnz     short loc_180049F2A
0x180049f09  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180049f10  xor     ebx, ebx
0x180049f12  call    cs:__imp_GetModuleHandleW
0x180049f19  nop     dword ptr [rax+rax+00h]
0x180049f1e  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180049f25  test    rax, rax
0x180049f28  jz      short loc_180049F3F
0x180049f2a  mov     rdx, rdi; lpProcName
0x180049f2d  mov     rcx, rax; hModule
0x180049f30  call    cs:__imp_GetProcAddress
0x180049f37  nop     dword ptr [rax+rax+00h]
0x180049f3c  mov     rbx, rax
0x180049f3f  mov     rax, rbx
0x180049f42  mov     rbx, [rsp+28h+arg_0]
0x180049f47  add     rsp, 20h
0x180049f4b  pop     rdi
0x180049f4c  retn
```
