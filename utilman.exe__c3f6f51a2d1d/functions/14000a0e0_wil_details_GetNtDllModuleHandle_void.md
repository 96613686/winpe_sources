# wil_details_GetNtDllModuleHandle(void)

- ea: `0x14000a0e0`
- end: `0x14000a110`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140005710`
- `0x14000a118`

## callees

- `0x14000a0e0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000a0f7`
- `KERNEL32!GetModuleHandleW` at `0x14000a0f7`

## string_xrefs

- `0x14000a0f0`: `ntdll.dll`

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
0x14000a0e0  sub     rsp, 28h
0x14000a0e4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a0eb  test    rax, rax
0x14000a0ee  jnz     short loc_14000A10A
0x14000a0f0  lea     rcx, ModuleName; "ntdll.dll"
0x14000a0f7  call    cs:__imp_GetModuleHandleW
0x14000a0fe  nop     dword ptr [rax+rax+00h]
0x14000a103  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a10a  add     rsp, 28h
0x14000a10e  retn
```
