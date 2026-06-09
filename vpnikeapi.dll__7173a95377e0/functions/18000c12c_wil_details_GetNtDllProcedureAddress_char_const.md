# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000c12c`
- end: `0x18000c14c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007ba0`
- `0x18000add0`
- `0x18000ae10`
- `0x18000c850`
- `0x18000c97c`
- `0x18000ca3c`
- `0x18000cab4`
- `0x18000cc8c`

## callees

- `0x18000c0fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c145`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
{
  HMODULE NtDllModuleHandle; // rax

  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  return GetProcAddress(NtDllModuleHandle, a1);
}

```

## disassembly

```asm
0x18000c12c  push    rbx
0x18000c12e  sub     rsp, 20h
0x18000c132  mov     rbx, rcx
0x18000c135  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000c13a  mov     rcx, rax
0x18000c13d  mov     rdx, rbx
0x18000c140  add     rsp, 20h
0x18000c144  pop     rbx
0x18000c145  jmp     cs:__imp_GetProcAddress
```
