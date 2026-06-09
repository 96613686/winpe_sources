# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000363c`
- end: `0x18000365d`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003248`
- `0x1800035f0`
- `0x180015788`
- `0x1800202ec`
- `0x1800205d8`
- `0x1800260d0`
- `0x180026cc8`

## callees

- `0x180004690`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003650`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003650`

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
0x18000363c  push    rbx
0x18000363e  sub     rsp, 20h
0x180003642  mov     rbx, rcx
0x180003645  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000364a  mov     rcx, rax; hModule
0x18000364d  mov     rdx, rbx; lpProcName
0x180003650  call    cs:__imp_GetProcAddress
0x180003656  nop
0x180003657  add     rsp, 20h
0x18000365b  pop     rbx
0x18000365c  retn
```
