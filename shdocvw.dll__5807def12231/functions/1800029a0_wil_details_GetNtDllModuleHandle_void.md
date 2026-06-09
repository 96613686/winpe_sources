# wil_details_GetNtDllModuleHandle(void)

- ea: `0x1800029a0`
- end: `0x1800029c9`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800027a0`
- `0x180004820`
- `0x180004b90`
- `0x18000a690`

## callees

- `0x1800029a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800029b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800029b7`

## string_xrefs

- `0x1800029b0`: `ntdll.dll`

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
0x1800029a0  sub     rsp, 28h
0x1800029a4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800029ab  test    rax, rax
0x1800029ae  jnz     short loc_1800029C4
0x1800029b0  lea     rcx, ModuleName; "ntdll.dll"
0x1800029b7  call    cs:__imp_GetModuleHandleW
0x1800029bd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800029c4  add     rsp, 28h
0x1800029c8  retn
```
