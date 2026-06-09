# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18003cc9c`
- end: `0x18003ccc7`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `43`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180041108`
- `0x1800470e0`

## callees

- `0x18003cc9c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18003ccb8`
- `KERNEL32!GetModuleHandleW` at `0x18003ccb8`

## string_xrefs

- `0x18003ccb1`: `ntdll.dll`

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
0x18003cc9c  sub     rsp, 28h
0x18003cca0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003cca7  test    rax, rax
0x18003ccaa  jz      short loc_18003CCB1
0x18003ccac  add     rsp, 28h
0x18003ccb0  retn
0x18003ccb1  lea     rcx, ModuleName; "ntdll.dll"
0x18003ccb8  call    cs:__imp_GetModuleHandleW
0x18003ccbe  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003ccc5  jmp     short loc_18003CCAC
```
