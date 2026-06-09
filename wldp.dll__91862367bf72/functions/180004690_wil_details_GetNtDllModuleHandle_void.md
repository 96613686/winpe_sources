# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180004690`
- end: `0x1800046b9`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000363c`
- `0x1800036c0`
- `0x180003b50`
- `0x180004400`
- `0x180025310`

## callees

- `0x180004690`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046a7`

## string_xrefs

- `0x1800046a0`: `ntdll.dll`

## pseudocode

```c
HINSTANCE wil_details_GetNtDllModuleHandle(void)
{
  HINSTANCE result; // rax

  result = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    result = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = result;
  }
  return result;
}

```

## disassembly

```asm
0x180004690  sub     rsp, 28h
0x180004694  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000469b  test    rax, rax
0x18000469e  jnz     short loc_1800046B4
0x1800046a0  lea     rcx, ModuleName; "ntdll.dll"
0x1800046a7  call    cs:__imp_GetModuleHandleW
0x1800046ad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800046b4  add     rsp, 28h
0x1800046b8  retn
```
