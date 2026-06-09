# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18004ff5c`
- end: `0x18004ff8c`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004d420`
- `0x18004ff94`

## callees

- `0x18004ff5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004ff73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004ff73`

## string_xrefs

- `0x18004ff6c`: `ntdll.dll`

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
0x18004ff5c  sub     rsp, 28h
0x18004ff60  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18004ff67  test    rax, rax
0x18004ff6a  jnz     short loc_18004FF86
0x18004ff6c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18004ff73  call    cs:__imp_GetModuleHandleW
0x18004ff7a  nop     dword ptr [rax+rax+00h]
0x18004ff7f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18004ff86  add     rsp, 28h
0x18004ff8a  retn
```
