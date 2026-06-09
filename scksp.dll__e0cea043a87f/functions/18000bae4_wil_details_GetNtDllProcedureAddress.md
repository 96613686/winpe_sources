# wil_details_GetNtDllProcedureAddress

- ea: `0x18000bae4`
- end: `0x18000bb1f`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b228`
- `0x18000b354`

## callees

- `0x18000bae4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb00`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bb00`

## string_xrefs

- `0x18000baf9`: `ntdll.dll`

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
0x18000bae4  push    rbx
0x18000bae6  sub     rsp, 20h
0x18000baea  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000baf1  mov     rbx, rcx
0x18000baf4  test    rax, rax
0x18000baf7  jnz     short loc_18000BB0D
0x18000baf9  lea     rcx, ModuleName; "ntdll.dll"
0x18000bb00  call    cs:__imp_GetModuleHandleW
0x18000bb06  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000bb0d  mov     rdx, rbx
0x18000bb10  mov     rcx, rax
0x18000bb13  add     rsp, 20h
0x18000bb17  pop     rbx
0x18000bb18  jmp     cs:__imp_GetProcAddress
```
