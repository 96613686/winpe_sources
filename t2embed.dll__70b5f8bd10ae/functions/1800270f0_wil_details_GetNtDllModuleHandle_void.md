# wil_details_GetNtDllModuleHandle(void)

- ea: `0x1800270f0`
- end: `0x180027119`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800241c0`
- `0x180027120`

## callees

- `0x1800270f0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180027107`
- `KERNEL32!GetModuleHandleW` at `0x180027107`

## string_xrefs

- `0x180027100`: `ntdll.dll`

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
0x1800270f0  sub     rsp, 28h
0x1800270f4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800270fb  test    rax, rax
0x1800270fe  jnz     short loc_180027114
0x180027100  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180027107  call    cs:__imp_GetModuleHandleW
0x18002710d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027114  add     rsp, 28h
0x180027118  retn
```
