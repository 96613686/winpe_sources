# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180040e18`
- end: `0x180040e38`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003cb7c`
- `0x18003fad0`
- `0x18003fb10`
- `0x1800415c4`
- `0x180041624`
- `0x18004169c`
- `0x180041728`

## callees

- `0x180040de8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040e31`

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
0x180040e18  push    rbx
0x180040e1a  sub     rsp, 20h
0x180040e1e  mov     rbx, rcx
0x180040e21  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180040e26  mov     rcx, rax
0x180040e29  mov     rdx, rbx
0x180040e2c  add     rsp, 20h
0x180040e30  pop     rbx
0x180040e31  jmp     cs:__imp_GetProcAddress
```
