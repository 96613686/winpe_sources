# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180022af0`
- end: `0x180022b11`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001874c`
- `0x18001b870`
- `0x180021030`
- `0x180021070`
- `0x180023b74`
- `0x180023ca0`
- `0x180023e2c`
- `0x180023ea4`

## callees

- `0x180022ac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022b04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022b04`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(LPCSTR lpProcName)
{
  HMODULE NtDllModuleHandle; // rax

  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  return GetProcAddress(NtDllModuleHandle, lpProcName);
}

```

## disassembly

```asm
0x180022af0  push    rbx
0x180022af2  sub     rsp, 20h
0x180022af6  mov     rbx, rcx
0x180022af9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180022afe  mov     rcx, rax; hModule
0x180022b01  mov     rdx, rbx; lpProcName
0x180022b04  call    cs:__imp_GetProcAddress
0x180022b0a  nop
0x180022b0b  add     rsp, 20h
0x180022b0f  pop     rbx
0x180022b10  retn
```
