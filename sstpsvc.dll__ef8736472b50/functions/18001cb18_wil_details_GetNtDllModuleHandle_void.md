# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18001cb18`
- end: `0x18001cb48`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800193c0`
- `0x18001cb50`

## callees

- `0x18001cb18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cb2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cb2f`

## string_xrefs

- `0x18001cb28`: `ntdll.dll`

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
0x18001cb18  sub     rsp, 28h
0x18001cb1c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cb23  test    rax, rax
0x18001cb26  jnz     short loc_18001CB42
0x18001cb28  lea     rcx, ModuleName; "ntdll.dll"
0x18001cb2f  call    cs:__imp_GetModuleHandleW
0x18001cb36  nop     dword ptr [rax+rax+00h]
0x18001cb3b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cb42  add     rsp, 28h
0x18001cb46  retn
```
