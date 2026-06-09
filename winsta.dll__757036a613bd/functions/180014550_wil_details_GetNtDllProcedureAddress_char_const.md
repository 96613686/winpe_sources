# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180014550`
- end: `0x18001458b`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800122c0`

## callees

- `0x180014550`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014584`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001456c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001456c`

## string_xrefs

- `0x180014565`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
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
0x180014550  push    rbx
0x180014552  sub     rsp, 20h
0x180014556  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001455d  mov     rbx, rcx
0x180014560  test    rax, rax
0x180014563  jnz     short loc_180014579
0x180014565  lea     rcx, ModuleName; "ntdll.dll"
0x18001456c  call    cs:__imp_GetModuleHandleW
0x180014572  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014579  mov     rdx, rbx
0x18001457c  mov     rcx, rax
0x18001457f  add     rsp, 20h
0x180014583  pop     rbx
0x180014584  jmp     cs:__imp_GetProcAddress
```
