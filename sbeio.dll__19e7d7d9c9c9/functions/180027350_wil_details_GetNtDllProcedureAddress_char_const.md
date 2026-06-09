# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180027350`
- end: `0x18002738b`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180024470`

## callees

- `0x180027350`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180027384`
- `KERNEL32!GetModuleHandleW` at `0x18002736c`
- `KERNEL32!GetModuleHandleW` at `0x18002736c`

## string_xrefs

- `0x180027365`: `ntdll.dll`

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
0x180027350  push    rbx
0x180027352  sub     rsp, 20h
0x180027356  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002735d  mov     rbx, rcx
0x180027360  test    rax, rax
0x180027363  jnz     short loc_180027379
0x180027365  lea     rcx, aNtdllDll; "ntdll.dll"
0x18002736c  call    cs:__imp_GetModuleHandleW
0x180027372  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027379  mov     rdx, rbx
0x18002737c  mov     rcx, rax
0x18002737f  add     rsp, 20h
0x180027383  pop     rbx
0x180027384  jmp     cs:__imp_GetProcAddress
```
