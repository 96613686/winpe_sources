# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180039888`
- end: `0x1800398e6`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180037ac0`

## callees

- `0x180039888`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800398aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800398aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800398c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800398c8`

## string_xrefs

- `0x1800398a1`: `kernelbase.dll`

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
0x180039888  mov     [rsp+arg_0], rbx
0x18003988d  push    rdi
0x18003988e  sub     rsp, 20h
0x180039892  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180039899  mov     rdi, rcx
0x18003989c  test    rax, rax
0x18003989f  jnz     short loc_1800398C2
0x1800398a1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800398a8  xor     ebx, ebx
0x1800398aa  call    cs:__imp_GetModuleHandleW
0x1800398b1  nop     dword ptr [rax+rax+00h]
0x1800398b6  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800398bd  test    rax, rax
0x1800398c0  jz      short loc_1800398D7
0x1800398c2  mov     rdx, rdi; lpProcName
0x1800398c5  mov     rcx, rax; hModule
0x1800398c8  call    cs:__imp_GetProcAddress
0x1800398cf  nop     dword ptr [rax+rax+00h]
0x1800398d4  mov     rbx, rax
0x1800398d7  mov     rax, rbx
0x1800398da  mov     rbx, [rsp+28h+arg_0]
0x1800398df  add     rsp, 20h
0x1800398e3  pop     rdi
0x1800398e4  retn
```
