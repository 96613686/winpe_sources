# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180012fa4`
- end: `0x180012fcf`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `43`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012f7c`
- `0x18001e320`

## callees

- `0x180012fa4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012fc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012fc0`

## string_xrefs

- `0x180012fb9`: `ntdll.dll`

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
0x180012fa4  sub     rsp, 28h
0x180012fa8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012faf  test    rax, rax
0x180012fb2  jz      short loc_180012FB9
0x180012fb4  add     rsp, 28h
0x180012fb8  retn
0x180012fb9  lea     rcx, ModuleName; "ntdll.dll"
0x180012fc0  call    cs:__imp_GetModuleHandleW
0x180012fc6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012fcd  jmp     short loc_180012FB4
```
