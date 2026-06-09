# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18003df88`
- end: `0x18003dfba`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `50`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800427d4`
- `0x180048570`

## callees

- `0x18003df88`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18003dfa5`
- `KERNEL32!GetModuleHandleW` at `0x18003dfa5`

## string_xrefs

- `0x18003df9e`: `ntdll.dll`

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
0x18003df88  sub     rsp, 28h
0x18003df8c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003df93  test    rax, rax
0x18003df96  jz      short loc_18003DF9E
0x18003df98  add     rsp, 28h
0x18003df9c  retn
0x18003df9e  lea     rcx, ModuleName; "ntdll.dll"
0x18003dfa5  call    cs:__imp_GetModuleHandleW
0x18003dfac  nop     dword ptr [rax+rax+00h]
0x18003dfb1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003dfb8  jmp     short loc_18003DF98
```
