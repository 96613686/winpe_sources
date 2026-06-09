# wil_details_GetNtDllProcedureAddress

- ea: `0x1800093ac`
- end: `0x1800093e7`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008b50`
- `0x180009094`

## callees

- `0x1800093ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800093c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800093c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800093e0`

## string_xrefs

- `0x1800093c1`: `ntdll.dll`

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
0x1800093ac  push    rbx
0x1800093ae  sub     rsp, 20h
0x1800093b2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800093b9  mov     rbx, rcx
0x1800093bc  test    rax, rax
0x1800093bf  jnz     short loc_1800093D5
0x1800093c1  lea     rcx, ModuleName; "ntdll.dll"
0x1800093c8  call    cs:__imp_GetModuleHandleW
0x1800093ce  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800093d5  mov     rdx, rbx
0x1800093d8  mov     rcx, rax
0x1800093db  add     rsp, 20h
0x1800093df  pop     rbx
0x1800093e0  jmp     cs:__imp_GetProcAddress
```
