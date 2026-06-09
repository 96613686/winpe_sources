# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18002e5c4`
- end: `0x18002e5f4`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002b270`
- `0x18002e5fc`

## callees

- `0x18002e5c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e5db`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e5db`

## string_xrefs

- `0x18002e5d4`: `ntdll.dll`

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
0x18002e5c4  sub     rsp, 28h
0x18002e5c8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002e5cf  test    rax, rax
0x18002e5d2  jnz     short loc_18002E5EE
0x18002e5d4  lea     rcx, ModuleName; "ntdll.dll"
0x18002e5db  call    cs:__imp_GetModuleHandleW
0x18002e5e2  nop     dword ptr [rax+rax+00h]
0x18002e5e7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002e5ee  add     rsp, 28h
0x18002e5f2  retn
```
