# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000fe50`
- end: `0x18000fe70`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f7d0`
- `0x18000f810`
- `0x18000fb70`
- `0x180014a84`
- `0x1800181bc`
- `0x1800182e8`
- `0x18001876c`
- `0x1800187e4`
- `0x1800189c0`

## callees

- `0x180008e78`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe69`

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
0x18000fe50  push    rbx
0x18000fe52  sub     rsp, 20h
0x18000fe56  mov     rbx, rcx
0x18000fe59  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000fe5e  mov     rcx, rax
0x18000fe61  mov     rdx, rbx
0x18000fe64  add     rsp, 20h
0x18000fe68  pop     rbx
0x18000fe69  jmp     cs:__imp_GetProcAddress
```
