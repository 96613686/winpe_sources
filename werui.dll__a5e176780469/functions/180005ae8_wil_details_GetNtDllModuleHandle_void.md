# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180005ae8`
- end: `0x180005b11`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004c60`
- `0x180005b18`

## callees

- `0x180005ae8`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180005aff`
- `KERNEL32!GetModuleHandleW` at `0x180005aff`

## string_xrefs

- `0x180005af8`: `ntdll.dll`

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
0x180005ae8  sub     rsp, 28h
0x180005aec  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005af3  test    rax, rax
0x180005af6  jnz     short loc_180005B0C
0x180005af8  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x180005aff  call    cs:__imp_GetModuleHandleW
0x180005b05  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005b0c  add     rsp, 28h
0x180005b10  retn
```
