# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180002b10`
- end: `0x180002b39`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003220`
- `0x180007d10`
- `0x1800315a0`

## callees

- `0x180002b10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002b27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002b27`

## string_xrefs

- `0x180002b20`: `ntdll.dll`

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
0x180002b10  sub     rsp, 28h
0x180002b14  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002b1b  test    rax, rax
0x180002b1e  jnz     short loc_180002B34
0x180002b20  lea     rcx, ModuleName; "ntdll.dll"
0x180002b27  call    cs:__imp_GetModuleHandleW
0x180002b2d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002b34  add     rsp, 28h
0x180002b38  retn
```
