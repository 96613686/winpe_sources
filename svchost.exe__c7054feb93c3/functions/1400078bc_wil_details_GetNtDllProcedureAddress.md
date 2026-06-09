# wil_details_GetNtDllProcedureAddress

- ea: `0x1400078bc`
- end: `0x1400078f7`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006fbc`
- `0x1400075a0`

## callees

- `0x1400078bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400078f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400078d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400078d8`

## string_xrefs

- `0x1400078d1`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const CHAR *a1)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, a1);
}

```

## disassembly

```asm
0x1400078bc  push    rbx
0x1400078be  sub     rsp, 20h
0x1400078c2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1400078c9  mov     rbx, rcx
0x1400078cc  test    rax, rax
0x1400078cf  jnz     short loc_1400078E5
0x1400078d1  lea     rcx, ModuleName; "ntdll.dll"
0x1400078d8  call    cs:__imp_GetModuleHandleW
0x1400078de  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1400078e5  mov     rdx, rbx
0x1400078e8  mov     rcx, rax
0x1400078eb  add     rsp, 20h
0x1400078ef  pop     rbx
0x1400078f0  jmp     cs:__imp_GetProcAddress
```
