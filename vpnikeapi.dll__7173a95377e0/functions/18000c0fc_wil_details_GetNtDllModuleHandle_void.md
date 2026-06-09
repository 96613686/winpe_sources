# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18000c0fc`
- end: `0x18000c125`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800087d0`
- `0x18000c12c`

## callees

- `0x18000c0fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c113`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c113`

## string_xrefs

- `0x18000c10c`: `ntdll.dll`

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
0x18000c0fc  sub     rsp, 28h
0x18000c100  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c107  test    rax, rax
0x18000c10a  jnz     short loc_18000C120
0x18000c10c  lea     rcx, ModuleName; "ntdll.dll"
0x18000c113  call    cs:__imp_GetModuleHandleW
0x18000c119  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c120  add     rsp, 28h
0x18000c124  retn
```
