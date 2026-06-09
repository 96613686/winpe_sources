# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180027270`
- end: `0x180027299`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180024e90`
- `0x1800272a0`

## callees

- `0x180027270`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180027287`
- `KERNEL32!GetModuleHandleW` at `0x180027287`

## string_xrefs

- `0x180027280`: `ntdll.dll`

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
0x180027270  sub     rsp, 28h
0x180027274  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002727b  test    rax, rax
0x18002727e  jnz     short loc_180027294
0x180027280  lea     rcx, ModuleName; "ntdll.dll"
0x180027287  call    cs:__imp_GetModuleHandleW
0x18002728d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027294  add     rsp, 28h
0x180027298  retn
```
