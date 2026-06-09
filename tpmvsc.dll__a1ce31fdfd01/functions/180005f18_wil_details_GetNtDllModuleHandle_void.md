# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180005f18`
- end: `0x180005f41`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003bf0`
- `0x180005f48`

## callees

- `0x180005f18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f2f`

## string_xrefs

- `0x180005f28`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180005f18  sub     rsp, 28h
0x180005f1c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005f23  test    rax, rax
0x180005f26  jnz     short loc_180005F3C
0x180005f28  lea     rcx, ModuleName; "ntdll.dll"
0x180005f2f  call    cs:__imp_GetModuleHandleW
0x180005f35  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005f3c  add     rsp, 28h
0x180005f40  retn
```
