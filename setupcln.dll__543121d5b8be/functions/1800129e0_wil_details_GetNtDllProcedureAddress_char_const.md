# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800129e0`
- end: `0x180012a01`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d950`
- `0x180010d00`
- `0x180010d40`
- `0x180012be4`
- `0x180012c5c`
- `0x180012ce8`

## callees

- `0x1800129b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800129f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800129f4`

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
0x1800129e0  push    rbx
0x1800129e2  sub     rsp, 20h
0x1800129e6  mov     rbx, rcx
0x1800129e9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800129ee  mov     rcx, rax; hModule
0x1800129f1  mov     rdx, rbx; lpProcName
0x1800129f4  call    cs:__imp_GetProcAddress
0x1800129fa  nop
0x1800129fb  add     rsp, 20h
0x1800129ff  pop     rbx
0x180012a00  retn
```
