# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14002f84c`
- end: `0x14002f892`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `70`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14002f490`
- `0x14002f4d0`

## callees

- `0x14002f84c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002f886`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002f868`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002f868`

## string_xrefs

- `0x14002f861`: `ntdll.dll`

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
0x14002f84c  push    rbx
0x14002f84e  sub     rsp, 20h
0x14002f852  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14002f859  mov     rbx, rcx
0x14002f85c  test    rax, rax
0x14002f85f  jnz     short loc_14002F87B
0x14002f861  lea     rcx, ModuleName; "ntdll.dll"
0x14002f868  call    cs:__imp_GetModuleHandleW
0x14002f86f  nop     dword ptr [rax+rax+00h]
0x14002f874  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14002f87b  mov     rdx, rbx
0x14002f87e  mov     rcx, rax
0x14002f881  add     rsp, 20h
0x14002f885  pop     rbx
0x14002f886  jmp     cs:__imp_GetProcAddress
```
