# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180048f88`
- end: `0x180048fb8`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800428d0`
- `0x180048fc0`

## callees

- `0x180048f88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180048f9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180048f9f`

## string_xrefs

- `0x180048f98`: `ntdll.dll`

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
0x180048f88  sub     rsp, 28h
0x180048f8c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180048f93  test    rax, rax
0x180048f96  jnz     short loc_180048FB2
0x180048f98  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180048f9f  call    cs:__imp_GetModuleHandleW
0x180048fa6  nop     dword ptr [rax+rax+00h]
0x180048fab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180048fb2  add     rsp, 28h
0x180048fb6  retn
```
