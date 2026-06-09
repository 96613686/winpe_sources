# wil_details_GetNtDllProcedureAddress

- ea: `0x18001f9c0`
- end: `0x18001f9fb`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001f960`

## callees

- `0x18001f9c0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001f9dc`
- `KERNEL32!GetModuleHandleW` at `0x18001f9dc`
- `KERNEL32!GetProcAddress` at `0x18001f9f4`

## string_xrefs

- `0x18001f9d5`: `ntdll.dll`

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
0x18001f9c0  push    rbx
0x18001f9c2  sub     rsp, 20h
0x18001f9c6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18001f9cd  mov     rbx, rcx
0x18001f9d0  test    rax, rax
0x18001f9d3  jnz     short loc_18001F9E9
0x18001f9d5  lea     rcx, ModuleName; "ntdll.dll"
0x18001f9dc  call    cs:__imp_GetModuleHandleW
0x18001f9e2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18001f9e9  mov     rdx, rbx
0x18001f9ec  mov     rcx, rax
0x18001f9ef  add     rsp, 20h
0x18001f9f3  pop     rbx
0x18001f9f4  jmp     cs:__imp_GetProcAddress
```
