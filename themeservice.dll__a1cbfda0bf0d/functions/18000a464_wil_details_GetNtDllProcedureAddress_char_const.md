# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000a464`
- end: `0x18000a484`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006934`
- `0x180009b50`
- `0x180009b90`
- `0x18000c2dc`
- `0x18000cb00`
- `0x18000cb60`
- `0x18000cbd8`

## callees

- `0x18000a434`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a47d`

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
0x18000a464  push    rbx
0x18000a466  sub     rsp, 20h
0x18000a46a  mov     rbx, rcx
0x18000a46d  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000a472  mov     rcx, rax
0x18000a475  mov     rdx, rbx
0x18000a478  add     rsp, 20h
0x18000a47c  pop     rbx
0x18000a47d  jmp     cs:__imp_GetProcAddress
```
