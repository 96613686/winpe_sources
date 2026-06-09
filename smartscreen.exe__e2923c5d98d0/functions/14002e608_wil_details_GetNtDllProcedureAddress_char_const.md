# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14002e608`
- end: `0x14002e643`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14002e280`
- `0x14002e2c0`

## callees

- `0x14002e608`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002e63c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002e624`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002e624`

## string_xrefs

- `0x14002e61d`: `ntdll.dll`

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
0x14002e608  push    rbx
0x14002e60a  sub     rsp, 20h
0x14002e60e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14002e615  mov     rbx, rcx
0x14002e618  test    rax, rax
0x14002e61b  jnz     short loc_14002E631
0x14002e61d  lea     rcx, ModuleName; "ntdll.dll"
0x14002e624  call    cs:__imp_GetModuleHandleW
0x14002e62a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14002e631  mov     rdx, rbx
0x14002e634  mov     rcx, rax
0x14002e637  add     rsp, 20h
0x14002e63b  pop     rbx
0x14002e63c  jmp     cs:__imp_GetProcAddress
```
