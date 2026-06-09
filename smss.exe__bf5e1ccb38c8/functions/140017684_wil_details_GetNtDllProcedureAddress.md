# wil_details_GetNtDllProcedureAddress

- ea: `0x140017684`
- end: `0x1400176ba`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140016d44`
- `0x140016e3c`

## callees

- `0x140017684`
- `0x14001a220`
- `0x14001a254`

## pseudocode

```c
__int64 __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
{
  __int64 ModuleHandleW; // rax
  __int64 retaddr; // [rsp+28h] [rbp+0h]

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW();
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  return GetProcAddressForCaller(ModuleHandleW, a1, retaddr);
}

```

## disassembly

```asm
0x140017684  push    rbx
0x140017686  sub     rsp, 20h
0x14001768a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x140017691  mov     rbx, rcx
0x140017694  test    rax, rax
0x140017697  jnz     short loc_1400176A5
0x140017699  call    GetModuleHandleW
0x14001769e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1400176a5  mov     r8, [rsp+28h]
0x1400176aa  mov     rdx, rbx
0x1400176ad  mov     rcx, rax
0x1400176b0  add     rsp, 20h
0x1400176b4  pop     rbx
0x1400176b5  jmp     GetProcAddressForCaller
```
