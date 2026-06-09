# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180011f34`
- end: `0x180011f5f`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `43`
- prototype: `HINSTANCE(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011ef0`
- `0x180017b74`
- `0x18001bb00`

## callees

- `0x180011f34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011f50`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011f50`

## string_xrefs

- `0x180011f49`: `ntdll.dll`

## pseudocode

```c
HINSTANCE wil_details_GetNtDllModuleHandle(void)
{
  HINSTANCE result; // rax

  result = (HINSTANCE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    result = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x180011f34  sub     rsp, 28h
0x180011f38  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011f3f  test    rax, rax
0x180011f42  jz      short loc_180011F49
0x180011f44  add     rsp, 28h
0x180011f48  retn
0x180011f49  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180011f50  call    cs:__imp_GetModuleHandleW
0x180011f56  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011f5d  jmp     short loc_180011F44
```
